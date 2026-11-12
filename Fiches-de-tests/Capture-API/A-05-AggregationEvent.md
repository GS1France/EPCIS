# Fiche de test A-05

## Enregistrement d’un événement de type « Aggregation Event » via requête HTTP POST

### Objectif

Validation de la capacité de la solution à intégrer un événement de type « Aggregation Event » conforme au standard EPCIS via l’interface de capture (HTTP POST)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un modèle d’événement de type « Aggregation Event » est partagé avec l’éditeur. Ce document est constitué des attributs de données qui doivent obligatoirement être enregistrées dans un événement de type « Aggregation Event ». A savoir :
  - Event type
  - eventTime
  - eventTimeZoneOffset
  - Action
  - ParentID
  - childEPCs et/ou childQuantityList (sauf si la valeur de l’attribut action est DELETE) avec en valeur un ou des identifiant(s) GS1 en syntaxe GS1 Digital Link URI ou EPC URN

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant un événement « Aggregation Event » conforme au standard EPCIS<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/capture avec un Aggregation Event conforme. | L’événement constitué de l’ensemble des attributs de données est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
