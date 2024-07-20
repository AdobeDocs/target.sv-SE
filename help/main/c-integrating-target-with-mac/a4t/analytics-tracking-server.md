---
keywords: analysspårningsserver;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;Reporting source;developtools
description: Lär dig hur du anger en Analytics-spårningsserver för aktiviteter som använder Analytics för  [!DNL Target] (A4T) om du använder en äldre version av at.js.
title: Hur använder jag en Analytics Tracking Server?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Använd en [!DNL Analytics]-spårningsserver

Om du använder en äldre version av at.js måste du ange en [!DNL Analytics]-spårningsserver för aktiviteter som använder [!DNL Adobe Analytics] för [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Du behöver inte ange en spårningsserver när du skapar en aktivitet om du använder at.js version 0.9.1 (eller senare). at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När aktiviteten skapas kan du lämna fältet [!UICONTROL Tracking Server] tomt på sidan [!UICONTROL Goals & Settings].
>
>[!DNL Target]-teamet stöder både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds. Mer information finns i [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

För att säkerställa att data från [!DNL Target] går till rätt plats i [!DNL Analytics], kräver A4T att en [!DNL Analytics]-spårningsserver skickas i alla anrop till Modstats från [!DNL Target]. För implementeringar som använder flera spårningsservrar använder du [!DNL Adobe Experience Platform Debugger] eller webbläsarens utvecklingsverktyg för att fastställa rätt spårningsserver för din aktivitet.

## Hämta spårningsservern [!DNL Analytics] med [!DNL Adobe Experience Platform Debugger]

Felsökaren bör visas på en sida där aktiviteten levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna [!DNL Adobe Experience Platform Debugger] från sidan där du skapar din aktivitet.

   Om du inte har installerat felsökaren läser du [Översikt över Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html).

1. Klicka på **[!UICONTROL Analytics]** i den vänstra navigeringsmenyn.

   ![Screen_DebuggerTrackServ-bild](assets/Screen_DebuggerTrackServ.png)

   Spårningsservern [!DNL Analytics] finns i avsnittet [!UICONTROL Hostname] i felsökaren.

   * **Spårningsserver för första part**: Om värdnamnet för begäran matchar domänen du är på är det en förstahandsspårningsserver. Om du till exempel är på `adobe.com` är `adobe.com` förstapartsspårningsservern.
   * **Spårningsserver från tredje part**: En spårningsserver från tredje part är vanligtvis `[company].sc.omtrdc.net` där företaget är företagets namn, men slutar alltid i `sc.omtrdc.net`.
   * **CNAME-implementeringar**: `sstats.adobe.com` är ett exempel på en CNAME-förstapartsspårningsserver för en https-begäran (säker). `stats.adobe.com` är ett exempel på en CNAME-förstapartsbegäran för en http-sida (inte säker).

1. Kopiera allt innehåll i fältet.

1. Klistra in spårningsserverinformationen i fältet **[!UICONTROL Tracking Server]** i avsnittet **[!UICONTROL Reporting Settings]** på skärmen **[!UICONTROL Goal & Settings]** för aktiviteten.

   >[!NOTE]
   >
   >Välj [!UICONTROL Analytics as the Reporting Source] för att din aktivitet ska vara tillgänglig för fältet [!UICONTROL Tracking Server].

## Hämta spårningsservern [!DNL Analytics] med hjälp av webbläsarens utvecklingsverktyg

Utvecklarverktygen ska visas på en sida där aktiviteten levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna webbläsarens utvecklingsverktyg (i Google Chrome klickar du på de tre lodräta ellipserna i det övre högra hörnet > Fler verktyg > Utvecklingsverktyg) på den sida där du skapar aktiviteten.

   ![Chrome utvecklarverktyg](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Klicka på fliken **[!UICONTROL Network]**.

1. Filtrera efter `/ss,` för att visa [!DNL Analytics]-begäranden.

   ![Chrome utvecklarverktyg med /ss-sökning](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Spårningsservern är värdnamnet för begäran.

   * **Spårningsserver för första part**: Om värdnamnet för begäran matchar domänen du är på är det en förstahandsspårningsserver. Om du till exempel är på `adobe.com` är `adobe.com` förstapartsspårningsservern.
   * **Spårningsserver från tredje part**: En spårningsserver från tredje part är vanligtvis `[company].sc.omtrdc.net` där företaget är företagets namn, men slutar alltid i `sc.omtrdc.net`.
   * **CNAME-implementeringar**: `sstats.adobe.com` är ett exempel på en CNAME-förstapartsspårningsserver för en https-begäran (säker). `stats.adobe.com` är ett exempel på en CNAME-förstapartsbegäran för en http-sida (inte säker).

1. Kopiera allt innehåll i fältet.

1. Klistra in spårningsserverinformationen i fältet **[!UICONTROL Tracking Server]** i avsnittet **[!UICONTROL Reporting Settings]** på skärmen **[!UICONTROL Goal & Settings]** för aktiviteten.

   >[!NOTE]
   >
   >Välj [!UICONTROL Analytics as the Reporting Source] för att din aktivitet ska vara tillgänglig för fältet [!UICONTROL Tracking Server].
