# Fiche de test B-01

## Obtention de la version du standard EPCIS et de la version de la solution

### Objectif

Validation de la capacité de la solution à transmettre le numéro de version du standard **EPCIS** implémenté ainsi que le numéro de version de la solution implémentée par l’éditeur.

### Prérequis

- Le serveur de requêtes EPCIS est en cours d’exécution.
- La solution autorise les requêtes entrantes (authentification du client auprès de l’API).

---

### Étapes de test

| Étape | Description de l’étape | Résultats attendus |
|:---:|---|---|
| **1** | Appel REST d’un endpoint de la solution.<br><br>**Exemple :**<br>`GET https://my-system.example.com/epcis/events` | Le numéro de version **2.0** du standard EPCIS est renvoyé dans le header de la réponse.<br><br>Le numéro de version de la solution de l’éditeur est renvoyé, si applicable.<br><br>La chaîne de caractères définie par l’éditeur doit être conforme à une URI. La chaîne de caractères peut être vide. |
