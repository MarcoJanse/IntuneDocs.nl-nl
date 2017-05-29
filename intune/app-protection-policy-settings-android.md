---
title: Beveiligingsbeleidsinstellingen voor Android-apps
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp worden de beveiligingsbeleidsinstellingen voor Android-apparaten beschreven.'
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a3c5fcd62538583180a6d604a7aca87a15caf5b4
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="android-app-protection-policy-settings"></a>Beveiligingsbeleidsinstellingen voor Android-apps
De in dit onderwerp beschreven beleidsinstellingen kunnen worden [geconfigureerd](app-protection-policies.md) voor een app-beveiligingsbeleid op het tabblad **Instellingen** in Azure Portal.
Er zijn twee soorten beleidsinstellingen, namelijk instellingen voor herlocatie van gegevens en instellingen voor toegang. In dit onderwerp verwijst de term *door beleid beheerde apps* naar apps die zijn geconfigureerd met een app-beveiligingsbeleid.

##  <a name="data-relocation-settings"></a>Instellingen voor herlocatie van gegevens

| Instelling | Gebruik | Standaardwaarde(n) |
|------|------|------|
| **Back-ups van Android voorkomen** | Kies **Ja** om te voorkomen dat deze app back-ups van werk- of schoolgegevens in de [Android-back-upservice](https://developer.android.com/google/backup/index.html) maakt. Kies **Nee** om toe te staan dat deze app een back-ups maakt van werk- of schoolgegevens.| Yes |
| **App mag gegevens overdragen naar ander apps** | Geef aan welke apps gegevens uit deze app kunnen ontvangen: <ul><li> **Door beleid beheerde apps**: overdracht alleen toestaan naar andere door beleid beheerde apps.</li> <li>**Alle apps**: overdracht naar alle apps toestaan. </li> <li>**Geen**: geen gegevensoverdracht naar apps toestaan, met inbegrip van andere door beleid beheerde apps.</li></ul> <p> Er zijn enkele uitzonderingsapps en -services waar Intune gegevens naar mag overbrengen. Zie [Uitzonderingen voor gegevensoverdracht](#Data-transfer-exemptions) voor een volledige lijst met apps en services.| Alle apps |
| **App mag gegevens ontvangen van andere apps** | Geef aan welke apps gegevens naar deze app kunnen overdragen: <ul><li>**Door beleid beheerde apps**: overdracht alleen toestaan vanuit andere door beleid beheerde apps.</li><li>**Alle apps**: gegevensoverdracht vanuit alle apps toestaan.</li><li>**Geen**: geen gegevensoverdracht vanuit apps toestaan, met inbegrip van andere door beleid beheerde apps.</li></ul> <p>Er zijn enkele uitzonderingsapps en -services van waaruit Intune gegevensoverdracht mag toestaan. Zie [Uitzonderingen voor gegevensoverdracht](#Data-transfer-exemptions) voor een volledige lijst met apps en services. | Alle apps |
| **'Opslaan als' voorkomen** | Kies **Ja** als u het gebruik van de optie Opslaan als wilt uitschakelen in deze app. Selecteer **Nee** als u het gebruik van de optie Opslaan als wilt toestaan. | Nee |
| **Knippen, kopiëren en plakken met andere apps beperken** | Geef op wanneer knip-, kopieer- en plakbewerkingen voor deze app kunnen worden gebruikt. U kunt kiezen uit: <ul><li>**Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere apps.</li><li>**Door beleid beheerde apps**: alleen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere door beleid beheerde apps.</li><li>**Door beleid beheerde apps met Plakken in**: knippen en kopiëren toestaan tussen deze app en andere door beleid beheerde apps. Gegevens uit alle apps mogen in deze app worden geplakt.</li><li>**Elke app**: geen beperkingen voor knip-, kopieer- en plakbewerkingen vanuit en naar deze app. | Elke app |
|**Weergave van webinhoud beperken tot beheerde browser** | Kies **Ja** om af te dwingen dat webkoppelingen in de app worden geopend in de Managed Browser-app. <br><br> Voor apparaten die niet zijn geregistreerd bij Intune, kunnen de webkoppelingen in door beleid beheerde apps alleen worden geopend in de Managed Browser-app. <br><br> Als u Intune gebruikt voor het beheer van uw apparaten, raadpleegt u [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies). | Nee |
| **Appgegevens versleutelen** | Kies **Ja** om versleuteling van werk- of schoolgegevens in deze app in te schakelen. Intune gebruikt een 128-bit OpenSSL-AES-versleutelingsmethode samen met het Android Keystore-systeem om appgegevens veilig te versleutelen. Gegevens worden synchroon versleuteld tijdens I/O-taken voor bestanden. Inhoud van de apparaatopslag wordt altijd versleuteld. <br><br> De versleutelingsmethode is **niet** gecertificeerd volgens FIPS 140-2.  | Yes |
| **Synchroniseren van contactpersonen uitschakelen** | Kies **Ja** om te voorkomen dat de app gegevens opslaat in de systeemeigen Contactpersonen-app op het apparaat. Kies **Nee** om ervoor te zorgen dat de app gegevens kan opslaan in de systeemeigen Contactpersonen-app op het apparaat. <br><br>Als u selectief wilt wissen om werk- of schoolgegevens uit de app te verwijderen, worden contactpersonen verwijderd die rechtstreeks vanuit de app met de systeemeigen Contactpersonen-app worden gesynchroniseerd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app. | Nee |
| **Afdrukken uitschakelen** | Kies **Ja** om te voorkomen dat de app werk- of schoolgegevens afdrukt. | Nee |


  >[!NOTE]
  >De versleutelingsmethode voor de instelling **Appgegevens versleutelen** is **niet** gecertificeerd volgens FIPS 140-2.

## <a name="data-transfer-exemptions"></a>Uitzonderingen voor gegevensoverdracht

Er zijn een aantal uitzonderingsapps en -platformservices waar het Intune beveiligingsbeleid voor apps gegevensoverdracht naar en van kan toestaan. Alle apps met bijvoorbeeld Intune-functionaliteit op Android moeten in staat zijn gegevens over te dragen van en naar Google tekst-naar-spraak, zodat tekst van uw mobiele apparaat hardop kan worden voorgelezen. Deze lijst kan worden gewijzigd en reflecteert de services en apps die als nuttig voor beveiligde productiviteit worden beschouwd.

### <a name="full-exemptions"></a>Volledige uitzonderingen

Voor deze apps en services is gegevensoverdracht naar en van Intune-beheerde apps volledig toegestaan.

|Naam van app/service | Beschrijving |
| ------ | ---- |
| com.android.phone | Systeemeigen phone-app
| com.android.vending | Google Play Store |
| com.android.documentsui | Android Documentkiezer|
| com.google.android.webview | [WebView](https://developer.android.com/reference/android/webkit/WebView.html), dat nodig is voor veel apps, inclusief Outlook. |
| com.android.webview |[WebView](https://developer.android.com/reference/android/webkit/WebView.html), dat nodig is voor veel apps, inclusief Outlook.|
| com.google.android.tts | Google Tekst naar spraak |
| com.android.providers.settings | Systeeminstellingen Android |
| com.azure.authenticator | Azure Authenticator-app, die vereist is voor een geslaagde verificatie in veel scenario's. |
| com.microsoft.windowsintune.companyportal | Intune Bedrijfsportal|

### <a name="conditional-exemptions"></a>Voorwaardelijke uitzonderingen
Voor deze apps en services is gegevensoverdracht naar en van Intune-beheerde apps onder bepaalde voorwaarden toegestaan.

|Naam van app/service | Beschrijving | Uitzonderingsvoorwaarde|
| ------ | ---- | --- |
| com.android.chrome | Google Chrome-browser | Chrome wordt gebruikt voor een aantal webweergaveonderdelen op Android 7.0+ en is nooit verborgen. Gegevensstroom naar en van de app is echter altijd beperkt.
| com.skype.raider | Skype | Voor de Skype-app zijn alleen bepaalde acties die in een telefonische oproep resulteren toegestaan. |
| com.android.providers.media | Android media-inhoudsprovider | Voor de media-inhoudsprovider is alleen de actie beltoonselectie toegestaan. |
| com.google.android.gms; com.google.android.gsf | Google Play-Services-pakketten | Voor deze pakketten zijn Google Cloud Messaging-acties zoals pushmeldingen toegestaan. |


##  <a name="access-settings"></a>Toegangsinstellingen

| Instelling | Gebruik | Standaardwaarde(n) |
|------|------|------|
| **Pincode is vereist voor toegang** | Kies **Ja** om een pincode te vereisen voor gebruik van deze app. De eerste keer dat de gebruiker de app uitvoert in een aan werk of school gerelateerde context, wordt de gebruiker gevraagd deze pincode in te stellen. Standaardwaarde = **Ja**.<br><br> Configureer de volgende instellingen voor pincodesterkte: <ul><li>**Aantal pogingen voordat pincode opnieuw wordt ingesteld**: geef het aantal pogingen voor de gebruiker op om de pincode in te voeren voordat de gebruik deze opnieuw moet instellen. Standaardwaarde = **5**.</li><li> **Eenvoudige pincode toestaan:** kies **Ja** als gebruikers eenvoudige pincodes mogen gebruiken, zoals 1234 of 1111. Kies **Nee** als ze geen eenvoudige tekenreeksen mogen gebruiken. Standaardwaarde = **Ja**. </li><li> **Lengte van de pincode:** geef het minimale aantal cijfers op waaruit een pincode moet bestaan. Standaardwaarde = **4**. </li><li> **Vingerafdruk in plaats van pincode toestaan (Android 6.0+)**: selecteer **Ja** als de gebruiker in plaats van een pincode [vingerafdrukverificatie](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) mag gebruiken voor toegang tot apps. Standaardwaarde = **Ja**. </li></ul> Op Android-apparaten kunt u gebruikers hun identiteit laten aantonen met behulp van [Android-vingerafdrukverificatie](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) in plaats van een pincode. Wanneer gebruikers deze app proberen te gebruiken via hun werk- of schoolaccount, moeten ze hun vingerafdruk in plaats van een pincode gebruiken. </li></ul>| Pincode vereisen: Ja <br><br> Pogingen om pincode opnieuw in te stellen: 5 <br><br> Eenvoudige pincode toestaan: Ja <br><br> Lengte pincode: 4 <br><br> Vingerafdruk toestaan: Ja |
| **Bedrijfsreferenties vereisen voor toegang** | Kies **Ja** om te vereisen dat gebruikers zich aanmelden met hun werk- of schoolaccount in plaats van een pincode voor toegang tot apps. Als u deze waarde op **Ja** instelt, overschrijft dit de vereisten voor de pincode of Touch-ID.  | Nee |
| **De uitvoering blokkeren van beheerde apps die op jailbroken of geroote apparaten worden uitgevoerd** |  Kies **Ja** om te voorkomen dat deze app wordt uitgevoerd op jailbroken of geroote apparaten. De gebruiker kan deze app nog steeds gebruiken voor privétaken maar moet voor het openen van werk- of schoolgegevens in deze app een ander apparaat gebruiken. | Yes |
| **Toegangsvereisten opnieuw controleren na (minuten)** | Configureer de volgende instellingen: <ul><li>**Time-out**: geef de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd. Standaardwaarde = **30** minuten.</li><li>**Offline respijtperiode**: als het apparaat offline is, geeft u de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd. Standaardwaarde = **720** minuten (12 uur).</li></ul>| Time-out: 30 <br><br> Offline: 720 |
| **Offline interval (in dagen) voordat app-gegevens worden gewist** | Werk- of schoolgegevens in deze app kunnen worden gewist als een apparaat langer dan een bepaalde periode offline is. Geef het aantal dagen op dat een apparaat offline mag zijn voordat de werk- of schoolgegevens van het apparaat worden verwijderd. <br><br> | 90 dagen |
| **Schermopname en Android Assistant blokkeren (Android 6.0+)** | Kies **Ja** om schermopnames en gebruik van de **Android Assistent**-functies van het apparaat te blokkeren bij gebruik van deze app. Als u **Ja** kiest, wordt ook de voorbeeldafbeelding van de app-schakelbaar vervaagd bij gebruik van deze app in combinatie met een werk- of schoolaccount. | Nee |
| **Minimumversie van het Android-besturingssysteem vereisen** | Kies **Ja** om een minimumversie van het Android-besturingssysteem te vereisen voor gebruik van deze app. Toegang door de gebruiker wordt geblokkeerd als de Android-versie op het apparaat niet aan de vereiste voldoet. <br><br> | Nee |
| **Minimumversie van het Android-besturingssysteem vereisen (alleen waarschuwing)** | Kies **Ja** om een minimumversie van het Android-besturingssysteem aan te bevelen voor gebruik van deze app. De gebruiker ziet een melding als de Android-versie op het apparaat niet aan de vereiste voldoet. De gebruiker kan deze melding negeren. <br><br> | Nee |
| **Minimumversie van app vereisen** | Kies **Ja** om een minimumversie van de app te vereisen voor gebruik van de app. Toegang door de gebruiker wordt geblokkeerd als de app-versie op het apparaat niet aan de vereiste voldoet.<br><br>Wanneer u apps als doel selecteert, is het versieschema tussen de apps vaak afwijkend.<br><br> | Nee |
| **Minimumversie van app vereisen (alleen waarschuwing)** | Kies **Ja** om een minimumversie van de app aan te bevelen bij gebruik van de app. De gebruiker ziet een melding als de app-versie op het apparaat niet aan de vereiste voldoet. De gebruiker kan deze melding negeren.<br><br>Wanneer u apps als doel selecteert, is het versieschema tussen de apps vaak afwijkend.<br><br> | Nee |
