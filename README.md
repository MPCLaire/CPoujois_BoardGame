# CPoujois_BoardGame
 
Attention, Visual Studio étant particulièrement capricieux, il faut l'ouvrir et générer la solution pour avoir tout le prjet :)

Pour le fonctionnement du mini-jeu de collecte, j'ai d'abord créé une nouvelle map. J'ai réutilisé le BP_ThirdPersonCharacter pour les mouvements. 
Les objets collectables BP_ItemBonus et BP_ItemMalus sont des enfants de la classe cpp Collectible. À l'intérieur, il y a une fonction "PickUp" qui s'active lorsque je rentre dans la box collision d'un des items.
Il y a trois variables, une booléenne IsBonus qui se set à l'intérieur des items, et deux integer ScoreBonus et ScoreMalus. Dans la fonction PickUp, je viens vérifier si 
l'item est un bonus, si oui je donne à l'input Score de la fonction la valeur de ScoreBonus, sinon je lui donne la valeur de ScoreMalus, puis je détruit l'item. La gestion
de l'augmentation du score se fait en blueprint.
Pour le timer, j'ai une fonction qui démarre le timer en lui donnant sa durée (elle est appelée dans le level blueprint), puis elle appelle une autre fonction qui set un timer
d'une seconde. Toutes les secondes, la variable "RemainingTime" se décrémente. Enfin, je vérifie si elle est arrivée à 0, et si c'est le cas, je crée le widget de fin, qui met pause au jeu et qui
permet de revenir à la map principale. 
Les fonctions UpdateTimer et GetScore communiquent avec des widgets pour afficher les informations à l'écran. 
Une fois le mini-jeu terminé, le score final est enregistré dans la structure dans le Game Instance.