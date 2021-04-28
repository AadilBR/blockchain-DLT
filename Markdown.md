1 - Un arbre de merkle nécessite une paire de hashes pour produire un nouveau hash parent. Il faut donc absolument que le nombre de transactions qui produiront le Merkle root soit pair. Comment est géré le cas ou le nombre de transactions dans le Block à valider est impair pour générer un Merlke root ?

     => les hashes impairs passés à une fonction de hachage directemrnt.

2 - Dans le réseau bitcoin, Comment un nouveau noeud arrive t'il à retrouver ses pairs et ainsi rejoindre le réseau ? Expliquer le processus avec vos propres mots.

    => Bitcoin Core est un des clients pair à pair de la crypto-monnaie Bitcoin. Lorsque vous lancerez votre nœud tout neuf, il n'aura en mémoire que le block 0, ou genesis block, daté du 3 janvier 2009. La première tâche qu'il devra entreprendre sera donc de se synchroniser avec le reste du réseau, ce que l'on appelle une synchronisation initiale.

    Cette synchronisation initiale nécessite de réaliser les opérations suivantes :

    télécharger l'intégralité de la blockchain (environ 351Go),
    valider l'intégralité des transactions ayant jamais eu lieu, ainsi que l'intégralité des blocs minés jusqu'à aujourd'hui,
    réaliser un index de toutes les transactions,
    calculer et enregistrer la balance (ou unspent transaction output, souvent abrégé en UTXO) de toutes les adresses Bitcoin connues du réseau.

3 - Pouvez vous nommer au moins une personne qui a ou aurait pu influencer directement ou indirectement la création de Bitcoin par ses travaux (une personne qui n'a pas été nommée dans le cours)?

    => Stuart Haber qui a fait des travaux sur l'horodatage de documents digitaux.

4 - Avec vos propres recherches et grâce aux compétences acquises en cours pouvez vous expliquer comment une Blockchain crée un lien entre ses différents Blocks?

    => de ce que j'ai compris à l'issus de mes recherche c'est que chaque block d'une blockchain est lié au block précedent et au suivant par un hash block unique d'où l'idée de chaine de blocs.

5 - Quelle structure de données informatique peut représenter le mieux cette chaine de Block: https://en.wikipedia.org/wiki/List_of_data_structures ?

    => Structures basées sur le hachage : Hash tree

6 - Si je souhaite modifier une transaction de 10 bitcoin que j'ai effectué il y a 6 mois en une transaction de 1 Bitcoin, que dois je modifier dans la Blockchain et que dois je mettre en oeuvre pour que cette modification persiste ?
Est ce possible selon vous ?

    => en gros c'est une machine a remonter le temps qu'il faudrait.
    il faudrait pouvoir modifier l'horodatage d'un bloc ainsi que celui de tout les blocs qui ont suivit jusqu'a aujourd'hui pour que les hashes résultants soient concaténés a leur noeud voisin et passés à une fonction de hachage.
    Ainsi de suite jusqu'au ce qu'il ne reste plus qu'un seul hash qui sera le Merkle root et ceci afin d'avoir un concenssus.