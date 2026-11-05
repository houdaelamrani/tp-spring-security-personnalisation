# 🎓 TP : Personnalisation de l'Authentification Spring Security & Thymeleaf

Projet réalisé dans le cadre du module Sécurité Informatique / Architectures Logicielles ).

---

## 🎯 Objectifs du TP

- Personnaliser le formulaire d'authentification par défaut de Spring Security avec **Thymeleaf**.
- Maîtriser le cycle de vie du flux d'authentification (`/login`, `/authenticate`, `/logout`).
- Implémenter une **redirection dynamique conditionnelle selon les rôles** via un `AuthenticationSuccessHandler`.
- Gérer les erreurs d'authentification et les messages de déconnexion.
- Mettre en place une **page d'accès refusé personnalisée (Erreur 403)**.
- Sécuriser les mots de passe avec **BCrypt**.
- Corriger le mécanisme de déconnexion pour respecter la protection **CSRF** (requête POST).

---

## 🏗️ Structure du Projet

```text
src/main
 ├─ java/ma/fstg/security
 │   ├─ config/
 │   │   ├─ SecurityConfig.java            # Configuration de la SecurityFilterChain
 │   │   └─ CustomAuthSuccessHandler.java  # Redirection dynamique par rôle
 │   ├─ web/
 │   │   └─ AuthController.java            # Contrôleur des vues Thymeleaf
 │   └─ FstgSecurityApplication.java       # Point d'entrée Spring Boot
 └─ resources/
     ├─ application.properties
     └─ templates/
         ├─ login.html                     # Page de connexion personnalisée
         ├─ admin-dashboard.html           # Espace Administrateur (ROLE_ADMIN)
         ├─ user-dashboard.html            # Espace Étudiant (ROLE_USER, ROLE_ADMIN)
         ├─ access-denied.html             # Page 403 personnalisée
         └─ home.html                      # Page d'accueil générale
```

---

## 👥 Comptes de Test

| Identifiant | Mot de passe | Rôle | Espace assigné |
| :--- | :--- | :--- | :--- |
| `admin_fstg` | `admin2026` | `ADMIN` | `/admin/dashboard` |
| `etudiant_fstg` | `fstg2026` | `USER` | `/user/dashboard` |

---

## ⚙️ Prérequis & Lancement

- **Java 17+** (ou Java 21)
- **Maven 3.8+**

```bash
# Compiler et lancer l'application
mvn spring-boot:run
```

L'application est accessible à l'adresse : **[http://localhost:8080/login](http://localhost:8080/login)**
