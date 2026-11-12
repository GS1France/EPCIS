# Fiche de test A-07

## Enregistrement d’un événement de type « Transaction Event » via requête HTTP POST

### Objectif

Validation de la capacité de la solution à intégrer un événement de type « Transcation Event » conforme au standard EPCIS via l’interface de capture (HTTP POST)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un modèle d’événement de type « Transaction Event » est partagé avec l’éditeur. Ce document est constitué des attributs de données qui doivent obligatoirement être enregistrées dans un événement de type « Transaction Event ». A savoir :
- Event type
- eventTime
- eventTimeZoneOffset
- Action
- epcList et/ou quantityList (sauf si la valeur de l’attribut action est DELETE) avec en valeur un ou des identifiant(s) GS1 en syntaxe GS1 Digital Link URI ou EPC URN
- BizTransactionList

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant un événement « Transaction Event » conforme au standard EPCIS<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/capture avec un Transaction Event conforme. | L’événement constitué de l’ensemble des attributs de données est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
