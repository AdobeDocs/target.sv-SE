---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 14bd000afe6983c2cdab185e4f54cc6b2f14627b
workflow-type: tm+mt
source-wordcount: '1238'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 20 augusti 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Informationen i den här artikeln uppdateras ofta, särskilt före releaser.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.3 (21 augusti 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**Erbjudandebeslut**

+++Se detaljer
* **Ett problem som hindrade kunder från att redigera beslutserbjudanden och välja specifika sidelement i det uppdaterade användargränssnittet** har korrigerats: I den uppdaterade processen för att skapa aktiviteter kunde kunderna inte redigera befintliga beslutserbjudanden eller välja specifika sidelement i Visual Experience Composer (VEC). Beslutserbjudandena visades felaktigt som erbjudanden från HTML och de ändringar som gjordes under redigeringen sparades inte. Dessutom gick det inte att läsa in vissa regionala URL:er, till exempel den japanska webbplatsen, korrekt i VEC, vilket blockerar skapande och uppdatering av aktiviteter. Besluten visas nu korrekt, sidelementen kan markeras som förväntat och regionala URL:er läses in korrekt i VEC, vilket återställer redigeringsfunktionerna. (TGT-53425)
* **Ett problem har korrigerats där [!UICONTROL Offer Decision] väljare inte kunde ändras och ändras oväntat efter att** sparats: I den uppdaterade processen för att skapa aktivitet kunde kunderna inte ändra [!UICONTROL Offer Decision]-väljaren som det var tänkt. Försöken att ändra väljaren misslyckades och väljaren återgick till ett felaktigt värde efter att den sparats. Detta beteende gjorde att beslutserbjudandet försvann från Visual Experience Composer (VEC), vilket blockerade ytterligare redigeringar. Ändringarna av väljaren bevaras nu korrekt, och beslutserbjudandena förblir synliga och redigerbara i VEC när de har sparats.(TGT-53433)
* **Korrigerade ett fel där [!UICONTROL Offer Decisions] försvann från aktiviteten efter att** sparats: [!UICONTROL Offer Decisions] som lades till under processen för att skapa aktivitet sparades inte efter att aktiviteten sparats och öppnats igen. Det här problemet uppstod när dynamiskt innehåll redigerades och [!UICONTROL Offer Decisions] infogades med specifika väljare och egenskaper. [!UICONTROL Offer Decisions] bevaras nu korrekt efter att du har sparat och väljarna förblir intakta, vilket garanterar konsekvent målinriktning och redigeringsbeteende. (TGT-53434)

+++

**Rekommendationer**

+++Se detaljer
* **Korrigerat problem i rekommenderadendations-gränssnitt där CSV-hämtning med anpassade villkor returnerade 404-fel**: Korrigerat ett problem där kunderna inte kunde hämta CSV-filen med anpassade villkor i processen för att skapa aktiviteter. Hämtningslänken fungerar nu korrekt, så att kunderna kan exportera anpassade villkor som förväntat. (TGT-51966)
* **Inkonsekvent inläsning av bilder i[!UICONTROL Catalog Search]** har korrigerats: Ett problem där miniatyrbilder och bilder i [!UICONTROL &#x200B; Catalog Search] inte lästes in konsekvent i processen där aktiviteten skapades har åtgärdats. Det gick inte att visa bilder om inte kolumnen &quot;Miniatyrbilds-URL&quot; var synlig och vissa produktbilder lästes in delvis eller inte alls efter navigerings- eller sökåtgärder. Bildinläsningsbeteendet har stabiliserats och miniatyrerna visas nu tillförlitligt oavsett om kolumnerna visas eller navigeras. (TGT-52778)
* **Ett problem har korrigerats där redigering av en rekommendation i en duplicerad upplevelse påverkade den ursprungliga upplevelsen**: Kunderna rapporterade att en rekommendation i en duplicerad upplevelse oavsiktligt ändrade den ursprungliga upplevelsen. I synnerhet efter att ha duplicerat Experience B i processen för att skapa aktiviteter och redigerat dess design eller kriterier, återspeglades samma ändringar i den ursprungliga Experience B, trots att de var separata enheter. Dubblerade upplevelser behåller nu separata konfigurationer, vilket säkerställer att redigeringar av en upplevelse inte påverkar originalet. (TGT-53369)
* **Ett problem har korrigerats där ändringar i en dubblerad upplevelse oavsiktligt påverkade den ursprungliga upplevelsen i en aktivitet**: Kunderna rapporterade att när de duplicerade en upplevelse i en aktivitet och tilldelar en ny publik, speglades även ändringar i den duplicerade upplevelsens design eller kriterier i den ursprungliga upplevelsen. Detta skedde trots att inga ändringar gjordes direkt i den ursprungliga versionen, vilket påverkade möjligheten att skapa oberoende variationer inom samma aktivitet. Processen för att skapa aktivitet isolerar nu duplicerade upplevelser korrekt och ser till att ändringar som görs i en upplevelse inte påverkar originalet. (TGT-53361)
* **Ett problem har korrigerats där [!UICONTROL Recommendation Catalog] ibland inte kunde visa fullständiga produktattributdata**: I det uppdaterade [!DNL Recommendations] användargränssnittet uppstod ett problem där vissa produktattribut, som meddelande, inte visades konsekvent i C[!UICONTROL atalog Search]-resultatet, trots att data fanns i feeden. Det här problemet innebar att kunderna måste konfigurera om kolumnsynligheten manuellt för att kunna hämta de värden som saknas. [!UICONTROL Catalog Search] visar nu alla konfigurerade attribut på ett tillförlitligt sätt, vilket eliminerar behovet av manuella kolumnåterställningar. (TGT-52769)
* **Korrigerade ett problem där [!UICONTROL Front Promotion] inte kunde inaktiveras i en aktiv aktivitet**: Försök att inaktivera [!UICONTROL Front Promotion] i en aktiv aktivitet sparades inte. När du har markerat [!UICONTROL Change Promotion] och inaktiverat den förblev kampanjen aktiv när aktiviteten redigerades om, vilket förhindrar uppdateringar av rekommendationskonfigurationer. Kampanjinställningarna sparas nu korrekt så att kunderna kan inaktivera eller ändra kampanjer i aktiva aktiviteter som förväntat. (TGT-53231)
* **Ett problem har korrigerats där aktiveringen av [!DNL Recommendations] [!UICONTROL Promotion] utan data utlöste ett oklart felmeddelande**: Om du aktiverar [!UICONTROL Front] eller [!UICONTROL Back Promotion] i en [!DNL Recommendations]-aktivitet utan att ange obligatoriska värden, resulterade det i ett allmänt meddelande om&quot;Ogiltigt indatafel&quot;. Det underliggande problemet var ett saknat konfigurationsfält, men felmeddelandet visade inte orsaken, vilket gjorde felsökningen svår. Processen för att skapa aktivitet ger nu ett tydligt och åtgärdbart felmeddelande när obligatoriska fält, som `collectionId` eller regler, saknas, vilket hjälper kunderna att snabbt identifiera och lösa konfigurationsproblem. (TGT-52616)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Se detaljer
* **Ett problem har korrigerats i processen för att skapa aktivitet som blockerade progression till [!UICONTROL Targeting]-steget i AP-aktiviteter**: Ett fel i processen för att skapa aktivitet där kunderna inte kunde fortsätta till [!UICONTROL Targeting]-steget i [!UICONTROL Automated Personalization]-aktiviteter (AP) har korrigerats om inte två platser lades till. Detta beteende skilde sig från den tidigare upplevelsen, där en enda plats med flera erbjudanden var tillräckligt. Kravet har korrigerats, vilket gör att kunderna kan fortsätta använda inställningar för en plats som en del av sina AP-arbetsflöden. (TGT-53426)
* **Ett problem har korrigerats där den nya processen för att skapa aktivitet inte angav parametern fmt=png-alpha för genomskinliga bilder**: I det uppdaterade användargränssnittet ingick parametern `fmt=png-alpha` inte längre i bilder som infogades under processen för att skapa aktivitet. Detta resulterar i att genomskinligheten går förlorad. Det här beteendet skiljer sig från det tidigare användargränssnittet, som automatiskt lägger till parametern i bild-URL:er och bevarar genomskinliga bakgrunder. Processen för att skapa aktivitet använder nu parametern `fmt=png-alpha` korrekt på bild-URL:er när genomskinlighet krävs, vilket ger en konsekvent återgivning av genomskinliga resurser. (TGT-52615)

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
