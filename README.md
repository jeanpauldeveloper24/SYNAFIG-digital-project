# SYNAGIF-digital-project
Ce projet vise à concevoir et développer la proposition d'écosystème numérique pour le **Syndicat National des Agents des Finances Générales de Côte d'Ivoire (SYNAFIG)**. Cet écosystème comprend un portail web administratif/institutionnel et une application mobile pour les adhérents.

Ce projet s'inscrit dans le cadre de la campagne électorale pour l'élection du Secrétariat Général, proposant une transformation institutionnelle axée sur la transparence, l'inclusivité nationale et la modernisation des services syndicaux.

---

### 🛠️ Stack Technique
- **Backend & Web Admin :** PHP 8.x (Laravel) + Blade + HTML5 / CSS3 / JavaScript
- **Application Mobile :** Flutter (Dart) - *Android & iOS*
- **Base de Données :** MySQL (Moteur InnoDB)
- **API :** RESTful API (Laravel Sanctum pour l'authentification)
- **Paiements :** Mobile Money (Wave, Orange Money, MTN MoMo, Moov)

---

### 📦 Dépendances Principales du Projet

#### Application Mobile (Flutter)
- [http](https://pub.dev/packages/http) / [dio](https://pub.dev/packages/dio) : Gestion des requêtes HTTP/REST vers l'API Laravel.
- [flutter_bloc](https://pub.dev/packages/flutter_bloc) / [provider](https://pub.dev/packages/provider) : Gestion d'état (*State Management*) réactive.
- [shared_preferences](https://pub.dev/packages/shared_preferences) : Stockage local léger (tokens d'authentification, préférences).
- [sqflite](https://pub.dev/packages/sqflite) : Base de données locale SQLite pour le mode hors-ligne (ex: cache de la carte de membre).
- [qr_flutter](https://pub.dev/packages/qr_flutter) : Génération et affichage du QR Code pour la carte de membre numérique.
- [firebase_core](https://pub.dev/packages/firebase_core) & [firebase_messaging](https://pub.dev/packages/firebase_messaging) : Réception des notifications push.
- [url_launcher](https://pub.dev/packages/url_launcher) : Ouvertures de liens externes, appels directs et redirections Mobile Money.
- [cached_network_image](https://pub.dev/packages/cached_network_image) : Mise en cache des images (photos de profil, illustrations des actualités).
- [intl](https://pub.dev/packages/intl) : Formatage des dates et monnaies (FCFA).

#### Backend & Web (Laravel)
- [laravel/breeze](https://packagist.org/packages/laravel/breeze) : Auth kit léger (connexion, inscription, réinitialisation de mot de passe) pour le portail web.
- [laravel/sanctum](https://packagist.org/packages/laravel/sanctum) : Authentification sécurisée par Tokens pour l'API Flutter et les sessions Web.
- [guzzlehttp/guzzle](https://packagist.org/packages/guzzlehttp/guzzle) : Client HTTP backend pour consommer les API des agrégateurs Mobile Money.

---

### 📂 Architecture du Dépôt
- `/backend_web` : Application Laravel (Portail Web Blade + API REST)
- `/mobile` : Code source Flutter
- `/docs` : Cahier des charges technique, scripts SQL, diagrammes et documentation

---

### 🚀 Quick Start (Environnement de dev)

#### 1. Backend (Laravel & MySQL)
```bash
cd backend_web
composer install
cp .env.example .env
# Configurer les accès MySQL dans le fichier .env
php artisan key:generate
php artisan migrate --seed
npm install && npm run dev
php artisan serve
