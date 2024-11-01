# Cache-cache (Forensics)

**Points** : 100

## Description

> J'ai appris beaucoup de trucs, j'ai séparé mon message secret et je l'ai caché dans l'image en 2 parties, pouvez-vous regrouper les 2 parties ?

**Format du drapeau** : `StarHack{premièrePartie_deuxièmePartie}`

---

## Étapes de Résolution

### Étape 1 :

Utilisez la commande `strings` pour analyser le fichier `peace.jpeg` et afficher les premières lignes.

```bash
strings peace.jpeg | head
```
Première partie du flag `exif_and`

### Étape 2 :

Utilisez la commande `strings` pour analyser le fichier `peace.jpeg` et afficher les dernieres lignes.

```bash
strings peace.jpeg | tail
```
Deuxième partie du flag `strings_easy`

## Flag 
`StarHack{exif_and_strings_easy}`
