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

public const POLL_CHECKS = [
    State::Draft->value         => ['checkCiRed', 'checkCiGreen'],
    State::ReadyToReview->value => ['checkCiRed', 'checkReviews'],
    State::NeedsTesting->value  => ['checkFailureSignal'],
];
```

<div class="mt-3 text-base space-y-1">

- chaque ligne : comment l'état s'affiche, ce qui tourne à l'entrée, si le poller le surveille
- ajouter une étape = une ligne et une méthode, <b>pas un refactor</b> ; un seul handler d'entrée mutualisé entre poller, commands et overrides manuels — les transitions ne divergent jamais
- autre différence avec les frameworks d'agents : les nœuds ne sont pas des étapes de raisonnement (plan, search, summarize, critique),

mais <b>les états d'une PR dans une vraie équipe</b> — le graphe n'est pas l'agent, c'est le processus dans lequel je travaille déjà. C'est ce qui le rend stable au fil des sorties de modèles, avec prompts et modèles vivant dans les nœuds.

</div>
