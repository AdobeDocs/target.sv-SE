---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b7258ae154ae2b354e70349d8d878a1338128417
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 23 maj 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## at.js version 2.9.0 (25 maj 2022)

* Stöd för klienttips för användaragent har lagts till.
* Korrigerade ett fel där flera mbox-förfrågningar på samma sida har olika ID:n för intrycket.

## [!DNL Target Standard/Premium] 22.5.1 (stegvis frisättning; 11-13 maj 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **11 maj**: Asien-Stillahavsområdet (APAC)
* **12 maj**: Amerika
* **13 maj**: Europa, Mellanöstern och Afrika (EMEA)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Ett problem som orsakade ett JavaScript-fel och som hindrade vissa kunder från att komma åt aktivitetsinformationen för vissa har åtgärdats [!UICONTROL Automated Personalization] (AP) aktiviteter. (TGT-43526)
* Ett problem som gjorde att vissa kunder inte kunde lägga till (eller redigera) ett specifikt erbjudande i en AP-aktivitet har åtgärdats. (TGT-43503)
* Ett problem i [!DNL Target] Gränssnitt som visade följande felmeddelande: &quot;Din globala mbox kanske inte är synkroniserad. Försök spara om den.&quot; Det här problemet var ett gränssnittsproblem och påverkade inte kundernas implementeringar. (TGT-43475)
* Ett problem som hindrade en kund från att redigera förbättringar på erfarenhetsnivå och målgrupper för en aktivitet om förbättringarna och målgrupperna skapades före den nya [!UICONTROL Audiences] Gränssnittet har distribuerats. (TGT-43433)
* Ett problem som gjorde att kunderna kunde välja dubblett har korrigerats [!DNL Adobe Audience Manager] (AAM) målgrupper när de redigerar rapportmålgrupper för en aktivitet. (TGT-43430)
* Korrigerade ett problem som hindrade kunder från att skapa dubblerade målgrupper, men i olika arbetsytor. (TGT-43423)
* Ett problem som gjorde att kunder inte kunde ta bort platser med ad hoc-erbjudanden i aktiviteter skapade i [!UICONTROL Form-Based Experience Composer]. (TGT-43315)
* Korrigerade ett problem som förhindrade kunder från att få tillgång till koderbjudanden efter att ha klickat på bilderbjudanden och sedan uppdaterat användargränssnittet. (TGT-43566)
* Korrigerade ett problem som fick redigeringar av profilskript att återgå till det ursprungliga oredigerade skriptet efter att skriptet redigerats, aktiverats och sedan inaktiverats. Profilskriptet förblir nu redigerat. (TGT-43249)
* Ett problem som orsakade följande fel vid försök att flytta en målgrupp till en annan arbetsyta har korrigerats: &quot;Vi kan inte slutföra din begäran. Kontakta Adobe Client Care om problemet kvarstår.&quot; (TGT-43212)
* Korrigerade ett fel som orsakade ett fel vid kloning av anpassade kodändringar för sidor i Single Page App (SPA). (TGT-43137)
* Korrigerade ett problem som gjorde att den ursprungliga kampanjen påverkades efter att en upplevelse duplicerats och sedan befordringen redigerades. (TGT-41775)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
