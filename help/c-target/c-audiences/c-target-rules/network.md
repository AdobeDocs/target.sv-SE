---
keywords: Targeting;network;target network;isp;domain name;connection speed;target isp;target domain name;target connection speed
description: Du kan skapa målgrupper i Adobe Target baserat på nätverksinformation.
title: Nätverksalternativ i Adobe Target
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 2%

---


# Nätverk{#network}

Du kan skapa målgrupper baserat på nätverksinformation.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Network]**.
1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

   * **Internet-leverantör:** En internetleverantör är en organisation som ger sina prenumeranter tillgång till internet, vanligen med en månads- eller årsavgift. Många internetleverantörer erbjuder ytterligare tjänster, som webbhotell eller e-post. Fältet Internet-leverantör är antingen en kommersiell Internet-leverantör (till exempel Comcast eller TimeWarner) eller en annan enhet som ett företag eller en utbildningsinstitution.

      Nedan följer några exempel på vanliga Internet-leverantörer i USA:

      | Populärt namn | ISP-namn | Domännamn | Exempel på IP-adress |
      |---|---|---|---|
      | Cablevision | Cablevision Systems Corp. | *.optonline.net | 68.196.130.239 |
      | CenturyLink | Qwest Communications Company, LLC | *.centurylink.net | 64.40.65.0 |
      | Stadskommunikation | Stadskommunikation | *.charter.com | 71.85.225.124 |
      | Comcast | Comcast Cable Communications, Inc. | *.comcast.net | 76.27.24.28 |
      | Cox | Cox Communications Inc. | *cox.net | 68.224.174.22 |
      | Speakeasy | MegaPath Corporation | *.högtaleasy.net | 66.93.240.0 |
      | Time Warner | Time Warner Cable Internet LLC | *.res.rr.com | 72.229.28.185 |
      | Verizon FiOS | MCI Communications Services, Inc. d/b/a Verizon Business | *.fios.verizon.net | 173.68.112.34 |
      | Vivint | Smartrove Inc. | *.vivinttrådlös.net | 170.72.26.105 |
      | AT&amp;T Wireless | AT | *.mycingular.net |  |
      | Sprint Mobile | Sprint Personal Communications Systems | IP-adress |  |
      | T-Mobile | T-Mobile USA, Inc. | IP-adress | 208.54.86.0 |
      | Verizon Wireless | Cellco Parternship DBA Verizon Wireless | *.myvzw.com | 70.195.74.199 |

      >[!NOTE]
      >
      >Använd ISP-namnet, inte det populära namnet, när du riktar dig mot en Internet-leverantör. Se till att du skapar regeln så att den inte är skiftlägeskänslig eller alltid använder gemener.

      Du kan testa ISP- och domännamnsvärdena. [https://www.whoismyisp.](https://www.whoismyisp.org) orgis a good resource for targeting purposes. Du kan använda de exempeladresser som anges i tabellen ovan eller ange egna. Använd sedan parametern `themboxOverride.browserIp= URL` för att efterlikna den IP-adressen.

   * **Domännamn:** Detta är domännamnet för besökarens IP-adress. Det här är inte domännamnet för den webbplats du använder med [!DNL Target]. Det här domännamnet är relaterat till besökarens IP-adress och kallas ibland för ett värdnamn. Det liknar vanligtvis Internet-leverantörens namn. Ibland refererar värdnamnet till äldre namn på företag som har ändrat namn på sin Internet-leverantör men inte domännamnet.
   * **Anslutningshastighet:** Detta är hastigheten på besökarens internetanslutning. Alternativen är: bredband, kabel, dialup, mobile, oc3, oc12, satellit, t1, t2, trådlöst och xdsl.

      Det här fältet baseras på anslutningstypen och inte på själva hastigheten. [!DNL Target] kan inte fastställa den exakta anslutningshastigheten för anslutningar. Bredbandsanslutningstypen används när det inte finns några indikationer på andra anslutningstyper, så det går inte att välja en viss typ.

1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Save]**.

Följande bild visar en målgrupp som riktar sig till besökare som använder AT&amp;T med en anslutningshastighet på [!UICONTROL Mobile].

![Nätverksmål](assets/target_network.png)

## Utbildningsvideo: Skapa målgrupper

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)