# Fiche de test A-18

## Enregistrement d’un événement incluant une section ILMD (Instance/Lot Master Data) via requête HTTP POST

### Objectif

Vérification de la capacité de la solution à intégrer une section ILMD (Instance/Lot Master Data) dans laquelle un numéro de lot est déclaré

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant un événement constitué d’une section ILMD est partagé avec l’éditeur

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant une section ILMD conforme au standard EPCIS | L’événement incluant le numéro de lot déclaré dans la section ILMD est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
