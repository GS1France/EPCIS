# Fiche de test A-15

## Enregistrement d’un événement incluant une référence à une transaction via requête HTTP POST

### Objectif

Vérification de la capacité de la solution à intégrer une référence à une transaction (exemple : un numéro de commande)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un événement constitué d’une section « BizTransactionList » est partagé avec l’éditeur

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant une section BizTransactionList conforme au standard EPCIS | L’événement incluant la référence à la transaction est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
