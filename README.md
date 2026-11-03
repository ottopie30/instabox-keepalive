# instabox-keepalive

Réveille la sandbox InstaBox toutes les 10 minutes pour qu'elle ne se mette pas
en pause d'inactivité pendant que le grabber Oracle tourne dessus.

Le GET sur le port publié (`9119`) réveille la machine ; elle répond `302` puis
`200` sur `/login`. Un `409` signifie cooldown après max-run (8 h) : le tick
suivant repart.

Ne pas supprimer : sans ce ping, la sandbox se fige au bout de 30 min.
