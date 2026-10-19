# Choisir ce qui n'est *pas* un événement

<div class="mt-6 text-lg space-y-4">

- un seul chemin de retour en `draft`, et c'est une <b>commande</b>
- pas de détection de push : je pousse des dizaines de fois par jour, souvent juste pour faire tourner la CI.
  Une commande explicite est un <b>signal</b> ; un push est du <b>bruit</b>
- CI *pending* ne déclenche rien
- CI rouge pendant `needs-testing` ne déclenche rien non plus : une build cassée remontera au moment du merge, et interrompre la QA ne rend service à personne

</div>

<div class="mt-10 rounded-lg bg-#2b2b2a text-white p-6 text-xl">
La moitié du design d'une state machine, c'est choisir ce qui n'est <b>pas</b> un événement — et c'est la moitié qui ne reçoit presque aucune attention.
</div>
