# SYNAGIF-digital-project
systeme de digitalisation de la mutuelle des agents des finances général

---

### Stack Technique
- **Backend & Web Admin :** PHP (Laravel) 
- **Application Mobile :** Flutter (Dart) - *Android & iOS*
- **Base de Données :** MySQL 
- **API :** RESTful API (Laravel Sanctum pour l'authentification)
- **Paiements :** Mobile Money (Wave, Orange Money, MTN MoMo, Moov)
- **Notifications Push :** Firebase Cloud Messaging (FCM)

---

### Architecture du Dépôt
- `/backend_web` : Application Laravel (Portail Web + API REST)
- `/mobile` : Code source Flutter
- `/docs` : Cahier des charges, scripts SQL, maquettes UI/UX

---

### Quick Start (Environnement de dev)

#### 1. Backend (Laravel & MySQL)
```bash
cd backend_web
composer install
cp .env.example .env
# Configurer les accès MySQL dans le .env
php artisan key:generate
php artisan migrate --seed
php artisan serve
