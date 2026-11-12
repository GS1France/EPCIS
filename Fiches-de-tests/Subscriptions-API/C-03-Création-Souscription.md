# Fiche de test C-03

## Création d’une souscription à une requête nommée

### Objectif

Validation de la capacité de la solution à créer une souscription à une requête nommée par callback HTTP afin de transmettre de façon automatisée les événements à un client souscripteur.

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Des événements EPCIS au format JSON constitué d’attributs de données conformes au standard EPCIS sont enregistrés dans la solution
- Une requête nommée est enregistrée dans la solution (cf. test C.01)

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’une souscription sur une requête nommée<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/queries/myQuery/subscriptions<br><br>{<br><br>"dest": "https://my-system.example.com/epcis/callback",<br><br>"signatureToken": "13df38d8275b13f05704629e5f1cf3d45d6132d5",<br><br>"schedule" : {<br><br>"minute": "60"<br><br>},<br><br>"reportIfEmpty": true,<br><br>"initialRecordTime": "2026-10-15T00:00:00.000Z"<br><br>} | La souscription est active sur la requête nommée suivant les paramètres indiquées.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
| **2** | Appel REST de la souscription créée<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/queries/myQuery/subscriptions | La souscription créée apparaît comme souscriptions active et les paramètres de la souscription sont consultables. |
| **3** | Vérification du bon fonctionnement de la souscription. | Suivant les paramètres de la souscription, le callback reçoit une requête HTTP contenant un document EPCIS Query correspondant aux filtres de la requête nommée. |
