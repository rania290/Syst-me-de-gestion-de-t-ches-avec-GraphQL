# 📌 Système de gestion de tâches avec GraphQL

Ce projet est une API GraphQL simple pour gérer des tâches. Il utilise **Node.js, Express, Apollo Server** et **GraphQL** pour fournir des fonctionnalités essentielles comme l'ajout, la récupération, la mise à jour et la suppression de tâches.

---

## 🎯 Objectifs
✅ Comprendre comment configurer et utiliser GraphQL avec Node.js et Express.  
✅ Apprendre à créer un **schéma GraphQL** et des **résolveurs** pour gérer les requêtes et les mutations.  
✅ Créer une **API simple de gestion de tâches**.  

---

## 🛠 Outils utilisés
- 🚀 **Node.js** : Environnement d'exécution JavaScript.
- 🏗 **Express** : Framework web léger pour Node.js.
- 🔌 **Apollo Server** : Serveur GraphQL performant pour Node.js.
- 📡 **GraphQL** : Langage de requête pour les API.

---

## ⚙️ Installation

### 1️⃣ Cloner le dépôt
```bash
git clone <URL_DU_DEPOT>
cd tp-graphql
```

### 2️⃣ Installer les dépendances
```bash
npm install
```

### 3️⃣ Démarrer le serveur
```bash
node index.js
```
🖥 Le serveur démarre sur : `http://localhost:5000/graphql`

---

## 📂 Structure du projet
```
tp-graphql/
├── node_modules/          # Dépendances installées
├── taskSchema.gql         # Schéma GraphQL des tâches
├── taskSchema.js          # Implémentation du schéma GraphQL
├── taskResolver.js        # Résolveurs pour les requêtes et mutations
├── index.js               # Point d'entrée du serveur
├── package.json           # Fichier de configuration du projet
└── README.md              # Documentation du projet
```

---

## 🚀 Utilisation de l'API

### 🖥 Accéder à l'interface GraphQL
Ouvrir Apollo Sandbox :
```
http://localhost:5000/graphql
```

### 📌 Exemples de requêtes

#### 🔍 Récupérer toutes les tâches
```graphql
query {
  tasks {
    id
    title
    description
    completed
    duration
  }
}
```

#### ➕ Ajouter une nouvelle tâche
```graphql
mutation {
  addTask(title: "Nouvelle Tâche", description: "Description ici", completed: false, duration: 5) {
    id
    title
    description
    completed
    duration
  }
}
```

#### ✅ Marquer une tâche comme terminée
```graphql
mutation {
  completeTask(id: "1") {
    id
    title
    completed
  }
}
```

#### ✏️ Modifier la description d'une tâche
```graphql
mutation {
  changeDescription(id: "1", description: "Nouvelle description") {
    id
    title
    description
  }
}
```

#### 🗑 Supprimer une tâche
```graphql
mutation {
  deleteTask(id: "1") {
    id
    title
  }
}
```

---

## 📜 Schéma GraphQL

Le schéma est défini dans `taskSchema.gql` :

```graphql
type Task {
  id: ID!
  title: String!
  description: String!
  completed: Boolean!
  duration: Int
}

type Query {
  task(id: ID!): Task
  tasks: [Task]
}

type Mutation {
  addTask(title: String!, description: String!, completed: Boolean!, duration: Int): Task
  completeTask(id: ID!): Task
  changeDescription(id: ID!, description: String!): Task
  deleteTask(id: ID!): Task
}
```

---

## 🛠 Résolveurs
Les résolveurs sont implémentés dans `taskResolver.js`. Ils gèrent les requêtes et mutations pour interagir avec les données des tâches.

---

## 📜 Licence
Ce projet est sous licence **MIT**. Voir `LICENSE` pour plus de détails.

---

## 💡 Remarques
- Ce projet est un **exemple éducatif** pour apprendre GraphQL avec Node.js et Express.
- Vous pouvez l'améliorer en ajoutant **l'authentification, la pagination** ou une base de données.



