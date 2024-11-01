# Cache-cache (Forensics)

**Points** : 100

## Description

> J'ai appris beaucoup de trucs, j'ai séparé mon message secret et je l'ai caché dans l'image en 2 parties, pouvez-vous regrouper les 2 parties ?

**Format du drapeau** : `StarHack{premièrePartie_deuxièmePartie}`

---

## Étapes de Résolution

### Étape 1 : Extraire des chaînes de caractères dans l'image

Utilisez la commande `strings` pour analyser le fichier `peace.jpeg` et afficher les premières lignes.

```bash
strings peace.jpeg | head
```
### Étape 2 : Extraire des chaînes de caractères dans l'image

Utilisez la commande `strings` pour analyser le fichier `peace.jpeg` et afficher les dernieres lignes.

```bash
strings peace.jpeg | tail
```

## Flag 
`StarHack{exif_and_strings_easy}`
