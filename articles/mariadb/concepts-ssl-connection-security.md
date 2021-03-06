---
title: SSL-Konnektivität – Azure Database for MariaDB
description: Informationen zum Konfigurieren von Azure Database for MariaDB und zugehörigen Anwendungen für die richtige Verwendung von SSL-Verbindungen
author: ajlam
ms.author: andrela
ms.service: mariadb
ms.topic: conceptual
ms.date: 03/10/2020
ms.openlocfilehash: 36532575645d135a7abe7239798b6f2abc4246f2
ms.sourcegitcommit: 849bb1729b89d075eed579aa36395bf4d29f3bd9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "79477067"
---
# <a name="ssl-connectivity-in-azure-database-for-mariadb"></a>SSL-Konnektivität in Azure Database for MariaDB
Azure Database for MariaDB unterstützt die Verbindung Ihres Datenbankservers mit Clientanwendungen, die Secure Sockets Layer (SSL) verwenden. Das Erzwingen von SSL-Verbindungen zwischen dem Datenbankserver und Clientanwendungen trägt zum Schutz vor Man-in-the-Middle-Angriffen bei, indem der Datenstrom zwischen dem Server und der Anwendung verschlüsselt wird.

## <a name="default-settings"></a>Standardeinstellungen
Der Datenbankdienst sollte standardmäßig so konfiguriert sein, dass beim Herstellen einer Verbindung mit MariaDB SSL-Verbindungen erforderlich sind.  Es wird empfohlen, die SSL-Option wenn möglich nicht zu deaktivieren.

Bei der Bereitstellung eines neuen Azure Database for MariaDB-Servers über das Azure-Portal und die CLI wird die Erzwingung von SSL-Verbindungen standardmäßig aktiviert.

Verbindungszeichenfolgen für verschiedene Programmiersprachen werden im Azure-Portal angezeigt. Diese Verbindungszeichenfolgen schließen die erforderlichen SSL-Parameter für die Verbindung mit Ihrer Datenbank ein. Wählen Sie im Azure-Portal Ihren Server aus. Wählen Sie unter der Überschrift **Einstellungen** die Option **Verbindungszeichenfolgen** aus. Der SSL-Parameter variiert je nach Connector, z.B. „ssl=true“ oder „sslmode=require“ oder „sslmode=required“ und weitere Variationen.

Informationen zum Aktivieren oder Deaktivieren von SSL-Verbindungen bei der Anwendungsentwicklung finden Sie unter [Konfigurieren von SSL](howto-configure-ssl.md).

## <a name="next-steps"></a>Nächste Schritte
- Erfahren Sie mehr über [Firewallregeln des Azure Database for MariaDB-Servers](concepts-firewall-rules.md).
- Erfahren Sie mehr über das [Konfigurieren der SSL-Konnektivität in der Anwendung für eine sichere Verbindung mit Azure Database for MariaDB](howto-configure-ssl.md).
