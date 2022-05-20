---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 953b511db6d2c7ccf883d8e256c4e0ab22718862
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

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

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i [Versionsinformation för Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdatering för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation, finns i [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md) sida. |
