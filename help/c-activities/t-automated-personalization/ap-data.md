---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes
description: Adobe Target samlar automatiskt in och använder en mängd olika data för att skapa sina personaliseringsalgoritmer i Automated Personalization- (AP) och Auto-Target-aktiviteter (AT). När en besökare kommer in i AP- eller AT-aktiviteten skickas en ögonblicksbild av informationen till en uppsättning"utbildningsposter" (de besökardata som personaliseringsalgoritmerna kommer att lära sig om).
title: Datainsamling för Adobe Target personaliseringsalgoritmer
feature: ap
translation-type: tm+mt
source-git-commit: 2b31d26bab2f2b702947c907c1d6966e5d0f20e3
workflow-type: tm+mt
source-wordcount: '1748'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMData-samling för målpersonaliseringsalgoritmer

[!DNL Adobe Target] samlar automatiskt in och använder en mängd olika data för att bygga sina personaliseringsalgoritmer i  [!UICONTROL Automated Personalization] (AP) och  [!UICONTROL Auto-Target] (AT)-aktiviteter. När en besökare går in i en AP- eller AT-aktivitet skickas en ögonblicksbild av information till en uppsättning&quot;utbildningsposter&quot; (de besökardata som personaliseringsalgoritmerna kommer att lära sig).

Mer information om målpersonaliseringsalgoritmer finns i [Slumpmässig skogsalgoritm](/help/c-activities/t-automated-personalization/algo-random-forest.md).

I följande tabell visas de data som samlats in av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] som standard, utan att marknadsföraren behöver göra något, samt namnkonventionen som används för att ange dessa attribut i [personaliseringsinsikter](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Du kan när som helst utöka indatauppsättningen. Mer information om hur du överför ytterligare data finns i [Överföra data för målpersonaliseringsalgoritmerna](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Datatyp | Beskrivning | Namnkonvention för datatyp | Exempelattribut |
| --- | --- | --- | --- |
| [Enhetsdata och mobildata](#device-mobile) | Enhetsspecifik och mobilspecifik information.<br>Se&quot;Enhetsdata och mobildata&quot; nedan. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | OS för mobil enhet<br>Storlek på mobilskärm |
| [Miljödata](#env) | Information om besökarens operativsystem och hur och när besökaren öppnar aktiviteten. | `Browser - / Operating System] - [Attribute Name]` | Webbläsare - Typ |
| Experience Cloud segment | Målgrupper skapade i Audience Manager eller Analytics och delade över hela Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Anpassade data |
| [Geografiska data](#geo) | Information om var besökaren befinner sig.<br>Se Geografiska data nedan. | `Geo - [geo attribute]` | Ort<br>Land<br>Region/delstat<br>Postnummer<br>Latitud<br>Longitud<br>Internetleverantör eller mobiloperatör |
| Profilattribut | Profilskript eller attribut som har överförts direkt till målprofilen via API:t för uppdatering | `Custom - Visitor Profile - [attribute name]` | Anpassade data |
| Refererande URL-parametrar | Den refererande URL:en är i allmänhet den URL som refererade till en viss sida som initierade Target-anropet.<br>Observera att den här variabeln kan påverkas av användarnas aktivitet på din webbplats samt av den tekniska implementeringen av din webbplats. | `Custom - [Referring URL Parameter] - [Parameter value]` | Anpassade data |
| Rapporteringssegment | Alla segment som har konfigurerats i aktivitetsinställningarna. | `Reporting Segment -[Segment Name]` | Anpassade data |
| [Sessionsdata](#session) | Information om besökarens beteende i sessionen vid åtkomst till aktiviteten. | `Visitor Profile - [Attribute Name]` | Besöksprofil - början på det senaste besöket |
| URL-parametrar | Target undersöker URL-adressen för att extrahera URL-parametrarna. | `Custom - URL Parameter - [URL Parameter]` | Anpassade data |

Följande avsnitt innehåller detaljerad information om de olika datatyperna, inklusive attributnamn, beskrivningar och exempelvärden.

## Enhetsdata och mobildata {#device-mobile}

| Attributnamn | Attributbeskrivning | Exempelvärden |
| --- | --- | --- |
| Mobil - enhet - varumärke | Varumärket för den mobila enhet som besökaren använde för att få tillgång till aktiviteten. | Apple |
| Mobil - Enhet - eReader | Anger om enheten är en eReader. | 0 är Falskt, 1 är sant |
| Mobil - Enhet - spelkonsol | Anger om enheten är en spelkonsol. | 0 är Falskt, 1 är sant |
| Mobil - Enhet - Media Player | Anger om enheten är en mediespelare. | 0 är Falskt, 1 är sant |
| Mobil - Enhet - Mobiltelefon | Anger om enheten är en mobiltelefon. | 0 är Falskt, 1 är sant |
| Mobil - enhet - modellnamn | Modellnamnet på den mobila enhet som besökaren använde för att få åtkomst till aktiviteten. | iPhone XS |
| Enhet - digitalbox | Anger om enheten är en digitalbox. | 0 är Falskt, 1 är sant |
| Mobil - enhet - surfplatta | Anger om enheten är en surfplatta. | 0 är Falskt, 1 är sant |
| Mobil - pixeldensitet (ppi) | Den mobila enhetens pixeldensitet som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 osv. |
| Mobil - OS - OSX (Android, Windows osv.) | Anger om användaren använde en OSX (eller Android, Windows, osv.) enhet för att komma åt aktiviteten. | 0 är Falskt, 1 är sant |
| Mobil - skärmhöjd (px) | Den mobila enhetens skärmhöjd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. |
| Mobil - Skärmbredd (px) | Den mobila enhetens skärmbredd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. |

## Miljödata {#env}

| Attributnamn | Attributbeskrivning | Exempelvärden |
| --- | --- | --- |
| Webbläsare - veckodag | Veckodag då besökaren kom åt aktiviteten. | 0 till 6.<br>(0 är söndag) |
| Webbläsare - Timme på dagen | Timmen på dagen då besökaren kom åt aktiviteten. | 0 till 23<br>(0 är midnatt) |
| Webbläsare - Timme i veckan | Den timme i veckan då besökaren kom åt aktiviteten. | 0 till 168<br>(Söndag midnatt är 0) |
| Webbläsare - språkinställning | Det språk som anges i besökarens webbläsare som används för att komma åt aktiviteten. | Engelska<br>tyska |
| Webbläsare - Skärmhöjd (px) | Enhetens skärmhöjd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. |
| Webbläsare - tid på dagen | Tidpunkten då användaren öppnade aktiviteten. | 0, 6, 12, 18<br>(0 är natt, 6 är morgon,<br>12 är eftermiddag, 18 är kväll) |
| Webbläsare - tidszon | Besökarens tidszon när aktiviteten används. | Pacific Time<br>Eastern Time<br>GMT |
| Webbläsare - Typ | Vilken typ av webbläsare besökaren använde när aktiviteten användes. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Annat |
| Webbläsare - veckodag/helg | Arbetsstatus när besökaren kom åt aktiviteten (helg, arbetstid eller fritid på veckodag). | Lördag och söndag är helgdag<br>måndag-fredag 0900 till 1800 är arbetstid<br>måndag-fredag efter 1800 tills 0900 är ledig veckodag |
| Webbläsare - fönsterhöjd (px) | Webbläsarens fönsterhöjd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. |
| Webbläsare - Fönsterbredd (px) | Webbläsarens fönsterbredd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. |
| Enhet - skärmhöjd | Enhetens skärmhöjd som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 osv. |
| Enhet - skärmbredd | Enhetens skärmbredd som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 osv. |
| Operativsystem | Operativsystemet på besökarens enhet som används för att komma åt aktiviteten. | Mac OS<br>Windows<br>Linux<br>Sökbot<br>Okänt operativsystem |
| Operativsystem - version | Operativsystemets version som besökaren använde för att komma åt aktiviteten. | Windows 10<br>Mac OS 10 |
| Trafikkällor - URL för landningssida | Den första sidan som besökaren såg när han kom åt er webbplats. | `https://www.adobe.com/ecloud.html` |

## Geografiska data {#geo}

| Attributnamn | Attributbeskrivning | Exempelvärden |
| --- | --- | --- |
| Geo - ort | Den stad som besökaren kom åt aktiviteten från. | San Francisco |
| Geo - land | Det land från vilket besökaren kom åt aktiviteten. | Tyskland |
| Geo - DMA | Det utsedda marknadsföringsområdet (DMA) från vilket besökaren kom åt aktiviteten. | Charlottesville |
| Geo - Latitude | Latituden varifrån besökaren kom åt aktiviteten. | 47.269<br>Rundad till 3 decimaler (ca 100 meter noggrannhet) |
| Geo - longitud | Longitud från vilken besökaren kom åt aktiviteten. | -122.269<br>Rundat till 3 decimaler (ca 100 meter noggrannhet) |
| Geo - delstat/region | Det läge eller den region som besökaren kom åt aktiviteten från. | Utah<br>New South Wales |
| Geo - postnummer | Postnumret som besökaren kom åt aktiviteten från. | 84004 |
| Mobil - fraktfirma | Mobiloperatören som besökaren använde vid åtkomsten till aktiviteten. | Vodafone<br>T-Mobile |
| Nätverk - anslutningshastighet | Enhetens nätverksanslutningshastighet när besökaren kom åt aktiviteten. | Bredband<br>Kabel<br>DSL<br>Mobil<br>Trådlöst<br>Satellit |
| Nätverk - domännamn | Namnet på nätverksdomänen som besökaren kom åt aktiviteten från. | `nnt.net` |
| Nätverk - ISP | Det nätverk som besökaren kom åt aktiviteten från. | företag för intern kommunikation |

## Sessionsdata {#session}

| Attributnamn | Attributbeskrivning | Exempelvärden |
| --- | --- | --- |
| Besöksprofil - beställningsvärde för livstid för aktivitet | Anger summan av alla ordervärden för alla besök/sessioner för en viss aktivitet. | Dubbel |
| Besöksprofil - livstid för aktivitet på plats | Anger besökarens totala tid som tillbringats på platsen, exklusive den aktuella sessionen, och uppdateras när sessionen förfaller. | Dubbla, millisekunder |
| Besöksprofil - Genomsnittlig sidvisning per besök under aktiviteten | Anger det genomsnittliga antalet sidvisningar per session, exklusive den aktuella sessionen. | Dubbel |
| Besöksprofil - genomsnittlig tid per besök | Anger den genomsnittliga tiden per besök/session. Detta inkluderar inte den aktuella sessionen. | Dubbla, millisekunder |
| Besöksprofil - första besök | Anger tidpunkten för det första besöket som användaren interagerade med Target. | Dubbla, millisekunder |
| Besöksprofil - timmar sedan senaste besök | Anger timmarna sedan det senaste besöket på den här aktiviteten. | Dubbel (endast positivt heltal) 1, 2, 3 osv. |
| Besökarprofil - Impressions of Location/Content | Anger antalet visningar för en viss plats/innehållskombination i en viss aktivitet. | Dubbel (endast positivt heltal) 1, 2, 3 osv. |
| Besöksprofil - senaste målinteraktion | Anger tiden för senaste interaktion med Target. Interaktion sker vid varje [!DNL Target]-begäran eftersom den aktuella implementeringen av [!DNL Target] uppdaterar profilen vid varje begäran. | Dubbla, millisekunder |
| Besökarprofil - Sidor som visas före aktivitet | Anger det totala antalet sidvisningar (visningar), inklusive aktuellt besök/session tills besökaren går in i aktiviteten. | Dubbel (endast positivt heltal) 1, 2, 3 osv. |
| Besöksprofil - sidvyer i aktuellt besök | Anger antalet sidvisningar under det aktuella besöket/sessionen tills besökaren går in i aktiviteten. Mer exakt, antalet visningar. Dessa visningar är inte riktiga sidvyer, utan det är det antal gånger som begäran har nått Target. Målet kan inte skilja mellan tidsgränser eller andra orsaker till att användaren inte tog emot eller visade innehållet. | Dubbel (endast positivt heltal) |
| Besöksprofil - start av aktuellt besök | Anger den tidpunkt då det aktuella besöket/sessionen med Target påbörjades. Besöken hos Target kan initieras utan att någon aktivitet behöver utföras. Allt som krävs är ett anrop till en [!DNL Target]-begäran. En besökare kan ta en stund tills aktiviteten aktiveras och ögonblicksbilden tas. | Dubbla, millisekunder |
| Besöksprofil - början på det senaste besöket | Anger tidpunkten för när det senaste besöket/sessionen med Target startades. Det här attributet uppdateras när sessionen förfaller.<br>Om detta är den första sessionen för besökaren resulterar det i  `LAST_SESSION_START = 0.` | Dubbla, millisekunder |
| Besöksprofil - tid sedan senaste besök vid första starten av aktiviteten | Anger längden mellan föregående session och tiden då användaren går in i aktiviteten och ögonblicksbilden utförs. | Dubbla, millisekunder |
| Besöksprofil - tid på besök innan aktiviteten påbörjas | Anger skillnaden mellan den senaste interaktionen med Target och när det aktuella besöket börjar. Detta attribut kan betraktas som besöks-/sessionslängd tills användaren går in i aktiviteten och ögonblicksbilden utförs.<br>Negativa värden inträffar när sessionen startar och den senaste uppdateringstiden aktiveras av samma  [!DNL Target] anrop. Negativa värden ska betraktas som 0 (noll). | Dubbla, millisekunder |
| Besöksprofil -Totalt antal besök | Anger totalt antal besök/sessioner. Inkluderar inte aktuellt besök/session. | Dubbel (endast positivt heltal) 1, 2, 3 osv. |
| Besöksprofil - Totalt antal besök till aktivitet | Anger antalet besök för en viss aktivitet. Om det inte finns något tidigare besök returneras 0 (noll). | Dubbel (endast positivt heltal) 1, 2, 3 osv. |
| Besökarprofil - Totalt antal besök till aktivitet med konvertering | Anger antalet besök/sessioner för en viss aktivitet när det fanns minst en konvertering under besöket. | Dubbel |
| Besöksprofil - Besök aktivitet utan konvertering | Antal besök/sessioner utan konverteringar till en viss aktivitet. Det här värdet återställs till noll efter konvertering eller till -1 om konvertering aldrig inträffar. | Dubbel (endast positivt heltal) 1, 2, 3 osv. |
