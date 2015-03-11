
### Environnements
 1. Local : Ordinateur du développeur, peut être un serveur physique
 2. Testing [**Est proche de la Production**] :
  * Possède la **même version de software**.
  * les **mêmes daemons**.
  * les mêmes caractéristiques de serveur physique ou les mêmes containers (RAM, Disque, Network, …).
  * Si Production utilise plusieurs serveurs, alors Testing possède plus de un serveur (ex: test de load-balancing).
  * De vraies données (peut être une partie des données de Production).
  * Configuré pour **afficher toutes les erreurs**.
  * Intègre plus de modules et d'outils de **Débugging / Profiling / Analyse**.
  * Les développeurs effectuent leurs **tests unitaires** en **Intégration Continue**.
  * Uniquement disponible pour les développeurs.
 3. Staging [**Est identique à Production**], c'est un miroir direct :
  * Possède la **même version de software**.
  * les **mêmes daemons**.
  * les mêmes caractéristiques de serveur physique ou les mêmes containers (RAM, Disque, Network, …).
  * Si Production utilise plusieurs serveurs, alors Testing possède plus de un serveur (ex: test de load-balancing).
  * De vraies données (peut être une partie des données de Production).
  * L'affichage des **erreurs est désactivé**.
  * Aucun modules ou outils de debugging installé.
  * Disponible pour l'équipe de Q&A et les bêtas-testeurs.

  Staging permet de simuler ce qui va se passer lors d'un push en live. Très utile pour se rendre compte si on a oublié quelqu un fichier type image ou stylesheet.
 4. Production : 

### Légende
* Couleur rouge : Bug à corriger
* Couleur jaune : Fonctionnalité à créer

### Workflow Kanban :
##### 1. Icebox/Brainstorming [ ] :
 * Chaque fonctionnalité correspond à une story
 * Chaque story comporte des sous-taches
 * Un développeur est chargé d'une tache d'une story

##### 2. Current/Develop [2 stories max]:
 * Implement [4 taches max]: Chaque développeur implémente une tache et la test en local.
 * Ready [4 taches max]: La tache est prête à être envoyée dans Testing

##### 3. Testing [4 stories max]: Test final sur l'environnement de test (configuration identique)
 * In progress : En cours de test dans l'environnement serveur de test ()
 * Ready : Une fois que toutes les taches d'une story sont prête, la story est envoyé dans Staging.

##### 4. Staging [1 story max] :
 * Wait : En attente de validation de l'équipe de Q&A
 * Ready : L'équipe de Q&A a validé la story (fonctionnalité ou bug) qui est prête pour la Production

##### 5. Done/Released