---
# required metadata

title: Microsoft Intune-bewerkingen begrijpen met behulp van rapporten | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Understand Microsoft Intune operations by using reports
Gebruik de informatie in dit onderwerp om u te helpen bij het maken en beheren van Microsoft Intune-rapporten die informatie geven over software, hardware en softwarelicenties in uw organisatie.

## Rapporten gebruiken
Intune-rapporten geven informatie over software, hardware en softwarelicenties in uw organisatie. Rapporten kunnen u helpen bij het bevestigen van huidige behoeften en het voorspellen van toekomstige uitgaven. De werkruimte **Rapporten** biedt u de hulpmiddelen voor het maken en beheren van rapporten. Zie [Inzicht in Microsoft Intune-bewerkingen met behulp van rapporten](understand-microsoft-intune-operations-by-using-reports.md) voor meer informatie over rapporten.

### Rapporttypen

|Rapporttype|Beschrijving|
|---------------|---------------|
|**Updaterapporten**|Geven de software-updates weer die geslaagd zijn op computers in uw organisatie, evenals de updates die mislukt, in behandeling of vereist zijn. Voor meer informatie over software-updates raadpleegt u [Windows-pc’s up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Rapporten met gedetecteerde software**|Tonen software die is geïnstalleerd op computers in uw organisatie en bevatten de softwareversies. U kunt de informatie die wordt weergegeven, filteren op basis van de software-uitgever en de softwarecategorie. U kunt de updates in de lijst uitbreiden om meer details weer te geven (zoals de computers waarop deze update is geïnstalleerd) door te klikken op de pijl naast het item.<br /><br />Wanneer u computers buiten gebruik stelt of de groepslidmaatschappen ervan in Intune wijzigt, kan het enkele minuten duren voordat deze wijzigingen worden weergegeven in het rapport met gedetecteerde software. Voor de meest nauwkeurige software-inventarisatiegegevens wacht u enkele minuten na het buiten gebruik stellen van computers of het wijzigen van hun groepslidmaatschappen voordat u een rapport met gedetecteerde software voor deze computers uitvoert.|
|**Computerinventarisrapporten**|Tonen informatie over beheerde computers in uw organisatie. Gebruik dit rapport voor het plannen van hardwareaankopen en voor meer begrip van de hardwarebehoeften van gebruikers in uw organisatie. Zie [Windows-pc's met Microsoft Intune beheren](manage-windows-pcs-with-microsoft-intune.md) voor meer informatie over het werken met beheerde computers.|
|**Inventarisrapporten van mobiele apparaten**|Tonen informatie over de mobiele apparaten in uw organisatie. U kunt de informatie filteren die wordt weergegeven op basis van groepen, of het nu een jailbroken of rooted apparaat betreft, en op besturingssysteem.|
|**Licentie-inkooprapporten**|Tonen de softwaretitels voor alle gelicentieerde software in geselecteerde licentiegroepen, op basis van de licentieovereenkomsten. Als softwarelicentiegegevens langer dan 24 uur niet zijn vernieuwd, worden deze vernieuwd wanneer u een licentierapport genereert. Een licentierapport is geen exacte berekening van de softwaretitels die worden gebruikt, noch een bewijs van naleving van overeenkomsten. Het rapport is een middel waarmee u licentiebeslissingen voor uw organisatie kunt nemen. Intune detecteert mogelijk bepaalde producten niet die over een Microsoft-volumelicentie kunnen beschikken. De beschikbare filters zijn:<br /><br />**Alle overeenkomsten** toont alle gelicentieerde softwareproducten die worden beheerd met Intune.<br /><br />**Volumelicentieovereenkomsten** toont uitsluitend VLSC-softwareproducten.<br /><br />**Overige softwarelicentieovereenkomsten** toont softwareproducten die buiten VLSC worden beheerd.|
|**Licentie-installatierapporten**|Vergelijk geïnstalleerde software op computers in uw organisatie met de huidige dekking van uw licentieovereenkomst volgens het Volume Licensing Service Center (VLSC). Filters omvatten:<br /><br />**Alle overeenkomsten** toont alle gelicentieerde softwareproducten die worden beheerd met Intune.<br /><br />**Volumelicentieovereenkomsten** toont uitsluitend VLSC-softwareproducten.<br /><br />**Overige softwarelicentieovereenkomsten** toont softwareproducten die buiten VLSC worden beheerd.|
|**Rapporten van voorwaarden**|Laat ziet of gebruikers de door u geïmplementeerde voorwaarden hebben geaccepteerd, en welke versie ze hebben geaccepteerd. U kunt maximaal 10 gebruikers opgeven waarvoor instemming met alle bij hun geïmplementeerde voorwaarden wordt weergegeven, of u kunt de acceptatiestatus voor een bepaalde bij hun geïmplementeerde voorwaarde weergeven.|
|**Rapporten over niet-compatibele apps**|Tonen informatie over de gebruikers die apps hebben geïnstalleerd die op uw lijsten met compatibele en niet-compatibele apps staan. Met dit rapport kunt u zoeken naar gebruikers en apparaten die niet voldoen aan uw bedrijfsbeleid inzake apps.|
|**Rapporten voor certificaatnaleving**|Toont welke certificaten via SCEP of PKCS #12 (.pfx) zijn uitgegeven aan gebruikers en apparaten. Met dit rapport kunt u zoeken naar certificaten die zijn uitgegeven, verlopen en ingetrokken.|
|**Apparaatgeschiedenisrapporten**|Tonen een historisch logboek van intrekkings-, wis- en verwijderingsacties. Gebruik dit rapport om te zien wie in het verleden acties op apparaten heeft gestart.|
|**Mac OS X-hardwarerapport**|Geeft de details weer van de hardware van alle ingeschreven Mac OS X-apparaten in de door u geselecteerde groepen. Zie [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md) voor informatie over de hardware-inventarisatie van deze apparaten.|
|**Mac OS X-softwarerapport**|Geeft de software weer die op alle Mac OS X-apparaten in de door u geselecteerde groepen is geïnstalleerd Het rapport bevat de softwarenaam (als een bundel-id), de verkorte (of gebruiksvriendelijke) versienaam, de versie en het aantal apparaten waarop de software is geïnstalleerd.|

#### Een rapport maken

1.  Klik in de Intune-beheerconsole op **Rapporten** en vervolgens op het rapporttype dat u wilt genereren, zoals wordt beschreven in bovenstaande tabel.

2.  Op de pagina **Nieuw rapport maken** accepteert u de standaardwaarden of past u deze aan om de resultaten te filteren die door het rapport worden geretourneerd. U kunt bijvoorbeeld selecteren dat alleen de software die is uitgegeven door Microsoft wordt weergegeven in het rapport met gedetecteerde software.

3.  Klik op **Rapport weergeven** om het rapport in een nieuw venster te openen.

Om het rapport te sorteren op elk van de weergegeven kolommen, klikt u op de kolomkop. Bovendien kunt u in sommige rapporten items in de lijst uitvouwen om meer details weer te geven.

## Meer rapportacties
Bovendien ondersteunen rapporten de volgende acties:

|Actie|Meer informatie|
|----------|--------------------|
|**Afdrukken**|Klik in een geopend rapport op het pictogram voor afdrukken en volg de instructies.|
|**Exporteren**|Klik in een geopend rapport op het pictogram voor exporteren en volg de instructies. U kunt een rapport exporteren naar de indeling met door komma's gescheiden waarden (.csv) of de HTML-indeling.|
|**Opslaan**|Op de pagina **Nieuw rapport maken** kan iedere gebruiker maximaal 100 rapporten opslaan. Configureer de rapportparameters zodat ze aan uw vereisten voldoen en klik vervolgens op **Opslaan**of **Opslaan als** als u een andere naam wilt gebruiken.|
|**Laden**|Op de pagina **Nieuw rapport maken** klikt u op **Laden** om eerder opgeslagen sets met rapportparameters op te halen.|
|**Verwijderen**|In de werkruimte **Rapporten** selecteert u het gewenste rapporttype, klikt u op **Laden**en klikt u vervolgens in de lijst met rapporten op het verwijderingspictogram (x) naast het rapport.|

## Zie ook
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO1-->

