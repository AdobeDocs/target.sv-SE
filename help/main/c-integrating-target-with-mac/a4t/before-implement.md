---
keywords: Recommendations
description: Lär dig implementeringskraven för Analytics för [!DNL Target] (A4T) och vad du bör tänka på innan du implementerar den här integreringen.
title: Vad ska jag veta innan jag implementerar A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 0%

---

# Innan du implementerar Analytics för Target (A4T) med at.js

Flera ändringar görs i datainsamlingsprocessen när du aktiverar [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

Innan du bestämmer dig för att använda den här integreringen ska du gå igenom följande avsnitt och fundera över vilken inverkan dina rapporteringsprocesser har.

>[!NOTE]
>
>Den här artikeln gäller endast för at.js-implementeringar.

## Implementeringskrav {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Innan du kan börja använda A4T måste du begära att ditt konto har etablerats för integreringen. Använd [Marketing Cloud integrations Provisioning Form](https://www.adobe.com/go/audiences) för att begära att få etableras.

Den här A4T-integreringen kräver att du implementerar följande biblioteksversioner (eller nyare), beroende på om du vill använda omdirigeringserbjudanden med A4T eller inte.

>[!NOTE]
>
>Följande krav listar *minimum* versioner av at.js krävs för att implementera A4T. The [!DNL Target] teamet har bara två versioner av [!DNL at.js]- den aktuella versionen och den senaste versionen. Uppgradera [!DNL at.js] vid behov för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns i [at.js Versionsinformation](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

### Krav krävs om *not* använda omdirigeringserbjudanden med A4T

För den här integreringen krävs att du implementerar följande biblioteksversioner (eller nyare) om du inte planerar att använda omdirigeringserbjudanden med A4T. Ordningen som anges är den ordning som operationerna utförs.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 1.8.0
* [!DNL Adobe Target]: at.js version 0.9.1
* Adobe Analytics: appMeasurement.js version 1.7.0

Mer information om hur du implementerar A4T med [!DNL Platform Web SDK], se [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}.

### Krav krävs för omdirigeringserbjudanden med A4T

Om du vill använda omdirigeringserbjudanden med A4T måste du implementera följande biblioteksversioner (eller nyare). Ordningen som anges är den ordning som operationerna utförs.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0+ och at.js 2.x+ fungerar inte längre med Visitor API-versioner som är äldre än 2.5.0 för att skicka Adobe Audience Manager-parametrar (AAM).

* [!DNL Adobe Target]: at.js version 1.6.2

* Adobe Analytics: appMeasurement.js version 2.1

Instruktioner för hämtning och distribution finns i [Analyser för målinriktad implementering](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Mer information om hur du implementerar A4T med [!DNL Platform Web SDK], se [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}.

## Saker att känna till innan ni implementerar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Den här integreringen aktiveras för nya aktiviteter när du väljer att använda [!DNL Analytics] som rapportkälla. När du har gjort de implementeringsändringar som beskrivs i det här dokumentet påverkas inte dina befintliga aktiviteter.
* Konfigurationsprocessen [!DNL Analytics] som rapportkälla för [!DNL Target] innehåller flera implementeringssteg, följt av ett provisioneringssteg. Det är en god idé att läsa igenom processen enligt beskrivningen nedan innan du implementerar den. När du har utfört de här stegen är du redo att använda [!DNL Analytics] som rapportkälla när den är aktiverad för dig. Etableringsprocessen kan ta upp till fem arbetsdagar.
* The [!DNL Visitor ID service] skapar en delad [!DNL Visitor ID] över [!DNL Adobe Experience Cloud]. Även om den inte ersätter [!DNL Target] mboxPC-id eller [!DNL Audience Manager] UUID ersätter det sättet [!DNL Analytics] identifierar nya besökare. Om konfigurationen är korrekt returneras [!DNL Analytics] besökarna bör också identifieras via sina gamla [!DNL Analytics] ID. På samma sätt, eftersom [!DNL Target] mboxPCid förblir intakt, nej [!DNL Target] besökarprofildata förloras när du uppgraderar till [!DNL Visitor ID service].
* The [!DNL Visitor ID service] måste köras innan [!DNL Analytics] och [!DNL Target] sidkod. Se till att `VisitorAPI.js` visas ovanför taggarna för alla andra [!DNL Experience Cloud] lösningar.

## Latens {#section_9489BE6FD21641A4844E591711E3F813}

När integreringen är aktiverad kommer du att uppleva ytterligare 5-10 minuters fördröjning på [!DNL Analytics]. Den här latensökningen tillåter data från [!DNL Analytics] och [!DNL Target] som ska lagras på samma träff, vilket gör att du kan dela upp aktiviteter per sida och webbplatsavsnitt.

Ökningen återspeglas i alla [!DNL Analytics] tjänster och verktyg, inklusive live-stream och realtidsrapportering, och gäller i följande scenarier:

* För liveströmmar, realtidsrapporter och API-begäranden samt aktuella data för trafikvariabler fördröjs bara träffar med ett extra data-ID.
* För aktuella data om konverteringsmått, slutförda data och dataflöden fördröjs alla träffar ytterligare 5-7 minuter.

Latensökningen börjar när du har implementerat [!DNL Experience Cloud] besökar-ID-tjänst, även om du inte har implementerat den här integreringen fullständigt.

## Kompletterande ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

Alla [!DNL Target] anrop som används av en A4T-aktivitet för att leverera innehåll eller registrera målmåttet måste ha en motsvarande [!DNL Analytics] som delar det extra ID:t för A4T så att det fungerar som det ska.

Träffar som innehåller data från [!DNL Analytics] och [!DNL Target] innehåller ett extra data-ID. Du kan se detta ID i [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) som `sdid` parameter. Exempel: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Detta ID genereras när som helst när följande kriterier finns på plats:

* Tjänsten för besökar-ID är implementerad

När [felsökning](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)måste du bekräfta att det kompletterande ID:t finns på [!DNL Analytics] träffar.

## Loggning av analys på klientsidan {#client-side}

Om at.js [!DNL Experience Cloud Visitor ID Service]och appMeasurement.js finns på sidan, [!DNL Analytics]och [!DNL Target] Sammanfogar händelser korrekt för rapportering- och analysändamål i bakänden så länge som rätt kompletterande ID inkluderas från sidan. Du behöver inte hantera och utföra några ytterligare åtgärder för att A4T ska fungera korrekt.

Det finns tillfällen då du kanske vill ha större kontroll över när och hur analysdata som är relaterade till [!DNL Target] till [!DNL Analytics] för rapportering. Du kan ha ett internt analysverktyg som du använder internt. Men du vill också skicka analysdata till [!DNL Analytics] via den interna analysprodukten så att andra medlemmar i organisationen kan fortsätta använda [!DNL Analytics] som en visuell rapportkälla. Se [Steg 7: Referens vid .js på alla webbplatssidor](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Analyser för målinriktad implementering* för mer information.

## Delade målgrupper

När du fyller i [Marketing Cloud integrations Provisioning Form](https://www.adobe.com/go/audiences)bör du vara medveten om följande viktiga information om [!UICONTROL Shared Audiences] som anges under &quot;[!UICONTROL For which capabilities are you requesting provisioning]?&quot;

![Formulär för förfrågningar](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

När du begär [!UICONTROL Shared Audiences]aktiverar du [!UICONTROL Target] och [!UICONTROL Adobe Audience Manager] AAM) att utbyta information, i detta fall målgrupper.

>[!IMPORTANT]
>
>Integrationen mellan [!UICONTROL Target] och AAM kostar mer. Du faktureras för varje [!UICONTROL Target] ringa AAM.
