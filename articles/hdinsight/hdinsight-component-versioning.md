---
title: Apache Hadoop-Komponenten und -Versionen – Azure HDInsight
description: Lernen Sie die Apache Hadoop-Komponenten und -Versionen in Azure HDInsight kennen.
author: hrasheed-msft
ms.author: hrasheed
ms.reviewer: jasonh
ms.service: hdinsight
ms.topic: conceptual
ms.custom: hdinsightactive,hdiseo17may2017,seoapr2020
ms.date: 04/09/2020
ms.openlocfilehash: 87c3e2439d1b4bef4a58663e3ea06d8bb7cb9b19
ms.sourcegitcommit: 849bb1729b89d075eed579aa36395bf4d29f3bd9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82192534"
---
# <a name="what-are-the-apache-hadoop-components-and-versions-available-with-hdinsight"></a>Welche Apache Hadoop-Komponenten und -Versionen sind in HDInsight verfügbar?

Erfahren Sie mehr über die Komponenten und Versionen der [Apache Hadoop](https://hadoop.apache.org/)-Umgebung in Microsoft Azure HDInsight und über das Enterprise-Sicherheitspaket. Darüber hinaus erfahren Sie, wie Sie Hadoop-Komponentenversionen in HDInsight überprüfen.

## <a name="apache-hadoop-components-available-with-different-hdinsight-versions"></a>Verfügbare Apache Hadoop-Komponenten in verschiedenen Versionen von HDInsight

Azure HDInsight unterstützt mehrere Hadoop-Clusterversionen, die jederzeit bereitgestellt werden können. Seit dem 4. April 2017 ist die von Azure HDInsight derzeit als Standardclusterversion verwendete Version die Version 3.6.

Die den HDInsight-Clusterversionen zugeordneten Komponentenversionen sind in der folgenden Tabelle aufgeführt:

> [!NOTE]  
> Die Standardversion für den HDInsight-Dienst kann ohne vorherige Ankündigung geändert werden. Wenn eine Versionsabhängigkeit vorliegt, geben Sie die HDInsight-Version an, wenn Sie Ihre Cluster mit dem .NET SDK mit Azure PowerShell und der klassischen Azure-Befehlszeilenschnittstelle erstellen.

| Komponente              | HDInsight 4.0 | HDInsight 3.6 (Standard)     |
|------------------------|---------------|-----------------------------|
| Apache Hadoop und YARN | 3.1.1         | 2.7.3                       |
| Apache Tez             | 0.9.1         | 0.7.0                       |
| Apache Pig             | 0.16.0        | 0.16.0                      |
| Apache Hive            | 3.1.0         | 1.2.1 (2.1.0 bei ESP Interactive Query) |
| Apache Tez Hive2       | -             | 0.8.4                       |
| Apache Ranger          | 1.1.0         | 0.7.0                       |
| Apache HBase           | 2.0.2         | 1.1.2                       |
| Apache Sqoop           | 1.4.7         | 1.4.6                       |
| Apache Oozie           | 4.3.1         | 4.2.0                       |
| Apache Zookeeper       | 3.4.6         | 3.4.6                       |
| Apache Storm           | -             | 1.1.0                       |
| Apache Mahout          | -             | 0.9.0+                      |
| Apache Phoenix         | 5             | 4.7.0                       |
| Apache Spark           | 2.3.1, 2.4    | 2.3.0, 2.2.0, 2.1.0         |
| Apache Livy            | 0.5           | 0.4, 0.4, 0.3               |
| Apache Kafka           | 1.1.1, 2.1    | 1.1, 1.0 * (Siehe Hinweis unten) |
| Apache Ambari          | 2.7.0         | 2.6.0                       |
| Apache Zeppelin        | 0.8.0         | 0.7.3                       |
| Mono                   | 4.2.1         | 4.2.1                       |

> [!NOTE]
> Aufgrund von Überlegungen zur Systemleistung ist die Unterstützung für Kafka Version 0.10 im März 2019 abgelaufen.

## <a name="check-for-current-hadoop-component-version-information"></a>Überprüfen der Informationen zur aktuellen Hadoop-Komponentenversion

Die mit den HDInsight-Clusterversionen verknüpften Komponentenversionen der Hadoop-Umgebung können sich bei Updates für HDInsight ändern. Um die Hadoop-Komponenten zu überprüfen und zu ermitteln, welche Versionen für einen Cluster verwendet werden, verwenden Sie die Ambari-REST-API. Mit dem Befehl **GetComponentInformation** rufen Sie Informationen zu Dienstkomponenten ab. Ausführliche Informationen finden Sie in der [Apache Ambari-Dokumentation](https://github.com/apache/ambari/blob/trunk/ambari-server/docs/api/v1/index.md).

### <a name="release-notes"></a>Versionshinweise

In den [HDInsight-Versionshinweisen](hdinsight-release-notes.md) finden Sie zusätzliche Anmerkungen zu den aktuellen Versionen von HDInsight.

## <a name="supported-hdinsight-versions"></a>Unterstützte HDInsight-Versionen

### <a name="support-expiration-and-retirement-for-hdinsight-versions"></a>Supportablauf und Deaktivierung von HDInsight-Versionen

**Supportablauf** bedeutet, dass Microsoft für die angegebene HDInsight-Version keinen Support mehr bereitstellt. Die Version ist zudem nicht mehr über das Azure-Portal für die Clustererstellung verfügbar. Diese Versionen können jedoch weiterhin mithilfe der Azure CLI oder der verschiedenen SDKs erstellt werden.

**Deaktivierung** einer HDInsight-Version bedeutet, dass vorhandene Cluster weiterhin unverändert ausgeführt werden. Neue Cluster dieser Version können jedoch nicht (auch nicht mithilfe der CLI und SDKs) erstellt werden. Auch andere Funktionen auf Steuerungsebene (z. B. manuelle und automatische Skalierung) können nach der Deaktivierung der Version möglicherweise nicht mehr verwendet werden. Für deaktivierte Versionen ist kein Support verfügbar.

In den folgenden Tabellen sind die Versionen von HDInsight aufgeführt. Der Ablauf der Unterstützung und die Deaktivierungstermine werden ebenfalls bereitgestellt, wenn sie bekannt sind.

### <a name="available-versions"></a>Verfügbare Versionen

Die folgende Tabelle enthält die im Azure-Portal verfügbaren Versionen von HDInsight und andere Bereitstellungsmethoden wie z.B. PowerShell und .NET SDK.

| HDInsight-Version | Betriebssystem des virtuellen Computers | Veröffentlichungsdatum | Supportablaufdatum | Deaktivierungstermin | Hochverfügbarkeit |  Verfügbarkeit im Azure-Portal |
| --- | --- | --- | --- | --- | --- | --- |
| HDInsight 4.0 |Ubuntu 16.0.4 LTS |24. September 2018 | | |Ja |Ja |
| HDInsight 3.6 |Ubuntu 16.0.4 LTS |4\. April 2017 | 31. Dezember 2020 |31. Dezember 2020 |Ja |Ja |

Die Unterstützung für Spark 2.1 und 2.2 und Kafka 1.0 läuft am 30. Juni 2020 ab.

> [!NOTE]  
> Nachdem die Unterstützung für eine Version abgelaufen ist, ist sie möglicherweise nicht mehr über das Microsoft Azure-Portal verfügbar. Clusterversionen stehen jedoch bis zum Zeitpunkt ihrer Deaktivierung weiterhin über den Parameter `Version` im Windows PowerShell-Befehl [New-AzHDInsightCluster](https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightcluster) und das .NET SDK zur Verfügung.

### <a name="retired-versions"></a>Eingestellte Versionen

Die folgende Tabelle enthält die Versionen von HDInsight, die derzeit **nicht** im Azure-Portal verfügbar sind.

| HDInsight-Version | HDP-Version | Betriebssystem des virtuellen Computers | Veröffentlichungsdatum | Supportablaufdatum | Deaktivierungstermin | Hochverfügbarkeit |  Die Verfügbarkeit im Azure-Portal |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HDInsight 3.5 |HDP 2.5 |Ubuntu 16.0.4 LTS |30. September 2016 |5\. September 2017 |28. Juni 2018 |Ja |Nein  |
| HDInsight 3.4 |HDP 2.4 |Ubuntu 14.0.4 LTS |29. März 2016 |29. Dezember 2016 |9\. Januar 2018 |Ja |Nein  |
| HDInsight 3.3 |HDP 2.3 |Windows Server 2012 R2 |2\. Dezember 2015 |27. Juni 2016 |31. Juli 2018 |Ja |Nein  |
| HDInsight 3.3 |HDP 2.3 |Ubuntu 14.0.4 LTS |2\. Dezember 2015 |27. Juni 2016 |31. Juli 2017 |Ja |Nein  |
| HDInsight 3.2 |HDP 2.2 |Ubuntu 12.04 LTS oder Windows Server 2012 R2 |18. Februar 2015 |1\. März 2016 |1\. April 2017 |Ja |Nein  |
| HDInsight 3.1 |HDP 2,1 |Windows Server 2012 R2 |24. Juni 2014 |18. Mai 2015 |30. Juni 2016 |Ja |Nein  |
| HDInsight 3.0 |HDP 2,0 |Windows Server 2012 R2 |11. Februar 2014 |17. September 2014 |30. Juni 2015 |Ja |Nein  |
| HDInsight 2.1 |HDP 1,3 |Windows Server 2012 R2 |28. Oktober 2013 |12. Mai 2014 |31. Mai 2015 |Ja |Nein  |
| HDInsight 1.6 |HDP 1.1 | |28. Oktober 2013 |26. April 2014 |31. Mai 2015 |Nein  |Nein  |

> [!NOTE]  
> Hochverfügbare Cluster mit zwei Hauptknoten werden standardmäßig für HDInsight Version 2.1 und höher bereitgestellt. Für HDInsight Version 1.6-Cluster sind sie nicht verfügbar.

## <a name="enterprise-security-package-for-hdinsight"></a>Enterprise Security Package für HDInsight

Enterprise Security für HDInsight ist ein optionales Paket, das Sie während der Clustererstellung zu Ihrem HDInsight-Cluster hinzufügen können. Das Enterprise Security Package unterstützt Folgendes:

- Integration in Active Directory für die Authentifizierung

    Bisher erstellten Sie HDInsight-Cluster ausschließlich mit einem lokalen Administratorbenutzer oder einem lokalen SSH-Benutzer. Der lokale Administratorbenutzer kann auf alle Dateien, Ordner, Tabellen und Spalten zugreifen.  Mit dem Enterprise-Sicherheitspaket können Sie die rollenbasierte Zugriffssteuerung aktivieren, indem Sie HDInsight mit Ihrem Active Directory-Konto integrieren. Dieses enthält eine lokale Active Directory-Instanz, Azure Active Directory Domain Services oder Active Directory auf einem virtuellen IaaS-Computer. Der Domänenadministrator des Clusters kann Benutzern die Berechtigung erteilen, ihren eigenen Firmen- oder Domänenbenutzernamen und ihr eigenes Kennwort zu verwenden.

    Weitere Informationen finden Sie unter

    - [Einführung in die Apache Hadoop-Sicherheit mit in die Domäne eingebundenen HDInsight-Clustern](./domain-joined/hdinsight-security-overview.md)
    - [Planen von in die Azure-Domäne eingebundenen Apache Hadoop-Clustern in HDInsight](./domain-joined/apache-domain-joined-architecture.md)
    - [Konfigurieren einer in die Domäne eingebundenen Sandboxumgebung](./domain-joined/apache-domain-joined-configure.md)
    - [Konfigurieren von in die Domäne eingebundenen HDInsight-Clustern mit Azure Active Directory Domain Services](./domain-joined/apache-domain-joined-configure-using-azure-adds.md)

- Autorisierung für Daten

  - Integration in Apache Ranger für die Autorisierung für Hive-, Spark SQL- und Yarn-Warteschlangen
  - Sie können die Zugriffssteuerung für Dateien und Ordner festlegen.

    Weitere Informationen finden Sie unter

  - [Konfigurieren von Apache Hive-Richtlinien in HDInsight mit Domänenverknüpfung](./domain-joined/apache-domain-joined-run-hive.md)

- Anzeigen der Überwachungsprotokolle zum Überwachen der Zugriffe und konfigurierten Richtlinien

### <a name="supported-cluster-types"></a>Unterstützte Clustertypen

Derzeit wird das Enterprise Security Package nur durch die folgenden Clustertypen unterstützt:

- Hadoop (nur HDInsight 3.6)
- Spark
- Kafka
- hbase
- Interactive Query

### <a name="support-for-azure-data-lake-storage"></a>Unterstützung für Azure Data Lake Storage

Das Enterprise-Sicherheitspaket unterstützt die Verwendung von Azure Data Lake Storage sowohl als Primärspeicher als auch als Zusatzspeicher.

### <a name="pricing-and-service-level-agreement-sla"></a>Preise und Vereinbarung zum Servicelevel (SLA)

Informationen zu Preisen und SLA für das Enterprise Security Package finden Sie unter [HDInsight-Preise](https://azure.microsoft.com/pricing/details/hdinsight/).

## <a name="service-level-agreement-for-hdinsight-cluster-versions"></a>Die Vereinbarung zum Servicelevel (Service Level Agreement, SLA) für HDInsight-Clusterversionen

Die Vereinbarung zum Servicelevel (Service Level Agreement, SLA) ist als _Supportfenster_ definiert. Das Supportfenster ist der Zeitraum, in dem von `Microsoft Customer Service and Support` Support für eine HDInsight-Version bereitgestellt wird. Wenn die Version ein verstrichenes _Supportablaufdatum_ aufweist, befindet sich das HDInsight-Cluster außerhalb des Supportfensters. Supportablauf für HDInsight-Version X (nachdem eine neuere X+1-Version verfügbar ist) ist das spätere Datum von:  

- Formel 1: Addieren Sie 180 Tage zum Releasedatum von HDInsight-Clusterversion X.
- Formel 2: Addieren Sie 90 Tage zum Releasedatum von HDInsight-Clusterversion X+1 im Azure-Portal.

Das _Deaktivierungsdatum_ ist das Datum, nach dem die Clusterversion nicht mehr in HDInsight erstellt werden kann. Ab dem 31. Juli 2017 kann die Größe eines HDInsight-Clusters nach dessen Deaktivierungsdatum nicht mehr geändert werden.

## <a name="default-node-configuration-and-virtual-machine-sizes-for-clusters"></a>Standardknotenkonfiguration und Standardgrößen von virtuellen Computern für Cluster

Weitere Informationen dazu, welche SKUs für virtuelle Computer für Ihren Cluster ausgewählt werden sollten, finden Sie in dem Artikel über [Details einer Azure HDInsight-Clusterkonfiguration](hdinsight-supported-node-configuration.md).

## <a name="next-steps"></a>Nächste Schritte

- [Einrichten von Clustern in HDInsight mit Apache Hadoop, Spark, Kafka usw.](hdinsight-hadoop-provision-linux-clusters.md)
- [Verwenden eines Windows-Computers mit Apache Hadoop in HDInsight](hdinsight-hadoop-windows-tools.md)
- [Hortonworks-Versionshinweise im Zusammenhang mit Azure HDInsight-Versionen](./hortonworks-release-notes.md)
