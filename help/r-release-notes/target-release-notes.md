---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
feature: Release Notes
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 14 januari 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
