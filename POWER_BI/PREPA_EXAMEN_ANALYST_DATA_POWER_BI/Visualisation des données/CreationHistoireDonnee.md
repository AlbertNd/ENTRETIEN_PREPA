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

