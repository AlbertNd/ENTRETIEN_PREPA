#  création de mesures à l’aide de DAX dans Power BI

- DAX (Data Analysis Expressions) est un langage de programmation utilisé dans Microsoft Power BI pour créer des colonnes calculées, des mesures et des tables personnalisées. Il s’agit d’une collection de fonctions, d’opérateurs et de constantes qui peuvent être utilisés dans une formule ou une expression pour calculer et retourner une ou plusieurs valeurs.
- Dans Power BI, il existe différentes techniques et fonctions de calcul permettant de créer des mesures ou des colonnes calculées. i lest possible d'obtenir le même résultat à l’aide de ces techniques.

#### Usage des colonnes calculées
- DAX permet de créer une colonne calculée qui n’existait pas à l’origine dans les sources en question.

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-table-visual-ss.png)

- On peut créer une colonne calculée qui multiplie le prix unitaire par la quantité
    - Elle produit une valeur pour chaque ligne, appelée **Total Price** (Prix total)
- Pour se faire => sélection du bouton points de **suspension (…)** sur la **table** dans la **liste Champs**, =>  sélection **Nouvelle colonne**.

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-column-ss.png)

- ***Une nouvelle formule DAX apparaît dans la barre de formule qui se trouve sous le ruban du haut.***

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-dax-column-ss.png)

- On peut remplacer le texte par defaut "Column = "
    - `Total Price = 'Sales OrderDetails'[Quantity] * 'Sales OrderDetails'[Unit Price]`
        - La valeur à gauche du signe égal correspond au nom de la colonne. 
        - Le texte situé à droite du signe égal est l’expression DAX. 
            - Cette expression DAX simple prend la valeur Quantity (Quantité) et la multiplie par la valeur Unit Price (Prix unitaire) pour chaque ligne. *Elle produira une valeur pour chacun des enregistrements de la table*. 
        - Si on fait glisser la nouvelle colonne de la liste Champs vers le visuel, il y aura les nouvelles valeurs.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-total-price-ss.png)

        - **NB:** ***Les colonnes calculées sont matérialisées dans l’extension de fichier Power BI. pbix, ce qui signifie que, chaque fois qu’une colonne calculée est ajoutée, la taille de l’ensemble du fichier augmente. Un trop grand nombre de colonnes calculées ralentit les performances et fait atteindre plus rapidement la taille de fichier maximale Power BI.***

1. **Création d’une colonne personnalisée** 
    - Il existe trois façons de créer une colonne personnalisée dans Power BI :
        1. Créez la colonne dans la requête source lorsque vous récupérez les données, par exemple en ajoutant le calcul à une vue dans une base de données relationnelle.
        2. Créez la colonne personnalisée dans Power Query.
        3. Créez une colonne calculée à l’aide de DAX dans Power BI Desktop.