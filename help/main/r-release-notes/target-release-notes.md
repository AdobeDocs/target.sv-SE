---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar som ingår i de kommande [!DNL Target] Frisläpp?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1cc630f12f4b9dc1d9c5700bc6174b40d4f0dae2
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 27 mars 2023**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 23.3.1 (28-30 mars 2023)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **28 mars**: Europa, Mellanöstern och Afrika (EMEA)
* **29 mars**: Asien-Stillahavsområdet (APAC)
* **30 mars**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
|--- |--- |
| AEM innehållsfragment för headless personalisering och experimenterande | Använd [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments] in [!DNL Target] verksamhet. Kombinera enkelheten och kraften i AEM med kraftfulla artificiella intelligens (AI) och maskininlärningsfunktioner (ML) i [!DNL Target] att testa och personalisera upplevelser i stor skala. |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]<p>(Releasedatum 30 mars 2023) | [!DNL Target] låter dig välja mätvärden baserat på binomiala händelser eller mätvärden baserade på kontinuerliga händelser när du använder [!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet.<P>Observera följande ändring av mätvärden som stöds:<ul><li>[!DNL Target] har behållit det tidigare beteendet för befintliga aktiviteter till och med 9 september 2023. Efter detta datum kommer aktiviteter som använder mätvärden som inte stöds att avbrytas för att tvinga befintlig aktivitetsmigrering till det nya beteendet.</li></ul> |
| [!UICONTROL Auto-Allocate] använda [!UICONTROL Analytics for Target] (A4T) | Uppdaterad självstudiekurs:<ul><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Allocate] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL Auto-Target] använda [!UICONTROL Analytics for Target] (A4T) | Uppdaterad självstudiekurs:<ul><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Target] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* Förbättrad målgrupps- och aktivitetssynkronisering så att objekt som skapats i [!DNL Adobe Experience Platform] och [!DNL Adobe Audience Manager] finns i [!DNL Target] Snabbare gränssnitt. (TGT-44568)
* Har ändrats så att användarna kan ta bort [!UICONTROL Default URL] under [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer] > [!UICONTROL Default URL]. Med den här ändringen kan kunderna ändra standard-URL:en tillbaka till en tom sträng, vilket tidigare inte var möjligt efter den initiala konfigurationen. (TGT-44577)
* Tog bort begränsningar som hindrade kunderna från att redigera eller ta bort körklara målgrupper (målgrupper med reserverade namn). (TGT-44655)
* Inaktiverade &quot;[!UICONTROL Done]&quot; när du laddade mellanrum visades i [!DNL Target] Gränssnitt när du skapar [kombinerade målgrupper](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Korrigerade [!UICONTROL Language] länken längst ned i [!UICONTROL Audiences] så att den länkar till[!UICONTROL Account communication preferences]&quot;. (TGT-43562)
* Löste ett problem som ibland hindrade kunder från att skapa [!UICONTROL A/B Test] aktiviteter efter att du har valt [!UICONTROL Adobe Analytics] option under [!UICONTROL Administration] > [!UICONTROL Reporting] > [!UICONTROL Reporting Experience Cloud Solution]. (TGT-44844)
* Ett problem som gjorde att kunderna inte kunde visa den senaste upplevelsen i ett [!UICONTROL Multivariate Test] aktivitet med många upplevelser inifrån [!UICONTROL Visual Experience Composer] (VEC). The [DOM-sökväg](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) längst ned på VEC hindrade ibland kunderna från att se den senaste upplevelsen. (TGT-44578)
* Korrigerade ett problem som gjorde att Bläddra-URL:en i VEC inte reflekterade den aktuella sidan som är synlig i en normal webbläsarsession om sidan kräver auktorisering eller anropar omdirigeringar. (TGT-44350)
* Ett problem som hindrade kunderna från att ändra [!UICONTROL Filter Incompatible Criteria] ange [!UICONTROL Recommendations] > [!UICONTROL Settings]. (TGT-44398)
* Ett problem som orsakade att POST begärde att få skapa nya har åtgärdats [!DNL Recommendations] feeds som ska misslyckas vid användning [!UICONTROL Analytics Classifications] med rapportsviter med punkter i namnen. (TGT-44598)
* Uppdaterade länkar i [!DNL Target] Gränssnitt som pekar på det nya [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Förbättrat skydd för att förhindra SSRF-försök (Server-Side Request Forgery) i [!DNL Recommendations] feeds. (TGT-43769)
* Ett problem som gjorde att kunderna inte kunde visa förhandsvisningsbilder i har korrigerats [!DNL Recommendations] skapar symboler om bildnamnet innehåller [GB18030 tecken](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* Ett problem som orsakade vissa har korrigerats [GB18030 tecken](https://en.wikipedia.org/wiki/GB_18030){target=_blank} att rymmas i [!UICONTROL Modifications] panel vid redigering [!UICONTROL Text/HTML] på en aktivitet [!UICONTROL Experiences] sida. (TGT-44600)
* Utför olika lokaliseringsåtgärder i hela [!DNL Target] Gränssnitt.


## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |


## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
