# Customize the generation, without forking

<div class="mt-4 grid grid-cols-[1.5fr_1fr] gap-8 items-start">

<div>

```php {all|7,10-11|14}
$dispatcher = new EventDispatcher();
$dispatcher->addSubscriber(new class implements EventSubscriberInterface {
    public static function getSubscribedEvents(): array
    {
        return [ClassGeneratedEvent::class => 'onClassGenerated'];
    }
    public function onClassGenerated(ClassGeneratedEvent $event): void
    {
        // every generated model implements your interface
        $event->getClassNode()->implements[]
            = new FullyQualified(App\Api\ApiModel::class);
    }
});
JaneOpenApi::build($options, $dispatcher)->generate($registry);
```

</div>

<div class="space-y-4 text-sm">

<div>
<div class="chip teal">lifecycle · read-only</div>
<div class="mt-1"><code>GenerationStarted</code>, <code>SchemaStarted</code>, <code>FileGenerated</code>…</div>
</div>

<div v-click="1">
<div class="chip">mutation · live references</div>
<div class="mt-1"><code>PropertyGuessedEvent</code>: swap a type, models <b>and</b> normalizers follow. <code>Class</code>/<code>PropertyGenerated</code>: the PhpParser AST</div>
</div>

<pre v-click="2" class="term"><span class="y">$</span> jane-openapi generate
 ➜ Guessing… <span class="ok">done (0.05s)</span>
 ➜ Generating… <span class="ok">done (0.30s)</span>
 ➜ 5 Models · 6 Normalizers · 1 Client
 <span class="ok">[OK]</span> Done in 0.35s</pre>

</div>

</div>

<div class="mt-4 text-xs opacity-60">
Experimental, built on <code>symfony/event-dispatcher</code>: event constructors are frozen, the list may grow, no <code>.jane-openapi</code> config entry yet.
</div>

<style>
.slidev-layout pre { font-size: 11.5px !important; line-height: 17px !important; }
</style>

<!--
~1 min. Before: customizing meant forking a generator class.
Click 2: the lifecycle events already power something everyone gets for free: the generate command finally tells you what it is doing. --quiet keeps it silent.
-->
