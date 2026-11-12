# Fiche de test B-03

## Mise en œuvre des exceptions suite à une requête non conforme au standard EPCIS

### Objectif

Vérification de la capacité de la solution à prendre le charge les exceptions telles que définies dans le standard EPCIS. Ces exceptions sont générées en raison de paramètres manquants ou incorrects transmis dans les méthodes de requête.

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Des événements EPCIS au format JSON constitué d’attributs de données conformes au standard EPCIS sont enregistrés dans la solution

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Appel REST de l’endpoints Events incluant des paramètres non conformes au standard EPCIS<br><br>Exemple :<br><br>GET https://my-system.example.com/epcis/events?EQ_action=ADDING | Une exception est renvoyée par la solution.<br><br>Cette exception doit être conforme à la RFC 7807 (Problem Details for HTTP APIs).<br><br>Exemple :<br><br>{<br><br>"type": "epcisException",<br><br>"title": " QueryParameterException",<br><br>"status": 400,<br><br>"detail": "Invalid value for action: ADDING"<br><br>} |
