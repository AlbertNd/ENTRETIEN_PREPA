# Ciblage des elements requis d'une conception de rapport 

### Obectif permettant de determiner les elements requis à la création de rapport 
- **Audiences**
    - Permet à l'auteur du rapport de créer un résultat qui peut etre utilisé efficacement et qui repond aux besoins du consommateur de rapports.
- **Type de rapport** 
    - Une conception de rapport peut etre classée par type de de rapport et une association se fait directement entre l'audience du rapport et le tye de rapport.
- **Elements requis de l'interface utilisateur**
- **Element requis de l'experience utilisateur**

1. ##### L'audience
    - Les trois audiences de consommateur de rapport:
        1. Les dirigeants : Prenneurs des decisions
        2. Les analystes : Fournis un travail de conseil
        3. Travailleur de l'information : Utilisateur des données pour prendre des decisions 
2. ##### Determination de type de rapport 
    - Les besoins de l'audience peuvent etre satisafaits par un ou une combinaison des 4 type de rapport 
        1. **Tableau de bord : Pour les dirigeants** 
            - L'objectif principale du tableau de bord est de comprendre le plus rapidementpossible ce qu'il raconte. Les interactions utilisateurs ksont limitées par des apercus qui sont très bien presentés à l'audience. ***un tableau de bord communique directement le sens qui se cache derriere les données pour reduire au minimum les mauvaises interpretation ou les confusions.*** Il presentent souvent les metriques globales sur une seul page
            -   ```
                Les tableaux de bord permettent de répondre à des questions comme « Où en sommes-nous ? » ou « Est-ce que nous y sommes arrivés ? »
                ```
        2. **Analytque : Pour les analystes** 
            - L'objectif principal est d'aider les consommateurs de rapports à découvrir des réponses à des questions tres diverses en interagissant avec le rapport et ses visuels. ***Ils ont souvent des nombreux segments pour filtrer les données de rapport et contiennent souvent des visuelles complexes qui exposent les details approfondis des données.*** 
            Le consommateur de rapports peut suivre plusieurs voies, ce qui lui permet d’explorer un sujet qui l’intéresse, de partager ses découvertes ou de revenir à l’endroit où il a commencé. Les consommateurs de rapports peuvent supprimer des couches et ajouter du contexte et des détails en incorporant des fonctionnalités interactives. Parmi les fonctionnalités interactives courantes, citons l’exploration, l’extraction et les info-bulles.
            -   ```
                    Un rapport analytique est un rapport qui va au-delà du type de question « Où en sommes-nous ? » pour répondre au type de question telle que « Pourquoi c’est arrivé ? » ou « Que risque-t-il de se passer après ? » .
                ```
        3. **Opérationnel : Pour les travailleurs informatique**
            - Les rapports opérationnels sont conçus pour donner au consommateur de rapports la possibilité de surveiller les données actuelles ou en temps réel, de prendre des décisions et d’agir en fonction de ces décisions. Les rapports opérationnels peuvent inclure des boutons qui permettent au consommateur de rapports de naviguer dans le rapport, et même au-delà pour entreprendre des actions dans les systèmes externes. Souvent, les rapports opérationnels servent de hub d’action que les consommateurs de rapports utilisent dans le cadre de leur activité et de leur charge de travail journalières.  
            -   ```
                Ce type de rapport doit réduire au minimum le nombre de fonctionnalités analytiques pour être sûr de rester concentré sur l’opération pour laquelle il a été conçu. Une expérience utilisateur simplifiée est l’objectif principal de ce type de rapport parce qu’un trop grand nombre de clics ou un flux illogique peuvent aboutir à une grande insatisfaction.

                Un bon exemple de rapport opérationnel est un rapport qui permet de surveiller une ligne de production. Lorsqu’un événement inattendu se produit, comme un dysfonctionnement de l’équipement, un bouton peut permettre aux employés de déclencher une demande de maintenance.

                Un exemple de rapport opérationnel pour Contoso Skateboard Store serait un rapport de stock qui informe le consommateur de rapports des niveaux de stock actuels et met en évidence les niveaux de stock bas ou les commandes en souffrance. Il comprend également un bouton Envoyer la commande qui permet aux utilisateurs de créer un bon de commande.  
                ```
        4. **Educatif (Pédagogique) : Général** 
            - Les rapports éducatifs partent du principe que le consommateur de rapports ne connaît pas les données ou le contexte. Les rapports doivent donc fournir des informations et des détails narratifs clairs pour aider à la compréhension. Ce type de rapport est souvent utilisé dans le journalisme et par les gouvernements pour communiquer des informations à des publics larges qui ont différents niveaux de compréhension du sujet.
            -   ```
                Un bon exemple de rapport éducatif est un rapport qui décrit la progression de la vaccination contre la COVID-19 et qui peut être filtré par la région géographique du consommateur de rapports.
                ```
### Définition des elements requis de l'interface utilisateur
- Les aspect a prendre en compte : 
    1. La forme 
    2. La méthode d'entrée 
    3. Le style et le theme 
    4. L'accessibilité
1. **Le facteur forme**
    - Un facteur de forme decrit la taille du materiel utilisé pour ouvrir les rapports et l'orientation des pages (***portait ou paysage***).
2. **La méthode d'entrée**
    - Un ordinateur a un clavier et un dispositif de pointage (souris), les appareils mobiles reposent sur des gestes courants comme appuyer, appuyer deux fois, glisser, pincer, écarter ou appuyer longuement. 
    Les consommateurs de rapports qui se servent d’appareils mobiles peuvent également utiliser le clavier visuel, le contrôle vocal ou les lecteurs de code-barres et de codes QR. Les appareils de réalité mixte ou augmentée reposent beaucoup sur les gestes des mains ou les mouvements du corps.
3. **Style et thème**
    - Le thème du rapport doit exprimer la marque de l'organisation ou viser à la compléter. Au minimum, le thème doit inclure les éléments suivants :
        - Un signe ou un logo de la marque 
        - Une palette de couleurs qui est en phase, ou vient en complément, de la marque de l’organisation
        - Les paramètres du texte, notamment la sélection, les tailles et la couleur de police.
    - ***Pour gérer les changements de style et de thème de manière efficace et réussie, concevez des rapports qui utilisent des images et des thèmes stockés dans un référentiel central. Cette approche améliore la gestion des changements : les changements appliqués au référentiel peuvent être répercutés automatiquement dans les rapports.***
4. **L'accessibilité**
    - Les rapports doivent communiquer avec l’audience la plus large possible. Il faut donc réfléchir à la façon dont les consommateurs de rapports malvoyants ou non-voyants, ou atteints d’un autre handicap physique, peuvent tirer pleinement parti des rapports.
        - des polices claires et grandes
        - des visuels bien espacés et grands
        - des couleurs suffisamment contrastées
        - et une navigation intuitive dans les rapports qui peut être comprise par les lecteurs de clavier et d’écran.

### Définition des elements requis de l'expérience utilisateur
[Voir doc](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-requirements/5-define-experience)

### Exploration des conceptions de rapport 
[Voir doc](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-requirements/6-explore-designs)


# Structuration des conceptions de rapports analytiques dans Power BI 

**NB:** L'objectif principale des rapport analystiques est de permettre au consommateuir de rapports de decouvrir des réponses à des questions tés diverses. Ils décompposent les rapports complexes de deux manieres: 
1. Condenser les volumes de données en resultats plus petits et plus ciblés
2. Visualiser les résultats sous forme de graphique pour comprendre rapidement les données.

- ***Une requete analytique comporte trois phases qui sont exécutées dans l'ordre suivant :*** 
    1. Filtrer (ou découper en tranches) : Ciblages des données pertinentes 
    2. Grouper (Découper en morceau) : Divise les résultats de requete en groupes
    3. Totaliser Produit un seul resultat de valeur 

### Conception de la présentation des rapport analytiques 
- Une bonne presentation de rapport doit tenir compte des principes de conception de placement, d'équiliibre, de contraste, de proximité et de répétition. 

1. **Placement:** 
    - Il est recommander de placer les informations les plus importantes en hautà gauche de la page et  organiser les éléments du rapport de gauche à droite et de hout en bas.
    - Les bord verticaux et horizontaux doivent etre alignés
    - **AL regle de tiers**: 
        -   ```
            Diviser la présentation d’une page en une grille invisible de neuf parties égales. La grille est formée de deux lignes horizontales équidistantes et de deux lignes verticales équidistantes. Les objets de rapport peuvent ensuite être placés dans les cellules de la grille.
            ```
2. **L'équilibre:**
    - L’équilibre fait référence au poids réparti sur la page de rapport par le placement d’objets de tailles identiques ou différentes
        - penser à la regle d'or pour reproduire un équilibre asymetrique
        ![regle d'or](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRUw6dABCvlHdP920ktDmyzfSbmkIXy-KGF_w&usqp=CAU)
        
        -Une fois que les graphiques les plus grands sont compris l'oeil est attiré par le plus petit et ainsi de suite.  

    - [Voir Doc](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-structure/2-design-analytical-report-layout)

3. **La proximité**
    - Lorsqu'une une page de rapport se compose de plusieurs groupes d’objets associés, on utilise l’espace pour les séparer visuellement
4. **Le contraste**
    - Le contraste peut être utilisé pour combiner deux objets opposés. 
    - Ce principe dirige le consommateur de rapports vers l’endroit où il doit regarder ou vers le visuel de données avec lequel il doit interagir en premier.

5. **Répétition**
    - La répétition dans une conception de rapport crée une association et une cohérence. Une bonne utilisation de la répétition peut aider à renforcer une présentation de rapport en reliant les objets de rapport associés.

### Création d'une expérience analytique guidée
- Une présentation de rapport analytique peut intégrer une expérience analytique guidée. De cette façon, la conception du rapport est en phase avec les processus automatiques et inconscients qui se produisent quand le consommateur du rapport regarde le rapport.
- L’expérience analytique guidée permet de naviguer entre trois niveaux :
    1. **Les métriques globales:**
        - Présentent des valeurs (cartes) uniques ou des visuels simples qui peuvent être rapidement compris. Ces métriques doivent être liées directement aux besoins fondamentaux du rapport.
    2. **Les visuels complémentaires:**
        - Peuvent être des visuels plus complexes qui fournissent le contexte des métriques globales.
        - ***Ils montrent souvent des groupes qui détaillent les métriques, par exemple par mois ou par produit.***
        - Ces visuels peuvent aussi se comporter comme des segments, ce qui permet de filtrer temporairement la page du rapport sur des visuels spécifiques, comme un ou plusieurs mois spécifiques.
    3. **Les détails:**
        - Le consommateur de rapports est dirigé vers une page de rapport supplémentaire dans laquelle il peut voir des détails précis
# Conception des rapport Power BI 

### La structure d'un rapport 
- Un rapport Power BI:
    - Se connecte à un seul jeux de donnée ( modèle de donnée)
    - A au moins une page de rapport 
    - Des objets de rapport disposés sur chaque page 
        - **Visuels** : visualisations de données de jeu de donnée
        - **Elements** : présentent un intérêt visuel, mais n’utilisent pas de données de jeu de données. Parmi les éléments, citons les zones de texte, les boutons, les formes et les images.

![Rapport](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-reports/media/1-report-structure.png)

- **Page d'un rapport**
    - À l’instar des feuilles de calcul Microsoft Excel, vous pouvez ajouter, renommer, reséquencer, masquer, dupliquer ou supprimer des pages de rapport Power BI.
    - Il est possible de masquer des pages quand celles-ci ne sont pas encore prêtes à être utilisées 

### Les objets de rapport 

- Tous les objets de rapport ont des propriétés en commun, qui peuvent être définies dans différentes sections des options de Mise en forme. Les paramètres couramment appliqués incluent des propriétés générales (emplacement, taille et texte de remplacement), un titre, un arrière-plan, une bordure et une ombre.
![Objet de rapport](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-reports/media/2-1-format-options.png)

1. **Visuels** [Voir Doc](https://docs.microsoft.com/fr-fr/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a)
    - Il y aplus de 30 visuls principaux 
    - Acceès au visuels par le volet Visualisations 
    ![Visualisation](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-reports/media/2-2-visualizations-pane-core-visuals.png)
    - Il est possible de charger des visuels personnalisé via **Microsoft AppSource**

2. **Les elements** 
    - Les éléments présentent un intérêt visuel, mais n’utilisent pas de données de jeu de données
    ![Element](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-reports/media/2-3-insert-ribbon-elements.png)
    - Les 4 types d'element :
        1. Zone de texte
        2. Boutons
        3. Formes
        4. Image
    - **NB:** ***La zone de texte mérite une mention spéciale, car elle est capable d’incorporer des valeurs dynamiques provenant du jeu de données du rapport dans des paragraphes de texte. Quand la page est filtrée, les valeurs dynamiques le sont également. Techniquement, la zone de texte n’est pas un visuel. Toutefois, dans le cas présent, elle se comporte comme telle. Elle est également disponible comme visuel de narration intelligente, qui résume automatiquement les données à l’aide de descriptions textuelles et d’insights.***
    ![zone texte](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-reports/media/2-4-create-dynamic-value.png)
    - Il est possible d'ajouter la zone de la naration intelligente à partir du volet Visualisation.

### Selection des visuels de rapport 
- **Visuels par catégorie**
    - Les graphiques à barres ou les histogrammes sont de bons choix quand vous devez montrer des données figurant dans plusieurs catégories
- **Visuels de série chronologique**
    - Les graphiques en courbes ou un histogramme pour montrer des valeurs dans le temps.L’axe des X doit présenter les valeurs de temps, triées de la plus ancienne à la plus récente
    - Les autres visuels principaux utilisable pour les données de séries chronologiques sont les suivants :
        - Histogramme empilé
        - Graphique en aires
        - Graphique en courbes et histogramme empilé
        - Graphique de ruban, qui présente l’avantage supplémentaire d’illustrer les changements de classement dans le temps
- **Visuels proportionnels**
    - Les visuels proportionnels montrent les données en tant que partie d’un tout. Ils communiquent en fait la manière dont une valeur est répartie sur une dimension. Les visuels d’histogramme et de graphique à barres fonctionnent bien pour visualiser les proportions sur plusieurs dimensions.
    - Les autres visuels principaux utilisable pour la visualisation proportionnelle sont les suivants :
        - Histogramme empilé 100 %
        - Graphique en entonnoir
        - Compartimentage
        - Graphique en secteurs
        - Graphique en anneau
- **Visuels numériques**
    - Souvent présentées par des visuels de carte, les valeurs numériques affichent des légendes générales qui attirent immédiatement l’attention. Elles peuvent être percutantes dans des rapports de tableau de bord et des rapports analytiques, car elles communiquent rapidement des données importantes.
- **Visuels de grille**
    - les tableaux et les matrices peuvent transmettre efficacement de nombreuses informations détaillées.
- **Visuels de performances**
    - La communication des performances consiste à décrire une valeur et sa comparaison avec une cible. Toute différence entre la valeur et la cible constitue sa variance, qui peut être favorable ou défavorable. La couleur ou les icônes peuvent communiquer l’état
    ![perf](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-reports/media/3-11-select-visual-performance.png)
    - Les autres visuels principaux utilisable pour montrer les performances sont les suivants :
        - Jauge
        - KPI
        - Tableau avec mise en forme conditionnelle
        - Matrice avec mise en forme conditionnelle
- **Visuels géospatiaux**
    - Quand un jeu de données contient des informations géospatiales, celles-ci peuvent être transmises à l’aide de visuels de carte

### Selection des visuels de rapport en fonction de la présentation du rapport 
- ***Il faut choisir le visuel qui correspond le mieux à l’espace disponible sur la page du rapport*** 

# Configuration ndes filtre de rapport Power BI 

### Appliquation des filtres à la stucture du rapport 
[Voi Doc](https://docs.microsoft.com/fr-fr/power-bi/create-reports/power-bi-report-filter?tabs=powerbi-desktop)
- On utilise le vole **Filtre** pour appliquer des filtres à la structure du rapport. 
    - Il comporte 3 sections : 
        1. Filtres dans toutes les pages 
        2. Filtres dans cette pages
        3. Filtre sur ce visuel
    ![filtre](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/media/filter-pane.png)
    - ***NB : Contrairement aux filtres au niveau du rapport et au niveau de la page, un filtre au niveau du visuel peut filtrer en utilisant une mesure. Quand une mesure filtre un visuel, elle est utilisée pour éliminer des groupes.***
- Les filtres s'applique a un seul champs et utilisent un des types de filtres suivant: 
    - **Basic** 
        - Permet de selectionner des élements dans une liste de valeurs distinctes trouvées dans le champ. il est aussi possible de limiter le filtre à une selection unique  ou lieu d'une selection multiple.
    - **Avancé**
        - Permet de créer des conditons plus complexes en utilisant des opérateurs sp"cifiques aux type de données. 
            - ***Operateur de champs de texte*** : Test por des condition telle que : 
                - Contient 
                - Commence par 
                - Est vierge
                - Est vide
                - ... 
            - ***Operation de champ nmérique*** : Test pour des condition telle que : 
                - Est inferieur à 
                - Est inferieur ou égale à 
                - ... 
            - ***Operateur de champ de date*** : Test pour des conditions telle que: 
                - Est apres 
                - Est le ou apres le 
                - ...
        - **NB**: *** Il est possible de combiner plusieur tests en utilisant un opérateur logique **ET/OU**   
    - **N premiers**
        - Il permet de filtrer par les N premiers (ou derniers) elements. 
        - ***Pour configurer le filtre il faut un champ dans la somme est calculée comme par exemple le CA*** 
        - ***Il s'applique aux champs de texte et de date qui sont disponible seulement dans les filtre au*** **niveau du visuel**

    - **Date relative et heure relative** 
        - S'applique que aux champs de date ce qui permet de filtrer par date ou heure relative
    
    **NB:** ***Il est possible de verouiller les filtrer afin que le consommateur ne puisse pas les modifier ou les supprimer.***
    ![filtre](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/media/filters-pane-card-lock-hide.png)
    **NB:** ***Il est possible de masquer le volet filtrer pour que le consommateur ne puisse pas l'ouvrir***
    ![filtre](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/media/filters-pane-lock.png)

### Application des filtres avec des segments 

- **Le segment**:
    - C'est un visuel fondamental dont l'objectif est de filtrer d'autre visuels. Il represente un moyen intuitif pour le consommateur de rapport de filtrer les données. 
    - Par defaut , les segments filtrent tous les autres visuels de la page
    - La synchronisation des segments peut également filtrer les visuels sur d'autres pages.
    - [Voir Doc interactions entre les visuels dans les visuels Power BI](https://docs.microsoft.com/fr-fr/power-bi/developer/visuals/visuals-interactions)
    - [Voir Doc Synchronisation des segments sur les pages dans les rapports Power BI](https://docs.microsoft.com/fr-fr/power-bi/developer/visuals/enable-sync-slicers)
    **NB:** ***un segment est un visuel qui propage des filtres à d’autres visuels sur la même page ou (quand ils sont synchronisés) sur d’autres pages.***

    - **Il est possible de configurer un segment en utilisant un ou plusieurs champs de la meme table ou une hierarchie.**
        - Lorqu'il est configurer pour utiliser plusieur champs ou une hierarchie, le segment présente une arbolescence d'elements extensible. 
    - **La disposition du segment dépend du type de données du champ.**
        - **Texte**:
            - Par defaut va produire un segment de liste
                - ***Liste (valeur par défaut) ou liste déroulante***
        - **Numerique**
            - Par defaut va produire un filtre entre les valeurs d'une plage numérique 
                - ***Liste, liste déroulante, entre (par défaut), inférieur ou égal à, ou supérieur ou égal à***
        - **Date**
            - Par defaut va produire un filtre entre les valeurs d'une plage de dates, permettant la selection de valeurs avec des controles de calendrier.
                - ***Liste, liste déroulante, entre (par défaut), avant, après, date relative ou heure relative***
        - **NB:** 
            - ***Au momment d ela conception, il est possible de modifier la disposition du segment pour que les listes deviennent des liste deroulantes*** **(Prenant ainsi moins de place sur la plage de rapport)**
            - ***Les plages de dates et numerique (ayant de valeur continues) permettent de selectionner une valeur unique qui fait office de limite inferieur et superieur du filtre.*** 
    - Pour modifier la disposition du segment, on place le curseur sur le segment pour faire apparaître une flèche vers le bas située dans le coin supérieur droit. on sélectionne la flèche pour faire apparaître un menu contextuel des options de disposition.
    ![Segment](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/media/slicer-layout.png)
- **NB:** ***Les segments de liste et de liste déroulante prennent en charge des options de mise en forme pour contrôler la sélection des éléments. Quand vous activez l’option Sélection simple, le segment autorise la sélection d’un seul élément. Cette approche a du sens pour un segment dans un scénario où les options sont Réel, Budget ou Prévision. Dans ce cas, il est logique de ne filtrer que par un seul scénario à la fois.***
- [Voir video demo](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/3-slicers)

### Conception des rapports avec des techniques de filtrage avancée
- Les differents autre technique de filtrage: 
    - **Interactios entre les visuels**
        - Le filtrage croisé et la selection croisée 
        - [Void Doc](https://docs.microsoft.com/fr-fr/power-bi/create-reports/power-bi-reports-filters-and-highlighting)
    - **Extraction**
        - Il est possible d'ajouter des pages d’extraction pour permettre aux consommateurs de rapports d’explorer à partir de visuels. Par défaut, l’action d’extraction propage tous les filtres qui s’appliquent au visuel à la page d’extraction.
        - [Voir dDoc](https://docs.microsoft.com/fr-fr/power-bi/create-reports/desktop-drillthrough)
    - **Info-bulle de rapport**
        - Il est possible d'ajouter des info-bulles de rapport qui vont apparaître quand les consommateurs de rapports placent le curseur sur des visuels. Par défaut, l’info-bulle de rapport reçoit tous les filtres qui s’appliquent au visuel.
        - [Voir Doc](https://docs.microsoft.com/fr-fr/power-bi/create-reports/desktop-tooltips?tabs=powerbi-desktop)
    - **Signets**
        - Ils capturent une vue spécifique d’un rapport, notamment les filtres, les segments, la sélection de la page et l’état des visuels.
        - Ils peuvent etre créer par l'auteur et ou par le consommateur du rapport
             - Les signets créés par un consommateur de rapport s’appellent des ***signets personnels.***
        - ***Comme les signets peuvent capturer l’état des filtres, quand ils sont appelés, ils appliquent l’état de ces filtres. Il est possible d'appeler des signets directement à partir du*** **volet Signets**,***ou alors de les appeler indirectement en sélectionnant un bouton, une image ou une forme.***
        ***Il est possible de créer un signet pour capturer l’état par défaut des segments. Un bouton sur la page de rapport pourrait ainsi avoir le texte*** **Réinitialiser les segments** ***; quand il est appelé, il va utiliser le signet.***
        - [Voir Doc](https://docs.microsoft.com/fr-fr/power-bi/consumer/end-user-bookmarks)
    - **Options de rapport**
        - Il est possible de configurer les paramètres des rapports ou des visuels pour contrôler les options de filtre et le comportement.
            - Désactiver des filtres persistants. (Les filtres persistants sont couverts dans l’unité 5.)
            - Masquer les en-têtes de visuel pour tous les visuels ou pour un visuel spécifique. Lorsque l’en-tête de visuel est masqué, les consommateurs de rapports ne peuvent pas placer le curseur sur l’icône Filtrer pour déterminer les filtres qui sont appliqués au visuel. (L’icône Filtrer est couverte dans l’unité 5.)
            - Masquer l’icône Filtrer pour un visuel spécifique.
            - Limiter les consommateurs de rapports à la modification des types de filtre (par exemple de « de base » à « avancé ») dans le volet Filtres.
            - Supprimer la zone de recherche dans le volet Filtres.
    - **Option de reduction des requetes**
        - Il est possible de configurer des paramètres de rapport pour réduire le nombre de requêtes envoyées au jeu de données.
            - Un moins grand nombre de requêtes va améliorer la réactivité quand les consommateurs de rapports mettent à jour des filtres, des segments ou des pages de rapport avec filtre croisé.
            ![Option](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/media/query-reduction-apply-button.png)
            -   ```
                    Envisagez d’activer les options de réduction des requêtes quand le jeu de données utilise le stockage de tables DirectQuery ou quand les volumes de données importés sont grands, et que les calculs sont complexes et lents.
                ```
- Les parametres de rapport peuvent: 
    - Désactiver le filtrage/la sélection croisé(e) par défaut. Tous les visuels, à l’exception des segments, ne propagent pas les filtres à d’autres visuels, sauf s’ils sont explicitement ajoutés en tant qu’interaction entre les visuels.

    - Ajouter un bouton **Appliquer** à des segments. La sélection du segment va filtrer seulement la page de rapport quand le consommateur du rapport sélectionne le bouton **Appliquer**.

    - Ajouter un bouton **Appliquer** à tous les filtres de base dans le volet Filtres. Un seul filtre va s’appliquer quand le consommateur du rapport sélectionne le bouton Appliquer dans la carte de filtre.

    - Ajouter un bouton **Appliquer** au **volet Filtres**. Tous les filtres vont s’appliquer simultanément quand le consommateur du rapport sélectionne le bouton **Appliquer**. Cette option est utile quand les consommateurs de rapports souhaitent mettre à jour de nombreux filtres en même temps.
### Filtrage au moment de la consommation 
- [Les consommateur peuvent utiliser plusieur techniques de filtrage lors de la visualisation d'un rapport Power BI](https://docs.microsoft.com/fr-fr/learn/modules/power-bi-effective-filters/5-consumption-time):
    - Utilisation de segments.
    - Utilisation de filtres.
    - Application d’actions de filtrage interactif.
    - Détermination des filtres appliqués.
    - Utilisation de filtres persistants.

