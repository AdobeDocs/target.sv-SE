---
keywords: target documentation change log;documentation updates;new topics;edits;updates
description: På den här sidan visas viktiga ändringar i Adobe Target-dokumentationen, som har beställts i releaser.
title: Dokumentationen ändras i produktdokumentationen för Adobe Target.
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 32cfa346ae6aa3246d830e1ce153cb45baab8c89
workflow-type: tm+mt
source-wordcount: '7578'
ht-degree: 0%

---


# Dokumentationsändringar{#documentation-changes}

På den här sidan visas viktiga ändringar i [!DNL Adobe Target] produktdokumentationen.

## Adobe Target Standard/Premium 20.2.1 (19 februari 2020)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 11 maj | [Värdar](/help/administrating-target/hosts.md) | Lagt till information om hur du använder funktionen ubox med omdirigeringar och vitlistor. |
|  | [Arbeta med regissörer](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Lagt till information om hur du använder värdar för att undvika Open Redirect-sårbarheter. |
|  | [Integrera rekommendationer med e-post](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Lagt till information om hur du använder värdar för att undvika Open Redirect-sårbarheter. |
|  | [E-post: implementera mål](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Lagt till information om hur du använder värdar för att undvika Open Redirect-sårbarheter. |
| 7 maj | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | I och med den kommande utfasningen av mbox.js den 30 augusti 2020 var David Son, var Adobe Target Product Manager nyligen värd för en utvecklarchatt för att diskutera fördelarna med att migrera mbox.js till at.js. Det finns en länk där du kan titta på webbinariet de kommande 30 dagarna. |
|  | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Uppdaterade avsnittet &quot;Överväganden&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Uppdaterad&quot;overrideMboxEdgeServer&quot;-rad under&quot;Settings&quot;. |
| 6 maj | [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Ytterligare information om ITP 2.3. |
| 4 maj | [Vanliga frågor om rapportering](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | Nya frågor och svar: &quot;Varför är trafiken delad mellan mina upplevelser ojämn i min A/B- eller MVT-aktivitet?&quot; |
| 29 april | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Ett känt problem har lagts till för rapportering av extrema order. |
| 28 april | [Profil och variabel ordlista](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Information om hur du använder `user.header('x-forwarded-for')` med nyare AWS-kanter för att hämta användarnas IP-adresser har tagits bort. Det här kommandot fungerar nu med nyare AWS-kanter. |
|  | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Ändrad till 6 maj för målversionen av Standard/Premium (20.4.1). |
| 23 april | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Uppdaterat ämne. |
| 22 april | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Nytt avsnitt har lagts till: *Ändringar i API:t för gruppstatus (4 maj 2020).* |
| 20 april | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Nytt avsnitt har lagts till: *Adobe Target-verktyget för kompetensutveckling: Utvecklarchatt, migrera Adobe Target mbox.js till at.js.* |
| 14 april | [Vitlista Målkantsvärdar](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | Nytt ämne. |
| 10 april | [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | Nytt avsnitt har lagts till: &quot;Bästa praxis för implementering.&quot; |
| 7 april | [Lyft och tillförsikt - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | Uppdaterad text för&quot;Varför kan jag inte se lyft och självförtroende för beräknade mätvärden?&quot; |
| 2 april | [Profil och variabel ordlista](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Lagt till information om hur du använder `user.header('x-forwarded-for')` med nyare AWS-kanter för att hämta användarnas IP-adresser. |
|  | [Uppgraderar från at.js 1.*x* to at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Följande anmärkning har lagts till:<ul><li>Efter installation av ECID-biblioteket v4.3.0+ och at.js 2.*x* kan du skapa aktiviteter som spänner över unika domäner samt spåra användare. Det är viktigt att komma ihåg att den här funktionen fungerar först när sessionen har upphört.</li></ul> |
| 30 mars | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | Ett känt fel som påverkar at.js-versionerna före kl. 2.2.0 har lagts till. Detta orsakade att klickspårning inte rapporterade konverteringar i A4T (Analytics for Target) när Adobe Analytics-koden inte fanns på sidelementen. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Följande information har lagts till i informationen för at.js version 2.2.0:<ul><li>Korrigerade ett problem som orsakade klickspårning för att inte rapportera konverteringar i A4T (Analytics for Target) när Adobe Analytics-kod inte fanns på sidelement.</li></ul> |
| 25 mars | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ytterligare information om följande nya versioner av at.js:<ul><li>at.js version 2.3.0</li><li>at.js version 1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Följande nya rader har lagts till i avsnittet Inställningar:<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>Följande nya avsnitt har lagts till:<ul><li>Skyddsprofil för innehåll</li></ul> |
| 24 mars | [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | Lagt till information om påverkan för följande:<ul><li>Profilskript baserade på 3rdPartyID</li><li>QA/Preview URLs in iOS devices</li></ul> |
| 20 mars | [Versionsinformation (aktuell)](/help/r-release-notes/release-notes.md) | Anges att Target Standard/Premium 20.2.1 kommer att vara den 23 mars 2020. |
| 13 mars | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Uppdaterade antalet&quot;Målgrupper, återanvändbara per konto&quot;. |
| 12 mars | [Versionsinformation (aktuell)](/help/r-release-notes/release-notes.md#summit) | Ytterligare registreringsinformation för kostnadsfri åtkomst till den digitala Summit på webben. |
| 9 mars | [Integritet](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Ytterligare information har lagts till i avsnittet&quot;Ersättning av den senaste oktetten med IP-adresser&quot;. |
|  | [Arbeta med attribut för flera värden](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Uppdaterat kodexempel i *Skicka en flervärdesparameter i JavaScript*. |
|  | [Anpassade entitetsattribut](/help/c-recommendations/c-products/custom-entity-attributes.md) | Lagt till kodexempel i *Använda API:er* under *Implementera attribut* med flera värden. |
| 4 mars | [Profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md) | Hela ämnet har uppdaterats med omfattande revideringar av avsnittet&quot;Bästa praxis&quot;. |
| 21 februari | [Versionsinformation (aktuell)](/help/r-release-notes/release-notes.md) | Lagt till information om den nya navigeringen i Adobe Experience Cloud. |
| 20 februari | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Beskrivningen av `enabled` inställningen har uppdaterats. Tillagd information för följande inställningar: `pageLoadEnabled` och `viewsEnabled`. |
| 19 februari | [Versionsinformation](/help/r-release-notes/release-notes.md) | Lagt till information om den kommande borttagningen av mbox.js-biblioteket. |
|  | [Geo](/help/c-target/c-audiences/c-target-rules/geo.md) | Anteckning som `mboxOverride.browserIp` stöds i at.js 1 har lagts till.*Endast x* . |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Tydlig text som förklarar vilka versioner av at.js som Target-teamet stöder. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 20.2.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 20.1.1 (4 februari 2020)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 4 februari | [Versionsinformation](/help/r-release-notes/release-notes.md): 20.1.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.10.1 (22 oktober 2019)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 29 januari 2020 | [Anpassa en design med Snabb](/help/c-recommendations/c-design-overview/customizing-a-template.md) | Uppdaterade text- och kodexempel. Nya kodexempel visar hur du arbetar med siffror i Snabbarhetsmallar. |
| 28 januari 2020 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Ändrade releasedatum för Target Standard/Premium 20.1.1. Releasedatum är nu 4 februari 2020. |
| 27 januari 2020 | [Insikter om personalisering - rapporter](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) | Nytt avsnitt har lagts till: &quot;Adobe Blogs.&quot; |
|  | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Följande information har lagts till: &quot;Om du använder API:t för gruppleverans är gränsen 50 mbox per batch-begäran.&quot; |
|  | [Resurser och kontaktinformation](/help/cmp-resources-and-contact-information.md#section_354AC2658BA84A2A96E64C5B2C43B73B) | Uppdaterad länk för att öppna en supportanmälan. |
|  | [Sammanfattningsrapport för automatiskt mål](/help/c-reports/auto-target-summary-report.md) | Uppdaterad text och bilder. |
| 23 januari 2020 | [Tolka autofördelningsrapporter](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Anteckning har lagts till för att använda Adobe Target-beräknaren för exempelstorlek för att avgöra vem som vinner. |
|  | [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md) | En kommentar som förklarar att om du använder at.js 2 har lagts till.*x*, `mboxCreate` stöds inte längre. Skicka produkt- eller innehållsinformation till Recommendations med at.js 2.*x*, använd `targetPageParams`. |
| 22 januari 2020 | [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Uppdaterade följande frågor och svar: &quot;Kan jag använda beräkningsverktyget för provstorlek när jag använder Automatisk allokering för att beräkna hur lång tid det tar för aktiviteten att identifiera vinnaren?&quot; |
| 15 januari 2020 | [Aktivera blandat innehåll i webbläsaren](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | En utbildningsvideo med instruktioner om hur du uppdaterar webbplatsinställningarna för att tillåta blandat innehåll i den senaste versionen av Chrome har lagts till. |
|  | [Feeds](/help/c-recommendations/c-products/feeds.md) | Lade till anteckning om att överföra och ta bort entiteter och entitetsattribut. |
|  | [Rekommendationer - frågor och svar](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Följande frågor och svar har lagts till: Vad betyder NO_CONTENT-svaret som ibland returneras i innehållspårningen Recommendations? |
|  | [Skapa en orderbekräftelseruta - mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/orderconfirm-create.md) | En kommentar som förklarar hur man utför orderbekräftelsen med at.js 2 har lagts till.*x*. |
| 9 januari 2020 | [TLS-krypteringsändringar (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | Uppdaterad text.<br>Efter den 1 mars 2020 stöder Adobe Target inte längre TLS 1.1-kryptering för Visual Experience Composer (VEC), Enhanced Experience Composer (EEC), aktivitetsleverans, API:er osv. Uppgradera till TLS 1.2 före 1 mars 2020 för att undvika problem. |
| 6 januari 2020 | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Ett känt fel har lagts till om status för feed för anpassade villkor. |
| 19 december 2019 | [Versionsinformation - Mål-Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Lagt till information om version 1.1.0. |
| 12 december 2019 | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Uppdaterat avsnitt med vanliga frågor och svar. |
|  | [Tolka autofördelningsrapporter](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Ändrade namn på ämnet och lade till följande avsnitt: &quot;Förstå Lyft- och förtroenderapportering i Automatisk allokering av aktiviteter.&quot; |
| 11 december 2019 | [Mål och målgrupper Frågor och svar](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) | Nya frågor och svar: &quot;Hur utvärderar Target URL:er när det gäller målinriktning?&quot; |
| 10 december 2019 | [Målgrupper](/help/r-troubleshooting-target/target-limits.md) | Mappningsparameteravsnittet har uppdaterats. |
|  | [Kriterier](/help/c-recommendations/c-algorithms/algorithms.md) | Meddelande om stöd för funktionen Villkorsanvändning har lagts till. |
| 5 december 2019 | [Webbplatssidor](/help/c-target/c-audiences/c-target-rules/site-pages.md) | Uppdaterat ämne. |
| 2 december 2019 | [Använd platstjänst](/help/c-target-mobile-app/use-location-service.md) | Nytt ämne. |
| 26 november 2019 | [Hur at.js hanterar flimmer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md) | Uppdaterad text i&quot;Hantera flimmer vid inläsning av at.js asynkront&quot;. |
|  | [Target Insider-nyhetsbrev](/help/r-release-notes/target-insider-newsletter.md) | Länk har lagts till i nyhetsbrevet från november 2019. |
|  | [Användare](/help/administrating-target/c-user-management/c-user-management/user-management.md) | Uppdaterad text och bilder under&quot;Ange roller och behörigheter&quot;. |
| 15 november 2019 | [Tio vanliga A/B-testfall och hur man undviker dem](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md) | &quot;Pitfall 7: Ändra trafiktilldelningen under testperioden.&quot; |
| 11 november 2019 | [Versionsinformation - Mål-Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Lagt till information om version 1.0.1. |
|  | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Hela ämnet har uppdaterats. |
|  | [Geo](/help/c-target/c-audiences/c-target-rules/geo.md#section_DD308A53AF0F48FA8C81423580561FE7) | Tillagd information som förklarar att geoinformation inte lagras, t.ex. Zip-koder. [!DNL Target] |
| 8 november 2019 | [Target Insider-nyhetsbrev](/help/r-release-notes/target-insider-newsletter.md) | Lagt till länkar till ytterligare tidigare problem. |
|  | [Sekretess- och dataskyddsbestämmelser](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) | CCPA-avsnittet har uppdaterats med ny anteckning.<br>Nya FAQ har lagts till som informerar kunderna om att Target inte har möjlighet att tillåta kunder att dela eller sälja data direkt från Target till tredje part, så det finns ingen avanmälan för Target att sälja dem. |
| 7 november 2019 | [Profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md#examples) | Kodexempel har lagts till för parametern adobeQA. |
| 5 november 2019 | [Webbplatssidor](/help/c-target/c-audiences/c-target-rules/site-pages.md#ts) | Uppdaterad text i avsnittet &quot;Felsökning&quot;. |
| 4 november 2019 | [at.js Frågor och svar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md) | Uppdaterad text under följande vanliga frågor och svar: &quot;Varför ser jag varningsmeddelanden, till exempel &quot;åtgärder där väljare saknas&quot;?&quot; |
| 31 oktober 2019 | [Arbeta med attribut för flera värden](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Nytt ämne. |
|  | [Versionsinformation - Mål-Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Nytt ämne. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#audience-parameters) | Nytt avsnitt har lagts till: &quot;Som i .js 1.*x* -parametrar för att skapa målgrupper stöds inte i at.js 2.*x*?&quot; |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Ett nytt känt problem med extra mellanslag har lagts till i mallregler. |
|  | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Lagt till information om Target Premium 19.10.2 och Target Java SDK. |
| 30 oktober 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till information om den kommande versionen av Target Premium 19.10.2 (31 oktober 2019). |
| 29 oktober 2019 | [Likhet i innehåll](/help/c-recommendations/c-algorithms/create-new-algorithm.md#concept_5402DAFA279C4E46A9A449526889A0CB) | Tillagd anteckning. |
|  | [Förhandsgranska och starta aktiviteten Rekommendationer](/help/c-recommendations/t-create-recs-activity/previewing-and-launching-your-recommendations-activity.md) | Nytt ämne. |
| 25 oktober 2019 | [Egna parametrar](/help/c-target/c-audiences/c-target-rules/custom-parameters.md#considerations) | Ett nytt objekt har lagts till under &quot;Considerations&quot; för att förklara att målanpassning inte utvärderas på interna mbox-parametrar. |
|  | [Använd dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) | Uppdaterat ämne helt och hållet och tagit bort föråldrade exempel. |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Länkning av anteckningar till API-dokumentationen för målleverans har lagts till för att hjälpa dig förstå vilka typer av förfrågningar/svar som är tillgängliga (matris, sträng och så vidare). |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Länkning av anteckningar till API-dokumentationen för målleverans har lagts till för att hjälpa dig förstå vilka typer av förfrågningar/svar som är tillgängliga (matris, sträng och så vidare). |
|  | [Webbplatssidor](/help/c-target/c-audiences/c-target-rules/site-pages.md#ts) | Avsnittet &quot;Felsökning&quot; har lagts till. |
| 24 oktober 2019 | [Rekommendationer - frågor och svar](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#section_DB3F40673AED42228E407C05437D99E9) | Uppdaterad text i följande frågor och svar: &quot;Varför kan Target ibland inte visa rekommendationer?&quot; |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | En anteckning har lagts till i ett känt fel som påverkar tidigare versioner av at.js (tidigare än version 2.2.0). |
|  | [Framgångsmått](/help/c-activities/r-success-metrics/success-metrics.md) | Anteckning om standardbeteendet för framgångsmått för aktiviteter som använder A4T har lagts till. |
| 22 oktober 2019 | [Kriterier/algoritmer](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms) | Lagt till rad för användarbaserade rekommendationer. |
|  | [Kriterier](/help/c-recommendations/c-algorithms/algorithms.md#custom-key) | Nytt avsnitt har lagts till: &quot;Använda en anpassad rekommendationsnyckel.&quot; |
|  | [Mål och målgrupper Frågor och svar](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) | Nya frågor och svar: &quot;När du skapar komplexa URL-strängar, utvärderar [!DNL Target] hela URL:en?&quot; |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.10.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target/Standard/Premium 19.9.1 (30 september 2019)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 17 oktober 2019 | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Uppdaterat ämne som förklarar hur Activity QA fungerar med cookies från tredje part. |
|  | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Versionsinformationen har uppdaterats med information om ändringar i det enhetliga skalet. |
| 10 oktober 2019 | [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state) | Nytt avsnitt har lagts till: &quot;serverState.&quot; |
|  | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Ytterligare information om versionerna at.js 2.2 och at.js 1.8. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ytterligare information om versionerna at.js 2.2 och at.js 1.8. |
|  | [Felsöka aktiviteter](/help/c-activities/c-troubleshooting-activities/troubleshooting-activities.md) | Nytt avsnitt har lagts till: &quot;Jag skapade en aktivitet med målgränssnittet och kan inte uppdatera den via API:t.&quot; |
| 9 oktober 2019 | [Serversida: implementera mål](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | Uppdaterat ämne. |
|  | [Versionsinformation - Målserversidans API:er](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Nytt ämne. |
|  | [Versionsinformation - Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Nytt ämne. |
|  | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Ytterligare information om V1/Delivery API och Node.js SDK. |
| 8 oktober 2019 | [Target Insider-nyhetsbrev](/help/r-release-notes/target-insider-newsletter.md) | Nytt ämne med länkar till den första omgången nyhetsbrev, med fler kommer. |
| 3 oktober 2019 | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Följande har lagts till: <ul><li>Känt fel och lösningar när du skapar en upplevelse utan ändringar med hjälp av at.js 2.*x* -bibliotek.</li><li>Samlingar, uteslutningar, villkor och designer som skapas via API är inte synliga i Target-användargränssnittet och kan bara redigeras via API.</li><li>Rekommendationsaktiviteter som skapas via API kan visas i användargränssnittet, men kan bara redigeras via API.</li></ul> |
|  | [Felsöka innehållsleverans](/help/c-activities/c-troubleshooting-activities/content-trouble.md#mboxdebug) | Anteckning har lagts till i avsnittet &quot;mboxDebug&quot;. |
| 2 oktober 2029 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till information om kommande versioner. |
| 1 oktober 2019 | [Profil och variabel ordlista](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Uppdaterad text i avsnittet Kundattribut. |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Uppdaterat kodexempel i avsnittet&quot;Call getOffers() for all views&quot;. |
| 30 september 2019 | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.9.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.7.1 (23 juli 2019) {#tgt-19-7-1}

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 27 september 2019 | [Hur länge ska du köra ett A/B-test?](/help/c-activities/t-test-ab/sample-size-determination.md) | Uppdaterad text om beräkningen av målprovets storlek. |
|  | [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Uppdaterad text om beräkningen av målprovets storlek. |
| 24 september 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Ändrad till 30 september 2019 för Target/Standard 19.2.1. |
|  | [Rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md) | Utbildningsvideo har lagts till. |
| 10 september 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Lagt till information om Target Standard/Premium 19.9.1. |
| 9 september 2019 | [AEM Experience fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md#considerations) | Avsnittet &quot;Överväganden&quot; har lagts till. |
|  | [Google Chrome SameSite cookie-principer](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) | Uppdaterad text för hela ämnet. |
|  | [CSP (Content Security Policy)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/content-security-policy.md) | Nytt ämne. |
| 6 september 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till information om Target Standard/Premium 19.9.1 (10 september 2019). |
|  | [Mål för mobilappar - frågor och svar](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | Nytt ämne. |
| 4 september 2019 | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Uppdaterat ämne. |
| 23 augusti 2019 | [Förhandsvisning av målmobiler](/help/c-target-mobile-app/target-mobile-preview.md) | Uppdaterat kodfragment i `AndroidManifest.xml`. |
|  | [Egna parametrar](/help/c-target/c-audiences/c-target-rules/custom-parameters.md#considerations) | Nytt avsnitt har lagts till: &quot;Överväganden.&quot; |
|  | [Överför anpassade villkor](/help/c-recommendations/c-algorithms/recommendations-csv.md) | Uppdaterad följande mening: Uppdateringar av anpassade villkor är som standard&quot;kumulativa&quot;. Nya nyckelvärdepar som anges i CSV-överföringsfilen skriver över befintliga nyckelvärdepar. Befintliga nyckelvärdepar som inte har nycklar angivna i CSV-överföringen är fortfarande tillgängliga för leverans och upphör att gälla om 31 dagar från den tidpunkt då de senast överfördes som en del av CSV-filen. |
| 20 augusti 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Uppskjuten version av Target/Premium 19.8.1 (20 augusti 2019). Innehåll från den här versionen kommer att införlivas i version 19.9.1 (24 september 2019). |
|  | [Vanliga frågor om design](/help/c-recommendations/c-design-overview/template-faq.md) | Följande frågor och svar har lagts till: &quot;Det rekommenderade objektets pris visar inte båda värdena till höger om decimalkommat. Hur visar jag dem?&quot; |
| 16 augusti 2019 | [Profilsynkronisering i realtid för mbox3rdPartyID](/help/c-target/c-visitor-profile/3rd-party-id.md) | Nytt avsnitt har lagts till: &quot;Överväganden.&quot; |
|  | [Skapa en rekommendationsaktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md) | Utbildningsvideo har lagts till. |
|  | [Feeds](/help/c-recommendations/c-products/feeds.md) | Utbildningsvideor har lagts till. |
|  | [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) | Utbildningsvideo har lagts till. |
|  | [Överför anpassade villkor](/help/c-recommendations/c-algorithms/recommendations-csv.md) | Utbildningsvideo har lagts till. |
|  | [Skapa villkorssekvenser](/help/c-recommendations/c-algorithms/create-criteria-sequence.md) | Utbildningsvideo har lagts till. |
|  | [Skapa en design](/help/c-recommendations/c-design-overview/create-design.md) | Utbildningsvideo har lagts till. |
|  | [Samlingar](/help/c-recommendations/c-products/collections.md) | Utbildningsvideo har lagts till. |
|  | [Undantag](/help/c-recommendations/c-products/exclusions.md) | Utbildningsvideo har lagts till. |
| 14 augusti 2019 | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Uppdaterad text och utökad videolänk för utbildning. |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Tydligare information om `consumerID` nyckeln. |
|  | [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#move) | Uppdaterad information i avsnittet Layout > Flytta. |
| 12 augusti 2019 | [Redigera en aktivitet eller spara som utkast](/help/c-activities/edit-activity.md#classic) | Nytt avsnitt har lagts till: &quot;Arbeta med äldre aktiviteter som skapats i Recommendations Classic.&quot; |
| 9 augusti 2019 | [Hur at.js fungerar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) | Nytt avsnitt har lagts till: &quot;How at.js renders offers with HTML content.&quot; |
|  | [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#considerations) | Nytt avsnitt har lagts till: &quot;Överväganden.&quot; |
| 7 augusti 2019 | [Förhämta erbjudandeinnehåll](/help/c-target-mobile-app/prefetch-offer-content.md) | Observera att förhämtningsfunktionen i SDK:er inte stöds för aktivitetstyperna Automatiskt mål, Automatisk allokering och Automatiserad personalisering. |
|  | [Felsöka integreringen med Analytics och Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md#unspecified) | Uppdaterad anteckning som anger hur lång tid det tar att slutföra klassificeringsprocessen. |
|  | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#unspecified) | Uppdaterad anteckning som anger hur lång tid det tar att slutföra klassificeringsprocessen. |
|  | [Sekretess- och dataskyddsbestämmelser](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) | Uppdaterat ämne som innehåller information om California Consumer Privacy Act (CCPA). |
|  | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#metrics) | Uppdaterat övervägande om att använda [!UICONTROL Activity Impressions] och [!UICONTROL Activity Conversions] mäta i [!DNL Analysis Workspace]. |
| 1 augusti 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Viktigt meddelande om API-stöd för Enterprise Permissions har lagts till. |
|  | [Ge Adobe I/O-integrationer åtkomst till arbetsytor och tilldela roller](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md) | Nytt ämne. |
| 31 juli 2019 | [Introduktion till rekommendationer](/help/c-recommendations/introduction-to-recommendations.md) | Nytt ämne. |
|  | [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md#recently-viewed) | Anteckning har lagts till i nyligen visade objekt. |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#preview) | Ett känt fel har lagts till med länkar för förhandsgranskning av Activity QA. |
| 29 juli 2019 | [Vanliga frågor om rapportering](/help/c-reports/reporting-frequently-asked-questions.md) | Nya frågor och svar: &quot;Varför innehåller mina [!UICONTROL Experience Targeting] (XT)-rapporter mätvärden för kontrollupplevelser?&quot; |
| 24 juli 2019 | [Uppgraderar från at.js 1.*x* to at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Nytt avsnitt har lagts till: [Stöd för spårning mellan domäner i at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain) |
|  | [Apple Intelligent Tracking Prevention (ITP) 2.*x *](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Nytt ämne. |
|  | [Rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md#status) | Nytt avsnitt har lagts till: &quot;Vi ser rekommendationserbjudandets status.&quot; |
|  | [Feeds](/help/c-recommendations/c-products/feeds.md) | Uppdaterade raden&quot;Importerar objekt&quot; och lade till&quot;Feed Imported at *time*&quot;-rad under [Feed Status](/help/c-recommendations/c-products/feeds.md#status). |
|  | [Katalogsökning](/help/c-recommendations/c-products/catalog-search.md) | Uppdaterad text om hur katalogen uppdateras. |
|  | [Så här fungerar Adobe Target](/help/c-intro/how-target-works.md#bots) | Nytt avsnitt har lagts till: &quot;Bot.&quot; |
|  | [Profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md#best) | Lagt till metodtips för att undvika långsam exekvering av regex. |
|  | [Feeds](/help/c-recommendations/c-products/feeds.md#steps) | FTP-serverinställningar som stöds har lagts till i steg. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ytterligare information om at.js 2.1.1. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.7.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.6.1 (26 juni 2019) {#tgt-19-6-1}

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 10 juli 2019 | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Tillagd begränsningsinformation för följande objekt:<ul><li>Antal erfarenheter per aktivitet.</li><li>Antal framgångsmått per aktivitet.</li><li>Antal rapportmålgrupper/segment per aktivitet.</li><li>Antal målgrupper per ruta, mätvärden och upplevelse.</li><li>Antal unika värden per målregel.</li><li>Antal unika målgrupper per målinriktningsregel.</li><li>Antal unika målinriktningsregler per aktivitet.</li><li>Antal aktiva profilskript.</li><li>Antal profilskript totalt.</li><li>Antal totala slingor per profilskript.</li><li>Antal aktiva aktiviteter.</li><li>Antal aktiva sparade (och inte avslutade) aktiviteter.</li><li>Antal egenskaper.</li><li>Antal erbjudanden.</li></ul> |
|  | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till information om den kommande Target 19.7.1-versionen (23 juli 2019).<br>Observera att informationen kan komma att ändras. |
| 8 juli 2019 | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Tillagd information som förklarar varför du bör använda CNAME. |
| 28 juni 2019 | [Kända problem och lösta](/help/r-release-notes/known-issues-resolved-issues.md#redirect)<br>[problemFörväntade datavariationer mellan Target och Analytics när A4](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)<br>[TRedirect offers-A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Lagt till information om ett känt fel som gör att ett begränsat antal kunder använder omdirigeringar med A4T för att se en högre andel träffar. |
| 26 juni 2019 | [Alternativ för visuell upplevelse](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles) | Lagt till information om [!UICONTROL Background] alternativet under *Stilar*. |
|  | [Visual Experience Composer för Single Page App (SPA)](/help/c-experiences/spa-visual-experience-composer.md) | Lagt till information om [!UICONTROL Clone] åtgärden. |
|  | [Klickspårning](/help/c-activities/r-success-metrics/click-tracking.md) | Lagt till information om [!UICONTROL Selected Elements] panelen. |
|  | [Visual Experience Composer för Single Page App (SPA)](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings) | Nytt avsnitt: &quot;Inställningar för sidleverans för SPA VEC.&quot; |
|  | [Välj kontroll för din automatiska personalisering eller Automatisk målaktivitet](/help/c-activities/t-automated-personalization/experience-as-control.md) | Nytt ämne. |
|  | [Google Chrome SameSite cookie-principer](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) | Nytt ämne. |
|  | [Datainsamling för målpersonaliseringsalgoritmer](/help/c-activities/t-automated-personalization/ap-data.md) | Nya tabeller har lagts till för att förklara enskilda attribut och för att ge exempel. |
|  | [Automatiserad personalisering - frågor och svar](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Nya frågor och svar: &quot;Kan jag ange en specifik upplevelse som ska användas som kontroll?&quot;<br>Följande frågor och svar har redigerats: &quot;Vad är de bästa sätten att skapa en automatiserad personaliseringsaktivitet?&quot; |
|  | [Automatiskt mål](/help/c-activities/auto-target-to-optimize.md) | Ytterligare information och frågor och svar om hur man anger en specifik upplevelse som ska användas som kontroll.<br>Uppdaterade avsnittet &quot;Bestämma trafikallokering&quot;. |
|  | [Skapa en automatiserad personaliseringsaktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md) | Steget med information om hur du väljer en viss upplevelse som standard har lagts till. |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Lagt till information om rapporter som inte kan återges för aktiviteter med Automatiskt mål i vissa situationer. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.6.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.5.1 (21 maj 2019) {#tgt-19-5-1}

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 19 juni 2019 | [Lägg till kampanjer](/help/c-recommendations/t-create-recs-activity/adding-promotions.md) | Lagt till information om kampanjer som dedupliceras mot objekt som rekommenderas av kriterierna för din aktivitet. |
| 13 juni 2019 | [Viktiga attributrapporter](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | Nya frågor och svar: &quot;Varför får vissa erbjudanden/upplevelser med en lägre konverteringsgrad större trafik jämfört med andra erbjudanden/upplevelser för ett visst automatiserat segment?&quot; |
|  | [Så här fungerar Adobe Target](/help/c-intro/how-target-works.md) | Viktig information om hur du använder Target i Kina har lagts till. |
|  | [Webbläsare som stöds](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Tog bort Microsoft Internet Explorer 11 (IE 11) från avsnittet Target Standard/Premium interface. Target stöder inte längre eller behåller kompatibiliteten för IE 11. Den här ändringen påverkar bara målgränssnittet. Innehållsleveransen påverkas inte. Ändringen följer liknande meddelanden från Adobe Analytics, Adobe Experience Platform och Adobe Audience Manager. Vi rekommenderar att användare byter till en webbläsare som stöds. |
| 11 juni 2019 | [Skapa aktivitet](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | Observera att det inte är nödvändigt att ange en spårningsserver om du använder A4T. |
|  | [Verksamhet](/help/c-activities/activities.md) | Viktigt att du inte kan återställa en borttagen aktivitet. Som bästa praxis kan du arkivera en aktivitet så att den kan arkiveras, om det behövs. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Begränsningen som anger att Experience Cloud Debugger inte stöds fullt ut i at.js 2.x har tagits bort. |
| 7 juni 2019 | [Anpassa en design med Snabb](/help/c-recommendations/c-design-overview/customizing-a-template.md#default) | Nytt avsnitt har lagts till: &quot;Scenario: Skapa en 4 x 2 standardrekommendationsdesign med logik för null-kontroll.&quot; |
|  | [Utbildningsvideor för Adobe Target Standard och Premium](/help/c-intro/target-standard-premium-training-videos.md#tutorials) | Uppdaterad länk till den nya webbplatsen för Adobe Target-självstudiekurser. |
| 6 juni 2019 | [adobe.target.triggerView (viewName, options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) | Beskrivningen av `options > page` parametern har uppdaterats. |
|  | [Administratörssteg](/help/administrating-target/start-target.md) | Hela artikeln har uppdaterats. |
|  | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Preliminär versionsinformation för Target 19.6.1 har lagts till. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Uppdaterad information om att distribuera at at.js med Adobe Launch, vilket är den metod som rekommenderas för distribution. |
|  | [Målgrupper](/help/c-intro/target-key-concepts.md) | Mindre textredigeringar. |
| 3 juni 2019 | [Versionsinformation (aktuell)](/help/r-release-notes/release-notes.md) | Information om den kommande versionen av at.js 2.1.0 har lagts till. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om den kommande versionen av at.js 2.1.0 har lagts till. |
|  | [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md) | Nytt avsnitt har lagts till: &quot;Loggning av analys på klientsidan.&quot; |
|  | [Analyser för Target-implementering](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) | Ändrat steg 7. |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Rader har lagts till i tabellen för följande fältnamn:<ul><li>Request > experienceCloud</li><li>Request > experienceCloud > analytics</li><li>Request > experienceCloud > analytics > log</li></ul> |
|  | [Funktionerna at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md) | Raden har lagts till i tabellen för `adobe.target.sendNotifications(options)`. |
|  | [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md) | Nytt ämne. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#integrations) | Ytterligare information om stöd för Adobe-deltagande finns i at.js 2.1.0. |
|  | [Sekretess och allmänna dataskyddsföreskrifter](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) | Updated information about opt-in support in at.js 2.1.0. |
| 31 maj 2019 | [Mobil](/help/c-target/c-audiences/c-target-rules/mobile.md) | En kommentar om målenheter som kör iOS 12.2 har lagts till. |
|  | [Planera och implementera rekommendationer](/help/c-recommendations/plan-implement.md) | Uppdaterat kodexempel. |
| 30 maj 2019 | [Åtkomstmål från Adobe Experience Cloud](/help/c-intro/target-access-from-mac.md#doc-lang) | Dokumentationen finns nu på förenklad kinesiska. |
|  | [Hämta data i en CSV-fil](/help/c-reports/downloading-data-in-csv-file.md) | Lagt till ny caveat i avsnittet Exportera beställningsinformation till CSV: &quot;Målgrupper som används i gränssnittet för målrapportering överförs inte till nedladdningsrapporten.&quot; |
|  | [Rapportinställningar](/help/c-reports/c-report-settings/report-settings.md) | Uppdaterade skärmbilder. |
| 29 maj 2019 | [Kategoritillhörighet](/help/c-target/c-visitor-profile/category-affinity.md) | Uppdaterad text för att förtydliga skillnaden mellan `user.categoryId` och `entity.categoryId`. |
|  | [Migrera från mbox.js till at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md) | Omlokaliserat avsnitt till detta ämne: Fördelar med at.js. |
|  | [at.js Frågor och svar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md) | Omlokaliserat avsnitt till detta ämne: &quot;Hur påverkar at.js och mbox.js sidinläsningstiden?&quot; |
|  | [Överför dynamiska data till erbjudanden](/help/c-experiences/c-manage-content/passing-profile-attributes-to-the-html-offer.md) | Syntaxen i beteenderaden Tidigare har korrigerats. |
| 28 maj 2019 | [Åtkomstmål från Adobe Experience Cloud](/help/c-intro/target-access-from-mac.md#doc-lang) | Nytt avsnitt har lagts till: &quot;Ändra språket för Target-produktdokumentationen.&quot; |
|  | [Identifiera en vinnare](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Uppdaterad information om p-värden. |
|  | [Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md) | Felsökningsavsnittet har lagts till om hur Target hanterar iframes på flera nivåer. |
|  | [Rekommendationer - frågor och svar](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Nya frågor och svar: &quot;Vilken är den förväntade tidsramen för import av rekommendationer för åtgärder?&quot; |
|  | [Implementera mål med Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) | Uppdaterade informationen under&quot;Advantages of Implementation at.js Using the Target Launch Extension&quot;. |
|  | [Felsöka innehållsleverans](/help/c-activities/c-troubleshooting-activities/content-trouble.md) | Ett nytt felsökningsavsnitt har lagts till om att at.js inte aktiverar mbox om du använder en ogiltig doctype. |
| 24 maj 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Ytterligare information om at.js 2.1.0. |
| 23 maj 2019 | [Hantera undantag](/help/c-activities/t-automated-personalization/managing-exclusions.md) | Lagt till information och länk för att begränsa vilka målgrupper som kan se specifika erbjudanden i AP-aktiviteter med målinriktningsregler. |
|  | [Serversida: implementera mål](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | Texten i introduktionen har uppdaterats. |
|  | [Erfarenheter och erbjudanden](/help/c-experiences/experiences.md) | Texten i introduktionen har uppdaterats. |
|  | [Målgrupper](/help/c-target/target.md) | Texten i introduktionen har uppdaterats. |
|  | [Framgångsmått](/help/c-activities/r-success-metrics/success-metrics.md) | Texten i introduktionen har uppdaterats. |
|  | [Rapporter](/help/c-reports/reports.md) | Texten i introduktionen har uppdaterats. |
|  | [Visual Experience Composer (VEC)](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) | Texten i introduktionen har uppdaterats. |
|  | [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) | Texten i introduktionen har uppdaterats. |
|  | [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Texten i introduktionen har uppdaterats. |
|  | [Ordlista](/help/c-intro/glossary.md) | Flera poster har lagts till och uppdaterats. |
| 22 maj 2019 | [Introduktion till Target](/help/c-intro/intro.md#kit) | Länk har lagts till i Adobe Target Welcome Kit. |
| 21 maj 2019 | [Visual Experience Composer för Single Page App (SPA)](/help/c-experiences/spa-visual-experience-composer.md) | <ul><li>Uppdaterad information om alternativet &quot;Flytta&quot;.</li><li>Observera att du kan utföra många åtgärder innan sidan läses in i VEC, eller även om sidan inte läses in helt. </li></ul> |
|  | [Användare](/help/administrating-target/c-user-management/c-user-management/user-management.md) | Uppdaterad text, uppdaterade bilder och tillagd utbildningsvideo. |
|  | [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | Odaterad text och bilder. |
|  | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Teckengränsen för kundattributets alias-ID har lagts till. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.5.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.4.2 (30 april 2019) {#target-19-4-2}

**Obs**: Target Standard/Premium 19.4.1 var en underhållsversion som uppdaterade användargränssnittet i Adobe Experience Cloud för att återspegla varumärkes- och produktförändringar.

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 15 maj 2019 | [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#triggerview) | Observera att du måste utlösa händelserna `at-view-start` och `at-view-end` . |
|  | [Överför dynamiska data till erbjudanden](/help/c-experiences/c-manage-content/passing-profile-attributes-to-the-html-offer.md) | Uppdaterad text. |
| 13 maj 2019 | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Objekt har lagts till i listan med överväganden om hur du använder QA-läge i en flersidig aktivitet. |
|  | [Inkludera samma upplevelse på liknande sidor](/help/c-experiences/c-visual-experience-composer/temtest.md) | Uppdaterade steg för att matcha användargränssnittet. |
|  | [at.js Frågor och svar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md) | Nya frågor och svar: &quot;Vilken HTML-dokumenttyp kräver at.js?&quot; |
| 10 maj 2019 | [Inställningar](/help/administrating-target/r-target-account-preferences/target-account-preferences.md) | Uppdaterad text och bild. |
|  | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Uppdaterad text. |
| 9 maj 2019 | [A4T-rapportering](/help/c-integrating-target-with-mac/a4t/reporting.md#reports-in-analysis-workspace) | Nytt avsnitt har lagts till: &quot;Rapporter på analysarbetsytan.&quot; |
|  | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Nya frågor och svar: &quot;Kan jag visa mina målaktivitetsdata i Adobe Analysis Workspace?&quot; |
|  | [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md#faqs) | Nya frågor och svar: &quot;Spelas klickspårskonverteringar in om en omdirigeringssida och aktivitets-URL:en tillhör olika egenskaper?&quot; |
| 8 maj 2019 | [Utbildningsvideor för Adobe Target Standard och Premium](/help/c-intro/target-standard-premium-training-videos.md) | Uppdaterat innehåll och länkar. |
|  | [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md) | Uppdaterad text i anteckningen under `entity.id` variabeln. |
| 1 maj 2019 | [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md) | Korrigerad skiftläge i följande variabelnamn:<br>Ändrad `pageURL` till `pageUrl`.<br>Ändrad `thumbnailURL` till `thumbnailUrl`. |
| 30 april 2019 | [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | <ul><li>Nytt avsnitt har lagts till: &quot;Stilar.&quot;</li><li>En tabell med HTML5-taggar som kan kapslas har lagts till.</li></ul> |
|  | [Klickspårning](/help/c-activities/r-success-metrics/click-tracking.md) | Information om DOM-sökvägsfunktionen har lagts till i avsnittet &quot;Överväganden&quot;. |
|  | [Feed-status och -indikatorer](/help/c-recommendations/c-products/feeds.md#section_5DDC2DECF70A42FDAFF2235E91371537) | Uppdaterade tabellen&quot;Feed Status&quot;. |
|  | [Arbeta med innehåll i biblioteket](/help/c-experiences/c-manage-content/assets-working.md) | Lagt till information om hur du tar bort mappar och bilder från resursbiblioteket. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.4.2 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.3.1 (29 mars 2019) {#section-19-3-1}

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 29 april 2019 | [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md#section_31D3450ADEAE4A29963A34F8E8C19FE0) | Följande frågor och svar har lagts till: &quot;Varför får jag ett felmeddelande om att ingen egenskap är associerad med den här aktiviteten, trots att det finns en tilldelad egenskap?&quot; |
| 24 april 2019 | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#types) | Anteckning har lagts till i avsnittet Aktivitetstyper. |
|  | [Testa en e-postbild i Adbox](/help/c-implementing-target/c-non-javascript-based-implementation/testing-email-image-adbox.md) | Omformaterat kodexempel. |
|  | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Korrigerade mindre typografi. |
| 23 april 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Uppdaterade versionsinformation och ändrade datum till 30 april (29 april). |
| 22 april 2019 | [Åtkomstmål från Adobe Experience Cloud](/help/c-intro/target-access-from-mac.md) | Nytt avsnitt har lagts till: &quot;Ändra standardspråk för målgränssnittet.&quot; |
| 19 april 2019 | [Rapport över automatiserade segment](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md#section_740910A52FA646B4AC9452F98C2F5719) | Nya frågor och svar: &quot;Finns det någon logik i ordningen som attribut visas i ett segmentkort?&quot; |
|  | [Feeds](/help/c-recommendations/c-products/feeds.md#section_5DDC2DECF70A42FDAFF2235E91371537) | Uppdaterat Viktigt som beskriver när överförda enheter upphör att gälla. |
| 16 april 2019 | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Nya frågor och svar: &quot;Kan jag ändra procentandelen trafiktilldelning i en aktivitet som använder A4T efter att aktiviteten har aktiverats?&quot; |
| 15 april 2019 | [Inledande etablering - Vanliga frågor om A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-initial-provisioning.md) | Nya frågor och svar: &quot;Hur skapar jag en A4T-aktivitet på flera sidor?&quot; |
|  | [Krav på användarbehörighet](/help/c-integrating-target-with-mac/a4t/account-reqs.md) | Uppdaterat ämne. |
|  | [Kända fel och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Kända fel för exkluderingsgrupper har flyttats till tabellen över lösta problem. |
| 11 april 2019 | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Uppdaterade kodexempel. |
|  | [Hjälptillägg för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Nya skärmbilder. |
|  | [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Följande frågor och svar har lagts till: &quot;Bör jag ta bort en underpresterande upplevelse från en autotilldelning-aktivitet för att snabba upp processen att fastställa en vinnare?&quot; |
| 10 april 2019 | [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md) | Mindre textuppdateringar av avsnittet Implementeringskrav (kraven har ordnats om). |
|  | [adobe.target.triggerView (viewName, options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) | Uppdaterad text för parametern &quot;options > page&quot;. |
| 8 april 2019 | [Förväntade datavariationer mellan Target och Analytics när A4T används och inte används](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md) | Uppdaterad [förväntad datavarians vid användning av A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md#expected-using-a4t). |
|  | [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md) | Uppdaterad information om A4T och omdirigeringar under [Vad bidrar till delar av data?](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#section_C9C906BEAA7D44DAB9D3C03932A2FEB8) |
|  | [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md#section_A0D2EF18033D4C3997B08A6EBB34C17A) | Uppdaterade minimikraven för att använda A4T med omdirigeringar (at.js version 1.6.2). |
|  | [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58) | <ul><li>Uppdaterade minimikraven för att använda A4T med omdirigeringar (at.js version 1.6.2).</li><li>Tillagd information som beskriver hur datamätningar räknas när en Target-träff inträffar, men ingen Analytics-träff inträffar. </li> |
|  | [Gränser](/help/r-troubleshooting-target/target-limits.md#excludedid) | Lagt till information om gränserna för parametern `excludedIDs` mbox. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#response-tokens) | Nytt avsnitt har lagts till: Svarstoken. |
| 5 april 2019 | [Adobe Target Basics webbinarium: Introduktion till rekommendationer](/help/c-recommendations/recommendations.md#intro-to-recs) | Länk har lagts till i inspelningen av webbseminariet&quot;Introduction to Recommendations&quot;. |
|  | [Activity QA bookmarklet](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | Uppdaterad JavaScript-kod för QA-bokmärkesaktiviteten. |
|  | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Uppdaterade den preliminära versionsinformationen för Target 19.4.1- och Target 19.4.2-utgåvorna, båda planerade i april 2019. |
| 4 april 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lade till preliminär versionsinformation för Target 19.4.1- och Target 19.4.2-utgåvorna, båda planerade i april 2019. |
| 30 mars 2019 | [Gränser](/help/r-troubleshooting-target/target-limits.md#excludedid) | Lagt till information om gränserna för parametern `excludedID` mbox. |
| 29 mars 2019 | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Följande kända fel har lagts till: &quot;På SPA-webbplatser (Single Page Application) kan du inte redigera åtgärder under [!UICONTROL Modifications] panelen om du avbryter inläsningen.&quot;<br>Följande kända fel har flyttats till avsnittet Lösta problem: &quot;v1-versionen av erbjudandets API:er på Adobe I/O behandlar alla erbjudanden som skapats via Target så att de ligger i standardarbetsytan.&quot; |
| 28 mars 2019 | [Visual Experience Composer (VEC)](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) | Följande nya avsnitt har lagts till:<ul><li>[Avbryt inläsning av en sida i VEC.](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md#cancel-loading)</li><li>[Redigera en sida medan sidan läses in eller när sidan inte kan läsas in](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md#loading).</li></ul> |
|  | [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Nytt avsnitt: &quot;[Navigera mellan element med DOM-sökvägen](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path).&quot; |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#cancel) | Ett aktuellt känt fel som uppstår när du avbryter inläsningen av en sida i VEC har lagts till. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.3.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.2.1 (19 februari 2019) {#section-19-2-1}

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 20 mars 2019 | [at.js Frågor och svar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md) | Uppdaterade följande frågor och svar: &quot;[Kan jag läsa in Target-biblioteket asynkront?](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#section_AB9A0CA30C5440C693413F1455841470)&quot; |
|  | [Profilsynkronisering i realtid för mbox3rdPartyID](/help/c-target/c-visitor-profile/3rd-party-id.md) | Anteckning har lagts till längst ned på sidan. |
|  | [](/help/r-troubleshooting-target/target-limits.md)<br>[LimitsCustom-entitetsattribut](/help/c-recommendations/c-products/custom-entity-attributes.md#limits) | Lagt till information om gränser för anpassade entitetsattribut. |
|  | [Mål och målgrupper Frågor och svar](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md#strings-that-represent-numbers) | Uppdaterad text. |
|  | [Skapa nya villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md#custom) | Ett nytt avsnitt som förklarar hur du skapar profilbaserade grupperingar för popularitetsalgoritmer har lagts till: &quot;Använd en anpassad rekommendationsnyckel.&quot; |
| 19 mars 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Ytterligare information om at.js, version 2.0.1 och 1.7.1. |
|  | [Visa rapporter - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Följande frågor och svar har lagts till: &quot;Stöder A4T virtuella rapportsviter?&quot; |
| 18 mars 2019 | [Versionsinformation för målversion (prerelease)](/help/r-release-notes/target-release-notes.md) och [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ytterligare information om at.js, version 2.0.1 och 1.7.1. |
|  | [Metoder för att hämta data till Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#section_92AB4820A5624C669D9A1F1B6220D4FA) och [Customer-attribut](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Tillagt: Du kan inte skicka följande tecken i `mbox3rdPartyID`: plustecken (+) och snedstreck (/). |
| 15 mars 2019 | [Innan du implementerar](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md) | Viktigt: Ändringar i at.js eller mbox.js stöds inte av Adobes kundtjänst. |
| 14 mars 2019 | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Ändrade datumet för målstandarden/premiumutgåvan 19.3.1 till den 29 mars 2019. |
| 13 mars 2019 | [Skapa en automatiserad personaliseringsaktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md) | Texten på raden Konverteringsmått har uppdaterats. |
|  | [Profilattribut](/help/c-target/c-visitor-profile/profile-parameters.md) | Nytt avsnitt har lagts till: &quot;JavaScript-referens för parametrar för skriptprofiler.&quot; |
|  | [Funktionerna at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md) | Omstrukturerad sida och nya sidor för varje at.js-funktion som gör det enklare att komma åt information. |
|  | [Hur at.js fungerar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | Introduktionsstycke har lagts till för att förklara en implementering på klientsidan. |
|  | [Rekommendationer - frågor och svar](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Följande frågor och svar har lagts till: &quot;Kan jag dynamiskt utesluta en enhet?&quot; |
| 12 mars 2019 | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) och [Debug at.js med Adobe Experience Cloud Debugger](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md) | Felsökaren stöds nu för integrering med at.js 2.x. |
| 11 mars 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md), versionsinformation för<br>[mål (prerelease)](/help/r-release-notes/target-release-notes.md)och krypteringsändringar för <br>[TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | Uppdaterad text som indikerar att TLS-ändringar kommer att inträffa den 1 **april 2019**. |
|  | [adobe.target.getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Följande avsnitt har lagts till: &quot;Hämta och återge data från flera rutor via getOffers() och applyOffers().&quot; |
| 6 mars 2019 | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | At_property-raden har lagts till i tabellen&quot;at.js 1.x parameters to at.js 2.x payload mapping&quot;. |
|  | [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) | Nytt avsnitt har lagts till: &quot;Använd TriggerView för att säkerställa att A4T fungerar korrekt med at.js 2.x och SPA.&quot; |
| 4 mars 2019 | [Rekommendationer Classic-dokumentation](/help/c-recommendations/recommendations-classic-documentaton.md) | Nytt ämne. |
|  | [Rekommendationer, klassiska jämfört med rekommendationer i Target Premium](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md) | Lagt till information om rekommendationer som ett erbjudande. |
| 28 februari 2019 | [Verksamhet](/help/c-activities/activities.md) | Uppdaterad text och bilder. |
|  | [Introduktion till Target](/help/c-intro/intro.md) | Lagt till&quot;Rekommendationer som ett erbjudande&quot; under&quot;Target Premium&quot;. |
|  | [Målgrupper](/help/c-intro/target-key-concepts.md) | Uppdaterad tabell för aktivitetstyper. |
| 26 februari 2019 | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Ett känt fel om stöd för företagsbehörigheter i mål-API:er har lagts till. |
| 25 februari 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md), versionsinformation för <br>[mål (prerelease)](/help/r-release-notes/target-release-notes.md)och krypteringsändringar för <br>[TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | Uppdaterade följande information:<br>Den 20 februari 2019 uppgraderades Adobe Target-infrastrukturen i EMEA-, Japan- och APAC-regionerna för att inte längre samla in data från slutanvändare med äldre enheter eller webbläsare som inte stöder TLS 1.1 eller senare. Samma uppgradering planeras för Nordamerika den 4 **mars 2019**. Att migrera till TLS 1.2 ger bättre säkerhet. Det är viktigt att du går igenom detaljerna och planerar ändringarna för en smidig övergång. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#payload-mapping) | Nytt avsnitt: &quot;at.js 1.x-parametrar till at.js 2.x-nyttolastmappning.&quot; |
|  | [Felsökning av problem relaterade till Förbättrad Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) | Kolumnen Värdnamn har lagts till i IP-adresserna i vitlistan. |
| 22 februari 2019 | [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | Avsnittet&quot;Hämta ditt arbetsyte-ID&quot; har lagts till. |
| 20 februari 2019 | [Kategoritillhörighet](/help/c-target/c-visitor-profile/category-affinity.md) | Avsnittet Kategoritillhörighetsalgoritm har uppdaterats. |
| 19 februari 2019 | [Visual Experience Composer för Single Page App (SPA)](/help/c-experiences/spa-visual-experience-composer.md) | Nya teman och utbildningsvideor. |
|  | [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) | Nya teman och utbildningsvideor. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ytterligare information om at.js, version 1.7.0 och 2.0.0. |
|  | [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Nytt ämne och utbildningsvideo. |
|  | [Funktionerna at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md) | Uppdaterat ämne som återspeglar förändringar i och med introduktionen av at.js 2.x.<br>Det finns tre nya funktioner för at.js 2.x.<ul><li>adobe.target.getOffers(options)</li><li>adobe.target.applyOffers(options)</li><li>adobe.target.triggerView (viewName, options)</li></ul> |
|  | [Hur at.js fungerar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | Uppdaterat ämne som återspeglar förändringar i och med introduktionen av at.js 2.x. och har lagt till utbildningsvideo. |
|  | [Hur at.js hanterar flimmer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md) | Uppdaterat ämne som återspeglar förändringar i och med introduktionen av at.js 2.x. |
|  | [at.js Frågor och svar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md) | Uppdaterat ämne som återspeglar förändringar i och med introduktionen av at.js 2.x. |
|  | [Felsöka at.js med Adobe Experience Cloud Debugger](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md) | Observera att Adobe Experience Cloud Debugger Network Request och Mbox Trace inte stöds ännu för at.js 2.x. |
|  | [at.js cookies](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | Nytt ämne. |
|  | [Rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md) | Nytt ämne. |
|  | [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | <ul><li>Lagt till information om hur du använder åtgärden för att lägga till rekommendationer till en upplevelse i en A/B-test eller Experience Targeting-aktivitet. [!UICONTROL Insert Before, Insert After, or Replace With]</li><li>Lagt till information om hur du använder åtgärden för att lägga till AEM Experience Fragments i en upplevelse. [!UICONTROL Insert Before or Insert After]</li></ul> |
|  | [Hjälptillägg för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Nytt ämne. |
|  | [Integritet och allmänna dataskyddsförordningen](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR) | Mindre redigeringar och information om Opt-in-funktioner samt at.js 1.7.0 och at.js 2.x. |
|  | [Kända problem och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md) | Lade till kända problem med mål-API:er. |
|  | [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md) | Anteckning om att angivna värden för entitetsattribut upphör att gälla efter 61 dagar. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.2.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 19.1.1 (22 januari 2019) {#section-19-1-1}

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 2 februari 2019 | [Versionsinformation](/help/r-release-notes/target-release-notes.md) för mål (prerelease) | Uppdaterade förhandsversionsinformation för [!DNL Target] version 19.2.1 (19 februari 2019). |
| 30 januari 2019 | [Målgrupper och målgrupper](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) | Nya frågor och svar: Strängar som representerar tal (flyttal stöds också) jämförs som tal. |
| 29 januari 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Enterprise Permissions support in Target APIs availability date to February 21, 2019. |
|  | [Systemstatusuppdateringar och proaktiva meddelanden](/help/r-release-notes/system-status-updates.md) | Avsnittet Proaktiva meddelanden har lagts till. |
| 22 januari 2019 | [](/help/c-recommendations/c-products/collections.md)<br>[](/help/c-recommendations/c-products/exclusions.md)<br>[CollectionsExclusionsCatalog](/help/c-recommendations/c-products/catalog-search.md)<br>[](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)<br>[searchSettingsRecommendations: filtrera samlingar och uteslutningar efter miljö (värdgrupp)](/help/administrating-target/hosts.md) | Lagt till information om filtrering av samlingar och undantag efter miljö (värdgrupp). |
|  | [Gränser](/help/r-troubleshooting-target/target-limits.md) | Uppdaterad information på raden Profilskriptvärde. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 19.1.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 18.11.1 (12 november 2018) {#section_4AD10E8B7EB04F96807FFDB763F31703}

| Datum | Ämne | Ändringar |
|--- |--- |--- |
| 16 januari 2019 | [Versionsinformation om mål (aktuell)](/help/r-release-notes/release-notes.md)<br>[Versionsinformation om mål (prerelease)](/help/r-release-notes/target-release-notes.md)<br>[om version at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om at.js version 1.6.4 har lagts till. |
| 10 januari 2019 | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md)<br>[Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md)<br>[TLS-krypteringsändringar (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | Datum då Target fullständigt kommer att fasa ut stödet för TLS 1.0-kryptering: 20 februari 2019. |
| 9 januari 2019 | [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Lagt till information om rekommendationer för att infoga före, infoga efter och ersätta med rader. |
|  | [Versionsinformation om mål (aktuell)](/help/r-release-notes/release-notes.md)<br>[Versionsinformation om mål (förhandsversion)](/help/r-release-notes/target-release-notes.md)<br>[Webbläsare som stöds](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Information om hur Target och Adobe Marketing Cloud upphör att fungera i Microsoft Internet Explorer 11 från och med mars 2019 har lagts till. |
|  | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till information för Target 19.1.1 och at.js 1.6.4. |
|  | [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information för version 1.6.4 av at.js har lagts till. |
|  | [Minimera antalet besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md) | Observera att efter 14 november 2016 kan kunderna inte längre skapa A4T-aktiviteter med omdirigeringserbjudanden. |
|  | [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Anteckning har lagts till under&quot;Varför räknas sidvyer på originalsidan och på omdirigeringssidan ibland?&quot; |
| 20 december 2018 | [Implementeringsmål för serversida](../c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | Lade till anteckning om CORS. |
| 14 december 2018 | [Implementera mål med Adobe Launch](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) | Länk till en ny utbildningsvideo: Implementera Target med Adobe Launch Tutorial. |
|  | [Insikter om personalisering - rapporter](../c-reports/c-personalization-insights-reports/personalization-insights-reports.md) | Länk till utbildningsvideo har lagts till. |
| 13 december 2018 | [Formulärbaserad Experience Composer](../c-experiences/form-experience-composer.md) | Uppdaterad text och bild. |
|  | [Kända problem och lösta problem](known-issues-resolved-issues.md) | Ett känt fel som indikerar att feedindexet Recommendations kan visa&quot;Väntar på index&quot; om objekten i flödet är desamma som i föregående körning har lagts till. |
|  | [Välj målgrupp](../c-activities/t-test-ab/t-test-create-ab/ab-audience.md) | Uppdaterade bilder. |
|  | [Lägg till upplevelse](../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md) | Uppdaterad bild. |
|  | [Skapa ett A/B-test](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) | Uppdaterade bilder. |
|  | [Testsammanfattning](../c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md) | Uppdaterad bild. |
|  | [Förhandsgranska upplevelser för ett multivariat test](../c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md) | Uppdaterad bild. |
|  | [Skapa kombinationer](../c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md) | Uppdaterad text och bilder. |
|  | [Skapa ett multivariata test](../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md) | Uppdaterad text och bilder. |
| 11 december 2018 | [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Tillagt att standardvärdet för overrideMboxEdgeServer är &quot;true&quot; från och med at.js version 1.6.2. |
| 7 december 2018 | [ Kända fel och lösta problem ](known-issues-resolved-issues.md) | Flyttade följande från tabellen Kända fel till tabellen Lösta problem: <ul><li>at.js: Mboxes som inte aktiveras i Microsoft Explorer 11-webbläsare efter uppgradering till at.js version 1.0 på grund av interaktionen mellan at.js och Visitor API 2.2.0.0.</li><li>Målinriktning: Det går för närvarande inte att söka efter en sträng som innehåller specialtecken (t.ex. ett mellanslag eller kommatecken) när målgrupper med geomål skapas.</li></ul> |
| 5 december 2018 | [ Insikter om personalisering - rapporter ](../c-reports/c-personalization-insights-reports/personalization-insights-reports.md) | Observera att personaliseringsInsikter-rapporterna endast är tillgängliga i standardmiljön. |
|  | [ Adobe Analytics som rapportkälla för Adobe Target (AT) ](../c-integrating-target-with-mac/a4t/a4t.md) | Uppdaterad tabell som indikerar att A4T stöder distributioner på serversidan. |
| 29 november 2018 | [ Uppskatta den trafik som krävs för ett lyckat test](../c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) | Mindre textuppdateringar och uppdaterade bilder. |
| 27 november 2018 | [ Verksamhet ](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) | Uppdaterad text och bilder. |
|  | [ Profilskriptattribut ](../c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2) | Observera att Target har en begränsning på 1 000 profilskript per konto. |
| 15 november 2018 | [ Versionsinformation om målversion (aktuell) ](../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A)<br>[ Versionsinformation om målversion (prerelease) ](../r-release-notes/target-release-notes.md#reference_4A966062C61048D1A81412E2DDB16E34)<br>[ på .js ](../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) | Information om at.js version 1.6.3 har lagts till. |
|  | [ Insikter om personalisering - rapporter ](../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) | Nya ämnen har lagts till i de nya personaliseringsinsikterna:  Automatiska segment och viktiga attribut. |
| 14 november 2018 | Versionsinformation 18.11.1 [ Målversion (aktuell) ](../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 18.10.1 (24 oktober 2018) {#section_F3DB9A89D944428DBEE04634EB712601}

| Datum | Ämne | Ändringar |
|--- |--- |--- |
| 8 november 2018 | [Adobe Analytics som rapportkälla för Adobe Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) | NodeJS SDK har lagts till i kompatibilitetstabellen. |
| 7 november 2018 | [Hur länge ska du köra ett A/B-test?](../c-activities/t-test-ab/sample-size-determination.md#concept_2801F552DB874C20B8A17C1B774C0383) | Redigerat ämne och lagt till ytterligare information. |
|  | [Versionsinformation för mål (prerelease)](../r-release-notes/target-release-notes.md#reference_4A966062C61048D1A81412E2DDB16E34) | Lagt till information om funktioner i Target 18.11.1. |
| 5 november 2018 | [Integrera rekommendationer med e-post](../c-recommendations/c-recommendations-faq/integrating-recs-email.md#reference_256B16C894864F24AF970E43DC174420) | Uppdaterad länk i alternativ 3. |
|  | [Kundattribut](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8) | Följande kommentar har lagts till:<br>**Viktigt **: Datakällans namn och attributnamnet får inte innehålla en punkt. |
| 31 oktober 2018 | [Systemstatusuppdateringar](../r-release-notes/system-status-updates.md#concept_5CBDF506BEFA40E483CC7DE0DA915EAD) | Uppdaterat ämne. |
|  | [Target Basics Webinar Series](../cmp-resources-and-contact-information.md#concept_11902FAC95C64479AABE020557A7EEE4) | Länk till Best Practices i inspelning av målgruppssegmentering har lagts till. |
| 29 oktober 2018 | [TLS-krypteringsändringar (Transport Layer Security)](../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) | Nytt avsnitt har lagts till: Förväntat beteende med webbläsare som endast stöder TLS 1.0. |
| 26 oktober 2018 | [Kända fel och lösta problem](../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541) | <ul><li>Ett känt problem med att söka efter strängar som innehåller specialtecken har lagts till när målgrupper med geomål skapades.</li><li>Flyttad kl. 1.6.0 omdirigeringsproblem till tabellen Lösta problem.</li><li>Ett problem har flyttats till tabellen Lösta problem med aktiviteter i standardarbetsytan som tagits bort via API som fortsätter att visas i målgränssnittet</li></ul> |
| 24 oktober 2018 | [Inställningar](../administrating-target/r-target-account-preferences/target-account-preferences.md#reference_0CF97B1C2214412ABBC8222EA8A36D7E) | Lagt till information som ska beaktas när du väljer rapportkälla för aktiviteter i Inställningar > Inställningar eller per aktivitet. |
|  | [Skapa en automatiserad personaliseringsaktivitet](../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) | Lagt till information om filtrering för ej tilldelade erbjudanden. |
|  | [Skapa upplevelse](../c-activities/t-experience-target/t-xt-create/xt-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) | Lagt till information om att duplicera upplevelser i XT-aktiviteter. |
|  | [Lägg till upplevelse](../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) | Lagt till information om att duplicera upplevelser i A/B-tester. |
|  | [Om målgrupper](../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271) | Lagt till information om hanteringen av målgrupper som refereras i målaktiviteter som har tagits bort i Adobe Audience Manager (AAM). |
|  | [at.js-integreringar](../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) | Uppdaterat ämne. |
|  | [Implementera mål utan tagghanterare](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#topic_397FFA3D6918456BBE02A9FBE9537894) | Uppdaterade alla avsnitt.  Nytt avsnitt har lagts till: at.js-implementering. |
|  | Versionsinformation [om version 18.10.1](../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 18.9.1 (26 september 2018) {#section_F7E74227BB9D467E9ABC0797EDC2FE0D}

<table id="table_0348AA29207D48A4BDFFA187F4F845B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datum </th> 
   <th colname="col2" class="entry"> Ämne </th> 
   <th colname="col3" class="entry"> Ändringar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 24 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända problem och lösta problem </a> </p> </td> 
   <td colname="col3"> <p>Ett känt fel har lagts till om borttagna aktiviteter via API i standardarbetsytan som finns kvar i målgränssnittet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md#topic_AFFDC672A8A34D028B100EF6BE5D8129" format="dita" scope="local"> Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse </a> </p> </td> 
   <td colname="col3"> <p>En kommentar som förklarar att mindre avvikelser mellan manuella beräkningar med hjälp av de listade formlerna och de tal som visas i rapporten förväntas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 22 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md#concept_4D8107E193B64168A3C0B85B51612991" format="dita" scope="local"> Målcookie </a> </p> </td> 
   <td colname="col3"> <p>Viktig anteckning har lagts till högst upp i avsnittet som informerar klienter om att inte länka känslig information till mboxSession och mboxPC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 21 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A" format="dita" scope="local"> at.js Versionsinformation </a> </p> </td> 
   <td colname="col3"> <p>Ytterligare information om at.js version 1.6.2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md#topic_6BCC0D0984184379A2A2EA6FFC948899" format="dita" scope="local"> Sekretess och allmänna dataskyddsförordningen (GDPR) </a> </p> </td> 
   <td colname="col3"> <p>Avsnittet"Adobe Target och Adobe Launch Opt-In" har lagts till. </p> <p>Uppdaterade följande frågor och svar: </p> <p> 
     <ul id="ul_BBF57B0E30A541E1BD1BCADD21A3D0F7"> 
      <li id="li_020DE613F4F340D8B68186465883A60C"> <p>Hur hanterar Adobe Target samtyckeshantering? </p> </li> 
      <li id="li_515B157F27B04342BB5664FD8E258FE2"> <p>Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR-begäran om åtkomst och borttagning för Target? </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25" format="dita" scope="local"> Implementera mål med Adobe Launch </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterad länk till Adobe Target-tillägget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 18 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md#concept_216F959FF18143D6A3BA0BE937918580" format="dita" scope="local"> IP-adresser som används av rekommendationer för feberbearbetningsservrar </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterat IP-adressintervall som används av aktiviteter för målrekommendationer. </p> <p>Lagt till IP-adressintervall som används av API:er för målrekommendationer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 12 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40" format="dita" scope="local"> Aktivitets-QA </a> </p> </td> 
   <td colname="col3"> <p>Följande stycke har redigerats under <span class="wintitle"> överväganden</span>: </p> <p>Aktivitets-QA visar inte innehåll för arkiverade aktiviteter eller aktiviteter som ligger efter deras slutdatum. Om du inaktiverar en avslutad aktivitet måste du spara aktiviteten igen för att Activity QA ska fungera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 10 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../target-home.md#topic_74F655D8648E4586BCCFD789E60D13CE" format="dita" scope="local"> Produktdokumentation för Adobe Target </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterade dokumentationen för Adobe Target-produkten på följande språk: Tyska, spanska, franska, italienska, japanska och portugisiska (Brasilien). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 9 oktober 2019 </td> 
   <td colname="col2"> <p> <a href="../c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201" format="dita" scope="local"> Profilattribut </a> </p> </td> 
   <td colname="col3"> <p>Avsnittet Vanliga frågor om tillagda profilskript. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md#concept_216F959FF18143D6A3BA0BE937918580" format="dita" scope="local"> IP-adresser som används av rekommendationer för feberbearbetningsservrar </a> </p> </td> 
   <td colname="col3"> <p>Redigerad text som indikerar att <span class="wintitle"> Recommendations- </span> aktiviteter använder IP-adresser som finns i Oregon-datacentret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 8 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md#concept_216F959FF18143D6A3BA0BE937918580" format="dita" scope="local"> IP-adresser som används av rekommendationer för feberbearbetningsservrar </a> </p> </td> 
   <td colname="col3"> <p>Lagt till nytt IP-adressintervall för CIDR-notationen 192.243.242.0.0/24. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#concept_72A95F6466A04B409FCD5989A6B6A554" format="dita" scope="local"> Visa rapporter - A4T, vanliga frågor </a> </p> </td> 
   <td colname="col3"> <p>Reviderad hel sektion: "Ska jag använda besökare, aktivitetsintryck eller besök när jag tittar på rapporter?" Omformulerade metriska beskrivningar och en lista med överväganden lades till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE" format="dita" scope="local"> Skapa villkor </a> </p> </td> 
   <td colname="col3"> <p>Avsnittet"Förväntad bearbetningstid för villkor" har lagts till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03" format="dita" scope="local"> Verksamhet </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information om hur du inaktiverar Dagens tips. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="https://spark.adobe.com/page/Lo3Spm4oBOvwF/" format="https" scope="external"> Analys och mål: Best Practices for Analysis </a> </p> </td> 
   <td colname="col3"> <p>Kolla in den nya självstudiekursen Analytics for Target (A4t). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584" format="dita" scope="local"> Så här fungerar Adobe Target </a> </p> </td> 
   <td colname="col3"> <p>Hela ämnet har uppdaterats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72" format="dita" scope="local"> Skapa ett A/B-test </a> </p> <p> <a href="../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9" format="dita" scope="local"> Skapa en automatiserad personaliseringsaktivitet </a> </p> <p> <a href="../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765" format="dita" scope="local"> Skapa en upplevelseinriktad aktivitet </a> </p> <p> <a href="../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710" format="dita" scope="local"> Skapa ett multivariata test </a> </p> <p> <a href="../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB" format="dita" scope="local"> Inställningar för aktiviteten Rekommendationer </a> </p> <p> <a href="../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00" format="dita" scope="local"> Lägg till upplevelse </a> </p> <p> <a href="../c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB" format="dita" scope="local"> Ange mått </a> </p>
   </td> 
   <td colname="col3"> <p>Tabellen med tecken som inte tillåts i aktivitet, upplevelser eller metriska namn har uppdaterats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 oktober 2018 </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-products/collections.md#concept_671BEFFB997D4F1282665BF3CAC00AC5" format="dita" scope="local"> Samlingar </a> </p> </td> 
   <td colname="col3"> <p>Anteckning har lagts till efter steg 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-products/exclusions.md#task_E79DA82BA402415FB41232976EDEF1CA" format="dita" scope="local"> Undantag </a> </p> </td> 
   <td colname="col3"> <p>Anteckning har lagts till efter steg 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 27 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17" format="dita" scope="local"> Metoder för att hämta data till Target </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information om tillåtna tecken i frågeinställningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända fel och lösta problem </a> </p> </td> 
   <td colname="col3"> <p>Ett känt problem med rapportering på erbjudandenivå i AP-aktiviteter har flyttats till tabellen Lösta problem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 26 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81" format="dita" scope="local"> Alternativ för Visual Experience Composer </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information om <span class="wintitle"> alternativet </span> Infoga före. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <a href="../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9" format="dita" scope="local"> Skapa en automatiserad personaliseringsaktivitet </a> </td> 
   <td colname="col3"> <p>Lagt till information om rapportgruppslistan som gör att du kan filtrera erbjudanden efter rapporteringsgrupp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-activities/t-automated-personalization/managing-exclusions.md#topic_30B4E4F89C914EB2B20B038C0299ED2E" format="dita" scope="local"> Hantera undantag </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information om hur du använder flera erbjudanden från samma plats i en exkluderingsgrupp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../cmp-resources-and-contact-information.md#concept_11902FAC95C64479AABE020557A7EEE4" format="dita" scope="local"> Target Basics Webinar Series </a> </p> </td> 
   <td colname="col3"> <p>Länk till Best Practices i Reporting &amp; Value Socialization-sessionen har lagts till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-products/feeds.md#concept_1228B31E3D0B483B9DD42C5E2AE436E3" format="dita" scope="local"> Feeds </a> </p> </td> 
   <td colname="col3"> <p>Följande anmärkning har lagts till: </p> <p> <p>Viktigt:  Överförda feeds upphör att gälla efter 61 dagar. Detta innebär att rekommendationer inte längre returneras om en feed-fil inte har bearbetats under de senaste 60 dagarna. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända fel och lösta problem </a> </p> </td> 
   <td colname="col3"> <p>Ett känt problem med rapportering på erbjudandenivå har lagts till i AP-aktiviteter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/integrating-recs-email.md#reference_256B16C894864F24AF970E43DC174420" format="dita" scope="local"> Integrera rekommendationer med e-post </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterad anmärkning under Alternativ 1: Använd leverans-API." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0" format="dita" scope="local"> Rekommendationer </a> </p> </td> 
   <td colname="col3"> <p>Omordnade ämnen i hela avsnittet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Versionsinformation <a href="../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A" format="dita" scope="local"> för version 18.9.1 </a> </p> </td> 
   <td colname="col3"> <p>Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Target Standard/Premium 18.8.1 (21 augusti 2018) {#section_6A146EE91FFB49D1BA398B36817CD0A2}

<table id="table_F09AC99B587A4D6390B1F8AE54F5DC47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datum </th> 
   <th colname="col2" class="entry"> Ämne </th> 
   <th colname="col3" class="entry"> Ändringar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 21 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F" format="dita" scope="local"> Felsöka at.js Använda felsökningsfunktionen i Adobe Experience Cloud </a> </p> </td> 
   <td colname="col3"> <p>Ändrade hela temat och tillagda utbildningsvideor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 20 september 2018 </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A" format="dita" scope="local"> Versionsinformation för mål </a> </p> <p> <a href="../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A" format="dita" scope="local"> at.js Versionsinformation </a> </p> </td> 
   <td colname="col3"> <p>Ytterligare information om at.js 1.6.1-versionen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 19 september 2018 </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända fel och lösta problem </a> </p> </td> 
   <td colname="col3"> Ett problem med kodredigeraren har flyttats från tabellen Kända fel till tabellen Lösta problem. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 18 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-experiences/c-visual-experience-composer/c-vec-code-editor/experience-templates.md#concept_109BBD7EABC04DD39E6B7B1687786652" format="dita" scope="local"> Experience Templates </a> </p> </td> 
   <td colname="col3"> <p>Nytt ämne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../cmp-resources-and-contact-information.md#concept_11902FAC95C64479AABE020557A7EEE4" format="dita" scope="local"> Target Basics Webinar Series </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterade kommande datum för webbinarium. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 11 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-activities/c-activity-qa/use-qa-mode-with-server-side-delivery.md#concept_54698C5CE8934F68B20961CD83FD6202" format="dita" scope="local"> Använd aktivitets-QA med leverans på serversidan </a> </p> </td> 
   <td colname="col3"> <p>Nytt ämne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-target/c-audiences/c-target-rules/custom-parameters.md#concept_C4C6E00D7C5A4BE9B72D471DB2E3027B" format="dita" scope="local"> Egna parametrar </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information om att spara om anpassade målgrupper som skapats före version 18.5.1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända fel och lösta problem </a> </p> </td> 
   <td colname="col3"> <p>Ett känt fel har lagts till: Målaktivitetsavtryck och konverteringar räknas för närvarande felaktigt i Analysis Workspace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md#concept_41F88DE95D2943178BEC382736B5C038" format="dita" scope="local"> Vanliga frågor och svar om dataskyddsförordningen </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterat kodexempel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/recommendations-faq.md#concept_EF272DE4AC6C47B19026BFBE816F5DB8" format="dita" scope="local"> Rekommendationer - frågor och svar </a> </p> </td> 
   <td colname="col3"> <p>Ändrade den önskade hastighetsversionen till 1.7.0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 10 september 2018 </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A" format="dita" scope="local"> Versionsinformation för mål </a> </p> <p> <a href="../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451" format="dita" scope="local"> Krypteringsändringar för TLS (Transport Layer Security) </a> </p> </td> 
   <td colname="col3"> <p>Ändrade det datum då Adobe fasade ut stödet för TLS 1.0 från 12 september 2018 till februari 2019. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-reports/reports.md#concept_B5077F5503AA4C98901AA99EDCE6CDE6" format="dita" scope="local"> Rapporter </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information och länk för att planera A/B-tester. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/recommendations-faq.md#concept_EF272DE4AC6C47B19026BFBE816F5DB8" format="dita" scope="local"> Rekommendationer - frågor och svar </a> </p> </td> 
   <td colname="col3"> <p>Följande frågor och svar har lagts till: Vilken är den maximala storleken för en CSV-fil för en feed-överföring? </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E" format="dita" scope="local"> Besökarprofil </a> </p> </td> 
   <td colname="col3"> <p>Följande stycke har lagts till: </p> <p>En besökarprofil skapas i det lokala edge-minnet för varje mbox-anrop med den nya <span class="codeph"> mboxPC </span>. Efter 30 minuters inaktivitet sparas profilen i måldatabasen och är tillgänglig från andra kanter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90" format="dita" scope="local"> Aktivitets-URL </a> </p> </td> 
   <td colname="col3"> <p>Ändrad text och uppdaterad illustration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 7 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-recommendations-faq/recommendations-faq.md#concept_EF272DE4AC6C47B19026BFBE816F5DB8" format="dita" scope="local"> Rekommendationer - frågor och svar </a> </p> </td> 
   <td colname="col3"> <p>Nya frågor och svar: Varför kan jag inte spara min tidigare Rekommendationer-aktivitet efter att jag har definierat en ny målgrupp? </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 september 2018 </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Dataleverantörer </a> </p> </td> 
   <td colname="col3"> <p>Uppdaterat kodexempel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md#concept_41F88DE95D2943178BEC382736B5C038" format="dita" scope="local"> Vanliga frågor och svar om dataskyddsförordningen </a> </p> </td> 
   <td colname="col3"> <p>Mindre redigeringar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 30 augusti 2018 </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända fel och lösta problem </a> </p> </td> 
   <td colname="col3"> Följande kända fel har lagts till: <p> 
     <ul id="ul_7AF527E5989D468BBC9472EA1C7F376D"> 
      <li id="li_7F53C6F01E1E471FB546AF98F1FF7F1E"> <p>När du använder <span class="codeph"> at.js </span> version 1.6.0 sker omdirigeringar av Analytics for Target (A4T), men utan aktivitetskvalificering. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 28 augusti 2018 </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F" format="dita" scope="local"> Entitetsattribut </a> </p> </td> 
   <td colname="col3"> <p>Enhet-ID-raden har uppdaterats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-recommendations/c-algorithms/create-new-algorithm.md#concept_BC16005C7A1E4F1A87E33D16221F4A96" format="dita" scope="local"> Innehållsinställningar </a> </p> </td> 
   <td colname="col3"> <p>Tydligare information om <span class="wintitle"> alternativet </span> Rekommendera tidigare inköpta artiklar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 21 augusti 2018 </td> 
   <td colname="col2"> <p> <a href="../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767" format="dita" scope="local"> Insikter om personalisering - rapporter </a> </p> </td> 
   <td colname="col3"> <p>Nytt ämne. </p> <p> <p>Obs!  Den här funktionen kommer snart att vara tillgänglig. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5" format="dita" scope="local"> Ändringar </a> </p> </td> 
   <td colname="col3"> <p>Lagt till information om hur du dockar panelen Ändringar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81" format="dita" scope="local"> Alternativ för Visual Experience Composer </a> </p> </td> 
   <td colname="col3"> <p>Omorganiserat register för att ta hänsyn till nya grupperingar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../cmp-resources-and-contact-information.md#concept_11902FAC95C64479AABE020557A7EEE4" format="dita" scope="local"> Target Basics Webinar Series </a> </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_D5E4E05DFE7A4E45BF199395D7AC3CE1"> 
      <li id="li_7A4A621EC5C34E4AADD46AA294620D9C"> <p>Lagt till information om kommande webbinarier. </p> </li> 
      <li id="li_A77B214010EF45BEBD0E2CBB256AD67D"> <p>Länk har lagts till i inspelningen för det andra webbinariet: Steg för att lägga till automatisering och mer avancerade aktiviteter. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03" format="dita" scope="local"> Verksamhet </a> </p> </td> 
   <td colname="col3"> <p>Avsnittet"Tips och tricks" har lagts till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541" format="dita" scope="local"> Kända fel och lösta problem </a> </p> </td> 
   <td colname="col3"> <p>Upprepade problem med omdirigeringsaktiviteter i <span class="codeph"> at.js- </span> implementeringar kan göra att URL:en för förhandsgranskning hamnar i en loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> <a href="../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451" format="dita" scope="local"> Krypteringsändringar för TLS (Transport Layer Security) </a> </p> </td> 
   <td colname="col3"> <p>Borttagen det tidigare föreslagna datumet då TLS 1.0-stödet skulle fasas ut (12 september 2018). </p> <p>Det datum då TLS 1.0-stödet upphör kommer att tillkännages vid en senare tidpunkt. Men det är viktigt att du går igenom detaljerna och planerar ändringarna för en smidig övergång. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Versionsinformation <a href="../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A" format="dita" scope="local"> för version 18.8.1 </a> </p> </td> 
   <td colname="col3"> <p>Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. </p> </td> 
  </tr> 
 </tbody> 
</table>

