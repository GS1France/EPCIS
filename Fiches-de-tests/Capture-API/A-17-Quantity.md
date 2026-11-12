# Fiche de test A-17

## Enregistrement d’un événement incluant une quantité associée à un produit via requête HTTP POST

### Objectif

Vérification de la capacité de la solution à intégrer une quantité associée à un produit (exemple : un nombre d’unités de GTIN)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un événement constitué d’une section « quantityList » est partagé avec l’éditeur

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant une section quantityList conforme au standard EPCIS | L’événement incluant les données relatives à la quantité est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
