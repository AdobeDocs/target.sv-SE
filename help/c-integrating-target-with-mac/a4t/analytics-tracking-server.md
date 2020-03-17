---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: Om du använder en äldre version av at.js eller mbox.js måste du ange en analysspårningsserver för aktiviteter som använder Analytics för Target (A4T).
title: Använda en analysspårningsserver
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Använda en analysspårningsserver{#use-an-analytics-tracking-server}

Om du använder en äldre version av at.js eller mbox.js måste du ange en analysspårningsserver för aktiviteter som använder Analytics för Target (A4T).

>[!NOTE]
>
>Om du använder Adobe Analytics som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar aktiviteter om du använder mbox.js version 61 (eller senare) eller at.js version 0.9.1 (eller senare). Mbox.js- eller at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När du skapar en aktivitet kan du lämna [!UICONTROL Tracking Server] fältet tomt på [!UICONTROL Goals & Settings] sidan.

För att säkerställa att data från Target kommer till rätt plats i Analytics kräver A4T att en analysspårningsserver skickas i alla anrop till Modstats från Target. För implementeringar som använder flera spårningsservrar kan du använda Adobe Experience Cloud Debugger för att fastställa rätt spårningsserver för din aktivitet.

Felsökaren bör visas på en sida där aktiviteten kommer att levereras för att säkerställa att du väljer rätt spårningsserver. Du kan också ange en standardspårningsserver för varje konto. Kontakta kundtjänst om du vill ange eller ändra standardinställningen.

1. Öppna Adobe Experience Cloud Debugger på den sida där du skapar din aktivitet.

   Om du inte har installerat felsökaren läser du [Installera Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   Analysspårningsservern finns i SiteCatalyst-bildavsnittet i felsökaren. Fältet kallas *cookies* från första part eller cookies från *tredje part* beroende på implementeringen, och värdet för Analytics tracking-servern kommer att ha något av följande format:

   * (för CNAME-implementeringar)
   * (för implementeringar som inte är installerade på RDC)
   * (för implementering av RDC)
   *Företag* representerar Analytics-företagets namn, *mått* är ett exempel på ett CNAME-värde och *d1* är ett exempel på ett Analytics-datacenter.
1. Kopiera allt innehåll i fältet.
1. Klistra in spårningsserverinformationen i fältet i [!UICONTROL Reporting Settings] delen av [!UICONTROL Goal & Settings] **[!UICONTROL Tracking Server]** aktivitetens skärm.

   >[!NOTE]
   >
   >Du måste välja Adobe Analytics som rapportkälla för din aktivitet för att fältet Spårningsserver ska vara tillgängligt.

