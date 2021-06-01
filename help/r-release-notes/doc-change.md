---
keywords: måldokumentets ändringslogg;dokumentationsuppdateringar;nya ämnen;redigeringar;uppdateringar;uppdatera
description: Håll dig uppdaterad med viktiga tillägg och ändringar i produktdokumentationen för Adobe [!DNL Target] .
title: Var kan jag se dokumentationsuppdateringar för Target?
feature: Versionsinformation
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7bb1f896dd92b41d04eb0dfd39116ff1c132fe50
workflow-type: tm+mt
source-wordcount: '1338'
ht-degree: 0%

---

# Dokumentationsändringar

På den här sidan visas viktiga ändringar i [!DNL Adobe Target]-produktdokumentationen.

## Adobe [!DNL Target] Standard/Premium 21.4.1 (19 april 2021)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 1 juni | [CNAME och [!DNL Target]](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Följande frågor och svar har lagts till:<ul><li>Hur använder jag en länk för avanmälan med CNAME?</li></ul> |
|  | [Integritet](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Avsnittet&quot;Avanmäl dig&quot; har uppdaterats för att förklara hur du använder länken för avanmälan med CNAME. |
|  | [[!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Lagt till information om [!DNL Adobe Experience Platform Web SDK]. |
|  | [Analyser  [!DNL Target] för implementering](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform) | Nytt avsnitt har lagts till:<ul><li>Implementeringssteg för en [!DNL Adobe Experience Platform Web SDK]-implementering</li></ul> |
|  | [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) | Lagt till information om hur du använder omdirigeringserbjudanden med A4T och Platform Web SDK. |
|  | [Svarstoken](/help/administrating-target/response-tokens.md) | Lagt till information om att använda svarstoken med [!DNL Adobe Experience Platform Web SDK]. |
|  | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Lagt till information om Adobe Experience Platform Web SDK 2.6.0 (1 juni 2021). |
| 27 maj | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Avsnittet för [!DNL Target] API-anrop har lagts till. Gränsen är 50 anrop per minut. |
| 20 maj | [Enhetsbeslut](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | Länk har lagts till i följande blogginlägg på Adobe Tech Blog:<ul><li>Adobe Tech Blog - Del 2: Kör [!DNL Adobe Target] NodeJS SDK för experiment och personalisering på kantplattformar (AWS Lambda@Edge)</li></ul> |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Följande kända fel har lagts till: &quot;Arkivering av [!UICONTROL Auto Target]-aktiviteter kan orsaka synkroniseringsproblem.&quot; |
| 17 maj | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Ytterligare information om at.js 2.5.0. |
|  | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Uppdaterat ämne som indikerar att det finns förhandsgranskningslänkar tillgängliga för [!UICONTROL Automated Personalization]-aktiviteter (AP) med at.js 2.5.0 (och senare). |
|  | [Webbläsare som stöds](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Angiven att at.js 2.5.0-versionen tar bort stöd för Microsoft Internet Explorer 10, Internet Explorer 11 och alla äldre versioner. Microsoft Edge stöds fortfarande i at.js 2.5.0 och senare. |
|  | [Felsökning relaterade till  [!UICONTROL Enhanced Experience Composer]](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) | Listan över IP-adresser som ska tillåtslista har uppdaterats. |
| 12 maj | [[!DNL Target] versionsinformation (prerelease)](/help/r-release-notes/target-release-notes.md) | Förhandsversionsinformation har lagts till för följande:<ul><li>Adobe Experience Platform Web SDK (17 maj 2021)</li><li>Target Standard Premium 21.5.2</li></ul> |
| 10 maj | [[!DNL Recommendations] Vanliga frågor](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Följande frågor och svar har lagts till: &quot;Kan jag använda en algoritm som skapats i [!DNL Adobe Recommendations Classic] i [!DNL Recommendations Premium]?&quot; |
|  | [Implementering [!DNL Target] using [!DNL Dynamic Tag Manager] (DTM)](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md) | Anger att [!DNL Adobe Dynamic Tag Manager] inte längre stöds. I stället rekommenderar [!DNL Adobe] implementering med [[!DNL Adobe Experience Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). |
| 6 maj | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Följande frågor och svar har lagts till:<ul><li>Hur lång tid tar det att ändra konfigurationen för mina [!UICONTROL Recommendations]-aktiviteter, erbjudanden, kampanjer eller villkor så att de återspeglas på min webbplats?</li><li>Hur lång tid tar det för en användares beteende (till exempel att klicka på produkt A och köpa produkt B) att återspeglas i rekommendationerna *som*-användaren får?</li><li>Hur lång tid tar det för en användares beteende (till exempel att klicka på produkt A och köpa produkt B) att återspeglas i rekommendationerna *andra* användare får?</li></ul> |
|  | [Enhetsbeslut](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | Länk har lagts till i följande blogginlägg på Adobe Tech Blog:<ul><li>Del 1: Kör Adobe Target NodeJS SDK för experiment och personalisering på Edge-plattformar (Akamai Edge Workers)</li></ul> |
| 5 maj | [Målmeddelanden och evenemang](/help/r-release-notes/target-announcements.md) | Lagt till information om Adobe Target Community Q&amp;A Coffee Break som ska hållas onsdagen den 12 maj 2021 kl. 8.00. (PDT, GMT-7). |
| 27 april | [Cookie-inställningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | Uppdaterat ämne som indikerar att cookie-varaktighet (`deviceIdLifetime`-inställning) kan åsidosättas i version 2.3.1 eller senare av at.js. |
|  | [Adobe Target Guide](/help/target-home.md) | Ytterligare information om Adobe Summit. |
| 26 april | [Felsökning av On-device-beslut för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/troubleshooting-on-device-decisioning.md) | Nytt ämne. |
| 19 april | [Enhetsbeslut](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) | Följande nya artiklar har lagts till:<ul><li>[Enhetsbeslut](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)</li><li>[Funktioner som stöds för beslut på enheten](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)</li><li>[Regelartefakt för beslutsfattande på enhet](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#on-device-decisioning) | Lagt till information om `decisioningMethod`. |
|  | [adobe.target.getOffers() - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Följande har lagts till:<ul><li>Information om `decisioningMethod`-nyckeln.</li><li>Ett exempel på&quot;getCallOffers() för att fatta ett beslut på enheten&quot;.</li></ul> |
|  | [at.js, anpassade händelser](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Följande information har lagts till:<ul><li>Beslutsartifakt på enheten har slutförts</li><li>Avvikelsefakt på enheten misslyckades</li></ul> |
|  | [Verksamhet](/help/c-activities/activities.md) | Lagt till information om enhetsbeslut. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ytterligare information om at.js 2.5.0. |
|  | [Implementera mål utan tagghanterare](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) | Lagt till information om enhetsbeslut. |
|  | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Stöd för förhandsgranskningslänkar för [!UICONTROL Automated Personalization]-aktiviteter lades till med [at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
|  | [Använd dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators) | Lagt till information om följande nya operatorer:<ul><li>Finns i listan</li><li> Finns inte i listan</li><li>Listan innehåller ett objekt i</li><li>Listan innehåller inget objekt i</li><li>Listan innehåller alla objekt i</li><li>Listan innehåller inte alla objekt i</li></ul> |
|  | [Adobe Target cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)<br> (*Experience Cloud Services and* Administration Guide) | Ytterligare information om &quot;sessions-ID&quot; har lagts till. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 21.4.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe [!DNL Target] Standard/Premium 21.2.1 (9 mars 2021)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 9 april | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Tillagd förhandsversionsinformation för version 2.5.0 av at.js (19 april 2021) |
| 9 april | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till förhandsversionsinformation för Target Standard/Premium 21.4.1 (19 april 2021) |
|  | [Integrera Recommendations med e-post](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Anteckning som beskriver kapacitetsriktlinjer för alternativ 1 och 2 har lagts till. |
| 29 mars | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#persist-across-devices) | Nya frågor och svar:<ul><li>Bevaras rekommendationer baserade på nyligen visade objekt på flera enheter för en enskild besökare?</li></ul> |
| 23 mars | [Versionsinformation](/help/r-release-notes/release-notes.md) | Versionsinformation för at.js version 2.4.1 har lagts till. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Versionsinformation för at.js version 2.4.1 har lagts till. |
|  | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Uppdaterade följande frågor och svar:<ul><li>Hur lång tid tar det att uppdatera objekt i min katalog ska återspeglas på min webbplats?</li></ul> |
| 22 mars | [IP-adresser som används av Recommendations feed-bearbetningsservrar](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | Uppdaterad lista över IP-adresser. |
|  | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Avsnittet Antal enheter under Enheter uppdaterades. |
|  | [Geo](/help/c-target/c-audiences/c-target-rules/geo.md) | Ytterligare information om at.js 2.** xunder&quot;Hur kan jag testa mina aktiviteter som om jag är en användare som kommer från en annan plats?&quot; |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 21.2.1 | Följande avsnitt har lagts till: <ul><li>IP-adressändringar för Recommendations-servrar för bearbetning av feeds (16 mars 2021)</li></ul> |
| 19 mars | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#deactivated) | Följande frågor och svar har lagts till:<ul><li>Varför ser jag fler intryck när min aktivitet har inaktiverats?</li></ul> |
| 12 mars | [A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | Följande nya självstudiekurs har lagts till:<ul><li>Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter</li></ul> |
| 9 mars | [Gränser](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>De tillåtna storleksbegränsningarna för erbjudanden har uppdaterats.</li><li>Teckengränsen för parametern categoryId har korrigerats.</li></ul> |
|  | [Tillåtelselista: Hörnkantsnoder](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Uppdaterade IP-adresser för edge [!DNL Target]. |
|  | [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md) | Tillagd text som anger att entity.value måste ha decimalformat (till exempel 15,99 istället för 15,99). |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 21.2.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe [!DNL Target] Standard/Premium 21.1.1 (19 januari 2021)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 22 februari | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Uppdaterade följande frågor och svar:<ul><li>Var kan segment användas i Analysis Workspace?</li></ul> |
| 16 februari | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Uppdaterad text för begränsningsstorlek för erbjudanden i prerelease notes. |
| 11 februari | [Så här fungerar Target](/help/c-intro/how-target-works.md) | Uppdaterat avsnittet &quot;Börjor&quot;. |
| 10 februari | [Målmeddelanden och evenemang](/help/r-release-notes/target-announcements.md) | Information om Adobe Target Community Q&amp;A Coffee Break lades till onsdagen den 24 februari 2021. |
| 8 februari | [Förhandsvisning av målmobiler](/help/c-target-mobile-app/target-mobile-preview.md) | Kodfragmentet som du ska lägga till i filen AndroidManifest.xml för version 4 av Adobe Mobile SDK har lagts till. |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Följande kända fel har klargjorts:<ul><li>Samlingar, uteslutningar, villkor och designer som skapas via API är inte synliga i Target-användargränssnittet och kan bara redigeras via API. Om du skapar något av de här objekten i målgränssnittet och sedan redigerar dem via API, återspeglas inte ändringarna i målgränssnittet. Objekt som redigeras via API bör fortsätta att redigeras via API för att undvika att ändringar går förlorade.</li></ul> |
| 1 februari | [Automated Personalization Sammanfattningsrapporter](/help/c-reports/reports-ap.md) | Nytt avsnitt har lagts till: &quot;Frågor och svar.&quot; |
| 27 januari | [Skapa omdirigeringserbjudanden](/help/c-experiences/c-manage-content/offer-redirect.md) | Uppdaterat ämne. |
|  | [Skapa fjärrerbjudanden](/help/c-experiences/c-manage-content/about-remote-offers.md) | Uppdaterat ämne. |
| 26 januari | [Konverteringsgrad](/help/c-reports/conversion-rate.md) | Tydligare hur Target använder&quot;summan av fyrkanter&quot; i Students t-test. |
| 22 januari | [Konverteringsgrad](/help/c-reports/conversion-rate.md#t-test) | Följande avsnitt har lagts till: &quot;Varför rekommenderar Target att man använder Students t-tests?&quot; |
| 21 januari | [Felsöka integreringen med Analytics och Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | Nytt avsnitt har lagts till: &quot;A4T-aktivitetsrapporter innehåller en rad med ett stort antal &quot;ospecificerade&quot; händelser.&quot; |
|  | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Uppdaterat följande avsnitt: &quot;Varför ser jag&quot;ospecificerad&quot; i Analytics-rapporterna? Vad betyder det?&quot; |
| 20 januari | [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Nytt ämne. |
| 19 januari | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Lagt till information om Target 21.1.1 (19 januari 2021). |
|  | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Uppdaterad text för parametern `productPurchasedID`. |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Ett känt fel har lagts till när en [!UICONTROL Recommendation]-aktivitet kopierades med en aktiv befordran. Alla ändringar i dubblettaktiviteten påverkar också den ursprungliga aktiviteten, och vice versa. En tillfällig lösning ingår. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 21.1.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |
