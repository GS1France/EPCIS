# Fiche de test A-11

## Enregistrement d’une série d’événements via requête HTTP POST

### Objectif

Validation de la capacité de la solution enregistrer un document EPCIS constitué d’une série d’événements conformes au standard EPCIS via l’interface de capture (HTTP POST)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant plusieurs événements constitués d’attributs de données conformes au standard EPCIS est partagé avec l’éditeur

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant plusieurs événements conformes au standard EPCIS | L’ensemble des événements est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
