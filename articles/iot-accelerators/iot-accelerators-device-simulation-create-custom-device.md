---
title: Erstellen eines benutzerdefinierten simulierten Geräts – Azure | Microsoft-Dokumentation
description: In diesem Tutorial erstellen Sie mithilfe der Gerätesimulation ein benutzerdefiniertes simuliertes Gerät für Simulationen.
author: troyhopwood
manager: timlt
ms.service: iot-accelerators
services: iot-accelerators
ms.topic: tutorial
ms.custom: mvc
ms.date: 10/25/2018
ms.author: troyhop
ms.openlocfilehash: 302b863e7ad7d6df286adf53342356f279ab92d2
ms.sourcegitcommit: 0947111b263015136bca0e6ec5a8c570b3f700ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "61450547"
---
# <a name="tutorial-create-a-custom-simulated-device"></a>Tutorial: Erstellen eines benutzerdefinierten simulierten Geräts

In diesem Tutorial erstellen Sie mithilfe der Gerätesimulation ein benutzerdefiniertes simuliertes Gerät für Simulationen. Zur Erleichterung des Einstiegs in die Gerätesimulation können Sie eines der enthaltenen exemplarischen simulierten Geräte verwenden. Sie können aber auch benutzerdefinierte simulierte Geräte erstellen, wie in diesem Artikel beschrieben. Informationen zu weiteren Anpassungsoptionen finden Sie unter [Create an advanced device model](iot-accelerators-device-simulation-advanced-device.md) (Erstellen eines erweiterten Gerätemodells).

In diesem Tutorial führen Sie Folgendes durch:

>[!div class="checklist"]
> * Anzeigen einer Liste Ihrer simulierten Gerätemodelle
> * Erstellen eines benutzerdefinierten simulierten Geräts
> * Klonen eines Gerätemodells
> * Löschen eines Gerätemodells

Wenn Sie kein Azure-Abonnement besitzen, erstellen Sie ein [kostenloses Konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), bevor Sie beginnen.

## <a name="prerequisites"></a>Voraussetzungen

Für dieses Tutorial benötigen Sie eine in Ihrem Azure-Abonnement bereitgestellte Instanz der Gerätesimulation.

Falls Sie die Gerätesimulation noch nicht bereitgestellt haben, absolvieren Sie zunächst die [Schnellstartanleitung zum Bereitstellen und Ausführen einer IoT-Gerätesimulation in Azure](quickstart-device-simulation-deploy.md).

## <a name="open-device-simulation"></a>Öffnen der Gerätesimulation

Um die Gerätesimulation in Ihrem Browser auszuführen, navigieren Sie zunächst zu [Azure IoT solution accelerators](https://www.azureiotsolutions.com) (Solution Accelerators für Azure IoT).

Sie werden unter Umständen aufgefordert, sich mit den Anmeldeinformationen Ihres Azure-Abonnements anzumelden.

Klicken Sie anschließend auf der Kachel für die Gerätesimulation, die Sie im Rahmen der **Schnellstartanleitung zum Bereitstellen und Ausführen einer IoT-Gerätesimulation in Azure** bereitgestellt haben, auf [Starten](quickstart-device-simulation-deploy.md).

## <a name="view-your-device-models"></a>Anzeigen Ihrer Gerätemodelle

Wählen Sie auf der Menüleiste die Option **Device models** (Gerätemodelle) aus. Auf der Seite **Device models** (Gerätemodelle) werden alle Geräte aufgeführt, die in dieser Instanz der Gerätesimulation verfügbar sind:

![Gerätemodelle](media/iot-accelerators-device-simulation-create-custom-device/devicemodelnav.png)

## <a name="create-a-device-model"></a>Erstellen eines Gerätemodells

Klicken Sie rechts oben auf der Seite auf **+ Add Device Models** (+ Gerätemodelle hinzufügen):

![Gerätemodell hinzufügen](media/iot-accelerators-device-simulation-create-custom-device/devicemodels.png)

In diesem Tutorial erstellen Sie einen simulierten Kühlschrank, der Temperatur- und Luftfeuchtigkeitsdaten sendet.

Füllen Sie das Formular mit den folgenden Informationen aus:

| Einstellung             | value                                                |
| ------------------- | ---------------------------------------------------- |
| Device model name (Name des Gerätemodells)   | Refrigerator                                         |
| Modellbeschreibung   | Einen Kühlschrank mit Temperatur- und Luftfeuchtigkeitssensoren |
| Version             | 1.0                                                  |

> [!NOTE]
> Der Name des Gerätemodells muss eindeutig sein.

Klicken Sie auf **+ Add data point** (+ Datenpunkt hinzufügen), um Datenpunkte für Temperatur und Luftfeuchtigkeit mit folgenden Werten hinzuzufügen:

| Datenpunkt          | Verhalten        | Mindestwert | Höchstwert | Einheit |
| ------------------- | --------------- | --------- | --------- | ---- |
| Temperatur         | Zufällig          | -50       | 100       | F    |
| Luftfeuchtigkeit            | Zufällig          | 0         | 100       | %    |

Klicken Sie auf **Speichern**, um das Gerätemodell zu speichern.

![Erstellen des Gerätemodells](media/iot-accelerators-device-simulation-create-custom-device/adddevicemodel.png)

Ihr Kühlschrank ist nun in der Liste der Gerätemodelle enthalten. Möglicherweise müssen Sie auf **Weiter** klicken, um zu einer anderen Seite zu wechseln, damit Ihr Kühlschrank angezeigt wird.

## <a name="clone-a-device-model"></a>Klonen eines Gerätemodells

Durch Klonen eines Gerätemodells können Sie eine Kopie eines vorhandenen Gerätemodells erstellen. Die Kopie kann dann bearbeitet und an Ihre spezifischen Anforderungen angepasst werden. Klonen spart Zeit, wenn Sie ähnliche Gerätemodelle erstellen möchten.

Wenn Sie ein Gerätemodell klonen möchten, aktivieren Sie das Kontrollkästchen neben dem Modell, und klicken Sie anschließend auf der Aktionsleiste auf **Klonen**:

![Löschen des Gerätemodells](media/iot-accelerators-device-simulation-create-custom-device/clonedevice.png)

## <a name="delete-a-device-model"></a>Löschen eines Gerätemodells

Sie können jedes benutzerdefinierte Gerätemodell löschen. Wenn Sie ein Gerätemodell löschen möchten, aktivieren Sie das Kontrollkästchen neben dem Modell, und klicken Sie anschließend auf der Aktionsleiste auf **Löschen**:

![Löschen des Gerätemodells](media/iot-accelerators-device-simulation-create-custom-device/deletedevice.png)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie Sie benutzerdefinierte Gerätemodelle erstellen, klonen und löschen. Weitere Informationen zu Gerätemodellen finden Sie in der folgenden Anleitung:

> [!div class="nextstepaction"]
> [Create an advanced device model](iot-accelerators-device-simulation-advanced-device.md) (Erstellen eines erweiterten Gerätemodells)