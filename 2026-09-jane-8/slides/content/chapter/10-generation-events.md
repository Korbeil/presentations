# Generation events

<div class="grid grid-cols-2 gap-6 text-sm mt-2">

<div>

```php
$dispatcher = new EventDispatcher();
$dispatcher->addSubscriber(new class implements EventSubscriberInterface {
    public function getSubscribedEvents(): array
    {
        return [PropertyGuessedEvent::class => 'onPropertyGuessed'];
    }

    public function onPropertyGuessed(
        PropertyGuessedEvent $event
    ): void {
        // replace the guessed type: flows into
        // models AND normalizers
        $event->getProperty()->setType(
            new Type($event->getProperty()->getObject(), 'int')
        );
    }
});

JaneOpenApi::build($options, $dispatcher);
```

</div>

<div>

<v-click>

### Intercept the generator

([ADR 0013](https://github.com/janephp/janephp/blob/next/docs/contributing/adrs/0013-generation-events.md), experimental — [#859](https://github.com/janephp/janephp/issues/859))

</v-click>

<v-click>

**Lifecycle events** — `Generation*`, `Schema*`, `Guessing*`, `Generating*`, `FileGenerated` — what console progress is built on

</v-click>

<v-click>

**Mutation events** — `PropertyGuessedEvent` (types), `PropertyGeneratedEvent` / `ClassGeneratedEvent` (PhpParser AST: psalm tags, methods, traits…)

</v-click>

<v-clicks>

<div class="text-xs text-gray-800">

Throwing listener → generation aborts · programmatic only, no `.jane` config option yet

</div>

</v-clicks>

</div>

</div>
