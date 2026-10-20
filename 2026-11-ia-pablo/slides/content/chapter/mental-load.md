# Moins de charge mentale, moins de tokens

<div class="mt-6 grid grid-cols-2 gap-12">

<div>

### <mdi-brain class="text-[#e9ce37]"/> Des prompts toujours identiques

<div class="mt-3 text-base space-y-2">

- chaque lancement a la même forme : **un lien** (ticket ou PR), **le bon worktree**, **l'agent** choisi par l'état de la PR
- je ne me demande plus « comment je formule ça ? » — le format est déjà décidé
- les sorties ont toujours la même structure : je sais où regarder, je lis plus vite

</div>

<div class="mt-6 pl-4 border-l-4 border-[#e9ce37] text-lg font-600">
Je n'écris plus de prompts. Je lis des résultats.
</div>

</div>

<div>

### <mdi-cash-minus class="text-[#e9ce37]"/> Les tokens là où il y a du jugement

<div class="mt-3 text-base space-y-2">

- polling, transitions d'état, tri des reviews, CI verte ou non, sync des worktrees, mise à jour du checkout principal : **du PHP déterministe**
- un agent n'est lancé que s'il y a **vraiment quelque chose à faire** — et souvent un modèle rapide et pas cher
- plus de « regarde où en est ma PR » envoyé à un LLM pour rien

</div>

<div class="mt-6 stat">
<div class="bignum">0<small>&thinsp;token</small></div>
<div class="cap">pour savoir s'il y a quelque chose à faire</div>
</div>

</div>

</div>

<!--
Retour sur la checklist du matin : ce n'était pas le temps, c'était le changement de contexte. Un format de prompt fixe, c'est une décision de moins à chaque lancement.
Côté coût : tout ce qui est « boring » ne passe jamais par un LLM. Les tokens ne servent qu'aux étapes où il faut lire, comprendre, décider.
-->
