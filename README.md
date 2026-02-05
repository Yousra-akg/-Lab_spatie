---
marp: true
theme: default
paginate: true
backgroundColor: #F8F9F9
color: #1A5276
_class: lead
---

# LAB — Spatie Permission
## Role-Based Access Control avec Laravel

**Réalisée par : Yousra Akajou**  
**Encadrée par : M. Fouad Essarraj**  
**Date : Février 2026**

---

## Pourquoi ce lab ?

Ce laboratoire vise à explorer une solution professionnelle
de gestion d’autorisations dans une application Laravel.

Objectifs :

- Découvrir la gestion d’accès basée sur les rôles
- Comprendre la relation rôles ↔ permissions
- Implémenter une sécurité adaptable
- Contrôler les actions utilisateurs efficacement

---

## Présentation du package

Le module **Spatie Permission** étend Laravel pour permettre :

✔ Définition de profils utilisateurs  
✔ Attribution d’actions autorisées  
✔ Gestion dynamique des droits  
✔ Vérification automatique des accès  

👉 Il remplace les vérifications manuelles complexes
par une approche structurée et maintenable.

---

## Éléments fondamentaux

### Utilisateur
- Entité connectée à l’application
- Peut recevoir plusieurs rôles
- Peut avoir des permissions directes

### Rôle
- Ensemble de privilèges regroupés
- Simplifie la gestion globale
- Exemple : Manager, Admin, Visiteur

### Permission
- Autorisation précise
- Exemple : créer article, modifier profil
- Peut être assignée individuellement ou via un rôle

---

## Organisation interne

Lors de l’intégration, le package ajoute des tables dédiées :

- `roles`
- `permissions`
- `model_has_roles`
- `model_has_permissions`
- `role_has_permissions`

### Logique relationnelle

- Un utilisateur ⇄ plusieurs rôles  
- Un rôle ⇄ plusieurs permissions  
- Contrôle basé sur les données stockées  

Cela permet une adaptation sans modifier le code source.

---

## Mise en place technique

### Installation

```bash
composer require spatie/laravel-permission
```
### Publication des ressources
```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
```
### Migration de la base
```bash
php artisan migrate
```
- Résultat : création automatique des tables nécessaires.

## Impact sur l’interface

L’intégration influence aussi le comportement visuel :

- Affichage conditionnel des éléments

- Actions disponibles selon le profil

- Navigation adaptée aux droits

### Exemples

- Accès panneau admin limité

- Actions de modification filtrées

- Boutons invisibles sans autorisation

## Points forts de la solution

- Administration simplifiée

- Sécurité évolutive

- Adaptation sans refactorisation lourde

- Compatible architecture Laravel

- Approche professionnelle standardisée

- Gain de temps en développement

## Conclusion

L’utilisation de Spatie permet :

- Une gestion précise des accès

- Une application plus sécurisée

- Une maintenance facilitée

- Une meilleure expérience utilisateur
