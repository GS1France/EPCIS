# Fiche de test C-06

## Suppression d’une requête nommée

### Objectif

Validation de la capacité de la solution à supprimer une requête nommée afin de désactiver les souscriptions qui lui sont rattachées

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Une requête nommée est enregistrée dans la solution (cf. test E.01)
- Une souscription à une requête nommée est enregistrée dans la solution (cf. test E-03)

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Suppression de la requête nommée<br><br>Exemple :<br><br>DELETE https://my-system.example.com/epcis/queries/myQuery | La solution confirme la suppression de la requête nommée par un code de statut de réponse de succès HTTP.<br><br>Les événements associés à la requête nommée pour laquelle la souscription s’appliquait ne sont plus transmis par la solution. |
| **2** | Appel REST de l’endpoint Queries<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/queries | La liste des requêtes nommées est renvoyée par la solution. La requête nommée supprimée à l’étape 1 ne figure pas dans la liste. |
| **3** | Envoi d’un événement correspondant aux paramètres d’une souscription existante et associée à la requête nommée supprimée à l’étape 1 | L’événement n’est pas transmis au titre de la souscription applicable. |
