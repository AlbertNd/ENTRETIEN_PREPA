# Gérer des espaces de travail et des jeux de données dans Power BI

[Voir Doc Supp Organiser le travail dans les nouveaux espaces de travail.](https://learn.microsoft.com/fr-fr/power-bi/collaborate-share/service-new-workspaces)

***Un espace de travail est un référentiel centralisé dans lequel vous pouvez collaborer avec des collègues et des équipes pour créer des collections de rapports et de tableaux de bord.***
- **ils offrents les avantages suivants**
    - Des efforts de collaboration ciblés. On peut utiliser des espaces de travail pour héberger des rapports et des tableaux de bord destinés à être utilisés par plusieurs équipes.
    - Ils permettent de partager et de présenter des rapports et des tableaux de bord dans un environnement unique.
    - Ils garantissent le maintien du niveau de sécurité le plus élevé en contrôlant qui peut accéder aux jeux de données, rapports et tableaux de bord.

#### Distribuer un rapport ou un tableau de bord
- En créant un espace de travail dans le service Power BI, on peut héberger les rapports à un seul endroit, les partager facilement, collaborer avec d’autres équipes et mettre à jour les rapports.

1. **Créer un espace de travail** 
    - Les differentes étapes :
        1. Accès au service [Power BI](https://powerbi.microsoft.com/fr-fr/)
        2. Selection dans le menu deroulant **Espaces de travail** 
        3. Dans la fenetre qui s'affiche => Clik sur le boutton **Créer un espace de travail**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-create-new-app-5-ss.png#lightbox)

        4. Dans la fenêtre **Créer un espace de travail**, on introduit les informations dans les champs **Nom de l’espace de travail** et **Description**, puis téléchargez une **Image de l’espace de travail**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-create-workspace-1-ssm.png#lightbox)

        5. Dans le menu déroulant **Avancé**, il est possible de créer une Liste de contacts d’utilisateurs qui vont recevoir des notifications en cas de problème avec l’espace de travail.
            - Par défaut, il s’agit des utilisateurs de l’espace de travail, mais on peut aussi ajouter des utilisateurs spécifiques. 
            - on peut également ajouter cet espace de travail à un OneDrive spécifique et déterminer s’il fera partie d’une **capacité dédiée** ou non. 
                - *Les capacités dédiées sont une fonctionnalité de Power BI Premium qui permet de veiller à ce que les espaces de travail aient leurs propres ressources de calcul au lieu de partager des ressources avec d’autres utilisateurs.*
        6. Une fois les champs pertinents rempli => **Enregistrer**

2. **Affecter des rôles d’espace de travail** 
    - Les rôles d’espace de travail vous permettent de désigner qui peut faire quoi dans un espace de travail.
        - Les types de role dans un espace de travail: 
            - **Administrateur**
                - *Ajouter/supprimer d’autres utilisateurs*
                - *Publier, mettre à jour et/ou partager une application dans un espace de travail*
                - *Créer, modifier, supprimer et publier des rapports et du contenu dans un espace de travail*
                - *Consulter des rapports et tableaux de bord et interagir avec eux dans un espace de travail*
                - *Configurer des actualisations de données*
            - **Membre**
                - *Peut ajouter des utilisateurs avec des autorisations inférieures*
                - *Ne peut pas supprimer d’utilisateurs*
                - *Ne peut pas supprimer l’espace de travail*
                - *Ne peut pas mettre à jour les métadonnées relatives à l’espace de travail*
            - **Contributeur**
                - *Ne peut pas ajouter ni supprimer des utilisateurs*
                - *Ne peut pas publier, mettre à jour ou modifier une application dans un espace de travail, sauf si cette capacité lui est donnée par les administrateurs/membres*
                - *Peut créer, mettre à jour et publier du contenu et des rapports dans un espace de travail*
                - *Peut planifier des actualisation de données*
            - **Observateur**
                - *Ne peut pas ajouter ni supprimer des utilisateurs*
                - *Peut uniquement consulter un rapport ou un tableau de bord dans un espace de travail*
                - *Peut lire les données stockées dans un dataflow de l’espace de travail*
            - **NB/** ***Si l’espace de travail est associé à une capacité Premium, un utilisateur non professionnel peut consulter le contenu au sein l’espace de travail sous le rôle d’observateur.***
    - Pour attribuer ces rôles aux utilisateurs:
        1. Accès à l’espace de travail créé *(dans le coin supérieur gauche du ruban)* => sélection **Accès**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-workspace-access-3-ss.png)

        2.  Dans la fentre **Accès**:
            - Ajout de l’adresse e-mail de différents utilisateurs, des groupes de sécurité à extension messagerie, des listes de distribution, des Groupes Microsoft 365 et des groupes de sécurité standard, puis leur attribuer des rôles spécifiques.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-workspace-app-7-ss.png)

            - Il est également possible de modifier le rôle attribué à l’utilisateur en bas, ainsi que de supprimer l’utilisateur de l’espace de travail en sélectionnant les points de suspension **(...)** en regard de leur nom.
3. **Créer et configurer une application**
    - Une application est une fenêtre en lecture seule publiée dans vos données à des fins d’affichage et de distribution en masse.
        - *Ce processus nécessite une licence Power BI Pro.* 
        - *La consommation et l’affichage d’une application nécessitent une licence Pro ou une capacité Premium optionnelle*
    - Une fois que le contenu de l'espace de travail d'appplication est ajouté, on crée l'application:
        1. accès à l'espace de travail , dans le ruban, => selection **+ Nouveau**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-create-new-app-ss.png)

        - Dans ce ruban on peut choisir de créer un rapport, un jeu de données, un jeu de données de streaming ou un dataflow pour n’en citer que quelques-uns.
        - Lorsqu'on selectionne l’une de ces options, une fenêtre apparaît, dans laquelle on peut ajouter le nom de l’application et sélectionner la source du rapport (par exemple, le jeu de données utilisé pour créer un rapport).
        - Il est également possible de sélectionner le bouton **Obtenir des données** en bas à gauche de la barre de navigation pour importer des rapports déjà existants à partir de Power BI Desktop et de les ajouter à l’application de l'espace de travail.
        - Il est aussi possible de configurer l'application et choisir d’inclure ou non le rapport ou le tableau de bord dans l’application lors de la publication.
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-create-workspace-window-2-ss.png)

        - ***Si vous ne voulez pas inclure ce rapport ou tableau de bord dans cette application, on peut désactiver cette option.***

        2. Lorqu'on est prêt à publier l'application avec sa collection de rapports, tableaux de bord et jeux de données, on revient à l’espace de travail => sélection **Créer une application** dans l’angle supérieur droit du ruban.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-update-app-10-ss.png)

        3. Cela permet de récupérer la fenêtre dans laquelle on peut générer l'application en la nommant, en ajoutant une description et en ajoutant un logo d’application ou une couleur de thème, si nécessaire.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-workspace-access-3-ssm.png)

        - Sous l’onglet **Navigation**:
            - Il est possible de modifier l’ordre dans lequel le contenu est orienté pour l’utilisateur en créant un volet de navigation personnalisé. 
                - *Par exemple, on peut modifier le nom du contenu, modifier le lien et l’ajouter à une section spécifique dans le volet de navigation.* 
            - On peut également ajouter du contenu externe à Power BI par le biais d’un lien. 
                - *Ce contenu externe peut également être inclus dans la zone de contenu.*
                    - *Par exemple, une vidéo YouTube ou une série de diapositives PowerPoint doivent avoir une URL incorporée, pas une URL brute*

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-publish-app-ss.png)

        - Sous l'onglet **Autorisation**:
            - Il est possible d'accorder l’accès à tous les utilisateurs ou choisir ceux qui ont accès.
            - Il est possible d'octroyer aux utilisateurs des autorisations de création et de partage, ce qui signifie qu’ils peuvent créer et partager le contenu dans l’application.
            - Avec les autorisations de Build, on peut autoriser les utilisateurs à se connecter aux jeux de données sous-jacents afin qu’ils puissent réutiliser et créer leurs propres rapports à l’aide du même jeu de données.      
                - *Les autorisations de Build sont nécessaires si les utilisateurs veulent exporter les données sous-jacentes ou créer du contenu par-dessus les données.* 
            - On peut également autoriser les utilisateurs à créer uniquement une copie du rapport à afficher dans un autre espace de travail, où ils peuvent modifier et supprimer des visuels selon leurs besoins. 
            - On peut également octroyer aux utilisateurs des autorisations de partage pour qu’ils puissent partager des jeux de données et rapports sous-jacents.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-included-app-6-ss.png)

        4. Après avoir apporté les modifications nécessaires => sélection **Publier l’application** 
            - On obtient un lien que l'on peut partager avec les utilisateurs.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-publish-app-7-ss.png)

4. **Mettre à jour des espaces de travail**
    - Pour mettre à jour l'espace de travaill:
        1. revenir à l’espace de travail et effectuez les mises à jour nécessaires dans les rapports ou les tableaux de bord
            - *L’espace de travail fait office de zone intermédiaire où on peut apporter des modifications, mais ces dernières ne sont pas ajoutées à l’application tant que on a pas sélectionné **Mettre à jour l’application** dans l’angle supérieur droit du ruban (où figurait auparavant Publier l’application).* 
            - Les mises à jour apportées aux jeux de données et aux dataflows le sont immédiatement. 
            - Lorsqu'on selectionne cette option, on peut apporter des modifications sous les onglets **Configuration, Navigation et Autorisations**, puis => sélection du bouton **Mettre à jour l’application**.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/02-publish-app-9-ss.png)

[Voir Doc Publier une application dans Power BI.](https://learn.microsoft.com/fr-fr/power-bi/collaborate-share/service-create-distribute-apps)

#### Superviser l’utilisation et le niveau de performance
- Il est essentiel de connaître l’utilisation et les performances de votre espace de travail car cela :
    - Vous permet de concentrer l'effort d’amélioration. *(Si on sait où le niveau de performance est le pire)*
    - Quantifie l’impact des rapports. Les métriques *(Mesures)* d’utilisation aident à déterminer la réussite des rapports.
        - *Ces métriques de performance et d’utilisation sont toutes les deux une fonctionnalité disponible dans un espace de travail. Avec ces métriques, on peut voir qui utilise les rapports, quelles actions sont effectuées sur les rapports et quels problèmes de performances existent.*
1. **Configurer et afficher les rapports des métriques d’utilisation**

    [Voir Doc Surveiller l'utilisation des métriques. ](https://learn.microsoft.com/fr-fr/power-bi/collaborate-share/service-modern-usage-metrics)

    - *Les rapports des métriques d’utilisation sont disponibles pour les utilisateurs de **Power BI Pro** et uniquement accessibles aux utilisateurs dotés de rôles d’**administrateur**, de **membre** ou de **contributeur**.*
    - Pour afficher les rapport des metriques d'utilisateur
        1. Accès à l'espace de travail 
        2. Rechercher le rapport ou le tableau de bord pour lequel on veut voir les métriques d’utilisation.
        3. Selection des points de suspension *(...)*
        4. Selection **Afficher le rapport des metriques**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/03-report-label-ssm.png)

        - Lorsque le rapport des métriques d'utilisation est prêt à être consulté, une invite dirige vers un tableau de bord. 
            - Dans l’onglet Utilisation des rapports, on peut afficher les détails suivants :
                - Graphiques **Observateurs par jour**, **Observateurs uniques par jour** *(ce qui n’inclut pas les utilisateurs qui reviennent plusieurs fois dans les mêmes rapports)*, **Partages par jour**
                - Cartes KPI **Nombre total de vues**, **Nombre total d’observateurs** et **Nombre total de partages**
                - Nombre total de **vues et de partages** *(permet de comparer votre rapport avec d’autres rapports dans l’application)*
                - **Nombre de vues par utilisateur** *(détails sur chaque utilisateur distinct ayant consulté le tableau de bord)*
            - Il est également possible de filtrer selon la méthode de distribution du rapport *(par exemple, par le biais d’un partage ou de l’espace de travail directement)* et le type de plateforme *(par exemple, mobile ou web)*.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/03-usage-metrics-1-ssm.png)

            - Il est également possible d'afficher les métriques de performance dans l’onglet **Rapport de performance**

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/03-report-performance-metrics-ss.png)

    - Sous l’onglet **Rapport de performance =**, on peut afficher les métriques telles que :
        - **Délai d’ouverture par défaut** : le temps nécessaire, au 50e centile, pour ouvrir le rapport.
        - **Tendance du délai d’ouverture** : comment le délai d’ouverture par défaut évolue dans le temps. 
            - *Ces métriques peuvent éclairer sur les performances du rapport quand le nombre d’utilisateurs commence à augmenter.*
        - Graphiques **Performances quotidiennes/hebdomadaires** : met en évidence les performances pour 10, 50 %, 90 % et 90% des actions d’ouverture de rapport chaque jour et chaque semaine.
        - Des filtres de date permettent de voir comment les performances évoluent selon les jours.

#### Recommander une stratégie de cycle de vie de développement

[Voir Doc  Pratiques recommandées pour les pipelines de déploiement.](https://learn.microsoft.com/fr-fr/power-bi/create-reports/deployment-pipelines-best-practices)

- **Le cycle de vie de développement** : c'est une processus itératif, il nécessite en règle générale de créer une solution initiale, de la tester dans un environnement différent, de la reprendre et d’effectuer des révisions si besoin, puis de publier enfin un produit final.

1. **Pipeline de déploiement (Premium)** 
    - Le pipeline de déploiement de Power BI est une fonctionnalité qui gère le contenu des tableaux de bord, rapports et jeux de données entre différents environnements tout au long du cycle de vie du développement. 
        - Ici, on peut développer et tester du contenu Power BI à un seul emplacement centralisé et rationaliser le processus avant de déployer le contenu final vers les utilisateurs finaux. 
        - ***Il s’agit d’une fonctionnalité de Power BI Premium qui oblige à être administrateur de capacité.***
    - Les avantages de l’utilisation du pipeline de déploiement sont les suivants :
        - **Productivité améliorée** - Grâce à cette fonctionnalité, on peut réutiliser les pipelines de déploiement précédents pour veiller à ne pas dupliquer les efforts.
        - **Livraison plus rapide du contenu** - Le développement de rapports est rationalisé, ce qui signifie qu’il faut moins de temps pour passer en production.
        - **Diminution de l’intervention humaine nécessaire** - En ayant la possibilité de réutiliser des pipelines de déploiement, le risque d’erreur lié au déplacement du contenu d’un environnement à un autre est moindre.
2. **Environnements de développement**
    - En général, le développement et la collaboration se produisent en différentes étapes. Les rapports et les tableaux de bord sont intégrés et itérés dans une série de phases contrôlées, ou environnements, lors desquelles plusieurs tâches ont lieu :
        - **Développement** - Emplacement auquel les développeurs de tableaux de bord ou modélisateurs de données peuvent créer du contenu avec d’autres développeurs. Il s’agit de la première étape dans le pipeline de déploiement.
        - **Test** - Phase pendant laquelle un petit groupe d’utilisateurs et des testeurs d’acceptation utilisateur peuvent voir et examiner de nouveaux rapports, fournir des commentaires et tester les rapports avec des jeux de données plus volumineux pour détecter les bogues et les incohérences de données avant le passage en production.
        - **Production** - Phase pendant laquelle un public plus large peut utiliser les rapports testés qui se sont révélés fiables et exacts. Il s’agit de la phase finale du pipeline de déploiement.
    - *On peut choisir l’environnement de développement à inclure dans le pipeline de déploiement, selon les besoins métier. Par exemple, on peut choisir d’inclure uniquement les environnements de test et de production, si besoin.*

3. **Configuration des pipelines de déploiement** 
    - Pour configurer un pipeline de déploiement:
        1. Accès au service Power BI 
        2. Dans le ruban situer sur le cote gauche de la page => selection **Pipelines de déploiement**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-full-8-ss.png)

        3. Dans la page qui apparait => selection **Créer un pipeline** 
        4. Nom et descritpion si necessaire
        5. Selection **Créer** 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-pipeline-page-2-ss.png)

        - Ci dessus les étapes du cycle de vie de développement : **Développement**, **test** et **Production**
        6. Pour créer le pipeline, on attribue des espaces de travail à chacunes des phases pour facilité l'hébérgement des rapport et tableaux de bord pendant chaque phase.
            - => Selection **Attribuer un espace de travail**
        7. Dans la fenetre **Attribuer un espace de travail à une étape de déploiement** => On ajoute l'espace de travail *(exemple : Tailwinds Traders)* à l'environnement **Développement**. 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-report-performance-metrics-4-ss.png)

        - ***Seuls les espaces de travail attribués à une capacité Premium apparaissent. De plus, on ne peut affecter qu’un seul espace de travail à chaque pipeline. Power BI génère automatiquement les deux autres espaces de travail utilisés dans le pipeline.***
        8. Si on dispose déjà d'espaces de travail de Développement, de Test et de Production, on va choisir celui avec lequel on souhaite travailler puis => **Assigner**.
        9. Apres l'assignation on obtient:

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-settings-5-ssm.png)

        - ***L’image précédente affiche le nombre de jeux de données, de rapports et de tableaux de bord inclus dans l’environnement actuel, **Développement**. À chaque phase, vous avez la possibilité de publier l’espace de travail associé en tant qu’application en sélectionnant **Publier l’application**.*
        10. Pour afficher tous les objets qui constituent l’espace de travail => **Afficher plus**.
4. **Phase de test**
    - Pour effectuer la phase de test:
        1. Selection **Déployer pour tester**
            - *Cette action va créer un nouvel espace de travail qui porte par defaut le meme nom que l'espace de travail initial mais avec un suffixe **[Test]***
                - *Il est possible de modifier ce nom en entrant les paramètres de l’espace de travail dans l’interface du pipeline de déploiement*
        2. Le test doit émuler les conditions que les objets vont rencontrer une fois qu’ils seront déployés vers les utilisateurs finaux. 
            - *Ainsi, Power BI permet de modifier la source des données utilisées pendant le test.* 
            - Pour cela, **il faut d’abord entrer les paramètres de déploiement de l’environnement en sélectionnant l’icône représentant un éclair**

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-pipeline-1-ssm.png)

        3. Dans la fenêtre **Paramètres** qui s’affiche on choisis le jeu de données approprié. 
            - Supposons que l'on souhaite que le jeu de donnée soit utilisé mais avec une source differente:
                - *On va créer des paramatres dans power query ou ajoutez une nouvelle regle.* 
                - Dans le menu deroulant **Regles de source de donnée** => Selection **+Ajouter une regle**

                ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-change-source-8-ss.png) 

                - Dans la section **Règles des sources de données** on peut modifier la source de données, qui a été utilisée lors du développement, pour la remplacer par une nouvelle, utilisée pour tester les rapports et une fois terminé =>  sélection **Enregistrer** en bas de la carte.

                ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-add-workspace-3-ssm.png)

        4. **Phase de production**
            -  ***Ici, on a besoin de créer une règle de source de données pour le jeu de données dans l’espace de travail pour garantir l’utilisation des données de production.***  
            - On va modifier la source en passant de la version du fichier qui se trouve dans le dossier test à la version production.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-change-source-7-ss.png)  

            - Une fois le jeu de données actualisé, l'espace de travail de production est prêt. 
                - on peut alors empaqueter l’espace de travail en tant qu’application, laquelle est alors disponible pour les utilisateurs finaux. 
                - Le pipeline de déploiement s’affiche comme illustré dans la figure suivante.

                ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-compare-9-ssm.png)

                - Ainsi, un pipeline de déploiement de la phase de développement à la phase de test a ete correctement créé 
5. **Autres opérations dans le pipeline de développement** 
    - Supposons que l'on recoive une notification indiquand que l'un des autres developpeur à modifier le rapport. 
        - Pour afficher les modifications apportées à ce rapport: 
            1. Selection **Comparer**

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-compare-11-ssm.png)

            2. Cela permet de vois si les operation different entre les environnement de développement et de test. 

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-data-source-rules-6-ssm.png)

            - La différence est généralement enregistrée sous forme d’objets ajoutés ou supprimés. 
                - Si on décide que les modifications ne doivent pas être déployées dans la phase suivante, On peut choisir d’ignorer les modifications. 
                    - *Par exemple, l’autre développeur a ajouté un rapport appelé "AdditionalOrderInfo" dans l’environnement de développement, mais on ne veut pas déployer ces modifications. En sélectionnant un rapport spécifique et en sélectionnant Déployer pour tester, on peut choisir les rapports à déplacer d’un environnement à l’autre.*

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-deployment-compare-10-ssm.png#lightbox)

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/04-dev-life-cycle-3-ssm.png#lightbox)

        - ***Il faut etre prudent avec cet outil. Les rapports dépendent de leurs jeux de données. Si un jeu de données a changé mais que on ne le déploie pas avec un rapport associé, le rapport ne se comportera pas correctement.***
        - **Il est recommandé d’utiliser des pipelines de déploiement dans le service Power BI.** 
            - *Non seulement cet outil garantit que le cycle de vie de développement est rationalisé, mais il permet aussi de créer un seul emplacement centralisé pour collaborer, suivre et déployer les rapports.*

#### Résoudre les problèmes liés aux données en consultant leur traçabilité
- *Dans la vue Traçabilité dans Power BI, il est possible d'actualiser rapidement des jeux de données et voir les relations qui existent entre les artefacts dans un espace de travail, ainsi que leurs dépendances externes.*
- La fonctionnalité d'affichage de la **Tracabilité** permet de determiner les jeux de données qui doivent etre actualisée. 
1. **Traçabilité des données**
    - La traçabilité des données fait référence au chemin suivi par les données depuis la source de données jusqu’à la destination.
        - La fonctionnalité d’affichage de la Traçabilité dans Power BI est cruciale, car :
            - Elle simplifie le processus de résolution des problèmes
                - On peut voir le chemin suivi par les données depuis la source jusqu’à la destination afin de déterminer facilement les points sensibles et les goulots d’étranglement.
            - Elle permet de gérer plus facilement les espaces de travail et de voir clairement l’impact d’une seule et même modification dans un jeu de données sur les rapports et tableaux de bord.
            - Elle permet de gagner du temps en facilitant l’identification des rapports et tableaux de bord qui n’ont pas été actualisés.
2. **Utiliser la vue Traçabilité** 

    [Voir Doc  Traçabilité des données.](https://learn.microsoft.com/fr-fr/power-bi/collaborate-share/service-data-lineage)

    - La vue Traçabilité n’est accessible qu’aux rôles d’**administrateur**, de **contributeur** et de **membre**. De plus, elle **nécessite une licence Power BI Pro** et n’est disponible que pour les **espaces de travail d’application**.
    - Pour accéder à la vue Traçabilité
        1. Accéès à l’espace de travail
        2. Sélection **Traçabilité** dans le menu déroulant **Vue** dans le ruban supérieur.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-opening-lineage-view-ssm.png)

        - Une fois que le canevas de la vue s’ouvre, on peut commencer à examiner cette vue. Ci-dessous, un extrait de la traçabilité des données de l’espace de travail, Tailwind Sales.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-excerpt-lineage-ssm.png)

        - Cette vue montre tous les artefacts inclus dans l'espace de travail. 
            - Les artefacts incluent les sources de données, les jeux de données et dataflows, les rapports et les tableaux de bord. 
            - Chaque carte représente un artefact et les flèches situées entre ces cartes représentent le flux des données ou la relation entre les différents artefacts. 
                - En suivant les flèches de gauche à droite, on peut voir le flux de données depuis la source jusqu’à la destination, qui est souvent un tableau de bord. 
                    - Ce flux est généralement le suivant : **sources de données** => **jeux de données/dataflows** => **rapports** => **tableaux de bord**.
                1. **Sources de données**
                    - Chacune des cartes suivantes est une source de données utilisée dans l'espace de travail.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-datasets-dataflows-lineage-view-3-ss.png)

                    - Cette carte indique le type de source de données (par exemple, Texte/CSV) et la passerelle, qui indique la source des données. 
                        - Si on est connectés aux données par le biais d’une passerelle de données locale, la carte fournira d’autres informations sur la passerelle. 
                        - De plus, en double-cliquant sur la carte, on obtient plus d’informations sur la source de données, comme le chemin du fichier et l’état de la connexion.
                    - La sélection de l’icône en bas à droite de la carte permet de surligner le chemin depuis la source de données jusqu’à la destination, ce qui indique plus clairement le chemin exact suivi par les données.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-card-icon-detail-ssm.png)
                
                2. **Jeux de données/dataflows** 
                    - Souvent, les jeux de données et dataflows peuvent se connecter à des sources de données externes, comme SQL Server ou des jeux de données externes issus d’autres espaces de travail. 
                    - Ci-dessous, des exemples de cartes de jeu de données et de dataflow dans la vue Traçabilité.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-dataset-from-different-workspace-4-ssm.png)

                    - La vue Traçabilité utilise des flèches pour connecter des objets, comme des jeux de données, à leurs sources de données. 
                        - Sur ces cartes: 
                            - On peut voir à quel moment le jeu de données a été actualisé pour la dernière fois. 
                            - On peut  aussi actualiser le jeu de données lui-même en sélectionnant l’icône en forme de flèche située en bas à gauche de la carte.

                            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-opening-lineage-view-1-ssm.png)

                        - Si un jeu de données ou dataflow appartient à un autre espace de travail (dans cet exemple, l’espace de travail Tailwind), celui-ci est indiqué sur la carte.

                        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-card-metadata-4-ssm.png)

                        - En double-cliquant sur n’importe quelle carte, on peut afficher les métadonnées, telles que la sensibilité, la personne qui a été configurée, la date de la dernière actualisation, ainsi que les noms et le nombre de tables dans ce jeu de données.

                        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-card-icon-detail-2-ssm.png)

                        - Il est également possible de voir l’impact de ce jeu de données sur tous les espaces de travail. En sélectionnant l’icône représentant des fenêtres superposées en bas à droite d’une carte de jeu de données, on peut déterminer l’analyse d’impact du jeu de données.

                        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-impact-analysis-icon-5-ssm.png)

                        - Dans la fenêtre **Analyse d’impact**, on peut voir le nombre d’espaces de travail, de rapports et de tableaux de bord auxquels ce jeu de données appartient, ainsi que le nombre de vues que ce jeu de données a récolté.

                        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-excerpt-lineage-2-ssm.png)

                        - Au bas de la fenêtre **Analyse de l’impact**, on peut voir plus d’informations sur les rapports et tableaux de bord spécifiques dont ce jeu de données fait partie. 
                            - De plus, onpeut **Notifier des contacts**, ce qui permet d’informer les propriétaires des jeux de données (ou tout autre utilisateur) des modifications apportées au jeu de données.
                            - *L’analyse d’impact s’avère utile pour déterminer si on a des jeux de données inutilisés ou non consultés.*
                3. **Rapports et tableaux de bord**
                    - Les cartes des rapports et tableaux de bord ont des fonctionnalités similaires à celles des cartes des sources de données et jeux de données.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-report-metadata-7-ssm.png)

                    - La sélection d’une carte entraîne l’affichage d’une fenêtre dans laquelle on peut voir les métadonnées relatives au rapport ou au tableau de bord. 
                        - Dans cette fenêtre, on peut également accéder directement au rapport ou au tableau de bord. on peut aussi activer ou désactiver l’inclusion du rapport ou tableau de bord dans l’application.

                        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-refresh-feature-card-8-ssm.png)

                        - Cette carte contient aussi des options utiles sous les points de suspension **(...)**, 
                            - Dans ce menu, on peut choisir d’analyser le rapport dans Excel, de le supprimer, de créer des insights rapides, de créer une analyse Quick Insights, d’enregistrer une copie dans un espace de travail, etc.

                            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/05-ellipsis-on-report-card-ss.png)

#### Configurer la protection des données

[Voir Doc Appliquer des étiquettes de sensibilité des données dans Power BI.](https://learn.microsoft.com/fr-fr/power-bi/enterprise/service-security-apply-data-sensitivity-labels)

- Il faut souvent appliquer des exigences et des réglementations strictes pour veiller à ce que les données sensibles soient sécurisées. 
    - Power BI offre plusieurs méthodes pour aider à accomplir cette tâche :
        - Utilisez les étiquettes de confidentialité Microsoft pour étiqueter les tableaux de bord, les rapports, les jeux de données et les dataflows suivant la même taxonomie que celle utilisée pour classer et protéger les fichiers dans Microsoft 365.
        - Ajoutez des mesures de protection supplémentaires, comme le chiffrement et les filigranes, lors de l’exportation des données.
        - Utilisez Microsoft Cloud App Security pour superviser et examiner les activités dans Power BI.
    - ***Supponsons que l'on veuille mettre une securité de telle sorte que aucun utilisateur n'est la possibilité d'exporter des données sans autorisation. par conséquent il faut implementer des mesures de sécurité compplete pour proteger l'accès aux données à la fois dans Power BI et en dehors. et en fin configurer des étiquettes de protection des données dans Power BI.***
        - *Avant de commencer, vérifier qu'on a les licences appropriées, comme indiqué [Dans la documentation](https://learn.microsoft.com/fr-fr/power-bi/enterprise/service-security-data-protection-overview).*

1. **Étiquette de confidentialité**
    - Les étiquettes de confidentialité spécifient les données qui peuvent être exportées. Ces étiquettes sont configurées à l’extérieur de Power BI, qui permet de les utiliser rapidement et facilement dans les rapports et tableaux de bord.
    - Elles permettent de définir et de protéger le contenu, même en dehors de Power BI. Les jeux de données, les flux, les rapports et les tableaux de bord peuvent utiliser ce mécanisme, et tous les utilisateurs peuvent utiliser cette fonctionnalité, sauf si des exceptions ont été définies.
    - Une fois qu ela capacité d'ajouter des étiquettes est vérifier:
        1. Accès à l'espace de travail 
        2. Choisir une objet à sécuriser 
        3. Selection **Parametres** (sous les points de suspension **(...)**)

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/06-exporting-excel-4-ssm.png)

        4. Une fenetre s'affiche et dans laquelle on peut attibuer une étiquette de confidentialité aux données. 
            - Par exemple si les étiquette **Aucune**, **Personnel**, et **Général**, **Confidentiel** et **Hautement confidentiel** on etait extérieurement configuré, on peut les appliquer aux données. 

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/06-sensitivity-settings-1-ssm.png)

            - Par exemple, si on souhaite affecter une étiquette **Confidentiel** au rapport ***Sales Data*** , lorsque on modifie cette étiquette dans le volet Paramètres , elle apparaît sous la forme d’une étiquette sur le rapport.

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/06-reports-dashboards-cards-6-ss.png)

            - **Ce facteur est essentiel lorsque on exporte des données**. 
                - Les données exportées vers des fichiers **Microsoft Excel**, **Microsoft PowerPoint** et **PDF** ont des étiquettes de confidentialité appliquées. 
                    - *Par exemple, si on souhaite exporter des données de données de ventes dans un fichier Excel, si on est un utilisateur autorisé, on vera la vue Excel suivante lorsqu'on exporte dans Excel.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/create-manage-workspaces-power-bi/media/06-dashboard-with-label-4-ssm.png)

                    - ***Toutefois, si on a pas d’autorisations établies, l’accès sera refusé pour afficher les données. Cette vérification garantit que seuls les utilisateurs appropriés ont accès à l’affichage des données, ce qui permet de s’assurer que les données sont sécurisées.***








