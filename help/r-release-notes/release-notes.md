---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Vilka nya funktioner ingår i den aktuella versionen?
title: Versionsinformation (aktuell)
feature: Release Notes
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---


# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard- och Target Premium-version. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Target Standard/Premium 21.1.1 (19 januari 2021)

Den här underhållsversionen innehåller följande förbättringar, korrigeringar och ändringar.

Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

* En varning lades till när ett [!DNL Adobe Analytics]-mått valdes när [!UICONTROL Analytics as the reporting source] (A4T) användes i en [!UICONTROL Auto-Target]-aktivitet. [!UICONTROL Auto-Target] modellerna är optimerade för att fungera med binära (konverteringsbaserade) mätvärden. Om du väljer ett kontinuerligt mätvärde, till exempel intäkt, kan resultatet bli suboptimalt och [!UICONTROL Personalization Insights]-rapporterna kanske inte är korrekta. (TGT-38926)
* En statusikon har lagts till i [!UICONTROL Auto-Target Summary]-rapporten för [!UICONTROL Auto-Target]-aktiviteter som använder A4T. Den gröna bockikonen bredvid varje upplevelse i rapporten anger att en anpassad maskininlärningsmodell har skapats för den upplevelsen. Klockikonen anger att det inte finns tillräckligt med trafik för att skapa modellen. (TGT-38925)
* Rapporterna [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] för [!UICONTROL Auto-Target]-aktiviteter som använder A4T- och [!DNL Analytics]-konverteringsmått genereras och ser likadana ut som när [!DNL Target] används som rapportkälla. (TGT-38931)
* Ett miljöfilteralternativ har lagts till i [!UICONTROL Recommendations] [!UICONTROL Collections]-listan. (TGT-38353)
* Korrigerade ett problem som gjorde att felaktigt produktantal visades i [!UICONTROL Recommendations]-samlingar. (TGT-39162)
* Ett [!UICONTROL Last Updated]-filter har lagts till i [!UICONTROL Recommendations] [!UICONTROL Catalog Search]. (TGT-38340)
* Korrigerade ett fel i [!UICONTROL Recommendations] som gjorde att sidan [!UICONTROL Create Sequence] hängde efter att branschens vertikala ändrats. (TGT-38160)
* Ett problem som gjorde att aktiviteten inte kunde sparas om Device Co-op var aktiverad och användaren ändrades från [!DNL Target] som rapportkälla till [!DNL Analytics] (A4T) har åtgärdats. (TGT-38163)
* Ett problem som hindrade användare från att ta bort en målgrupp från ett erbjudande i en [!UICONTROL Automated Personalization]-aktivitet har åtgärdats. (TGT-39058)
* Korrigerade ett problem som gjorde att fel tidsram (start- och slutdatum) visades i [!UICONTROL Audience Info]-kort för vissa kunder. (TGT-39150)
* Ett problem som gjorde att vissa kunder inte kunde se aktivitetslistan i [!UICONTROL Default Workspace] har korrigerats. (TGT-38526)

## at.js 2.4.0 (14 januari 2021)

Den här versionen av at.js är en underhållsrelease och innehåller följande korrigeringar:

* Lägger till stöd för ett enhetligt profil-/plattforms-ID i leverans-API customerIds.
* Korrigerar ogiltig stiltaggsinmatning.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som kanske inte finns med i versionsinformationen.<br>Mer information finns i  [Dokumentationsändringar](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i  [Versionsinformation för tidigare versioner](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i  [versionsinformationen](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html) för Experience Cloud. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdateringslista för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar. |
| Kommande versionsinformation | Mer information om målversionerna för den aktuella månaden, inklusive förhandsversionsinformation, finns på sidan [Versionsinformation för mål - Förhandsversion](/help/r-release-notes/target-release-notes.md). |
