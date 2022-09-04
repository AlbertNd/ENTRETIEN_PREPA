# Data Analysis Expression (DAX)

### Introduiction 
- Pour produire des rapport et des tableaux de bord appropriés, il faut une bonne comprehension des question que les utilisateurs du rapport et du tablea de bord peuvent poser.
    - Il donc se concentrer sur la conception de modele de données qui prendra le mieux en charge les visualisations dans les rapport et tableaux de bord.
- Au developpement du modele, on effectue les taches suivante.
    1. Se connecter aux données
    2. Transformer et préparer les données 
    3. Definir la logique métier en ajoutant des calcul **DAX**
    4. Appliquer des autorisation de données avec la sécurité au niveau des lignes en ajoutant des roles
    5. Publier le modele sur Power BI
- **NB:** ***Les modeles optimaux sont importants pour offrir de bonnes performances de requete et pour reduire les temps d'actualisation des données et l'utilisation des ressources de service y compris la memoire et le processeur.***

### Conception des schémas en étoile

1. **Tables de faits**
    - Le role d'une table de fait est de stocker une accumulation des lignes qui represent des **observations** ou des **evenements** qui enregistrent une **activité métier spécifique**.
        - Table de fait de vente 
            - Des commande client 
            - Lignes de commande 
        - Table de fait enregistrement des mouvement de stocks 
        - Table de fait pour les soldes boursier ou les taux d'échange qutidiens de la devise. 
    - Dans les requete anlytique, les données de la table de faits sont résumées pour produire des valeurs telles que les ventes et la quantité.
2. **Tables de dimension**
    - Le table de dimension decris des **entetités metier**.
        - Personnes
        - Lieux
        - Produit ou concepte
            - Une table de dimension qui contient une ligne pour chaque date est un exemple courant de table de dimension de concept.
    - ***Les colonnes des tables des dimensions permettent le filtrage et le regroupement des données de la table de faits***
    - Chaque table de dimension doit avoir une colonne unique, **la colonne clé**. 
        - Pas de valeur dupliquée
        - Pas de valeur manquant 
    - Les colonnes supplementaires stockent des valeurs descriptives: 
        - Nom 
        - Sous-catégorie
        - Catégorie
        - Couleur 
        - etc... 
    - ***Dans les requetes analytiques, les colonnes sont utilisé pour filtrer et regrouper les données.***
3. Tableau de comparaison 

|**Caracteristiques**|**Table de dimension**|**Table de faits**|
|---|---|---|
|**Objectif du modèle**| Stocke les entités métier| Stocke les événements ou les observations|
|**Structure de table**| Contient une colonne clé et des colonnes descriptives pour le filtrage et le regroupement|Contient les colonnes de clé de dimension et les colonnes de mesure numériques qui peuvent être résumées|
|**Volume de données**|En général, contient moins de lignes (par rapport aux tables de faits)|Peut contenir de nombreuses lignes|
|**Objectif de la requête**|Pour filtrer et grouper|Pour résumer|

### Association des tables de schéma en étoile 

[Voir Doc](https://docs.microsoft.com/fr-fr/power-bi/guidance/star-schema)

- Dans le modele, les tables de dimension sont liées aux table de faits à l'aide de relation **un-à-plusieurs**
    - Les relations permettent aux filtres et aux groupes appliqués aux colonne de la table de dimension de se propager à la tables de faits.
- Les tables de dimension peuvent être utilisées pour filtrer plusieurs tables de faits et les tables de faits peuvent être filtrées par plusieurs tables de dimension
- **NB:** ***l n’est pas recommandé de lier une table de faits directement à une autre table de faits.***

[Pour la pratique, telecahregement d'Adventure Works DW 2020 M01.pbix](https://docs.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms#data-warehouse-downloads)

### Les requetes analytiques 
- Une **requete analytique** est une requete qui produit un resultat à partir d'un model de données. 
    - une requête analytique est écrite sous la forme d’une instruction de requête DAX (Data Analysis Expressions)
        - ***NB: outefois, vous n’avez pas besoin d’écrire une instruction DAX native. Il vous suffit de configurer des objets visuels de rapport en mappant les champs de jeux de données.***
    - Une requete analytique comporte trois phases:
        1. **Filtrer**
            - Le filtre ou le decopage cible les données de pertinence. Les filtre peuevent etre appliquer à trois etendues differentes: 
                1. Le rapport complet
                2. Une page spécifique 
                3. Un objet du visuel
        2. **Grouper**
            - Le refroupementou le decoupage divise les résultats de requete en groupes 
        3. **Résumer**
            - Le  résumé produit un résultat de valeur unique. 
                - Les colonne numerique sont résumé en à l'aide de méthodes de résumé
                    - **Somme**
                    - **nombre**
                    - **nombre-distinct**
                    - **pourcentage**
                    - **moyenne**
                    - **mediane**
                    - **minimum , maximum**
                    - **ecart-type**
                    - etc ... 
- **NB:** *** Toutes les requetes analytiques n'ont pas besoin de filtrer, de grouper, de résumer***
    - En règle générale, les objets visuels de rapport sont filtrés, par exemple par une période ou un emplacement géographique.
    - Le regroupement est facultatif. Par exemple, un objet visuel de carte, qui est utilisé pour afficher une valeur unique, n’est pas concerné par le regroupement.
    - En règle générale, les objets visuels de rapport résument. L’une des exceptions notables, toutefois, est l’objet visuel de segment, qui n’est pas concerné par le résumé.

### Configuration des objets visuels de rapport 
- Lors de la conception, l'ajout et la configuration d'un objet visuel de rapport impliquent la méthodologie suivante: 
    1. Sélectionner un type d'objet visuel, comme une graphique. 
    2. Mapper les chmps de jeux de données , ***affichés dans le volet champs***, sur les zones de configuration des champs visuels. 
        - Pour une graphique a barres, les zones de configuration sont 
            - **Axe Y**
            - **Axe X**
            - **Légende**
            - **Petits multiples**
            - **Info-Bulles**
    3. Configurer des champs mappés 
        - Il est possible de renommer des champs mappés ou de basculer le champ pour qu’il soit résumé ou non résumé. Si le champ résume, vous pouvez sélectionner la méthode de résumé.
    4. Appliquez des options de mise en forme, telles que les propriétés d’axe, les étiquettes de données et bien d’autres.

- **Les champs**
    - Champs est un terme collectif utilisé pour décrire une resource de modele qui peut etre utilisée pour configurer un objet visuel. 
        - Les trois ressources de modele differentes qui sont des champs sont les suivant: 
            1. **Colonnes** 
                - Il est possible d'utiliser les colonnes pour filtrer, grouper, resumer les valeurs de colonnes. 
                - Il est possible de résumer les colonnes de texte à l'aide de:
                    - Premier (par ordre alphabetique)
                    - Dernier
                    - nombre ou nombre-distinct
            2. **Niveau de hiérarchie**
                - Alors que les niveaux de hiérarchie sont basés sur des colonnes, ils peuvent être utilisés pour filtrer et grouper, mais **pas pour être résumés**.
                - Il est possible de résumer la colonne sur laquelle est basé le niveau de hiérarchie, à condition qu’elle soit visible dans le volet Champs
            3. **Mesures**
                - Elle sont concus pour résumer les données de modele. 
                - Elle ne peuvent pas etre utiliser pour grouper les données.
                    - ***NB:Toutefois, les mesures peuvent être utilisées pour filtrer les données dans un cas particulier : pour utiliser une mesure pour filtrer un objet visuel lorsque l’objet visuel affiche la mesure et que le filtre est un filtre de niveau visuel (donc, pas un rapport ou un filtre au niveau de la page). Lorsqu’il est utilisé de cette manière, un filtre de mesures est appliqué après la requête analytique a résumé les données Ce processus est effectué pour éliminer les groupes pour lesquels la condition de filtre de mesure n’est pas true. (Pour ceux qui sont familiarisés avec la syntaxe SQL, une mesure utilisée pour filtrer un objet visuel est semblable à la clause HAVINGdans une instruction SELECT.)***

# Ecrire des formules DAX pour les modeles Power BI Desktop

