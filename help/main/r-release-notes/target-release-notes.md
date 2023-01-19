---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5ad7427df49f6091f69fadac96fd55e7b48a4cda
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 19 januari 2023**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 22.13.3 (25 januari 2023)

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

* Utökat stöd för JSON-erbjudanden i [!UICONTROL Automated Personalization] (AP) med formulärbaserad Experience Composer. (TGT-41460)
* Implementerat [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md) för AP-aktiviteter. (TGT-44341)
* Experience names in [!DNL Recommendations] aktiviteter visas nu med egna namn så att kunderna bättre kan korrelera data i [!DNL Adobe Analytics] med det i [!DNL Target] Gränssnitt. (TGT-41853)
* Ett problem som orsakade felet 500 i [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) aktiviteter som innehåller rekommendationer. Problemet uppstod när [!DNL Target] det gick inte att ta bort villkorsobjekt från [!DNL Target] Användargränssnitt och [!DNL Recommendations] som inte längre används. (TGT-44383)
* Platsen har tagits bort från erbjudandets namn i [!UICONTROL Offer Level] rapport för [!UICONTROL Automated Personalization] verksamhet. Den här ändringen gör rapporten mer läsbar. (TGT-44294)
* Ändrade namn på &quot;[!UICONTROL Experience Fragment]&quot; i [!UICONTROL Visual Experience Composer] (VEC) arbetsflöde. Alternativet är nu &quot;[!UICONTROL HTML XF].&quot; (TGT-44132)
* Lagt till möjlighet att visa metadata för upplevelsefragment i verktygstipset för erbjudandeinformation. (TGT-43838)
* Alternativen för 45-dagars och 90-dagars kalender har tagits bort från åtkomstpunkten och [!UICONTROL Auto-Target] [!UICONTROL Personalization Insights] och [!UICONTROL Important Attributes] rapporter i [!DNL Target] Gränssnitt. På grund av användningsmönster och för att förbättra prestanda har datumintervallen tagits bort. Gränssnittet har uppdaterats för att återspegla de aktuella tillåtna intervallen: 15, 30 och 60 dagar. (TGT-39357)
* Otillåten möjlighet att ändra [!UICONTROL Same as Optimization Goal] på [!UICONTROL Goals & Settings] sida efter att aktiviteten är aktiv. (TGT-43923)
* Ett problem som orsakade problem med standardarbetsytan i [!DNL Target] backend när du uppgraderar från [!DNL Target Standard] till [!DNL Target Premium]. (TGT-44081 &amp; TGT-44306)
* Länken på [!UICONTROL Implementation] sida ([!UICONTROL Administration] > [!UICONTROL Implementation]) för&quot;Implementeringsmetoder med On-Device Decisioning&quot; så att de pekar på sidan som förklarar hur du använder enhetsbeslut för alla SDK:er som stöds: Node.js, Java, .NET och Python. Mer information finns i [Komma igång med mål-SDK:er](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Ett problem som orsakade filöverföringsproblem vid användning har korrigerats [!DNL Scene7] och [!DNL Target].
* Förbättrad tillgänglighet för [!DNL Target] Användargränssnitt för personer med funktionshinder genom att använda resultat från en intern användarvänlighetsrevision. Dessa tillgänglighetsförbättringar inkluderar åtkomst till funktioner som tidigare inte var tillgängliga via tangentbordet, alt-text-förbättringar, möjlighet att zooma delar av användargränssnittet så att de blir mer användbara, förbättrat tangentbordsfokus med mera.   (TGT-42759)
* Utför olika lokaliseringsåtgärder i hela [!DNL Target] Gränssnitt.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |


## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
