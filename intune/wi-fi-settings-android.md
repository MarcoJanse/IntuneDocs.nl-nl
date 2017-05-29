---
title: Wi-Fi-instellingen voor Android-apparaten in Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over de Intune-instellingen die u kunt gebruiken om Wi-Fi-verbindingen op Android-apparaten te configureren.'
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 0dd0b8c4e4cf6733c20282817cba99d8379ef24e
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="wi-fi-settings-for-android-devices-in-microsoft-intune"></a>Wi-Fi-instellingen voor Android-apparaten in Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Wi-Fi-instellingen voor basis- en ondernemingsprofielen

- **Netwerknaam**: voer een naam voor deze Wi-Fi-verbinding in. Dit is de naam die gebruikers te zien krijgen in de lijst met beschikbare verbindingen op hun apparaat.
- **SSID**: afkorting voor Service Set Identifier. Dit is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hierboven hebt gemaakt, wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: als u deze optie kiest, maakt het apparaat verbinding wanneer het zich in het bereik van dit netwerk bevindt.
- **Verborgen netwerk**: hiermee wordt voorkomen dat dit netwerk wordt weergegeven in de lijst met beschikbare netwerken op het apparaat.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Wi-Fi-instellingen voor alleen ondernemingsprofielen

- **EAP-type**: kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt om beveiligde draadloze verbindingen te verifiëren. U kunt kiezen uit:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Overige opties wanneer u een EAP-type kiest

#### <a name="server-trust"></a>Vertrouwelijke server



|Naam van de instelling|Meer informatie|Wanneer gebruiken|
|-------------|---------------|-----------|
|**Namen van certificaatservers**|Geef een of meer algemene namen op die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Als u deze informatie verstrekt, kunt u het dialoogvenster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van eindgebruikers als zij verbinding maken met dit Wi-Fi-netwerk.|EAP-type is **EAP-TLS** of **EAP-TTLS**|
|**Basiscertificaat voor servervalidatie**|Kies het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. |EAP-type is **EAP-TLS**, **EAP-TTLS** of **PEAP**|
|**Identiteitsprivacy (externe identiteit)**|Geef de tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|EAP-type is **PEAP**|


#### <a name="client-authentication"></a>Clientverificatie


|Naam van de instelling|Meer informatie|Wanneer gebruiken|
|----------|--------------|----------|
|**Clientcertificaat voor clientverificatie (identiteitscertificaat)**|Kies het SCEP- of PKCS-certificaatprofiel dat wordt gebruikt om de verbinding te verifiëren.|EAP-type is **EAP-TLS**|
|**Verificatiemethode**|Selecteer de verificatiemethode voor de verbinding:<br>- **Certificaten** om het SCEP- of PKCS-clientcertificaat te selecteren dat het identiteitscertificaat is dat aan de server wordt gepresenteerd.<br><br>- **Gebruikersnaam en wachtwoord** om een andere verificatiemethode op te geven. <br><br>Als u **Gebruikersnaam en wachtwoord** hebt geselecteerd, configureert u het volgende:<br><br>-  **Niet-EAP-methode (interne identiteit)** en selecteer vervolgens hoe u de verbinding verifieert. Kies uit het volgende:<br>- **Geen**<br>- **Niet-versleuteld wachtwoord (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP versie 2 (MS-CHAP v2)**<br>De beschikbare opties zijn afhankelijk van het geselecteerde EAP-type.<br><br>**en**<br><br>- **Identiteitsprivacy (externe identiteit)**: geef de tekst op die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|EAP-type is **EAP-TTLS** of **PEAP**|
