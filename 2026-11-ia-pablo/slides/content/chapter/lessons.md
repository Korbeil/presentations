# La concevoir m'a appris quelques choses

<div class="mt-8 text-lg space-y-7">

- **Choisir ce qui n'est *pas* un événement.** CI *pending* → rien ; CI rouge en `needs-testing` → rien.
- **Un seul chemin de retour vers `draft`** : une commande explicite, jamais un `git push` brut. Une commande est un signal — un push est du bruit.
- **Les reviews, définies** : les miennes exclues, bots ignorés sauf autorisés, la dernière par reviewer gagne, une non-approbation bat toute approbation.
- **Une CI verte est une politique** : `ignore_checks: ["approval"]` — deux gates, un mot.
- **Pas tout mérite un LLM** : l'intelligence tient dans cinq fichiers markdown ; le reste, c'est une state machine avec un meilleur nom.

</div>
