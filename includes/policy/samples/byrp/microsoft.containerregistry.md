---
author: DCtheGeek
ms.service: azure-policy
ms.topic: include
ms.date: 05/13/2020
ms.author: dacoulte
ms.custom: generated
ms.openlocfilehash: 37c3899ecacb445258c58252d3fea545f9ea380f
ms.sourcegitcommit: fdec8e8bdbddcce5b7a0c4ffc6842154220c8b90
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83658258"
---
|Name |BESCHREIBUNG |Auswirkungen |Version |GitHub |
|---|---|---|---|---|
|[Containerregistrierungen müssen mit einem kundenseitig verwalteten Schlüssel (CMK) verschlüsselt werden](https://portal.azure.com/#blade/Microsoft_Azure_Policy/PolicyDetailBlade/definitionId/%2Fproviders%2FMicrosoft.Authorization%2FpolicyDefinitions%2F5b9159ae-1701-4a6f-9a7a-aa9c8ddd0580) |Hiermit überwachen Sie Containerregistrierungen, für die die Verschlüsselung mit kundenseitig verwalteten Schlüsseln (Customer-Managed Key, CMK) nicht aktiviert ist. Weitere Informationen zur CMK-Verschlüsselung finden Sie unter [https://aka.ms/acr/CMK](https://aka.ms/acr/CMK). |Audit, Disabled |1.0.0-preview |[Link](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/Container%20Registry/ACR_CMKEncryptionEnabled_Audit.json) |
|[Containerregistrierungen dürfen keinen uneingeschränkten Netzwerkzugriff zulassen](https://portal.azure.com/#blade/Microsoft_Azure_Policy/PolicyDetailBlade/definitionId/%2Fproviders%2FMicrosoft.Authorization%2FpolicyDefinitions%2Fd0793b48-0edc-4296-a390-4c75d1bdfd71) |Hiermit überwachen Sie Containerregistrierungen, für die keine Netzwerkregeln (IP oder VNET) konfiguriert sind und standardmäßig den gesamten Netzwerkzugriff zulassen. Containerregistrierungen mit mindestens einer IP-/Firewallregel oder einem konfigurierten virtuellen Netzwerk werden als konform eingestuft. Weitere Informationen zu Container Registry-Netzwerkregeln finden Sie unter [https://aka.ms/acr/vnet](https://aka.ms/acr/vnet). |Audit, Disabled |1.0.0-preview |[Link](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/Container%20Registry/ACR_NetworkRulesExist_Audit.json) |
|[Containerregistrierungen müssen Private Link-Instanzen verwenden](https://portal.azure.com/#blade/Microsoft_Azure_Policy/PolicyDetailBlade/definitionId/%2Fproviders%2FMicrosoft.Authorization%2FpolicyDefinitions%2Fe8eef0a8-67cf-4eb4-9386-14b0e78733d4) |Überwachen Sie Containerregistrierungen, die nicht über mindestens eine Verbindung mit privatem Endpunkt verfügen. Clients in einem virtuellen Netzwerk können über Private Link-Instanzen sicher auf Ressourcen mit Verbindungen mit privaten Endpunkten zugreifen. Weitere Informationen finden Sie unter [https://aka.ms/acr/private-link](https://aka.ms/acr/private-link). |Audit, Disabled |1.0.0-preview |[Link](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/Container%20Registry/ACR_PrivateEndpointEnabled_Audit.json) |
|[Container Registry sollte einen VNET-Dienstendpunkt verwenden.](https://portal.azure.com/#blade/Microsoft_Azure_Policy/PolicyDetailBlade/definitionId/%2Fproviders%2FMicrosoft.Authorization%2FpolicyDefinitions%2Fc4857be7-912a-4c75-87e6-e30292bcdf78) |Diese Richtlinie überwacht alle Container Registry-Instanzen, die nicht für die Verwendung eines VNET-Dienstendpunkts konfiguriert sind. |Audit, Disabled |1.0.0-preview |[Link](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/Network/VirtualNetworkServiceEndpoint_ContainerRegistry_Audit.json) |
