---
title: iOS-apparaten inschrijven via Configuratieassistent | Microsoft Docs
description: Zakelijke iOS-apparaten inschrijven met behulp van het hulpprogramma Apple Configurator om de fabrieksinstellingen van het apparaat terug te zetten en dit voor te bereiden voor de Configuratieassistent.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 01de894167a65f6b3a46808610232feb8dd7e536


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>IOS-apparaten inschrijven met Apple Configurator via Configuratieassistent

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune ondersteunt het inschrijven van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat wordt uitgevoerd op een Mac-computer. Met dit proces wordt het apparaat teruggezet naar de fabrieksinstellingen en wordt het voorbereid voor uitvoering van Configuratieassistent door de bedrijfsbeleidsregels voor de nieuwe gebruiker van het apparaat te installeren.

## <a name="setup-assistant-enrollment-for-ios-devices-with-microsoft-intune"></a>iOS-apparaten inschrijven via Configuratieassistent in Microsoft Intune
Met behulp van Apple Configurator kunt u de fabrieksinstellingen van iOS-apparaten terugzetten en deze apparaten voorbereiden op de nieuwe gebruiker van het apparaat. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen en wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt. Voor de meeste scenario's is vereist dat het beleid dat op het iOS-apparaat is toegepast, **gebruikersaffiniteit** bevat, zodat de app Intune Company Portal kan worden gebruikt.

**Vereisten**
* [iOS-inschrijving ingeschakeld](set-up-ios-and-mac-management-with-microsoft-intune.md) door het installeren van een APNs-certificaat
* Fysieke toegang tot iOS-apparaten&mdash;de fabrieksinstellingen moeten zijn teruggezet op deze apparaten en voor de apparaten moet geen wachtwoordbeveiliging zijn ingesteld
* Serienummers van apparaten&mdash;zie [Het serienummer van een Apple product vinden](https://support.apple.com/en-us/HT204308)
* USB-verbindingskabels
* Een Mac-computer met [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Groep mobiele apparaten maken** (optioneel).
    Als uw bedrijf voor het beheer van apparaten groepen mobiele apparaten vereist, maakt u deze groepen. Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) voor meer informatie.

2.  **Een profiel maken voor apparaten**.
    Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten. De volgende stappen laten zien hoe u een inschrijvingsprofiel kunt maken voor iOS-apparaten die worden ingeschreven met Apple Configurator.

    1.  Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies **Toevoegen**.
    ![Inschrijvingsprofiel voor apparaten maken](../media/pol-sa-corp-enroll.png)

    2.  Geef details voor de apparaatprofielen op:

        -   **Naam**&mdash;De naam van het inschrijvingsprofiel voor apparaten (niet zichtbaar voor gebruikers).

        -   **Beschrijving**&mdash;De beschrijving van het inschrijvingsprofiel voor apparaten (niet zichtbaar voor gebruikers).

        -   **Inschrijvingsgegevens**&mdash;Hiermee geeft u op hoe apparaten worden ingeschreven.

            -   **Vragen om gebruikersaffiniteit**&mdash;Het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. **Gebruikersaffiniteit** moet worden ingesteld voor DEP-beheerde apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps.

            -   **Geen gebruikersaffiniteit**&mdash;Het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

        -   **Vooraf toegewezen apparatengroep**&mdash;Alle apparaten waarvoor dit profiel wordt geïmplementeerd, behoren in eerste instantie tot deze groep. U kunt apparaten na de inschrijving opnieuw toewijzen.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

        -  **Device Enrollment Program**&mdash;Het Apple Device Enrollment Program (DEP) kan niet worden gebruikt met inschrijving via Configuratieassistent. Zorg ervoor dat de wisselknop is ingesteld op **uit**.

    3.  Kies **Profiel opslaan** om het profiel toe te voegen.

3.  **iOS-apparaten toevoegen voor inschrijving met Configuratieassistent**.
    Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Groepen** &gt; **Alle apparaten** &gt; **Alle apparaten in bedrijfseigendom** &gt; **Alle apparaten** en kies vervolgens **Apparaten toevoegen**. U kunt apparaten op twee manieren toevoegen:

    ![Dialoogvenster Apparaten toevoegen](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Een CSV-bestand met serienummers uploaden**&mdash;Maak een lijst met door komma's gescheiden waarden (CSV) van twee kolommen zonder koptekst. Zorg ervoor dat het CSV-bestand niet meer dan 5000 apparaten bevat en niet groter is dan 5 MB.

        |||
        |-|-|
        |&lt;Serienummer 1&gt;|&lt;Details apparaat 1&gt;|
        |&lt;Serienummer 2&gt;|&lt;Details apparaat 2&gt;|
        Dit CSV-bestand ziet er in een teksteditor als volgt uit:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Handmatig apparaatdetails toevoegen**&mdash;Geef het serienummer en de apparaatdetails van maximaal 15 apparaten op.

    > [!NOTE]
    > Als u op een later tijdstip apparaten in bedrijfseigendom uit het Intune-beheer wilt verwijderen, moet u het serienummer van het apparaat mogelijk uit Intune verwijderen in de apparaatgroep **Op iOS-serienummer** onder **Vooraf geregistreerde bedrijfsapparaten** om de apparaatregistratie uit te schakelen. Als met Intune een noodherstelprocedure wordt uitgevoerd op of rond de tijd dat u de serienummers verwijdert, moet u controleren of alleen de serienummers van actieve apparaten in die groep worden weergegeven.

    Kies **Volgende**.

4.  **Apparaten selecteren voor inschrijving**.
    Bevestig de apparaten die moeten worden ingeschreven. Serienummers die al zijn ingeschreven of die op een andere manier worden ingeschreven, kunnen niet worden geïmporteerd. Kies **Volgende** om door te gaan.

5.  **Profiel toewijzen**.
    Kies in de lijst met beschikbare profielen het profiel dat u wilt toewijzen, controleer de **details van het inschrijvingsprofiel**en kies vervolgens **Voltooien**. U kunt handmatig toegevoegde apparaten toewijzen aan elk inschrijvingsprofiel.

6.  **Een profiel exporteren voor implementatie op iOS-apparaten**.
    Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en selecteer vervolgens het apparaatprofiel dat op mobiele apparaten moet worden geïmplementeerd. Kies **Exporteren** op de taakbalk. Kopieer de **profiel-URL** en sla deze op. U zult deze later in Apple Configurator uploaden om het Intune-profiel te definiëren dat wordt gebruikt door iOS-apparaten.
    Voor ondersteuning van Apple Configurator 2 moet u de profiel-URL 2.0 bewerken. Als u dit wilt doen, vervangt u deze code:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Door deze code:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   In de volgende procedure gaat u deze profiel-URL met Apple Configurator uploaden naar de Apple DEP-service om het Intune-profiel te definiëren dat door iOS-apparaten wordt gebruikt.



7.  **Het apparaat voorbereiden met Apple Configurator**.
    iOS-apparaten zijn verbonden met de Mac-computer en ingeschreven voor beheer van mobiele apparaten.

    1.  Open **Apple Configurator2** op een Mac-computer. Kies in de menubalk **Apple Configurator 2** en vervolgens **Voorkeuren**.

         > [!WARNING]
         > De apparaten worden tijdens het inschrijvingsproces opnieuw ingesteld op de fabrieksconfiguraties. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet het apparaat verbinden wanneer het scherm **Hallo** wordt weergegeven.

    2. Selecteer in het deelvenster met voorkeuren **Servers** en kies het plusteken (+) om de wizard voor de MDM-server te starten. Kies **Volgende**.

    3. Voer de **naam** en de **inschrijvings-URL** in voor de MDM-server uit stap 6 in 'iOS-apparaten inschrijven via Configuratieassistent in Microsoft Intune'. Voer voor de inschrijvings-URL de profiel-URL voor inschrijving in die u hebt geëxporteerd uit Intune. Kies **Volgende**.  

       De waarschuwing 'Server-URL is niet geverifieerd' kunt u zonder problemen negeren. Als u wilt doorgaan, kiest u **Volgende** totdat de wizard is voltooid.

    4.  Verbind de mobiele iOS-apparaten met de Mac-computer met een USB-adapter.

        > [!WARNING]
        > De apparaten worden tijdens het inschrijvingsproces opnieuw ingesteld op de fabrieksconfiguraties. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet Configuratieassistent starten wanneer het scherm **Hallo** wordt weergegeven.

    5.  Kies **Voorbereiden**. Selecteer in het deelvenster iOS-apparaat voorbereiden de optie **Handmatig** en kies vervolgens **Volgende**.

    6. Selecteer in het deelvenster Registreren bij MDM-server de naam van de server die u hebt gemaakt en kies vervolgens **Volgende**.

    7. Selecteer in het deelvenster Apparaten onder supervisie plaatsen het toezichtsniveau en kies **Volgende**.

    8. Kies in het deelvenster Een organisatie maken de **organisatie** of maak een nieuwe organisatie en kies vervolgens **Volgende**.

    9. Kies in het deelvenster iOS-configuratieassistent configureren de stappen die de gebruiker krijgt te zien en kies vervolgens **Voorbereiden**. Voer een verificatie uit om de vertrouwensinstellingen bij te werken als dit wordt gevraagd.  

    10. Zodra het iOS-apparaat klaar is met de voorbereidingen, kunt u de USB-kabel verwijderen.  

8.  **Apparaten distribueren**.
    De apparaten zijn nu gereed voor bedrijfsinschrijving. Schakel de apparaten uit en distribueer ze naar gebruikers. Wanneer gebruikers de apparaten inschakelen, wordt Configuratieassistent gestart.



### <a name="see-also"></a>Zie tevens
[Vereisten voor het inschrijven van apparaten](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO2-->

