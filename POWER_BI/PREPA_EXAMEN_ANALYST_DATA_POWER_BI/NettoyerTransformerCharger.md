# Nettoyage, transformation et chargement des données 
- Lorsque l'on importe des données et que l'on les analyse on recontre souvent plusieurs problemes qui peuvent rendre l'analyse incorect. 
    - Une colonne appelée **Employment status** contient seulement des nombres.
    - Plusieurs colonnes contiennent des erreurs.
    - Certaines colonnes contiennent des valeurs Null.
    - L’ID client apparaît dans certaines colonnes comme s’il était dupliqué de façon répétée.
    - Une même colonne d’adresse contient l’adresse postale, la ville, l’état et le code postal combinés.
    - ...
- Power BI et Power Query offrent un environnement puissant pour nettoyer et préparer les données.Les avantages des données propre: 
    - ***Les mesures et les colonnes produisent des résultats plus précis quand des calculs et des agrégations sont effectués sur celles-ci.***
    - ***Les tables sont organisées, où les utilisateurs peuvent trouver les données de façon intuitive.***
    - ***Les doublons sont supprimés, ce qui simplifie la navigation dans les données. Elles se traduisent aussi par des colonnes qui peuvent être utilisées dans des sélecteurs et des filtres.***
    - ***Une colonne complexe peut être fractionnée en deux colonnes plus simples. Plusieurs colonnes peuvent être combinées en une seule colonne pour des raisons de lisibilité.***
    - ***Les codes et les entiers peuvent être remplacés par des valeurs lisibles par les humains.***
#### Mise en forme des données initiales 
- L’éditeur Power Query de Power BI Desktop permet de mettre en forme (transformer) vos données importées:
    - Renommer des colonnes ou des tables, 
    - Changer du texte en nombre, 
    - Supprimer des lignes, 
    - Définir la première ligne comme en-tête, 
    - etc...

#### Bien demarrer avec l'editeur Power Query
- Onglet **Accueil** => **transformer les données** => **éditeur Power Query**

![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-open-query-editor-transform-button-ssm.png)

- Dans l’éditeur Power Query:
    - Toutes les étapes effectuées pour mettre en forme les données sont enregistrées. 
        - Chaque fois que la requête se connecte à la source de données, elle applique automatiquement les étapes : 
            - Les données sont toujours mises en forme selon ce que l'on a spécifié. 
             aucune modification n’est apportée à votre source de données d’origine. Vous pouvez voir une liste de vos étapes sur le côté droit de l’écran, dans le volet  Paramètres de la requête, ainsi que les propriétés de la requête. 
