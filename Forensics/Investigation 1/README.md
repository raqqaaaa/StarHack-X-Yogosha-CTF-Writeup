# Investigation 1 (Forensics)

**Points** : 500

## Description

> Une vulnérabilité de service a été détectée, mais tout est maintenant en ordre. Étant donné que nous faisons partie de l'équipe de Forensics, nous devons fournir un rapport pour l'équipe. Nous avons obtenu une capture Wireshark, et nous devons maintenant répondre aux questions suivantes : Combien de ports ouverts ?
> 
> Quel est le CVE ? Exemple : CVE-2024-3377

**Format du drapeau** : `StarHack{NombreDePortsOuverts_CVE}`

---

## Étapes de Résolution

### Étape 1 : Analyser la capture réseau en ligne

Allez sur le site d’analyse de captures réseau [https://apackets.com/upload](https://apackets.com/upload).
Chargez le fichier `challenge.pcapng` en cliquant sur **Upload**.
Cliquez ensuite sur **View Report** pour accéder au rapport d'analyse.
   
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301921154390294568/image.png?ex=67263c0f&is=6724ea8f&hm=debc4b9ec406a714a65355610acb74ac094fef276df136c1a590e7068f060b5c&)

### Étape 2 : Identifier les Ports Ouverts

Dans le rapport, recherchez la section **Open Ports**.
Le rapport indique que **3 ports** sont ouverts : **21 (FTP), 22 (SSH), et 80 (HTTP)**.
Nous avons ainsi la première partie du flag : `3` (le nombre de ports ouverts).
   
![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301922121722761309/image.png?ex=67263cf6&is=6724eb76&hm=967c342638f0b5cd93aa03887407f20f9de289c98acb5899593f50d493d17311&)

### Étape 3 : Identifier la Version et la Vulnérabilité

Dans la section **FTP** du rapport, nous voyons le service suivant :
   
```bash
ProFTPD 1.3.5 Server (ProFTPD Default Installation) [172.17.0.2]
```

![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301922248394801172/image.png?ex=67263d14&is=6724eb94&hm=88d77b5dc7ffacb43da4e2dc39b76b75b4625cf78dd424473c2b54510d458d59&)

En recherchant en ligne, on trouve que la version ProFTPD 1.3.5 est vulnérable à CVE-2015-3306, une vulnérabilité permettant l'accès non autorisé à certains fichiers via les commandes SITE CPFR et SITE CPTO.

![Description de l'image](https://cdn.discordapp.com/attachments/1250870245246238853/1301922717796270112/image.png?ex=67263d84&is=6724ec04&hm=7b6652d58d22c4e161f1413b973bbdd36a9ffee984a97c9792cea95734ecbb4b&)

## FLAG
`StarHack{3_CVE-2015-3306}`
