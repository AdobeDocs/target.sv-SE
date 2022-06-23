---
keywords: analysspårningsserver;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;Reporting source;developtools
description: 'Lär dig hur du anger en analysspårningsserver för aktiviteter som använder Analytics för [!DNL Target] (A4T) om du använder en äldre version av at.js. '
title: Hur använder jag en Analytics Tracking Server?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---

# Använda en analysspårningsserver

Om du använder en äldre version av at.js måste du ange en analysspårningsserver för aktiviteter som använder [!DNL Adobe Analytics] for [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Du behöver inte ange en spårningsserver när du skapar en aktivitet om du använder at.js version 0.9.1 (eller senare). at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När du skapar en aktivitet kan du lämna [!UICONTROL Tracking Server] fältet är tomt på [!UICONTROL Goals & Settings] sida.
>
>The [!DNL Target] team har stöd för både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds. Mer information finns i [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).

För att säkerställa att data från [!DNL Target] går till rätt plats i [!DNL Analytics]kräver A4T att en analysspårningsserver skickas i alla anrop till Modstats från [!DNL Target]. För implementeringar som använder flera spårningsservrar använder du [!DNL Adobe Experience Platform Debugger] eller webbläsarens utvecklingsverktyg för att fastställa rätt spårningsserver för din aktivitet.

## Hämta Analytics-spårningsservern med Adobe Experience Platform Debugger

Felsökaren bör visas på en sida där aktiviteten levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna sidan som du skapar aktiviteten på [!DNL Adobe Experience Platform Debugger].

   Om du inte har installerat felsökaren kan du läsa [Introduktion till Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Klicka **[!UICONTROL Analytics]** i den vänstra navigeringsmenyn.

   Analysspårningsservern finns i [!UICONTROL Hostname] i felsökaren.

   * **Spårningsserver för första part**: Om värdnamnet för begäran matchar den domän du är på är det en förstapartsspårningsserver. Om du till exempel är på `adobe.com`, `adobe.com` är förstahandsspårningsservern.
   * **Spårningsserver från tredje part**: En spårningsserver från tredje part är vanligtvis `[company].sc.omtrdc.net` där företaget är namnet på ditt företag, men alltid avslutas i `sc.omtrdc.net`.
   * **CNAME-implementeringar**: `sstats.adobe.com` är ett exempel på en CNAME-förstahandsspårningsserver för en https-begäran (säker). `stats.adobe.com` är ett exempel på en CNAME-förstapartsbegäran för en http-sida (osäker).

1. Kopiera allt innehåll i fältet.

1. I **[!UICONTROL Reporting Settings]** i **[!UICONTROL Goal & Settings]** skärm för aktiviteten, klistra in spårningsserverinformationen i **[!UICONTROL Tracking Server]** fält.

   >[!NOTE]
   >
   >Välj [!UICONTROL Analytics as the Reporting Source] för din aktivitet på [!UICONTROL Tracking Server] som ska vara tillgängligt.

## Hämta Analytics tracking-servern med hjälp av webbläsarens Developer Tools

Utvecklarverktygen ska visas på en sida där aktiviteten levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna webbläsarens utvecklingsverktyg (i Google Chrome, klicka på de tre vertikala ellipserna i det övre högra hörnet > Fler verktyg > Utvecklingsverktyg) på den sida där du skapar aktiviteten.

   ![Kromutvecklarverktyg](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Klicka på **[!UICONTROL Network]** -fliken.

1. Filter för `/ss,` för att visa Analytics-förfrågningar.

   ![Verktyg för Chrome-utvecklare med /ss-sökning](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Spårningsservern är värdnamnet för begäran.

   * **Spårningsserver för första part**: Om värdnamnet för begäran matchar den domän du är på är det en förstapartsspårningsserver. Om du till exempel är på `adobe.com`, `adobe.com` är förstahandsspårningsservern.
   * **Spårningsserver från tredje part**: En spårningsserver från tredje part är vanligtvis `[company].sc.omtrdc.net` där företaget är namnet på ditt företag, men alltid avslutas i `sc.omtrdc.net`.
   * **CNAME-implementeringar**: `sstats.adobe.com` är ett exempel på en CNAME-förstahandsspårningsserver för en https-begäran (säker). `stats.adobe.com` är ett exempel på en CNAME-förstapartsbegäran för en http-sida (osäker).

1. Kopiera allt innehåll i fältet.

1. I **[!UICONTROL Reporting Settings]** i **[!UICONTROL Goal & Settings]** skärm för aktiviteten, klistra in spårningsserverinformationen i **[!UICONTROL Tracking Server]** fält.

   >[!NOTE]
   >
   >Välj [!UICONTROL Analytics as the Reporting Source] för din aktivitet på [!UICONTROL Tracking Server] som ska vara tillgängligt.
