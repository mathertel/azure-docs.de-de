---
title: Leitfaden für die Veröffentlichung von VM-Angeboten für Azure Marketplace
description: Dieser Artikel beschreibt die Anforderungen zum Veröffentlichen einer VM und einer kostenlosen Softwaretestversion, die auf dem Marketplace bereitgestellt werden.
services: Azure, Marketplace, Compute, Storage, Networking, Blockchain, Security
author: dsindona
ms.service: marketplace
ms.subservice: partnercenter-marketplace-publisher
ms.topic: conceptual
ms.date: 04/15/2020
ms.author: dsindona
ms.openlocfilehash: 2fa67d81546db86535c179a9c59d0602c1175cba
ms.sourcegitcommit: 849bb1729b89d075eed579aa36395bf4d29f3bd9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "81687493"
---
# <a name="virtual-machine-offer-publishing-guide"></a>Leitfaden für die Veröffentlichung von VM-Angeboten

VM-Images zählen zu den wichtigsten Verfahren, eine Lösung im Azure Marketplace zu veröffentlichen. Informieren Sie sich in diesem Handbuch über die Anforderungen für dieses Angebot. 

Hierbei handelt es sich um Transaktionsangebote, die über den Marketplace bereitgestellt und abgerechnet werden. Die Benutzer sehen hier den Aktionsaufruf „Jetzt kaufen“.

## <a name="free-trial"></a>Kostenlose Testversion 

Wenn Sie das Abrechnungsmodell Bring-Your-Own-License (BYOL) verwenden, können Sie Benutzern das Testen Ihres Angebots mit befristeten Softwarelizenzen ermöglichen. 

## <a name="test-drive"></a>Testversion

Sie stellen mindestens eine VM über IaaS- oder SaaS-Apps bereit (Infrastructure-as-a-Service bzw. Software-as-a-Service). Ein Vorteil der Testversion-Veröffentlichungsoption ist die automatische Bereitstellung einer VM oder einer gesamten Lösung mit einer von einem Partner gehosteten geführten Tour. Eine Testversion stellt Ihrem Kunden eine Bewertung ohne Zusatzkosten zur Verfügung. Ihr Kunde muss nicht bereits Azure-Kunde sein, um die Testversion zu nutzen. 

Für erste Schritte kontaktieren Sie uns unter [amp-testdrive](mailto:amp-testdrive@microsoft.com). 

|Requirements (Anforderungen)  |Details |
|---------|---------|
| Sie verfügen über eine Marketplace-App   |    Mindestens eine VM über IaaS oder SaaS.      |

## <a name="interactive-demo"></a>Interaktive Demo

Mit einer interaktiven Demo bieten Sie Ihren Kunden eine geführte Einführungen in Ihr Produkt. Der Vorteil der Veröffentlichungsoption der interaktiven Demo ist, dass Sie ohne komplizierte Bereitstellung für komplexe Lösungen eine Testversion bieten können. 

## <a name="virtual-machine-offer"></a>VM-Angebot

Verwenden Sie den VM-Angebotstyp beim Bereitstellen einer virtuellen Appliance für das Abonnement Ihres Kunden. VMs können vollständig kommerziell genutzt werden und verwenden nutzungsbasierte oder Bring-Your-Own-Licence-Lizenzierungsmodelle (BYOL). Microsoft hostet die kommerzielle Transaktion und führt für Sie die Abrechnung mit Ihrem Kunden durch. Sie haben den Vorteil, dass Sie die bevorzugte Zahlungsmethoden zwischen Ihrem Kunden und Microsoft, einschließlich des Enterprise Agreements, nutzen können.

> [!NOTE]
> Zu diesem Zeitpunkt können die finanziellen Verpflichtungen des Enterprise Agreements für die Azure-Nutzung Ihrer VM, nicht aber für Ihre Softwarelizenzgebühren verwendet werden.  
> 
> [!NOTE]
> Sie können die Ermittlung und Bereitstellung Ihrer VM auf eine bestimmte Gruppe von Kunden beschränken, indem Sie das Image und die Preise als privates Angebot veröffentlichen. Durch private Angebote haben Sie die Möglichkeit, exklusive Angebote für Ihre besten Kunden zu erstellen und benutzerdefinierte Software und Bestimmungen für sie anzubieten. Benutzerdefinierte Bestimmungen ermöglichen Ihnen die Schaffung vielfältiger Szenarios, wie etwa vom Vertrieb erzielte Geschäftsabschlüsse mit Sonderpreisen und -bestimmungen sowie ein frühzeitiger Zugang zu Software, die in limitierter Anzahl veröffentlicht wird. Durch private Angebote können Sie Sonderpreise oder -produkte für eine begrenzte Anzahl von Kunden anbieten, indem Sie eine neue SKU mit diesen Konditionen erstellen.  
> *   Weitere Informationen zu privaten Angeboten finden Sie auf der Seite für private Angebote in Azure Marketplace unter [azure.microsoft.com/blog/private-offers-on-azure-marketplace](https://azure.microsoft.com/blog/private-offers-on-azure-marketplace).  

| Anforderung | Details |  
|:--- |:--- | 
| Abrechnung und Messung | Ihre VM muss entweder BYOL oder die monatliche nutzungsbasierte Bezahlung unterstützen. |  
| Azure-kompatible virtuelle Festplatte (VHD) | VMs müssen unter Windows oder Linux erstellt werden. <ul> <li>Weitere Informationen zum Erstellen einer Linux-VHD finden Sie unter [Von Azure unterstützte Distributionen von Linux](https://docs.microsoft.com/azure/virtual-machines/linux/endorsed-distros).</li> <li>Weitere Informationen zum Erstellen einer Windows-VHD finden Sie unter [Erstellen einer Azure-kompatiblen VHD](./partner-center-portal/azure-vm-create-offer.md).</li> </ul> |  

>[!Note]
>Die Nutzung des CSP-Partnerkanals (Cloud Solution Provider) ist jetzt verfügbar.  Unter [Cloud Solution Providers](./cloud-solution-providers.md) finden Sie weitere Informationen zum Vermarkten Ihres Angebots über die Microsoft CSP-Partnerkanäle.

## <a name="next-steps"></a>Nächste Schritte

Falls Sie dies noch nicht getan haben, 

- [Erfahren Sie mehr](https://azuremarketplace.microsoft.com/sell) über den Marketplace.

Wenn Sie registriert sind und ein neues Angebot erstellen oder an einem vorhandenen arbeiten,

- [Melden Sie sich bei Partner Center an](https://partner.microsoft.com/dashboard/account/v3/enrollment/introduction/partnership), um Ihr Angebot zu erstellen oder abzuschließen.
- Weitere Informationen finden Sie unter [Erstellen eines VM-Angebots](./partner-center-portal/azure-vm-create-offer.md).
