# powerbi-supply-chain-diagnostic
Ce tableau de bord exécutif Power BI diagnostique les causes d'un OTIF de 92 % (objectif 95 %). Il dépasse le simple suivi pour analyser l'impact des délais fournisseurs, des goulets d'étranglement en centre de distribution et du panier moyen (AOV) par catégorie sur la performance logistique globale.

Le rapport met en lumière les relations directes entre la qualité/délais des fournisseurs, les goulets d'étranglement opérationnels dans les centres de distribution (DC) et les contraintes logistiques liées aux catégories à fort panier moyen.

## Architecture du rapport & navigation
Le rapport intègre une barre de navigation dynamique avec réinitialisation des filtres :

* **Executive Summary :** vue d'ensemble stratégique pour la direction, synthétisant les indicateurs clés de performance (OTIF, volumes, niveau de service).
* **Operational Risk :** analyse approfondie de la chaîne d'approvisionnement, isolant les retards fournisseurs, les taux de rejet qualité et l'impact direct sur les ruptures de stock.
* **Financial Performance :** exploration de l'impact financier par catégorie de produits, mettant en évidence la corrélation entre la valeur moyenne des commandes (AOV) et la charge logistique.
* **Glossary :** guide de référence rapide expliquant les acronymes clés et la méthodologie de calcul des métriques.
* **Analysis :** synthèse exécutive et conclusions diagnostiques regroupant les 3 constats majeurs et le plan d'action stratégique.
* **Bouton réinitialiser (Reset) :** bouton d'action permettant de réinitialiser instantanément tous les filtres appliqués sur la page.

## Principaux insights diagnostiques

1. **Effet retardateur qualité (1 mois) :** les taux de rejet élevés constatés en juillet sur les fournisseurs bas de tableau (**Eastern Food Logistics - 81 % OTIF** et **Value Foods Wholesale - 85 %**) ont épuisé les stocks de sécurité, provoquant un pic de ruptures de stock de 7 % en août.
2. **Goulet d'étranglement régional :** alors que les hubs majeurs (**Berlin Export Hub** et **Vilnius DC**) maintiennent un retard moyen faible de 0,11 jour, le centre **Riga Central DC** affiche un retard moyen de 0,20 jour (~5 heures de rétention/commande) bien qu'il soit le 3ᵉ générateur de revenus du réseau.
3. **Surcharge logistique des surgelés :** la catégorie Surgelés génère un panier moyen (AOV) plus de deux fois supérieur aux autres catégories du fait des achats volumineux. Cependant, cette saturation de la chaîne du froid entraîne le plus bas niveau de service du réseau (**89 % OTIF**), contrairement aux produits de boulangerie (**94 % OTIF**).

## Méthodologie & choix techniques

* **Modélisation des données (schéma en étoile) :** organisation optimale séparant la table de faits des transactions (commandes & expéditions) des tables de dimensions (fournisseurs, centres de distribution, produits, calendrier).
* **Mesures DAX avancées :** création de formules DAX sur-mesure pour le calcul dynamique de l'OTIF %, du panier moyen, des jours de retard moyens et des indicateurs de décalage temporel.
* **Conception orientée décision :** priorisation de la lisibilité exécutive via l'étiquetage direct des données, le nettoyage des légendes superflues et l'intégration d'encadrés narratifs d'analyse.

## Plan d'action stratégique proposé

* **Gestion fournisseurs :** audit qualité strict des fournisseurs à risque (**Eastern Food** & **Value Foods**) et mise en place d'un stock tampon de 2 semaines avant le pic du T3.
* **Optimisation de Riga Central DC :** réorganisation des flux d'expédition et révision des fréquences de transporteurs pour aligner la vitesse de Riga sur celles de Berlin et Vilnius.
* **Capacité chaîne du froid :** réservation de capacités frigorifiques dédiées et lissage des créneaux de livraison pour sécuriser les commandes surgelés à fort AOV.
