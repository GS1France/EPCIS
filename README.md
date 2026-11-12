# EPCIS
Procédure de qualification des solutions de traçabilité au standard GS1 EPCIS

Ce répertoire regroupe les fiches de tests permettant de vérifier la conformité d'une solution EPCIS 2.0.

Les tests sont organisés en trois catégories :

- **A – Capture API** : capture des événements EPCIS et des données de référence
- **B – Query API** : interrogation des événements EPCIS
- **C – Subscriptions API** : requêtes nommées et souscriptions

---

## A – Capture API

| ID | Test |
|---|---|
| A-01 | [ObjectEvent](Capture-API/A-01-ObjectEvent.md) |
| A-02 | [ObjectEvent – KO](Capture-API/A-02-ObjectEvent-KO.md) |
| A-03 | [AssociationEvent](Capture-API/A-03-AssociationEvent.md) |
| A-04 | [AssociationEvent – KO](Capture-API/A-04-AssociationEventKO.md) |
| A-05 | [AggregationEvent](Capture-API/A-05-AggregationEvent.md) |
| A-06 | [AggregationEvent – KO](Capture-API/A-06-AggregationEvent-KO.md) |
| A-07 | [TransactionEvent](Capture-API/A-07-TransactionEvent.md) |
| A-08 | [TransactionEvent – KO](Capture-API/A-08-TransactionEvent-KO.md) |
| A-09 | [TransformationEvent](Capture-API/A-09-TransformationEvent.md) |
| A-10 | [TransformationEvent – KO](Capture-API/A-10-TransformationEvent-KO.md) |
| A-11 | [Multiple Events](Capture-API/A-11-Multiple-Events.md) |
| A-12 | [Multiple Events – KO](Capture-API/A-12-Multiple-Events-KO.md) |
| A-13 | [Trade Item Master Data](Capture-API/A-13-Trade-item-master-data.md) |
| A-14 | [Location Master Data](Capture-API/A-14-Location-master-data.md) |
| A-15 | [Business Transaction](Capture-API/A-15-BizTransaction.md) |
| A-16 | [Source / Destination](Capture-API/A-16-Source-Destination.md) |
| A-17 | [Quantity](Capture-API/A-17-Quantity.md) |
| A-18 | [ILMD](Capture-API/A-18-ILMD.md) |
| A-19 | [Extension Schema](Capture-API/A-19-Extension-schema.md) |

---

## B – Query API

| ID | Test |
|---|---|
| B-01 | [Standard Version](Query-API/B-01-StandardVersion.md) |
| B-02 | [Get Events](Query-API/B-02-Get-Events.md) |
| B-03 | [Exceptions](Query-API/B-03-Exceptions.md) |

---

## C – Subscriptions API

| ID | Test |
|---|---|
| C-01 | [Requête nommée](Subscriptions-API/C-01-Requête-Nommée.md) |
| C-02 | [Exécution d'une requête nommée](Subscriptions-API/C-02-Exécution-Requête-Nommée.md) |
| C-03 | [Création d'une souscription](Subscriptions-API/C-03-Création-Souscription.md) |
| C-04 | [Suppression d'une souscription](Subscriptions-API/C-04-Suppression-Souscription.md) |
| C-05 | [Souscription – KO](Subscriptions-API/C-05-Souscription-KO.md) |
| C-06 | [Suppression d'une requête nommée](Subscriptions-API/C-06-Suppression-Requête-Nommée.md) |
