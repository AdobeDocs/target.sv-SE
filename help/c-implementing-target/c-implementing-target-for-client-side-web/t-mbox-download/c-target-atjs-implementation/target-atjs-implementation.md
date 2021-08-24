---
keywords: Målstandard;at.js;implementation
description: Lär dig hur du migrerar till at.js, det nya implementeringsbiblioteket för Adobe [!DNL Target] som är utformat för både vanliga webbimplementeringar och Single Page-program (SPA).
title: Hur migrerar jag från mbox.js till at.js?
feature: at.js
role: Developer
exl-id: 1d95faeb-7caa-44d6-b637-a06db393e50e
source-git-commit: e0713ccd25da71c2655b567ff8715a22203f46fb
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---

# Migrera från mbox.js till at.js

at.js-biblioteket är ett nytt implementeringsbibliotek för [!DNL Adobe Target] som är utformat för både vanliga webbimplementeringar och enkelsidiga program.

[!DNL at.js] ger bland annat bättre sidladdningstider för webbimplementeringar och bättre implementeringsalternativ för enkelsidiga program.

[!DNL at.js] ersätts  [!DNL mbox.js] för  [!DNL Target] implementeringar. [!DNL at.js]-biblioteket innehåller även de komponenter som ingick i [!DNL target.js], så det finns inte längre något anrop till [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 med FP-11577 (eller senare) stöder at.js-implementeringar med integrering av Adobe Target-Cloud Services. Mer information finns i [Funktionspaket](https://experienceleague.adobe.com/docs/) och [Integrera med Adobe Target](https://experienceleague.adobe.com/docs/) i *Adobe Experience Manager 6.2-dokumentationen*.

## Implementera at.js {#implement}

Om du vill använda [!DNL at.js] ersätter du referensen [!DNL mbox.js] på sidor där du vill implementera den. Du kan inte använda både [!DNL mbox.js] och [!DNL at.js] på en enda sida. Du kan dock använda båda sidorna på webbplatsen.

Biblioteket [!DNL at.js] fungerar för befintliga implementeringar med funktionerna `mboxCreate()`, `mboxDefine()` och `mboxUpdate()` och har stöd för nya funktioner som fokuserar på single-page-appbaserade implementeringar.

Du kan använda [!DNL at.js] var du än använder [!DNL mbox.js].

[!DNL at.js]-biblioteket innehåller flera förbättringar av [!DNL mbox.js]-biblioteket, bland annat:

* Helt asynkron kommunikation via AJAX

   >[!IMPORTANT]
   >
   >Även om [!DNL at.js] kommunicerar med [!DNL Target]-servrarna asynkront måste själva [!DNL at.js]-filen läsas in synkront i `<head>`-avsnittet på sidan. Helst ska det vara ett av de första inlästa skripten. När den har lästs in kör [!DNL at.js] mbox-anrop asynkront via `XMLHttpRequest`, och blockerar inte sidåtergivning.

* Inga fler spärrsamtal
* Ingen `document.write()` används
* Ingen omedelbar körning av JavaScript i [!DNL Target]-svar
* Bättre timeout och felhantering

   * Anpassningsbar [timeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) per anrop
   * Inga omladdningar vid timeout

* Funktioner som är särskilt utformade för single page-appar/MVC-ramverk

## Utbildningsvideo: at.js - Fördelar och bästa praxis för implementering ![Översikt](/help/assets/overview.png)

Den här videon handlar om inspelningen av &quot; [kontorstid](/help/cmp-resources-and-contact-information.md)&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Så fungerar biblioteket at.js
* Fördelarna med at.js jämfört med mbox.js
* Hur at.js hanterar flimmer
* Felhantering i at.js
* Felsökningsmetoder
* Kända fel och framtida färdplan

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
