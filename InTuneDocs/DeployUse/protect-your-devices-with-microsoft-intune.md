---
# required metadata

title: Apparaten beveiligen met Microsoft Intune | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apparaten beveiligen met Microsoft Intune
Wanneer uw apparaten worden beheerd door Intune, moet u ervoor zorgen dat deze zijn beschermd tegen onbevoegde toegang en andere dreigingen. Hier zijn enkele mogelijkheden van Intune waarmee u deze doelstellingen kunt bereiken.

> [!TIP]
> In dit onderwerp worden niet alle manieren besproken waarop Intune kan helpen bij de beveiliging van uw apparaten. U kunt bijvoorbeeld Intune-beleid gebruiken om veel beveiligingsinstellingen te configureren voor uw apparaten, zoals wachtwoorden, versleutelingsinstellingen en hardwarefuncties als Bluetooth en de camera van het apparaat. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor meer informatie over deze instellingen

## Toegangscodes opnieuw instellen wanneer de apparaten van gebruikers zijn vergrendeld
De eerste stap in het beveiligen van bedrijfsgegevens op mobiele apparaten is het vereisen van een wachtwoordcode om het apparaat te kunnen gebruiken. U zult daarom soms een [wachtwoordcode opnieuw moeten instellen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) of een medewerker moeten helpen om dit te doen door een wachtwoordcode te verwijderen of door op afstand een tijdelijke wachtwoordcode in te stellen. U kunt ook [een apparaat vergrendelen op afstand](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) als dit is zoekgeraakt of gestolen.

## Een extra beschermingslaag toevoegen aan Windows-apparaten
[Multi-Factor Authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) is een veiligere manier om de identiteit van gebruikers van Windows en Windows Phone-apparaten op het netwerk te verifiëren.  Met MFA moeten gebruikers hun identiteit buiten de gebruikersnaam en het wachtwoord bevestigen via een telefoongesprek of een tekstbericht.

## Microsoft Passport-instellingen op Windows-apparaten beheren
Intune biedt de mogelijk van integratie met [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Dit is een alternatieve aanmeldingsmethode voor Windows 10 en hoger, waarbij Active Directory of een Azure Active Directory-account wordt gebruikt ter vervanging van een wachtwoord, smartcard of virtuele smartcard.

## Windows-pc's beveiligen die door de Intune-client worden beheerd
Intune blijft ondersteuning bieden voor beveiligingsbeleid voor Windows-pc's die u niet registreert, maar met de clientsoftware van de Intune-computer beheert. Zie [Gebruik beleid voor het beveiligen van Windows-pc’s waarop de Intune-clientsoftware wordt uitgevoerd](policies-to-protect-windows-pcs-in-microsoft-intune.md) als u wilt weten hoe u dit beleid kunt gebruiken om uw Windows-pc's te beveiligen.


<!--HONumber=May16_HO1-->

