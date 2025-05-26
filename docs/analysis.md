# Études préliminaires

## Analyse du problème

Il est difficile pour un cycliste débutant ou qui ne connaît pas un quartier de savoir où circuler pour faire le trajet le plus sécuritaire. En permettant aux utilisateurs de donner leur avis sur les routes, ils peuvent avoir une meilleure idée de quelles rues utiliser et lesquelles éviter.

## Exigences

### Exigences fonctionnelles

- L'utilisateur doit pouvoir consulter une carte qui indique la sécurité des rues et pistes cyclables à ses alentours
- L'utilisateur doit pouvoir évaluer une partie d'une rue ou piste cyclable pour sa sécurité en donnant une note de 1 à 10
- L'utilisateur doit pouvoir enregistrer un trajet pour l'évaluer d'un coup
- L'application doit se recentrer sur la position de l'utilisateur à chaque ouverture
- L'utilisateur doit pouvoir marquer des points de services de vélo et des stationnements de vélo pour la communauté
- L'utilisateur doit pouvoir consulter les points de services de vélo et des stationnements de vélo marqués par les autres utilisateurs

### Exigences non fonctionnelles

- L'application doit être fluide
- L'application doit pouvoir rouler en arrière plan pour suivre l'itinéraire parcouru par l'utilisateur lorsqu'il l'enregistre

## Recherche de solutions

- Présenter les solutions existantes et justifier le choix retenu.
- Google Maps: Cette application n'est pas très pratique pour le vélo, puisqu'elle ne présente que l'information de si une rue possède ou non une piste cyclable. De plus, l'information est très souvent pas à jour ou fausse.
- OsmAnd: Cette application donne des meilleurs itinéraires que Google Maps pour le vélo mais n'offre pas plus d'information que Google Maps sur les types de pistes cyclables.
- Geovelo: Cette application est plus centrée sur la France et ne prend pas en compte l'opinion des autres utilisateurs.

## Méthodologie

Je créerai cette application en Kotlin avec Android Studio. 
Pour la carte de l’application, j’utiliserai MapBox. Ce service donne accès à des cartes de haute qualité et permet d’y ajouter des annotations, que j’utiliserai pour indiquer la qualité des routes. L’utilisation est gratuite jusqu’à 25’000 utilisateurs.

Pour les coordonnées formant les rues, j’utiliserai le Overpass API fourni par OpenStreetMap, qui est aussi utilisé par MapBox. En écrivant des queries style SQL, on a accès à des nodes avec des identifiants uniques ainsi que leur longitude et latitude.

Pour la base de données, je vais utiliser Superbase. Dans celle-ci seront stockées les évaluations des utilisateurs pour les rues à l’aide des ID uniques donnés par Overpass. 

Les positions des points de services et des stationnements de vélo y seront aussi stockés.
À l’aide de l’API de la ville de Montréal pour les annonces de travaux et de rues barrées, la carte pourra être mise à jour en temps réel.

L’interface de l’application sera prototypée à l’aide de Figma. Une fois celle-ci créée, je pourrai savoir exactement quoi stocker dans la base de données et je serai en mesure de commencer à programmer l’application.