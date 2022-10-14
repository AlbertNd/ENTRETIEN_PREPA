# Visualiser des données dans Power BI 

#### Présentation de l’utilisation des objets visuels Power BI
- Les objets visuels Power BI sont des graphiques et éléments visuels utilisé pour donner vie aux données. elle permettent de partager des analyses, d'ameliorer la comprehension, la rétention et l'attrait. Enfin elles aident à prendre des decision rapides. 

#### Ajouter des éléments de visualisation aux rapports

- Les objets visuels vous permettent de présenter les informations et **insights** importants découverts dans les données.
- Chaque objet visuel est représenté par une icône dans le volet Visualisations.

![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/2-add-visualization-ssm.png)

#### Choisir une visualisation efficace

- Lorsque on sélectionne les champs que l'on souhaite afficher dans une visualisation, on peut faire des essais avec tous les différents types de visualisation pour trouver celui qui correspond le mieux aux besoins. 
    - Il est aussi possible de télécharger d’autres objets visuels à partir de Microsoft AppSource ou d'importer des visuels personnalisés.
- **Les differents types de visualisation disponible dans Power Bi :**
    1. **Visualisations tableau et matrice**
        - **La visualisation tableau** 
            - Le tableau est une grille qui contient des données associées dans une série logique de lignes et de colonnes. La table prend en charge deux dimensions et peut également contenir des en-têtes et une ligne pour les totaux.
        - **La visualisation matrice** 
            - Elle permet de sélectionner un ou plusieurs éléments (lignes, colonnes, valeurs) dans la matrice pour mettre en surbrillance d’autres objets visuels sur la page de rapport.
    2. **Graphiques à barres et histogrammes**
        - Les graphiques à barres et d’histogrammes présentent des données spécifiques à travers différentes catégories dans un format **empilé** ou en **cluster**. Le format Empilé entasse les éléments d’information les uns sur les autres.
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-stacked-bar-column-chart-visualization-ss.png)

    3. **Graphiques en courbes et en aires**
        - Les visualisations Graphique en courbes et Graphique en aires aident à présenter des tendances dans le temps. Le graphique en aires de base se base sur le graphique en courbes, avec la zone comprise entre l’axe et la ligne remplie. La principale différence entre ces deux types de graphiques est que le graphique en aires met en évidence l’amplitude des changements au fil du temps.

        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-area-chart-visualization-ss.png)

    4. **Graphique à secteurs, graphique en anneau et Treemaps**
        - Les visualisations Graphique à secteurs, Graphique en anneau et Treemap vous montrent la proportion de chaque partie par rapport à l’ensemble, en divisant les données en segments.
            - *Ces graphiques conviennent mieux pour illustrer des pourcentages, par exemple les cinq meilleures ventes par produit ou par pays, ou toute autre catégorie disponible.*
        - La visualisation Treemap affiche les données sous la forme d’un ensemble de rectangles imbriqués.
            - *Chaque niveau de la hiérarchie est représenté par un rectangle de couleur (branche) contenant des rectangles plus petits (feuilles). L’espace à l’intérieur de chaque rectangle est alloué en fonction de la valeur mesurée. Les rectangles sont organisés par taille, du coin supérieur gauche (le plus grand) au coin inférieur droit (le plus petit).*
            - Une Treemap est idéale pour visualiser :
                - De grandes quantités de données hiérarchiques lorsqu’un graphique à barres ne peut pas gérer efficacement le grand nombre de valeurs.
                - Les proportions entre chaque partie et l’ensemble.
                - Le motif de distribution de la mesure entre chaque niveau de catégories dans la hiérarchie.
                - Les attributs, en utilisant le codage par taille et couleur.
                - Les motifs, les valeurs hors norme, les contributeurs les plus importants et les exceptions.

            ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-treemap-visualization-ss.png)

    5. **Graphiques combinés**
        - La visualisation combinée est une combinaison d’un histogramme et d’un graphique en courbes qui peut avoir un ou deux axes Y. La combinaison de deux graphiques en un seul.  
        - Il permet de :
            - Comparer plusieurs mesures avec des plages de valeurs différentes.
            - Illustrer la corrélation entre deux mesures dans un seul objet visuel.
            - Déterminer si une mesure correspond à la cible définie par une autre mesure
            - Économiser de l’espace sur la page de votre rapport.

        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-line-clustered-column-chart-visualization-ss.png)

    6. **Visualisation carte**
        - La visualisation carte présente une seule valeur : un point de données unique. 
            - Ce type de visualisation est idéal pour visualiser des statistiques importantes que l'on souhaite suivre sur le tableau de bord ou rapport, comme la valeur totale, les ventes annuelles à ce jour ou l’évolution d’une année sur l’autre.
        - La visualisation carte multiligne affiche un ou plusieurs points de données, avec un point de données pour chaque ligne.

        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-card-visualizations-ss.png)

    7. **Visualisation d’entonnoir** 
        - La visualisation entonnoir affiche un processus linéaire qui comporte des étapes séquentielles connectées, où les éléments circulent de façon séquentielle d’une étape à l’autre.
            - *ils sont utiles pour représenter un workflow, comme le passage d’un prospect de vente à un prospect qualifié, par le biais d’une proposition et d’une vente.*
                - *Lorsque les données sont séquentielles et passent par au moins quatre étapes.*
                - *Lorsque le nombre d’éléments de la première étape est supposé être supérieur au nombre d’éléments de l’étape finale.*
                - *Pour calculer un résultat potentiel (revenu, ventes, transactions, etc.) par étapes.*
                - *Pour calculer et suivre les taux de conversion et de rétention.*
                - *Pour révéler les goulots d’étranglement dans un processus linéaire.*
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-funnel-visualization-ss.png)
    
    8. **Graphique en jauge**
        - Un graphique en jauge radiale a un arc circulaire et affiche une valeur unique qui mesure la progression vers un objectif ou une cible. Elles occupent beaucoup de place en comparaison avec les données qu’elles fournissent. Il est plus efficace d’utiliser une paire de jauges avec une ***[sparkline](https://learn.microsoft.com/fr-fr/power-bi/create-reports/power-bi-sparklines-tables)*** pour que les utilisateurs puissent voir la tendance et savoir comment procéder.
            - *La valeur à la fin de l’arc représente la valeur maximale par défaut, qui est toujours le double de la valeur réelle. L’ombrage de l’arc représente la progression vers cette cible. La valeur à l’intérieur de l’arc représente la valeur de progression. Power BI répartit toutes les valeurs possibles uniformément le long de l’arc, de la valeur minimale (la plus à gauche) à la valeur maximale (la plus à droite).*
            - Pour créer un objet visuel réaliste, Il faut spécifier chacune des valeurs.
                - Le montant dans les champs Valeur cible, 
                - La valeur minimale et Valeur maximale dans le volet Visualisation.

        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-gauge-visualization-ss.png)
    
    9. **Visualisation en cascade**
        - La visualisation en cascade (également appelée « diagramme de pont ») montre un total cumulé au fur que des valeurs sont ajoutées ou soustraites, ce qui est utile pour afficher une série d’évolutions positives et négatives. 
            - *Le graphique se compose de colonnes à code de couleurs, ce qui vous permet d’identifier rapidement les augmentations et les diminutions.* 
        - Les colonnes de valeur initiale et finale commencent souvent sur l’axe horizontal, tandis que les valeurs intermédiaires sont des colonnes flottantes
        - Il sont utile pour: 
            - *Visualiser les évolutions dans le temps ou dans différentes catégories.*
            - *Auditer les modifications majeures qui contribuent à la valeur totale.*
            - *Tracer le bénéfice annuel de l'organisation en présentant différentes sources de revenus pour déterminer plus facilement le bénéfice total (ou la perte).*
            - *Illustrer les effectifs de début et de fin de l'organisation au cours d’une année.*
            - *Visualiser l’argent gagné et dépensé chaque mois et le solde actuel de du compte.*
    10. **Graphique à nuages de points** 
        - La visualisation de graphique à nuages de points est efficace pour comparer un grand nombre de points de données sans tenir compte du temps.
            - Il comporte deux axes de valeur a afficher: 
                - un jeu de données numériques le long d’un axe horizontal
                - un jeu de valeurs numériques le long d’un axe vertical
        - Ils permettent d’effectuer les opérations suivantes:
            - Afficher les relations entre deux valeurs numériques.
            - Tracer deux groupes de nombres sous la forme d’une série de coordonnées x et y
            - Transformer l’axe horizontal en échelle logarithmique.
            - Afficher les données de la feuille de calcul qui incluent des paires ou des jeux de valeurs groupés.
            - Afficher des motifs dans de grands jeux de données, par exemple en affichant des tendances linéaires ou non linéaires, des clusters et des valeurs hors norme.
            - Comparer un grand nombre de points de données sans tenir compte du temps. Plus on inclue de données dans un graphique à nuages de points, meilleures sont les comparaisons effectué.
        - Il est possible de définir le nombre de points de données, jusqu’à un **maximum de 10 000**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-scatter-chart-visualization-ss.png)
    
    11. **Cartes**
        - Power BI s’intègre à Bing Maps pour fournir des coordonnées cartographiques par défaut (processus appelé « géocodage »), ce qui permet de créer des cartes
        - Une carte de base (carte à bulles) est utilisée pour associer des informations catégoriques et quantitatives à des emplacements spatiaux. Ce type d’objet visuel de carte affiche les emplacements géographiques précis de points de données sur une carte
            - ***Une carte de remplissage***:
                - utilise des ombrages, des teintes ou des motifs pour afficher la variation d’une valeur à travers une région géographique.
            - ***Une carte de forme***
                -  utilise des couleurs pour afficher des comparaisons relatives de régions géographiques. 
            - ***Une carte ArcGIS*** 
                - Afficher des informations graphiques de manière plus interactive.

        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-map-visualization-ss.png)
    
    12. **Visualisation segment**
        - La visualisation segment est un graphique autonome qui peut être utilisé **pour filtrer les autres objets visuels de la page**. 
            - *Les segments fournissent un mode de filtrage plus avancé et personnalisé par rapport au volet **Filtres**, qui est adapté aux opérations de filtrage plus basiques.* 
        - Les segments se présentent dans de nombreux formats différents, notamment ***liste***, ***liste déroulante*** et ***boutons***, et peuvent être mis en forme pour permettre la sélection d’une seule, de plusieurs ou de toutes les valeurs disponibles.
        - Ils sont utilent pour: 
            - Visualiser des filtres couramment utilisés ou importants sur le canevas de rapport pour un accès plus facile.
            - Simplifier la capacité à voir l’état filtré actuel sans avoir à ouvrir une liste déroulante.
            - Filtrer les colonnes inutiles et masquées dans les tables de données.
            - Créer des rapports plus ciblés en plaçant des segments en regard d’objets visuels importants.
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-slicer-visualization-ss.png)

    13. **Visualisation Q&R**
        - La visualisation Q&R permet de poser des questions en langage naturel et d’obtenir des réponses sous la forme d’un objet visuel
            - *Ce type de visualisation aide à créer des objets visuels dans le rapport, et peut également être utilisé comme outil permettant aux consommateurs d’obtenir rapidement des réponse*
        - Une visualisation Q&R se compose des quatre composants principaux:
            1. La zone de question, où les utilisateurs entrent leur question et voient des suggestions pour les aider à compléter la question.
            2. Une liste préremplie de questions suggérées.
            3. Une icône que les utilisateurs peuvent sélectionner pour convertir un objet visuel Q&R en un objet visuel standard.
            4. Une icône que les utilisateurs peuvent sélectionner pour ouvrir les outils de Q&R, pour permettre aux concepteurs de configurer le moteur de langage naturel sous-jacent.    
                - Lorsque on entre des requêtes en langage naturel dans Q&R avec Power BI, on peut spécifier le type d’objet visuel dans la requête. 
                - ***Par exemple pour implémenter le Chiffre d'affaires net par pays.**
                
                ![](https://learn.microsoft.com/fr-fr/training/modules/visuals-power-bi/media/3-question-answer-visualization-ss.png)

#### Mettre en forme et configurer des visualisations
