---
keywords: miljödata;sessionsdata;geodata;geografiska data;enhetsdata;mobildata;attribut;profilattribut;personaliseringsalgoritmer;maskininlärningsalgoritmer;maskininlärningsalgoritmer
description: Lär dig vilka data [!DNL Adobe Target] samlar in och använder för att skapa maskininlärningsalgoritmer.
title: Vilka data samlas in för att skapa algoritmer för maskininlärning?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '1967'
ht-degree: 0%

---

# Data som används av [!DNL Target] maskininlärningsalgoritmer

[!DNL Adobe Target] samlar automatiskt in och använder olika data för att skapa sina personaliseringsalgoritmer i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT)-aktiviteter. När en besökare går in i en [!UICONTROL Automated Personalization]- eller [!UICONTROL Auto-Target]-aktivitet skickas en ögonblicksbild av information till en uppsättning&quot;utbildningsposter&quot; (de besökardata som personaliseringsalgoritmerna lär sig om).

Mer information om personaliseringsalgoritmerna [!DNL Target] finns i [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Standardattributkategorier för [!DNL Target]

I följande tabell visas de data som samlats in av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] aktiviteter som standard, utan någon konfiguration av [!DNL Target] eller andra [!DNL Adobe]-lösningar. Tabellen innehåller också den namnkonvention som används för att ange dessa attribut i [Personalization Insights Reports](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Du kan när som helst utöka indatauppsättningen. Mer information om hur du överför ytterligare data finns i [Överföra data för  [!DNL Target] personaliseringsalgoritmerna](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Datakategori | Systemprefix | Beskrivning | Visningsnamn i [!UICONTROL Insights] rapporter |
| --- | --- | --- | --- |
| Miljöparametrar | ENV | Information om en användares miljö, inklusive operativsystem, webbläsare och tid på veckodag/dag. | Webbläsare - [Attributnamn]<br>Operativsystem - [värde] |
| Geografi | GEO | Information om en användares geografi, som hämtas via IP-sökning. | Geo - [geo-attribut] |
| Mobil enhet | MOB | Information om en användares mobila enhet. | Enhet - [enhetsattribut]<br>Mobil - [mobilattribut] |
| [!DNL Target] rapporteringssegment | SEG | Rapporteringssegment konfigurerade i [!DNL Target]-rapportering. | Rapporteringssegment -[Segmentnamn] |
| Sessionsbeteende | SE | Information om användarbeteende, t.ex. antalet sidor som visas. | Besökarprofil - [Attributnamn] |

## Anpassade [!DNL Target]-attributkategorier

I följande tabell visas kunddata som samlats in av [!UICONTROL Automated Personalization]- och [!UICONTROL Auto-Target]-aktiviteter. Dessa data samlas bara in om du anger dem. Specifika attributnamn och exempelvärden är specifika för din systemkonfiguration.

| Datakategori | Systemprefix | Beskrivning | Visningsnamn i [!UICONTROL Insights] rapporter |
| --- | --- | --- | --- |
| Sidparametrar | RUTA | Anpassade sidparametrar (&quot;mbox parameters&quot;) skickades i anropet till [!DNL Target]. | Anpassad - Mbox-parameter - [parameternamn] |
| Profil för [!DNL Target] | PRO | Anpassade profilattribut överförs direkt till profilen [!DNL Target] via API- eller sidparameter och [!DNL Target]-profilskript. | Anpassad - besökarprofil - [attributnamn] |
| Kundattribut | CRS | Kundattribut överfördes till profilen [!DNL Target] via [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Anpassad - besökarprofil - [attributnamn] |
| URL-parametrar | URL | URL och eventuella URL-parametrar för den sida som visas. | Anpassad - URL-parameter - [URL-parameter] |
| Refererande URL | REF | Refererande URL och eventuella URL-parametrar för den refererande URL:en. | Anpassad - [Refererande URL-parameter] - [Parametervärde] |
| [!DNL Adobe Experience Cloud] delade målgrupper | AAM | Alla målgrupper som delas med [!DNL Target] från andra [!DNL Adobe Experience Cloud]-lösningar (till exempel [!DNL Adobe Audience Manager] och [!DNL Adobe Analytics] via [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Anpassad - Experience Cloud-målgrupp - [målgruppsnamn] |
| [!DNL Adobe Experience Platform Real-time CDP] målgrupper | UPS | CDP-målgrupper i realtid för plattform delade med [!DNL Target] via [!UICONTROL Destinations]. |  |
| [!DNL Adobe Experience Platform Real-time CDP] attribut | AEP | CDP-attribut i realtid för plattformen delade med [!DNL Target] via [!UICONTROL Destinations]. |  |

## Blockera funktioner från [!DNL Target] maskininlärningsalgoritmer

Funktioner kan blockeras från [!DNL Target] maskininlärningsalgoritmer, vilket förhindrar att de används i någon [!UICONTROL Automated Personalization]- eller [!UICONTROL Auto-Target]-modell eller aktivitet.

Mer information finns i [Översikt över API:t för modeller (Blockeringslistning)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} i *[!DNL Adobe Target]Utvecklarhandbok*.

## Enhetsdata och mobildata {#device-mobile}

| Attributnamn | Attributbeskrivning | Exempelvärden | Systemnamn |
| --- | --- | --- | --- |
| Mobil - enhet - varumärke | Varumärket för den mobila enhet som besökaren använde för att få tillgång till aktiviteten. | Apple | MOB_targeting.mobile.vendor |
| Mobil - Enhet - eReader | Anger om enheten är en eReader. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.Reader |
| Mobil - Enhet - spelkonsol | Anger om enheten är en spelkonsol. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.gamesConsole |
| Mobil - Enhet - Media Player | Anger om enheten är en mediespelare. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.mediaPlayer |
| Mobil - Enhet - Mobiltelefon | Anger om enheten är en mobiltelefon. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.mobilePhone |
| Mobil - enhet - modellnamn | Modellnamnet på den mobila enhet som besökaren använde för att få åtkomst till aktiviteten. | iPhone XS | MOB_targeting.mobile.model |
| Enhet - digitalbox | Anger om enheten är en digitalbox. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.setTopBox |
| Mobil - enhet - surfplatta | Anger om enheten är en surfplatta. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.tablet |
| Mobil - pixeldensitet (ppi) | Den mobila enhetens pixeldensitet som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 och så vidare. | MOB_targeting.mobile.displayPpi |
| Mobil - OS - OS X ([!DNL Android], [!DNL Windows] och så vidare) | Anger om användaren använde en OSX-enhet (eller [!DNL Android], [!DNL Windows] och så vidare) för att få åtkomst till aktiviteten. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.os[OS]<br>Till exempel MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobil - skärmhöjd (px) | Den mobila enhetens skärmhöjd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 och så vidare. | MOB_targeting.mobile.displayHeight |
| Mobil - Skärmbredd (px) | Den mobila enhetens skärmbredd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 och så vidare. | MOB_targeting.mobile.displayWidth |

## Miljödata {#env}

| Attributnamn | Attributbeskrivning | Exempelvärden | Systemnamn |
| --- | --- | --- | -- |
| Webbläsare - veckodag | Veckodag då besökaren kom åt aktiviteten. | 0-6.<br>(0 är söndag) | ENV_DayOfWeek |
| Webbläsare - Timme på dagen | Timmen på dagen då besökaren kom åt aktiviteten. | 0 - 23<br>(0 är midnatt) | ENV_UserHour |
| Webbläsare - Timme i veckan | Den timme i veckan då besökaren kom åt aktiviteten. | 0 - 168<br>(Söndag midnatt är 0) | ENV_WeekHour |
| Webbläsare - språkinställning | Det språk som anges i besökarens webbläsare som används för att komma åt aktiviteten. | Engelska<br>tyska | ENV_Language |
| Webbläsare - tid på dagen | Tidpunkten då användaren öppnade aktiviteten. | 0, 6, 12, 18<br>(0 är natt, 6 är morgon,<br>12 är eftermiddag, 18 är kväll) | ENV_LocalTimePeriod |
| Webbläsare - tidszon | Besökarens tidszon när aktiviteten används. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Webbläsare - Typ | Vilken typ av webbläsare besökaren använde när aktiviteten användes. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>Annan | ENV_Browser |
| Webbläsare - veckodag/helg | Arbetsstatus när besökaren kom åt aktiviteten (helg, arbetstid eller fritid på veckodag). | Lördag och söndag är helgdag<br>Måndag-fredag 0900 - 1800 är arbetstid<br>Måndag-fredag efter 1800 tills 0900 är ledig veckodag | ENV_UserHourType |
| Webbläsare - fönsterhöjd (px) | Webbläsarens fönsterhöjd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 och så vidare, | ENV_BrowserHeight |
| Webbläsare - Fönsterbredd (px) | Webbläsarens fönsterbredd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 och så vidare, | ENV_BrowserWidth |
| Enhet - skärmhöjd (px) | Enhetens skärmhöjd som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 och så vidare, | ENV_ScreenHeight |
| Enhet - Skärmbredd (px) | Enhetens skärmbredd som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 och så vidare, | ENV_ScreenWidth |
| Operativsystem | Operativsystemet på besökarens enhet som används för att komma åt aktiviteten. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Sökbot<br>Okänt operativsystem | ENV_OperatingSystem |
| Operativsystem - version | Operativsystemets version som besökaren använde för att komma åt aktiviteten. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Trafikkällor - URL för landningssida | Den första sidan som besökaren såg när han kom åt er webbplats. | `https://www.adobe.com/ecloud.html` | ENV_Referer |

## Geografiska data {#geo}

| Attributnamn | Attributbeskrivning | Exempelvärden | Systemnamn |
| --- | --- | --- | --- |
| Geo - ort | Den stad som besökaren kom åt aktiviteten från. | San Francisco | Geo_stad |
| Geo - land | Det land från vilket besökaren kom åt aktiviteten. | Tyskland | Geo_Country |
| Geo - DMA | Det utsedda marknadsföringsområdet (DMA) från vilket besökaren kom åt aktiviteten. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latituden varifrån besökaren kom åt aktiviteten. | 47.269<br>Rundad till 3 decimaler (ca 100 meter noggrannhet) | GEO_Latitude |
| Geo - longitud | Longitud från vilken besökaren kom åt aktiviteten. | -122.269<br>Rundad till 3 decimaler (ca 100 meter noggrannhet) | GEO_Longitud |
| Geo - region | Det läge eller den region som besökaren kom åt aktiviteten från. | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - postnummer | Postnumret som besökaren kom åt aktiviteten från. | 84004 | GEO_ZipCode |
| Mobil - transportör | Mobiloperatören som besökaren använde vid åtkomsten till aktiviteten. | [!DNL Vodafone]<br>[!DNL T-Mobile] | GEO_mobileCarrier |
| Nätverk - anslutningshastighet | Enhetens nätverksanslutningshastighet när besökaren kom åt aktiviteten. | Bredband<br>Kabel<br>DSL<br>Mobil<br>Trådlöst<br>Satellit | GEO_ConnectionSpeed |
| Nätverk - domännamn | Namnet på nätverksdomänen som besökaren kom åt aktiviteten från. | `nnt.net` | GEO_DomainName |
| Nätverk - ISP | Det nätverk som besökaren kom åt aktiviteten från. | företag för intern kommunikation | GEO_ISPName |

## Sessionsdata {#session}

| Attributnamn | Attributbeskrivning | Exempelvärden | Systemnamn |
| --- | --- | --- | --- |
| Besöksprofil - beställningsvärde för livstid för aktivitet | Anger summan av alla ordervärden för alla besök/sessioner för en viss aktivitet. | Dubbel | SES_CUMULATIVE_ORDER_VALUE |
| Besöksprofil - livstid för aktivitet på plats | Anger besökarens totala tid som tillbringats på platsen, exklusive den aktuella sessionen, och uppdateras när sessionen förfaller. | Dubbla, millisekunder | SES_TOTAL_TIME |
| Besöksprofil - Genomsnittlig sidvisning per besök under aktiviteten | Anger det genomsnittliga antalet sidvisningar per session, exklusive den aktuella sessionen. | Dubbel | SES_REQUESTS_PER_SESSION |
| Besöksprofil - genomsnittlig tid per besök | Anger den genomsnittliga tiden per besök/session. Detta inkluderar inte den aktuella sessionen. | Dubbla, millisekunder | SES_TIME_PER_SESSION |
| Besöksprofil - första besök | Anger tiden för det första besöket som användaren interagerade med [!DNL Target]. | Dubbla, millisekunder | SES_PROFILE_CREATION_TIME |
| Besöksprofil - timmar sedan senaste besök | Anger timmarna sedan det senaste besöket på den här aktiviteten. | Dubbel (endast positivt heltal) 1, 2, 3 och så vidare. | SES_HOURS_SINCE_LAST_VISIT |
| Besökarprofil - Impressions of Location/Content | Anger antalet visningar för en viss plats/innehållskombination i en viss aktivitet. | Dubbel (endast positivt heltal) 1, 2, 3 och så vidare. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Besökarprofil - senaste [!DNL Target]-interaktion | Anger tiden för senaste interaktion med [!DNL Target]. Interaktion sker för varje [!DNL Target]-begäran eftersom den aktuella implementeringen av [!DNL Target] uppdaterar profilen för varje begäran. | Dubbla, millisekunder | SES_PROFILE_UPDATE_TIME |
| Besökarprofil - Sidor som visas före aktivitet | Anger det totala antalet sidvisningar (visningar), inklusive aktuellt besök/session tills besökaren går in i aktiviteten. | Dubbel (endast positivt heltal) 1, 2, 3 och så vidare. | SES_TOTAL_PAGE_VIEWS |
| Besöksprofil - sidvyer i aktuellt besök | Anger antalet sidvisningar i det aktuella besöket/sessionen tills besökaren går in i aktiviteten. Mer exakt, antalet visningar. De här avtrycken är inte riktiga sidvyer, utan det är det antal gånger som begäran har nått [!DNL Target]. [!DNL Target] kan inte skilja mellan tidsgränser eller andra orsaker som användaren inte tog emot eller visade innehållet. | Dubbel (endast positivt heltal) | SES_SESSION_POSITION |
| Besöksprofil - start av aktuellt besök | Anger den tid då det aktuella besöket/sessionen med [!DNL Target] påbörjades. Besöken hos [!DNL Target] kan initieras utan att någon aktivitet anges. Allt som krävs är ett anrop till en [!DNL Target]-begäran. En besökare kan ta en stund innan aktiviteten aktiveras och ögonblicksbilden tas. | Dubbla, millisekunder | SES_SESSION_START |
| Besöksprofil - start av senaste besök | Anger tidpunkten då det senaste besöket/sessionen med [!DNL Target] påbörjades. Det här attributet uppdateras när sessionen förfaller.<br>Om detta är den första sessionen för besökaren resulterar det i `LAST_SESSION_START = 0.` | Dubbla, millisekunder | SES_LAST_SESSION_START |
| Besöksprofil - tid sedan senaste besök vid första starten av aktiviteten | Anger längden mellan föregående session och tiden då användaren går in i aktiviteten och ögonblicksbilden utförs. | Dubbla, millisekunder | SES_RECENCY |
| Besöksprofil - tid på besök innan aktiviteten påbörjas | Anger skillnaden mellan den senaste interaktionen med [!DNL Target] och när det aktuella besöket påbörjades. Detta attribut kan betraktas som besöks-/sessionslängd tills användaren går in i aktiviteten och ögonblicksbilden utförs.<br>Negativa värden inträffar när sessionens början och den senaste uppdateringstiden aktiveras av samma [!DNL Target]-anrop. Negativa värden ska betraktas som 0 (noll). | Dubbla, millisekunder | SES_SESSION_TIME |
| Besöksprofil -Totalt antal besök | Anger totalt antal besök/sessioner. Inkluderar inte aktuellt besök/session. | Dubbel (endast positivt heltal) 1, 2, 3 och så vidare. | SES_TOTAL_SESSIONS |
| Besöksprofil - Totalt antal besök till aktivitet | Anger antalet besök för en viss aktivitet. Om det inte finns något tidigare besök returneras 0 (noll). | Dubbel (endast positivt heltal) 1, 2, 3 och så vidare. | SES_PREVIOUS_VISIT_COUNT |
| Besökarprofil - Totalt antal besök till aktivitet med konvertering | Anger antalet besök/sessioner för en viss aktivitet när det fanns minst en konvertering under besöket. | Dubbel | SES_CUMULATIVE_SUCCESSES |
| Besöksprofil - Besök aktivitet utan konvertering | Antal besök/sessioner utan konverteringar till en viss aktivitet. Det här värdet återställs till noll efter konvertering eller till -1 om konvertering aldrig inträffar. | Dubbel (endast positivt heltal) 1, 2, 3 och så vidare. | SES_SUCCESS_RECENCY |
