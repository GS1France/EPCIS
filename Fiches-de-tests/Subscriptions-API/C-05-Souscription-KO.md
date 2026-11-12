# Fiche de test C-05

## Rejet d’une souscription non conforme

### Objectif

Validation de la capacité de la solution à rejeter une demande de souscription non conforme

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Une requête nommée est enregistrée dans la solution (cf. test E.01)

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’une souscription sur une requête nommée avec des paramètres invalides ou absents.<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/queries/myQuery/subscriptions<br><br>{<br><br>"dest": "https://my-system.example.com/epcis/callback",<br><br>"signatureToken": "13df38d8275b13f05704629e5f1cf3d45d6132d5",<br><br>"reportIfEmpty": true,<br><br>"initialRecordTime": "2026-10-15T00:00:00.000Z"<br><br>} | Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs).<br><br>{<br><br>"type": "epcisException:QueryParameterException",<br><br>"title": "Missing parameter",<br><br>"status": "400",<br><br>"detail": "schedule parameters are missing"<br><br>} |
| **2** | Envoi d’une souscription sur une requête nommée inexistante<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/queries/myQueryUnknown/subscriptions<br><br>{<br><br>"dest": "https://my-system.example.com/epcis/callback",<br><br>"signatureToken": "13df38d8275b13f05704629e5f1cf3d45d6132d5",<br><br>"schedule" : {<br><br>"minute": "60"<br><br>},<br><br>"reportIfEmpty": true,<br><br>"initialRecordTime": "2026-10-15T00:00:00.000Z"<br><br>} | Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs).<br><br>Exemple :<br><br>{ "type":"epcisException:QueryParameterException",<br><br>"title": "Query not found",<br><br>"status": 400,<br><br>"detail": "no query found with name : myQueryUnknown"<br><br>} |
| **3** | Appel REST de la souscription rejetée<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/queries/myQueryUnknown/subscriptions | Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs).<br><br>Exemple :<br><br>{<br><br>"type": "epcisException:NoSuchResourceException",<br><br>"title": "API not Found",<br><br>"status": "404",<br><br>"detail": "API Not Found : . /myQueryUnknown/subscriptions"<br><br>} |
