---
keywords: måldokumentets ändringslogg;dokumentationsuppdateringar;nya ämnen;redigeringar;uppdateringar;uppdatera
description: Håll dig uppdaterad med viktiga tillägg och ändringar i [!DNL Adobe Target] dokumentation.
title: Var kan jag se dokumentationsuppdateringar för [!DNL Target]?
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '1507'
ht-degree: 0%

---

# Dokumentationsändringar

Den här sidan innehåller viktiga ändringar av [!DNL Adobe Target] produktdokumentation.

## [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 13 mars | [[!UICONTROL Time Frame]](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Information har lagts till som anteckning för att spara tidsbaserade målgrupper på nytt med hänsyn till DST (Daylight Saving Time). |
| 6 mars | [Webbläsare](/help/main/c-target/c-audiences/c-target-rules/browser.md) | Uppdaterad information i följande avsnitt:&quot;Uppdateringar för [!DNL iPad] och [!DNL iPhone] in [!UICONTROL Browser] publikattribut (30 april 2024)&quot;. |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Hela avsnittet har uppdaterats:&quot;Uppdateringar för `Browser:iPad` och `Browser:iPhone` in [!UICONTROL Browser] publikattribut (30 april 2024)&quot;. |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 24.1.1-utgåvan. |

## [!DNL Target] Standard/Premium 24.1.1 (22 januari, 23 och 25 januari 2024)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 28 februari | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Lagt till information om [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024). |
| 26 februari | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om kommande [!UICONTROL Adobe Target Community] Kaffebrytning (28 februari 2024). |
| 23 februari | [IP-adresser som används av [!DNL Recommendations] servrar för hantering av feeds](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | Följande viktiga anteckning och nya IP-adresser som du bör tillåtslista har lagts till.<P>**Viktigt**: [!DNL Target] teamet uppdaterar för närvarande NAT-gatewayadresserna för hämtning [!DNL Recommendations] feeds. Om du implementerar IP-tillåtelselistning måste du tillåtslista följande nya AWS-värdar. De befintliga värdarna planeras att avvecklas den 30 juni 2024. Om du vill ha en mjuk övergång tillåtslista du alla nio adresserna. Det är inte brådskande att ta bort de befintliga adresserna. |
| 8 februari | [Förhämtning](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/prefetch.html){target=_blank} | Nytt avsnitt har lagts till:&quot;Förhämta rutor med clickTrack-statistik när Analytics for Target (A4T) används&quot; |
| 5 februari | [Skapa en aktivitet som använder Analytics som rapportkälla](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | Text som anger att du inte kan använda samma aktivitetsnamn för två aktiviteter från separata arbetsytor när du använder [!UICONTROL Analytics for Target] (A4T) som rapportkälla. |
|  | [Aktivitetsinställningar - vanliga A4T-frågor](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | Text som anger att du inte kan använda samma aktivitetsnamn för två aktiviteter från separata arbetsytor när du använder [!UICONTROL Analytics for Target] (A4T) som rapportkälla. |
|  | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om Adobe Target Community Coffee Break som beräknas släppas den 7 februari 2024. |
| 24 januari | [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Versionsinformation för at.js version 2.11.4 har lagts till. |
|  | [Webbläsare](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | De två nya profilerna är ännu inte tillgängliga. Anteckningarna uppdateras när profilerna är tillgängliga. |
|  | [at.js Frågor och svar](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html){target=_blank} | Tillagda frågor och svar om at.js i en Ionic App-miljö. Implementeringen har inte testats eller rekommenderas inte. |
| 22 januari | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Viktig information om borttagningen av iPad och iPhone från [!UICONTROL Browser] målgruppsattribut som kräver ändringar från din sida före 30 april 2024. |
|  | [Webbläsare](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | Nytt avsnitt har lagts till: <ul><li>Borttagning av iPad och iPhone från Browser-målgruppsattribut (30 april 2024)</li></ul> |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 24.1.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.11.1 (13 och 14 november 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 18 januari | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Tillagda förhandsversionsinformation för kommande [!DNL Target Standard/Premium] 24.1.1-utgåvan. |
| 13 december | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om [!DNL Adobe Target] 2024 Personalization Maturity Webinar Series. |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html){target=_blank} | Två nya valfria inställningar har lagts till: <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 4 december | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till registreringsinformation för&quot;Maskinininlärning och AI-rapportering och -analys&quot; [!DNL Adobe Target Community] Coffee Break session: onsdagen den 6 december 2023. |
| 1 december | [API:er för Adobe Target-profiluppdatering](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank} | Flyttade äldre API-dokumentation till följande artiklar:<ul><li>[Adobe Target Profile APIs - översikt](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank}</li><li>[Adobe Target API för uppdatering av enstaka profil](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html){target=_blank}</li><li>[Adobe Target API för gruppprofilsuppdatering](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?){target=_blank}</li></ul> |
| 29 november | [API för gruppprofiluppdatering](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | Tydligare skillnader om hur [!DNL Target] hanterar kundattribut när en profil skapas för en användare [!DNL Target] har ännu inte setts när du använder [!UICONTROL Bulk Profile Update API] v2 till skillnad från v1. |
| 21 november | [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Versionsinformation för at.js 2.11.3 har lagts till. |
| 17 november | [Administratörssteg](/help/main/administrating-target/start-target.md) | Följande viktiga anteckning har lagts till:<ul><li>Användare med [!UICONTROL Product Admin] eller [!UICONTROL System Admin] rättigheter i [!DNL Adobe Admin Console] kan redigera eller ändra alla inställningar på [!UICONTROL Administration] sida av [!DNL Target], oavsett [!DNL Target] roll. Användare utan [!UICONTROL Product Admin] eller [!UICONTROL System Admin] rättigheter i [!DNL Adobe Admin Console] måste ha den specifika [!DNL Target] roll att göra dessa ändringar.1</li></ul> |
|  | [Gränser](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | Uppdaterat avsnitt med information om hur [!DNL Target] hanterar trunkering i at.js 2.*x* och [!DNL Adobe Experience Platform Web SDK]. |
|  | [Leverans-API](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html){target=_blank} | Lagt till omdirigeringar till den aktuella dokumentationen för leverans-API och har ersatt den tidigare dokumentationen (`http://developers.adobetarget.com/api/delivery-api/`). Uppdatera bokmärken efter behov. |
| 16 november | [API för gruppprofilsuppdatering](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | Följande caveat tillagdes:&quot;Uppdateringar inträffar vanligtvis på mindre än en timme, men kan ta upp till 24 timmar att reflektera.&quot; |
| 13 november | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.11.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.10.2 (24 oktober 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 10 november | [Recommendations API-referens](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | The [!DNL Adobe Target] [!DNL Recommendations] API har flyttats till [!DNL Adobe Developer] webbplats. Uppdatera bokmärkena om det behövs. |
|  | [Tidsram](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Observera att [!DNL Target] målgrupper inte tar hänsyn till DST-ändringar (Daylight Saving Time). Du måste uppdatera målgrupperna manuellt för att kunna ta hänsyn till DST-ändringar. |
| 8 november | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Tillagda förhandsversionsinformation för kommande [!DNL Target Standard/Premium] 23.11.1-utgåvan. |
| 28 oktober | [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Mer information om version 2.11.2 av at.js har lagts till. |
| 25 oktober | [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md) | Lagt till information om [!UICONTROL Activities] uppdatering av sidanvändargränssnittet (25 oktober 2023) |
| 24 oktober | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.10.2-utgåvan. |

## [!DNL Target] Standard/Premium 23.9.1 (6-11 september 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 17 oktober | [Vanliga frågor om rapportering](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | Uppdaterade följande vanliga frågor och svar:&quot;Varför finns det inga data tillgängliga för min aktivitetsrapport? &quot; |
| 11 oktober | [[!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) | Uppdaterad information om A4T-stöd för [!DNL Adobe Experience Platform Web SDK]. |
| 10 oktober | [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Versionsinformation för at.js version 2.11.0 har lagts till. |
| 6 oktober | [Svarstoken](/help/main/administrating-target/response-tokens.md) | Alla kodexempel har uppdaterats. |
|  | [Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Allocate] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} | Hela självstudiekursen i *[!UICONTROL Adobe Target Tutorials]* guide. |
| 4 oktober | [Verksamhet](/help/main/c-activities/activities.md) | Uppdaterad text och bilder som återspeglar den gränssnittsuppdatering som ingår i [!DNL Target] 23.9.4-utgåvan. |
|  | [Feeds](/help/main/c-recommendations/c-products/feeds.md) | Uppdaterad text och bilder som återspeglar den gränssnittsuppdatering som ingår i [!DNL Target] 23.9.4-utgåvan. |
| 2 oktober | [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.9.3-utgåvan. |
|  | [[!DNL Recommendations] implementeringsmönster](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} | Den nya *Recommendations implementeringsmönster med at.js* artiklar hjälper dig att förstå och skapa [!DNL Adobe Target Recommendations] implementering när du använder JavaScript-biblioteket at.js.<P>Allmän information om [!DNL Target] mönster, se [Översikt över implementeringsmönster](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank} i *Adobe Target Developer Guide*.<P>Det nya implementeringsmönstret för Recommendations består av följande artiklar:<ul><li>[Recommendations implementeringsmönster med översikten at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[Initiera SDK:er](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[Konfigurera datainsamling](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[Återge upplevelser](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=en){target=_blank}</li><li>[Meddela [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=en){target=_blank}</li></ul></ul> |
| 29 september | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Tillagda förhandsversionsinformation för [!DNL Target Standard/Premium] 23.9.3-utgåvan. |
|  | [Initiera Java SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | Följande nya parametrar har lagts till i tabellen:<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 22 september | [Felsökning relaterade till [!UICONTROL Enhanced Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) | Listan över IP-adresser som ska tillåtslista har uppdaterats. |
| 18 september | [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.9.3-utgåvan. |
| 15 september | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Tillagda förhandsversionsinformation för [!DNL Target Standard/Premium] 23.9.3-utgåvan. |
| 12 september | [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.9.2-utgåvan. |
|  | [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Versionsinformation har lagts till för at.js version 2.10.3. |
| 11 september | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Tillagda förhandsversionsinformation för [!DNL Target Standard/Premium] 23.9.2-utgåvan. |
| 6 september | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.9.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.8.1 (9 augusti 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 1 september | [Miljö](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | Uppdaterad anmärkning under&quot;Ange standardmiljön för rapportering&quot;. |
| 30 augusti | [Integritet](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html#aep){target=_blank} | Nytt avsnitt har lagts till:&quot;IP-obehörig på datasterivå när Adobe Experience Platform Web SDK används&quot; |
|  | [Aktivitetsinställningar - vanliga A4T-frågor](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | Korrigerad tidsram för att data ska visas i rapporter i vanliga frågor och svar:&quot;Jag har just skapat en aktivitet. Varför ser jag inga data som kommer in?&quot; |
| 29 augusti | [Funktioner som stöds för beslut på enheten](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html){target=_blank} | Listan med Geo-attribut som stöds för målinriktning har lagts till när ODD (On-device decisioning) används på klientsidan. |
|  | [Översikt över beslut på enheter](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html){target=_blank} | Listan med Geo-attribut som stöds för målinriktning har lagts till när ODD (On-device decisioning) används på serversidan. |
|  | [Implementera Target med AEP Mobile SDK i en inbyggd app med webbvyer](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html){target=_blank} | Ny artikel. |
|  | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om den kommande brytningen av Adobe Target Community Coffee Break (30 augusti 2023):&quot;Strategize for maximum ROI impact with peak  readiness&quot; (Strategize for maximum ROI impact with peak säsonreadiness readiness). |
| 14 augusti | [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | Lagt till information som klargör att det inte går att läsa in en sida på webbplatsen med ett tomt värde *not* ta bort QA-cookien från webbläsaren när at.js 2.*x* distribueras. |
|  | [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | Definitionen av&quot;konfidentialitet&quot; har uppdaterats. |
|  | [Erbjudanden](/help/main/c-experiences/c-manage-content/manage-content.md) | En kommentar som förklarar att bilderbjudandena inte ingår i [!UICONTROL Enterprise User Permissions] modell. |
| 9 augusti | [Förhandsvisning av målmobiler](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html){target=_blank} | Uppdaterat ämne med information om aktuella versioner av [!DNL Adobe Experience Platform Mobile SDK]. |
| 9 augusti | [Förhandsvisning av målmobiler](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html){target=_blank} | Uppdaterat ämne med information om aktuella versioner av [!DNL Adobe Experience Platform Mobile SDK]. |
|  | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om följande webbinarium som planeras äga rum den 17 augusti 2023: *Strategiera för maximal ROI-påverkan med beredskap för högsäsong*. |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.8.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.7.1 (24-26 juli 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
|  | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om följande webbinarium som planeras äga rum den 17 augusti 2023: *Strategiera för maximal ROI-påverkan med beredskap för högsäsong*. |
| 7 augusti | [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Tydligare information om vilka versioner av at.js som stöds. |
| 25 juli | [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md#edge) | Lagt till information om den planerade uppgraderingen av Edge-infrastrukturen som är planerad till 9 augusti 2023. |
|  | [Tillåtelselista: Hörnkantsnoder](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | Uppdaterade NAT och IP/domäner för edge-driftsättningar 41-48. |
| 24 juli | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.7.1-utgåvan. |
