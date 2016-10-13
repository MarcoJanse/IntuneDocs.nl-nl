---
title: De regel Device Threat Protection inschakelen in het nalevingsbeleid | Microsoft Intune
description: De regel Mobile Threat Protection inschakelen in het nalevingsbeleid van het apparaat.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fa05027e1785bb27a607aa9e31b685107a84f63f
ms.openlocfilehash: 3de68238515a2584b6f1a5785e13688097468415


---

# De regel Device Threat Protection inschakelen in het nalevingsbeleid
Met Intune en Lookout Mobile Threat Protection kunt u mobiele bedreigingen detecteren en een risicoanalyse maken op het apparaat. U kunt een nalevingsbeleidsregel maken om de risicoanalyse mee te nemen bij het bepalen of het apparaat compatibel is. Vervolgens kunt u het beleid voor voorwaardelijke toegang gebruiken om toegang tot Exchange, SharePoint en andere services toe te staan of te blokkeren op basis van de apparaatcompatibiliteit.

Als de bedreigingsdetectie van Lookout MTP van invloed moet zijn op het nalevingsbeleid voor het apparaat:

* De regel **Device Threat Protection** moet zijn ingeschakeld in het nalevingsbeleid.

* De status op de pagina **Lookout-status** in de **Intune-beheerconsole** moet **Actief** zijn. Zie het onderwerp [Lookout MTP-verbinding in Intune inschakelen](enable-lookout-mtp-connection-in-intune.md) voor meer informatie en instructies over het activeren van de Lookout-integratie.


Voordat u de regel Device Threat Protection maakt in het nalevingsbeleid, raden we u aan uw [abonnement in te stellen met Lookout MTP](set-up-your-subscription-with-lookout-mtp.md), de [Lookout-verbinding in Intune in te schakelen](enable-lookout-mtp-connection-in-intune.md) en de [Lookout for Work-app te configureren](configure-and-deploy-lookout-for-work-apps.md). De nalevingsregel wordt pas afgedwongen nadat de installatie is voltooid.

Als u de Device Threat Protection-regel wilt inschakelen, kunt u een bestaand nalevingsbeleid gebruiken of een nieuw beleid maken.

Als onderdeel van de configuratie van Lookout MTP in de [Lookout MTP-console](https://aad.lookout.com) hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. In het nalevingsbeleid van Intune stelt u met het bedreigingsniveau het maximaal toegestane bedreigingsniveau in.

Ga op de pagina **Nalevingsbeleid** van de **Intune-beheerconsole** naar **Apparaatstatus** en schakel de regel **Device Threat Protection** in met de wisselknop. Selecteer vervolgens het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:
* **Geen (beveiligd)**: dit is het meest veilige niveau.  Dit betekent dat er op het apparaat geen bedreigingen mogen staan.  Als er bedreigingen van welk niveau dan ook worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.  
* **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
* **Gemiddeld**: Het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.
* **Hoog**: dit is de minst veilige optie. Het komt erop neer dat alle bedreigingsniveaus worden toegestaan. Dit is mogelijk alleen nuttig als u deze oplossing slechts voor rapportagedoeleinden gebruikt.

![schermopname met de instelling voor de regel Device Threat Protection ](../media/mtp/mtp-compliance-policy-rule.png)

![schermopname met de optie voor het bedreigingsniveau voor de instelling voor de regel Device Threat Protection](../media/mtp/mtp-compliance-policy-setting.png)

Als u beleid voor voorwaardelijke toegang voor Office 365 en andere services maakt, wordt bovenstaande compatibiliteitsevaluatie in acht genomen en wordt niet-compatibele apparaten de toegang tot bedrijfsresources geweigerd tot de bedreiging is opgelost.

U kunt de compatibiliteitsstatus van een apparaat bekijken op de pagina **Alle apparaten** van de **Intune-beheerconsole**.

![schermopname van de pagina Apparaten in de Intune-beheerconsole waarop de compatibiliteitsstatus van een apparaat is weergeven](../media/mtp/mtp-device-status-intune-console.png)

## Volgende stappen
* Beleid voor voorwaardelijke toegang maken
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype voor Bedrijven Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->

