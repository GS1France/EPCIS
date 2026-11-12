# Fiche de test C-04

## Suppression d’une souscription

### Objectif

Validation de la capacité de la solution à supprimer une souscription afin de mettre fin à la transmission des événements associés

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Des événements EPCIS au format JSON constitué d’attributs de données conformes au standard EPCIS sont enregistrés dans la solution
- Une souscription à une requête nommée est enregistrée dans la solution (cf. test E-03) et son identifiant de souscription est connu

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Suppression de la souscription<br><br>Exemple :<br><br>DELETE https://my-system.example.com/epcis/queries/myQuery/subscriptionID | La solution confirme la suppression de la souscription par un code de statut de réponse de succès HTTP.<br><br>Les événements associés à la requête nommée pour laquelle la souscription s’appliquait ne sont plus transmis par la solution. |
| **2** | Appel REST de la souscription supprimée<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/queries/myQuery/subscriptions | La souscription supprimée ne figure plus dans la liste des souscriptions actives. |
