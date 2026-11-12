# Fiche de test A-16

## Enregistrement d’un événement incluant un transfert de propriété / possession d’un produit via requête HTTP POST

### Objectif

Vérification de la capacité de la solution à intégrer un transfert de propriété / possession d’un produit (exemple : identification de l’entreprise / site d’origine et de destination d’un produit)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un événement constitué d’une section « sourceList » et d’une section « destinationList » est partagé avec l’éditeur

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant les sections sourceList et destinationList conformes au standard EPCIS | L’événement incluant les données relatives au transfert de propriété / possession est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
