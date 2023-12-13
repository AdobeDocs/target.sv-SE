---
keywords: måldokumentets ändringslogg;dokumentationsuppdateringar;nya ämnen;redigeringar;uppdateringar;uppdatera
description: Håll dig uppdaterad med viktiga tillägg och ändringar i [!DNL Adobe Target] dokumentation.
title: Var kan jag se dokumentationsuppdateringar för [!DNL Target]?
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: bc57a7543c124f5be2d5f8d1df973cf10105d92b
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%

---

# Dokumentationsändringar

Den här sidan innehåller viktiga ändringar av [!DNL Adobe Target] produktdokumentation.

## [!DNL Target] Standard/Premium 23.11.1 (13 och 14 november 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
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
|  | [Initiera Java SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | Följande nya parametrar har lagts till i tabellen:<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
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

## [!DNL Target] Standard/Premium 23.6.1 (27-29 juni 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 20 juli | [CSP-direktiv (Content Security Policy)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/content-security-policy.html){target=_blank} | Följande frågor och svar har lagts till i *Adobe Target Developer Guide*: Hur tillåter eller förhindrar jag att min webbplats bäddas in som iFrame under utländska domäner? |
| 10 juli | [Överväganden och kända begränsningar](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/known-limitations.html){target=_blank} | Lagt till information i *Målleverans-API* dokumentation om att HTTP/2 använder gemena rubriknamn. |
| 27 juni | [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | Aktivitets-QA är nu tillgängligt för alla målaktivitetstyper, inklusive [!UICONTROL Automated Personalization] (AP) aktiviteter. Information om förhandsgranskningslänkar har tagits bort. |
|  | Förhandsgranska URL:er | Eftersom alla aktivitetstyper nu stöder Aktivitets-QA har det här avsnittet tagits bort och omdirigerats till [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md) ämne. |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.6.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.5.1 (23-25 maj 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 26 juni | [Mål för mobilappar](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/overview.html){target=_blank} | Länk till implementeringen har lagts till [!DNL Adobe Experience Cloud] i självstudiekursen om mobilappar. |
| 12 juni | [Adobe Target cookies](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-target.html){target=_blank} | Uppdaterad artikel i *Handbok för gränssnittskomponenter i Experience Cloud Central* förklara cookies som används av [!DNL Target]. |
|  | [Initiera Java SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | Lagt till information om parametern &quot;environment&quot;. |
|  | [Initiera Python SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/python/initialize-sdk.html){target=_blank} | Lagt till information om parametern &quot;environment&quot;. |
| 5 juni | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Uppdaterad information om följande händelser:<ul><li>Registreringslänken för [!DNL Adobe Target Recommendations] Kaffebrytning (onsdag den 7 juni 2023)</li><li>Lagt till information om det senaste webbinariet&quot;Mobilupplevelseoptimering och personalisering för autentiserade miljöer&quot; och lade till en länk till inspelningen.</li></ul> |
|  | [Tillämpa en rapportmålgrupp på ett framgångsmått](/help/main/c-target/apply-reporting-audience-success-metric.md) | Avsnittet&quot;Överväganden&quot; har uppdaterats och avsnittet&quot;Exempel&quot; har lagts till. |
|  | [Mål och målgrupper Frågor och svar](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md#url-targeting) | Uppdaterat avsnittet &quot;URL-målanpassning&quot;. |
| 30 maj | [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.5.2-utgåvan. |
|  | [Integrera med [!DNL Real-Time Customer Data Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md) | Uppdaterad artikel med information om delning [!UICONTROL Real-Time CDP Profile Attributes] med [!DNL Target] för användning i HTML och JSON. |
|  | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Information om följande kommande Coffee Break-händelser har lagts till:<ul><li>[!DNL Adobe Target Recommendations] Kaffebrytning (7 juni)</li><li>Uppföljning av webbseminariet om beredskap för personaliseringsprogram (21 juni)</li></ul> |
| 23 maj | [Tillåtelselista: Hörnkantsnoder](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | Uppdaterad viktig anteckning. |
|  | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Uppdaterad förhandsversionsinformation för kommande versioner. |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.5.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.4.1 (25-27 april 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 22 maj | [Integrera med [!DNL Real-Time Customer Data Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#videos-blogs) | Följande nya videoklipp har lagts till:<ul><li>Konfigurera [!DNL Adobe Target] mål in [!DNL Real-Time Customer Data Platform]</li><li>Aktivera segment och profilattribut</li><li>Använd [!DNL Real-Time CDP] segment i [!DNL Target]</li><li>Använd [!DNL Real-Time CDP] profilattribut i [!DNL Adobe Target]</li></ul> |
|  | [Tillåtelselista: Hörnkantsnoder](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | Uppdaterad viktig anteckning. |
| 19 maj | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Uppdaterad förhandsversionsinformation för kommande versioner. |
| 17 maj | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om [!UICONTROL Adobe Target Community] Q&amp;A Coffee Break on onsdagen den 24 maj 2023. |
| 16 maj | [Entitetsattribut](/help/main/c-recommendations/c-products/entity-attributes.md) | Anger att&quot;blanksteg&quot; inte tillåts i `entity.id` värden. |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html){target=_blank} | Uppdaterat `viewsEnabled` description. |
|  | [Implementering av Single Page-program](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/target-atjs-single-page-application.html){target=_blank} | Utför följande uppdateringar:<ul><li>Anteckning har lagts till efter steg 2 under Implementera Adobe Target-vyer.</li><li>Uppdaterat steg 2&quot;Kör målbegäran&quot; under&quot;Åtgärdsordning för första sidinläsning&quot;.</li></ul> |
| 4 maj | [Konfigurera autentisering för Adobe Target API:er](https://experienceleague.adobe.com/docs/target-dev/developer/api/configure-authentication.html){target=_blank} | En kommentar som förklarar behovet av att migrera från en JWT-autentiseringsuppgift till en OAuth Server-till-Server-autentiseringsuppgift har lagts till. |
| 3 maj | [Visa rapporter - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#activity-impressions) | Följande frågor och svar har lagts till:<ul><li>Hur spårar jag aktivitetsintryck i [!DNL Analysis Workspace] när du använder [!UICONTROL Analytics for Target] (A4T)?</li></ul> |
| 26 april | [AEM [!UICONTROL Experience Fragments] och [!UICONTROL Content Fragments] översikt](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) | The [!UICONTROL AEM Content Fragments] finns nu för alla [!DNL Target customers]. |
|  | [AEM [!UICONTROL Content Fragments]](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) | The [!UICONTROL AEM Content Fragments] finns nu för alla [!DNL Target customers]. |
|  | [*Adobe Target Developer Guide*](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html){target=_blank} | The *Adobe Target Developer Guide* har flyttats till *[!UICONTROL Adobe Experience League]*. Flytten till *[!UICONTROL Experience League]* hjälpmedel för lokalisering av text på ytterligare språk, gör sökningen på *Experience League* för att spänna över och erbjuda sökresultat från båda *[!UICONTROL Adobe Target Business Practitioner Guide]* och *[!UICONTROL Adobe Target Developer Guide]* och ger ytterligare fördelar.<P>Du kommer att omdirigeras från föregående plats till *[!UICONTROL Experience League]* automatiskt. Uppdatera bokmärkena efter behov. |
| 24 april | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Ytterligare information om följande frågor om Adobe Target Community Coffee Break:<ul><li>Optimering och personalisering av mobilupplevelser för autentiserade miljöer</li></ul> |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.4.1-utgåvan. |

## [!DNL Target] Standard/Premium 23.3.1 (28-30 mars 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 19 april | [[!UICONTROL Location Contribution] rapport (MVT)](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) | Uppdaterad information i anteckningen. |
| 13 april | [[!DNL Target] versionsinformation (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Lagt till information om [!DNL Target] Standard/Premium 23.4.1 (25-27 april 2023). |
| 12 april | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Länk har lagts till för att registrera följande webbinarium:<ul><li>Leverera personaliserade kundupplevelser varje gång!</li></ul> |
|  | [Viktiga attributrapporter](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md#models-api) | Följande frågor och svar har lagts till:<ul><li>Jag ser ett eller flera attribut som jag inte vill att modellen ska använda för utbildning. Kan jag ta bort dessa attribut från utbildningsmodellen?</li></ul> |
|  | [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#multiple-roles) | Följande frågor och svar har lagts till:<ul><li>Vad händer om en användare har flera roller och behörigheter?</li></ul> |
|  | [AEM innehållsfragment](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) | Nytt ämne. Observera att den här funktionen har statusen&quot;prerelease&quot; för teständamål. |
| 5 april | [Använd offertbeslut](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | Tillagd text som anger att [!UICONTROL Analytics as the reporting source] (A4t) stöds inte i aktiviteter som använder offertbeslut. |
| 3 april | [[!DNL Adobe Target] meddelanden och evenemang](/help/main/r-release-notes/target-announcements.md) | Lagt till information om [!UICONTROL Adobe Target Community] Kaffebrytning planerad till onsdagen den 12 april 2023. |
|  | [Tillåtelselista: Hörnkantsnoder](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | Anteckningen har lagts till för att tillåtslista alla [!DNL Adobe Analytics] IP-adressblock. |
| 30 mars | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Uppdaterad versionsinformation för releasen av optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] funktion som låter dig välja mätvärden baserat på binomiala händelser eller mätvärden baserade på kontinuerliga händelser när du använder [!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet. |
|  | [A4T-stöd för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) | Avsnittet&quot;Måttvärden som stöds&quot; har uppdaterats för att innehålla information om de mått som stöds (och inte stöds) för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] aktiviteter använda [!UICONTROL Analytics for Target] (A4T) |
|  | [Adobe Target Tutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html){target=_blank} | Uppdaterade följande självstudiekurser:<ul><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Allocate] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Target] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |
|  | [Versionsinformation för mål (prerelease)](/help/main/r-release-notes/target-release-notes.md) | Lagt till information för [!DNL Adobe Experience Manager] AEM och [!DNL Adobe Target] [!UICONTROL Content Fragments] release. (6 april 2023) |
| 28 mars | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 23.3.1-utgåvan. |

## [!DNL Target] Standard/Premium 22.15.1 (8 och 9 mars 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
|  | [Redigera en aktivitet eller spara som utkast](/help/main/c-activities/edit-activity.md) | Lagt till avsnittet&quot;Bästa metoder&quot;. |
|  | [Ändringar](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Följande kommentar har lagts till i avsnittet&quot;Felsökning av anpassad kod&quot;:<ul><li>Anpassade koderbjudanden i VEC återges inte om när `triggerView()` anropas med `{page: false}` som alternativ.</li></ul> |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Ytterligare information om at.js 2.10.2-versionen. |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 22.15.1-utgåvan. |

## [!DNL Target] Standard/Premium 22.13.3 (25 januari 2023)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 21 februari | [Tillåtelselista: Hörnkantsnoder](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} | Uppdaterad lista över IP-adresser som ska tillåtslista för alla regioner i [Adobe Target Developer Guide](https://experienceleague.corp.adobe.com/docs/target-dev/developer/overview.html){target=_blank}. |
|  | [Ändringar](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Tillagd text som förklarar att exemplet med JQuery förutsätter att kundens webbplats har jQuery tillgängligt på sidan när [!DNL Target] verkställer erbjudandena. |
| 10 februari | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 22.14.5-utgåvan. |
| 8 februari | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för at.js 2.10.1 har lagts till. |
| 2 februari | [Felsöka problem med Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#section_FA2A18E8FD6A4274B2E395DBAA2FB407) | Följande avsnitt har uppdaterats:<ul><li>VEC visas som brutet när jag använder bläddringsläge</li></ul> |
|  | [Bygg målgrupper i Target](/help/main/c-target/c-audiences/create-audience.md) | En lista med tecken och teckensekvenser som inte kan användas i publiknamn har lagts till. |
| 31 januari | [Gränser](/help/main/r-troubleshooting-target/target-limits.md#mbox-names) | En lista över tillåtna och otillåtna tecken i mbox-namn har lagts till. |
| 25 januari | [Create JSON offers](/help/main/c-experiences/c-manage-content/create-json-offer.md) | Anger att stöd för JSON erbjuder i [!UICONTROL Automated Personalization] (AP) aktiviteter som använder formulärbaserad Experience Composer är nu tillgängliga. |
|  | [Adobe Target notiser och event](/help/main/r-release-notes/target-announcements.md) | Lagt till information om följande händelse:<ul><li>[!DNL Adobe Target] Community Q&amp;A Coffee Break: Mobile &amp; Authenticated Use Case for Experience Optimization</li></ul> |
|  | [Versionsinformation för mål (aktuell)](/help/main/r-release-notes/release-notes.md) | Versionsinformation för [!DNL Target Standard/Premium] 22.13.3-utgåvan. |
