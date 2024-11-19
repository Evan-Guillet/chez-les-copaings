# Conventions de Nommage et Nomenclature - Projet Laravel & Vue.js

Ce document décrit les règles et conventions de nommage adoptées pour garantir la lisibilité, la maintenabilité et la cohérence de ce projet.

---

## Table des matières
1. [Structure générale du projet](#structure-générale-du-projet)
2. [Conventions de nommage](#conventions-de-nommage)
    - [PHP (Laravel)](#php-laravel)
    - [Vue.js & TypeScript](#vuejs--typescript)
    - [Bases de données (MariaDB)](#bases-de-données-mariadb)
3. [Branches GitHub](#branches-github)
4. [Langages à utiliser](#langages-à-utiliser)
5. [Bonnes pratiques](#bonnes-pratiques)

---

## Structure générale du projet

Vue simplifiée de la structure du projet (back) :
project-root/
```
├── app/
│   ├── Console/
│   ├── Http/
│   │   ├── Controllers/
│   │   ├── Middleware/
│   ├── Models/
│   ├── Services/
│   └── Helpers/
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── factories/
├── public/
├── resources/
│   ├── css/
│   ├── js/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── store/
│   │   └── types/
│   ├── views/
├── routes/
│   ├── api.php
│   ├── web.php
│   └── channels.php
├── storage/
├── tests/
└── webpack.mix.js
```


---

## Conventions de Nommage

### PHP (Laravel)

#### Dossiers
- **`app/Models/`** : Contient les modèles Eloquent. Les noms doivent être au **singulier** et en **PascalCase**.
  - Exemple : `User.php`, `OrderDetail.php`
- **`app/Http/Controllers/`** : Contient les contrôleurs. Les noms doivent être au **singulier** et en **PascalCase**, suivis de `Controller`.
  - Exemple : `UserController.php`, `OrderController.php`
- **`app/Http/Middleware/`** : Contient les middlewares. Les noms doivent refléter l’action et être en **PascalCase**.
  - Exemple : `Authenticate.php`, `VerifyCsrfToken.php`
- **`database/migrations/`** : Fichiers horodatés avec une description précise en **snake_case**.
  - Exemple : `2023_11_19_120000_create_users_table.php`

#### Fichiers
- **Classes et méthodes** : Utiliser le **PascalCase** pour les noms de classes et le **camelCase** pour les noms de méthodes.
  - Exemple : `class UserController`, `public function createOrder()`
- **Constantes** : Nommer en **UPPER_SNAKE_CASE**.
  - Exemple : `USER_STATUS_ACTIVE`

---

### Vue.js & TypeScript

#### Dossiers
- **`resources/js/components/`** : Contient des composants Vue. Les noms doivent être en **PascalCase**.
  - Exemple : `Navbar.vue`, `UserCard.vue`
- **`resources/js/pages/`** : Contient les pages Vue. Les noms doivent être en **PascalCase**.
  - Exemple : `Dashboard.vue`, `ProfilePage.vue`
- **`resources/js/store/`** : Contient les modules Vuex/Pinia. Les noms doivent être en **camelCase**.
  - Exemple : `userStore.ts`, `cartStore.ts`
- **`resources/js/types/`** : Contient les types TypeScript. Les noms doivent être en **PascalCase**.
  - Exemple : `UserType.ts`, `OrderType.ts`

#### Fichiers
- **Composants Vue** : Utiliser le **PascalCase** pour les noms des fichiers et exporter toujours un composant Vue par fichier.
- **Types** : Utiliser `I` pour préfixer les interfaces et les noms doivent être en **PascalCase**.
  - Exemple : `IUser`, `IOrder`

---

### Bases de données (MariaDB)

- **Noms des tables** : Utiliser le **snake_case** et préférer le **pluriel**.
  - Exemple : `users`, `order_details`
- **Colonnes** : Utiliser le **snake_case** et préférer les noms explicites.
  - Exemple : `first_name`, `created_at`
- **Clés étrangères** : Utiliser le format `{singulier_nom_table}_id`.
  - Exemple : `user_id`, `order_id`

---

## Branches GitHub

Nommer les branches en **anglais** selon le type de travail effectué :

1. **Branches principales** :
   - `main` : La branche principale contenant le code stable prêt pour la production.
   - `develop` : La branche contenant le code en cours de développement.

2. **Branches de fonctionnalités** :
   - Préfixer par `feature/` suivi d’un nom descriptif en **kebab-case**.
   - Exemple : `feature/user-authentication`, `feature/dashboard-ui`

---

## Langages à utiliser

Appliquer les règles suivantes :

1. **Commits et Merge Requests** :
   - Utiliser l'**anglais** pour les titres et les descriptions.
   - Exemple : 
     - Commit : `Added: account creation`
     - Merge Request : `Fixed: account page background display`
2. **Commentaires dans le code** :
   - Utiliser l'anglais pour les commentaires dans le code source.
   - Exemple : 
     ```php
     // allow users to send messages
     ```
3. **Documentation technique** :
   - Tous les fichiers README / guides d'installation doivent être rédigés en **francais**.
4. **Noms des variables et fonctions** :
   - Utiliser des noms descriptifs en **anglais**, quel que soit le langage.
   - Exemple : 
     ```typescript
     const calculateTotalPrice = (cartItems: Item[]): number => { ... }
     ```

---

## Bonnes Pratiques

1. **Cohérence** : Respecter toujours les conventions pour éviter la confusion.
2. **Lisibilité** : Les noms doivent être descriptifs, explicites et éviter les abréviations non standard.
3. **Documentation** : Ajouter des commentaires pour les sections complexes.
4. **Tests** : Organiser les tests avec des noms de fichiers reflétant la classe testée.
   - Exemple : `UserTest.php` pour tester `User`.
5. **Git Workflow** :
   - Préférer les branches descriptives en anglais.
     - Exemple : `feature/authentication-flow`, `bugfix/fix-order-details`

---
