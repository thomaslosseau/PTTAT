# PTTAT : Personal Triathlon Trainer Assistant Tool

## Intentions
L'outil a pour but de faciliter le travail d'entraineur en passant moins de temps sur la plannification. L'outil ferait la plannification annuelle sur base de quelques éléments et la plannification hebdomadaire sur base de cette plannification. Il s'adapte évidemment à l'athlète concerné. L'outil serait capable de d'adapter l'entrainement prévu sur base de certaines remarques imposées. Possibilité de grouper des athlètes sur une même plannification.

Dans un second temps, l'outil pourrait stocker les informations en ligne et compléter un google drive directement.
Dans un troisieme temps, l'outil est en platteforme sur un site. Les athlètes ont un compte et peuvent accéder à leur plannification. Directement faire leurs retours sur la plateforme. Prévoir leurs jours d'entrainement et que les entrainements plannifiés par l'outil soient directement mis sur leur montre. 

## Objectifs Généraux
* **[P]** Plannifier jusqu'à un objectif majeur selon des conditions et des règles générales
* **[P]** Plannifier des séances sur base du moment dans la prépa générale (donc sur base de la période, du moment dans le cycle, du type de séance et de l'athlète)
* **[P]** Possibilité de modifier ce qui est plannifié

* Ecriture de la plannification sur un document en ligne

* Site sportif avec accès personnel
* Réception d'un carnet d'entrainement
* Synchronisation avec les applications et montre sportives

## Décomposition plus spécifique
### Plannification annuelle
* Création d'un plan sur base d'un fichier structuré de règles : priorité de blocs, TSS
* Adaptation du plan sur base de contraintes : début, fin, dates de compétitions, vacances, temps disponible, points faibles de l'athlète, ...
* Impression lisible et claire du plan
* Modification sur l'impression lisible et lecture de celui-ci par l'outil
* Stockage du plan

### Plannification d'une séance
* Sur base des critères de la plannification annuelle, d'un fichier de règles pour les séances et de l'athlète, crée une séance calcule le TSS estimé de chaque séance et adapte l'entrainement à cela
* Impression lisible et claire de la séance
* Lecture d'une séance et adaptations si modifications
* Stockage

## Liste de tâches
1. Structure et organisation des dossiers/fichiers
2. Classe athlète
3. Définir les règles de plannification
4. Plannifier annuellement
5. Impression plannification annuelle
6. Ajouter petit à petit des contraintes
7. Lecture d'une impression de plannification annuelle et enregistrement selon changements
8. DB Athlètes + Plannification annuelle + Séances
9. Règles des types de séances
10. Creation séance sur base d'un fichier de règles et de l'athlète
11. Lecture d'une semaine du plan annuel
12. Création des séances selon la semaine du plan annuel et de l'athlète
13. Impression séance
14. Lecture d'une impression de plannification de séance et enregistrement selon changements
15. Contraintes préalables supplémentaires à une séance

## Détail de chaque tâche
### Structure et organisation des dossiers/fichiers
### Classe athlète
### Définir les règles de plannification
### Plannifier annuellement
### Impression plannification annuelle
### Ajouter petit à petit des contraintes
### Lecture d'une impression de plannification annuelle et enregistrement selon changements
### DB Athlètes + Plannification annuelle + Séances
Si je me rappelle bien de mes cours sur les databases, il me faut faire des tableaux, avec chaque ligne et des exemples. L'objectif c'est d'avoir au global le moins d'infos redondantes possible et la lecture la plus simple possible. Jamais plus de deux informations communes par lignes qui ne changent pas. Dans ce cas-ci, pas d'importance de sécurité des données, je n'aurai que le nom prénom et date de naissance des athlètes comme données vraiment privées donc OSEF.
DB Athlètes :  
| #Athlète | Nom | Prénom | Date de Naissance | [#Pépas] |
|--|--|--|--|--|
| a1 | Van Lierde | Frederik | 25/05/1979 | [p1,p2] |
| a2 | Michel | Claire | 13/10/1988 | [p2] |
| a3 | Bashir | Abdi | 10/02/1989 | [p3] |
> j'ai un doute sur la colonne [#Prépas] peut-être serait il préférable de garder les athlètes dans une prépa plutôt que dans les 2 sens

DB Prépas :   
| #Prépa | Nom | Sport | [#Athlètes] |
|--|--|--|--|
| p1 | KONA2013 | Triathlon | [a1] |
| p2 | JO2024 | Triathlon | [a1,a2] |
| p3 | JO2024 | CaP | [a3] |
> Oui FVL n'a pas fait les JO2024
### Règles des types de séances
### Creation séance sur base d'un fichier de règles et de l'athlète
### Lecture d'une semaine du plan annuel
### Création des séances selon la semaine du plan annuel et de l'athlète
### Impression séance
### Lecture d'une impression de plannification de séance et enregistrement selon changements
### Contraintes préalables supplémentaires à une séance
