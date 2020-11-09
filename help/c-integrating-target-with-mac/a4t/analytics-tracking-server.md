---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;reporting source;developer tools
description: Om du använder en äldre version av at.js eller mbox.js måste du ange en analysspårningsserver för aktiviteter som använder Analytics för Target (A4T).
title: Använda en analysspårningsserver
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 0%

---


# Använda en analysspårningsserver

Om du använder en äldre version av at.js eller mbox.js måste du ange en analysspårningsserver för aktiviteter som använder [!DNL Analytics] för [!DNL Target] (A4T).

>[!NOTE]
>
>Om du använder [!DNL Analytics] som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar en aktivitet om du använder mbox.js version 61 (eller senare) eller at.js version 0.9.1 (eller senare). Mbox.js- eller at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När du skapar en aktivitet kan du lämna [!UICONTROL Tracking Server] fältet tomt på [!UICONTROL Goals & Settings] sidan.
>
>Teamet [!DNL Target] stöder både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds. Mer information finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)för at.js.

För att säkerställa att data från [!DNL Target] går till rätt plats i [!DNL Analytics]A4T kräver A4T att en analysspårningsserver skickas i alla anrop till Modstats från [!DNL Target]. För implementeringar som använder flera spårningsservrar kan du använda [!DNL Adobe Experience Platform Debugger] eller webbläsarens utvecklingsverktyg för att fastställa rätt spårningsserver för din aktivitet.

## Hämta Analytics-spårningsservern med Adobe Experience Platform Debugger

Felsökaren bör visas på en sida där aktiviteten kommer att levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna sidan som du skapar aktiviteten på [!DNL Adobe Experience Platform Debugger].

   Om du inte har installerat felsökaren läser du [Introduktion till Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Click **[!UICONTROL Analytics]** in the left navigation menu.

   Analysspårningsservern finns i felsökningsavsnittet [!UICONTROL Hostname] .

   * **Spårningsserver** för första part: Om värdnamnet för begäran matchar den domän du är på är det en förstapartsspårningsserver. Om du till exempel är på `adobe.com`är `adobe.com` den första part-spårningsservern.
   * **Spårningsserver** från tredje part: En spårningsserver från tredje part är vanligtvis `[company].sc.omtrdc.net` där företaget är namnet på ditt företag, men avslutas alltid `sc.omtrdc.net`.
   * **CNAME-implementeringar**: `sstats.adobe.com` är ett exempel på en CNAME-förstahandsspårningsserver för en https-begäran (säker). `stats.adobe.com` är ett exempel på en CNAME-förstapartsbegäran för en http-sida (osäker).

1. Kopiera allt innehåll i fältet.

1. Klistra in spårningsserverinformationen i fältet i **[!UICONTROL Reporting Settings]** delen av **[!UICONTROL Goal & Settings]** **[!UICONTROL Tracking Server]** aktivitetens skärm.

   >[!NOTE]
   >
   >Du måste välja [!UICONTROL Analytics as the Reporting Source] att aktiviteten ska vara [!UICONTROL Tracking Server] tillgänglig.

## Hämta Analytics tracking-servern med hjälp av webbläsarens Developer Tools

Utvecklarverktygen ska visas på en sida där aktiviteten levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna webbläsarens utvecklingsverktyg (i Google Chrome klickar du på de tre vertikala ellipserna i det övre högra hörnet > Fler verktyg > Utvecklingsverktyg) på den sida där du skapar aktiviteten.

   ![Kromutvecklarverktyg](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Klicka på **[!UICONTROL Network]** fliken.

1. Filtrera för `/ss,` att visa Analytics-begäranden.

   ![Verktyg för Chrome-utvecklare med /ss-sökning](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Spårningsservern är värdnamnet för begäran.

   * **Spårningsserver** för första part: Om värdnamnet för begäran matchar den domän du är på är det en förstapartsspårningsserver. Om du till exempel är på `adobe.com`är `adobe.com` den första part-spårningsservern.
   * **Spårningsserver** från tredje part: En spårningsserver från tredje part är vanligtvis `[company].sc.omtrdc.net` där företaget är namnet på ditt företag, men avslutas alltid `sc.omtrdc.net`.
   * **CNAME-implementeringar**: `sstats.adobe.com` är ett exempel på en CNAME-förstahandsspårningsserver för en https-begäran (säker). `stats.adobe.com` är ett exempel på en CNAME-förstapartsbegäran för en http-sida (osäker).

1. Kopiera allt innehåll i fältet.

1. Klistra in spårningsserverinformationen i fältet i **[!UICONTROL Reporting Settings]** delen av **[!UICONTROL Goal & Settings]** **[!UICONTROL Tracking Server]** aktivitetens skärm.

   >[!NOTE]
   >
   >Du måste välja [!UICONTROL Analytics as the Reporting Source] att aktiviteten ska vara [!UICONTROL Tracking Server] tillgänglig.

