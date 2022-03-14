---
keywords: analysspårningsserver;A4T;analyssegment;rapportsviter;felaktiga data;överblivna;gjorde;VisitorAPI.js;mboxMCSDID;phantom;ospecificerad
description: Utforska vanliga problem som kunder har stött på när de använder Analytics för [!DNL Target] (A4T).
title: Hur felsöker jag analysen och [!DNL Target] Integrering (A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 0%

---

# Felsöka analysen och [!DNL Target] integrering (A4T)

Det här avsnittet handlar om några vanliga problem som har uppstått vid användning [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Aktiviteter visar inte data i Analytics, utan anges i stället som&quot;unspecified&quot;. {#unspecified}

Det finns flera orsaker till varför data visas som&quot;ospecificerade&quot;:

* Klassificering i [!DNL Target] har inte bearbetats fullständigt.

   Klassificeringen tar i allmänhet från 24 till 72 timmar att klassificera rapporter efter att de sparats första gången.

* Rapportsviten innehåller inga data, men [!DNL Target] har försökt klassificera träffar. [!DNL Target] kan inte klassificera data förrän den första träffen inträffar.

   Se till att rapportsviten har haft minst en träff.

* Klassificeringsanropet från [!DNL Target] till [!DNL Analytics] misslyckades.

   [Kontakta kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du behöver hjälp.

Om du bryter ned raden &quot;unspecified&quot; (ospecificerad) med dimensionen &quot;Analytics for Target&quot; (Analyser för mål) och den inte består av några aktivitets-ID:n, innebär det att allt klassificeras korrekt. Om aktivitets-ID finns med i listan fungerar det som en indikation på ett klassificeringsproblem.

>[!NOTE]
>
>Ibland visas data korrekt i rapporter, men återgår sedan till&quot;ospecificerad&quot; eftersom en ny aktivitet har lagts till som inte har slutfört klassificeringen. Kom ihåg att det i allmänhet tar mellan 24 och 72 timmar att klassificera rapporter efter första sparandet.
>
>Inga data förloras när de listas som&quot;ospecificerade&quot;. Data tilldelas korrekt till lämplig aktivitet eller upplevelse efter att klassificeringen har körts.

## A4T-aktivitetsrapporter innehåller en rad med många&quot;ospecificerade&quot; händelser. {#added_unspecified_events}

Det kan finnas en[!UICONTROL Unspecified]&quot; som visas i din rapport, beroende på vilka mätvärden du använder för att visa data med.

Vanligtvis visas den här raden om du väljer ett vanligt mått i rapporten som inte är [!DNL Target]-specific (till exempel [!UICONTROL Page Views], [!UICONTROL Visits], [!UICONTROL Unique Visitors]och så vidare). I det här fallet [!UICONTROL “Unspecified”] raden innehåller alla [!UICONTROL Page Views], [!UICONTROL Visits]och [!UICONTROL Unique Visitors] som inte är kopplade till [!DNL Target] verksamhet.

Den raden har inga [!DNL Target]-associerad information (t.ex. inga besökare, besök eller visningar). Mer information finns i [&quot;Ospecificerad&quot;, &quot;Ingen&quot;, &quot;Annan&quot; och &quot;Okänd&quot; vid rapportering](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) i *Tekniska anteckningar för analyser*.

Om du väljer en [!DNL Target]-specifika mätvärden i rapporten, som [!UICONTROL “Unspecified”] raden visas inte. Det enda sättet att undvika detta i betänkandet är att sätta upp en [!DNL Target] anropa varje begäran som skickas från den sidan, som inte är vanlig eller nödvändig.

## Mina analysdata visar ett uppblåst besöks- eller besökarantal sedan A4T startades. {#section_4BE374E573D44FB7918611699B74F58E}

Mer information finns i [Minimera antalet uppblåsta besök och besökare i A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Den beräknade ökningen av intäktsmått visar inte korrekta data. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Information om lyft och förtroende är inte tillgänglig i Analytics. De är dock tillgängliga i Target-rapporterna.

## Aktiviteter visas inte i analysrapporter. {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T-aktiviteter kräver att en analysspårningsserver anges. Se [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) för att säkerställa att Analytics Tracking Server är korrekt konfigurerad.

>[!NOTE]
>
>Du behöver inte ange en spårningsserver när du skapar en aktivitet om du använder at.js version 0.9.1 (eller senare). at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När du skapar en aktivitet kan du lämna [!UICONTROL Tracking Server] fältet är tomt på [!UICONTROL Goals & Settings] sida.

## Mina analyssegment visas inte i Target. {#section_DEE87F1557834F448E99381D3D02EEEF}

Kontrollera att du har rätt behörigheter innan du börjar skapa A4T-aktiviteter:

* Tillhör webbtjänståtkomstgruppen i Adobe Analytics för att kunna använda Analytics som rapportkälla för Target
* Bli medlem i en eller flera Experience Cloud-grupper som har tillgång till Analytics och Target.
* Verifiera att Analytics och Target visas i avsnittet Marketing Apps i den vänstra navigeringen.

## Studsfrekvens, studsar och exitvärden visas som positiva i rapporter. {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Dessa mätvärden visas som positiva i rapporter och är kända.

Även om dessa mätvärden är negativa visas lyften som om de var positiva i Target-rapporterna. Även om du till exempel vill ha en lägre avhoppsfrekvens visas den högre avhoppsfrekvensen som vinnare med den högsta avhoppsfrekvensen. Tänk på dessa och liknande mätvärden och om du hellre vill öka eller minska siffrorna när du fattar beslut baserat på rapporter.

## Rapportsviten som jag behöver visas inte. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

Listan med rapportsviter som visas i [!DNL Target Standard/Premium] är listan med rapportsviter som har konfigurerats för [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T). Du kanske inte ser alla rapporteringsprogram du har.

Om du använder flera rapportkällor måste rapportsviterna finnas i standardrapportkälluppsättningen i [!DNL Target] också. Om rapportsviterna inte finns i standardrapportkällan visas inte rapportsviterna.

Om du fortfarande inte ser den rapportserie du söker kan du kontakta [Kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att aktivera det.

## Jag ser inte så mycket data i rapporter som förväntat. {#section_75002584FA63456D8D9086172925DD8D}

Granska implementeringen, särskilt på sidor där besökarna är berättigade till upplevelser, och se till att ID:n för kompletterande data matchar i [!DNL Target] och [!DNL Analytics] samtal.

* **at.js 1.x**: I [!DNL Target] call, the additional ID is contained in the `mboxMCSDID` parameter. I [!DNL Analytics] call, the additional ID is contained in the `sdid` parameter.
* **at.js 2.x**: I [!DNL Target] anrop, returneras det extra ID:t i HTTP-huvudet som värdet för `experienceCloud.analytics.supplementalDataId`. I [!DNL Analytics] call, the additional ID is contained in the `sdid` parameter.

Det enklaste sättet att undersöka det kompletterande ID:t är att använda Adobe Experience Platform Debugger.

Om du inte har installerat felsökaren kan du läsa [Introduktion till Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Felsökning](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

Om det inte finns något ytterligare data-ID i [!DNL Target] ring, bekräfta att [!DNL VisitorAPI.js] filen läses in innan [!DNL at.js]. Om det inte finns något ytterligare data-ID i [!DNL Analytics] ring, bekräfta att [!DNL Target] anrop före [!DNL Analytics] ring.

Mer information finns i [Analyser för målinriktad implementering](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) eller kontakt [Kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
