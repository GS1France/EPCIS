# Fiche de test B-02

## Obtention d’événements conformes au standard EPCIS via méthode REST

### Objectif

Validation de la capacité de la solution à exécuter une requête standard afin d’obtenir des événements conformes au standard EPCIS.

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Des événements EPCIS au format JSON constitué d’attributs de données conformes au standard EPCIS sont enregistrés dans la solution

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Appel REST de l’endpoint Events incluant des paramètres standardisés<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/events?eventType=ObjectEvent | Les données correspondantes aux paramètres de la requête sont renvoyées par la solution dans un EPCIS Query Document conforme au standard.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
