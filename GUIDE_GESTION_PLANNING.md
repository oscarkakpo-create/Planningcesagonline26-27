# CESAG ONLINE — Guide de Gestion du Planning (Promotion 2026–2027)

Ce dépôt héberge l'espace officiel de planning pour la **nouvelle promotion 2026–2027**.
Il est **100 % étanche** et indépendant de l'ancienne promotion 2025–2026 (aucun lien croisé, zéro risque de confusion pour les nouveaux étudiants).

---

## 1. Liens publics des programmes

Une fois le dépôt publié sur GitHub Pages, les étudiants accéderont directement à leurs espaces :

* **Portail d'accueil général :** `https://oscarkakpo-create.github.io/planning-cesag-2026-2027/`
* **MBA AG (Administration et Gestion) :** `https://oscarkakpo-create.github.io/planning-cesag-2026-2027/mba-ag/`
* **MBA GP (Gestion de Projets) :** `https://oscarkakpo-create.github.io/planning-cesag-2026-2027/mba-gp/`
* **MBA MSCH (Management du Capital Humain) :** `https://oscarkakpo-create.github.io/planning-cesag-2026-2027/mba-msch/`

> **Astuce WhatsApp :** Dans le groupe WhatsApp de chaque filière, donnez directement le lien direct du programme. L'étudiant arrive directement sur son planning sans chercher.

---

## 2. Règle d’or : Où se font les mises à jour ?

👉 **Uniquement dans le dossier `data/` !**  
Vous n'avez **jamais** besoin de modifier les fichiers HTML, le design ou le code.

* Pour mettre à jour **MBA AG** : modifier `data/mba-ag.json`
* Pour mettre à jour **MBA GP** : modifier `data/mba-gp.json`
* Pour mettre à jour **MBA MSCH** : modifier `data/mba-msch.json`

---

## 3. Structure d'une séance dans le fichier JSON

Chaque séance ajoutée dans `"sessions": [ ... ]` suit ce modèle simple :

```json
{
  "id": "s1",
  "date": "2026-11-20",
  "title": "Introduction au Management et Environnement des Affaires",
  "type": "Cours",
  "teacher": "Dr. Prénom NOM",
  "start": "18:00",
  "end": "20:00",
  "status": "pending",
  "moodle": "https://formations.cesagonline.com/course/view.php?id=XXXX",
  "room": "https://formations.cesagonline.com/mod/bigbluebuttonbn/view.php?id=YYYY"
}
```

### Signification des statuts (`status`) :
* `"pending"` : **Programmé** (Devient automatiquement "Confirmée" à 15h00 GMT le jour même).
* `"confirmed"` : **Confirmée** (Pastille verte).
* `"rescheduled"` : **Reportée** (Pastille orange, exclue du fichier ICS).
* `"cancelled"` : **Annulée** (Pastille rouge, barrée à l'affichage).

---

## 4. Comment publier les modifications sur le site ?

Ouvrez un terminal dans le dossier et tapez :

```bash
git add .
git commit -m "maj: planning semaine du [date]"
git push origin main
```

Le site est automatiquement mis à jour en moins de 60 secondes sur GitHub Pages.
