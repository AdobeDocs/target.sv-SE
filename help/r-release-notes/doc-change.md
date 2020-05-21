---
keywords: target documentation change log;documentation updates;new topics;edits;updates
description: På den här sidan visas viktiga ändringar i Adobe Target-dokumentationen, som har beställts i releaser.
title: Dokumentationen ändras i produktdokumentationen för Adobe Target.
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: da102687f5d73813e3670b166eb0e668b96c93b6
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---


# Dokumentationsändringar{#documentation-changes}

På den här sidan visas viktiga ändringar i [!DNL Adobe Target] produktdokumentationen.

## Adobe Target Standard/Premium 20.4.1 (6 maj 2020)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
| 21 maj | [Vitlista Målkantsnoder](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | Tillagd `mboxedge30.tt.omtrdc.net` i listan. |
| 20 maj | [Versionsinformation för mål (prerelease)](/help/r-release-notes/target-release-notes.md) | Lagt till information om den kommande versionen av Target Standard/Premium 20.6.1 (10 juni 2020). |
|  | [Värdar](/help/administrating-target/hosts.md) | Anteckning har lagts till i avsnittet&quot;Bästa praxis för säkerhet&quot;. |
| 14 maj | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | Lagt till information om ändringar i API v2 för profilbatchstatus. |
| 13 maj | [CNAME och Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Avsnittet&quot;Kända begränsningar&quot; har lagts till. |
| 11 maj | [Värdar](/help/administrating-target/hosts.md) | Lagt till information om hur du använder funktionen ubox med omdirigeringar och vitlistor. |
|  | [Arbeta med regissörer](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Lagt till information om hur du använder värdar för att undvika Open Redirect-sårbarheter. |
|  | [Integrera rekommendationer med e-post](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Lagt till information om hur du använder värdar för att undvika Open Redirect-sårbarheter. |
|  | [E-post: implementera mål](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Lagt till information om hur du använder värdar för att undvika Open Redirect-sårbarheter. |
| 7 maj | [Versionsinformation för mål (aktuell)](/help/r-release-notes/release-notes.md) | I och med den kommande utfasningen av mbox.js den 30 augusti 2020 var David Son, var Adobe Target Product Manager nyligen värd för en utvecklarchatt för att diskutera fördelarna med att migrera mbox.js till at.js. Det finns en länk där du kan titta på webbinariet de kommande 30 dagarna. |
|  | [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Uppdaterade avsnittet &quot;Överväganden&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Uppdaterad&quot;overrideMboxEdgeServer&quot;-rad under&quot;Settings&quot;. |
| 6 maj | [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Ytterligare information om ITP 2.3. |
|  | [Versionsinformation](/help/r-release-notes/release-notes.md): 20.4.1 | Den här versionen innehåller förbättringar och korrigeringar. Du kan läsa om dem och länka till dokumentationen från versionsinformationen. Den här versionen innehåller även många dokumentationsuppdateringar i hela hjälpen. |

## Adobe Target Standard/Premium 20.2.1 (19 februari 2020)

| Datum | Ämne | Ändringar |
| --- | --- | --- |
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
