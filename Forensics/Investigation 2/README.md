# Investigation 2 (Forensics)

**Points** : 500

## Description

> Une vulnérabilité a été détectée, et comme nous faisons partie de l'équipe de Forensics, nous avons besoin d'un rapport pour l'équipe. Nous avons obtenu une capture Wireshark, et nous devons maintenant répondre aux questions suivantes :
> 
> Quel est le nom d'utilisateur compromis ?
> 
> Quel est le domaine ?
> 
> Quel est le mot de passe en clair ?

**Format du drapeau** : `StarHack{username@DOMAIN_MotDePasseUtilisateurCompromis}`

---

## Étapes de Résolution

### Étape 1 : Télécharger et utiliser NetworkMiner pour analyser la capture

Rendez-vous sur le site [NetworkMiner](https://www.netresec.com/?page=NetworkMiner) pour télécharger cet outil d'analyse réseau.

Ouvrez NetworkMiner et chargez le fichier `investigation2.pcap`.

### Étape 2 : Rechercher les Identifiants dans NetworkMiner

Dans l'interface de NetworkMiner, accédez à l'onglet **Credentials**.

Vous trouverez les informations suivantes :

- **Nom d'utilisateur** : `lampard.frank`
  
- **Nom de domaine** : `YOGO.CORP`
  
- **Hash du mot de passe** : copiez ce hash pour l'étape suivante.

![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301930243812229181/image.png?ex=67264486&is=6724f306&hm=5967c1500f49d5fe0b4edb60a87721df1700d4bb02e9ccb8fd4ad833df354e98&)

### Étape 3 : Sauvegarder le Hash dans un Fichier

Copiez le hash du mot de passe depuis NetworkMiner.

Collez-le dans un fichier texte nommé `hash.txt`.

![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301929707905880196/image.png?ex=67264407&is=6724f287&hm=ea4b75602cb0e530b3d4bce7be7bfcea451572bf06733dfb0cc3652bd828699d&)

### Étape 4 : Craquer le Hash avec John the Ripper

```bash
/usr/sbin/john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301930580815908864/image.png?ex=672644d7&is=6724f357&hm=dff7c6e196434631afe702f651ab0a810fd6380799d2fbf774650f52023b02fc&)

### Étape 5 : Construire le Flag

En combinant le nom d'utilisateur, le domaine et le mot de passe en clair, le flag final est :

## FLAG
`StarHack{lampard.frank@YOGO.CORP_Number12rocks}`
