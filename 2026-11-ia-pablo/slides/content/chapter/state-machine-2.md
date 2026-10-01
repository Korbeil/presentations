<div class="mt-2 text-lg opacity-80">Ce que le poller surveille, à chaque tour :</div>

```php
public const POLL_CHECKS = [
    State::Draft->value         => ['checkCiRed', 'checkCiGreen'],
    State::ReadyToReview->value => ['checkCiRed', 'checkReviews'],
    State::NeedsTesting->value  => ['checkFailureSignal'],
];
```

<div class="mt-10 text-xl">
Autre différence avec les frameworks d'agents : les nœuds ne sont pas des étapes de raisonnement <i>(plan, search, summarize, critique)</i>, mais <b>les états d'une PR dans une vraie équipe</b> — le graphe n'est pas l'agent, c'est le processus dans lequel je travaille déjà.
</div>

<div class="mt-8 text-lg opacity-80">
C'est ce qui le rend stable au fil des sorties de modèles, avec prompts et modèles vivant dans les nœuds.
</div>
