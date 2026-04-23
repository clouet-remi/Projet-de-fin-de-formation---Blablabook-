# 📚 BlaBlaBook

> **Votre bibliothèque personnelle, réinventée.**
> Recherchez des millions de livres, organisez vos lectures et suivez votre progression — le tout dans une interface élégante, bilingue et accessible.

🚀 **Démo** — https://projet-de-fin-de-formation-blablabo.vercel.app/fr

> ⚠️ Le backend est hébergé sur Render (offre gratuite).
> Lors de la première requête, il peut mettre **30 à 60 secondes à démarrer** (cold start).

---

## Présentation

BlaBlaBook est une application web fullstack de gestion de bibliothèque personnelle. Elle permet aux utilisateurs de rechercher des livres via l'API Open Library (avec fallback Google Books), de les ajouter à leur bibliothèque, de suivre leur statut de lecture et de gérer leur profil.

L'application est disponible en **français et en anglais**, supporte le **mode nuit**, et est optimisée pour le **mobile et le desktop**.

---

## Fonctionnalités

### Livres

* 🔍 Recherche avec **autocomplétion** (debounce + navigation clavier)
* 📖 Fiche détaillée (description, livres similaires)
* 🎲 Suggestions aléatoires
* 🎯 Recommandations personnalisées
* 🔗 Partage de fiche livre

### Bibliothèque

* ➕ Ajout de livres
* 🏷️ Statuts : `À lire`, `En cours`, `Lu`
* 🗑️ Suppression avec confirmation
* 📊 Statistiques dynamiques

### Authentification

* 📝 Inscription avec validation
* 🔐 JWT (access + refresh token)
* 👤 Gestion du profil
* ❌ Suppression de compte

### Expérience utilisateur

* 🌍 FR / EN
* 🌙 Dark mode
* 🔔 Notifications toast
* ♿ Accessibilité (ARIA + clavier)
* 📱 Responsive
* 🤖 SEO (sitemap, OpenGraph)

---

## Stack technique

### Frontend

* Next.js (App Router)
* React
* Tailwind CSS
* shadcn/ui
* next-intl
* next-themes

### Backend

* Express
* TypeScript
* Prisma
* PostgreSQL
* Redis (Upstash)

### Infrastructure

| Service  | Provider |
| -------- | -------- |
| Frontend | Vercel   |
| Backend  | Render   |
| Database | Neon     |
| Cache    | Upstash  |

---

## Architecture

```plaintext
Frontend (Next.js - Vercel)
        ↓
API Proxy (/api)
        ↓
Backend (Express - Render)
        ↓
PostgreSQL (Neon) + Redis (Upstash)
```

---

## Installation locale (Docker)

### Prérequis

* Docker
* Docker Compose

### Configuration

Créer un `.env` :

```env
POSTGRES_USER=XXXX
POSTGRES_PASSWORD=XXXX
POSTGRES_DB=XXXX
POSTGRES_PORT=XXXX

PORT=XXXX
ALLOWED_ORIGINS="*"
DATABASE_URL=postgresql://username:password@db:5432/dbname?schema=public

FRONTEND_PORT=XXXX
```

---

### Lancement

```bash
bash init.sh
```

Ce script :

* démarre tous les services
* initialise la base de données
* lance le seeding

---

## Services locaux

| Service  | URL                   |
| -------- | --------------------- |
| Frontend | http://localhost:3000 |
| API      | http://localhost:3001 |
| Adminer  | http://localhost:8000 |

---

## Commandes utiles

```bash
docker compose logs -f
docker compose down
docker compose stop
bash init.sh
```

---

## Points techniques intéressants

* 🔁 Cache Redis sur les requêtes externes
* ⚡ Autocomplete optimisée (debounce + AbortController)
* 🔐 Auth sécurisée (JWT + cookies httpOnly)
* 🧠 Recommandations basées sur l’historique utilisateur
* 🌍 Internationalisation SSR (next-intl)

---

## Roadmap

* ⭐ Notation des livres
* ✍️ Avis utilisateur
* ⏳ Loading skeletons
* 🔍 SEO dynamique

---

## Équipe

* Frontend : Christopher
* Backend : Ophélie
* DevOps : Paul
* Product : Rémi

---

## Licence

Projet réalisé dans le cadre d'une formation.
# 📚 BlaBlaBook

> **Votre bibliothèque personnelle, réinventée.**
> Recherchez des millions de livres, organisez vos lectures et suivez votre progression — le tout dans une interface élégante, bilingue et accessible.

🚀 **Démo** — https://projet-de-fin-de-formation-blablabo.vercel.app/fr

> ⚠️ Le backend est hébergé sur Render (offre gratuite).
> Lors de la première requête, il peut mettre **30 à 60 secondes à démarrer** (cold start).

---

## Présentation

BlaBlaBook est une application web fullstack de gestion de bibliothèque personnelle. Elle permet aux utilisateurs de rechercher des livres via l'API Open Library (avec fallback Google Books), de les ajouter à leur bibliothèque, de suivre leur statut de lecture et de gérer leur profil.

L'application est disponible en **français et en anglais**, supporte le **mode nuit**, et est optimisée pour le **mobile et le desktop**.

---

## Fonctionnalités

### Livres

* 🔍 Recherche avec **autocomplétion** (debounce + navigation clavier)
* 📖 Fiche détaillée (description, livres similaires)
* 🎲 Suggestions aléatoires
* 🎯 Recommandations personnalisées
* 🔗 Partage de fiche livre

### Bibliothèque

* ➕ Ajout de livres
* 🏷️ Statuts : `À lire`, `En cours`, `Lu`
* 🗑️ Suppression avec confirmation
* 📊 Statistiques dynamiques

### Authentification

* 📝 Inscription avec validation
* 🔐 JWT (access + refresh token)
* 👤 Gestion du profil
* ❌ Suppression de compte

### Expérience utilisateur

* 🌍 FR / EN
* 🌙 Dark mode
* 🔔 Notifications toast
* ♿ Accessibilité (ARIA + clavier)
* 📱 Responsive
* 🤖 SEO (sitemap, OpenGraph)

---

## Stack technique

### Frontend

* Next.js (App Router)
* React
* Tailwind CSS
* shadcn/ui
* next-intl
* next-themes

### Backend

* Express
* TypeScript
* Prisma
* PostgreSQL
* Redis (Upstash)

### Infrastructure

| Service  | Provider |
| -------- | -------- |
| Frontend | Vercel   |
| Backend  | Render   |
| Database | Neon     |
| Cache    | Upstash  |

---

## Architecture

```plaintext
Frontend (Next.js - Vercel)
        ↓
API Proxy (/api)
        ↓
Backend (Express - Render)
        ↓
PostgreSQL (Neon) + Redis (Upstash)
```

---

## Installation locale (Docker)

### Prérequis

* Docker
* Docker Compose

### Configuration

Créer un `.env` :

```env
POSTGRES_USER=XXXX
POSTGRES_PASSWORD=XXXX
POSTGRES_DB=XXXX
POSTGRES_PORT=XXXX

PORT=XXXX
ALLOWED_ORIGINS="*"
DATABASE_URL=postgresql://username:password@db:5432/dbname?schema=public

FRONTEND_PORT=XXXX
```

---

### Lancement

```bash
bash init.sh
```

Ce script :

* démarre tous les services
* initialise la base de données
* lance le seeding

---

## Services locaux

| Service  | URL                   |
| -------- | --------------------- |
| Frontend | http://localhost:3000 |
| API      | http://localhost:3001 |
| Adminer  | http://localhost:8000 |

---

## Commandes utiles

```bash
docker compose logs -f
docker compose down
docker compose stop
bash init.sh
```

---

## Points techniques intéressants

* 🔁 Cache Redis sur les requêtes externes
* ⚡ Autocomplete optimisée (debounce + AbortController)
* 🔐 Auth sécurisée (JWT + cookies httpOnly)
* 🧠 Recommandations basées sur l’historique utilisateur
* 🌍 Internationalisation SSR (next-intl)

---

## Roadmap

* ⭐ Notation des livres
* ✍️ Avis utilisateur
* ⏳ Loading skeletons
* 🔍 SEO dynamique

---

## Équipe

* Frontend : Christopher
* Backend : Ophélie
* DevOps : Paul
* Product : Rémi

---

## Licence

Projet réalisé dans le cadre d'une formation.
