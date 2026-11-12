# Fiche de test A-12

## Rejet de l’enregistrement d’une série d’événements en cas de non-conformité via requête HTTP POST

### Objectif

Validation de la capacité de la solution à rejeter l’enregistrement de données non conformes au standard EPCIS via l’interface de capture (HTTP POST)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant plusieurs événements est partagé avec l’éditeur. Parmi ces événements, un événement présente des non-conformités au standard EPCIS
- La solution traite la capture selon le mode rollback

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant plusieurs événements conformes et 1 événement non conforme au standard EPCIS | Le document EPCIS est rejeté par la solution et aucun événement n’est enregistré.<br><br>Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs). |
