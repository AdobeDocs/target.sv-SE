---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6b92e823c854996e074716a7b8c4856176710c24
workflow-type: tm+mt
source-wordcount: '1772'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Utforska de senaste funktionerna, förbättringarna och korrigeringarna i [!DNL Adobe Target]. Versionsinformationen omfattar även uppdateringar av [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformskomponenter när det är tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Tidskänsliga uppdateringar som du behöver känna till {#time-sensitive}

[!BADGE Viktigt]{type=Informative}

För tidskänsliga uppdateringar relaterade till [!DNL Adobe Target] och din implementering, ger [!DNL Adobe] detaljerade versionsinformation och dokumentation via [!UICONTROL Experience League]. Här är några viktiga punkter som är relevanta för implementeringen:

### [!DNL Target]-gränssnittsversion växlar borttagning

Mer information finns i [[!DNL Target] Vanliga frågor om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.1.1 (18 januari 2026)

**Aktiviteter**

+++Se detaljer

* **Det går inte att kopiera aktivitet - ogiltiga användarindata.** Problemet som får användarna att se ett felmeddelande om ogiltig användarinmatning när en aktivitet kopieras har åtgärdats. Tidigare, när en aktivitet duplicerades, sparades inte aktivitetens arbetsytespecifika egenskapstilldelningar, vilket gjorde att serverdelen avvisade begäran om att spara eftersom ABActivity kräver minst en egenskap som tillhör en arbetsyta som inte är standard. Denna felmatchning utlöste ett allmänt fel i användargränssnittet, vilket gjorde att användarna inte fick någon vägledning. Korrigeringen ser till att arbetsytetilldelningar behålls korrekt under kopieringsåtgärder, så att användare kan spara den kopierade aktiviteten utan att ändra den och förhindra missvisande valideringsfel. (TGT-54282)
* **Aktivera arbetsytekolumn i erbjudandet om webbredigerare.** Den här uppdateringen åtgärdar förvirring hos kunderna som orsakas av erbjudanden från [!UICONTROL Default Workspace] som visas i andra arbetsytor i Web Editor. Även om det här beteendet fungerar som avsett är [!UICONTROL Default Workspace] erbjudanden avsiktligt synliga i alla arbetsytor, rapporterade kunderna att gränssnittet inte har gjort arbetsytans ursprung tydligt, särskilt när aktiviteter skapas i en icke-standardarbetsyta som &quot;Godkännare&quot;. För att förbättra tydligheten har kolumnen [!UICONTROL Workspace] nu aktiverats i webbredigerarens erbjudandelista, vilket gör att användarna enkelt kan skilja på vilken arbetsyta varje erbjudande tillhör och förhindra feltolkning av de ytterligare erbjudanden som visas. (TGT-54138)
* **Länkar med target=&quot;_blank&quot; öppnas på en ny flik.** Den här korrigeringen åtgärdar ett problem där skapade webbplatser som innehåller länkar med ~ target=&quot;_blank&quot;~ skulle öppnas på en ny webbläsarflik när de klickas i [!UICONTROL Browse] -läge, vilket stör förhandsgranskningen i redigeraren. Beteendet inträffade eftersom den redigerade sidans inbyggda länkattribut inte fångades upp av tilläggets inmatade JavaScript, till skillnad från det tidigare användargränssnittet där ankarelement omformades och deras mål åsidosattes för att behålla navigeringen i redigeraren. Uppdateringen ser till att länkar som använder ~target=&quot;_blank&quot;~ nu hanteras korrekt i Web Editor så att de inte längre kan öppna externa flikar under redigeringen. (TGT-54134)
* **Avmarkera egenskapsvarning.** Den här uppdateringen innehåller en visuell varning som tydligt informerar användare när de avmarkerar en egenskap som identifieras automatiskt i aktivitetsredigeraren. Tidigare fanns det ingen indikation på att egenskapen skulle tas bort permanent om du tog bort en egenskap som upptäcktes automatiskt, vilket skulle leda till att målinriktningskonfigurationen gick förlorad. Korrigeringen lägger till en varningsikon, som överensstämmer med beteendet i det äldre användargränssnittet, för att meddela användare att egenskapen tas bort från aktiviteten när de avmarkerar den. (TGT-54121)
* Listrutan **[!UICONTROL Workspaces]är begränsad till 20 i avsnittet [!UICONTROL Users].** Den här korrigeringen åtgärdar ett problem där listrutan [!UICONTROL Workspaces] i avsnittet [!UICONTROL Administration] > [!UICONTROL Users] endast visade 20 arbetsytor, även när en användare har tillgång till många fler. Det underliggande GraphQL-anropet för `licenseGroups` var även begränsat till 20 resultat, vilket gör att användargränssnittet visar en ofullständig lista trots att användaren har tillgång till fler arbetsytor i organisationen. Uppdateringen tar bort den här hårda gränsen så att hela uppsättningen tillgängliga arbetsytor nu returneras och visas korrekt. (TGT-53820)
* **Ett problem har korrigerats där erbjudandemodala inte visade arbetsytans kolumn.** Korrigerade ett fel där erbjudandemodala inte visade arbetsytans kolumn i det uppdaterade användargränssnittet. Detta orsakade förvirring för kunderna eftersom erbjudanden från [!UICONTROL Default Workspace] visades tillsammans med erbjudanden från den valda arbetsytan utan någon indikation på deras ursprung. Arbetsytans kolumn är nu aktiverad så att kunderna tydligt kan se vilken arbetsyta varje erbjudande tillhör. (TGT-52320)

+++

**Egenskaper**

+++Se detaljer
* **Aktivitetsredigering bör inte lägga till en egenskap som identifieras automatiskt om den redan har tagits bort.** Den här korrigeringen åtgärdar ett problem där redigering av en aktivitet automatiskt återinför en automatiskt identifierad egenskap som användaren tidigare har tagit bort. När en aktivitet för redigering öppnades igen återställdes den borttagna egenskapen felaktigt, vilket leder till inkonsekvent beteende och förvirring i [!UICONTROL Properties List]. Uppdateringen ser till att när en egenskap som identifieras automatiskt tas bort, tas den bort under alla efterföljande redigeringar och visas inte igen om inte användaren uttryckligen lägger till den igen. (TGT-54182)
* **Lägg inte till automatiskt identifierade egenskaper om de redan har tagits bort.** Den här korrigeringen ser till att när en användare tar bort en egenskap som identifieras automatiskt från en aktivitet, återinförs den inte längre i systemet vid efterföljande navigering i aktivitetsredigeraren. Om en användare tidigare avmarkerade en egenskap som identifieras automatiskt, flyttat till steget [!UICONTROL Targeting] och sedan återgått till [!UICONTROL Experiences] fylls den borttagna egenskapen i på nytt baserat på den automatiskt identifierade listan som lagras i statussegmentet i aktivitetsredigeraren. Den uppdaterade logiken jämför nu de automatiskt upptäckta egenskaperna med de aktuella egenskaperna i segmentet ~ActivityState~ och förhindrar att de automatiskt upptäckta egenskaperna som användaren redan har tagit bort läggs till igen. Detta resulterar i ett konsekvent beteende i alla steg och tar hänsyn till användaravsikten. (TGT-54181)
* **Lägg till text som identifieras automatiskt i egenskapslistan.** Den här förbättringen uppdaterar [!UICONTROL Properties List] så att alla egenskaper som identifieras automatiskt av systemet tydligt markeras. När en automatiskt identifierad egenskap också finns i den användarsynliga [!UICONTROL Properties List] visas nu texten&quot;(Auto-Detected)&quot; bredvid namnet, med det värde som lagrats i läget ~ ActivityEditorSlice~ . Detta speglar beteendet hos det gamla användargränssnittet och hjälper användarna att enkelt skilja mellan manuellt markerade egenskaper och de egenskaper som identifieras automatiskt. (TGT-54120)
* **Lägg till automatiskt identifierad [!UICONTROL Properties] i läget.** Den här uppdateringen ser till att läget ~ ActivityEditorSlice.ExperienceEditor~ konsekvent upprätthåller en uppdaterad lista över alla automatiskt identifierade egenskaps-ID:n som skickats från Web Editor till fliken Activity [!UICONTROL Experiences]. Varje gång användaren navigerar till fliken [!UICONTROL Experiences] uppdateras läget med alla nya identifierade egenskaper samtidigt som dubbletter förhindras, vilket ger korrekt spårning och tillförlitligt beteende i efterföljande steg. (TGT-54119)

+++

**Rekommendationer**

+++Se detaljer
* I listrutan **[!UICONTROL Environment]visas endast 100 resultat.** Den här korrigeringen åtgärdar en begränsning där kunder med fler än 100 miljöer bara kunde se de första 100 posterna i listrutan [!UICONTROL Environment] i [!UICONTROL Recommendations]. Den underliggande GraphQL-frågan (~getMiljömentsV2~) sidnumrerades med den hårdkodade sidstorleken 100, vilket gör att användargränssnittet bara visar en del av listan även om ytterligare sidor är tillgängliga. För kunder som har fler än 100 miljöer har det här problemet resulterat i saknade alternativ och en ofullständig urvalsupplevelse. Uppdateringen ökar gränsen så att alla miljöer returneras och visas, vilket ger fullständig synlighet oavsett antal miljöer. (TGT-53903)

+++

**Rapporter**

+++Se detaljer

* **Ett problem har korrigerats där [!UICONTROL Reports]-pilen inte tydligt visade expanderbara kolumner.** Korrigerade ett fel där rapporttabellen inte tydligt visade att ytterligare kolumner kunde expanderas i det uppdaterade användargränssnittet. Ett verktygstips som försvinner har lagts till i pilen [!UICONTROL Reports] nära kolumnrubrikerna för att hjälpa kunderna att förstå att fler kolumner är tillgängliga.

+++

**Vyer**

+++Se detaljer

* **Det går inte att ta bort ändringar som gjorts i vyer.** Den här korrigeringen åtgärdar ett problem där användare inte kunde ta bort ändringar i en aktivitet om inte ändringen först tillämpades på nytt i ytterligare vyer. När du redigerar en aktivitet (till exempel aktivitets-ID 302467) har försök att ta bort ändringar ingen effekt, vilket förhindrar användare från att ta bort oönskade ändringar. När en ändring har tillämpats igen med &quot;Använd för fler vyer&quot; och tilldelats till en `Page Load`-händelse fungerade borttagningen plötsligt som förväntat. (TGT-54088)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Se detaljer
* Namnet **[!UICONTROL Experience Fragment]trunkerades i det nya VEC-gränssnittet** (TGT-54312)
* **Det går inte att använda [!UICONTROL Advanced Settings] för [!UICONTROL Revenue]-mått.** Den här korrigeringen åtgärdar ett problem där användare stötte på ett 403-fel av typen &quot;Åtkomst nekad&quot; när [!UICONTROL Advanced Settings] konfigurerades för [!UICONTROL Revenue]-måttet i [!UICONTROL Goals & Settings]. Problemet uppstod när ett beroendevillkor som är kopplat till det primära målet lades till. I serverdelen krävdes inte redigeringsprivilegiet korrekt, även för användare som redan har tillräcklig behörighet för att skapa och redigera aktiviteter. Därför gick det inte att spara aktiviteten trots giltig konfiguration. Uppdateringen åtgärdar behörighetskontrollen så att användare med lämplig åtkomst kan lägga till metriska beroenden för intäkt utan att utlösa ett fel med förbjuden resurs. (TGT-54092)
* **Korrigerade ett fel där knappen Lägg till inte gällde för de valda bilderna.** Korrigerade ett problem som hindrade kunder från att lägga till vissa bilder när de valde eller uppdaterade en bild i processen för att skapa aktivitet. När kunderna sökte efter specifika resurser, till exempel bilder som returnerades när de sökte efter&quot;ipp&quot;, använde inte knappen [!UICONTROL Add] den valda bilden och ingen ändring skapades. Om du väljer andra bilder, till exempel `Homepage-banner-1-moz.jpg`, fortsätter det att fungera som förväntat. Uppdateringen ser till att alla giltiga bilder kan tillämpas på samma sätt i det uppdaterade användargränssnittet. (TGT-53610)
* **Ett problem har korrigerats där konfigurationen av målmåttet återställdes när ett URL-villkor togs bort.** Ett problem har korrigerats där ett enskilt URL-villkor i måttet [!UICONTROL Goal] orsakade att hela konfigurationen återställdes i det uppdaterade användargränssnittet. När kunder försökte ta bort ett sparat URL-villkor under [!UICONTROL Conversion] > [!UICONTROL Viewed a Page] växlades måltypen oväntat till [!UICONTROL Viewed an Mbox] och alla tidigare konfigurerade inställningar togs bort. Den här uppdateringen ser till att endast det valda URL-villkoret tas bort och att alla återstående målinställningar förblir intakta. (TGT-53271)
* **Ett problem där sökningen inte gick igenom undermapparna har korrigerats.** Ett problem där sökningen efter erbjudanden inte returnerade resultat från undermappar i det uppdaterade användargränssnittet har korrigerats. Kunderna kunde bara hitta ett erbjudande om de navigerade manuellt till den mapp där det sparades, vilket gör sökbeteendet inkonsekvent med API-funktionerna. Sökfunktionen har nu stöd för rekursiv sökning i mappar så att kunderna kan hitta erbjudanden utan att behöva öppna varje mapp separat. (TGT-51954)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
