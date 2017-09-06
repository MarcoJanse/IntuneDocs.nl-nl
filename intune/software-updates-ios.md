---
title: Updatebeleid voor iOS configureren
titleSuffix: Intune on Azure
description: "Configureer updatebeleid voor iOS zodat de nieuwste software-update automatisch wordt geïnstalleerd door iOS-apparaten die onder supervisie staan."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: d4af2d58ec21c54362cf451eac1a33b2088885d5
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2017
---
# <a name="configure-ios-update-policies"></a>Updatebeleid voor iOS configureren
Dankzij updatebeleid voor iOS kan de nieuwste software-update automatisch worden geïnstalleerd door iOS-apparaten die onder supervisie staan. U kunt dagen en tijdstippen instellen waarop u niet wilt dat de update wordt geïnstalleerd.

## <a name="configure-the-ios-update-policy"></a>Updatebeleid voor iOS configureren
1. Ga naar de Intune-blade in Azure Portal.
2. Kies **Software-updates** > **Updatebeleid voor iOS** op de blade **Intune**.
4. Kies op de blade voor beleid de optie **Maken** en voer een naam en beschrijving voor het beleid in.
5. Selecteer **Instellingen** > **Configureren** en voer de details in voor het geval waarbij iOS-apparaten niet worden gedwongen de meest recente update te installeren.
6. Kies **OK** om deze configuratie op te slaan. U bent nu terug in de blade **Updatebeleid maken**. Kies **Maken** om het beleid te maken en uw instellingen op te slaan.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de lijst met updatebeleidsregels voor iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Updatebeleid voor iOS aan gebruikers toewijzen
Als u een updatebeleid voor iOS aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. U kunt bestaande beleidsregel vinden on de blade **Software-updates** > **Updatebeleid voor iOS**.
1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u de blade waar u Azure Active Directory-beveiligingsgroepen kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Groepen selecteren** om de blade met de Azure AD-beveiligingsgroepen te openen. Kies **Selecteren** om het beleid voor gebruikers te implementeren.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving.

## <a name="change-the-restricted-days-for-the-policy"></a>De dagen met beperkingen voor het beleid wijzigen
1. Kies op de blade **Software-updates** de optie **Updatebeleid voor iOS**.
2. Selecteer het updatebeleid voor iOS dat u wilt bijwerken.
3. Selecteer **Eigenschappen** en werk de gegevens voor de dagen met beperkingen bij.