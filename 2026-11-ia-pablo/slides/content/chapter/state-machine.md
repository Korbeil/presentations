# Graph engineering ? Une state machine, un nom à la mode

« Graph engineering » ? C'est une state machine avec un meilleur nom. Et son moteur tient littéralement dans une table, dans une classe (`StateMachine.php`) :

```php
public function states(): array
{
    return [
        State::InProgress->value => ['emoji' => '🔨', 'label' => 'in-progress',
            'onEnter' => $this->enterInProgress(...), 'polled' => false],
        State::Draft->value      => ['emoji' => '📝', 'label' => 'draft',
            'onEnter' => $this->enterDraft(...), 'polled' => true],
        State::CiRed->value      => ['emoji' => '🔴', 'label' => 'ci-red',
            'onEnter' => $this->enterCiRed(...), 'polled' => true],
        // ... 9 états au total
    ];
}
```

<div class="mt-4 text-base space-y-1">

- chaque ligne : comment l'état s'affiche, ce qui tourne à l'entrée, si le poller le surveille
- ajouter une étape = une ligne et une méthode, <b>pas un refactor</b> ; un seul handler d'entrée mutualisé entre poller, commands et overrides manuels — les transitions ne divergent jamais

</div>

<style>
.slidev-layout h1 { font-size: 32px; line-height: 36px; }
.slidev-layout pre { font-size: 10.5px !important; line-height: 15px !important; padding-top: 0.4rem; padding-bottom: 0.4rem; }
.slidev-layout li { line-height: 24px; }
</style>
