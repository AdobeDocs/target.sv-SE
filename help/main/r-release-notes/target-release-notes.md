---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 888c50e7052229c22136526d632f89fbaa548298
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 25 januari 2023**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 22.13.3 (25-26 januari 2023)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **25 januari**: Europa, Mellanöstern och Afrika (EMEA)
* **25 januari**: Asien-Stillahavsområdet (APAC)
* **26 januari**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| Automated Personalization (AP) | Utökat stöd för JSON-erbjudanden i [!UICONTROL Automated Personalization] (AP) med formulärbaserad Experience Composer.<br>Mer information finns i [Skapa JSON-erbjudanden](/help/main/c-experiences/c-manage-content/create-json-offer.md). (TGT-41460) |
| Recommendations | Eget namn i [!UICONTROL Analytics for Target] A4T-rapportering är nu tillgänglig. Tidigare [!DNL Target] visas endast med upplevelse-ID:n. Den här förbättringen justerar rapporteringen mellan [!DNL Adobe Analytics] och [!DNL Target] och hjälper kunderna att effektivisera arbetet med att skapa rapporter i A4T. (TGT-41853) |
| AEM upplevelsefragment | Lagt till möjlighet att skilja mellan [!DNL Adobe Experience Manager] fragmenttyper (AEM XF) som exporteras till [!DNL Target]. I stället för alternativet Experience Fragment [!DNL Target] kan du nu filtrera och söka efter &quot;HTML XF&quot; och &quot;JSON XF&quot;. <br>Mer information finns i [AEM upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). (TGT-44132) |

* Ett problem som orsakade felet 500 i [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) aktiviteter som innehåller rekommendationer. Problemet uppstod när [!DNL Target] det gick inte att ta bort villkorsobjekt från [!DNL Target] Användargränssnitt och [!DNL Recommendations] som inte längre används. (TGT-44383)
* Platsen har tagits bort från erbjudandets namn i [!UICONTROL Offer Level] rapport för [!UICONTROL Automated Personalization] verksamhet. Den här ändringen gör rapporten mer läsbar. (TGT-44294)
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
