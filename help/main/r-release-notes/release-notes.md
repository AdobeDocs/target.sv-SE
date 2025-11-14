---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar;aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e5bc137ed1f32b07569a4f1a31746da19fb164d3
workflow-type: tm+mt
source-wordcount: '1736'
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

## [!DNL Target Standard/Premium] 25.11.2 (14 november 2025)

**Beslutserbjudanden**

+++Se detaljer
* **Erbjud beslut med dolda eller ogiltiga väljare som inte kan redigeras i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där offertbeslut som är kopplade till dolda eller ogiltiga väljare inte kunde redigeras om inte elementet var synligt i Visual Experience Composer (VEC). Redigering stöds nu direkt från panelen, vilket återställer funktionaliteten i det äldre användargränssnittet och säkerställer att offertbesluten kan ändras oavsett om väljaren visas eller inte. (TGT-53899)

+++

**Rekommendationer**

+++Se detaljer
* **Sidan kraschade när du redigerade villkor i en aktivitet.** Löste ett problem i det uppdaterade användargränssnittet där redigeringsaktivitetsvillkoren gjorde att sidan kraschade med konsolfel relaterade till `useCrudActionsCtx`. Villkorsredigeraren läses nu in och fungerar korrekt, vilket säkerställer att aktiviteter kan redigeras utan avbrott. (TGT-53971)
* **[!UICONTROL Message]-kolumnen kunde ibland inte visa produktdata i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade [!UICONTROL Recommendations]-användargränssnittet där kolumnen [!UICONTROL Message] i [!UICONTROL Catalog Search] ibland inte kunde visa produktdata, trots att det fanns värden i feeden. Kolumnen visar nu konsekvent rätt meddelandevärden för alla produkter, vilket garanterar tillförlitlig synlighet utan manuell omkonfiguration av kolumner. (TGT-52777)
* Knappen **[!UICONTROL Download Recommendations Data]visas inte när aktiviteten har sparats i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där knappen [!UICONTROL Download Recommendations Data] inte visades för vissa sparade aktiviteter, inte ens efter att användaren sparat om. Knappen visas nu på ett enhetligt sätt i alla aktiviteter, vilket säkerställer att användarna kan exportera rekommendationsdata på ett tillförlitligt sätt utan att behöva vidta tillfälliga åtgärder. (TGT-53802)
* **När vissa produkter öppnades från en samling returnerades &quot;Begärd resurs hittades inte&quot; och modal saknade ett stängningsalternativ.** Löste ett problem i det uppdaterade gränssnittet för rekommendationer där öppnandet av vissa produkter från en samling utlöste felet &quot;Begärd resurs hittades inte&quot; och visade ett tomt modalt fel utan ett stängningsalternativ. modal läser nu in produktinformation korrekt och ett stängningsalternativ är alltid tillgängligt för att avsluta på ett bra sätt. (TGT-53986)

+++

## [!DNL Target Standard/Premium] 25.11.1 (10 november 2025)


**Analyser för mål (A4T)**

+++Se detaljer
* **[!UICONTROL Goals & Settings]felmeddelande när [!DNL Adobe Analytics] används som rapportkälla i uppdaterat gränssnitt.** Löste ett problem i det uppdaterade [!UICONTROL Overview]-användargränssnittet där målavsnittet visade felmeddelandet &quot;Något gick fel. Vi kan inte slutföra din begäran. Kontakta [!DNL Adobe Client Care] om problemet kvarstår när [!DNL Adobe Analytics] (A4T) valdes som rapportkälla. Målen visas nu korrekt med [!UICONTROL Adobe Analytics]-mätvärden, vilket ger en konsekvent synlighet mellan olika rapportkällor. (TGT-54021)

+++

**Publiker**

+++Se detaljer
* **Det går inte att välja flera rapportmålgrupper i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där användare inte kunde välja flera nyligen skapade rapportmålgrupper samtidigt när en aktivitet redigerades. Flera målgrupper kan nu tilldelas samtidigt, vilket ger större flexibilitet och ökad effektivitet vid rapportkonfigurationen. (TGT-53253)

+++

**Beslutserbjudanden**

+++Se detaljer
* **Det går inte att redigera eller ersätta beslutserbjudanden i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där beslutserbjudanden inte kunde redigeras eller ersättas via panelen [!UICONTROL Modifications] och erbjudandenamnen visade sig vara tomma. Beslutserbjudandena är nu fullt tillgängliga och redigerbara, vilket återställer pariteten med det gamla användargränssnittet och säkerställer att kunderna kan hantera erbjudanden direkt inifrån aktiviteterna. (TGT-53884)

+++

**Lokalisering**

+++Se detaljer
* **Flera lokaliseringsfel i det koreanska och japanska användargränssnittet har korrigerats.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007 och TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++Se detaljer
* **Det gick inte att läsa in rekommendationsnyckeln efter att aktiviteten sparats. Det gick inte att matcha attribut med entitetsattribut.** Korrigerade ett problem där kampanjer av typen [!UICONTROL Promotion by Attribute] med regeltypen [!UICONTROL Entity Attribute Matching] inte läste in rekommendationsnyckeln när de redigerades efter att en aktivitet sparats. Problemet uppstod eftersom `customKeyId` inte begärdes via GraphQL. Rekommendationsnycklar läses nu in korrekt under kampanjredigeringar. (TGT-53117)
* **Rekommendationen kvarstår visuellt när du byter från ExpB till ExpA.** Löste ett problem där en rekommendation infogades i Experience B och sedan växlade till Experience A, så att rutan med rekommendationserbjudanden blev synlig. Det här var bara en visuell inkonsekvens. Ändringarna återges nu korrekt när du växlar mellan upplevelser, vilket säkerställer korrekt gränssnittsbeteende. (TGT-53911)
* **Rekommendationsnyckeln läses inte in för [!UICONTROL Promotion by Attribute] med [!UICONTROL Entity Attribute] matchning.** Löste ett problem där kampanjer av typen [!UICONTROL Promotion by Attribute] med regeltypen [!UICONTROL Entity Attribute Matching] inte läste in rekommendationsnyckeln när de redigerades efter att en aktivitet sparats. Rekommendationsnyckeln hämtas nu korrekt via GraphQL, vilket säkerställer att kampanjerna visas och fungerar som förväntat. (TGT-53917)
* **Redigering av rekommendationer för dolda HTML-element fungerar inte i det uppdaterade användargränssnittet.** Löste ett problem i användargränssnittet för [!UICONTROL New Create] och VEC där rekommendationsaktiviteter som tillämpades på dolda HTML-element inte kunde redigeras. Funktionen fungerar nu som förväntat, vilket återställer paritet med det gamla användargränssnittet och säkerställer att rekommendationerna kan ändras oavsett elementens synlighet. (TGT-53953)
* **Det går inte att redigera rekommendationsaktiviteter för dolda HTML-element i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där rekommendationsaktiviteter som tillämpats på dolda HTML-element inte kunde redigeras. Funktionen fungerar nu som förväntat, vilket återställer paritet med det gamla användargränssnittet och säkerställer att rekommendationerna kan ändras oavsett elementens synlighet. (TGT-53951)
* **Rekommendationskatalogen saknar ibland attributvärden i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade [!UICONTROL Recommendations]-användargränssnittet där katalogsökningslistor ibland inte kunde visa vissa attributvärden (t.ex. meddelande) även när de fanns i produktflödet. Attributvärden läses nu in konsekvent i sökresultat utan att någon kolumnomkonfiguration krävs, vilket förbättrar tillförlitligheten och effektiviteten i kataloghanteringen. (TGT-52769)
* Knappen **[!UICONTROL Download Recommendations]saknas för [!DNL Recommendations]-aktiviteter i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade [!DNL Recommendations]-gränssnittet där knappen [!UICONTROL Download Recommendations] inte var synlig för A/B-aktiviteter med rekommendationer. Knappen visas nu korrekt så att användarna kan exportera rekommendationsdata som förväntat, vilket överensstämmer med funktionen i det äldre användargränssnittet. (TGT-53768)
* Knappen **[!UICONTROL Download Recommendation Data]saknas i det uppdaterade översiktsgränssnittet.** Löste ett problem i det uppdaterade [!UICONTROL Overview]-gränssnittet där knappen [!UICONTROL Download Recommendation Data] inte var synlig för aktiviteter som innehåller rekommendationer. Knappen visas nu korrekt, så att användarna kan exportera rekommendationer direkt utan att behöva växla tillbaka till det gamla användargränssnittet. (TGT-53772)
* **Redigering av aktivitetsvillkor har ibland resulterat i en tom skärm i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där klickning på [!UICONTROL Edit Criteria in Experiences] ibland ledde till en tom skärm för vissa aktiviteter. Villkorsredigeraren läses nu in tillförlitligt i alla aktiviteter, vilket säkerställer att användarna kan redigera utan avbrott. (TGT-53961)
* **Det går inte att redigera sekvensvillkor i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där [!UICONTROL Sequence Criteria] försökte redigera fick popup-fönstret för kriterier att fastna vid inläsning och sedan visas en tom skärm. Villkorsredigeraren läses nu in korrekt, vilket gör att användare kan redigera och uppdatera sekvensvillkor utan avbrott. (TGT-53985)

+++

**[!UICONTROL Reports]**

+++Se detaljer
* **[!UICONTROL Multivariate Test] (MVT) platser och diagramrapporteringsproblem förhindrade rapportgenerering.** Löste ett problem där MVT-aktiviteter inte kunde generera [!UICONTROL Location Contribution]- och Graph-rapporter i målgränssnittet. Felet&quot;Något gick fel. Vi kan inte slutföra din begäran.&quot; Rapporterna läses nu in korrekt i användargränssnittet, vilket ger fullständig synlighet. (TGT-53654)
* **MVT-rapporter läses inte in på grund av ett [!UICONTROL Element]-rapportfel.** Korrigerade ett fel där MVT-aktivitetsrapporter inte kunde läsas in i målgränssnittet. Felmeddelandet&quot;Elementbidragsrapporten kunde inte hämtas.&quot; Rapporterna visas nu korrekt och ger full insyn i elementens bidrag. (TGT-53691)
* **Exportera beställningsinformation till CSV-utgåva för [!UICONTROL Experience Targeting] (XT)-aktiviteter.** Korrigerade ett problem där alternativet [!UICONTROL Export Order Details to CSV] felaktigt visades för XT-aktiviteter och returnerade en tom fil. Alternativet visas nu endast för AP-aktiviteter, vilket ger korrekt exportfunktion och förhindrar förvirring. (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Se detaljer
* **[!UICONTROL Delete Modification]-knappproblem förhindrade borttagning av aktivitetsändringar.** Löste ett problem där knappen [!UICONTROL Delete Modification] i användargränssnittet i [!DNL Target] inte fungerade, vilket hindrade användare från att ta bort ändringar i aktiviteter. Knappen fungerar nu som förväntat, så att ändringarna kan tas bort utan dröjsmål. (TGT-53728)
* **Standardväljare känns inte igen i det uppdaterade användargränssnittet.** Löste ett problem i det uppdaterade användargränssnittet där önskade väljare, till exempel `data-target-component-id`, inte fanns med i CSS-väljarlistan i VEC. Användarna kan nu välja önskade attribut på ett tillförlitligt sätt i stället för dynamiskt genererade klassnamn, vilket ger en stabil målinriktning över SPA-siduppdateringarna. (TGT-53908)
* **Justeringen av aktivitetsplatsen matchar inte mellan [!UICONTROL Edit] och [!UICONTROL Overview] sidor.** Löste ett problem där aktivitetsplatsnumreringen på sidan [!UICONTROL Overview] inte stämde överens med uppdateringar gjorda på sidan [!UICONTROL &#x200B; Edit Experience]. Platserna är nu konsekventa i båda vyerna, vilket ger korrekt justering och förhindrar att positioner saknas eller är felnumrerade. (TGT-53960 &amp; TGT-53954)
* **Det går inte att växla tillbaka till [!UICONTROL Design]-läget i den uppdaterade VEC:n.** Löste ett problem i det uppdaterade VEC-gränssnittet där användare inte kunde växla tillbaka till [!UICONTROL Design] efter att ha navigerat till en ny sida i [!UICONTROL Browse]-läget. Växlingsknappen [!UICONTROL Design] fungerar nu korrekt så att ändringar kan tillämpas sömlöst på flera sidor. (TGT-53988 &amp; TGT-53993)
* **Frågeparametern visas inte i aktivitetsöversikt.** Löste ett problem i det uppdaterade användargränssnittet där frågeparametrar inte visades på [!UICONTROL Overview]-sidan för aktiviteter, vilket orsakade avvikelser mellan [!UICONTROL Overview] och URL:er för sidleverans. Frågeparametrar visas nu korrekt och säkerställer att aktivitetsplatserna är helt representerade och konsekventa över olika vyer. (TGT-53701)

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
