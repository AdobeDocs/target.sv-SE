---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d73870275c266055825c2fce90489ef82825fca
workflow-type: tm+mt
source-wordcount: '1700'
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

## [!DNL Target Standard/Premium] 25.10.1 (22 oktober 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**Aktiviteter**

+++ Se detaljer
* **Ett användbarhetsproblem i det uppdaterade användargränssnittet** har åtgärdats. [!UICONTROL Observers] kan nu förhandsgranska aktiviteter med alternativet [!UICONTROL View Activity], precis som i det gamla användargränssnittet. (TGT-51741)
* **[!UICONTROL Observer]användare kan nu visa aktivitetsinnehåll i det uppdaterade användargränssnittet.** återställde synlighet för observatörsrollanvändare i det uppdaterade aktivitetsgränssnittet. Tidigare kunde observatörerna inte visa ändringar, erbjudanden och innehållsändringar - funktioner som fanns i det gamla användargränssnittet. (TGT-53785)
* **[!UICONTROL Approver]användare kan nu redigera aktivitetsmål utan redigeringsbehörighetsfel.** Löste ett behörighetsproblem i gränssnittet för att skapa aktivitet som hindrade användare på godkännarnivå från att spara ändringar i avancerade målinställningar. Berörda användare fick ett `403 Forbidden.Resource`-fel som krävde redigeringsbehörighet, trots att de har tillräcklig åtkomst. (TGT-53819)

+++

**Publiker**

+++Se detaljer
* **Markering av flera målgrupper har återställts i rapporten&quot;Endast den här aktiviteten&quot;.** Löste ett problem i gränssnittet för att skapa aktivitet som hindrade användare från att välja flera målgrupper under avsnittet [!UICONTROL This activity only] i [!UICONTROL Goals & Settings]. (TGT-53283)
* **Målgruppsbaserade rapportdiagram visar nu konverteringsdata korrekt.** Löste ett problem på fliken [!UICONTROL Reports] som orsakade att diagram inte fungerade när du valde målgrupper som inte var standard. Data och konfidensmått fanns tillgängliga, men det visuella diagrammet visade bara en solid linje, vilket försvårar analysen. (TGT-53769)
* **Gränssnittet [!UICONTROL Targeting] visar nu tydligt uteslutna målgruppsregler.** Löste ett problem i avsnittet [!UICONTROL Targeting] i användargränssnittet för att skapa aktivitet där målgruppsreglerna som är inställda på [!UICONTROL Exclude] inte visades tydligt. Detta ledde till förvirring när målgruppslogik granskades, särskilt för målgrupper som inte inkluderar specifika URL:er. (TGT-53809)
* **Målgruppsdefinitionsvärden kan nu markeras och kopieras på fliken [!UICONTROL Targeting].** Löste ett problem i gränssnittet Activity Create som hindrade användare från att markera och kopiera målgruppsregelvärden på fliken [!UICONTROL Targeting]. Den här funktionen var tillgänglig i det gamla användargränssnittet men saknas i det uppdaterade användargränssnittet. (TGT-53856)

+++

**Lokalisering**

+++Se detaljer
* **Felmatchningen av &quot;quote&quot; i sidredigerarkontexten zh_CN har korrigerats.** Korrigerade ett kontextuellt översättningsfel i zh_CN-språket där termen &quot;citat&quot; felaktigt översattes som &quot;报 价&quot;, vilket innebär en kommersiell prisoffert. I avsnittet Typografi > Rubrikformat > Blockcitat hänvisar den avsedda betydelsen till ett formateringselement - citattecken - inte priser. (TGT-53841)
* **Felmatchningen av &quot;quote removed&quot; i sidredigerarkontexten zh_CN har korrigerats.** Korrigerade ett översättningsfel i zh_CN-språket där &quot;citattecknet borttaget&quot; felaktigt återgavs som &quot;移 除 报 价&quot;, vilket innebär en kommersiell prisoffert. I avsnittet Typografi > Rubrikformat > Blockcitat hänvisar termen till ett formateringselement - citattecken - inte priser. (TGT-53843)
* **Felmatchningen av&quot;omarrangerat citattecken&quot; i sidredigerarkontexten zh_CN har korrigerats.** Korrigerade ett kontextuellt översättningsfel i zh_CN-språket där&quot;citattecknet omordnades&quot; felaktigt översattes som&quot;重 新 排 列 了 价&quot;, vilket innebär en kommersiell prisoffert. I avsnittet Typografi > Rubrikformat > Blockcitat hänvisar termen till ett formateringselement - citattecken - inte priser. (TGT-53844)
* **Felmatchningen av &quot;quote changed&quot; i sidredigerarkontexten zh_CN har korrigerats.** Korrigerade ett översättningsfel i zh_CN-språket där &quot;offerten har ändrats&quot; felaktigt återgavs som &quot;更 改 报 价&quot;, vilket tyder på en kommersiell prisoffert. I avsnittet Typografi > Rubrikformat > Blockcitat hänvisar termen till ett formateringselement - citattecken - inte priser. (TGT-53845)

+++

**Rekommendationer**

+++Se detaljer
* **CSS-väljarändringar för rekommendationer sparas nu korrekt.** Löste ett problem i gränssnittet för att skapa aktivitet som hindrade användare från att uppdatera CSS-väljaren för rekommendationsplaceringar. Ändringarna återställs efter att de sparats och uppdateringarna till behållarna för målanpassning blockeras. (TGT-53835)
* **Val av sidinläsningshändelse kvarstår nu i rekommendationsändringar.** Löste ett problem i gränssnittet för att skapa aktivitet som hindrade användare från att spara ändringar när en rekommendations händelsetyp ändrades från [!UICONTROL View] till [!UICONTROL Page Load]. Även om markeringen verkar vara slutförd återställs den efter att ha navigerat bort och blockerat aktivitetspublikationen. (TGT-53957)

+++

**Rapporter**

+++Se detaljer
* **[!UICONTROL Export order details to CSV] hämtar nu fullständiga data.** Löste ett problem i det uppdaterade [!UICONTROL Overview]-gränssnittet som orsakade att alternativet [!UICONTROL Export Order details to CSV] laddade ned tomma filer, även när det fanns giltiga rapportdata. (TGT-53787)

+++

**Säkerhet**

+++Se detaljer
* **IMS-förfiltret har lagts till för att skydda GQL-slutpunkter från dataexponering över grupper.** Löste ett säkerhetsproblem på fliken Admin som påverkar GraphQL-slutpunkterna licenseGroups och targetProperties. Problemet uppstod när JIL API användes med en Admin Client-token som skulle kunna utnyttjas för att få åtkomst till produktdata för flera organisationer. (TGT-53837)

+++

**Visual Experience Composer (VEC)**

+++Se detaljer
* **Redigeringsstabiliteten har återställts i gränssnittet för att skapa aktivitet.** Löste ett tillfälligt fel i VEC-gränssnittet som gjorde att redigering misslyckades och länkarna blev oväntat klickbara, vilket dirigerar om användare från sidan. (TGT-53153)
* **Redigering återställd för sparade aktiviteter i gränssnittet Skapa aktivitet.** Löste ett problem som hindrade användare från att redigera aktiviteter efter att ha sparat ändringarna. Aktiviteter som påverkas har fastnat i [!UICONTROL Applying initial modifications], vilket blockerar ytterligare uppdateringar och döljer knappen [!UICONTROL Cancel]. (TGT-53631)
* **VEC slutar inte längre att fungera på [!UICONTROL Applying initial modifications].** Löste ett prestandaproblem i VEC som orsakade långa fördröjningar vid inläsning av upplevelser med ett stort antal ändringar. De berörda användarna såg gränssnittet som fastnat på [!UICONTROL Applying initial modifications] i flera minuter, särskilt i Experience B-scenarier. (TGT-53727)
* **VEC läser nu in ändringar utan rotelement.**
Löste ett problem i VEC som gjorde att upplevelserna stacks när ändringar som saknade ett tydligt rotelement lästes in. Dessa ändringar gjorde att användargränssnittet hängde oändligt på &quot;A[!UICONTROL pplying initial modifications]&quot;. (TGT-53799)
* **Att spara ändringar i aktiviteter fungerar nu som förväntat.** Löste ett behörighetsrelaterat problem i det nya användargränssnittet som hindrade användare från att spara ändringar när de redigerade mål och avancerade inställningar i aktiviteter. De berörda användarna såg ett rött felband och ett&quot;Forbidden.Resource&quot;-meddelande, trots att de hade lämplig åtkomst. (TGT-53816)
* **VEC-gränssnittet bevarar nu upplevelseändringar i olika vyer.** Löste flera problem i den uppdaterade VEC som påverkade upplevelseutvecklingen. Ändringarna blev inte korrekta, särskilt när du använde HTML-erbjudanden eller växlade mellan vyer. (TGT-53825)
* **Alla vyer visas nu korrekt när en ändring sträcker sig över flera upplevelser.** Löste ett problem i gränssnittet för att skapa aktivitet där endast en vy visades när en ändring tillämpades på flera vyer. Verktygstipset för hovring kunde inte visa alla associerade vyer, även om ändringen tillämpades korrekt. (TGT-53827)
* **VEC:n stoppas inte längre regelbundet på [!UICONTROL Applying initial modifications].** Löste ett intermittent problem i VEC där upplevelserna inte kunde läsas in och fastnade på [!UICONTROL Applying initial modifications]. Detta beteende var inkonsekvent och utlöste ibland omdirigeringsslingor eller krävde manuell cacherensning. (TGT-53916)
* **VEC-inläsningsproblemet kunde inte reproduceras.** Ett rapporterat problem har utretts där VEC fastnade på [!UICONTROL Applying initial modifications] när befintliga aktiviteter redigerades. Beteendet misstänktes vara relaterat till HTML-innehåll som saknar ett överordnat element. Vi kommer att fortsätta övervaka för upprepning och rekommenderar att du använder strukturerade behållare för HTML för att säkerställa stabilitet. (TGT-53972)
* **[!UICONTROL Design]-läget i VEC fungerar inte längre som [!UICONTROL Browse]-läge ibland.** Löste ett problem i användargränssnittet där [!UICONTROL Design]-läget ibland betedde sig som [!UICONTROL Browse] , vilket tillåter klickbara `<a>`-länkar och förhindrar att element markeras. Detta gjorde att hovringsrutan stängdes och att ändringsarbetsflöden blockerades. (TGT-53136)
* **Knappklick i [!UICONTROL Composer]-läge utlöser inte längre sidomdirigering.** Löste ett problem i det uppdaterade VEC-gränssnittet där klickning på en knapp i [!UICONTROL Composer]-läge orsakade en oväntad omdirigering till knappens mål-URL. Detta hindrade användare från att redigera call-to-action-element (CTA) och störde redigeringsarbetsflödet. (TGT-53137)
* **Erbjud koduppdateringar i automatiserade personaliseringsaktiviteter och spara nu utan fel.** Löste ett problem i det nya användargränssnittet som orsakade felet [!UICONTROL Invalid user input] vid uppdatering av erbjudandekod i [!UICONTROL Automated Personalization]-aktiviteter. Felet hindrade användare från att spara ändringar, även när indata var giltiga. (TGT-53586)
* **[!UICONTROL Design]-läget i VEC blockerar nu länknavigering för redigerbara komponenter.** Löste ett problem i den uppdaterade VEC där klickbara element - som knappar och länkar - utlöste en sidomdirigering även i [!UICONTROL Design] -läge. Det här beteendet simulerade läget [!UICONTROL Browse] och hindrade användare från att ändra nyckelkomponenter. (TGT-53696)
* Måttet **[!UICONTROL Clicked an element] fungerar nu utan omdirigering eller fel.** Löste ett problem i det nya användargränssnittet som orsakade oväntade omdirigeringar och tomma skärmar när konverteringsmåttet [!UICONTROL Clicked an element] valdes. Om du klickar på en knapp under installationen utlöstes navigeringen i stället för att elementet registrerades, vilket resulterade i ett [!UICONTROL element not found]-fel. (TGT-53817)
* **Befintliga aktiviteter fastnar inte längre i en oändlig inläsningsloop under redigering.** Löste ett problem i det nya användargränssnittet där redigering av en befintlig aktivitet i VEC gjorde att sidan fastnade i en oändlig inläsningsloop. Problemet påverkade inte nyskapade aktiviteter och utlöstes av tidigare ändringar på sidan. (TGT-53913)
* **Befintliga aktivitetssidor med ändringar läses nu in korrekt i VEC.** Löste ett fel i den uppdaterade VEC som gjorde att sidor fastnade i inläsningsfasen när en befintlig aktivitet redigerades med sparade ändringar. Nya aktiviteter lästes in utan problem, men tidigare konfigurerade aktiviteter kunde inte återges. (TGT-53967)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=sv-SE) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv-SE){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
