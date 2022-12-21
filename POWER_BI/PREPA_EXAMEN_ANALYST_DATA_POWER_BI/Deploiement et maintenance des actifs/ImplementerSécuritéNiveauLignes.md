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
- ***La méthode statique dans la sécurité au niveau des lignes utilise une **valeur fixe dans le filtre DAX**, tandis que la méthode dynamique **utilise une fonction DAX**.***
- La sécurité au niveau des lignes implique plusieurs étapes de configuration qui doivent être effectuées dans l’ordre suivant :
    1. Créer un rapport dans Microsoft Power BI Desktop.
        1. Importer les données.
        2. Confirmer le modèle de données entre les deux tables.
        3. Créer les visuels de rapport.
    2. Créer des rôles **RLS** (Role-Level Security ) dans Power BI Desktop en utilisant DAX.
    3. Tester les rôles dans Power BI Desktop.
    4. Déployer le rapport sur le service Microsoft Power BI.
    5. Ajouter des membres au rôle dans le service Power BI.
    6. Tester les rôles dans le service Power BI.

1. **Création d’un rapport dans Power BI Desktop** 
    - Faire les étapes normales pour créer un rapport dans Power BI Desktop. 
        - Utilisez Microsoft Power Query pour récupérer et nettoyer les données. 
        - Vérifiez que la relation existe entre les deux tables en utilisant l’onglet Modélisation ; *il doit s’agir d’une relation un-à-plusieurs dans la colonne empID de l'exemple ci-dessous.*

        ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-power-bi-report-ss.png)

        - *Il faut noter que la table précédente contient des lignes pour toutes les ventes de tous les départements. On va limiter la visibilité afin que seuls les employés d’un département spécifique puissent voir leurs propres ventes.*
2. **Créer des rôles RLS dans Power BI Desktop** 
    - Pour créer des rôles RLS dans Power BI Desktop, 
        1. sélection de l’onglet **Modélisation**
        2. sélection **Gérer les rôles**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-manage-roles-ss.png)

        3. Dans la page Gérer les rôles, sélection **Créer**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-create-button-ss.png)

        - **La sécurité au niveau des lignes Power BI utilise DAX pour contrôler qui peut voir quelles données.**
            - *On peut l’imaginer comme étant toujours en train d’ajouter un autre filtre aux utilisateurs appropriés, quels que soient les filtres, les segments ou les interactions qu’ils choisissent sur un rapport Power BI.*

        4. Dans la page **Gérer les rôles**, 
            - On crée un rôle pour chaque département et on lui ajoute une expression DAX. 
                - *Par exemple, on peut créer un rôle appelé Jeu, puis ajouter l’expression **DAX [department] = "Jeu"**. Ensuite, chaque fois qu’un membre de ce rôle interagit avec le rapport, Power BI ajoute ce filtre à ses interactions, limitant ainsi ce qu’il voit.*

                ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-manage-roles-dax-ss.png)

            - Une valeur fixe est utilisée dans le filtre à droite du signe égal (dans le cas présent, "Jeu"). 
                - Cela signifie que, si on doit ajouter une catégorie, il faut créer un rôle avec une nouvelle valeur dans l’expression DAX.
            - Il faut noter comment le filtre DAX est appliqué à la table de dimension. 
                - *La sécurité au niveau des lignes est plus efficace lorsque les données sont organisées dans un schéma en étoile.* 
                    - *n applique le filtre DAX à une table de dimension, comme cela a été fait avec la table Produits.*
            - Le filtre DAX est appliqué à chaque interaction, segment et filtre que l’utilisateur applique. Si on a un filtre DAX qui fonctionne mal, l’expérience utilisateur en sera affectée. Par conséquent, on garde le filtre DAX aussi simple que possible.
3. **Tester les rôles dans Power BI Desktop** 
    - On peut vérifier que le filtre fonctionne en sélectionnant l’onglet **Modélisation**, puis **Afficher comme rôles**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-view-role-ssm.png)

    - Dans la fenêtre **Afficher comme rôles**, 
        - sélection du le rôle Jeu. 
            - Le rapport est maintenant rendu comme si on ete dans ce rôle et on ne voit que les enregistrements inclus dans le département Jeu.

            ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-row-level-security-results-ss.png)
    
    - ***On peut annuler ce filtre en sélectionnant à nouveau **Afficher comme rôles**, puis **Aucun**.***
4. **Déployer le rapport dans le service Power BI**
    - On peut déployer le rapport sur le service Power BI en sélectionnant le bouton **Publier** sous l’onglet **Accueil**, puis en sélectionnant un espace de travail.

5. **Ajouter des membres au rôle dans le service Power BI** 
   - Pour ajouter des membres au rôle dans le service Power BI, 
        1. On accéde à l'espace de travail dans le service Power BI. 
        2. On recherche le jeu de données qu'on a créé avec le même nom que le rapport. 
        3. On sélectionne le bouton de sélection **(...)**, puis **Sécurité**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-dataset-secuirty-ssm.png) 

        - Dans l’écran **Sécurité au niveau des lignes**, 
            - On peut ajouter des utilisateurs Microsoft Azure Active Directory (Azure AD) et des groupes de sécurité au rôle de sécurité. 
                - *Lorsque des membres sont ajoutés à ce rôle, le filtre DAX que l'on a défini précédemment leur est appliqué. Si des membres ne sont pas ajoutés au rôle, mais qu’ils ont accès au rapport, la sécurité au niveau des lignes ne s’applique pas à ces derniers.*
                    -  *On peut ajouter les trois personnes du département Jeu au rôle Jeu. Et maintenant, quand ces membres se connectent, ils voient uniquement le rapport avec les données qui s’appliquent à eux.*

                    ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-row-level-security-ss.png)

6. **Tester les rôles dans le service Power BI**
    - On peut tester les rôles dans le service Power BI en sélectionnant les points de suspension **(...)** à côté du rôle Jeu sur l’écran Sécurité au niveau des lignes, puis en sélectionnant **Tester comme rôle**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/02-test-as-role-ss.png)

    - Cette sélection affiche le rapport comme si on etait membre du rôle dans le service Power BI.

#### Configurer la sécurité au niveau des lignes avec la méthode dynamique
- On peut configurer la sécurité au niveau des lignes une seule fois, sans qu’il soit nécessaire de continuer à la gérer de manière dynamique.

- Supposons que l'on souhaite que la securité au niveau des lignes Power BI montre uniquement les ventes à la personne qui les a réalisées.
    - *Dans cet exemple, Russel King a réalisé quatre ventes. Lorsqu’il consulte le rapport, Russel ne doit voir que les ventes dont il est responsable et aucune autre.* 
    - On peut configurer la sécurité au niveau des lignes exactement comme fait avant, avec une seule modification. 
        - Au lieu de créer quatre rôles, on a besoin d’en créer qu’un seul.    
    - **Le filtre DAX pour ce rôle ressemble à l’image suivante.**

    ![](https://learn.microsoft.com/fr-fr/training/modules/row-level-security-power-bi/media/03-dynamic-ss.png)

    - Il faut noter qu’à la place de la chaîne fixe, telle que **Jeu** ou **Habillement**, une fonction DAX est utilisée dans le filtre de sécurité au niveau des lignes. 
        - La fonction **userprincipalname()** compare l’adresse e-mail de la table Employés à l’e-mail que l’utilisateur a entré pour se connecter au service Power BI. 
            - *Si Russel King utilise l’adresse e-mail russel@tailwindtraders.com pour se connecter au service Power BI, le système compare cette valeur à l’adresse e-mail figurant dans la table Employés. En supposant qu’une relation a été créée entre Employés et Ventes, Russel voit uniquement ses quatre ventes.*
