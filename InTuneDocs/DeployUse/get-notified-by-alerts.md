---
# required metadata

title: Blijf op de hoogte met waarschuwingen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Blijf op de hoogte met Microsoft Intune-waarschuwingen
Waarschuwingen zorgen ervoor dat u op de hoogte blijft van wat er in Microsoft Intune gebeurt.

Waarschuwingen kunnen u bijvoorbeeld op de hoogte brengen van de volgende gebeurtenissen:

-   Een probleem met de Exchange-connector dat gevolgen heeft voor het beheer van mobiele apparaten

-   Malware dat op een computer is gevonden

-   Een conflict tussen twee Intune-beleidsregels dat is gedetecteerd


## Hoe waarschuwingen werken
Waarschuwingen worden gegenereerd op basis van **waarschuwingstypen**, een reeks vooraf geconfigureerde regels die in Intune zijn geïntegreerd. Bijvoorbeeld, het type waarschuwing **Cloudopslag heeft 10% of minder vrije ruimte** waarschuwt u wanneer er bijna geen schijfruimte meer is voor het opslaan van uw apps in de cloud. U kunt dit inschakelen of uitschakelen, en eigenschappen voor elk type waarschuwing configureren. Voor het bovenstaande berichttype kunt u bijvoorbeeld het volgende configureren:

-   **Status:** Of dit type waarschuwing is ingeschakeld of uitgeschakeld

-   **Ernst:** Hoe ernstig is deze waarschuwing?


|Ernst|Details|
|--------|-------|
    |![Kritieke waarschuwing](../media/Critical-Alert.jpg)|Geeft een ernstig probleem aan dat u zo snel mogelijk moet onderzoeken, bijvoorbeeld of er malware is gedetecteerd op een computer.|
    |![Waarschuwing](../media/Warning-Alert.jpg)|Geeft een probleem aan dat momenteel niet ernstig is, maar wel ernstig kan worden als u er geen aandacht aan besteedt, bijvoorbeeld beveiligingsupdates die wachten om te worden geïnstalleerd.|
    |![Informatieve waarschuwing](../media/Informational-Alert.jpg)|Geeft informatie aan die niet essentieel is voor uw activiteiten, bijvoorbeeld dat er een nieuwe versie van de Exchange-connector beschikbaar is.|

Overige waarschuwingstypen bevatten mogelijk andere items die u kunt configureren, zoals het percentage apparaten dat door een probleem moet worden getroffen voordat er een waarschuwing wordt gegenereerd.

**Als aan de criteria in een waarschuwingstype wordt voldaan, wordt er een waarschuwing gegenereerd en weergegeven in de Intune-beheerconsole.**

Bovendien kunt u Intune zodanig configureren dat u per e-mail wordt gewaarschuwd wanneer er een waarschuwing wordt gegenereerd.

## Waarschuwingen configureren
Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Beheer** &gt; **Waarschuwingen en meldingen** en kies vervolgens een van de volgende configuratietaken:

|Taak|Beschrijving|
|--------|---------------|
|**Waarschuwingstypen**|Kies het waarschuwingstype dat u wilt configureren en voer vervolgens een van de volgende handelingen uit:<br /><br />Kies **Configureren**. Configureer de instellingen die u wilt configureren in het dialoogvenster **Waarschuwingstype configureren** en kies vervolgens **OK**.<br /><br />Schakel de waarschuwing **in** of **uit**.<br /><br />Vouw het knooppunt **Waarschuwingstypen** uit en kies een categorie om alleen de waarschuwingstypen in die categorie weer te geven.|
|**Ontvangers**|Kies **Toevoegen** om een nieuw e-mailadres toe te voegen waarop de e-mailmeldingen worden ontvangen die u configureert.<br /><br />U kunt ook bestaande ontvangers **bewerken** of **verwijderen** .<br /><br />Als u meldingen wilt ontvangen, moet u dit e-mailadres ook toevoegen als ontvanger onder **Meldingsregels**.|
|**Meldingsregels**|Hiermee configureert u regels die definiëren naar wie een e-mailmelding wordt verzonden. U hebt de volgende mogelijkheden:<br /><br />**Een bestaande regel kiezen**: kies een regel en kies vervolgens **Ontvangers selecteren**. U kunt vervolgens alle ontvangers selecteren die een e-mailbericht ontvangen wanneer er een waarschuwing wordt gegenereerd die aan deze regel voldoet.<br /><br />**Maak een nieuwe regel**: voer een naam in voor de regel, selecteer de waarschuwingscategorie en de ernst van de waarschuwing die van toepassing zijn op de regel, selecteer de apparaatgroepen waarop de regel van toepassing is en selecteer de gebruikers die een e-mail ontvangen wanneer er een waarschuwing wordt gegenereerd.<br /><br />U kunt een bestaande regel ook **inschakelen**, **uitschakelen**, **bewerken**en **verwijderen** .|

## Werken met waarschuwingen
Gebruik de volgende opties om met waarschuwingen in de Intune-beheerconsole te werken.

|Optie|Beschrijving|
|----------|---------------|
|**Actieve waarschuwingen weergeven**|Kies een van de volgende mogelijkheden:<br /><br />**Een samenvatting van waarschuwingen weergeven**: de ernstigste fouten worden weergegeven in het deelvenster Waarschuwingen van de werkruimte **Dashboard**. Kies het deelvenster voor gedetailleerde informatie.<br /><br />Daarnaast vindt u een samenvatting van de waarschuwingen op de pagina **Overzicht** van de werkruimte **Waarschuwingen** .<br /><br />**Alle waarschuwingen weergeven**: kies in de werkruimte **Waarschuwingen** de optie **Alle waarschuwingen**.|
|**Meldingen weergeven**|Kies een van de volgende mogelijkheden:<br /><br />Kies in de werkruimte **Dashboard** de optie **Meldingen**.<br /><br />Kies in de werkruimte **Waarschuwingen** achtereenvolgens de opties **Alle waarschuwingen** &gt; **Meldingen**.|
|**Een waarschuwing sluiten**|Kies in de lijst met waarschuwingen de waarschuwing die u wilt sluiten en kies vervolgens **Waarschuwing sluiten**.<br /><br />Gesloten waarschuwingen worden na 90 dagen definitief verwijderd.|
|**Een gesloten waarschuwing opnieuw activeren**|Stel in de lijst met waarschuwingen de vervolgkeuzelijst **Filters** in op **Gesloten**.<br /><br />Selecteer in de lijst met gesloten waarschuwingen de waarschuwing die u opnieuw wilt activeren en kies vervolgens **Waarschuwing opnieuw activeren**.|
Intune-waarschuwingen blijven actief tot:

-   Het probleem is opgelost dat de waarschuwing heeft veroorzaakt

-   U de waarschuwing handmatig sluit

-   45 dagen zijn verstreken nadat de waarschuwing werd gegenereerd

> [!TIP] Als dezelfde waarschuwing wordt gegenereerd door apparaten waarop verschillende besturingssystemen worden uitgevoerd, ziet u mogelijk meerdere versies van dezelfde waarschuwing in de lijst met waarschuwingen.

### Zie ook
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)


<!--HONumber=May16_HO5-->

