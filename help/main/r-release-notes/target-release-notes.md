---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 95d8bd994ffdb1d256b7eb0aea1a2462b40ce530
workflow-type: tm+mt
source-wordcount: '2221'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 21 augusti 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Informationen i den här artikeln uppdateras ofta, särskilt före releaser.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.3 (21 augusti 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!UICONTROL Activities]**

+++Se detaljer
* **Ett problem har korrigerats där sparande aktiviteter utlöste ett ogiltigt användarindatafel på grund av felaktiga egenskapsdata**: Kunderna påträffade ett kritiskt fel när de försökte spara befintliga aktiviteter. Felmeddelandet indikerade ogiltiga användarindata, som specifikt refererar till ett okänt egenskapsnamninnehåll i JSON-nyttolasten. Nya aktiviteter som använder samma egenskap sparades, vilket tyder på att problemet isolerades till äldre aktivitetsdata. Processen för att skapa aktivitet hanterar nu äldre egenskapskonfigurationer korrekt, vilket förhindrar ogiltiga indatafel och säkerställer konsekvent sparfunktion för nya och befintliga aktiviteter. (TGT-53507)
* **Ett fel som gjorde att kunderna inte kunde spara en aktivitet på grund av felet InvalidProperty.Json** har korrigerats: Kunderna påträffade ett fel när de försökte spara en aktivitet i det uppdaterade användargränssnittet, även utan att göra några ändringar. Felmeddelandet visade en ogiltig JSON-struktur: &quot;Ogiltig Json. Okänt egenskapsnamn &#39;content&#39;. Plats: rad - 1, kolumn - 432.&quot; Problemet orsakades av en okänd egenskap i nyttolasten för begäran och har nu lösts. Kunder kan spara aktiviteter utan att det här felet uppstår. (TGT-53513)
* **Korrigerade ett fel där schemalagda aktiviteter felaktigt visade statusen [!UICONTROL Live] tills sidan uppdaterades**: Kunder observerade att när de schemalägger en aktivitet att publiceras vid ett framtida datum och en framtida tidpunkt visades statusen omedelbart som [!UICONTROL Live] i stället för [!UICONTROL Scheduled]. Detta orsakade förvirring även om bekräftelsemeddelandet korrekt indikerade att aktiviteten schemalagdes. Om du uppdaterar sidan har statusvisningen korrigerats. Problemet har nu lösts och schemalagda aktiviteter visar korrekt schemalagd status utan att en uppdatering krävs. (TGT-52937)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Se detaljer
* **Ett problem har korrigerats där kunder inte kunde skriva rapportsvitnamn under processen för att skapa aktivitet**: Kunder som använder [!DNL Adobe Analytics] som rapportkälla under processen för att skapa aktivitet kunde inte skriva i listrutan [!UICONTROL Report Suite] för att söka efter specifika rapportsviter. Detta påverkade arbetsflödena för organisationer med ett stort antal rapportsviter, där manuell bläddring försenade konfigurationen avsevärt. Listrutan sorterades inte i bokstavsordning och svarade inte konsekvent på inmatningar, vilket gjorde det svårt att hitta rapportsviter som &quot;Office + Store - Webb - Produkt&quot;. Problemet har åtgärdats och kunderna kan nu söka effektivt genom att skriva namnen på rapportsviterna. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Se detaljer
* **Korrigerade ett problem där målgrupper som gått ut med tidsram blockerade aktivitetssparande även efter borttagning**: Kunderna kunde inte spara aktiviteter i det uppdaterade användargränssnittet på grund av ett fel relaterat till utgångna målgrupper med tidsram. Felmeddelandet kvarstår även efter att den berörda publiken har tagits bort: &quot;Aktiviteten innehåller publik med ogiltig tidsram.&quot; Problemet uppstod eftersom systemet fortsatte att validera målgruppen med endast aktivitet, även när det inte längre användes. Beteendet komplicerades ytterligare av tidszonsavvikelser. Valideringslogiken har korrigerats och kunderna kan nu spara aktiviteter utan att detta fel uppstår. (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++Se detaljer
* **Korrigerade ett fel som förhindrade kunder från att infoga Experience Fragments med [!UICONTROL Insert Before] eller [!UICONTROL Insert After] i användargränssnittet**. Ett fel uppstod när kunder försökte infoga [!UICONTROL Experience Fragments] i en aktivitet med hjälp av alternativen Infoga före eller Infoga efter i det uppdaterade användargränssnittet. Felmeddelandet som visades var:&quot;Erbjudandeinnehåll måste innehålla exakt ett HTML-element.&quot; Problemet var specifikt för det uppdaterade användargränssnittet och uppstod inte i den tidigare versionen. Problemet har nu lösts och kunderna kan infoga [!UICONTROL Experience Fragments] utan att detta fel uppstår. (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++Se detaljer
* **Ett problem som hindrade kunder från att redigera beslutserbjudanden och välja specifika sidelement i det uppdaterade användargränssnittet** har korrigerats: I den uppdaterade processen för att skapa aktiviteter kunde kunderna inte redigera befintliga beslutserbjudanden eller välja specifika sidelement i Visual Experience Composer (VEC). Beslutserbjudandena visades felaktigt som erbjudanden från HTML och de ändringar som gjordes under redigeringen sparades inte. Dessutom gick det inte att läsa in vissa regionala URL:er, till exempel den japanska webbplatsen, korrekt i VEC, vilket blockerar skapande och uppdatering av aktiviteter. Besluten visas nu korrekt, sidelementen kan markeras som förväntat och regionala URL:er läses in korrekt i VEC, vilket återställer redigeringsfunktionerna. (TGT-53425)
* **Ett problem har korrigerats där [!UICONTROL Offer Decision] väljare inte kunde ändras och ändras oväntat efter att** sparats: I den uppdaterade processen för att skapa aktivitet kunde kunderna inte ändra [!UICONTROL Offer Decision]-väljaren som det var tänkt. Försöken att ändra väljaren misslyckades och väljaren återgick till ett felaktigt värde efter att den sparats. Detta beteende gjorde att beslutserbjudandet försvann från Visual Experience Composer (VEC), vilket blockerade ytterligare redigeringar. Ändringarna av väljaren bevaras nu korrekt, och beslutserbjudandena förblir synliga och redigerbara i VEC när de har sparats.(TGT-53433)
* **Korrigerade ett fel där [!UICONTROL Offer Decisions] försvann från aktiviteten efter att** sparats: [!UICONTROL Offer Decisions] som lades till under processen för att skapa aktivitet sparades inte efter att aktiviteten sparats och öppnats igen. Det här problemet uppstod när dynamiskt innehåll redigerades och [!UICONTROL Offer Decisions] infogades med specifika väljare och egenskaper. [!UICONTROL Offer Decisions] bevaras nu korrekt efter att du har sparat och väljarna förblir intakta, vilket garanterar konsekvent målinriktning och redigeringsbeteende. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Se detaljer
* **Ett problem i [!DNL Recommendations]-gränssnittet där CSV-hämtning med anpassade villkor returnerade 404-fel** har korrigerats där kunderna inte kunde hämta CSV-filen med anpassade villkor i processen för att skapa aktiviteter. Hämtningslänken fungerar nu korrekt, så att kunderna kan exportera anpassade villkor som förväntat. (TGT-51966)
* **Inkonsekvent inläsning av bilder i[!UICONTROL Catalog Search]** har korrigerats: Ett problem där miniatyrbilder och bilder i [!UICONTROL &#x200B; Catalog Search] inte lästes in konsekvent i processen där aktiviteten skapades har åtgärdats. Det gick inte att visa bilder om inte kolumnen &quot;Miniatyrbilds-URL&quot; var synlig och vissa produktbilder lästes in delvis eller inte alls efter navigerings- eller sökåtgärder. Bildinläsningsbeteendet har stabiliserats och miniatyrerna visas nu tillförlitligt oavsett om kolumnerna visas eller navigeras. (TGT-52778)
* **Ett problem har korrigerats där redigering av en rekommendation i en duplicerad upplevelse påverkade den ursprungliga upplevelsen**: Kunderna rapporterade att en rekommendation i en duplicerad upplevelse oavsiktligt ändrade den ursprungliga upplevelsen. I synnerhet efter att ha duplicerat Experience B i processen för att skapa aktiviteter och redigerat dess design eller kriterier, återspeglades samma ändringar i den ursprungliga Experience B, trots att de var separata enheter. Dubblerade upplevelser behåller nu separata konfigurationer, vilket säkerställer att redigeringar av en upplevelse inte påverkar originalet. (TGT-53369)
* **Ett problem har korrigerats där ändringar i en dubblerad upplevelse oavsiktligt påverkade den ursprungliga upplevelsen i en aktivitet**: Kunderna rapporterade att när de duplicerade en upplevelse i en aktivitet och tilldelar en ny publik, speglades även ändringar i den duplicerade upplevelsens design eller kriterier i den ursprungliga upplevelsen. Problemet uppstod trots att inga ändringar gjordes direkt i den ursprungliga versionen, vilket påverkade möjligheten att skapa oberoende variationer inom samma aktivitet. Processen för att skapa aktivitet isolerar nu duplicerade upplevelser korrekt och ser till att ändringar som görs i en upplevelse inte påverkar originalet. (TGT-53361)
* **Korrigerade ett fel där [!UICONTROL Recommendation Catalog] ibland inte kunde visa fullständiga produktattributdata**: I det uppdaterade [!DNL Recommendations] användargränssnittet uppstod ett problem där vissa produktattribut, som meddelande, inte visades konsekvent i [!UICONTROL Catalog Search]-resultaten, trots att data fanns i feeden. Det här problemet innebar att kunderna måste konfigurera om kolumnsynligheten manuellt för att kunna hämta de värden som saknas. [!UICONTROL Catalog Search] visar nu alla konfigurerade attribut på ett tillförlitligt sätt, vilket eliminerar behovet av manuella kolumnåterställningar. (TGT-52769)
* **Korrigerade ett problem där [!UICONTROL Front Promotion] inte kunde inaktiveras i en aktiv aktivitet**: Försök att inaktivera [!UICONTROL Front Promotion] i en aktiv aktivitet sparades inte. När du har markerat [!UICONTROL Change Promotion] och inaktiverat den förblev kampanjen aktiv när aktiviteten redigerades om, vilket förhindrar uppdateringar av rekommendationskonfigurationer. Kampanjinställningarna sparas nu korrekt så att kunderna kan inaktivera eller ändra kampanjer i aktiva aktiviteter som förväntat. (TGT-53231)
* **Ett problem har korrigerats där aktiveringen av [!DNL Recommendations] [!UICONTROL Promotion] utan data utlöste ett oklart felmeddelande**: Om du aktiverar [!UICONTROL Front] eller [!UICONTROL Back Promotion] i en [!DNL Recommendations]-aktivitet utan att ange obligatoriska värden, resulterade det i ett allmänt meddelande om&quot;Ogiltigt indatafel&quot;. Det underliggande problemet var ett saknat konfigurationsfält, men felmeddelandet visade inte orsaken, vilket gjorde felsökningen svår. Processen för att skapa aktivitet ger nu ett tydligt och åtgärdbart felmeddelande när obligatoriska fält, som `collectionId` eller regler, saknas, vilket hjälper kunderna att snabbt identifiera och lösa konfigurationsproblem. (TGT-52616)
* **Korrigerade ett fel som förhindrade att listan [!UICONTROL Product] visades i [!UICONTROL Edit] modal på fliken [!UICONTROL Recommendations]**: Kunderna kunde inte visa den filtrerade produktlistan när de redigerade en [!UICONTROL collection] eller [!UICONTROL exclusion] på fliken [!UICONTROL Recommendations]. Listan förväntades uppdateras i realtid baserat på tillämpade regler, men den såg inte ut som den var tänkt. Problemet har åtgärdats och produktlistan visas nu korrekt och uppdateras dynamiskt när reglerna ändras. (TGT-53481)
* **Ett problem med layouten i dialogrutan Visa detaljer i det uppdaterade användargränssnittet** har korrigerats: Layouten för spärrning av vydetaljer i det uppdaterade användargränssnittet har ändrats för att förbättra tydligheten och användbarheten. Dialogrutan innehåller nu två flikar:
   * Fliken [!UICONTROL Details]: Visar all relevant information för det markerade objektet.
   * Fliken [!UICONTROL Inventory]: Visar alla produkter som filtrerats enligt de aktuella reglerna för samling och undantag.

  Den här förbättringen gör det enklare för kunderna att navigera och förstå artikelspecifika data och lagersammanhang i aktivitetsskapandeprocessen. (TGT-53503)

   * **Korrigerade ett problem där borttagna erbjudanden i rekommendationsaktiviteter återkom efter att ha sparat**: Kunder rapporterade att när [!UICONTROL front] eller [!UICONTROL back] erbjudanden togs bort från [!DNL Recommendations] aktiviteter och aktiviteten sparades, fortsatte kampanjerna att visas när de öppnades igen. Problemet uppstod både i staging- och produktionsmiljöer och påverkade den uppdaterade processen att skapa aktivitet. Problemet har lösts. Kampanjer som tas bort från en aktivitet bevaras nu korrekt när de har sparats. (TGT-53490)

+++

**Rapporter**

+++Se detaljer
* **Ett problem har korrigerats där [!UICONTROL Automated Segments]-rapporten visade null-målgruppsvärden**: Kunderna rapporterade att [!UICONTROL Automated Segments] i aktivitetsrapporter visade null för målgruppsdata, vilket förhindrar en korrekt analys av segmentets prestanda. Det här problemet uppstod vid åtkomst till avsnittet [!UICONTROL Reports] och val av [!UICONTROL Automated Segments], även om giltiga målgruppsdata förväntades. [!UICONTROL Automated Segments] visar nu målgruppsvärden korrekt, vilket ger tillförlitliga rapporter och segmenteringsinsikter. (TGT-52793)

+++

**Single Page Applications (SPA)**

+++Se detaljer
* **Korrigerade ett problem där växling mellan [!UICONTROL Browse] - och [!UICONTROL Design]-lägen återställde SPA-läget i det uppdaterade användargränssnittet**: Kunder rapporterade att växling mellan [!UICONTROL Browse] - och [!UICONTROL Design] -lägen i det uppdaterade användargränssnittet gjorde att webbredigeraren lästes in igen och att SPA-lägena återställdes. Detta störde arbetsflödena och krävde att kunderna skrev in informationen igen. Problemet har lösts. SPA-läget bevaras nu när du växlar mellan lägen, vilket ger en jämnare och mer konsekvent upplevelse när du skapar aktiviteter. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Se detaljer
* **Ett problem har korrigerats i processen för att skapa aktivitet som blockerade progression till [!UICONTROL Targeting]-steget i AP-aktiviteter**: Ett fel i processen för att skapa aktivitet där kunderna inte kunde fortsätta till [!UICONTROL Targeting]-steget i [!UICONTROL Automated Personalization]-aktiviteter (AP) har korrigerats om inte två platser lades till. Detta beteende skilde sig från den tidigare upplevelsen, där en enda plats med flera erbjudanden var tillräckligt. Kravet har korrigerats, vilket gör att kunderna kan fortsätta använda inställningar för en plats som en del av sina AP-arbetsflöden. (TGT-53426)
* **Ett problem har korrigerats där den nya processen för att skapa aktivitet inte angav parametern fmt=png-alpha för genomskinliga bilder**: I det uppdaterade användargränssnittet ingick parametern `fmt=png-alpha` inte längre i bilder som infogades under processen för att skapa aktivitet. Detta resulterar i att genomskinligheten går förlorad. Det här beteendet skiljer sig från det tidigare användargränssnittet, som automatiskt lägger till parametern i bild-URL:er och bevarar genomskinliga bakgrunder. Processen för att skapa aktivitet använder nu parametern `fmt=png-alpha` korrekt på bild-URL:er när genomskinlighet krävs, vilket ger en konsekvent återgivning av genomskinliga resurser. (TGT-52615)
* **Korrigerade ett problem som hindrade kunder från att söka efter rapportsviter i det uppdaterade användargränssnittet**: i det uppdaterade användargränssnittet tillät inte listrutan [!UICONTROL Report Suites] i avsnittet [!UICONTROL Goals & Settings] kunderna att skriva och söka, vilket gjorde det svårt att hitta specifika rapportsviter, särskilt för klientorganisationer med ett stort antal poster. Till skillnad från det tidigare användargränssnittet sorterades inte listan och ingen indatabaserad filtrering saknades. Problemet har åtgärdats. Kunder kan nu skriva för att söka efter och filtrera rapportsviter och återställa de funktioner som finns i det gamla användargränssnittet. (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++Se detaljer
* **Ett problem har korrigerats där en kund som är begränsad till en enda arbetsyta kunde visa aktiviteter från andra arbetsytor**: Kunder med begränsad åtkomst till en arbetsyta kunde oväntat visa aktiviteter över alla arbetsytor när de valde [!UICONTROL All Workspaces] i processen för att skapa aktiviteter. Detta innebar en risk för oavsiktliga ändringar i andra arbetsytor, vilket kan påverka webbplatsens prestanda. Åtkomstkontrollerna i Workspace har förbättrats för att säkerställa att kunderna bara kan visa och interagera med aktiviteter på sin tilldelade arbetsyta. (TGT-53101)
* **Korrigerade ett problem där en kund kunde visa aktiviteter från [!UICONTROL Default Workspace] utan åtkomst:** En kund med begränsad åtkomst till arbetsytan för mellanlagring kunde visa aktiviteter från [!UICONTROL Default Workspace] via processen för att skapa aktiviteter. Detta beteende inträffade trots korrekt serverdelskonfiguration och åtkomsträttigheter. Åtkomstkontrollerna i Workspace har förbättrats för att säkerställa att kunderna bara kan visa aktiviteter på sin tilldelade arbetsyta.(TGT-53297)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
