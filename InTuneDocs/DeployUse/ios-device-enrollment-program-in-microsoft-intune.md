---
# required metadata

title: Apple DEP-beheer voor iOS-apparaten met Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS-apparaten in bedrijfseigendom met het Device Enrollment Program inschrijven
Microsoft Intune kan 'draadloos' een inschrijvingsprofiel implementeren op iOS-apparaten die via het Device Enrollment Program zijn aangeschaft. Het inschrijvingspakket kan configuratieassistentopties voor het apparaat bevatten. Gebruikers kunnen de inschrijving niet opheffen wanneer de apparaten zijn ingeschreven via DEP.

## Apple DEP-beheer voor iOS-apparaten met Microsoft Intune
Voor het beheren van iOS-apparaten in bedrijfseigendom met het Device Enrollment Program (DEP) van Apple moet uw organisatie lid worden van DEP en apparaten verwerven via dat programma. Details van dit proces kunt u vinden op:  [https://deploy.apple.com](https://deploy.apple.com). Voordelen van het programma zijn onder andere handsfree instellen, dus zonder dat elk apparaat via een USB-verbinding op een computer hoeft te worden aangesloten.

Voordat u iOS-apparaten van het bedrijf met DEP kunt inschrijven, moet u een DEP-token van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten van uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

1.  **Beginnen met beheer van iOS-apparaten met Microsoft Intune**
    Voordat u iOS-apparaten met het Device Enrollment Program (DEP) kunt inschrijven, moet u het iOS-beheer voor Intune hebben ingeschakeld.

2.  **Een coderingssleutel ophalen**
    Open als gebruiker met beheerdersrechten de [Microsoft Intune-beheerconsole](http://manage.microsoft.com), ga naar **Beheer** &gt; **Mobiele apparaten beheren** &gt; **iOS** &gt; **Programma apparaatinschrijving** en klik op **Coderingssleutel downloaden**. Sla het coderingssleutelbestand (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

      ![Een Device Enrollment Program-token bijwerken](../media/dev-sa-ios-dep.png)

3.  **Een Device Enrollment Program-token ophalen**
    Ga naar de [Device Enrollment Program-portal](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple-id van uw bedrijf. Deze Apple-id moet later ook worden gebruikt om uw DEP-token te verlengen.

    1.  Ga in de [Device Enrollment Program-portal](https://deploy.apple.com) naar **Programma apparaatinschrijving** &gt; **Servers beheren** en klik vervolgens op **MDM-server toevoegen**..

    2.  Voer de **MDM-servernaam** in en klik vervolgens op **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

    3.  Het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt geopend. Klik op **Bestand selecteren...** om het .pem-bestand te uploaden en klik vervolgens op **Volgende**..

    4.  In het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt een koppeling met **Uw servertoken** weergegeven. Download het servertokenbestand (.p7m) naar uw computer en klik vervolgens op **Gereed**..

    Dit certificaatbestand (.p7m) wordt gebruikt om een vertrouwensrelatie tussen Intune en de Device Enrollment Program-servers van Apple tot stand te brengen.

4.  **Het DEP-token toevoegen aan Intune**
    Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beheer** &gt; **Beheer van mobiele apparaten** &gt; **iOS** &gt; **Device Enrollment Program** en klik op **Het DEP-Token uploaden**. **Blader** naar het certificaatbestand (.p7m), voer uw **Apple-id** in en klik op **Uploaden**..

5.  **Inschrijvingsbeleid voor bedrijfsapparaten toevoegen**
    Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en klik vervolgens op **Toevoegen**. Geef **algemene** details op zoals **Naam** en **Beschrijving**, geef op of apparaten die aan het profiel zijn toegewezen, gebruikersaffiniteit hebben of deel uitmaken van een groep en schakel vervolgens **Programma-instellingen apparaatinschrijving voor dit beleid configureren** in zodat DEP wordt ondersteund. Met de **deelvensters van de configuratieassistent** worden bij het instellen de iOS-apparaatinstellingen geconfigureerd.

      ![Deelvenster van de configuratieassistent](../media/pol-sa-corp-enroll.png)

6.  **DEP-apparaten toewijzen voor beheer**
    Ga naar de [Device Enrollment Program-portal](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple-id van uw bedrijf. Ga naar **Implementatieprogramma** &gt; **Programma apparaatinschrijving** &gt; **Apparaten beheren**. Geef een manier voor **Apparaten kiezen** op, geef apparaatgegevens op en geef apparaatdetails op aan de hand van **Serienummer** en **Bestelnummer** of voer **CSV-bestand uploaden** uit. Selecteer vervolgens **Toewijzen aan server**, selecteer de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en klik vervolgens op **OK**..

7.  **Door DEP beheerde apparaten synchroniseren**
    Open als gebruiker met beheerdersrechten de [Microsoft Intune-beheerconsole](http://manage.microsoft.com), ga naar **Beheer** &gt; **Mobiele apparaten beheren** &gt; **iOS** &gt; **Programma apparaatinschrijving** en klik op **Nu synchroniseren**. Er wordt een synchronisatieaanvraag verzonden naar Apple. Als u na de synchronisatie door DEP beheerde apparaten wilt bekijken, gaat u in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Groepen** &gt; **Alle apparaten in bedrijfseigendom**. In de werkruimte **Apparaten in bedrijfseigendom** wordt de **Status** voor beheerde apparaten weergegeven als 'Geen contact gemaakt' totdat het apparaat wordt ingeschakeld en de configuratieassistent wordt uitgevoerd om het apparaat in te schrijven.

    Om te voldoen aan de voorwaarden van Apple voor acceptabel DEP-verkeer, worden door Intune de volgende beperkingen opgelegd:
     -  Een volledige DEP-synchronisatie kan niet vaker dan eens in de 7 dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen 7 dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
     -  Een synchronisatieaanvraag krijgt 10 minuten voor de uitvoering. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop Synchronisatie uitgeschakeld.

8.  **Apparaten onder gebruikers distribueren**
    Uw apparaten in bedrijfseigendom kunnen nu onder gebruikers worden gedistribueerd. Wanneer een iOS-apparaat wordt ingeschakeld, zal het worden ingeschreven voor beheer door Intune.



### Zie tevens
[Voorbereidingen voor het inschrijven van apparaten](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->

