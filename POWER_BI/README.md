# Power BI 

## Aplication  
- Application de bureau **Power BI Desketop**
- [Service SaaS](https://playground.powerbi.com/fr-fr/explore-features) en ligne (Software as a Service ou logiciel en tant que service) appellé **service Power BI**
- Application mobile
## Composant de power BI 

### Les blocs de construictions 
1. Visualisations 
2. Jeux de données 
3. Rapports 
4. Tableaux de bord 
5. Vignettes 

- **Visualisation:** 
    - Representation visuelle des données 
        - Graphique 
        - Carte en couleur 
        - Autre images de representation des donées 
    - ***NB: Les elemsnts visuelles permettent de representer les données de maniere à fournir du contexte et des informations, chose qui est difficile à dégager avec un tableau brut comportant des chiffres ou du texte.***
- **Jeux de données:**
    - Collection de données pour créer des visualisation. 
        - Peut etre issues de plusieurs source differente  via des connecteur integrer dans Power BI  
            - Excel 
            - MSQL 
            - Azure
            - Oracle 
- **Rapport**
    - Un rapport est une collection de visualisation, d'elements liés les uns aux autres, qui apparaissent ensemble sur une ou plusieurs pages. 
- **Tableaux de bord**
    - C'est une collection de visuelle que l'on peut partager avec d'autre utilisateurs. autrement dit, c'est un groupe d'elements visuelle choisis afin d'offrir une vue globale des données ou des informations à presenter 
    - ***NB: Il doit tenir sur une page appeller Canvas***
- **Vignettes**
    - C'est une visualisation unique figurant dans un tableaux de bord
    - ***Si on conculte un tableau de bord et que l'on est pas les proprietaire, il est impossible de changer la taille ni la disposition des vignettes.

### Exploration et utilisation du services PowerBI 

- **Une application :** Collection de rapports et de vissuels prets à l'emploi et predefinis, partagé avec l'ensemble d'une organisation. 

### Création des tableaux de bord prédefinis avec les services cloud

- Connection a des données 
   1. **Obtenir des données** (Coin inferieur gauche de la fenetre d'aceuil) 
    - Presentation des source disponible dans le service Power BI

### Nettoyage, transformation et chargement des données dans Power BI

***PowerBI et Power Query offre un environnement puissant pour nettoyer et preparer les données.*** 

### Mise en forme des donnée initiales**

- L'éditeur **Power Query** de Power BI Desktop permet de mettre en forme (transformer) les donnée importées. 
    - Renommer des colonnes ou des tables 
    - Changer du texte en nombre 
    - Supprimle des lignes 
    - Définir la premiere lignes comme en tete 
    - .... 
1. Demarrage de l'edituer power Query 
    - Dans l'application desktop: 
        - Onglet acceuil
            - Trasformer les données 
                - Transformer les données => Editeur Power Query 
                    - Voir Volet de gauche pour les données de la requetes
            - *Les étapes effectuer pour mettre ne forme les données sont eregistrées et à chaque fois que la requete se connecte à la source de données, elle applique automatiquement les étapes.* 
            *Les données sont toujours mises en forme selon ce que l'on spécifie.*
            *L'éditeur apporte les modifications seulement à une vue particuliere des données.* ***Aucune modification ne sera apporter  à la source de données d'origine***
            - La liste des étapes et des propriétés de la requete peut etre consulter sur le coté droit de l'ecran dansle volet **Paramatres de la requete**
            - [Fonctionalité](https://docs.microsoft.com/fr-fr/power-query/power-query-ui#the-query-ribbon)  

2. Identification des entete et des noms de colonnes
    1. Déterminer leur emplacement et etre sur qu'ils sont au bon endroit. 
    2. Promouvoir les en-tete
        - ***Mettre la premiere lignes de de la table comme en-tete de colonne.***
            - **Onglet Acceuil**
                - Option : Utiliser la premiere ligne pourles en-tete. 
                - Ou button de liste deroulant sur la colonne et selection de l'option. 
    3. Renomer des colonnes 
        - Boutton droit sur l'en-tete et selectionner Renommer 
        - Doubler clicker sur l'en-tete.
    4. Suppression des lignes du haut 
        -  Onglet Acueil
            - Supprimer les lignes 
                - Supprimer les premiere lignes
    4. Suppression des colonnes 
        - Selection dela collonne 
            - Ognlet Acueil
                - Supprimer les colonnes.
    5. Pivoter les colonnes en cas de besoin. 
        - Onglet Transformer 
            - Pivoter 
            - Depivoter    

### Simplification de la structure des données 
- Examination des noms des requetes(tables) pour determiner siil y a des ameliorations à y apporter, examiner le contenu des colonnes et remplacer les valeurs necessitant des corrections.

1. Renommer une requte 
    - Dans le volet requete 
        - Selection de la requete a renomer 
            - Click sur le bouton droit 
                - Selectionner renommer
2. Remplacement des valeurs 
    - Selection de la colonne
    - Editeur Power BI 
        - Onglet transformer 
            - Remplacer les données
                - Valeur à rechercher
                - Remplacer par 
                - OK  
3. Remplacement des valeurs null 
    - Editeur Power BI 
        - Onglet transformer 
            - Remplacer les données
                - Valeur à rechercher =`null`
                - Remplacer par =`0`
                - OK  
4. Suppression des doublons 
    - Selection de la colonne 
        - Click droit 
            - Supprimer les doublons
 
 ### Evaluation et changement des types de données des colonnes 
 - ***Lorsqu'on importe des données Power BI Desktop demarre automatiquemnet l'analyse des 1000 premiere lignes et essaye de detecter le type des données dansles colonnes. Il arrive que Power BI ne detecter pas les données correctes. ce qi amene des probleme de performance.*** 

1. Implication des types de données incorrects 
    - Les problemes que souleve Power Bi lorsque les données sont incorrects
        - Impossible des creer certains calcul
        - Impossible de creer des relation avec d'autre tables 
2. Changement de types de données d'une colonne
    - Dans l'éditeur de données de Power Query 
        - Selection de la colonne 
            - Onglet transformation 
                - Type de donnees 
    - Dans la vue rapport Power BI avec l'outils colonne
        - Selection du type de donnée en regardant l'en-tete de la colonne 
            - Selection de typpe de données corrects dans la liste
[Pour plus d'info](https://docs.microsoft.com/fr-fr/power-bi/connect-data/desktop-data-types)

### Combinaison de plusieurs tables en une seule 

[Documentation](https://docs.microsoft.com/fr-fr/power-bi/connect-data/desktop-shape-and-combine-data)

- On peut combiner des tables dans une seule : 
    - Si il existe trop de tables
    - Si plusieur tables ont un role similaire 
    - Si une table n'a qu'une ou deux colonnes qui peuvent etre transferées dans une autre table
    - Si Si on souhaite utiliser plusieurs colonnes de differentes tables dans une colonne personnalisée. 
-  On peu combinner des tables de deux maniere differentes : 
    1. **L'ajout de requetes:**  
        - Onglet Aceuil
            - Combiner 
                - Ajouter des requetes
                    - ***Va ajouter les lignes d'une tables existantes dans une autre** 
                - Ajouter des requete comme etant nouvelle)
                    - Le resultat de l'ajout aboutit à une nouvelle requete ou une nouvelle table.
                        - Tables disponibles => tables à ajouter
    2. **Fusion des requetes** 
        - Onglet Aceuil
            - Combiner 
                - Fusionner des requetes
                    - ***Fucionner les requetes revient a combiner les données de plusieurs tables en une seule sur base d'une colonne comune entre les tables. => Clause JOIN dans SQL*** 
                - Fusionner les requetes comme nouvelles  
                    - Ouverture d'une nouvelle fentre avec choix de table à fusionner et ensuite choix de la colonne commune aux tables 
                - NB : **Il est possible de choisir les maniere de combiner les tables => JOIN dans SQL**
                    - Externe gauche : Toutes les lignes de la premiere table et les lignes correspondant de la deuxieme
                    - Externe entiere : Toutes les lignes des deux tables 
                    - Interne : Les lignes correspondant entre les deux tables. 
    - **NB: L'ajout de requeter revient a ajouter des lignes de données à une autre table. fusionner revient a ajoutez des colonnes d'une tables dans une autre via une colonne clef entre les deux**

### Profilage des données dans Power BI 
- Leprofilage consiste à étudier les nuances des données : 
    - Déterminer les anomalies 
    - Examiner et développer les structures de données sous-jacentes 
    - interroger les statistiques des données 
    - .....
- ***Concepte permettant de mettre en forme et d'organiser les données, afin de facilité l'interaction, l'identification de la structure de données afin de faciliter l'utilisation en front-end*** 

1. L'examination des structures des données.
    - Avant de l'examination dans léditeur Power Query.
        - Visualisation du model des données => `Onglet Modelisation`
            - Possiblite de : 
                - Modification des propriete de colonne et des tables 
                - Transformer les données avec **Transformer les données**(Power Query) 
                - Onglet Gere les relation les relation 
                    - Creer 
                    - Supprimer 
                    - Modifier 
                    - Gerer 
2. Recherche des anomalies des données et les statistiques des données.
    - L'éditeur Power Query détermine les anomalie des données avec la fonctionalité **Distribution des colonnes**
        - Onglet acceuil
            - Tranformer les données 
                - Editeur Power Query 
                    - Onglet affichage 
                        - Dans la zone Apercu des données 
                            - Distribution des données 
                                - *La distribution des données dans la colonne, le nombre de valeurs distinctes et uniques*
                            - Qualité de la colonne 
                                
                            - Profil de colonne
                                - *Analyse plus approfondie des statistiques des colonnes pour les* ***1000*** *premiere lignes de donnée.* 
                                - Nombre de ligne 
                                - Valeur minimale et maximale 
                                - Valeur hors norme par Power BI 
                                - Lignes vide et des chaines 
- ***NB : Par défaut, Power Query examine les 1 000 premières lignes de votre jeu de données. Pour modifier ce paramètre,*** **sélectionnez l’état du profilage dans la barre d’état, puis sélectionnez Profilage de colonne basé sur l'ensemble du jeu de données.**
        

### Utilisation de l'editeur avancé pour modifier le code M 

- [Documentation code M](https://docs.microsoft.com/en-us/powerquery-m/)

- Onglet acceuil
    - Tranformer les données 
        - Editeur Power Query         
            - Onglet affichage
                - Editeur avancé 





