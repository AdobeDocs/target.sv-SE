---
keywords: miljödata;sessionsdata;geodata;geografiska data;enhetsdata;mobildata;attribut;profilattribut;personaliseringsalgoritmer;maskininlärningsalgoritmer;maskininlärningsalgoritmer
description: Läs vilka data Adobe [!DNL Target] samlar in och använder för att skapa maskininlärningsalgoritmer.
title: Vilka data samlas in för att skapa algoritmer för maskininlärning?
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 32f2c32c697f5afa169d9e453fdc454dda533f8b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# ![PREMIUM](/help/assets/premium.png) Data som används av [!DNL Target] maskininlärningsalgoritmer

[!DNL Adobe Target] samlar automatiskt in och använder en mängd data för att bygga upp personaliseringsalgoritmer i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT) verksamhet. När en besökare går in i en AP- eller AT-aktivitet skickas en ögonblicksbild av information till en uppsättning&quot;utbildningsposter&quot; (de besökardata som personaliseringsalgoritmerna kommer att lära sig).

Läs mer om [!DNL Target] personaliseringsalgoritmer, se [Slumpmässig skogsalgoritm](/help/c-activities/t-automated-personalization/algo-random-forest.md).

## Standard [!DNL Adobe Target] attributkategorier

I följande tabell visas de data som samlats in av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] aktiviteter som standard, utan någon konfiguration av [!DNL Target] eller andra [!DNL Adobe] lösningar, liksom namnkonventionen som används för att ange dessa attribut i [Insikter om personalisering - rapporter](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Du kan när som helst utöka indatauppsättningen. Mer information om hur du överför ytterligare data finns i [Överför data för [!DNL Target] personaliseringsalgoritmer](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Datakategori | Systemprefix | Beskrivning | Visningsnamn i [!UICONTROL Insights] rapporter |
| --- | --- | --- | --- |
| Miljöparametrar | ENV | Information om en användares miljö, inklusive operativsystem, webbläsare och tid på veckodag/dag. | Webbläsare - [Attributnamn]<br>Operativsystem - [Värde] |
| Geografi | GEO | Information om en användares geografi, som hämtas via IP-sökning. | Geo - [geo-attribut] |
| Mobil enhet | MOB | Information om en användares mobila enhet. | Enhet - [enhetsattribut]<br>Mobil - [mobilattribut] |
| Målrapporteringssegment | SEG | Rapporteringssegment konfigurerade i [!DNL Target] rapportering. | Rapporteringssegment -[Segmentnamn] |
| Sessionsbeteende | SE | Information om användarbeteende, till exempel hur många sidor som visas. | Besökarprofil - [Attributnamn] |

## Egna Adobe Target-attributkategorier

I följande tabell visas kunddata som samlats in av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] verksamhet. Dessa data samlas bara in om du anger dem. Specifika attributnamn och exempelvärden är specifika för systemkonfigurationen.

| Datakategori | Systemprefix | Beskrivning | Visningsnamn i [!UICONTROL Insights] rapporter |
| --- | --- | --- | --- |
| Sidparametrar | RUTA | Anpassade sidparametrar (&quot;mbox parameters&quot;) skickades i anropet till [!DNL Target]. | Anpassad - Mbox-parameter - [parameternamn] |
| [!DNL Target] profil | PRO | Anpassade profilattribut som har överförts direkt till [!DNL Target] profil via API eller sidparameter och [!DNL Target] profilskript. | Anpassad - besökarprofil - [attributnamn] |
| Kundattribut | CRS | Kundattribut överförda till [!DNL Target] via [Adobe Experience Cloud Customer Attributes Service](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Anpassad - besökarprofil - [attributnamn] |
| URL-parametrar | URL | URL och eventuella URL-parametrar för den sida som visas för tillfället. | Anpassad - URL-parameter - [URL-parameter] |
| Refererande URL | REF | Refererande URL och eventuella URL-parametrar för den refererande URL:en. | Anpassad - [Refererande URL-parameter] - [Parametervärde] |
| Adobe Experience Cloud delade målgrupper | AAM | Alla målgrupper som delas med [!DNL Target] från andra [!DNL Adobe Experience Cloud] lösningar (till exempel [!DNL Adobe Audience Manager] och [!DNL Adobe Analytics], via [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Anpassad - Experience Cloud-målgrupp - [Målgruppsnamn] |
| Adobe Experience Platform RTCDP-målgrupper | UPS | AEP RTCDP-målgrupper delade med [!DNL Target] via Destinationer. |  |

## Blockera funktioner från [!DNL Target] maskininlärningsalgoritmer

Funktioner kan blockeras från [!DNL Target] maskininlärningsalgoritmer som förhindrar att de används i [!UICONTROL Auto-Target] eller [!UICONTROL Automated Personalization] modell eller aktivitet.

Så här blockerar du en kategori med funktioner från [!DNL Target] maskininlärningsalgoritmer, kontakta [Adobe kundtjänst](/help/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) och ange de funktionskategorier som du vill blockera med hjälp av systemprefixen ovan.

Blockera en eller flera specifika funktioner från [!DNL Target] maskininlärningsalgoritmer, kontakta [Adobe kundtjänst](/help/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) och ange de specifika funktionsnamn som ska blockeras med hjälp av nedanstående systemnamn. Följande avsnitt innehåller detaljerad information om de olika datatyperna, inklusive attributnamn, beskrivningar och exempelvärden.

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
| Mobil - pixeldensitet (ppi) | Den mobila enhetens pixeldensitet som besökaren använde för att komma åt aktiviteten. | 1, 2, 3 osv. | MOB_targeting.mobile.displayPpi |
| Mobil - OS - OSX (Android, Windows osv.) | Anger om användaren använde en OSX (eller Android, Windows, osv.) enhet för att komma åt aktiviteten. | 0 är Falskt, 1 är sant | MOB_targeting.mobile.os[OS]<br>Till exempel MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobil - skärmhöjd (px) | Den mobila enhetens skärmhöjd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. | MOB_targeting.mobile.displayHeight |
| Mobil - Skärmbredd (px) | Den mobila enhetens skärmbredd (i pixlar) som besökaren använde för att få åtkomst till aktiviteten. | 1, 2, 3 osv. | MOB_targeting.mobile.displayWidth |

## Miljödata {#env}

|Attributnamn|Attributbeskrivning|Exempelvärden|Systemnamn| | — | — | — | — | |Webbläsare - veckodag|Den veckodag då besökaren kom åt aktiviteten.|0 till 6.<br>(0 är söndag)|ENV_DayOfWeek| |Webbläsare - Timme på dagen|Timmen på dagen då besökaren kom åt aktiviteten.|0 till 23<br>(0 är midnatt)|ENV_UserHour| |Webbläsare - Timme i veckan|Den timme i veckan då besökaren kom åt aktiviteten.|0 till 168<br>(Söndag midnatt är 0)|ENV_WeekHour| |Webbläsare - språkinställning|Det språk som anges i besökarens webbläsare används för att komma åt aktiviteten.|Engelska<br>German|ENV_Language| |Webbläsare - Tid på dagen|Tidpunkt på webbläsarens dag när besökaren kom åt aktiviteten.|0, 6, 12, 18<br>(0 är natt, 6 är morgon,<br>12 är eftermiddag, 18 är kväll)|ENV_LocalTimePeriod| |Webbläsare - tidszon|Besökarens tidszon när aktiviteten används.|Stillahavstid<br>Eastern Time<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |Webbläsare - typ|Den typ av webbläsare besökaren använde när aktiviteten öppnades.|Krom<br>Firefox<br>Internet Explorer<br>Safari<br>Annat|ENV_Browser| |Webbläsare - Veckodag/helg|Arbetsstatus när besökaren kom åt aktiviteten (helg, arbetstimmar eller veckodag ledig tid).|Lördag och söndag är helger<br>Måndag-fredag 0900 till 1800 är arbetstid<br>Måndag-fredag efter 1800 till 0900 är veckodag ledig tid|ENV_UserHourType| |Webbläsare - Fönsterhöjd (px)|Webbläsarens fönsterhöjd (i pixlar) som besökaren använde för att komma åt aktiviteten.|1, 2, 3 osv.|ENV_BrowserHeight| |Webbläsare - Fönsterbredd (px)|Webbläsarens fönsterbredd (i pixlar) som besökaren använde för att komma åt aktiviteten.|1, 2, 3 osv.|ENV_BrowserWidth| |Enhet - Skärmhöjd (px)|Enhetens skärmhöjd som besökaren använde för att komma åt aktiviteten.|1, 2, 3 osv.|ENV_ScreenHeight| |Enhet - Skärmbredd (px)|Enhetens skärmbredd som besökaren använde för att komma åt aktiviteten.|1, 2, 3 osv.|ENV_ScreenWidth| |Operativsystem|Operativsystemet på besökarens enhet som används för att komma åt aktiviteten.|Mac OS<br>Windows<br>Linux<br>Sök i början<br>Okänt operativsystem|ENV_OperatingSystem| |Operativsystem - Version|Operativsystemets version som besökaren använde för att få åtkomst till aktiviteten.|Windows 10<br>Mac OS 10|ENV_OperatingSystemVersion| |Trafikkällor - Refererande landningssidans URL|Den första sidan som besökaren såg när han kom åt webbplatsen.|`https://www.adobe.com/ecloud.html`|ENV_Referer|

## Geografiska data {#geo}

| Attributnamn | Attributbeskrivning | Exempelvärden | Systemnamn |
| --- | --- | --- | --- |
| Geo - ort | Den stad som besökaren kom åt aktiviteten från. | San Francisco | Geo_stad |
| Geo - land | Det land från vilket besökaren kom åt aktiviteten. | Tyskland | Geo_Country |
| Geo - DMA | Det utsedda marknadsföringsområdet (DMA) från vilket besökaren kom åt aktiviteten. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latituden varifrån besökaren kom åt aktiviteten. | 47.269<br>Avrundat till 3 decimaler (ca 100 meter noggrannhet) | GEO_Latitude |
| Geo - longitud | Longitud från vilken besökaren kom åt aktiviteten. | -122.269<br>Avrundat till 3 decimaler (ca 100 meter noggrannhet) | GEO_Longitud |
| Geo - delstat/region | Det läge eller den region som besökaren kom åt aktiviteten från. | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - postnummer | Postnumret som besökaren kom åt aktiviteten från. | 84004 | GEO_ZipCode |
| Mobil - fraktfirma | Mobiloperatören som besökaren använde vid åtkomsten till aktiviteten. | Vodafone<br>T-Mobile | GEO_mobileCarrier |
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
| Besöksprofil - första besök | Anger tidpunkten för det första besök som användaren interagerade med [!DNL Target]. | Dubbla, millisekunder | SES_PROFILE_CREATION_TIME |
| Besöksprofil - timmar sedan senaste besök | Anger timmarna sedan det senaste besöket på den här aktiviteten. | Dubbel (endast positivt heltal) 1, 2, 3 osv. | SES_HOURS_SINCE_LAST_VISIT |
| Besökarprofil - Impressions of Location/Content | Anger antalet visningar för en viss plats/innehållskombination i en viss aktivitet. | Dubbel (endast positivt heltal) 1, 2, 3 osv. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Besöksprofil - senaste [!DNL Target] Interaktion | Anger tiden för senaste interaktion med [!DNL Target]. Interaktion sker på varje [!DNL Target] begäran eftersom den aktuella implementeringen av [!DNL Target] uppdaterar profilen för varje begäran. | Dubbla, millisekunder | SES_PROFILE_UPDATE_TIME |
| Besökarprofil - Sidor som visas före aktivitet | Anger det totala antalet sidvisningar (visningar), inklusive aktuellt besök/session tills besökaren går in i aktiviteten. | Dubbel (endast positivt heltal) 1, 2, 3 osv. | SES_TOTAL_PAGE_VIEWS |
| Besöksprofil - sidvyer i aktuellt besök | Anger antalet sidvisningar under det aktuella besöket/sessionen tills besökaren går in i aktiviteten. Mer exakt, antalet visningar. Dessa visningar är inte riktiga sidvyer, utan det är det antal gånger som begäran har nått Target. Målet kan inte skilja mellan tidsgränser eller andra orsaker till att användaren inte tog emot eller visade innehållet. | Dubbel (endast positivt heltal) | SES_SESSION_POSITION |
| Besöksprofil - start av aktuellt besök | Anger den tidpunkt då det aktuella besöket/sessionen med Target påbörjades. Besöken hos Target kan initieras utan att någon aktivitet behöver utföras. Allt som krävs är ett samtal till alla [!DNL Target] begäran. En besökare kan ta en stund tills aktiviteten aktiveras och ögonblicksbilden tas. | Dubbla, millisekunder | SES_SESSION_START |
| Besöksprofil - början på det senaste besöket | Anger tidpunkten för senaste besök/session med [!DNL Target] igång. Det här attributet uppdateras när sessionen förfaller.<br>Om detta är den första sessionen för besökaren resulterar det i `LAST_SESSION_START = 0.` | Dubbla, millisekunder | SES_LAST_SESSION_START |
| Besöksprofil - tid sedan senaste besök vid första starten av aktiviteten | Anger längden mellan föregående session och tiden då användaren går in i aktiviteten och ögonblicksbilden utförs. | Dubbla, millisekunder | SES_RECENCY |
| Besöksprofil - tid på besök innan aktiviteten påbörjas | Anger skillnaden mellan den senaste interaktionen med [!DNL Target] och när det aktuella besöket började. Detta attribut kan betraktas som besöks-/sessionslängd tills användaren går in i aktiviteten och ögonblicksbilden utförs.<br>Negativa värden inträffar när sessionen startar och den senaste uppdateringstiden aktiveras av samma [!DNL Target] ring. Negativa värden ska betraktas som 0 (noll). | Dubbla, millisekunder | SES_SESSION_TIME |
| Besöksprofil -Totalt antal besök | Anger totalt antal besök/sessioner. Inkluderar inte aktuellt besök/session. | Dubbel (endast positivt heltal) 1, 2, 3 osv. | SES_TOTAL_SESSIONS |
| Besöksprofil - Totalt antal besök till aktivitet | Anger antalet besök för en viss aktivitet. Om det inte finns något tidigare besök returneras 0 (noll). | Dubbel (endast positivt heltal) 1, 2, 3 osv. | SES_PREVIOUS_VISIT_COUNT |
| Besökarprofil - Totalt antal besök till aktivitet med konvertering | Anger antalet besök/sessioner för en viss aktivitet när det fanns minst en konvertering under besöket. | Dubbel | SES_CUMULATIVE_SUCCESSES |
| Besöksprofil - Besök aktivitet utan konvertering | Antal besök/sessioner utan konverteringar till en viss aktivitet. Det här värdet återställs till noll efter konvertering eller till -1 om konvertering aldrig inträffar. | Dubbel (endast positivt heltal) 1, 2, 3 osv. | SES_SUCCESS_RECENCY |
