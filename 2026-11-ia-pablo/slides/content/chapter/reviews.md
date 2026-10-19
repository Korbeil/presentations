# Qu'est-ce qu'une review ? *(plus dur que prévu)*

L'un des détails qui m'ont coûté bien plus d'itérations que prévu :

<div class="mt-6 text-base space-y-1.5">

- **les miennes sont exclues** : répondre à un commentaire sur ma propre PR crée une review à mon nom — je repasserais en draft juste pour répondre à une question
- **bots ignorés**, sauf s'ils sont explicitement autorisés
- seules les reviews **postérieures au dernier événement GitHub `ready_for_review`** comptent — un vrai timestamp, contrairement au verdict résumé ; une approbation d'un tour précédent ne fuit pas dans celui-ci
- **la dernière review par reviewer gagne** ; une review non approbatrice **bat toutes les approbations** : si quelqu'un a pris le temps d'écrire, je lis son feedback avant la QA

</div>

<div class="mt-8 rounded-lg bg-#f7e9a0 p-3 text-base">
Une state machine, ce n'est pas que le graphe : <b>ce sont toutes les règles fines autour.</b>
</div>
