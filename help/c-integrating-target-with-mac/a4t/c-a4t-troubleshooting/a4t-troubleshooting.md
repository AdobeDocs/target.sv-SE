---
keywords: analytics tracking server;A4T;analytics segments;report suites;incorrect data;orphaned;sdid;VisitorAPI.js;mboxMCSDID;phantom;unspecified
description: I det här avsnittet beskrivs några vanliga problem som har uppstått när Analytics används som rapportkälla för Target (A4T).
title: Felsöka integreringen med Analytics och Target (A4T)
feature: a4t troubleshooting
subtopic: Multivariate Test
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---


# Felsöka integreringen med Analytics och Target (A4T){#troubleshoot-the-analytics-and-target-integration-a-t}

I det här avsnittet beskrivs några vanliga problem som har uppstått när Analytics används som rapportkälla för Target (A4T).

## Aktiviteter visar inte data i Analytics, utan anges i stället som&quot;unspecified&quot;. {#unspecified}

Det finns flera orsaker till detta:

* Klassificeringen i [!DNL Target] har inte bearbetats fullständigt.

   Klassificeringen tar i allmänhet mellan 24 och 72 timmar att klassificera rapporter efter att de sparats första gången.

* Rapportsviten innehåller inga data, men [!DNL Target] har försökt klassificera träffar. [!DNL Target] kan inte klassificera data förrän den första träffen inträffar.

   Se till att rapportsviten har haft minst en träff.

* Klassificeringsanropet från [!DNL Target] till [!DNL Analytics] misslyckades.

   [Kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du behöver hjälp.

>[!NOTE]
>
>Ibland visas data korrekt i rapporter, men återgår sedan till&quot;ospecificerad&quot; eftersom en ny aktivitet har lagts till som inte har slutfört klassificeringen. Kom ihåg att det i allmänhet tar mellan 24 och 72 timmar att klassificera rapporter efter det att du sparat dem första gången.
>
>Inga data förloras när de listas som&quot;ospecificerade&quot;. Data tilldelas korrekt till lämplig aktivitet eller upplevelse efter att klassificeringen har körts.

## Mina analysdata visar ett uppblåst besöks- eller besökarantal sedan A4T startades. {#section_4BE374E573D44FB7918611699B74F58E}

Mer information finns i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Den beräknade ökningen av intäktsmått visar inte korrekta data. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Information om lyft och förtroende är inte tillgänglig i Analytics. De är dock tillgängliga i Target-rapporterna.

## Aktiviteter visas inte i analysrapporter. {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T-aktiviteter kräver att en analysspårningsserver anges. Se [Använda en Analytics Tracking Server](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) för att se till att Analytics Tracking Server är korrekt konfigurerad.

>[!NOTE]
>
>Om du använder Adobe Analytics som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar en aktivitet om du använder mbox.js version 61 (eller senare) eller at.js version 0.9.1 (eller senare). Mbox.js- eller at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När du skapar en aktivitet kan du lämna [!UICONTROL Tracking Server] fältet tomt på [!UICONTROL Goals & Settings] sidan.

## Mina analyssegment visas inte i Target. {#section_DEE87F1557834F448E99381D3D02EEEF}

Kontrollera att du har rätt behörigheter innan du börjar skapa A4T-aktiviteter:

* Du måste tillhöra webbtjänståtkomstgruppen i Adobe Analytics för att kunna använda Analytics som rapportkälla för Target.
* Du måste vara medlem i en eller flera Experience Cloud-grupper som har tillgång till Analytics och Target.
* Verifiera att Analytics och Target visas i avsnittet Marketing Apps i den vänstra navigeringen.

## Studsfrekvens, studsar och exitvärden visas som positiva i rapporter. {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Detta är ett känt problem.

Även om dessa mätvärden är negativa visas lyften som om de var positiva i Target-rapporterna. Även om du till exempel vill ha en lägre avhoppsfrekvens visas den högre avhoppsfrekvensen som vinnare med den högsta avhoppsfrekvensen. Tänk på dessa och liknande mätvärden och om du hellre vill öka eller minska siffrorna när du fattar beslut baserat på rapporter.

## Rapportsviten som jag behöver visas inte. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

Listan med rapportsviter i [!DNL Target Standard/Premium] är listan med rapportsviter som har konfigurerats för [!DNL Analytics] att vara rapportkälla för [!DNL Target] (A4T). Det innebär att du kanske inte ser alla rapporteringsprogram du har.

Om du använder flera rapportkällor måste rapportsviterna också finnas i standardrapportkälluppsättningen i [!DNL Target] . annars visas inte rapportsviterna.

Om du fortfarande inte ser den rapportserie du söker kan du kontakta [kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att aktivera den.

## Jag ser inte så mycket data i rapporter som förväntat. {#section_75002584FA63456D8D9086172925DD8D}

Granska implementeringen, särskilt på sidor där besökarna är berättigade till upplevelser, och se till att ID:n för kompletterande data matchar i [!DNL Target] och [!DNL Analytics] i samtal.

* **at.js 1.x**: I [!DNL Target] anropet finns det kompletterande ID:t i `mboxMCSDID` parametern. I [!DNL Analytics] anropet finns det kompletterande ID:t i `sdid` parametern.
* **at.js 2.x**: I [!DNL Target] anropet returneras det extra ID:t i HTTP-huvudet som värde för `experienceCloud.analytics.supplementalDataId`. I [!DNL Analytics] anropet finns det kompletterande ID:t i `sdid` parametern.

Det enklaste sättet att undersöka det kompletterande ID:t är att använda Adobe Experience Platform Debugger.

Om du inte har installerat felsökaren läser du [Introduktion till Adobe Experience Platform Debugger](https://docs.adobe.com/content/help/en/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Felsökning](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

Om det inte finns något ytterligare data-ID i [!DNL Target] anropet bekräftar du att [!DNL VisitorAPI.js] filen har lästs in före [!DNL at.js] eller [!DNL mbox.js]. Om det inte finns något ytterligare data-ID i [!DNL Analytics] samtalet bekräftar du att [!DNL Target] samtalet utlöses före [!DNL Analytics] samtalet.

Mer information finns i [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) eller kontakta [kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
