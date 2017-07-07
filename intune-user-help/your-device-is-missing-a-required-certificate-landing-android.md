---
title: Er ontbreekt een vereist certificaat voor uw apparaat | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 910fe2bc4e616c3b60d351efaffe173f58c04bc6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="your-device-is-missing-a-required-certificate"></a>Er ontbreekt een vereist certificaat voor uw apparaat

## <a name="whats-a-certificate"></a>Wat is een certificaat?

[Cryptografie](https://technet.microsoft.com/library/cc962030.aspx) is de wetenschap voor het beveiligen van informatie. Van oudsher wordt cryptografie gebruikt om gecodeerde berichten door te geven [om ervoor te zorgen dat de communicatie geheim blijft](https://technet.microsoft.com/library/cc962019.aspx). In de eenvoudigste vorm worden letters vervangen of omgezet om zodoende een onleesbaar, gecodeerd of verborgen bericht te maken. Alleen gebruikers met een ontsleutelingssleutel of _certificaat_ kunnen het gecodeerde bericht weer converteren naar de oorspronkelijke, leesbare vorm. Uw Android-apparaat maakt gebruik van certificaten voor Intune om ervoor te zorgen dat de communicatie tussen uw apparaat en organisatieresources, zoals e-mail en documenten, veilig van het ene apparaat naar het andere worden verzonden.

## <a name="fixing-certificate-issues"></a>Certificaatproblemen oplossen

Als uw Android-apparaat niet bij Intune is ingeschreven en er ontbreekt een bepaald certificaat dat door uw IT-beheerder wordt vereist, kunt u zich niet aanmelden bij de bedrijfsportal-app. Wanneer u zich probeert aan te melden, wordt het volgende bericht weergegeven:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

U moet eerst controleren of er een [certificaat op het apparaat ontbreekt dat doorgaans vooraf wordt geïnstalleerd](your-device-is-missing-a-preinstalled-certificate-android.md).

Als dit niet werkt, kan uw IT-beheerder [vereisen dat u een tweede certificaat voor extra beveiliging installeert](your-device-is-missing-an-IT-required-certificate-android.md).

Nog hulp nodig? Neem contact op met uw IT-beheerder. Ga naar de [bedrijfsportalwebsite](http://portal.manage.microsoft.com) voor de betreffende contactgegevens.
