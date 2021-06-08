---
keywords: Recommendations
description: Lär dig implementeringskraven för Analytics för [!DNL Target] (A4T) och vad du bör tänka på innan du implementerar den här integreringen.
title: Vad ska jag veta innan jag implementerar A4T?
feature: Analyser för mål (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 4c696f55f56a116cff61c2c307f750e72cc0107c
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 0%

---

# Innan du implementerar Analytics för Target (A4T) med at.js

Flera ändringar sker i datainsamlingsprocessen när du aktiverar [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

Innan du bestämmer dig för att använda den här integreringen ska du gå igenom följande avsnitt och fundera över vilken inverkan dina rapporteringsprocesser har.

>[!NOTE]
>
>Den här artikeln gäller endast för at.js-implementeringar.

## Implementeringskrav {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Innan du kan börja använda A4T måste du begära att ditt konto har etablerats för integreringen. Använd formuläret [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences) för att begära att få etableras.

Den här A4T-integreringen kräver att du implementerar följande biblioteksversioner (eller nyare), beroende på om du vill använda omdirigeringserbjudanden med A4T eller inte:

### Krav krävs om *inte* använder omdirigeringserbjudanden med A4T

För den här integreringen krävs att du implementerar följande biblioteksversioner (eller nyare) om du inte planerar att använda omdirigeringserbjudanden med A4T. Ordningen som anges är den ordning som operationerna utförs.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 1.8.0
* [!DNL Adobe Target] (beroende på implementeringen): at.js version 0.9.1 eller mbox.js version 61
* Adobe Analytics: appMeasurement.js version 1.7.0

### Krav krävs för omdirigeringserbjudanden med A4T

Om du vill använda omdirigeringserbjudanden med A4T måste du implementera följande biblioteksversioner (eller nyare). Ordningen som anges är den ordning som operationerna utförs.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 2.3.0

   **Obs!**  at.js 1.8.0 eller senare fungerar inte längre med Visitor API-versioner som är äldre än 2.5.0 för att skicka  [!DNL Adobe Audience Manager] (AAM) parametrar.

* [!DNL Adobe Target]: at.js version 1.6.2

   **Obs**: Biblioteket mbox.js stöder inte omdirigeringserbjudanden med A4T. Implementeringen måste använda at.js.

* Adobe Analytics: appMeasurement.js version 2.1

Instruktioner för hämtning och distribution finns i [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Saker att känna till innan ni implementerar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Den här integreringen aktiveras för nya aktiviteter när du väljer att använda [!DNL Analytics] som rapportkälla. När du har gjort de implementeringsändringar som beskrivs i det här dokumentet påverkas inte dina befintliga aktiviteter.
* Processen att konfigurera [!DNL Analytics] som rapportkälla för [!DNL Target] innehåller flera implementeringssteg, följt av ett provisioneringssteg. Det är en god idé att läsa igenom processen enligt beskrivningen nedan innan du implementerar den. När du har slutfört de här stegen kan du använda [!DNL Analytics] som rapportkälla när den är aktiverad. Etableringsprocessen kan ta upp till fem arbetsdagar.
* [!DNL Visitor ID service] skapar en delad [!DNL Visitor ID] över [!DNL Adobe Experience Cloud]. Även om det inte ersätter mboxPC-id:t [!DNL Target] eller UUID:t för [!DNL Audience Manager] ersätter det sättet [!DNL Analytics] identifierar nya besökare. Om konfigurationen är korrekt bör återkommande [!DNL Analytics]-besökare även identifieras via deras gamla [!DNL Analytics]-ID. På samma sätt försvinner inga [!DNL Target]-data för besökarprofilen när du uppgraderar till [!DNL Visitor ID service] eftersom mboxPCid förblir intakt.[!DNL Target]
* [!DNL Visitor ID service] måste köras före sidkoden för [!DNL Analytics] och [!DNL Target]. Kontrollera att `VisitorAPI.js` visas ovanför taggarna för alla andra [!DNL Experience Cloud]-lösningar.

## Latens {#section_9489BE6FD21641A4844E591711E3F813}

När integreringen är aktiverad kommer du att uppleva ytterligare 5-10 minuters fördröjning i [!DNL Analytics]. Den här fördröjningsökningen gör att data från [!DNL Analytics] och [!DNL Target] kan lagras på samma träff, vilket gör att du kan dela upp aktiviteter per sida och webbplatsavsnitt.

Ökningen återspeglas i alla [!DNL Analytics]-tjänster och -verktyg, inklusive live-stream och realtidsrapportering, och gäller i följande scenarier:

* För liveströmmar, realtidsrapporter och API-begäranden samt aktuella data för trafikvariabler fördröjs bara träffar med ett extra data-ID.
* För aktuella data om konverteringsmått, slutförda data och dataflöden fördröjs alla träffar ytterligare 5-7 minuter.

Fördröjningen börjar när du har implementerat besökar-ID-tjänsten [!DNL Experience Cloud], även om du inte har implementerat den här integreringen fullständigt.

## Kompletterande ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

Alla [!DNL Target]-anrop som används av en A4T-aktivitet för att leverera innehåll eller registrera målmåttet måste ha en motsvarande [!DNL Analytics]-träff som delar det kompletterande ID:t för A4T för att fungera korrekt.

Träffar som innehåller data från [!DNL Analytics] och [!DNL Target] innehåller ett extra data-ID. Du kan se detta ID i [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) som `sdid`-parametern. Exempel: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Detta ID genereras när som helst när följande kriterier finns på plats:

* Tjänsten för besökar-ID är implementerad
* En version av [!DNL mbox.js] som stöder den här integreringen är implementerad.

När [felsökning](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) inträffar måste du kontrollera att det extra ID:t finns på [!DNL Analytics] träffar.

## Loggning av analys på klientsidan {#client-side}

Om at.js är [!DNL Experience Cloud Visitor ID Service] och appMeasurement.js på sidan [!DNL Analytics] och [!DNL Target] sammanfogar händelser korrekt för rapportering- och analyssyften i bakänden så länge som rätt kompletterande ID inkluderas från sidan. Du behöver inte hantera och utföra några ytterligare åtgärder för att A4T ska fungera korrekt.

Det finns fall där du kanske vill ha större kontroll över när och hur analysdata som är relaterade till [!DNL Target] ska skickas till [!DNL Analytics] för rapportering. Du kan ha ett internt analysverktyg som du använder internt. Men du vill också skicka analysdata till [!DNL Analytics] via den interna analysprodukten så att andra medlemmar i organisationen kan fortsätta använda [!DNL Analytics] som en visuell rapportkälla. Se [Steg 7: Mer information finns i at.js eller mbox.js på alla webbplatssidor](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) i *Analytics for Target Implementation*.

## Delade målgrupper

När du fyller i [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences) ska du vara medveten om följande viktiga information om alternativet [!UICONTROL Shared Audiences] som listas under &quot;[!UICONTROL For which capabilities are you requesting provisioning]?&quot;

![Formulär för förfrågningar](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

När du begär [!UICONTROL Shared Audiences] aktiverar du [!UICONTROL Target] och [!UICONTROL Adobe Audience Manager] (AAM) för att dela information, i det här fallet målgrupper.

>[!IMPORTANT]
>
>Integrationen mellan [!UICONTROL Target] och AAM medför extra kostnader. Du faktureras för varje [!UICONTROL Target]-samtal i AAM.
