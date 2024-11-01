# Fichier ZIP protégé par mot de passe (Forensics)

**Points** : 500

## Description

> J'ai oublié le mot de passe de mon fichier ZIP, pouvez-vous m'aider à récupérer mon fichier précieux, s'il vous plaît ?

---

## Étapes de Résolution

### Étape 1 : Extraire le hash du fichier ZIP

Utilisez `zip2john` pour extraire le hash du fichier `flag.zip`. Ce hash est nécessaire pour pouvoir attaquer le mot de passe avec **John the Ripper**.

```bash
/usr/sbin/zip2john flag.zip > hash.txt
```
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301917473544732723/image.png?ex=672638a2&is=6724e722&hm=e995df8c94126192a5685da74144a54bc671461b2bcec75a1fe899f6c254c60b&)

### Étape 2 : Craquer le mot de passe avec John the Ripper

```bash
/usr/sbin/john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301918405963677776/image.png?ex=67263980&is=6724e800&hm=86e6ba4f3ed8f3cf13142eaf903787252c61c7f4dd5155efb174d54952b6080e&)

### Étape 3 : Afficher le mot de passe trouvé

Une fois que le mot de passe est trouvé, vous pouvez l'afficher avec la commande suivante :

```bash
/usr/sbin/john hash.txt --show
```
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301918573937033216/image.png?ex=672639a8&is=6724e828&hm=64316933f21e1d862d7891c0786c25cd33b70e0aa68c4664f02043382bac14f8&)

### Étape 4 : Utiliser le mot de passe pour ouvrir le fichier ZIP

Le mot de passe trouvé est friendster. Utilisez-le pour déverrouiller le fichier flag.zip et accéder au contenu.

Ouvrez le fichier ZIP avec le mot de passe friendster.
Dans le fichier extrait `flag.txt`, vous trouverez le `flag`.
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301918783291523174/image.png?ex=672639da&is=6724e85a&hm=c25a6657f7e5a28d684e1e35614607b69f15f343bfd7971bbe81acd2e1a9f4c5&)


## Flag
`flag{we_can_bruteforce_anything_to_get_what_we_want}`
