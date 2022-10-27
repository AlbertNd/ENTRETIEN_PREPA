# Créer des tableaux de bord dans Power BI
- Les tableaux de bord Microsoft Power BI Microsoft sont différents des rapports Power BI. 
    - Les tableaux de bord permettent aux consommateurs de rapports de créer un seul artefact de données. Ils euvent être constitués de visuels épinglés issus de différents rapports. 
    1. **Les tableaux de bord**: Il peuvent contenir des visuels de differents jeux de données.
        - ***Seul le service Power BI inclut la fonctionnalité de tableaux de bord Power BI***
        - Il est possible d'afficher les tableau de bord sur mobile mais il n'est pas possible de les créer dessus
    2. **Les rapport** : Ils utiliser les données d'un seul jeu de donnée.
- **NB : Seul le service Power BI inclut la fonctionnalité de tableaux de bord Power BI**
    - *Il faut prendre les tableaux de bord comme la vitrine d’une boulangerie où on souhaite présenter l’essentiel des produits, alors que c’est à l’intérieur du magasin (et dans les rapports dans Power BI Desktop) que tous les ingrédients sont transformés pour remplir la vitrine.*

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/01-dashboard-example-ss.png)

1. **Tableaux de bord et rapports** 
    - Similarités et differences etre les tableaux de bord et les rapports 
        - Les tableaux de bord peuvent être créées à partir de jeux de données ou de rapports multiples.
        - Les tableaux de bord n’ont pas les volets **Filtre**, **Visualisation** et **Champs** qu’il y a dans Power BI Desktop. 
            - On ne peut donc ni ajouter de nouveaux filtres et segments, ni apporter des modifications.
        - Les tableaux de bord ne peuvent avoir qu’une seule page, alors que les rapports peuvent comprendre plusieurs pages.
        - On ne peut pas voir le jeu de données sous-jacent directement sur un tableau de bord, mais on peut le voir dans un rapport, sous l’onglet **Données** dans Power BI Desktop.
        - Les tableaux de bord et les rapports peuvent être actualisés pour afficher les données les plus récentes.
        - Les tableaux de bord permettent à un utilisateur d’épingler des visuels de différents rapports et jeux de données à un seul canevas, ce qui simplifie le groupement de ce qui est important pour l’utilisateur. 
        - Les rapports sont plus concentrés sur la possibilité de visualiser et d’appliquer des transformations à un seul jeu de données. 
            - *Il faut voir les tableaux de bord comme l’étape suivante à franchir après avoir créé vos rapports dans Power BI Desktop.*
2. **Gérer des vignettes sur un tableau de bord**
    - Les vignettes sont les éléments de rapport individuels, ou instantanés, des données qui sont ensuite épinglées à un tableau de bord. 
        - Elles peuvent provenir d’une multitude d’emplacements, notamment des rapports, des jeux de données, d’autres tableaux de bord, Microsoft Excel ou SQL Server Reporting Services, entre autres. 
        - Lors de l’épinglage d’un élément de rapport à un tableau de bord, on crée une connexion directe entre le tableau de bord et le rapport d’où provient l’instantané.
3. **Épingler une vignette à un tableau de bord**

    [Voir doc Présentation des vignettes de tableaux de bord](https://learn.microsoft.com/fr-fr/power-bi/create-reports/service-dashboard-tiles)

    - Une fois les rapport téléchargé dans le service Power BI et affiché, pour créer un tableau de bord on peut épingler soit une page de rapport entière, soit des vignettes individuelles.
        - Le processus d’épinglage extrait des visuels du rapport et les « épingle » à un tableau de bord pour faciliter leur affichage. 
            - Lorsque on apporte des modifications aux visuels dans le rapport, et qu'on le republie dans Power BI Service, les modifications sont reflétées dans le tableau de bord.
        - Pour examiner un visuel spécifique, il faut penser à épingler la vignette à un nouveau tableau de bord pour un affichage facile. 
            - On peut effectuer cette tâche en pointant sur le visuel => dans l’en-tête du visuel, sélection de l’icône **Épingler le visuel**

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/01-pin-visual-button-ss.png)

            - Une fois l'icone sélectionné, une fenêtre s’affiche, dans laquelle on peut choisir d’épingler ce visuel à un tableau de bord nouveau ou existant. 

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/01-pin-dashboard-window-ss.png)
            
            - Une fois qu'on a sélectionné **Épingler**, on est redirigé vers le nouveau tableau de bord, où on vient d’épingler une vignette provenant du rapport. 
                - On peut redimensionner et déplacer ce visuel dans le tableau de bord en le sélectionnant, puis en le faisant glisser avant de le déposer.

                ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/01-pin-single-tile-ss.png)

            - ***L’un des principaux avantages d’un tableau de bord est la possibilité d’épingler un visuel issu d’un jeu de données différent.***
3. **Épingler une vignette à partir d’un autre rapport** 
    - Et si on souhaite épingler un visuel d’un autre rapport (et d’un autre jeu de données) à un tableau de bord existant:
        - On pointe sur le visuel dans le rapport d’origine => sélection de l’icône **Épingler**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/01-pin-dash-ss.png)

4. **le tableaux**
    - Lorsque on accéde au tableau de bord, les deux visuels sont épinglés, indépendamment du jeu de données sous-jacent.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/01-pin-tiles-ss.png)

#### Configurer des alertes de données
-  Les alertes de données peuvent être utilisées pour indiquer si un point des données spécifique est supérieur, inférieur ou égal à un seuil défini.
    - ***Ces alertes sont des fonctionnalités qui ne sont accessibles que sur le service Power BI et sont disponibles sur des éléments de rapport tels que les visuels, les jauges et les cartes KPI.*** 
1. **Configurer les alertes** 

    [ Voir Doc Alerte de données dans le service Power BI.](https://learn.microsoft.com/fr-fr/power-bi/create-reports/service-set-data-alerts)

    - Une fois les rapports chargés dans le service Power BI et que les visuels choisis sont épinglés à un tableau de bord:
        1. => Sélection des **points de suspension (...)** dans le coin de la vignette pour laquelle on veut définir une alarme, puis sélection **Gérer les alertes**.
        2. Dans la fenêtre:
            - sélection **+ Ajouter une règle d’alerte**, ce qui ajoute une nouvelle alerte. 
            - S'assurer que le commutateur bascule **Active est Activé**, 
            - Nommer l’alerte
            - Définir la condition. *(On choisi le seuil pour lequel on souhaite créer l’alerte, ce qui inclut des options pour Au-dessus ou En-dessous d’un seuil spécifique)*.
            - Sélection de la fréquence d'envois des alertes.
                -  Ces alertes sont envoyées directement au centre de notification dans Power BI, ***Mais il est possible de configurer des e-mails qui seront envoyés si le seuil est franchi.***
        3. **Enregistrer et fermer**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/02-manage-alerts-button-ss.png)

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/02-manage-alerts-window-options-ssm.png)

    - *Cette fonctionnalité est accessible à toute personne ayant accès au tableau de bord et pas seulement à son propriétaire. Les utilisateurs peuvent les personnaliser afin que toute personne qui utilise le rapport puisse avoir son propre ensemble d’alertes. De plus, on peut activer ou désactiver l’alerte à l’aide du commutateur bascule.*

#### Explorer les données en posant des questions

1. **Fonctionnalité question réponses** 
- La fonctionnalité Questions et réponses est un outils de Power BI Desktop qui vous permet de poser des questions en langage naturel sur les données.
- Pour localiser la fonctionnalité **Questions et réponses**, 
    - Dans le tableau de bord dans le service Power BI voir le long du ruban supérieur, il y a la zone de recherche **Poser une question sur vos données.** 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/03-question-answer-feature-ss.png)

    - Ce qui mene à la page suivante 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/03-question-answer-visual-example-ss.png)

- Le visuel **Question et reponse** est composé des trois elements: 
    1. **Zone de question**: dans cet élément, l’utilisateur peut entrer sa question sur les données.
        - *Exemple de question : Quel a été le montant moyen des ventes par catégorie ? La saisie de cette question déclenche le moteur d’analyse en langage naturel de Power BI pour analyser et déterminer les données appropriées à afficher.*
    2. **Vignettes de suggestion préremplies** : cet élément contient des vignettes avec des suggestions préremplies pour les questions que l’utilisateur peut envisager de poser. Lorsque l’utilisateur sélectionne l’une de ces vignettes, l’analyse s’affiche. 
        - *Exemple, si on sélectionne la vignette Noms de catégories de produits en tête des ventes de mars, on obient le visuel ci-dessous, converti à partir du visuel Questions et réponses.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/03-converting-visual-icon-ss.png)

    3. **Icône Épingler le visuel**: cette icône se trouve en haut à droite du visuel.
        - ***La sélection de l’icône Épingler un visuel vous permet d’épingler le visuel à un tableau de bord nouveau ou existant***

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/03-pin-visual-ssm.png)

#### Ajouter un thème de tableau de bord
- Lors de la création de tableaux de bord, il faut s'assurer que le même thème est appliqué aux tableaux de bord pour créer une image cohérente. 
    - On peut également appliquer un thème spécifique aux rapports et aux tableaux de bord afin que tous les éléments ou vignettes du rapport soient uniformes. Power BI a la fonctionnalité nécessaire pour appliquer un thème directement à tous les visuels d’un rapport.
1. **Thèmes dans Power BI**
    - => Dans service Power Bi => Dans un tableau de bord => Selection du menu deroulant d'edition => Selection **Theme du tableau de bord** 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/04-dashboard-theme-button-ssm.png) 

    - Cette sélection ouvre une fenêtre dans laquelle on peut choisir parmi divers thèmes, notamment **Clair** (le thème par défaut), **Foncé**, **Adapté aux daltoniens** et **Personnalisé**, où on peut creer son propre thème. Il est aussi possible de charger son propre thème JSON ou télécharger un thème.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/04-dashboard-theme-ss.png)

    - En choisissant **personalisé**, il est possible d'ajouter une igame d'arriere plan ou de modifier la couleur d'arriere-plan, la couleur de la vignette, l'opacité, la couleur de police ... 
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/04-dashboard-theme-custom-ss.png)

#### Épingler une page de rapport dynamique à un tableau de bord
- Le processus de création de rapports et de tableaux de bord est itératif. À mesure que les données sont actualisées et que les besoins évoluent, les rapports et les tableaux de bord doivent également être mis à jour, à la fois au niveau de vos filtres ou segments, mais aussi des éléments de rapport, graphiques et cartes.
1. **Épingler une page dynamique**
    - Lorsque on épingle un élément visuel, on peut l’ajouter à un nouveau tableau de bord ou à un tableau de bord existant.
        - Il est possible de faire de même avec des rapports complets : 
            - Quand on épingle une page de rapport, tous les éléments visuels du rapport sont épinglés à un tableau de bord et restent dynamiques, ce qui signifie que toutes les modifications apportées au rapport sont immédiatement reflétées dans le tableau de bord auquel on a épinglé le rapport.
    - L’épinglage d’une page dynamique est un moyen simple d’épingler tous les éléments visuels à la fois, ce qui évite tout reformatage dans le tableau de bord. 
    - Pour épingler une page dynamique
        - => sélection des **points de suspension (...)** dans la barre de navigation du rapport, puis choisisir **Épingler à un tableau de bord**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/05-pin-live-page-ssm.png)

        - Une fois la sélection effectuée, on peut choisir d’épingler ce rapport à un nouveau tableau de bord ou à un nouveau tableau de bord existant. 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/05-pin-live-page-ss.png)

        - Après avoir sélectionné l’option **Épingler un élément dynamique**, une nouvelle fenêtre s’ouvre et affiche le tableau de bord. 
            - Dans le tableau de bord, on peut modifier les éléments visuels selon les besoins.
                - Tous les segments et filtres restent fonctionnels et les éléments visuels contiennent les mêmes données que dans le rapport.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/05-dashboard-example-ss.png)

        - ***Toutes les modifications apporté au rapport de tickets s’affichent automatiquement dans le tableau de bord lorsque la page est actualisée. Dans Power BI Desktop, on peut apporter des modifications aux éléments visuels ou données selon les besoins, puis procéder au déploiement dans le fichier d’espace de travail approprié afin de mettre simultanément à jour le rapport et le tableau de bord.***
 - **NB: Les tableaux de bord représentent un regroupement d’informations provenant de différentes sources, et pas simplement un « tremplin » pour les rapports. Il est recommandé d’utiliser l’épinglage au niveau de la vignette dans un premier temps, avant d’épingler si nécessaire la page de rapport complète. Afficher une page de rapport entière dans une vignette de tableau de bord peut être difficile.**

 [Voir Doc Épingler une page de rapport complète.](https://learn.microsoft.com/fr-fr/power-bi/create-reports/service-dashboard-pin-live-tile-from-report)

#### Configurer un tableau de bord en temps réel

[Voir Doc Streaming en temps réel dans Power BI](https://learn.microsoft.com/fr-fr/power-bi/connect-data/service-real-time-streaming)

- La possibilité d’afficher des données de streaming en temps réel sur ces tableaux de bord peut s’avérer essentielle. Avec les fonctionnalités de diffusion en continu en temps réel de Power BI, il est possible de diffuser des données et mettre à jour des tableaux de bord dès que les données sont enregistrées.

1. **Diffuser en continu dans Power BI** 
    - Les données de streaming peuvent provenir de sources diverses, notamment des réseaux sociaux, des capteurs d’usine, des métriques d’utilisation de services et d’autres sources qui contiennent un flux constant de points de données.
    - **Les données provenant d’un jeu de données de streaming ne sont pas stockées dans un modèle de données Power BI, mais dans un cache temporaire**. 
        - Par conséquent, on ne peut pas modéliser les données avec ce type de jeu de données. La seule façon de visualiser les données à partir d’une source de données de streaming consiste **à créer une vignette directement sur un tableau de bord et à utiliser une source de données de streaming personnalisée**. 
            - Ces vignettes sont optimisées pour afficher rapidement les données et, dans la mesure où aucune base de données d’où extraire les données n’existe, ces types de vignettes présentent une faible latence et sont mieux adaptés aux données qui n’ont pas besoin de transformations supplémentaires, telles que la température ou l’humidité.
2. **Visualiser les données en temps réel dans Power BI**
    - Pour visualiser les données de streaming, il faut créer une nouvelle vignette directement sur un tableau de bord existant ou nouveau.
    - => ouvrir un tableau de bord existant, sélection du menu déroulant d’édition => sélection **Ajouter une vignette**.
        - Dans la fenetre  qui s'affiche on peut sélectionner **Jeux de données de streaming personnalisés** sous **Données en temps réel**.
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/06-new-tile-added-ss.png)

    - => Selection **Suivant** => choisir un jeu de données de streaming existant ou en récupérer de nouveaux, 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/06-add-new-streaming-dataset-ss.png)

    - ***Après avoir sélectionné le nouveau jeu de données => **Suivant** => introduire les détails du jeu de données de streaming => ajout d'une nouvelle vignette de jeu de données de streaming.*** 
        - *Les vignettes de jeu de données de streaming peuvent avoir la forme de graphiques en courbes, de graphiques à barres empilées, de cartes et de jauges et sont mises en forme de façon similaire à tout autre type de vignette.*

#### Configurer la classification des données

[Voir Doc Classification des données d’un tableau de bord.](https://learn.microsoft.com/fr-fr/power-bi/enterprise/service-security-apply-data-sensitivity-labels)

1. **Configurer la classification des données des tableaux de bord**
    - La classification des données aide le propriétaire du tableau de bord à souligner l’importance de la sécurité pour les utilisateurs afin qu’ils prennent conscience du niveau de sécurité lors de l’affichage ou du partage d’un tableau de bord.
    - La classification des données est une fonctionnalité qui peut être activée et désactivée selon les besoins. 
        - Par défaut, tous les tableaux de bord utilisent un certain type de classification. Cependant, le propriétaire du tableau de bord peut manuellement modifier la classification. Pour apporter manuellement des modifications, des droits d’administrateur sont nécessaires dans le service Power BI.
    - Il existe trois choix de classification dans Power Bi 
        1. **Impact élevé**
        2. **Impact faible**
        3. **Impat moyen**
    - Pour accéder à la classification des données sur un tableau de bord dans **le service Power BI** => **les points de suspension (...)** en regard du nom du tableau de bord => sélection **Paramètres**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/07-data-classification-settings-ss.png)

    - Dans la fenêtre qui apparaît, sous Tableaux de bord => le menu déroulant sous **Classification des données** pour choisir la manière dont on souhaite classifier les données. 
        - *Exemple: Le tableau de bord Tickets contient des informations très sensibles et il doit donc être marqué comme Impact élevé.* 
    - Une fois cette sélection effectuée, le tableau de bord suit les règles de données par défaut ou celles que on a établies sous Paramètres du client.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/07-data-classification-dashboard-ss.png)

    - Lorsque on ouvre le tableau de bord, celui-ci reflètera la nouvelle classification des données

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/07-dashboard-tag-ss.png)

#### Définir un affichage mobile

[Voir Doc  Optimiser un tableau de bord pour les téléphones mobiles](https://learn.microsoft.com/fr-fr/power-bi/create-reports/service-create-dashboard-mobile-phone-view)

- Pour accéder à l’affichage mobile dans Power BI Desktop
    - => Sélection **Afficher** => Sélection **Disposition mobile**

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/08-mobile-view-updates-ss.png)

    - Il est aussi possible d' optimiser les tableaux de bord pour l’affichage mobile dans le service Power BI. 
        - => Sélection du **menu déroulant d’édition** dans le ruban de la page d’accueil => **Disposition pour mobile**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/08-mobile-view-dashboard-ssm.png)

        - Cette sélection permet d’accéder à une vue dans laquelle il est possible de choisir les vignettes que l'on souhaite affichage sur le téléphone.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-dashboards-power-bi/media/08-mobile-view-dash-ss.png)

        - Il est possible de redimensionner et réorienter les vignettes et les visuels dans l’ordre souhaité. 
            - *Cette affichage sur le téléphone est personnalisable pour chaque utilisateur du tableau de bord*  
            - Sélection **Affichage téléphone** pour pouvoir créer un nouvel affichage que l'on pourra voir sur le téléphone lorsque on se connecte au service Power BI.