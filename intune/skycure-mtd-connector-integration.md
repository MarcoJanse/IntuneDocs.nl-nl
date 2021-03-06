---
title: Integratie van Skycure met Microsoft Intune instellen
titlesuffix: 
description: Meer informatie over hoe u de Skycure Mobile Threat Defense (MTD) -oplossing instelt met Microsoft Intune om toegang tot uw bedrijfsbronnen met mobiele apparaten te beheren.
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a09806afae72f60961a94ab27707b4851006cf0
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-the-skycure-integration-with-intune"></a>De integratie van Skycure met Intune instellen

Voer de volgende stappen uit om de Skycure Mobile Threat Defense-oplossing te integreren met Intune. U moet Skycure-apps in Azure AD toevoegen om gebruik te kunnen maken van eenmalige aanmelding.

## <a name="before-you-begin"></a>Voordat u begint

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Het Azure AD-account dat wordt gebruikt voor de integratie van Intune en Skycure

-   Zorg ervoor dat het Azure AD-account juist is geconfigureerd in de [Skycure-beheerconsole](https://aad.skycure.com), voordat u met de eenvoudige integratie van Skycure begint.

### <a name="full-integration-vs-read-only"></a>Volledige integratie tegenover een integratie met alleen-lezen

Skycure ondersteunt twee modi van integratie met Intune:

-   **Integratie met alleen-lezen (eenvoudige integratie):** hierbij worden alleen apparaten uit Azure Active Directory geïnventariseerd en wordt de Skycure-console hiermee gevuld.
<br>
    -   Als de selectievakjes **Report the health and risk of devices to Intune** en **Also report security incidents to Intune**  niet zijn ingeschakeld in de Skycure-beheerconsole, is er sprake van een integratie met alleen-lezen. Bij een dergelijke integratie wordt de status van een apparaat (compatibel of niet-compatibel) nooit gewijzigd in Intune.
<br></br>
-   **Volledige integratie:** stelt Skycure in staat om risico- en beveiligingsincidentgegevens voor apparaten aan Intune te melden. Hierbij wordt een tweerichtingscommunicatie tussen beide cloudservices tot stand gebracht.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Hoe worden de Skycure-apps gebruikt bij Azure AD en Intune?

-   **iOS-app:** stelt eindgebruikers in staat om zich bij Azure AD aan te melden met een iOS-app.

-   **Android-app:** stelt eindgebruikers in staat om zich bij Azure AD aan te melden met een Android-app.

-   **Beheerapp:** dit is de Skycure Azure AD-app voor meerdere tenants die communicatie tussen services met Intune mogelijk maakt.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>De integratie met alleen-lezen tussen Intune en Skycure instellen

> [!IMPORTANT]
> De Skycure-beheerdersreferenties bestaan uit een e-mailaccount dat een geldige gebruiker moet zijn in Azure Active Directory. Als dat niet het geval is, mislukt de aanmelding. Skycure maakt gebruik van Azure Active Directory om deze beheerder te verifiëren door middel van eenmalige aanmelding.

1.  Ga naar de [Skycure-beheerconsole](https://aad.skycure.com).

2.  Voer uw **Skycure-beheerdersreferenties** in en klik vervolgens op **Doorgaan**.

3.  Ga naar **Instellingen**, kies onder **Intune-integratie** de optie **Eenvoudige integratie**.

4.  Klik op het label **iOS-app** op **Aan Active Directory toevoegen**.

    ![Afbeelding van iOS-app in de Skycure-beheerconsole](./media/skycure-setup-1.png)

5.  Wanneer de aanmeldingspagina wordt geopend, voert u uw Intune-referenties in en klikt u vervolgens op **Accepteren**.

    ![Afbeelding van de aanmeldingsprompt in Intune voor iOS-app](./media/skycure-setup-2.png)

6.  Wanneer de app aan Azure AD is toegevoegd, wordt in de Skycure-beheerconsole aangegeven dat de app aan Azure AD is toegevoegd.

    ![Afbeelding van het voltooiingsscherm voor iOS-app](./media/skycure-setup-3.png)

> [!NOTE]
> Herhaal dezelfde procedure voor de **Android-app voor Skycure** en de **beheerapp**.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Een Azure AD-beveiligingsgroep toevoegen aan Skycure

U moet een Azure AD-beveiligingsgroep toevoegen met alle apparaten waarop Skycure wordt uitgevoerd.

-  Voer alle beveiligingsgroepen met apparaten waarop Skycure wordt uitgevoerd in en selecteer deze. Klik vervolgens op **Wijzigingen toepassen**.

    ![Afbeelding waarin u ziet waar u de beveiligingsgroep configureert in de Skycure-beheerconsole](./media/skycure-setup-4.png)

Met Skycure worden apparaten met de Mobile Threat Defense-service gesynchroniseerd met de Azure AD-beveiligingsgroepen.

![Afbeelding van de beveiligingsgroepconfiguratie in de Skycure-beheerconsole die is voltooid](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>De volledige integratie tussen Intune en Skycure instellen

1.  Ga naar de [Skycure-beheerconsole](https://aad.skycure.com).

2.  Voer uw **Skycure-beheerdersreferenties** in en klik vervolgens op **Doorgaan**.

3.  Ga naar **Instellingen**, kies onder **Intune-integratie** de optie **Volledige integratie**.

4.  Controleer de volgende instellingen:

    a.  De status en het risico van het apparaat melden aan Intune

    b.  Ook beveiligingsincidenten melden aan Intune

5.  Klik op **Wijzigingen toepassen**.

    ![Afbeelding van de volledige integratie van Skycure die is voltooid](./media/skycure-setup-6.png)

## <a name="next-steps"></a>Volgende stappen

[Skycure-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
