```markdown
# Checkpoint MongoDB CRUD

## Commandes MongoDB

### Étape 1 - Afficher toute la liste de contacts

```bash
mongo
use contact
db.contactlist.find({})
```

### Étape 2 - Afficher toutes les informations sur une seule personne par identifiant

```bash
# Remplacez "ID_de_la_personne" par l'_id réel de la personne concernée
var idPersonne = ObjectId("ID_de_la_personne");
db.contactlist.findOne({ _id: idPersonne })
```

### Étape 3 - Afficher tous les contacts âgés de >18 ans

```bash
db.contactlist.find({ âge: { $gt: 18 } })
```

### Étape 4 - Afficher tous les contacts avec un âge >18 et un nom contenant "ah"

```bash
db.contactlist.find({ $and: [{ âge: { $gt: 18 } }, { Nom: /ah/ }] })
```

### Étape 5 - Changer le prénom du contact de « Kefi Seif » en « Kefi Anis »

```bash
db.contactlist.updateOne({ Prénom: "Seif" }, { $set: { Prénom: "Anis" } })
```

### Étape 6 - Supprimer les contacts âgés de moins de <5 ans

```bash
db.contactlist.deleteMany({ âge: { $lt: 5 } })
```

### Étape 7 - Afficher toute la liste de contacts après les modifications

```bash
db.contactlist.find({})
```