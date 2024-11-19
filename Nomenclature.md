# Conventions de Nommage et Nomenclature - Chez les Copaings

Ce document décrit les règles et conventions de nommage adoptées pour garantir la lisibilité, la maintenabilité et la cohérence de ce projet.

---

## Table des matières
1. [Structure générale du projet](#structure-générale-du-projet)
2. [Conventions de nommage](#conventions-de-nommage)
    - [PHP (Laravel)](#php-laravel)
    - [Vue.js & TypeScript](#vuejs--typescript)
    - [Bases de données (MariaDB)](#bases-de-données-mariadb)
3. [Branches GitHub](#branches-github)
    - [Organisation des branches](#organisation-des-branches)
    - [Workflow GitHub](#workflow-github)
    - [Règles de nommage des branches](#règles-de-nommage-des-branches)
4. [Langages à utiliser](#langages-à-utiliser)
5. [Bonnes pratiques](#bonnes-pratiques)

---

## Structure générale du projet

Vue simplifiée de la structure du projet (backend)  
```
project-root/
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

### Schéma des branches
![Schéma des branches](https://github.com/user-attachments/assets/20b80a9b-c741-4911-ac3e-2f97dc54257f)  

---

### Organisation des branches
1. **Branches principales** :
   - **`main`** : Branche principale représentant l'environnement de **préproduction**.
   - **`staging`** : Branche dédiée aux tests et validations.

2. **Branches de travail** :
   - Préfixées selon le domaine :
     - **`front/`** : Modifications frontend. Exemple : `front/add-login-page`
     - **`back/`** : Modifications backend. Exemple : `back/user-authentication`

---

### Workflow GitHub

1. **Création de branche** :  
   Travailler sur une branche dédiée (préfixée par `front/` ou `back/`).

2. **Passage en staging** :  
   Fusionner la branche dans `staging`. Exécuter des tests pour valider les modifications.

3. **Validation et sauvegarde** :  
   Avant de fusionner dans `main`, effectuer une sauvegarde pour prévenir tout problème.

4. **Mise à jour de main** :  
   Fusionner `staging` dans `main` après validation complète.

---

### Règles de nommage des branches

- **Langue** : Les noms doivent être en **anglais**.
- **Préfixes** :
  - **`front/`** pour le frontend
  - **`back/`** pour le backend
- **Format** : Utiliser le **kebab-case** pour décrire la tâche.  
  Exemple : `front/add-login-page`, `back/fix-order-api`

---

### Règle de nommage des commits  

- Les **Types** :
  - **`feat`** pour les ajouts  
  - **`fix`** pour le problèmes réglés  
  - **`maj`** pour les mise à jour
- La **Nomenclature** :  
  Commit conventionel : `<type>[étendue optionnelle]: <description>`  
  Exemple : `feat(login): added login button`  
  Exemple : `fix(logout): fixed logout_button redirection`  
  Exemple : `maj(login): changed login_button background color`  

---

## Langages à utiliser

1. **Commits et Merge Requests** : Rédiger en **anglais**.
   - Exemple : `Fix: add user authentication`
2. **Commentaires** : Toujours en anglais, sauf exceptions liées à des règles métier spécifiques.
   - Exemple : `// Calculate the total price of items`
3. **Documentation technique** : Préférer le **français** pour les fichiers README et guides d’installation.
4. **Noms de variables** : Utiliser l’**anglais**.
   - Exemple : `const calculateTotalPrice = (cartItems: Item[]): number => { ... }`

---

## Bonnes pratiques

1. **Cohérence** : Respecter strictement les conventions établies.
2. **Lisibilité** : Utiliser des noms explicites, éviter les abréviations non standard.
3. **Documentation** : Ajouter des commentaires pour expliquer les sections complexes.
4. **Tests** : Noms de fichiers tests reflétant la classe ou la fonctionnalité testée.
   - Exemple : `UserTest.php`
5. **Git Workflow** :  
   - Utiliser des branches descriptives et bien nommées.
   - Exemple : `feature/add-payment-method`, `bugfix/fix-cart-bug`

---
