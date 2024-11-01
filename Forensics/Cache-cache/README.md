# Cache-cache (Forensics)

**Points** : 500

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
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301909524260847636/image.png?ex=6726313a&is=6724dfba&hm=3b30bb89dec9da7dfda6ac543fe6f209cb4ab0ef1d2ea7d2cd2003e850704313&)

Première partie du flag `exif_and`

### Étape 2 :

Utilisez la commande `strings` pour analyser le fichier `peace.jpeg` et afficher les dernieres lignes.

```bash
strings peace.jpeg | tail
```
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301909879103164436/image.png?ex=6726318f&is=6724e00f&hm=0210c2a697167a0db27f612e21451f39d4d0e6b3b4441b7492c227810caa3b33&)

Deuxième partie du flag `strings_easy`

## Flag 
`StarHack{exif_and_strings_easy}`
