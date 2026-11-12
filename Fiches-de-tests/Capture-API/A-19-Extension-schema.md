# Fiche de test A-19

## Enregistrement d’un événement incluant des données associées à schéma d’extension référencé dans le document EPCIS

### Objectif

Vérification de la capacité de la solution à intégrer des donnés additionnels au standard EPCIS via un schéma d’extension (namespace contexte JSON) référencé dans le document EPCIS

### Prérequis

- Le serveur de requêtes EPCIS est en cours d'exécution
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API)
- Un document EPCIS au format JSON incluant des données faisant référence à un schéma d’extension

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Envoi d’un document EPCIS incluant des données faisant référence à un schéma d’extension | L’événement incluant les données associées au schéma d’extension est enregistré par la solution.<br><br>Le serveur retourne un code de statut de réponse de succès HTTP. |
