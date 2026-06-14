# 📘 Fiche de Révision – Cloud, Docker, Node.js, Microservices

---

## 1. Node.js

**Définition simple :**
Node.js est un environnement qui permet d'exécuter du code JavaScript **côté serveur** (en dehors du navigateur).

**Rôle backend :**
- Permet de créer des serveurs web et des API.
- Gère plusieurs requêtes en même temps grâce à un fonctionnement **asynchrone** (non-bloquant).
- Utilise **npm** (Node Package Manager) pour installer des bibliothèques.

📌 **À retenir :** Node.js = "JavaScript qui tourne sur un serveur, pas dans le navigateur".

---

## 2. Microservices

**Définition :**
Architecture qui découpe une application en **plusieurs petits services indépendants**, chacun ayant une fonction précise.

**Caractéristiques principales :**
- Chaque service est **indépendant** (déployable séparément).
- Communication entre services via **API (HTTP/REST)** ou **messages (RabbitMQ)**.
- Chaque service peut avoir sa **propre base de données**.
- Plus facile à **maintenir, faire évoluer et tester**.
- Possibilité d'utiliser des **langages différents** pour chaque service.

📌 **Exemple :** Une app e-commerce avec :
- Service "Utilisateurs"
- Service "Produits"
- Service "Commandes"
- Service "Paiement"

---

## 3. Cloud Computing

**Définition simple :**
Le Cloud, c'est l'utilisation de **serveurs distants** (via Internet) pour stocker des données ou exécuter des applications, sans avoir besoin de matériel physique personnel.

**Cloud public :**
Infrastructure partagée, gérée par un fournisseur, accessible à tout le monde via Internet.

**Exemples de Cloud public :**
- **AWS** (Amazon Web Services)
- **Microsoft Azure**
- **Google Cloud Platform (GCP)**

📌 **À retenir :** Cloud = "Louer de la puissance informatique au lieu de l'acheter".

---

## 4. Avantages du Cloud

- 💰 **Coût réduit** : pas besoin d'acheter de serveurs physiques.
- 📈 **Scalabilité** : on augmente ou diminue les ressources selon les besoins.
- 🌍 **Accessibilité** : accessible depuis n'importe où via Internet.
- 🔒 **Sécurité & sauvegarde** gérées par le fournisseur.
- ⚡ **Rapidité de déploiement** des applications.
- 🔧 **Maintenance simplifiée** (le fournisseur gère les mises à jour matérielles).

---

## 5. Docker

**Concepts clés :**
- **Image** : modèle/plan figé contenant tout ce qu'il faut pour exécuter une application (code, dépendances, configuration).
- **Conteneur** : une **instance en cours d'exécution** d'une image. Léger, rapide, isolé.
- **Dockerfile** : fichier texte qui décrit comment construire une image.

📌 **Analogie :** Image = recette de cuisine, Conteneur = plat préparé à partir de cette recette.

**Commandes importantes :**

| Commande | Rôle |
|----------|------|
| `docker pull <image>` | Télécharge une image depuis Docker Hub |
| `docker images` | Liste toutes les images présentes localement |
| `docker rmi <image>` | Supprime une image |
| `docker run <image>` | Crée et démarre un conteneur à partir d'une image |
| `docker ps` | Liste les conteneurs en cours d'exécution |

---

## 6. Express.js

**Définition / rôle :**
Express.js est un **framework pour Node.js** qui simplifie la création de serveurs web et d'API (gestion des routes, requêtes, réponses).

**Installation :**
```bash
npm install express
```

**Exemple basique :**
```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000, () => {
  console.log('Serveur démarré sur le port 3000');
});
```

📌 **À retenir :** Express = "Boîte à outils qui rend Node.js plus facile pour créer des API".

---

## 7. RabbitMQ

**Définition :**
RabbitMQ est un **système de messagerie** (message broker) qui permet à différents services de communiquer entre eux de manière **asynchrone**, via des **files d'attente (queues)**.

**Fonctionnement simple :**

```
┌────────────┐        ┌─────────────┐        ┌──────────────┐
│  PRODUCER   │  --->  │    QUEUE     │  --->  │   CONSUMER    │
│ (envoie le  │        │ (stocke le   │        │ (récupère et  │
│  message)   │        │   message)   │        │  traite le    │
│             │        │              │        │   message)    │
└────────────┘        └─────────────┘        └──────────────┘
```

- Le **Producer** envoie un message dans la **Queue**.
- La **Queue** garde le message jusqu'à ce qu'il soit traité.
- Le **Consumer** récupère le message et l'exécute.

📌 **Exemple :** Un service "Commande" (Producer) envoie un message "nouvelle commande" → RabbitMQ (Queue) → un service "Email" (Consumer) lit le message et envoie une confirmation par email.

📌 **À retenir :** RabbitMQ = "facteur" qui transmet les messages entre services sans qu'ils aient besoin de se parler directement.

---

## ✅ Mini Résumé Final (5 lignes)

Node.js exécute du JavaScript côté serveur ; Express.js simplifie la création d'API avec Node.js. Les microservices découpent une application en services indépendants qui communiquent via API ou RabbitMQ. Le Cloud (AWS, Azure, GCP) permet d'héberger ces services à distance, sans matériel physique, avec scalabilité et coûts réduits. Docker permet d'empaqueter chaque microservice dans une image et de l'exécuter dans un conteneur isolé. RabbitMQ relie les microservices grâce au schéma Producer → Queue → Consumer pour une communication asynchrone.
