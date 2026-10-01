# Qu'est-ce qu'une review ? *(c'était plus dur que prévu)*

Des **trois** détails qui ont coûté plus d'itérations que prévu, celui-ci est le pire :

<div class="mt-6 text-base space-y-1.5">

- **les miennes sont exclues** : répondre à un commentaire sur ma propre PR crée un review à mon nom — je repasserais en draft juste pour répondre à une question
- **bots ignorés** sauf s'ils sont explicitement autorisés
- seules les reviews **postérieures au dernier événement GitHub `ready_for_review`** comptent — un vrai timestamp, contrairement au verdict résumé ; une approbation qui traîne depuis un tour précédent ne fuite pas dans celui-ci
- **la dernière review par reviewer gagne** ; une review non-approbative **bat toute approbation** : si quelqu'un a pris le temps d'écrire, je lis le feedback avant la QA

</div>

<div class="mt-8 rounded-lg bg-#f7e9a0 p-3 text-base">
Chacune de ces règles corrige un bug vécu, d'abord remonté par le dashboard. Une state machine n'est pas juste un graphe d'états : <b>ce sont toutes les règles fines autour.</b>

</div>
