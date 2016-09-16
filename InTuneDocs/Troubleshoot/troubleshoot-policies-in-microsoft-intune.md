---
title: Beleidsproblemen oplossen | Microsoft Intune
description: Problemen met de configuratie van het beleid oplossen.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1f133d31311706365888cf33ceb4c4412deec333
ms.openlocfilehash: a8afc681b8b12e1e760dea3f784e4beac4697242


---

# Beleidsproblemen oplossen in Microsoft Intune

Als u problemen hebt met het implementeren en beheren van beleid met Intune, begint u hier. Dit onderwerp bevat oplossingen voor een aantal veelvoorkomende problemen.

## Wordt er beleid toegepast op het apparaat?
**Probleem:** het is onduidelijk of er een bepaald beleid wordt toegepast op een apparaat of een apparaat functioneert niet overeenkomstig een beleid.

Controleer de beleidsgegevens voor elk apparaat om na te gaan hoe het beleid van invloed is op een bepaald apparaat.

In de Intune-beheerconsole vindt u voor elk apparaat een tabblad Beleid onder **Apparaateigenschappen**. Als dat niet het geval is, wordt de inschrijving voor het apparaat waarschijnlijk nog uitgevoerd of wordt er mogelijk geen beleid toegepast. Elk beleid heeft een **Bedoelde waarde** en een **Status**. De beoogde waarde is wat u wilt bereiken bij het toewijzen van het beleid. De status is wat feitelijk wordt bereikt wanneer alle beleidsregels die betrekking hebben op het apparaat samen met de beperkingen en vereisten van de hardware en het besturingssysteem als een geheel worden beschouwd. Mogelijke statussen zijn:

-   **Conform**: het apparaat heeft het beleid ontvangen en rapporteert aan de service dat het voldoet aan de instelling.

-   **Niet van toepassing**: de beleidsinstelling is niet van toepassing. E-mailinstellingen voor iOS-apparaten zijn bijvoorbeeld niet van toepassing op een Android-apparaat.

-   **In behandeling**: het beleid is naar het apparaat verzonden, maar de status is door het apparaat nog niet gerapporteerd aan de service. Zo moet de gebruiker in geval van versleuteling voor Android versleuteling inschakelen, waardoor de actie mogelijk in behandeling is.

In de onderstaande schermafbeelding ziet u twee duidelijke voorbeelden:

-   **Eenvoudige wachtwoorden toestaan** is ingesteld op **Ja**, zoals wordt weergegeven in de kolom **Bedoelde waarde** , maar de **Status** is **Niet van toepassing**. Dit komt doordat eenvoudige wachtwoorden niet worden ondersteund voor Android-apparaten.

-   Zo is ook het uitgevouwen beleidsitem **E-mailinstellingen voor iOS-apparaten** niet op dit apparaat toegepast, omdat dit een Android-apparaat is.

![Intune-apparaatbeleid](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Houd er rekening mee dat wanneer er twee sets beleidsregels met verschillende beperkingsniveaus zijn die op hetzelfde apparaat of dezelfde gebruiker van toepassing zijn, in de praktijk het meest beperkende beleid van toepassing is.

## Aan Microsoft Intune-beleid gerelateerde fouten in policyplatform.log
Bij niet-MDM-Windows-apparaten kunnen beleidsfouten in het bestand policyplatform.log het gevolg zijn van niet-standaardinstellingen in Windows Gebruikersaccountbeheer (UAC) op het apparaat. Bepaalde niet-standaard-UAC-instellingen kunnen invloed hebben op Microsoft Intune-clientinstallaties en de beleidsuitvoering.

### UAC-problemen oplossen

1.  Stel de computer buiten gebruik, zoals wordt beschreven in [Apparaten buiten gebruik stellen vanuit Microsoft Intune-beheer](/intune/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Wacht twintig minuten tot de clientsoftware is verwijderd.

    > [!NOTE]
    > Probeer niet om de client te verwijderen vanuit Programma's en onderdelen.

3.  Typ **UAC** in het startmenu om de instellingen voor Gebruikersaccountbeheer te openen.

4.  Verplaats de schuifregelaar voor meldingen naar de standaardinstelling.


## Waarschuwing: het opslaan van de toegangsregels in Exchange is mislukt
**Probleem**: u ontvangt in de beheerconsole de waarschuwing **Het opslaan van de toegangsregels in Exchange is mislukt**  .

Als u beleid hebt gemaakt in de werkruimte Beleid voor Exchange On-Premises van de beheerconsole, maar O365 gebruikt, worden de geconfigureerde beleidsinstellingen niet door Intune afgedwongen. Noteer de beleidsbron die in de waarschuwing wordt vermeld.  Verwijder onder de werkruimte voor beleid voor Exchange On-Premises de verouderde regels omdat dit algemene Exchange-regels zijn in Intune voor een on-premises Exchange-toepassing en geen betrekking hebben op O365. Maak vervolgens een nieuw beleid voor O365.

## Fout: kan de waarde niet ophalen van de computer, 0x80041013
Dit kan gebeuren als de tijd op het lokale systeem met meer dan vijf minuten afwijkt. Als de tijd op de lokale computer afwijkt, mislukken beveiligde transacties omdat de tijdstempels ongeldig zijn.

U lost dit probleem op door de lokale systeemtijd zo gelijk mogelijk in te stellen op de internettijd of op de tijd die is ingesteld op de domeincontrollers in het netwerk.

## Het beveiligingsbeleid voor verschillende MDM-apparaten kan niet worden gewijzigd
Bij Windows Phone- en Windows RT-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld een **minimumaantal tekens voor het wachtwoord** in op 8 en wilt dit vervolgens terugbrengen tot 4. Het meer beperkende beleid is al toegepast op het apparaat.

Afhankelijk van het apparaatplatform moet u mogelijk het beveiligingsbeleid opnieuw instellen als u de beveiliging naar beneden toe wilt bijstellen.
Veeg bijvoorbeeld in Windows RT op het bureaublad vanaf rechts over het scherm om de balk **Charms** te openen en kies **Instellingen** &gt; **Configuratiescherm**.  Selecteer de applet **Gebruikersaccounts** .
In het navigatiemenu aan de linkerkant vindt u onderaan een koppeling **Beveiligingsbeleid opnieuw instellen** . Kies deze koppeling en kies vervolgens **Beleid opnieuw instellen**.
Andere MDM-apparaten, zoals Android, Windows Phone 8.1 en hoger of iOS moeten mogelijk buiten gebruik worden gesteld en weer opnieuw bij de service worden ingeschreven zodat u een minder beperkend beleid kunt toepassen.

## Kan geen beleid maken of clients registreren als de bedrijfsnaam speciale tekens bevat
**Probleem:** u kunt geen beleid maken of clients registreren.

**Oplossing:** verwijder in het [Office 365-beheercentrum](https://portal.office.com/) de speciale tekens uit de bedrijfsnaam en sla de bedrijfsgegevens op.

### Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Aug16_HO4-->

