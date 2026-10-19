# Ce que le poller surveille

Une deuxième table, dans `Poller.php` : ce que chaque état surveillé a le droit de vérifier, à chaque tour.

```php
public const POLL_CHECKS = [
    State::Draft->value         => ['checkCiRed', 'checkCiGreen'],
    State::CiRed->value         => ['checkCiGreen'],
    State::ReadyToReview->value => ['checkCiRed', 'checkReviews'],
    State::WaitingReview->value => ['checkCiRed', 'checkReviews'],
    State::Approved->value      => ['checkCiRed'],
    State::NeedsTesting->value  => ['checkFailureSignal'],
];
```

<div class="mt-8 text-xl">
Dans les frameworks d'agents, les nœuds sont des étapes de raisonnement <i>(plan, search, summarize, critique)</i>. Ici, ce sont <b>les états d'une PR dans une vraie équipe</b> : le graphe n'est pas l'agent, c'est le processus dans lequel je travaille déjà.
</div>

<div class="mt-6 text-lg opacity-80">
C'est ce qui le garde stable d'une sortie de modèle à l'autre : prompts et modèles vivent dans les nœuds.
</div>
