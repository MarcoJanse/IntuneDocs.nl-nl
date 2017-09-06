---
title: Office 365 Exchange Online beveiligen zonder dat apparaatbeheer is vereist
description: Geef werknemers toegang tot hun werk-e-mail. Geen beheeragent vereist.
keywords: Toegang tot e-mail van Office 365 Exchange
author: arob98
manager: angrobe
ms.date: 08/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3e27f8ae8b42617f73d44fdf128772204f1963ed
ms.sourcegitcommit: 86687a8272ee3269aa7330e85022661b20450059
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2017
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Office 365 Exchange Online beveiligen zonder dat apparaatbeheer is vereist

U kunt werknemers toegang geven tot hun werk-e-mail zonder de overhead van het instellen van een apparaatbeheersysteem. U kunt toegang tot Office 365 Exchange Online geven via Intune. Bevestig dat u licenties hebt voor Microsoft 365 of voor Azure Active Directory (premium) en Intune om de benodigde stappen te voltooien. Werknemers moeten beschikken over een [ondersteund iOS- of Android-apparaat](supported-devices-browsers.md). 

Als u een apparaatbeheersysteem wilt instellen, is dat mogelijk. Dit type app-beveiliging werkt onafhankelijk van apparaatbeheer. 

## <a name="action-plan"></a>Actieplan

1. [Meer informatie over voorwaardelijke toegang](conditional-access.md). 
2. [Meer informatie over voorwaardelijke toegang op basis van apps](app-based-conditional-access-intune.md).
3. [Beleid voor voorwaardelijke toegang op basis van apps instellen voor Exchange Online](app-based-conditional-access-intune-create.md).
4. [Blokkeer apps die niet kunnen worden beheerd](app-modern-authentication-block.md), met name apps die geen gebruik maken van de Azure Active Directory Authentication Library (ADAL).
5. (Optioneel) [Beleid voor voorwaardelijke toegang op basis van apps instellen voor SharePoint Online](app-based-conditional-access-intune-create.md). Deze beleidsregels blokkeren de toegang tot uw bedrijfsgegevens vanuit apps die niet kunnen worden beheerd en beveiligd. Dit beleid beperkt bovendien de toegang via mobiele SharePoint. 

## <a name="what-to-tell-employees-and-students"></a>Wat u werknemers en leerlingen/studenten over Intune kunt vertellen

* Vraag uw werknemers en leerlingen/studenten om Microsoft Outlook of Microsoft SharePoint voor iOS te downloaden en installeren vanuit de Apple App Store of voor Android vanuit Google Play. 
* Als u de toegang blokkeert tot apps die geen moderne authenticatie gebruiken, stel de werknemers en leerlingen/studenten dan op de hoogte van deze beperking. 

## <a name="next-steps"></a>Volgende stappen

U hebt voorwaardelijke toegang op basis van apps gebruikt om de beveiliging van bedrijfsgegevens te verbeteren. Bij de volgende stappen krijgt u meer informatie over andere manieren waarop u de beveiliging van uw bedrijfsgegevens kunt verbeteren, met inbegrip van: 

* Instellen van [voorwaardelijke toegang op basis van apparaatcompatibiliteit, apparaatrisico, locatie en gebruikerskenmerken in Active Directory en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).  
* Instellen van app-beveiligingsbeleid om uw bedrijfsgegevens te beschermen tegen opzettelijke en niet-opzettelijke gegevenslekken. 
* Gebruik van Azure Information Protection om bedrijfsgegevens buiten uw netwerk te beveiligen. 

Wilt u hulp bij het inschakelen van dit of andere scenario's voor EMS of Office 365? Als u ten minste 150 licenties voor Microsoft 365, Enterprise Mobility + Security of Azure Active Directory Premium hebt, gebruikt u uw [FastTrack-voordelen](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 