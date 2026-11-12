# Fiche de test A-08

## Rejet de l’enregistrement d’un événement de type « Transaction Event » via requête HTTP POST

### Objectif

Validation de la capacité de la solution à rejeter l’enregistrement d’événement de type « Transaction Event » lorsque celui-ci n’est pas conforme au standard EPCIS via l’interface de capture (HTTP POST)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un modèle d’événement de type « Transaction Event » est partagé avec l’éditeur. Ce document présente des non-conformités au standard EPCIS

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant un événement « Transaction Event » non conforme.<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/capture avec un Transaction Event omettant l’attribut epcList et quantityList alors que la valeur de l’attribut action est ADD | Le document EPCIS est rejeté par la solution et aucun événement n’est enregistré.<br><br>Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs). |
| **2** | Envoi d’un document EPCIS incluant un événement « Transaction Event » non conforme.<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/capture avec un Transaction Event omettant l’attribut eventTime. | Le document EPCIS est rejeté par la solution et aucun événement n’est enregistré.<br><br>Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs). |
