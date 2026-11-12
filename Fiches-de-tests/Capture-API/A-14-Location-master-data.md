# Fiche de test A-14

## Enregistrement d’un événement incluant des données de référence sur un lieu via requête HTTP POST

### Objectif

Vérification de la capacité de la solution à intégrer des données de référence sur un lieu (location master data) incluses dans le header du document EPICS.

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un header avec une section VocabularyList constitué de données de référence sur un lieu est partagé avec l’éditeur

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant un header constitué d’une section VocabularyList relative à un lieu | Les données de référence indiquées dans le header du document EPCIS sont enregistrées par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
