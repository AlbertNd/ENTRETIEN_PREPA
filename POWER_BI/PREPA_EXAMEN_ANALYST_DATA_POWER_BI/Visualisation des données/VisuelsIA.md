# Utiliser des visuels IA dans Power BI
- Parfois, le moyen le plus rapide d’obtenir une réponse consiste à poser une question en utilisant ses propres mots. 
    - *C’est exactement ce que Power BI permet de faire avec ses fonctionnalités d’intelligence artificielle (IA) en matière d’analytique avancée. L’une des fonctionnalités de Power BI permet de ***poser des questions en langage naturel***, puis répond à ces questions.*
- L’analyse de données non numériques peut être difficile, mais avec les fonctionnalités d’IA de Power BI, il est possible d'analyser les données texte pour obtenir plus d’insights qu’auparavant.     - 
    - *Par exemple, on peut avoir une multitude de commentaires ou d’avis de clients, ou les résultats d’une enquête sur les employés. On peut analyser ces données supplémentaires et les transformer en informations très utiles.*
- Étant donné que les chiffres ne disent pas tout, on peut utiliser les fonctionnalités IA dans Power BI pour explorer plus en détail les données, voir ce que les gens disent et obtenir des résultats plus constructifs et plus explicites qui aideront finalement à prendre de meilleures décisions.

#### Utiliser le visuel Questions et réponses
- La fonctionnalité **Questions et réponses** de Power BI permet d’explorer les données avec ses propres mots, en permettant de poser des questions en langage naturel, puis en répondant à ces questions.
    - Elle donne des idées concernant le type de visuels que l'on peut afficher dans le rapport et permet de le faire rapidement. 
    - Elle offre aux utilisateurs des rapports un outil efficace leur permettant d’obtenir de façon indépendante des réponses rapides à leurs questions sur les données.
- Power BI enregistre toutes les questions qui sont posées. et on peut ensuite utiliser ces informations pour configurer la fonctionnalité Questions et réponses pour une plus grand efficacité. Comme la fonctionnalité Questions et réponses répond à un grand nombre de questions, moins de personnes s’adresseront à vous pour avoir des réponses.
1. **Ajouter le visuel Questions et réponses à votre canevas de rapport**
    - Pour accéder à la fonctionnalité Questions et réponses, il faut ajouter le visuel Questions et réponses au rapport. 
        - => Double-cliquer n’importe où sur le canevas pour afficher le visuel
        - => Sélection de l’icône Questions et réponses dans le volet Visualisations.

        ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-add-visualization-ssm.png)

    - La fonctionnalité Questions et réponses est également disponible sous forme de bouton, ce qui est utile si on veut gagner de la place sur le canevas du rapport.

    ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-add-button-ssm.png)

    - On peut commencer à poser des questions tout de suite en sélectionnant une des questions suggérées ou en entrant une question dans la zone de question. 
        - *À mesure que l'on tape, Power BI affiche automatiquement des suggestions pour aider à terminer la question.*

    ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-ask-question-ss.png)

2. **Configurer la fonctionnalité Questions et réponses**
    - Une fois le visuel Questions et réponses ajouté au rapport, on peut configurer la fonctionnalité Questions et réponses sous-jacente afin qu’elle améliore sa capacité à répondre à des questions sur les données:
        -  On apprend à la fonctionnalité Questions et réponses à mieux comprendre les utilisateurs. 
            - Cette configuration peut être utile dès le départ pour préparer le visuel à une utilisation active.
            - On peut superviser et passer en revue de manière proactive les questions provenant des utilisateurs, puis dissiper les malentendus ou corriger les fautes de frappe courantes. 
            - On peut gérer les termes clés associés aux données afin de pouvoir ajouter une bibliothèque de synonymes qui peuvent être entrés par différents utilisateurs de l’organisation quand ils posent des questions sur les données.
            - On peut calibrer en permanence la fonctionnalité Questions et réponses pour qu’elle fournisse de meilleures réponses.
        - ***Un trait de soulignement rouge s’affiche sous un terme lorsque Power BI ne le comprend pas.*** 
            - *Par exemple : Si le mot pays n’est pas utilisé dans le jeu de données, on décide d’utiliser le terme région à la place et de savoir pourquoi la question n’est pas traitée. c'est ainsi que l'on réalise qu'il faut apprendre à Power BI ce que l'on veut dire en ajoutant un nouveau terme à son dictionnaire des synonymes.*

            ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-problem-question-ss.png)

            - ***Sélection de l’icône des paramètres située à droite de la zone de question pour ouvrir la fenêtre de configuration Questions et réponses. => sélection de l’option **Enseigner les Q/R.*****

            ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-setup-ss.png)

            - Introduire à nouveau la question => sélection du bouton **Envoyer**. 
                - Dans la section **"Définir les termes que Questions et réponses ne comprend pas"** qui s’affiche => introduire l'autre terme ou un synonyme. 
                - Power BI affiche un aperçu des résultats, ce qui permet de voir si ce nouveau terme retournera les résultats recherché. Si c’est le cas => Selection **Enregistrer**.

                ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-define-terms-ss.png)

            - Ainsi, lorsque des utilisateurs recherchent les ventes par pays, Power BI sait qu’ils veulent en fait dire « par région » et il affiche automatiquement les données associées dans le visuel.

            ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-problem-resolved-ss.png)

3. **Utiliser la fonctionnalité Questions et réponses pour créer des visuels**
    - Quand Power BI répond à une question et que l'on trouve le résultat du visuel intéressant ou utile, on peut l’ajouter en tant que visuel standard au rapport.
        - *Par exemple, si on passe en revue les questions qui sont posées et que l'on constate que plusieurs utilisateurs posent la même question, on peut ajouter la réponse aux visuels standards du rapport afin qu’ils n’aient plus à le faire.* 
        - *On peut également utiliser la fonctionnalité Questions et réponses pour commencer à générer le rapport, en posant des questions et en adoptant les formats de résultats de visuels suggérés de Power BI.*
    - Pour transformer un résultat de Questions et réponses en visuel standard => clic sur l’icône à côté de la zone de question.

    ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/2-visualization-ss.png)

#### Rechercher des facteurs importants avec le visuel des influenceurs clés

[Voir Doc  Créer des visualisations d’influenceurs clés.](https://learn.microsoft.com/fr-fr/power-bi/visuals/power-bi-visualization-influencers?tabs=powerbi-desktop)

- Le visuel Influenceurs clés permet de comprendre les facteurs qui affectent une métrique spécifique. 
    1. Il analyse les données, 
    2. Classe les facteurs importants, 
    3. Affiche ces facteurs en tant qu’influenceurs clés. 
- Le visuel aide également à comparer l’importance relative de ces facteurs, ce qui signifie que l'on peut créer les visuels tout en comprenant quels facteurs ont un impact sur ces visuels et pourquoi les visuels apparaissent comme ils le font.
    - *Par exemple : Si on génére plusieurs visuels pour l’équipe du service clientèle et qu'on souhaite comprendre les facteurs qui influencent les ventes. Un facteur peut être le type de client et un autre peut être l’emplacement. Le visuel Influenceurs clés trouvera ces informations.*
- Pour établir les influenceurs clés: 
    1. On ajoute d’abord le visuel **Influenceurs clés** au rapport en sélectionnant l’icône **Influenceurs clés** dans le **volet Visualisation**. 
    2. Remplir le visuel avec les métriques que l'on veut mesurer. *(Dans le cas ci les ventes : Donc, dans la barre d’outils des champs Analyser, on ajoute le champ Ventes et, dans la barre d’outils des champs Expliquer par, on ajoute les champs Nom de ville et Nom de produit.)*.  
    3. Le visuel est mis à jour en fonction des champs ajoutés, puis affiche l’influence de ces champs sur les données.

    ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/3-use-key-influencers-visual-ssm.png)

    - ***On peut ensuite utiliser la liste déroulante **Ce qui influence...** pour voir ce qui a amené les données à diminuer ou à augmenter. Ex: Les ventes pour la Californie sont susceptibles d’être supérieures de 130 700,00 USD aux ventes des autres villes.***

#### Utiliser le visuel Arborescence hiérarchique pour décomposer une mesure

[Voir Doc Créer et afficher des visuels d’arborescence hiérarchique dans Power BI.](https://learn.microsoft.com/fr-fr/power-bi/visuals/power-bi-visualization-decomposition-tree)

- Le visuel Arborescence hiérarchique agrège automatiquement les données et permet d’explorer les dimensions, de telle sorte que l'on peut consulter les données sur plusieurs dimensions. Étant donné que le visuel Arborescence hiérarchique est un visuel d’IA, on peut l’utiliser pour une exploration improvisée et pour effectuer une analyse de la cause racine.
- *Supposons que l'on veut pouvoir analyser le pourcentage de produits de l’organisation dont les commandes sont en souffrance, Càd le pourcentage de produits en rupture de stock.*
    1. On ajoute le visuel **Arborescence hiérarchique** au rapport en sélectionnant l’icône **Arborescence hiérarchique** du **volet Visualisation**. 
    2. Dans le champ **Analyser**, on ajoute la mesure ou l’agrégat que l'on souhaite analyser.
    3. Dans la zone de champ **Expliquer par**, on ajoute la ou les dimensions que l'on souhaite explorer en détail. 
        - *Dans le cas présent, on veut analyser le champ Ventes en explorant différentes dimensions, comme Pays, Ville et Produit.*

        ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/4-use-decomposition-tree-visual-ss.png)

        - Le visuel est mis à jour en fonction des champs ajoutés et affiche le résultat de synthèse de l’analyse.:
            - Ici, la valeur des ventes est de 13 499 680,00 USD. On peut sélectionner le signe plus **(+)**, qui présente les options d’exploration qu'on a ajoutées. 
            - On peut sélectionner n’importe quel champ de la liste déroulante pour explorer les données et voir comment elles ont contribué au résultat global.
        - En haut de la liste des dimensions qu'on a ajoutées, il y a deux options supplémentaires signalées par des icônes en **forme d’ampoule**. 
            - ***Ces options sont appelées **Fractionnements IA**. Elles recherchent automatiquement les valeurs élevées et faibles dans les données.***
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/4-ai-split-options-ss.png)

        - ***Les fractionnements de l’IA fonctionnent en prenant en compte tous les champs disponibles et en déterminant celui qui doit être exploré pour obtenir la valeur la plus élevée/la plus faible de la mesure analysée. On peut utiliser les résultats de ces fractionnements pour savoir quelles données regarder.*** 
        - **Ci-dessous, l’illustration du résultat de la sélection du découpage IA Valeur élevée.**

        ![](https://learn.microsoft.com/fr-fr/training/modules/ai-visuals-power-bi/media/4-apply-ai-split-decomposition-tree-ss.png)






