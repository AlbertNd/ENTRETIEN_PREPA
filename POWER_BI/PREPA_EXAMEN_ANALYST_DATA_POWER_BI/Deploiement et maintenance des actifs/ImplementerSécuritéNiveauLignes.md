# Implémenter la sécurité au niveau des lignes
- ***Microsoft Power BI peut permettre de sécuriser des rapports et des espaces de travail en autorisant à les partager avec des utilisateurs ou des groupes Active Directory.
    - On peut aussi partager un seul rapport et faire en sorte que les utilisateurs voient des données différentes en fonction de leur poste.

- Supposons que l'on utilise la table suivante pour suivre les ventes

![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/01-sales-table-ss.png)

- On utilise aussi la table suivante pour les information sur les employers 

![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/01-employees-table-ss.png)

- Et le tableau suivant montre les produits 

![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/01-products-table-ss.png)

- *On souhaite créer un rapport où les employés d’un département spécifique peuvent uniquement voir les ventes de ce département.* 
    - *Par exemple, Maria Cameron travaille dans le département Jeu et doit uniquement voir les ventes de ce département, et pas celles des départements Sports, Habillement ou Automobile.*
- ***Ces données sont organisées dans un schéma en étoile. La table Ventes contient tous les attributs d’une table de faits, tandis que les employés et les produits sont des tables de dimension.*** 

![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/01-data-model-ss.png)

- Il existe deux façons d’implémenter la sécurité au niveau des lignes dans Power BI : 
    1. **la méthode statique** 
    2. **la méthode dynamique**
- **NB:** *La sécurité au niveau des lignes utilise un filtre DAX comme mécanisme de logique principal.* 

#### Configurer la sécurité au niveau des lignes avec la méthode statique