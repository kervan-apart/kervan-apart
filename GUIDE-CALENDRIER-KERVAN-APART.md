# 📅 Guide de mise à jour du calendrier - Kervan Apart

## 🎯 Quand utiliser ce guide
- Pour ajouter une nouvelle réservation
- Pour supprimer une réservation annulée
- Pour modifier des dates existantes

**Fréquence** : 1-2 fois par semaine
**Temps nécessaire** : 2 minutes

---

## 📝 PROCÉDURE COMPLÈTE

### ÉTAPE 1 : Ouvrir le fichier

1. Aller sur GitHub : https://github.com/kervan-apart/kervan-apart
2. Cliquer sur **index-FR.html**
3. Cliquer sur l'icône **crayon ✏️** (Edit this file)

---

### ÉTAPE 2 : Trouver le tableau des dates

**Appuyer sur Ctrl+F** (Windows) ou **Cmd+F** (Mac)

**Chercher** : `const bookedDates`

**Vous trouvez un tableau qui ressemble à ça** :

```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },
    { start: '2026-04-10', end: '2026-04-17' },
    { start: '2026-05-20', end: '2026-06-05' },
    { start: '2026-07-01', end: '2026-07-15' }
];
```

---

### ÉTAPE 3 : Modifier les dates

#### ➕ AJOUTER une réservation

**Exemple** : Ajouter une réservation du 10 au 17 mai 2026

**AVANT** :
```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },
    { start: '2026-04-10', end: '2026-04-17' }
];
```

**APRÈS** :
```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },
    { start: '2026-04-10', end: '2026-04-17' },
    { start: '2026-05-10', end: '2026-05-17' }  // ← NOUVELLE ligne
];
```

**⚠️ ATTENTION** :
- Virgule `,` à la fin de chaque ligne SAUF la dernière
- Format dates : `AAAA-MM-JJ` (2026-05-10, PAS 10/05/2026)

---

#### ➖ SUPPRIMER une réservation

**Supprimer toute la ligne**, y compris la virgule.

**AVANT** :
```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },
    { start: '2026-04-10', end: '2026-04-17' },  // ← À supprimer
    { start: '2026-05-10', end: '2026-05-17' }
];
```

**APRÈS** :
```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },
    { start: '2026-05-10', end: '2026-05-17' }
];
```

---

#### ✏️ MODIFIER une réservation

**Changer simplement les dates** sur la ligne existante.

**Exemple** : Prolonger du 17 au 20 mai

**AVANT** :
```javascript
{ start: '2026-05-10', end: '2026-05-17' }
```

**APRÈS** :
```javascript
{ start: '2026-05-10', end: '2026-05-20' }
```

---

### ÉTAPE 4 : Sauvegarder

1. **En haut à droite**, cliquer sur **"Commit changes..."** (bouton vert)
2. **Une fenêtre s'ouvre** :
   - Titre : `Mise à jour réservations mai 2026` (par exemple)
   - Description : Laisser vide ou ajouter des détails
3. **Cliquer** sur le bouton vert **"Commit changes"**

---

### ÉTAPE 5 : Vérifier

1. **Attendre 2-3 minutes** (GitHub Pages déploie le site)
2. **Aller sur le site** : https://kervan-apart.github.io/kervan-apart/index-FR.html
3. **Recharger avec cache vidé** :
   - Windows : **Ctrl + Shift + R**
   - Mac : **Cmd + Shift + R**
4. **Vérifier** que les nouvelles dates apparaissent en **rouge** dans le calendrier

---

## ⚠️ RÈGLES IMPORTANTES

### ✅ FORMAT DES DATES

**BON** : `2026-05-10` (AAAA-MM-JJ)

**MAUVAIS** :
- ❌ `10/05/2026`
- ❌ `10-05-2026`
- ❌ `2026/05/10`
- ❌ `10 mai 2026`

---

### ✅ VIRGULES

```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },  // ← Virgule ICI
    { start: '2026-04-10', end: '2026-04-17' },  // ← Virgule ICI
    { start: '2026-05-10', end: '2026-05-17' }   // ← PAS de virgule (dernière ligne)
];
```

**Règle** : Virgule après chaque ligne SAUF la dernière avant `]`

---

### ✅ ORDRE CHRONOLOGIQUE

**Recommandé** : Trier les dates du plus ancien au plus récent

**Exemple** :
```javascript
const bookedDates = [
    { start: '2026-03-15', end: '2026-03-22' },  // Mars
    { start: '2026-04-10', end: '2026-04-17' },  // Avril
    { start: '2026-05-10', end: '2026-05-17' },  // Mai
    { start: '2026-07-01', end: '2026-07-15' }   // Juillet
];
```

**Mais ce n'est pas obligatoire** - le code fonctionne même dans le désordre.

---

## 🔧 DÉPANNAGE

### ❌ Le calendrier ne s'affiche plus

**Cause probable** : Erreur de syntaxe (virgule manquante/en trop, guillemets cassés)

**Solution** :
1. GitHub → kervan-apart → Commits
2. Trouver votre dernier commit
3. Cliquer sur les 3 points `...` → "Revert this commit"
4. Recommencer proprement

---

### ❌ Les dates ne s'affichent pas en rouge

**Vérifier** :
1. Format `AAAA-MM-JJ` correct ?
2. Attendu 2-3 minutes après commit ?
3. Rechargé avec Ctrl+Shift+R ?
4. Regarder la console (F12) pour erreurs JavaScript

---

### ❌ Le site ne se charge plus

**Solution d'urgence** :
1. Commits → Trouver un commit ancien qui fonctionnait
2. "Revert" tous les commits récents jusqu'à retrouver la version stable

---

## 📋 CHECKLIST RAPIDE

Avant de commit, vérifier :

- [ ] Format dates : `AAAA-MM-JJ`
- [ ] Virgules correctes (après chaque ligne sauf dernière)
- [ ] Guillemets corrects : `'2026-05-10'`
- [ ] Accolades correctes : `{ start: ..., end: ... }`
- [ ] Crochets fermés : `];` à la fin

---

## 🎯 VERSIONS MULTILINGUES

**Après avoir modifié index-FR.html**, répéter pour les 6 autres versions :

1. index-EN.html (Anglais)
2. index-TR.html (Turc)
3. index-RU.html (Russe)
4. index-DE.html (Allemand)
5. index-ZH.html (Chinois)
6. index-AR.html (Arabe)

**Procédure identique** : Chercher `const bookedDates`, modifier, commit.

**Astuce** : Faire toutes les versions d'un coup (7 commits rapides).

---

## 💡 EXEMPLES CONCRETS

### Exemple 1 : Ajouter 3 nouvelles réservations

```javascript
const bookedDates = [
    // Réservations existantes
    { start: '2026-03-15', end: '2026-03-22' },
    { start: '2026-04-10', end: '2026-04-17' },
    
    // Nouvelles réservations
    { start: '2026-05-10', end: '2026-05-17' },
    { start: '2026-06-01', end: '2026-06-08' },
    { start: '2026-07-15', end: '2026-07-29' }
];
```

---

### Exemple 2 : Tableau vide (aucune réservation)

```javascript
const bookedDates = [];
```

**Pas de virgule, juste les crochets vides.**

---

### Exemple 3 : Une seule réservation

```javascript
const bookedDates = [
    { start: '2026-08-01', end: '2026-08-15' }
];
```

**Pas de virgule après l'unique ligne.**

---

## 📞 AIDE

**En cas de problème** :
- Vérifier la syntaxe (virgules, guillemets, crochets)
- Utiliser "Revert this commit" pour annuler
- Consulter ce guide étape par étape

**Temps moyen par mise à jour** : 2 minutes ⏱️

**Fréquence** : 1-2 fois par semaine 📅

---

*Dernière mise à jour : Avril 2026*
*Site : https://kervan-apart.github.io/kervan-apart/*
*GitHub : https://github.com/kervan-apart/kervan-apart*
