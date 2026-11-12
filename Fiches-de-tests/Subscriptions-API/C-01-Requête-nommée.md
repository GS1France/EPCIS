# Fiche de test C-01

## Création et consultation d’une requête nommée

### Objectif

Validation de la capacité de la solution à créer une requête nommée sur les événements EPCIS et à la restituer à un client

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Des événements EPCIS au format JSON constitué d’attributs de données conformes au standard EPCIS sont enregistrés dans la solution

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’une requête nommée incluant un nom de requête et des filtres de sélection des événements<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/queries<br><br>{<br><br>"name": "myQuery",<br><br>"query": {<br><br>"eventType": ["ObjectEvent"],<br><br>"EQ_bizStep": ["shipping"]<br><br>}<br><br>} | Le serveur retourne un code de statut de réponse de succès HTTP. |
| **2** | Appel REST de l’endpoint Queries<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/queries | La liste des requêtes nommées est renvoyée par la solution. La requête créée à l’étape 1 figure dans la liste. |
