---
title: Apparaten synchroniseren met Microsoft Intune - Azure | Microsoft Docs
description: Synchroniseer apparaten die zijn geregistreerd bij of worden beheerd met Microsoft Intune om het meest recente beleid en de meest recente acties te verkrijgen. Bevat de stappen die moeten worden uitgevoerd om te synchroniseren via Azure Portal en bevat de codes van fouten waarvoor opnieuw een poging kan worden gedaan.
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d2d13ce2ed06549a6cd09fd766a0072b15fcd067
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions---intune"></a>Apparaten synchroniseren om het meest recente beleid en de meest recente acties te verkrijgen - Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met apparaatactie **Synchroniseren** wordt het geselecteerde apparaat direct ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die erop zijn toegepast. Met deze functie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Een apparaat synchroniseren

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**. 
3. In **Intune** selecteert u **Apparaten** en vervolgens **Alle apparaten**.
4. Kies een apparaat in de lijst met apparaten die u beheert en kies vervolgens **...Meer**. Selecteer vervolgens de actie **Synchroniseren**.
5. Selecteer **Ja** om te bevestigen.


## <a name="retryable-error-codes"></a>Codes van fouten waarvoor een nieuwe poging kan worden gedaan

Wanneer een beheerder de apparaatactie **Synchroniseren** uitvoert, zijn iOS- en Android-apps waarbij de actie is mislukt, maar waarbij een foutcode is gegenereerd waarin is aangegeven dat een nieuwe poging kan worden gedaan, nog altijd beschikbaar voor het apparaat. Apps waarbij een foutcode is gegenereerd waarin is aangegeven dat er geen nieuwe poging kan worden gedaan, kunnen pas na zeven dagen weer beschikbaar worden gemaakt voor het apparaat.


| Foutcode  | Voorgestelde beschrijving | Er kan een nieuwe poging worden gedaan |
|---|---|---|
| 2016330898 | Er is een onbekende fout opgetreden. | Nee |
| 2016330897 | Er is een time-out opgetreden voor de verbinding met Intune. Stel de verbinding opnieuw in. | Ja |
| 2016330896 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja |
| 2016330895 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja |
| 2016330894 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja |
| 2016330893 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja|
| 2016330892 | Internationale roaming is uitgeschakeld. | Nee|
| 2016330891 | De mobiele gegevensverbinding vor dit apparaat kan niet worden gebruikt terwijl er wordt gebeld. Wacht tot het gesprek is beëindigd. | Ja|
| 2016330890 | Het mobiele netwerk voor dit apparaat. Deze apparaten kunnen momenteel niet worden gebruikt. | Nee|
| 2016330889 | De beveiligde verbinding is mislukt. Stel de verbinding opnieuw in. | Ja|
| 2016330888 | De evaluatie van de vertrouwelijke server is mislukt. | Nee|

## <a name="next-step"></a>Volgende stap

Kies **Apparaatacties** om de status van de synchronisatieactie te zien. 
