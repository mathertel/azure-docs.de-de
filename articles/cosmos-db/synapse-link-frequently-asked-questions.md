---
title: Häufig gestellte Fragen zu Azure Synapse Link für Azure Cosmos DB
description: Hier erhalten Sie Antworten auf häufig gestellte Fragen zu Synapse Link für Azure Cosmos DB in Bereichen wie Abrechnung, Analysespeicher, Sicherheit und Gültigkeitsdauer im Analysespeicher.
author: srchi
ms.author: srchi
ms.service: cosmos-db
ms.topic: conceptual
ms.date: 05/19/2020
ms.openlocfilehash: 36be05f72597ae9864eff812862589cafb1f5b0d
ms.sourcegitcommit: bb0afd0df5563cc53f76a642fd8fc709e366568b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83596469"
---
# <a name="frequently-asked-questions-about-azure-synapse-link-for-azure-cosmos-db"></a>Häufig gestellte Fragen zu Azure Synapse Link für Azure Cosmos DB

Azure Synapse Link für Azure Cosmos DB sorgt für eine enge Integration zwischen Azure Cosmos DB und Azure Synapse Analytics. Dadurch können Kunden Analysen in Quasi-Echtzeit zu ihren operativen Daten durchführen, wobei eine vollständige Leistungsisolation von ihren Transaktionsworkloads ohne ETL-Pipeline besteht. Dieser Artikel bietet Antworten auf häufig gestellte Fragen zu Synapse Link für Azure Cosmos DB.

## <a name="general-faq"></a>Allgemeine häufig gestellte Fragen

### <a name="is-synapse-link-supported-for-all-azure-cosmos-db-apis"></a>Wird Synapse Link für alle Azure Cosmos DB-APIs unterstützt?
In der öffentlichen Vorschauversion wird Synapse Link nur für die Azure Cosmos DB SQL (Core)-API unterstützt. Die Unterstützung für die Cosmos DB-API für Mongo DB und die Cassandra-API befindet sich derzeit in der geschlossenen Vorschau.  Wenn Sie Zugriff auf die geschlossene Vorschau anfordern möchten, wenden Sie sich an das [Azure Cosmos DB-Team](mailto:cosmosdbsynapselink@microsoft.com).

### <a name="is-synapse-link-supported-for-multi-region-azure-cosmos-accounts"></a>Wird Synapse Link für Azure Cosmos-Konten in mehreren Regionen unterstützt?
Ja, für Azure Cosmos-Konten in mehreren Regionen werden die im Analysespeicher gespeicherten Daten auch global verteilt. Unabhängig davon, ob eine einzelne Schreibregion (einzelner Master) oder mehrere Schreibregionen (Multimaster) genutzt werden, können analytische Abfragen, die von Azure Synapse Analytics ausgeführt werden, von der nächstgelegenen lokalen Region verarbeitet werden.

Wenn Sie die Konfiguration eines Azure Cosmos-Kontos in mehreren Regionen mit Unterstützung für Analysespeicher planen, empfiehlt es sich, beim Erstellen des Kontos alle erforderlichen Regionen hinzuzufügen.

### <a name="can-i-choose-to-enable-synapse-link-for-only-certain-region-and-not-all-regions-in-a-multi-region-account-set-up"></a>Kann ich auswählen, dass Synapse Link in einem Konto mit mehreren Regionen nur für eine bestimmte Region und nicht für alle Regionen eingerichtet werden soll?
Wenn Synapse Link in der Vorschauversion für ein Konto mit mehreren Regionen aktiviert ist, wird der Analysespeicher in allen Regionen erstellt. Die zugrunde liegenden Daten sind für Durchsatz und Transaktionskonsistenz im Transaktionsspeicher optimiert.

### <a name="can-i-disable-the-synapse-link-feature-for-my-azure-cosmos-account"></a>Kann ich die Synapse Link-Funktion für mein Azure Cosmos-Konto deaktivieren?
Wenn die Synapse Link-Funktion auf Kontoebene aktiviert ist, ist es derzeit nicht möglich, sie zu deaktivieren.  Wenn Sie die Funktion deaktivieren möchten, müssen Sie Ihr Azure Cosmos-Konto löschen und ein neues erstellen.

Wenn die Synapse Link-Funktion auf Kontoebene aktiviert ist, Sie aber über keine vom Analysespeicher aktivierten Container verfügen, hat dies **keine** Auswirkungen auf die Abrechnung.

## <a name="azure-cosmos-db-analytical-store"></a>Azure Cosmos DB-Analysespeicher

### <a name="can-i-enable-analytical-store-on-existing-containers"></a>Kann ich den Analysespeicher für vorhandene Container aktivieren?
Derzeit kann der Analysespeicher nur für neue Container (in neuen und vorhandenen Konten) aktiviert werden.

### <a name="can-i-disable-analytical-store-on-my-azure-cosmos-containers-after-enabling-it-during-container-creation"></a>Kann ich den Analysespeicher für meine Azure Cosmos-Container deaktivieren, wenn er während der Containererstellung aktiviert wurde?
Derzeit kann der Analysespeicher in einem Azure Cosmos-Container nicht deaktiviert werden, wenn er während der Containererstellung aktiviert wurde.

### <a name="is-analytical-store-supported-for-azure-cosmos-containers-with-autoscale-provisioned-throughput"></a>Wird der Analysespeicher für Azure Cosmos-Container mit per Autoskalierung bereitgestelltem Durchsatz unterstützt?
Ja, der Analysespeicher kann für Container mit per Autoskalierung bereitgestelltem Durchsatz aktiviert werden.

### <a name="is-there-any-effect-on-azure-cosmos-db-transactional-store-provisioned-rus"></a>Gibt es Auswirkungen auf vom Azure Cosmos DB-Transaktionsspeicher bereitgestellte RUs?
Azure Cosmos DB garantiert eine Leistungsisolation zwischen Transaktions- und Analyseworkloads. Wenn Sie den Analysespeicher für einen Container aktivieren, hat dies keine Auswirkungen auf die RUs, die im Azure Cosmos DB-Transaktionsspeicher bereitgestellt wurden. Die Transaktionen (Lese- und Schreibvorgänge) und die Speicherkosten für den Analysespeicher werden separat abgerechnet. Weitere Informationen finden Sie in den [Preisen für den Azure Cosmos DB-Analysespeicher](analytical-store-introduction.md#analytical-store-pricing).

### <a name="are-delete-and-update-operations-on-the-transactional-store-reflected-in-the-analytical-store"></a>Spiegeln sich im Transaktionsspeicher vorgenommene Lösch- und Aktualisierungsvorgänge im Analysespeicher wider? 
Ja, im Transaktionsspeicher vorgenommene Lösch- und Aktualisierungsvorgänge spiegeln sich im Analysespeicher wider. Sie können die Gültigkeitsdauer (Time to Live, TTL) für den Container so konfigurieren, dass Verlaufsdaten einbezogen werden, damit der Analysespeicher alle Versionen der Elemente beibehält, die die analytischen TTL-Kriterien erfüllen. Weitere Informationen finden Sie in der [Übersicht über die analytische Gültigkeitsdauer](analytical-store-introduction.md#analytical-ttl).

### <a name="can-i-connect-to-analytical-store-from-analytics-engines-other-than-azure-synapse-analytics"></a>Kann ich über andere Analysemodule als Azure Synapse Analytics eine Verbindung mit dem Analysespeicher herstellen?
Mithilfe der verschiedenen von Azure Synapse Analytics bereitgestellten Laufzeiten können Sie nur auf Abfragen für den Analysespeicher zugreifen und diese ausführen. Der Analysespeicher kann mithilfe von Folgendem abgefragt und analysiert werden:

* Synapse Spark mit vollständiger Unterstützung für Scala, Python, SparkSQL und C#. Synapse Spark ist von zentraler Bedeutung für Datentechnik- und Data Science-Szenarien.
* SQL (serverlos) mit T-SQL-Sprache und Unterstützung für bekannte BI-Tools (z. B. Power BI Premium usw.)

### <a name="can-i-connect-to-analytical-store-from-synapse-sql-provisioned"></a>Kann ich über Synapse SQL (bereitgestellt) eine Verbindung mit dem Analysespeicher herstellen?
Derzeit ist es nicht möglich, über Synapse SQL (bereitgestellt) auf den Analysespeicher zuzugreifen.

### <a name="can-i-write-back-the-query-aggregation-results-from-synapse-back-to-the-analytical-store"></a>Kann ich die Abfrageaggregationsergebnisse aus Synapse zurück in den Analysespeicher schreiben?
Der Analysespeicher ist ein schreibgeschützter Speicher in einem Azure Cosmos-Container. Daher können Sie die Aggregationsergebnisse nicht direkt in den Analysespeicher schreiben, Sie können sie jedoch in den Azure Cosmos DB-Transaktionsspeicher eines anderen Containers schreiben, der später als Bereitstellungsebene genutzt werden kann.

### <a name="is-the-autosync-replication-from-transactional-store-to-the-analytical-store-asynchronous-or-synchronous-and-what-are-the-latencies"></a>Ist die Replikation mit automatischer Synchronisierung aus dem Transaktionsspeicher in den Analysespeicher asynchron oder synchron, und welche Wartezeiten bestehen? 
Die Replikation ist asynchron, und die erwartete Wartezeit liegt derzeit bei ca. zwei Minuten.

### <a name="are-there-any-scenarios-where-the-items-from-the-transactional-store-are-not-automatically-propagated-to-the-analytical-store"></a>Gibt es Szenarien, in denen die Elemente aus dem Transaktionsspeicher nicht automatisch an den Analysespeicher weitergegeben werden?
Wenn bestimmte Elemente in Ihrem Container gegen das [genau definierte Schema für Analysen](analytical-store-introduction.md#analytical-schema) verstoßen, werden sie nicht in den Analysespeicher aufgenommen. Wenn Sie Szenarien durch ein genau definiertes Schema für Analysen blockiert haben, wenden Sie sich per E-Mail an das [Azure Cosmos DB-Team](mailto:cosmosdbsynapselink@microsoft.com), um Hilfe zu erhalten.

### <a name="can-i-partition-the-data-in-analytical-store-differently-from-transactional-store"></a>Kann ich die Daten im Analysespeicher anders partitionieren als im Transaktionsspeicher?
Die Daten im Analysespeicher werden basierend auf der horizontalen Partitionierung von Datenbank-Shards im Transaktionsspeicher partitioniert. Derzeit ist es nicht möglich, eine andere Partitionierungsstrategie für den Analysespeicher auszuwählen.

### <a name="can-i-customize-or-override-the-way-transactional-data-is-transformed-into-columnar-format-in-the-analytical-store"></a>Kann ich die Art und Weise, wie Transaktionsdaten in das Spaltenformat im Analysespeicher transformiert werden, anpassen oder außer Kraft setzen?
Derzeit können Sie die Datenelemente nicht transformieren, wenn sie automatisch aus dem Transaktionsspeicher in den Analysespeicher weitergegeben werden. Wenn Sie Szenarien durch diese Einschränkung blockiert haben, wenden Sie sich per E-Mail an das [Azure Cosmos DB-Team](mailto:cosmosdbsynapselink@microsoft.com).

## <a name="analytical-time-to-live-ttl"></a>Analytische Gültigkeitsdauer (Time To Live, TTL)

### <a name="is-ttl-for-analytical-data-supported-at-both-container-and-item-level"></a>Wird die Gültigkeitsdauer für analytische Daten sowohl auf Container- als auch auf Elementebene unterstützt?
Derzeit kann die Gültigkeitsdauer für analytische Daten nur auf Containerebene konfiguriert werden, und das Festlegen der analytischen Gültigkeitsdauer auf Elementebene wird nicht unterstützt.

### <a name="after-setting-the-container-level--analytical-ttl-on-an-azure-cosmos-db-container-can-i-change-to-a-different-value-later"></a>Kann ich nach dem Festlegen der analytischen Gültigkeitsdauer auf Containerebene für einen Azure Cosmos DB-Container später zu einem anderen Wert wechseln?
Ja, die analytische Gültigkeitsdauer kann auf einen beliebigen gültigen Wert aktualisiert werden. Weitere Informationen zur analytischen Gültigkeitsdauer finden Sie im Artikel [Analytische Gültigkeitsdauer](analytical-store-introduction.md#analytical-ttl).

### <a name="can-i-update-or-delete-an-item-from-the-analytical-store-after-it-has-been-ttld-out-from-the-transactional-store"></a>Kann ich ein Element im Analysespeicher aktualisieren oder löschen, nachdem die Gültigkeitsdauer im Transaktionsspeicher abgelaufen ist?
Alle transaktionalen Aktualisierungen und Löschvorgänge werden in den Analysespeicher kopiert. Wenn das Element jedoch aus dem Transaktionsspeicher gelöscht wurde, kann es im Analysespeicher nicht aktualisiert werden. Weitere Informationen finden Sie im Artikel [Analytische Gültigkeitsdauer](analytical-store-introduction.md#analytical-ttl).

## <a name="billing"></a>Abrechnung

### <a name="what-is-the-billing-model-of-synapse-link-for-azure-cosmos-db"></a>Was ist das Abrechnungsmodell von Synapse Link für Azure Cosmos DB?
Der [Azure Cosmos DB-Analysespeicher](analytical-store-introduction.md) ist in der öffentlichen Vorschau bis zum 30. August 2020 ohne zusätzliche Kosten verfügbar. Synapse Spark und Synapse SQL werden über die [Synapse-Dienstnutzung](https://azure.microsoft.com/pricing/details/synapse-analytics/) abgerechnet.

## <a name="security"></a>Sicherheit

### <a name="what-are-the-ways-to-authenticate-with-the-analytical-store"></a>Welche Möglichkeiten gibt es für die Authentifizierung beim Analysespeicher?
Die Authentifizierung beim Analysespeicher erfolgt genauso wie beim Transaktionsspeicher. Für eine bestimmte Datenbank können Sie sich mit dem Masterschlüssel oder dem schreibgeschützten Schlüssel authentifizieren. Sie können den verknüpften Dienst in Synapse Studio nutzen, um zu verhindern, dass die Azure Cosmos DB-Schlüssel in die Spark-Notebooks eingefügt werden. Der Zugriff auf diesen verknüpften Dienst steht allen Benutzern zur Verfügung, die Zugriff auf den Arbeitsbereich haben.

## <a name="synapse-run-times"></a>Synapse-Laufzeiten

### <a name="what-are-the-currently-supported-synapse-run-times-to-access-azure-cosmos-db-analytical-store"></a>Welche Synapse-Laufzeiten werden derzeit für den Zugriff auf den Azure Cosmos DB-Analysespeicher unterstützt?

|Synapse-Laufzeit |Aktuelle Unterstützung |
|---------|---------|
|Synapse Spark-Pools | Lesen, Schreiben (über Transaktionsspeicher), Tabelle, temporäre Ansicht |
|Synapse SQL (serverlos)    | Lesen, Anzeigen (geschlossene Vorschau)  |
|Synapse SQL (bereitgestellt)   |  Nicht verfügbar |

### <a name="do-my-synapse-spark-tables-sync-with-my-synapse-sql-serverless-tables-the-same-way-they-do-with-azure-data-lake"></a>Erfolgt die Synchronisierung meiner Synapse Spark-Tabellen mit meinen Tabellen von Synapse SQL (serverlos) genau so wie bei Azure Data Lake?
Diese Funktion ist derzeit nicht verfügbar.

### <a name="can-i-do-spark-structured-streaming-from-analytical-store"></a>Kann ich strukturiertes Spark-Streaming aus dem Analysespeicher durchführen?
Die Unterstützung für strukturiertes Spark-Streaming für Azure Cosmos DB wird derzeit mithilfe der Änderungsfeedfunktion des Transaktionsspeichers implementiert. Im Analysespeicher wird dies noch nicht unterstützt.

## <a name="synapse-studio"></a>Synapse Studio

### <a name="in-the-synapse-studio-how-do-i-recognize-if-im-connected-to-an-azure-cosmos-db-container-with-the-analytics-store-enabled"></a>Wie erkenne ich in Synapse Studio, ob eine Verbindung mit einem Azure Cosmos DB-Container besteht, der mit dem Analysespeicher aktiviert ist?
Ein Azure Cosmos DB-Container, der mit dem Analysespeicher aktiviert ist, weist das folgende Symbol auf:

![Ein Azure Cosmos DB-Container, der mit dem Analysespeicher aktiviert ist – Symbol](./media/synapse-link-frequently-asked-questions/analytical-store-icon.png)

Ein Transaktionsspeichercontainer wird durch das folgende Symbol dargestellt:

![Ein Azure Cosmos DB Container, der mit dem Transaktionsspeicher aktiviert ist – Symbol](./media/synapse-link-frequently-asked-questions/transactional-store-icon.png)
 
### <a name="how-do-you-pass-azure-cosmos-db-credentials-from-synapse-studio"></a>Wie werden Azure Cosmos DB-Anmeldeinformationen von Synapse Studio übermittelt?
Derzeit werden Azure Cosmos DB-Anmeldeinformationen beim Erstellen des verknüpften Diensts von dem Benutzer übermittelt, der Zugriff auf die Azure Cosmos DB-Datenbanken hat. Der Zugriff auf diesen Speicher steht anderen Benutzern zur Verfügung, die Zugriff auf den Arbeitsbereich haben.

## <a name="next-steps"></a>Nächste Schritte

* Erfahren Sie mehr über die [Vorteile von Synapse Link](synapse-link.md#synapse-link-benefits).

* Erfahren Sie mehr über die [Integration zwischen Synapse Link und Azure Cosmos DB](synapse-link.md#synapse-link-integration).
