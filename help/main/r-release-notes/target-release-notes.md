---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 24 juli 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.2 (13 augusti 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

**[!UICONTROL Activities]**

+++Se detaljer
* Korrigerade ett problem i det uppdaterade användargränssnittet för [!DNL Target] där vissa aktiviteter inte kunde läsas in vid redigeringsförsök. Det här problemet gjorde att kunderna lämnade användarna på en obegränsad inläsningsskärm. Problemet påverkade flera aktiviteter och rapporterades inträffa inkonsekvent mellan olika kunder. Med den här korrigeringen läses de påverkade aktiviteterna in korrekt, vilket ger smidig redigering och minskar störningarna i aktivitetsarbetsflödena. (TGT-53209)
* Korrigerade ett fel i processen för att skapa aktivitet som hindrade kunder från att spara ändringar på grund av ett serverdelsvalideringsfel: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Det här problemet uppstod när specifika element i en aktivitet ändrades, vilket resulterade i en misslyckad sparningsåtgärd. Korrigeringen ser till att `optionLocalId`-referenser nu valideras korrekt, vilket gör att kunder kan spara aktiviteter utan att detta fel påträffas. (TGT-53293)
* Korrigerade ett problem i processen för att skapa aktiviteter som gjorde att användargränssnittet kraschade efter att sidor byttes tre gånger under redigeringen. Kraschen utlöstes av ogiltiga alternativreferenser, vilket resulterade i konsolfel som &quot;Option with localId &#39;7&#39; not found.&quot; Med den här uppdateringen kan kunderna nu växla mellan sidor och tillämpa ändringar utan att stöta på systemfel eller avbrott. (TGT-53295)
* Korrigerade ett problem i processen för att skapa aktivitet där kunderna inte kunde spara ändringar i en aktivitet på grund av ett ogiltigt användarinmatningsfel. Felet uppstod när upplevelser i det uppdaterade användargränssnittet ändrades, vilket förhindrar att uppdateringar implementeras. Aktiviteten kan nu sparas utan avbrott så att kunderna kan redigera och publicera. (TGT-53267)
* Ett problem har korrigerats i processen där användare inte kunde redigera aktiviteter i det uppdaterade användargränssnittet på grund av en kontinuerlig inläsningsskärm. Kunder kan nu öppna och ändra aktiviteter utan att stöta på inläsningsfel. (TGT-53415)

+++

**Upplevelsefragment (XF)**

+++Se detaljer
* Korrigerade ett fel i processen för att skapa aktivitet som gjorde att kunder kunde redigera HTML för [!DNL Experience Fragments] (XF) som exporterades från [!DNL Adobe Experience Manager] (AEM) i [!DNL Target]. Detta beteende var oavsiktligt eftersom XF:er ska förbli låsta för redigering när de har publicerats från AEM. Korrigeringen ser till att alternativet&quot;Redigera HTML&quot; inte längre är tillgängligt för AEM-exporterade fragment, vilket bevarar innehållets integritet och förväntade styrning. (TGT-53286)

+++

**QA-läge**

+++Se detaljer
* Ett problem har korrigerats i processen där inledande mellanslag i aktivitets-URL:en inte trimmades korrekt när de sparades. Detta orsakade ogiltiga QA-länkar och felaktig formatering i serverdelen. Efter uppdateringen sparas URL:er nu korrekt, vilket förhindrar brutna länkar och förbättrar tillförlitligheten i QA-arbetsflöden för kunder. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Se detaljer
* Korrigerade ett fel i det nya [!UICONTROL Catalog Search]-gränssnittet där funktionen [!UICONTROL Advanced Search] inte kunde ge några förslag. Användarna måste ange exakta värden med exakt stavning, vilket gör sökningen krånglig och felbenägen. Med den här korrigeringen ger [!UICONTROL Advanced Search] nu relevanta förslag när användare skriver, vilket förbättrar användbarheten och minskar friktionen vid sökning av produkter. (TGT-52008)
* Ett antal problem har åtgärdats, bland annat att kriterieinformationen inte fungerade korrekt på enheter med liten skärm, att det inte gick att välja Alla värdgrupper i filtret [!UICONTROL Environment] och att det inte gick att interagera med entiteter som inte har något namn. Dessa korrigeringar förbättrar användbarheten i olika skärmstorlekar, säkerställer korrekt filtrering och möjliggör fullständig interaktion med alla produktenheter, vilket förbättrar den övergripande upplevelsen för användarna. (TGT-52992)
* Korrigerade ett problem i aktivitetsskapandeprocessen [!DNL Recommendations] där produkt-ID:n saknades i produktinformationsfönstret, vilket gjorde det svårt för kunder att kopiera eller referera till produkt-ID:n under arbetsflöden. Produkt-ID:n visas nu tydligt i detaljvyn, vilket ger bättre synlighet och stöd för effektivare produkthantering för kunder. (TGT-51964)
* Ett problem har korrigerats i aktivitetsskapandeprocessen där kolumnen [!UICONTROL Message] i vyn [!DNL Recommendations] inte visade produktdata trots att meddelanden fanns. Kunderna var tvungna att ta bort kolumnen manuellt och lägga till den på nytt för att tillfälligt visa innehållet, som ofta skulle försvinna igen vid bläddring eller sökning. Den här uppdateringen återställer konsekvent synlighet för produktmeddelanden, vilket förbättrar katalognavigering och arbetsflöden för granskning. (TGT-52777)
* Korrigerade ett fel i processen för att skapa aktivitet där det inte fanns några resultat om du valde miljön Alla värdgrupper i vyn [!DNL Recommendations]. Kunderna kan nu visa produktdata i alla värdgrupper som förväntat, vilket förbättrar synligheten och filtreringsnoggrannheten under aktivitetsinställningarna. (TGT-53006)
* Ett problem har korrigerats i processen för att skapa aktivitet där inaktiveringen av den främre erbjudandeväxlingen i aktivitetsinställningarna inte kvarstod efter att aktivitetsinställningarna sparats. Kunder som försökte ta bort frontkampanjen återaktiverades när aktiviteten granskades, vilket förhindrade en korrekt anpassning. Med den här uppdateringen kan ändringar sparas på ett tillförlitligt sätt, vilket ger kunderna full kontroll över kampanjinställningarna. (TGT-53215)

+++

**Visual Experience Composer (VEC)**

+++Se detaljer
* Korrigerade ett problem i processen där vissa aktiviteter inte kunde läsas in, vilket medförde att kunderna inte kunde komma åt ändringarna. Dessutom svarade inte knappen [!UICONTROL Cancel], vilket förhindrar kunder från att stoppa inläsningen eller avsluta redigeringsvyn. Med den här korrigeringen kan du nu läsa in aktiviteter tillförlitligt och knappen [!UICONTROL Cancel] fungerar som förväntat, vilket förbättrar den övergripande stabiliteten och användarupplevelsen i Visual Experience Composer (VEC) (TGT-53218)
* Korrigerade ett problem i det uppdaterade VEC-gränssnittet där ändringar inte kunde läsas in när de växlades mellan upplevelser i en XT-aktivitet (Experience Targeting). Kunderna kunde inte redigera upplevelser utöver den som de ursprungligen angav, och knappen [!UICONTROL Cancel] saknades eller svarade inte. Den här korrigeringen ser till att ändringar nu läses in korrekt i alla upplevelser och att knappen [!UICONTROL Cancel] fungerar tillförlitligt, även utan tillägget Helper, vilket förbättrar redigeringsarbetsflödena och minskar frustrationen. (TGT-53256)
* Korrigerade ett problem där växling mellan olika upplevelser orsakade en vit skärm. Dessutom har ett problem korrigerats i processen där kunderna skapade en vitskärm när de försökte ändra flera upplevelser i en aktivitet. Detta problem uppstod efter att ändringar gjorts i två upplevelser och sedan valt en tredje upplevelse, vilket förhindrar ytterligare redigeringar. Uppdateringen säkerställer smidiga övergångar mellan upplevelserna, så att kunderna kan göra ändringar utan avbrott. (TGT-53266)
* Ett problem har korrigerats där anpassade kodändringar som gjorts i Visual Experience Composer (VEC) inte sparades på ett tillförlitligt sätt i ett enda försök. Kunder rapporterade att ändringar, som formatuppdateringar eller HTML-redigering, ibland saknades på webbplatsen och i QA-URL:er, även efter att ha använt både [!UICONTROL Edit Content]- och [!UICONTROL Save]-knapparna. Den här regressionen har åtgärdats och säkerställer att alla anpassade kodändringar bevaras som förväntat mellan redigeringssessionerna. (TGT-53418)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
