# 🚀 Blablabook — Fullstack App (Docker + Next.js + Express + Prisma)

Application fullstack développée avec une architecture conteneurisée via Docker Compose.

👉 **Démo en ligne** :
https://projet-de-fin-de-formation-blablabo.vercel.app/fr

> ⚠️ Le backend est hébergé sur Render (free tier).
> Lors de la première requête, il peut mettre **30 à 60 secondes à se réveiller**. Merci de patienter si l’API ne répond pas immédiatement.

---

## 🧱 Stack technique

* **Frontend** : Next.js
* **Backend** : Express + Prisma
* **Base de données** : PostgreSQL
* **Admin DB** : Adminer
* **Conteneurisation** : Docker & Docker Compose

---

## ⚙️ Prérequis

* Docker
* Docker Compose
* Un fichier `.env` à la racine du projet

---

## 🔐 Configuration (.env)

Créer un fichier `.env` basé sur ce modèle :

```env
# ─── Base de données ───────────────────────────────
POSTGRES_USER=XXXXXX
POSTGRES_PASSWORD=XXXXXX
POSTGRES_DB=XXXXXX
POSTGRES_PORT=XXXX

# ─── API (Express + Prisma) ────────────────────────
PORT=XXXX
ALLOWED_ORIGINS="*"
DATABASE_URL=postgresql://username:password@db:5432/dbname?schema=public

# ─── Frontend (Next.js) ────────────────────────────
FRONTEND_PORT=XXXX
```

> ⚠️ Ne pas modifier `@db:5432` dans `DATABASE_URL`
> `db` correspond au service PostgreSQL dans Docker.

---

## ▶️ Lancement du projet

Depuis la racine du projet :

```bash
bash init.sh
```

### Ce script automatise :

1. L'arrêt et la suppression des conteneurs existants
2. Le démarrage des services (`db`, `adminer`, `api`, `frontend`)
3. L'attente que l’API soit prête
4. Le reset de la base de données + seeding

---

## 🌐 Services disponibles en local

| Service  | URL                   | Description          |
| -------- | --------------------- | -------------------- |
| Frontend | http://localhost:3000 | Application Next.js  |
| API      | http://localhost:3001 | API Express          |
| Adminer  | http://localhost:8000 | Interface PostgreSQL |

---

## ✅ Vérification

1. Accéder à Adminer : http://localhost:8000
2. Se connecter avec les identifiants du `.env`
3. Vérifier que les tables sont présentes et remplies

---

## 📜 Logs

```bash
docker compose logs -f          # Tous les services
docker compose logs -f api      # Backend uniquement
docker compose logs -f frontend # Frontend uniquement
```

---

## 🧰 Commandes utiles

```bash
# Stopper les conteneurs (sans supprimer les volumes)
docker compose stop

# Stopper et supprimer les conteneurs
docker compose down

# Redémarrage complet (avec reset BDD + seed)
bash init.sh
```

---

## 💡 Notes

* Le projet est conçu pour un environnement de développement local via Docker
* Le backend en production utilise Render (cold start possible)
* Le frontend est déployé sur Vercel

---
