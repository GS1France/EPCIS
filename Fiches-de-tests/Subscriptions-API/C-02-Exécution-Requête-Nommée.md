# Fiche de test C-02

## Exécution d’une requête nommée

### Objectif

Validation de la capacité de la solution à exécuter une requête nommée afin de restituer les événements correspondants aux filtres définies par la requête

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Des événements EPCIS au format JSON constitué d’attributs de données conformes au standard EPCIS sont enregistrés dans la solution

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Appel REST de la requête nommée<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/queries/myQuery/events | Les données correspondantes aux filtres de la requête sont renvoyées par la solution dans un EPCIS Query Document conforme au standard.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
