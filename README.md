# Le Bidul - Site Web

Site web de l'agenda culturel Le Bidul, construit avec Django.

## Architecture du projet

```
lebidul/
├── apps/
│   ├── __init__.py
│   ├── accounts/
│   │   ├── __init__.py
│   │   ├── models.py        # User personnalisé
│   │   ├── views.py         # inscription, connexion, profil
│   │   ├── urls.py          # /comptes/...
│   │   ├── forms.py         # formulaires inscription/connexion
│   │   └── admin.py         # config de l'admin pour les users
│   ├── agenda/
│   │   ├── __init__.py
│   │   ├── models.py        # Evenement, Lieu, Categorie, Auteur
│   │   ├── views.py         # liste, détail, créer, modifier, supprimer
│   │   ├── urls.py          # /agenda/...
│   │   ├── forms.py         # formulaire création/modification événement
│   │   └── admin.py         # config de l'admin pour les événements
│   └── pages/
│       ├── __init__.py
│       ├── models.py        # (vide au début, peut servir plus tard)
│       ├── views.py         # accueil, à propos
│       ├── urls.py          # /
│       └── admin.py
├── lebidul/
│   ├── __init__.py
│   ├── settings.py          # tous les réglages du projet
│   ├── urls.py              # routeur principal
│   └── wsgi.py              # point d'entrée production
├── templates/
│   ├── base.html            # squelette commun (navbar, footer)
│   ├── accounts/
│   │   ├── login.html
│   │   ├── inscription.html
│   │   └── profil.html
│   ├── agenda/
│   │   ├── liste.html
│   │   ├── detail.html
│   │   ├── form.html        # utilisé pour créer ET modifier
│   │   └── confirmer_suppression.html
│   └── pages/
│       ├── accueil.html
│       └── apropos.html
├── static/
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── main.js
├── media/                   # fichiers uploadés (créé automatiquement)
├── .env                     # variables secrètes (jamais sur Git !)
├── .gitignore
├── manage.py
└── requirements.txt
```

## Groupes et permissions

| Groupe | Droits |
|---|---|
| `Redacteur` | Créer et modifier des événements |
| `Admin` (superuser) | Accès total |
