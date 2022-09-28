# La matière abordée dansles labos Microsoft Power BI 

1. **Préparation des données dans Power BI => [(Voir Labo)](https://learn.microsoft.com/fr-fr/training/modules/get-data/lab-prepare)** 

    1. ***Enregistrer le fichier Power BI Desktop***
    2. ***Définir les options de Power BI Desktop***
        - Fichier => Options et paramètres => Options => dans le groupe fichier actif => chargement des données *(Les paramètres de Chargement des données pour le fichier actif permettent de définir des options qui déterminent les comportements par défaut lors de la modélisatio)* => Deselection des options de relations
    3. ***Obtenir des données de SQL Server***
        - Acceuil => zone Données => Selection SQL Server 
            - Zone Serveur => localhost => Utiliser mes informations d’identification actuelles.
        - Fenetre de navigation => selection des 6 tables 
        - Tranformer les données => éditeur Power Query 
    4.  ***Afficher un aperçu des requêtes SQL Server***
        - Bare d'etat => statistique de la table 
        - Derniere colonne contenant liens tbales et valeur *(colonnes représentent les relations avec d’autres tables de la base de données. Elles peuvent être utilisées pour joindre des tables ensemble.)*
        - Evaluation de la qualité, distribution, profilage des colonnes 
            - Affichage => zone apercus des données
    5. ***Obtenir des données d’un fichier CSV***
        - Ajout d'une nouvelle requête
            - Acceuil => zone nouvelle requete => Nouvelle source => Texte/CSV 
    6. ***Obtenir des données supplémentaires d’un fichier CSV***

2. **Modéliser les données dans Power BI Desktop (partie 1)** 
    1. ***Créer des relations de modèle***
        1. Demarrage
        2. Créer des relations de modèle
            - Dans Power BI Desktop => selection de l'icone Modele => 7 tables 
            - Dans Power BI Desktop => selection de l'icone Rapport
            - Creation d'une visuel Product|Categorie & Sales|Sales
            - relation dela table Product et sales pour le visuel 
                - Modelisation => relations => gere les relations => nouveau => Fenetre créer une relation => Connection des clef dans les deux tables.
                - Relation un à plusiers 
                - Direction du filtre croisé => sens unique 
                - Rendre cette relation => active 
            - Création de relation à partir du diagramme 
    2.  ***Configuration des tables ***
        1. Configurer la table Product
            - Création de hierarchie 
                - Volet champs  => click droit sur colonne => Creer une hierarchie 
                    - Volet propriétés => zone nom 
                    - Deuxieme hierarchie => volet propriété => liste deroulant hierarchie => selection de la sous catégorie souhaité
                    - ...
                - Pour terminer => *Appliquer les changements de niveau*
            - Organisation des colonne dans une dossier d'affichage 
                - Selection des colonnes souhaité => volet Popriétés => zone Dossier d'affichage => introduire mise en forme ( nom du dossier) 
        2. Configurer la table Region
            - Configurer la table Reseller
            - Catégorisation: càd placement de la colone country (pas celle de la hierarchie) dans la catéorie des Country/region *(Utile pour le rendu visuel de la carte)*
                - Volet propriété => Avancé => liste deroulante catégorie de données => Country/Region
        3. Configurer la table Reseller
            - Configurer la table Reseller
            - Categorisation : 
                - Country-Region dans la catégorie Pays/Région
                - State-Province dans la catégorie Département ou province
                - City dans la catégorie Ville
        4.  Configurer la table Sales
            - Description de la colonne
                - Volet propriété => description
            - Mise en forme colonne 
                - Volet propriété => section mise en forme:
                    - Separateur de miliers => Oui 
                    - Nombre deciaml
            - Avancé 
                - Totaliser par la moyenne 
        5. Mettre à jour en bloc les propriétés
    3.  ***Examiner l’interface du modèle ***
        - Vue rapport 
        - Volet chammps 
            - les colonnes 
            - les hierarchies
            - champs visibles 
            - ornément d'icone et symbole 
            - info bulle
        - Hierarchie date automatique 
        - desactivation de Date/heure automatique 
            - fichier => Option et paramettre => options => fichier actif => chargement des données => time intelligence => date/heure automatique.
    4.  ***Création des mesures rapides ***
        1. Créer des mesures rapides
            - Click droit sur la tables => Nouvelle mesure rapide.