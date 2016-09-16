---
title: Apparaten registreren | Microsoft Intune
description: Mobile Device Management (MDM) maakt gebruik van inschrijving om apparaten onder beheer te brengen en toegang tot resources toe te staan.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a7a0f834df939432910e32e6e635a70f021b37a9
ms.openlocfilehash: 63405b43609eda515656ad397c5c7ff4253a8167


---

# Apparaten inschrijven bij Intune voor beheer
Mobile Device Management (MDM) van Microsoft Intune maakt gebruik van inschrijving om apparaten onder beheer te brengen en toegang tot bronnen toe te staan. De manier waarop u apparaten inschrijft, is afhankelijk van het apparaattype, het eigendom en het benodigde beheerniveau. 'Bring your own device'-scenario’s (BYOD-scenario’s) en scenario’s met apparaten die bedrijfseigendom zijn (COD, company-owned device), vereisen een inschrijvingsproces. Organisaties die Exchange ActiveSync gebruiken, lokaal of gehost in de cloud, kunnen lichter beheer zonder inschrijvingsvereisten toepassen. Windows-pc's kunnen ook worden beheerd met Intune-clientsoftware.

Zie [Kiezen hoe u apparaten inschrijft](/intune/get-started/choose-how-to-enroll-devices1) voor hulp.

###  Ondersteunde apparaatplatformen

Met Intune kunnen de volgende apparaatplatformen worden beheerd:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Instantie voor beheer van mobiele apparaten instellen
De MDM-instantie definieert de beheerservice die gemachtigd is voor het beheren van een reeks apparaten. De opties voor de MDM-instantie bevatten Intune zelf en Configuration Manager met Intune. Als u Configuration Manager als beheerinstantie instelt, kunnen er geen andere services voor het Mobile Device Management worden gebruikt.

>[!IMPORTANT]
> Overweeg zorgvuldig of u mobiele apparaten wilt beheren met Intune alleen (onlineservice) of met System Center Configuration Manager met Intune (on-premises softwareoplossing in combinatie met de onlineservice). Nadat de instantie voor het Mobile Device Management is ingesteld, kan deze niet meer worden gewijzigd.

1.  Kies in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management**.

2.  Klik in de lijst **Taken** op **Instantie voor beheer van mobiele apparaten instellen**. Het dialoogvenster **Instantie voor beheer van mobiele apparaten instellen** wordt geopend.

    ![Het dialoogvenster Instantie voor Mobile Device Management instellen](../media/intune-mdm-authority.png)

3.  Intune vraagt u te bevestigen dat u Intune wilt gebruiken als uw MDM-instantie. Schakel het selectievakje in en kies vervolgens **Ja** als u mobiele apparaten wilt beheren met Microsoft Intune.

## De Intune-bedrijfsportal configureren

De Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken.

> [!TIP]
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal.

Een aangepaste bedrijfsportal geeft uw eindgebruikers een vertrouwde en efficiënte ervaring. Hiervoor hoeft u zich enkel als tenant of servicebeheerder aan te melden bij de [Microsoft Intune-beheerconsole](https://manage.microsoft.com), **Beheerder**&gt;**Bedrijfsportal** te kiezen en de instellingen van de bedrijfsportal te configureren.

![beheerconsole-beheerder-werkruimte-comp-portalinstellingen](../media/cp_sa_cpsetup.PNG)

## Overzicht van registratiemethoden voor apparaten

De volgende tabel bevat registratiemethoden voor apparaten in bedrijfseigendom met hun voordelen.

**iOS-registratiemethoden**

| **Methode** |  **[Wissen](#Wipe)** | **[Affiniteit](#Affinity)**   |   **[Vergrendeld](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nee|    Ja |   Nee |
|**[DEM](#DEM)**|   Nee |Nee |Nee  |
|**[DEP](#DEP)**|   Ja |   Opt |   Opt|
|**[USB-SA](#USB-SA)**| Ja |   Opt |   Nee|
|**[USB-Direct](#USB-Direct)**| Nee |    Nee  | Nee|

**Windows- en Android-registratiemethoden**

| **Methode** |  **[Wissen](#Wipe)** | **[Affiniteit](#Affinity)**   |   **[Vergrendeld](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nee|    Ja |   Nee |
|**[DEM](#DEM)**|   Nee |Nee |Nee  |

**Registratiemethoden voor apparaten**

### BYOD
Bring Your Own Device. Gebruikers installeren de bedrijfsportal-app en registreren hun apparaat. Als een apparaat met de bedrijfsportal wordt geregistreerd, wordt het apparaat toegevoegd aan de werkplek. Voor de registratie van iOS-apparaten met de bedrijfsportal is een Apple-id vereist. BYOD vereist geen aanvullende configuratie voor apparaten in bedrijfseigendom. Zie de stappen voor het [instellen van apparaatbeheer](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### DEM
Apparaatregistratiebeheer. De beheerder maakt DEM-accounts om apparaten in bedrijfseigendom te beheren. Beheerders kunnen vervolgens Bedrijfsportal installeren en veel apparaten zonder gebruiker registreren. Meer informatie over [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### DEP
Apple Device Enrollment Program. De beheerder maakt en implementeert het beleid draadloos op iOS-apparaten van het bedrijf die zijn gekocht en beheerd met DEP. Het apparaat wordt geregistreerd wanneer iOS-Configuratieassistent wordt uitgevoerd. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  - Vergrendelde registratie
  - Voorwaardelijke toegang
  - Jailbreakdetectie
  - Beheer van mobiele toepassingen

Meer informatie over [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### USB-SA
Door USB verbonden registratie met Configuratieassistent. De beheerder maakt een Intune-beleid en exporteert het beleid naar Apple Configurator. Door USB verbonden apparaten van het bedrijf worden voorbereid met Intune-beleid. De beheerder moet elk apparaat handmatig registreren. Gebruikers ontvangen hun apparaten en voeren Configuratieassistent uit om hun apparaat te registreren. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  - Voorwaardelijke toegang
  - Jailbreakdetectie
  - Beheer van mobiele toepassingen

Meer informatie over [Setup Assistant enrollment with Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (Registratie met Configuratieassistent met Apple Configurator). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### USB-Direct
Directe registratie. De beheerder maakt een Intune-beleid en exporteert het beleid naar Apple Configurator. Door USB verbonden apparaten van het bedrijf worden direct geregistreerd zonder dat de fabrieksinstellingen hoeven worden hersteld. De beheerder moet elk apparaat handmatig registreren. De apparaten worden beheerd als apparaten zonder gebruiker. Ze zijn niet vergrendeld of onder supervisie en kunnen geen voorwaardelijke toegang, jailbreakdetectie en beheer van mobiele toepassingen ondersteunen. Meer informatie over [directe registratie met Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

**Gedrag voor mobiele apparaten in bedrijfseigendom**

### Wissen
Hiermee geeft u op of bij registratie van het apparaat de fabrieksinstellingen moeten worden hersteld, of alle gegevens van het apparaat moeten worden verwijderd en of de oorspronkelijke staat van het apparaat moet worden hersteld.
[Buiten gebruik stellen van apparaten](retire-devices-from-microsoft-intune-management.md) ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### Affiniteit
Hiermee geeft u op of de registratiemethode ondersteuning biedt voor Gebruikersaffiniteit waarmee een apparaat met een specifieke gebruiker wordt verbonden. Opt-apparaten kunnen worden geregistreerd met of zonder gebruikersaffiniteit. Gebruikersaffiniteit is vereist voor de ondersteuning van het volgende:
  - MAM-apps (Mobile Application Management)
  - Voorwaardelijke toegang tot e-mail en bedrijfsgegevens
  - Bedrijfsportal-app

[Gebruikersaffiniteit](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices) ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### Vergrendelen
Hiermee geeft u op of het apparaat kan worden vergrendeld om te voorkomen dat de gebruiker het Intune-beleid verwijdert en dus het apparaat niet meer wordt beheerd. Voor iOS-apparaten vereist vergrendeling van het apparaat dat de modus Onder supervisie actief is.
([Terug naar de tabel](#overview-of-device-enrollment-methods))

## Apparaatinschrijving inschakelen  
 Dankzij inschrijving kunnen gebruikers toegang krijgen tot bedrijfsbronnen op hun eigen apparaten en kan de beheerder ervoor zorgen dat die apparaten de beleidsregels naleven die de bedrijfsbronnen beveiligen. Dit is de beste manier om met Intune 'Bring Your Own Device'-scenario's te ondersteunen. De beheerder moet inschrijving in de Intune-console inschakelen, waarvoor mogelijk het maken van een vertrouwensrelatie met het apparaat is vereist en licenties aan gebruikers moeten worden toegewezen. Het apparaat wordt vervolgens ingeschreven, meestal door gebruikers die de referenties voor hun werk- of schoolaccount invoeren. Het apparaat ontvangt vervolgens beleid van Intune en krijgt toegang tot bronnen.

[Apparaten inschrijven in Intune voorbereiden](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Apparaten inschrijven die bedrijfseigendom zijn
Apparaten die bedrijfseigendom (COD) zijn, kunnen met de Intune-console worden beheerd. iOS-apparaten kunnen rechtstreeks via de hulpprogramma's van Apple worden ingeschreven. Alle typen apparaten kunnen worden ingeschreven door een beheerder of manager die de apparaatinschrijvingsbeheerder gebruikt. Apparaten met een IMEI-nummer kunnen ook worden geïdentificeerd en getagd als bedrijfseigendom om COD-scenario's mogelijk te maken.

[Apparaten inschrijven die bedrijfseigendom zijn](manage-corporate-owned-devices.md)

## Mobile Device Management met Exchange ActiveSync en Intune
Mobiele apparaten die niet zijn ingeschreven maar die met Exchange ActiveSync (EAS) verbinding maken, kunnen met behulp van MDM EAS-beleid door Intune worden beheerd. Intune gebruikt een Exchange-connector om met EAS te communiceren, zowel op locatie als in de cloud.

[Mobile Device Management met Exchange ActiveSync en Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Windows-pc's met Intune beheren  
U kunt Microsoft Intune ook gebruiken om Windows-pc's te beheren met de Intune-clientsoftware voor Windows-pc’s. Pc's die door de Intune-client worden beheerd, kunnen:

 - Software- en hardware-inventarisatierapporten maken
 - Bureaubladtoepassingen installeren (bijvoorbeeld .exe en .msi-bestanden)
 - Firewall-instellingen

Computers die door Intune-clientsoftware worden beheerd, kunnen niet selectief worden gewist of buiten gebruik worden gesteld, en kunnen geen gebruik maken van de talloze Intune-beheerfuncties, zoals voorwaardelijke toegang, VPN- en Wi-Fi-instellingen, of de implementatie van certificaten en e-mailconfiguraties.

[Windows-pc's met Intune beheren](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->

