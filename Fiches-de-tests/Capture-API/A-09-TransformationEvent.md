# Fiche de test A-09

## Enregistrement d’un événement de type « Transformation Event » via requête HTTP POST

### Objectif

Validation de la capacité de la solution à intégrer un événement de type « Transformation Event » conforme au standard EPCIS via l’interface de capture (HTTP POST)

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un modèle d’événement de type « Transformation Event » est partagé avec l’éditeur. Ce document est constitué des attributs de données qui doivent obligatoirement être enregistrées dans un événement de type « Transformation Event ». A savoir :
- Event type
- eventTime
- eventTimeZoneOffset
- inputEPCList & inputQuantityList ET outputEPCList & outputQuantityList (si l’attribut TransformationID n’est pas renseigné)
- inputEPCList & inputQuantityList OU outputEPCList & outputQuantityList (si l’attribut TransformationID est renseigné)

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant un événement « Transformation Event » conforme au standard EPCIS<br><br>Exemple :<br><br>POST https://my-system.example.com/epcis/capture avec un Transformation Event conforme. | L’événement constitué de l’ensemble des attributs de données est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
