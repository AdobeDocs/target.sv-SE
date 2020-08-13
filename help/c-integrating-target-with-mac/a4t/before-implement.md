---
keywords: Recommendations
description: Flera ändringar görs i datainsamlingsprocessen när Analytics aktiveras som rapportkälla för Target (A4T).
title: Innan du implementerar Adobe Analytics som rapportkälla för Adobe Target (A4T)
feature: a4t implementation
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---


# Innan du implementerar{#before-you-implement}

Flera ändringar sker i datainsamlingsprocessen när du aktiverar [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

Innan du bestämmer dig för att använda den här integreringen ska du granska följande avsnitt och tänka på hur rapportprocesserna påverkas:

## Implementeringskrav {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Innan du kan börja använda A4T måste du begära att ditt konto etableras för integreringen. Använd [det här formuläret](https://www.adobe.com/go/audiences) för att begära etablering.

Den här A4T-integreringen kräver att du implementerar följande biblioteksversioner (eller nyare), beroende på om du vill använda omdirigeringserbjudanden med A4T eller inte:

### Krav krävs om omdirigeringserbjudanden *inte* används med A4T

För den här integreringen krävs att du implementerar följande biblioteksversioner (eller nyare) om du inte planerar att använda omdirigeringserbjudanden med A4T. Ordningen som anges är den ordning som operationerna utförs.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 1.8.0
* [!DNL Adobe Target] (beroende på implementeringen): at.js version 0.9.1 eller mbox.js version 61
* Adobe Analytics: appMeasurement.js version 1.7.0

### Krav krävs för omdirigeringserbjudanden med A4T

Om du vill använda omdirigeringserbjudanden med A4T måste du implementera följande biblioteksversioner (eller nyare). Ordningen som anges är den ordning som operationerna utförs.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 2.3.0
* [!DNL Adobe Target]: at.js version 1.6.2

   **Obs!** Biblioteket mbox.js stöder inte omdirigeringserbjudanden med A4T. Implementeringen måste använda at.js.

* Adobe Analytics: appMeasurement.js version 2.1

Instruktioner för hämtning och distribution finns i [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Saker att känna till innan ni implementerar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Den här integreringen aktiveras för nya aktiviteter när du väljer att använda [!DNL Analytics] som rapportkälla. När du har gjort de implementeringsändringar som beskrivs i det här dokumentet påverkas inte dina befintliga aktiviteter.
* Konfigurationsprocessen [!DNL Analytics] som rapportkälla för [!DNL Target] omfattar flera implementeringssteg, följt av ett provisioneringssteg. Det är en god idé att läsa igenom processen enligt beskrivningen nedan innan du implementerar den. När du har slutfört de här stegen kan du börja använda [!DNL Analytics] som rapportkälla så snart den är aktiverad. Etableringsprocessen kan ta upp till fem arbetsdagar.
* Med det här alternativet [!DNL Visitor ID service] skapas en delad [!DNL Visitor ID] över [!DNL Adobe Experience Cloud]. Även om det inte ersätter [!DNL Target] mboxPC-id eller [!DNL Audience Manager] UUID ersätter det sättet som [!DNL Analytics] identifierar nya besökare på. Om konfigurationen är korrekt bör återkommande [!DNL Analytics] besökare även identifieras via sitt gamla [!DNL Analytics] ID för att förhindra besöksklickning. På samma sätt försvinner inga data för besökarprofilen när du uppgraderar till [!DNL Target] mboxPCid [!DNL Target] eftersom [!DNL Visitor ID service]mboxPCid förblir intakt.
* Den [!DNL Visitor ID service] måste köras före din [!DNL Analytics] - och [!DNL Target] sidkod. Se till att det `VisitorAPI.js` visas ovanför taggarna för alla andra [!DNL Experience Cloud] lösningar.

## Latens {#section_9489BE6FD21641A4844E591711E3F813}

När integreringen är aktiverad kommer du att uppleva ytterligare 5-10 minuters fördröjning på [!DNL Analytics]. Den här fördröjningsökningen gör att data från [!DNL Analytics] och [!DNL Target] kan lagras på samma träff, vilket gör att du kan dela upp aktiviteter per sida och webbplatsavsnitt.

Ökningen återspeglas i alla [!DNL Analytics] tjänster och verktyg, inklusive liveströmmar och realtidsrapportering, och gäller i följande scenarier:

* För liveströmmar, realtidsrapporter och API-begäranden samt aktuella data för trafikvariabler fördröjs bara träffar med ett extra data-ID.
* För aktuella data om konverteringsmått, slutförda data och dataflöden fördröjs alla träffar ytterligare 5-7 minuter.

Observera att latensökningen börjar efter att du har implementerat [!DNL Experience Cloud] besökar-ID-tjänsten, även om du inte har implementerat den här integreringen fullständigt.

## Kompletterande ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

Alla [!DNL Target] anrop som används av en A4T-aktivitet för att leverera innehåll eller registrera målmåttet måste ha en motsvarande [!DNL Analytics] träff som delar samma extra ID för att A4T ska fungera korrekt.

Träffar som innehåller data från [!DNL Analytics] och [!DNL Target] innehåller ett extra data-ID. Du kan se det här ID:t i [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) som `sdid` parameter. Exempel: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Detta ID genereras när som helst när följande kriterier finns på plats:

* Tjänsten för besökar-ID är implementerad
* En version av [!DNL mbox.js] som stöder den här integreringen implementeras.

Kontrollera att det kompletterande ID:t finns i [!DNL Analytics] träffar när du felsöker.

## Loggning av analys på klientsidan {#client-side}

Som standard när at.js, [!DNL Experience Cloud Visitor ID Service]och appMeasurement.js finns på sidan, [!DNL Analytics] [!DNL Target] och sammanfogar händelser korrekt för rapporterings- och analysändamål i bakänden så länge som rätt kompletterande ID finns på sidan, vilket nämns ovan. Du behöver inte hantera och utföra ytterligare åtgärder för att A4T ska fungera korrekt.

Det finns dock situationer då du kanske vill ha större kontroll över när och hur analysdata som är relaterade [!DNL Target] till ska skickas [!DNL Analytics] för rapportering. Ni kanske har ett internt analysverktyg som ni kan använda internt, men också vill skicka analysdata till [!DNL Analytics] via den interna analysprodukten så att andra medlemmar i organisationen kan fortsätta att använda [!DNL Analytics] som en visuell rapportkälla. Se [steg 7: Se at.js eller mbox.js på alla webbplatssidor](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) i *Analytics for Target Implementation* för mer information.
