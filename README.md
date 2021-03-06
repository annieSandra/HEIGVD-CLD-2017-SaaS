# LABORATOIRE 4 - Software as a sercice 

Dans ce laboratoire nous nous intéressons aux infrastructures cloud de type software as a service et plus particulièrement à salesforce. Nous allons premièrement crée un compte salesforce gratuit et nous familliariser avec l'application. Ensuite, évaluer les capacités d'importation de donnée depuis notre appli et préparer notre appli pour la vente (exportation de donnée). Enfin, évaluer les capacités de contrôle de mise à jour.

## ETUDIANTS 

* FRANCHINI Fabien
* DONGMO NGOUMNAI Annie Sandra

## TABLE DES MATIERES 

1. [Tâche 1: Inscription saleforce](#t%C3%82che-1-inscription-salesforce)
2. [Tâche 2: Familiarisation avec l'application](#t%C3%82che-2-familiarisation-avec-lapplication)
3. [Tâche 3: Evaluation de capacité d'importation des données](#t%C3%82che-3-evaluation-de-capacite-dimportation-des-donnees)
4. [Tâche 4: Preparation pour la vente](#t%C3%82che-4-preparation-pour-la-vente)
5. [Tâche 5: Evaluation des capacités de mise à jour de contrôle](#t%C3%82che-5-evaluation-des-capacites-de-controle-de-mise-a-jour)

## TÂCHE 1: INSCRIPTION SALESFORCE 

À partir du site officiel de salesforce nous avons choisit free trial(option 30 jours gratuit) pour créer notre compte 
![inscription salesforce](assets/images/CreationCompte.png)
nous sommes invité à entrer nos données 
![inscription salesforce](assets/images/creationCompte2.png)
après validation par email du compte crée, on se connecte pour la première fois à l'appli et une page d'accueil nous est affiché avec 4 différentes options de visites
![inscription salesforce first Connection](assets/images/CreationCompte3.png)


## TÂCHE 2: FAMILIARISATION AVEC L'APPLICATION

Nous allons commençer notre visite par la gestion des encours 
![gestion des encours](assets/images/FamiliarisationApplication1.png)
en choisissant d'afficher toutes opportunitées on obtient un tableau d'opportunité avec 50 éléments et leur description (nom opportunité, montant, date cloture etc voire figure)
![gestion des encours](assets/images/familiariasationAppliToutesLesOpportunitees3.png)
on constate qu'on peut également choisir de visualiser ses opportunitées sous forme de `kanban` (voire figure)
![gestion des encours opportunité vue kanban](assets/images/familiarisationAppliVueKanban.png)

## TÂCHE 3: EVALUATION DE CAPACITE D'IMPORTATION DES DONNEES

ici nous allons tenter d'importer le fichier `contact.csv` contenant les données suivantes :
```
 Firstname, Lastname, Email, Preffered food
 Albert, einstein, aeinstein@hes-so.ch, French
 Bertrand, Piccard, bpiccard@hes-so.ch, Italian
 Claude, Nicollier, cnicollier@hes-so.ch, Mexican
```
pour cela dans la barre de menu nous choisissons l'option `configuration` une page d'acceuil s'affiche puis dans l'onglet `donnée` de la section `Administration` nous choisissons l'option `Assistant d'importation de donnée` (voire figure suivante):
![evaluation capacité importation de donnée](assets/images/tache3ClickOnImportationDonnée.png)

la page suivante s'affiche nous proposant de lancer l'assistant d'importation
![evaluation capacité importation de donnée](assets/images/Tache3LancementAssistantdImportationSuite1.png)

une fois lancer l'importation se passe en 3 étapes: 
- `selection des données` : c'est ici qu'on choisi le type de données à importer (comptes et contact, piste, solution, etc), l'action à éffectuer (dans notre cas est d'ajouter de nouveaux enregistrements), l'emplacement des données (fichier CSV, outlook CSV, etc) qui dans notre cas est un fichier CSV : 
![evaluation capacité importation de donnée](assets/images/tache3ImportingDataCSV1.png)

- `modification de mappage` : c'est ici qu'on peut mapper les champs de notre CSV qui n'ont pas pu automatiquement être mappé par exemple dans notre cas `Preffered food` n'a pas pu être mappé(avec un champ existant de salesforce) on peut donc choisir manuellement le champ de salesforce sur lequel il sera mappé dans notre cas nous n'avons pas choisit de champ il ne sera par conséquent pas importer dans salesforce.
![evaluation capacité importation de donnée](assets/images/tache3ImportationdataCSV2.png)

- `Démarrage importation` : c'est ici que l'utilisateur choisit ou pas d'importer ses données avec les configurations qu'il a fait dans notre cas nous avons 3 champs mappés et un champ non mappé
![evaluation capacité importation de donnée](assets/images/tache3ImportationdataCSV3.png)

une fois terminer l'importation on reçoit par email un message de confirmation d'importation. Si on va dans l'onglet contact de la barre de menu et qu'on selectionne tous les contacts on remarque qu'il y a les 3 nouveaux contacts qu'on a rajouté(albert,bertrand, claude) avec leur champs non spécifiés vides (tel le telephone, nom du compte etc):
![evaluation capacité importation de donnée](assets/images/tache3ImportationdataCSVTermineeTousLesContact.png)

## TÂCHE 4: PREPARATION POUR LA VENTE

ici nous allons exporter toutes les données de salesforce pour le fournisseur. La procédure est presque identique à celle de l'importation sauf que dans ce cas nous choisissons l'option `Exporter les données` puis le boutton `exporter maintenant`
![preparation pour la vente](assets/images/tache4ExportingData1.png)

une fois terminé quelques minutes plutard nous reçevons par email un message pour confirmer la reception de l'exportation
![preparation pour la vente](assets/images/tache4ExportingDataReceiveConfirm.png)

un click sur le lien de confirmation nous affiche la page suivante avec le ZIP des données
![preparation pour la vente](assets/images/tache4exportingdata2.png)

une fois téléchargé on remarque le zip contient un ensemble de fichier CSV parmi lesquels le fichier Contact.csv dont les dernières entrées sont celles des données importées précédement:
![preparation pour la vente](assets/images/tache4exportingDataResultzipwithMyImport.png)

il est claire que pour quelqu'un qui ne s'y connait pas ça fait toute suite un champ de bataille de données(on compte 118 fichiers csv) presque incompréhensible vu la longueur des differentes tables (grand nombre de champ).En plus s'il faut comparer par exemple le fichier `Lead.csv` à la table `Lead` du model de donné officiel il y a une énorme différence dans le .csv on compte 45 champ alors la table Lead du modèle de donné contient 8 champs
![preaparation pour la vente](assets/images/tache4Lead.PNG)
![prepartion pour la vente](assets/images/tache4exportingdataSchema.png)

## TÂCHE 5: EVALUATION DES CAPACITES DE CONTROLE DE MISE A JOUR

Ici nous allons visualiser les mises à jour contrôlable par l'utilisateur. Pour cela nous sommes parti dans `configuration`-> `paramètres de la société` -> `mise à jour critique` : 
![evaluation de capacité de controle mise ajour](assets/images/tache5MiseAJourCritique.png)

Ainsi l'utilisateur pourra tester l'influence des mises à jour programmer en les activant et notant le comportement de son appli pour y adapter en attendant les mises à jour officielles. En générales ces mises à jour influences l'application client et donc par conséquent le client qui l'utilise. On peut dire que grâce à ce featuring (visualisation mise à jour critique avant leur date effective activation ) implementer par salesforce 1 l'utilisateur pourra d'une certaine manière contrôler correctement l'application malgrès les différentes mises à jour.

