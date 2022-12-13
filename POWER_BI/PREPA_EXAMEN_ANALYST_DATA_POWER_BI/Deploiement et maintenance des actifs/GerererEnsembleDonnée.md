# Gérer les jeux de données dans Power BI
- *Quand les jeux de données sont publiés dans l’espace de travail de l'organisation dans le service Microsoft Power BI, toute personne ayant besoin d’un accès à ces jeux de données peut les trouver à un emplacement central, ce qui offre des possibilités de collaboration entre les équipes. 
    - Cela réduit également les travaux effectués en double, car un jeu de données peut être utilisé par plusieurs utilisateurs pour des raisons métier différentes. 
    - *Par exemple, un jeu de données peut être utilisé pour créer plusieurs rapports Power BI. Comme la préparation et le nettoyage des données peuvent prendre beaucoup de temps, le partage des jeux de données peut être un accélérateur de productivité pour les créateurs de rapports.*
- Le partage de jeux de données doit être géré activement pour des performances organisationnelles optimales. 
    - *Par exemple, il est possible d'automatiser le processus d’actualisation pour le rendre plus efficace et pour que les utilisateurs aient toujours accès aux données les plus récentes.*
    - *Il est également possible de promouvoir certains jeux de données par rapport à d’autres, afin que les utilisateurs puissent identifier clairement les meilleurs jeux de données à utiliser.*
- La gestion des jeux de données implique également l’implémentation de paramètres dans ces jeux de données, afin de favoriser la prise de décisions et la résolution des problèmes métier. 
    - *Par exemple, on peut utiliser des paramètres pour modifier le nom du serveur ou de la base de données du jeu de données, ou le chemin pour une source de données.* 
    - *On peut aussi utiliser des paramètres pour configurer des actualisations incrémentielles des données, et pour exécuter des scénarios de simulation et effectuer une analyse de type scénario sur les données.*
- Un autre aspect important de la gestion des jeux de données est la configuration et la maintenance d’une passerelle, pour permettre à sois-même et à d’autres utilisateurs d’accéder à la source de données locale à partir du cloud. 
    - Il faut également se préparer à des problèmes potentiels susceptibles de survenir en rapport avec la passerelle et qui pourraient interrompre l’accès utilisateur aux jeux de données. 
        - *Un problème de connectivité de service peut s’avérer nuisible à la productivité des utilisateurs. S’ils ne peuvent pas accéder aux données, ils ne peuvent pas travailler et la capacité de prise de décision de l’organisation sera à l’arrêt. Il est essentiel d’être préparé à traiter de tels problèmes en temps utile.*
1. **Créer des rapports dynamiques avec des paramètres** 
    - Pour créer un rapport dynamique:
        1. Acceuile dans Power BI desktop => Selection **Optenir les données**.
        2. Selection Base de donnée SQL
        3. Introduire les details 
        4. Selection **Options avancées** 
        5. Mettre la requete dans la zonne d'instruction

            ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-add-query-execution-statement-ssm.png)

            ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-sql-query-ss.png)
        
        6. Selection **Modifier** pour ouvrir les données dans l'éditeur Power Query. 
        7. Création des paramatres
            1. Sou l'onglet **Acuiel** => Selection **Gerer les parametres** => **Nouveau parametre** 
            2. Dans la fenêtre Paramètres, on remplace le nom du paramètre par défaut par un nom plus descriptif pour rendre explicite son objectif.
            3. Selection **Texte** dans la liste **Type** et **N’importe quelle valeur** dans la liste **Valeur suggérée**.
            4. **OK**

            ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-add-parameter-ss.png)

            5. Une nouvelle requete s'affiche 

            ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-parameter-query-ss.png)

            6. Ajuster le code dans la requête SQL pour évaluer votre nouveau paramètre :
                1. Clic droit sur **Query1**  => sélection **Éditeur avancé**.
                2. On remplace la valeur existante de l’instruction d’exécution par une esperluette **(&)** suivie du nom du paramètre.

                ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-adjust-sql-query-statement-ssm.png)

                3. On vérifie qu’aucune erreur ne s’affiche en bas de la fenêtre => **Terminé**.
                    - *On remarquer aucune différence sur l’écran, mais Power BI aura bien exécuté la requête.*
                4. Pour vérifier que la requête a bien été exécutée, on peut effectuer un test en sélectionnant la requête de paramètre et en entrant une nouvelle valeur dans la zone Valeur actuelle.

                ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-enter-parameter-value-ss.png)

                - Une icône d’avertissement devrait s’afficher en regard de la requête. Si tel est bien le cas, on selectionne cette requête pour voir le message d’avertissement, lequel indique qu’une autorisation est nécessaire pour exécuter cette requête de base de données native =>  Sélection **Modifier une autorisation**, puis **Exécuter**.

                - Lorsque la requete s'execute avec succés, le parametre se met à jour et affiche la nouvelle valeur.

                ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-paramenter-updated-values-ss.png)

                5. **Fermer et Appliquer** pour revenir à l'éditeur de rapport.
            8.  Application des parametre au rapport 
                1. Selection **Modifier les requetes** => **Modifier les parametres**
                2. Dans la fenêtre **Modifier les paramètres**, introduire une nouvelle valeur => **OK**.
                3. Sélection **Appliquer les modifications**, puis réexécuter la requête native.
                    - Les données pour la nouvelle valeur ont été passée via le paramètre.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-apply-parameter-report-ss.png)

                    - On peut désormais créer un rapport affichant des données pour une valeur particulière à la fois. Si on veut afficher des données pour plusieurs valeurs en même temps, il faut effectuer des étapes supplémentaires.
2. **Créer des rapports dynamiques pour plusieurs valeurs**
- ***Pour tenir compte de plusieurs valeurs à la fois, il faut d’abord créer une **feuille de calcul Excel** avec une table composée d’une colonne contenant la liste des valeurs.* 
- ***Ensuite, on utilise la fonctionnalité **Obtenir les données** dans Power BI Desktop pour se connecter aux données de cette feuille de calcul Excel, puis suivez ces étapes :***
    1. Dans la fenêtre **Navigateur** => sélection **Modifier** pour ouvrir les données dans l’éditeur Power Query => une nouvelle requête pour la table de données.

    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-table-query-pane-ss.png)

    2. On renomme la colonne de la table avec un nom plus descriptif.
    3. On change le type de données de la colonne en **Texte** afin qu’il corresponde au type de paramètre et pour éviter des problèmes de conversion des données.
    4. Dans la section **Propriétés** de la requête, on change également le nom de la source de données en quelque chose de plus descriptif.
    5. Creation d'une fonction qui va passer la nouvelle requete dans **Query1**
        1. Clic droit sur **Query1** => sélection **Créer une fonction**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-create-function-option-ssm.png)

        2. Introduire un nom pour la fonction => **OK**.
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-create-function-window-ss.png)

        - La nouvelle fonction va apparaître dans le volet Requêtes.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-function-query-pane-ssm.png)

        3. Pour que **Query1** n’apparaisse pas dans la liste de champs du rapport, ce qui pourrait potentiellement perturber les utilisateurs, on peut désactiver son chargement dans le rapport en cliquant avec le bouton droit sur **Query1**, puis en sélectionnant **Activer le chargement** *(sélectionnée par défaut)* pour désactiver la fonctionnalité.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-enable-load-option-ssm.png)

        4. Sélection de la requête chargée à partir de la feuille de calcul Excel puis, sous l’onglet **Ajouter une colonne**, sélection **Appeler une fonction personnalisée** pour exécuter la fonction personnalisée ainsi créée.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-invoke-custom-function-option-ssm.png)

        5. Dans la fenêtre **Appeler une fonction personnalisée**, sélection de la fonction dans la liste Requête de fonction.
            - Le **Nouveau nom de colonne** se met à jour automatiquement et la table qui contient les valeurs qu'il faut passer via le paramètre est sélectionnée par défaut
        6. Sélection **OK** et on exécute si nécessaire la requête native.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-invoke-custom-function-window-ss.png)

        - Une nouvelle colonne pour la fonction *GetSalesFromSalesPerson* va apparaître en regard de la colonne *SalesPersonID*.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-function-column-ss.png)

        7. Sélection de l’icône avec deux flèches dans l’en-tête de la nouvelle colonne, puis cocher les cases des colonnes que l'on veut charger. 
            - Dans cette section, on détermine les détails qui seront disponibles dans le rapport pour chaque valeur *(ID de vendeur)*.
        8. On décoche la case **Utiliser le nom de la colonne d’origine comme préfixe** dans le bas de l’écran, car on a pas besoin de voir un préfixe avec les noms des colonnes dans le rapport.
        9. **OK**

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-select-columns-function-ss.png)

        - Et normalement les données pour les colonnes sélectionnées, pour chaque valeur *(ID de vendeur)*.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/2-view-columns-function-ss.png)

        - *Si nécessaire, on peut ajouter d’autres valeurs (ID de vendeur) à la colonne SalesPersonID dans la feuille de calcul Excel ou modifier les valeurs existantes*.
        
        10. On enregistre les modifications, puis retour à l’éditeur Power Query.
        11. Sous l’onglet **Accueil**, sélection **Actualiser l’aperçu**, puis réexécuter la requête native (si nécessaire). 
            - *Il y a les ventes des nouveaux ID de vendeur ajoutés dans la feuille de calcul*.
        12. **Fermer et appliquer** pour revenir à l’éditeur de rapport, où se trouve les noms des nouvelles colonnes dans le volet Champs.
        13. Création des rapport

#### Créer des paramètres de scénario
- On peut utiliser des **paramètres de simulation** pour exécuter des scénarios et une analyse de type de scénario sur les données. 
    - *Les paramètres de simulation sont des ajouts puissants aux modèles de données et aux rapports Power BI, car ils permettent d’examiner les données d’historique pour analyser les résultats potentiels si un scénario différent s’était produit. Les paramètres de simulation peuvent aussi aider à anticiper, à prédire ou à prévoir ce qui pourrait se produire dans le futur.*
- On peut utiliser des **paramètres de simulation** dans plusieurs situations, 
    - *par exemple pour déterminer l’effet de remises plus substantielles sur l’augmentation des ventes, ou pour permettre aux conseillers commerciaux de voir leur rémunération s’ils atteignent certains objectifs ou pourcentages de vente.*
- ***Supposons par exemple que l'on veut determiner l'augmentation (le pourcentage) des ventes a realisé pour atteindre un chiffre d'affaires brut de 2 million chaque mois***

1. **Créer un paramètre de scénario** 
- Pour créer un parametre de simulation:
    1. Onglet **Modélisation** => selection **Nouveau parametre**
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-add-what-if-parameter-ssm.png)

    2. Dans la fenêtre **Paramètre de scénario**, configuration du nouveau paramètre.
    3. On change le nom du paramètre. *Ex Sales Forecast Percentage (Pourcentage de prévision des ventes)*.
    4. On sélectionne le **Nombre décimal fixe** comme **Type de données**, *car onutilise une devise dans les prévisions*.
    5. On définis la valeur **Minimum** sur **1**, la valeur **Maximum** sur **1,50** et la valeur **Incrément** sur **0,05**, ce qui correspond au degré d’ajustement du paramètre quand il fait l’objet d’une interaction dans un rapport.
    6. On définis la valeur Par défaut sur **1,00**.
    7. On laisse la case **Ajouter un segment à cette page** cochée *pour que Power BI ajoute automatiquement un sélecteur avec le paramètre de simulation dans la page de rapport active.*
    8. **OK**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-configure-what-if-parameter-ssm.png)

    - ***Le nouveau visuel de sélecteur va apparaître dans la page de rapport active.***
        - ***On peut déplacer le curseur pour voir les nombres augmenter en fonction des paramètres appliqués. On voit aussi un nouveau champ pour la table Sales Forecast Percentage dans le volet Champs et, quand on developpe ce champ, le paramètre de simulation doit être sélectionné.***

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-view-what-if-slicer-ssm.png)

        - De même, on peut qu’une mesure a également été créée. On peut utiliser cette mesure pour visualiser la valeur actuelle du paramètre de scénario.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-view-what-if-measure-ssm.png)

        - Une fois que l'on a créé un paramètre de simulation, ce paramètre et la mesure font partie du modèle : ils sont donc disponibles dans le rapport et peuvent être utilisés sur d’autres pages du rapport. En outre, étant donné que le paramètre et la mesure font partie du modèle, on peut supprimer le sélecteur dans la page du rapport. Si on veut le rétablir, on peut faire glisser le paramètre de simulation depuis la liste Champs dans le canevas, puis changer le type de visuel en « sélecteur ».

2. **Utiliser un paramètre de scénario**
    - Si on veut utiliser le paramètre de simulation après l’avoir créé, il faut créer une mesure dont la valeur s’ajuste avec le curseur.
        -  On peut créer des mesures complexes et uniques qui permettent aux utilisateurs des rapports de visualiser la variable du paramètre de simulation. Cependant, pour que cet exemple reste simple, la nouvelle mesure est le montant total des ventes, avec le pourcentage de prévision appliqué.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-create-new-measure-ss.png)

        - Ensuite, on crée un histogramme groupé avec le champ **MonthName** sur l’axe, et les mesures **GrossSales** et **Gross Sales Forecast** comme valeurs.
        - Au départ, les barres sont similaires ; cependant, au fur et à mesure qu'on deplace le curseur, on peut voir que la colonne Gross Sales Forecast reflète le pourcentage de prévisions des ventes.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-use-what-if-slicer-ssm.png)

        - Pour améliorer le visuel, on peut ajouter une ligne constante, de façon à voir clairement les performances de l’organisation par rapport à un seuil ou une cible spécifique. 
            - Par exemple, on va ajouter une ligne constante de 2 millions de dollars comme valeur de seuil. on va ensuite utiliser le curseur pour déterminer de quel pourcentage le chiffre d’affaires brut doit augmenter chaque mois pour atteindre ce seuil. 
            
            ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/3-add-constant-line-ss.png)
            
            - Ici, le chiffre d’affaires brut doit augmenter de 1,40 % pour atteindre le seuil de 2 millions de dollars.

#### Utiliser une passerelle Power BI pour se connecter à des sources de données locales

![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/4-overview-gateway-ss.png)

- *Le logiciel de la passerelle agit comme un pont:*
    -  *Il permet aux organisations de conserver des bases de données et d’autres sources de données sur leurs réseaux locaux ainsi que d’accéder à ces données locales dans des services cloud, comme Power BI et Microsoft Azure Analysis Services.*
- *Une passerelle favorise des flux de communication en arrière-plan rapides entre un utilisateur dans le cloud vers la source de données locale, puis en retour vers le cloud.*
- Les deux types de passerelles locales sont :
    - **Mode organisation**: permet à plusieurs utilisateurs de se connecter à plusieurs sources de données locales et convient à des scénarios complexes.
    - **Mode personnel**: permet à un utilisateur de se connecter à des sources de données. 
        - Ce type de passerelle peut être utilisé uniquement avec Power BI et ne peut pas être partagé avec d’autres utilisateurs. ***Il convient donc dans des situations où on est le seul utilisateur à créer des rapports***. on va installer la passerelle sur l'ordinateur local, qui doit rester en ligne pour que la passerelle fonctionne.

1. **Utiliser une passerelle locale**
    - Avant de pouvoir se connecter à la source de donnée locale , il faut [Installer la passerelle de données locale](https://learn.microsoft.com/fr-fr/data-integration/gateway/service-gateway-install) et puis la configurer en fonction des besoins.
    - Une fois que la passerelle locale est installée et configurée, on peut la démarrer, puis se connecter avec le compte d’organisation Microsoft 365.

    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/4-sign-in-gateway-ss.png)

    - Quand on travail dans le cloud et qu'on interagis avec un élément connecté à une source de données locale, les actions suivantes se produisent :
        - Le service cloud crée une requête et les informations d’identification chiffrées pour la source de données locale. La requête et les informations d’identification sont envoyées à la file d’attente de la passerelle pour traitement.
        - Le service cloud de passerelle analyse la requête et envoie les demandes à Microsoft Azure Service Bus.
        - Service Bus envoie les demandes en attente à la passerelle.
        - La passerelle reçoit la requête, déchiffre les informations d’identification et se connecte à une ou plusieurs sources de données avec ces informations d’identification.
        - La passerelle envoie la requête à la source de données à exécuter.
        - Les résultats sont renvoyés de la source de données à la passerelle, puis au service cloud. Le service utilise ensuite ces résultats.

        ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/4-how-gateway-works-ss.png)

2. **Résoudre les problèmes de la passerelle de données locale**
- La résolution des problèmes d’une passerelle est un sujet en perpétuelle évolution. 
    - Il faut se reporter aux documents suivants pour obtenir les informations les plus récentes en matière de résolution des problèmes :
        - **Pour voir comment exécuter un test de port réseau**, voir [Ajuster les paramètres de communication pour la passerelle de données locale.](https://learn.microsoft.com/fr-fr/data-integration/gateway/service-gateway-communication#network-ports-test/?azure-portal=true)
        - **Pour découvrir comment fournir des informations de proxy pour la passerelle**, voir [Configurer les paramètres de proxy pour la passerelle de données locale.](https://learn.microsoft.com/fr-fr/data-integration/gateway/service-gateway-proxy)
        - **Pour trouver la région actuelle du centre de données où vous vous trouvez**, voir [Définir la région du centre de données.](https://learn.microsoft.com/fr-fr/data-integration/gateway/service-gateway-data-region)

#### Configurer une actualisation planifiée de jeu de données
- La fonctionnalité **Actualisation planifiée** de Power BI vous permet de définir la fréquence et les créneaux horaires pour actualiser un jeu de données particulier. La planification de l’actualisation des données permet d’économiser du temps, car on a pas à actualiser manuellement les données. Elle garantit également que les utilisateurs finaux puissent accéder aux données les plus à jour.
- Supposons que l'on crée un rapport et que l'on se rend compte que la version des données de ventes que l'on utilise n'est pas la plus recente. Et vérifiant l'état d'actualisation on remarque qu'elles ont été actualisées pour la derniere fois il y a 10 jours et qu'aucune actualisation n'est planifiée.

![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-view-dataset-last-refresh-time-ss.png)

- Étant donné l’importance de disposer de données de ventes exactes, il faut trouver une solution. En règle générale, les données sont mises à jour chaque semaine, mais on ne veut pas revenir au rapport chaque semaine pour actualiser manuellement le jeu de données, et on peut parfois oublier de le faire. 
    - *On décide donc d’utiliser la fonctionnalité **Actualisation planifiée** de Power BI pour résoudre ce problème.*

1. **Configurer une planification d’actualisation**

- ***Avant de pouvoir configurer une planification d’actualisation, il faut avoir créé une connexion de passerelle.***
- Pour configurer une planification d’actualisation pour le jeu de données, on doit suivre ces étapes:
    1. Accédez à la page **Jeux de données + dataflows**.
    2. Placer le curseur sur le jeu de données pour lequel on souhaite configurer la planification => sélection de l’icône **Planifier l’actualisation**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-select-schedule-refresh-option-ssm.png)

    3. Dans la page Paramètres, on active la fonctionnalité **Actualisation planifiée**.
    4. Sélection de la **Fréquence d’actualisation** et veiller à ce que le fuseau horaire correct soit sélectionné.
    5. Ajouter la ou les heures auxquelles on souhaite que l’actualisation se produise. 
        - On peut configurer jusqu’à huit créneaux horaires quotidiens si le jeu de données figure dans une capacité partagée, ou 48 créneaux horaires dans Power BI Premium.
    6. une fois terminé de configurer l’actualisation planifiée => **Appliquer**.

    - Si on souhaite que le systeme actualise les données de ventes quotidiennement à 6:00, 10:00 et 15:00

    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-select-schedule-refresh-settings-ss.png)

    - Une fois qu ela configuration est plannifié, la pages des parametres du jeu de données informe de l'heure de la prochaine actualisation

    ![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-view-dataset-next-refresh-time-ssm.png)

2. **Effectuer une actualisation à la demande**
- En plus des actualisations planifiées, on peut actualiser un jeu de données à tout moment en effectuant une actualisation à la demande. Ce type d’actualisation n’affecte pas l’heure d’actualisation planifiée suivante.
    * Par exemple, on peut avoir besoin d’actualiser immédiatement, car on doit visualiser les données les plus récentes et on ne peut pas attendre la prochaine actualisation, ou bien on veut tester la configuration de la passerelle et de la source de données.
- Pour effectuer une actualisation à la demande, dans la page **Jeux de données + dataflows**, on pointe sur le jeu de données que l'on veut actualiser => sélection de l’icône **Actualiser maintenant**.

![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-select-refresh-now-option-ss.png)

3. **Vérifier l’état et l’historique d’actualisation**
- On peut vérifier l’état et l’historique d’actualisation à tout moment. Cette fonctionnalité est pratique si on veut déterminer à quel moment la dernière actualisation s’est produite et quand la prochaine est planifiée. C’est également une bonne pratique que de vérifier à l’occasion l’état des jeux de données pour voir si des erreurs d’actualisation se sont produites.
```
    Power BI désactive votre planification d’actualisation après quatre échecs consécutifs ou quand le service 
    détecte une erreur irrécupérable nécessitant une mise à jour de la configuration, par exemple des informations
    d’identification non valides ou ayant expiré. Il n’est pas possible de modifier le seuil d’échecs consécutifs.
```
- ***Un moyen rapide de vérifier l’état d’actualisation consiste à afficher la liste des jeux de données dans un espace de travail***

![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-view-dataset-next-refresh-time-2-ssm.png)

- Si un jeu de données affiche une petite icône d’avertissement, on sait que le jeu de données rencontre actuellement un problème. = > On sélectionne l’icône d’avertissement pour obtenir plus d’informations.

![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-refresh-error-message-ssm.png)

- Il faut également vérifier à l’occasion l’historique d’actualisation, pour passer en revue l’état de réussite ou d’échec des cycles de synchronisation passés. Pour afficher l’historique d’actualisation, ouvrir la page des paramètres du jeu de données, puis sélectionner **Historique d’actualisation**.

![](https://learn.microsoft.com/fr-fr/training/modules/manage-datasets-power-bi/media/5-check-refresh-history-ssm.png)

#### Configurer les paramètres d’actualisation incrémentielle
- La fonctionnalité **Actualisation incrémentielle** dans Power BI est une fonctionnalité très utilisée, car elle permet d’actualiser rapidement de très grands jeux de données et aussi souvent que nécessaire, sans devoir à recharger à chaque fois les données d’historique.
```
    L’actualisation incrémentielle doit être utilisée seulement sur les sources de données et les requêtes qui prennent 
    en charge le Query Folding. Si le Query Folding n’est pas pris en charge, l’actualisation incrémentielle risque
    d’entraîner une mauvaise expérience utilisateur : en effet, elle émet les requêtes pour les partitions appropriées,
    mais elle extrait toutes les données, éventuellement plusieurs fois.
```
- Habituellement, du code complexe était nécessaire pour effectuer des actualisations incrémentielles, mais on peut maintenant définir une stratégie d’actualisation dans Power BI Desktop. 
    - La stratégie d’actualisation est appliquée quand on publie sur le service Power BI, qui effectue ensuite le travail de gestion des partitions pour des charges de données optimisées, ce qui offre les avantages suivants :
        - **Actualisations plus rapides:** 
            - *Seules les données qui doivent être modifiées sont actualisées. Par exemple, si on dispose de 5 années de données et qu'on a besoin d’actualiser seulement les 10 derniers jours, car ce sont les seules données qui ont changé, l’actualisation incrémentielle actualise seulement ces 10 jours de données. Sans aucun doute, le temps nécessaire pour actualiser 10 jours de données est bien plus court que pour 5 années de données.*
        - **Actualisations plus fiables:** 
            - *On plus besoin de maintenir actives les connexions de données de longue durée pour planifier une actualisation.*
        - **Consommation réduite des ressources:** 
            - comme on doit actualiser seulement une quantité plus petite de données, la consommation globale de mémoire et d’autres ressources est réduite.
    - *Supposons que les donnée de rapport soitent obselete et que on ne peut pas actualiser manuellement les données en ajoutant un nouveau fichier car les actualisations doivent se produire régulierement pour correspondre à la fréquence des transactions commerciales qui se produisent. et de plus, la tache d'actualisation manuelle devient plus difficile car les jeux de données comportent des millions de lignes. il faut donc implémenter une meilleure solution d'actualisation des données.* 
        - *On peut définir une stratégie d’actualisation incrémentielle pour résoudre ce problème via les étapes suivantes:*
            1. Définir les paramètres de filtrage.
            2. Utiliser ces paramètres pour appliquer un filtre.
            3. Définir la stratégie d’actualisation incrémentielle.
            4. Publier les modifications sur le service Power BI.
1. **Définir les paramètres de filtrage**



























