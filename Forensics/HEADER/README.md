# HEADER (Forensics)

**Points** : 500

## Description

> Mon image est corrompue, pouvez-vous la réparer pour moi s'il vous plaît ?
> 
---

## Étapes de Résolution

### Étape 1 : Utiliser `ghex` pour modifier l'en-tête de l'image

Ouvrez le fichier `flag.png` avec l'éditeur hexadécimal `ghex` pour inspecter et corriger son en-tête.

```bash
ghex flag.png
```

![Description de l'image](https://media.discordapp.net/attachments/1250870245246238853/1301911549178282076/image.png?ex=6726331d&is=6724e19d&hm=6944259a02d9bd8b70c4255bf99ccc3031e7d7670344efdd19e76940804bd806&=&format=webp&quality=lossless)

![Description de l'image](https://media.discordapp.net/attachments/1250870245246238853/1301911463656689684/image.png?ex=67263309&is=6724e189&hm=8e55b3603071ad096b57fd68c2fbbfd336ee137637d6aa9f1980c9060f30c6cd&=&format=webp&quality=lossless)

Dans le fichier `flag.png`, remplacez les octets `00 00 00 00 00 00 00 00` au début du fichier par l'en-tête PNG correct : `89 50 4E 47 0D 0A 1A 0A`

![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301911812593160232/image.png?ex=6726335c&is=6724e1dc&hm=a3e1a80e222c117019a4d5aa429c02fce759ef9397f90185c139fba649a5e9b5&)

Enregistrez les modifications dans ghex.

### Étape 2 : Ouvrir l'image réparée et récupérer le flag

Après avoir modifié l'en-tête, ouvrez l’image `flag.png`. Elle devrait maintenant s'afficher correctement et révéler le flag.

![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301911928809197638/image.png?ex=67263378&is=6724e1f8&hm=d2f2b2649a07cf805fe36cb4ecaa9c035b244d88c927343cb5e35c8222f67f98&)

## FLAG
`FLAG{BROKEN_HEADER?EASILY_FIXED}`
