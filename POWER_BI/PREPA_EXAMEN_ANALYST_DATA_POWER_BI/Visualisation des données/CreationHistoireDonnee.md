# créer une histoire basée sur les données avec des rapports Power BI
#### Conception d'une mise en page de rapport
- La mise en page des rapports doit p^rendre en compte les besoins de l'entreprise, du contexte des données sous-jacentes et des exigences de sortie. 
    - **Un tableau de bord**:
        - Présente des informations de haut niveau sur une seule page. 
    - **Un rapport** :
        - C'est une vue multiperspective du jeu de données, avec des éléments visuels qui représentent différents résultats et informations de ce jeu de données.
1. **Meilleures pratiques de conception de rapports**
    1. Choix d'une bon  format *(Qui tient compte des souhaits des utilisateurs)*
        - Plusieurs visuels complexes qui offrent le plus de détails ou alors une petite gamme de visuels de base.
    2. Examination attentive de chaque elements visuel et autres que l'on souhaite utiliser dans le rapport.
        - Il faut un objectif et une vision de l'apparance finale (Jeu de couleur, police particulier, ...)
    3. La mise en page de rapport
        - Dessiner prealablement un croquis de la mise en page du rapport (Soumettre pour confirmation)
        - Se concentrer sur lesinformations les plus importantes ( Couleur vive, icone de résumé...)
        - Selectionner le bon arriere plan pour le contxte (Couleur, image, ...)

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-example-bad-report-design-ss.png)

        **VS**

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-example-improved-report-design-ss.png)


#### Conseil plus detailés pour la mise en page
1. **Rapport** 
    - Tenir compte que les rapport peuvent etre affichier sur des écrans avec des proportions et des tailles différentes.
        - La vue d'affichage par défaut est **Ajuster à la page** *(càd le contenu est mis à l'échelle pour s'adapter au mieux à la page)*. 
        - Si il faut modifier cet affichage : => onglet **Affichage** => sélection **Affichage de la page** => option d'affichage de page souhaité

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-page-view-options-ss.png)

    - Les paramettre de la page => Volet **Format**

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-page-configuration-options-ssm.png)

2. **Visuel**
    - Si on souhaite utiliser une combinaison des visuels differents, il est important d'utiliser le bon nombre de visuels sur une page, puis de dimensionner et de positionner ces visuels de manière stratégique.
        1. ***Nombre de visuels*** 
            - Limiter le nombre de visuels qu'on utilise sur une page et examiner chaque visuel pour voir si il est nécessaire. Si un visuel n'ajoute pas de valeur à l'audience. *Il est preferable de fournir des informations d'autres manières, telles que des pages d'extraction et des info-bulles de page de rapport. Moins visuels = rapport moins chargé = meilleures performances. 
        2. ***Position des visuels***
            - Il est recommandé de placer le visuel le plus important dans le coin supérieur gauche du rapport, car les utilisateurs lisent très probablement de gauche à droite et de haut en bas, de placer le logo dans ou à proximité de cette zone et organiser les autres visuels en conséquence.
            - Pour **répartir uniformément la distance entre les visuels situés sur le canevas**,   
                - => fonction **Aligner** 
                    - CTRL + clic pour sélectionner tous les visuels à aligner => onglet **Format** => **Distribuer horizontalement**.

            ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-page-alignment-options-ssm.png)

            ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-evenly-distributed-visuals-ss.png)

        3. ***Taille des visuels***
            - Lorsque on ajoute un visuel à un rapport, Power BI détermine la taille de ce visuel par défaut. on peut redimensionner ce visuel pour s'assurer qu'il présente les informations affichées de la manière la plus optimale.
        4. ***Interaction des visuels***
            - Les visuels qu'on ajoute au rapport interagissent les uns avec les autres.Par conséquent, il est important de comprendre ces interactions et d'examiner comment elles peuvent affecter l'expérience utilisateur globale du rapport.
        5. ***Hiérarchies dans les visuels***
            - Il faut considérer comment les hiérarchies affecteront la façon dont les données s'affichent dans les visuels et l'expérience de navigation des utilisateurs des rapports
                - Définir la manière dont les hiérarchies sont présentées dans les visuels
                - Déterminer le chemin hiérarchique des visuels afin d'avoir un contrôle total sur le niveau de détail accessible
3. **Accessibilité du rapport** 
    - Il est essentiel d'envisager la possibilité que les utilisateurs aient des déficiences auditives, motrices, cognitives ou visuelles.
    1. ***Normes d'accessibilité***
        - Power BI respecte les normes d'accessibilité conformément aux directives pour l'accessibilité du contenu Web **(WCAG)**.
            - La perceptible - Les composants d'information et d'interface utilisateur doivent être présentables aux utilisateurs d'une manière qu'ils peuvent percevoir.
            - Opérable - Les composants de l'interface utilisateur et la navigation doivent être utilisables.
            - Compréhensible - Les informations et le fonctionnement de l'interface utilisateur doivent être compréhensibles.
    2. ***Fonctionnalités d'accessibilité***
        - Les fonctionnalités d'accessibilité intégrées à Power BI Desktop par defaut: 
            - Navigation au clavier
            - Compatibilité lecteur d'écran
            - Affichage des couleurs à contraste élevé
            - Mode de mise au point
            - Afficher le tableau de données
        - Les fonctionnalités d'accessibilité à configurer :
            - ***Texte alternatif***
                - Le texte alternatif aide à s'assurer que les utilisateurs comprennent ce que on essaie de communiquer avec les objets. (Voir Format => General => Zone Texte)
                - Pour appliquer une **mise en forme conditionnelle** => bouton droit sur la zone Texte alternatif => sélection **Mise en forme conditionnelle** => configurartion des paramètres selon les besoins.

                ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-add-alt-text-option-ssm.png)

            - ***Ordre de tabulation***
                - Aide les utilisateurs au clavier à naviguer dans le rapport dans un ordre qui correspond à celui des utilisateurs visuels
                    - Pour définir l'ordre de tabulation:
                        - Onglet **Affichage** => sélection **Volet de sélection** = > placement des objets dans le bon ordre

                        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-set-tab-order-objects-ss.png)
            
            - ***Titres et étiquettes***
                - Éviter d'utiliser des acronymes ou du jargon que les nouveaux utilisateurs ou les utilisateurs externes ne comprendront pas.
                - S'assurer que toutes les étiquettes d'un visuel sont faciles à lire et à comprendre. Il est possible d'activer ou désactiver les étiquettes pour chaque série du visuel ou les positionner au-dessus ou en dessous d'une série pour les rendre plus claires. ***Ne pas activer les étiquettes pour chaque visuel, car cela pourrait avoir l'effet inverse en distrayant les utilisateurs et en rendant le rapport moins accessible.***

                ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-comparison-visual-labels-ss.png)

            - ***Marqueurs***
                - Il est recommandé d'éviter d'utiliser la couleur (y compris la mise en forme conditionnelle de la fonctionnalité) comme seul moyen de transmettre des informations.
                    - Il est possible d'utiliser des marqueurs pour transmettre différentes séries. Pour les visuels de lignes, de zones et de combinaisons, y compris les visuels de dispersion et de bulles, on peut activer les marqueurs et utiliser une forme différente pour chaque ligne.
                    *Gardez à l'esprit que si on active des marqueurs pour chaque visuel, cela peut être distrayant et rendre le rapport moins accessible aux utilisateurs*.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-turn-markers-ssm.png)

                    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-view-markers-visual-ss.png)

            - ***Thèmes***
                - S'assurer qu'il existe un contraste suffisant entre le texte et les couleurs d'arrière-plan ; le rapport de contraste doit être d'au moins **4,5:1**. 
                    [Voir outils tel que Color Contrast Analyser](https://chrome.google.com/webstore/detail/color-contrast-analyzer/dagdlcijhfbmgkjokkjicnnfimlebcll), ^[WebAim](https://webaim.org/) et [Accessible Colors](https://accessible-colors.com/)
                - L'utilisation de moins de couleurs ou d'une palette monochrome dans le rapport peut aider à atténuer la création de rapports inaccessibles. 
                    - Les combinaison à eviter :
                        - **Vert** et **rouge**
                        - **Bleu** et **violet**
                        - **Vert** et **marron**
                        - **Vert** et **bleu**
                        - **Vertclair** et **jaune**
                        - **Bleu** et **gris**
                        - **Vert** et **gris**
                        - **Vert** et **noir**
                - Les themes integré dans Power Bi 
                    
                ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/2-view-theme-options-ss.png)

#### Ajouter des boutons, des favoris et des sélections
- Il est possible d'utiliser les [Signets](https://learn.microsoft.com/fr-fr/power-bi/create-reports/desktop-bookmarks?tabs=powerbi-desktop), [Bouttons](https://learn.microsoft.com/fr-fr/power-bi/create-reports/desktop-buttons?tabs=powerbi-desktop), [Sélections]()

1. **Ajouter des signets**
    - Ils permettent de capture une vue configurée d’une page de rapport pour que l'on puissiez revenir rapidement à cette vue plus tard. 
        - *Utile pour assurer le suivi de votre propre avancement lorsque vous créez des rapports.*
        - *Utile pour créer une présentation de type PowerPoint qui parcourt les signets dans l’ordre, créant ainsi un scénario avec votre rapport.*
    - Lorsqu'on enregistre un signet, les elemenst suivant sont enregistré:
        - ***Page actuelle***
        - ***Filtres***
        - ***Segments, notamment le type de segment (par exemple, liste déroulante ou liste) et l’état du segment***
        - ***État de sélection de l’objet visuel (par exemple, filtres de surbrillance croisée)***
        - ***Ordre de tri***
        - ***Emplacement d’exploration***
        - ***Visibilité d’un objet (à l’aide du volet  Sélection )***
        - ***Mode Focus ou À la une de tout objet visible***
    - Exemple: si on souhaite permettre à l'utilisateur de pouvoir basculer netre deux objets visuels sur une page, 
        1. Configuration de la facon dont on veut que la page s'affiche initialement.
            - Onglet **Affichage** => Selection **Sélection** :
                - *Dans le volet Sélection qui s’affiche, il y a la liste de tous les éléments de la page, ainsi qu’une icône d’œil qui indique les éléments actuellement visibles*
                - **NB:** Il est possible de renommer les éléments de la liste en double-cliquant dessus afin de savoir exactement qui est qui. 
        2. Ajout d'un signet pour capturer le visuel de la page dans son état actuel. 
            - Onglet **Affichage** => Selection **Signets** => selection **Ajouter**:
                - Renommer(Double click) le signets avec un objectif claire *(Ex : Graphique des variances)*
    - Si plusieurs Signets
        - ***On répéte ces étapes pour ajouter d’autres signets : sélection des éléments que l'on souhaite afficher/masquer sur la page de rapport, puis ajout d'un signet et lui donner un nom descriptif.***
    - **Grpahique variance**

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/3-add-bookmark-ssm.png)

    - **Tableau de bord**

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/3-select-items-dashboard-bookmark-ssm.png)
    
    **Il est possible ensuite d'affecter ces signets à des boutons pour autoriser les utilisateurs à basculer entre les signets.**

2. **Ajouter des boutons**
    - Il est possible d'utiliser des bouttons pour des nombreuses raisons:
        - Basculer entre deux objets visuels d’un rapport (comme requis dans l’exemple précédent)
        - Descendre dans la vue des données d’un objet visuel
        - Passer d’une page de rapport à une autre
    - Power BI Desktop fournit une série de types de boutons

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/3-button-options-ssm.png)

    - Supponsons que l'on souhaite un boutton personalisé permettant de basculer entre deux signets
        1. Onglet **Insert** = > Selection **Bouttons** => Selection du type de bouton souhaité *(Dans ce cas ci ***Vide**)*
        2. Une fois que le bouton est ajouter à la page: 
            1. On slection le boutton
            2. Dans le volet **Visualisations** 
                - Deplacement du curseur **Texte du bouton**  vers  la position **Active**
                - Developement de la section **Text du bouton** 
                    - Introduire le texte à afficher sur le bouton
                    - Mise en forme du boutton et texte du bouton *(Couleur, police, ...)
            3. Ajout d'une action au bouton
                - Volet **Visualisations** => **Action** => **Activé**
                    - Developpement de la section **Action** => choix du type d'action souhaité. 
                        - ***Retour*** : *renvoie l’utilisateur à la page précédente du rapport.* 
                            - *Cette option est utile pour les pages d’extraction ou les pages accessibles à partir d’une page principale.*
                        - ***Signet*** : *affiche la page de rapport associée à un signet défini pour le rapport actuel.*
                        - ***Extraction*** : *dirige l’utilisateur vers une page d’extraction filtrée sur sa sélection, sans utiliser de signets.*
                        - ***Navigation entre les pages*** : *dirige l’utilisateur vers une autre page du rapport, aussi sans utiliser de signets, ce qui est un moyen efficace de créer une expérience de navigation pour les utilisateurs.*
                        - ***Questions et réponses*** : *ouvre une fenêtre **Explorateur de questions et réponses**, où les utilisateurs peuvent taper des questions pour trouver rapidement les informations qu’ils recherchent, et de spécifier le type d’objet visuel dans lequel ils veulent voir les informations s’afficher.* 
                            - *Cette option peut être utile si on souhaite gagner de l’espace dans le rapport tout en offrant à l’utilisateur une fonctionnalité de questions et réponses.*
                        - ***URL web*** : *ouvre un site web dans une nouvelle fenêtre de navigateur.* 
                            - *Par exemple, si on souhaite accorder aux utilisateurs un accès rapide au site web à partir d’un rapport.*
            - Dans le'exemple ci-dessous:
                - On selectionne le type d'action **Signet**(Bookmark) et on selection le signet **Tableau de bord principal**
                    - *Il aussi possible de rajouter une info-bull visible au survole du bouton.*
            
            ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/3-assign-bookmark-action-ssm.png)

            - ***copier et coller le bouton afin d’avoir deux boutons avec une mise en forme cohérente sur la page. On renomme le deuxième bouton en **Graphique de variance** et on modifie l’action affectée au signet **Graphique de variance**.*

            ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/3-two-buttons-ssm.png)

#### Concevoir le mode de navigation au sein d'un rapport
- Le mode de navigation au sein d'un rapport correspond à la façon dont les utilisateurs passent d'une page à une autre, ou d'un objet visuel à un autre, avant de revenir à leur point de départ

1. **Ajout des boutons de navigation**
    - Pour concevoir le mode de navigation:
        - On peut créer une nouvelle page **Navigation** au sein du rapport et y ajouter des boutons de navigation
        - On peut également utiliser une combinaison des deux options. 
    - ***Lorsque les utilisateurs sélectionnent un de ces boutons, ils accèdent directement à une autre page du rapport, que l'on peut masquer afin qu'elle soit uniquement accessible via les boutons de la page **Navigation**.***
    1. Dans le volet **visualisation** => **Action** => Type d'action **Navigation au sein de la page** => page de **Destination** du boutton.
    2. Copier et coller pour en créer un deuxième avec la même mise en forme
    3. Sur a page de **Destination** : 
        - Selection du bouton **Vide** dans le menu des bouton => type d'action **Precedent** 

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-add-customized-back-button-ssm.png)

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-assign-bookmark-as-action-ss.png)

    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-add-default-back-button-ssm.png)

2. **Définir la destination de navigation**
    - Il est possible d'utiliser la mise en forme conditionnelle pour définir la destination de navigation en fonction du résultat d'une mesure. ***Ce type de méthode de navigation permet d'économiser de l'espace dans votre rapport***
        - *Ex: plutôt que d'utiliser plusieurs boutons de navigation (comme l'illustre l'image précédente), on peut utiliser un seul bouton pour accéder à différentes pages en fonction de la sélection de l'utilisateur*

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-conditional-navigation-ss.png)

        - Ce type de navigation peut etre utile pour les raison suivantes:
            - Spécifier le chemin logique que les utilisateurs du rapport doivent suivre. 
                - *En d'autres termes,on détermine l'ordre dans lequel les utilisateurs consulteront les différentes pages.*
            - Raconter une histoire basée sur les données. 
                - *On peut l'utiliser pour adresser aux employés un message qui est sauvegardé par les données. Cette méthode peut favoriser un changement, comme une augmentation des ventes.*
            - Créer un portail où les utilisateurs ont accès à un ensemble de rapports.
    - **Pour utiliser la mise en forme conditionnelle afin de définir la navigation:**
        1. Créer un tableau à une seule colonne contenant les noms des destinations de navigation. 
        2. Dans ce tableau, on verifie que les valeurs entrées correspondent aux noms des pages du rapport.

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-load-table-ss.png)

        3. On l'ajoute à la page du rapport en tant que segment à **sélection unique**
        4. Ajout d'un bouton de navigation au sein de la page 
            - Dans la section **Actions**,on s'assurez que la **Destination** est définie sur **Aucune**
        5. Click droit sur la destination et sélection **Mise en forme conditionnelle**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-conditional-formatting-option-ss.png)

        6. Dans la fenetre **Destination**
            - Selection du nom de la colonne créée. *(En fonction de la sélection opérée par l'utilisateur, le bouton peut permettre d'accéder à différentes pages)*
        7. Configuration de la mise en forme conditionnelle

        ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/4-conditional-navigation-configuration-ss.png)

#### Utiliser les interactions de base
- Dans Power BI Desktop, le rapport est dynamique. 
    - Si on effectue une sélection sur un objet visuel dans le rapport, d’autres objets visuels peuvent changer pour refléter cette sélection. De même, s’il existe des hiérarchies dans les données, on peut monter et descendre dans la hiérarchie pour afficher les données à différents niveaux.

1. **Afficher les interactions** 
    - Il est possible d'effectuer des modifications afin de contrôler la façon dont ces interactions circulent entre les objets visuels
        1. ***Utiliser les hiérarchies**
            - Une hiérarchie est une structure dans laquelle des groupes sont classés l’un au-dessus de l’autre, en fonction d’un état spécifique
            - ***Les icônes de hiérarchie se situent au-dessus de l’objet visuel***

            ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/5-add-default-hierarchy-ssm.png)

            - Il est possible de descendre et monter dans la hierarchie 

            ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/5-expand-hierarchy-ssm.png#lightbox)

            - IL est aussi possible de prédéfinir le chemin d’accès de la hiérarchie pour les utilisateurs du rapport et supprimer le travail d’estimation *(Empêcher les utilisateurs d’afficher un niveau de hiérarchie particulier)*.
                - Pour ce faire: 
                    1. On supprime tous les champs dela barre d'outils **Axe**
                    2. Dans le volet **Champs**  => click droit sur le champs que l'on souhaite definir comme niveau superieur de la hierarchie => Selection **Nouvelle hiérarchie**
                    3. La nouvelle hierarchie s'affiche dans la liste du volet **Champs**
                    4. Faire glisser d'autre champs dans la hierarchie (ou click droit => ajouter à la hierarchie)

                    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/5-create-hierarchy-ssm.png)

                    5. Selection de l'objet visuel => Volet Champs => **Nouvelle hiérarchie**  

                    ![](https://learn.microsoft.com/fr-fr/training/modules/data-driven-story-power-bi/media/5-apply-new-hierarchy-ssm.png)
                    
#### Utiliser les interactions avancées et l'extraction
- Pour bénéficier d'un contrôle total sur le comportement de votre rapport et être en mesure de déterminer l'expérience utilisateur attendue, vous pouvez modifier les interactions par défaut et utiliser les fonctionnalités d'extraction.


        
