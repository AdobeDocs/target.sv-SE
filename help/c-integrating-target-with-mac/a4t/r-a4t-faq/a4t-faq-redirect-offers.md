---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;redirect;redirect offer;adobe-mc-sdid;adobe_mc_ref
description: Hitta svar på frågor om hur du använder omdirigeringserbjudanden när du använder Analytics för [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] aktiviteter.
title: Var hittar jag frågor om omdirigeringserbjudanden med A4T?
feature: Analyser för mål (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 0%

---

# Omdirigeringserbjudanden - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om hur du använder omdirigeringserbjudanden när du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Har Analytics för Adobe Target (A4T) stöd för omdirigeringserbjudanden? {#section_46B8B03ED4D542C6AD875F5F61176298}

Ja, om implementeringen använder [!DNL at.js]. Implementeringen måste dock uppfylla de minimikrav som anges nedan för att du ska kunna använda [omdirigeringserbjudanden](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) i aktiviteter där Analytics används som rapportkälla.

>[!NOTE]
>
>Det finns ett känt fel som gör att ett begränsat antal kunder använder omdirigeringar med A4T för att se en högre procentandel av antalet träffar som inte sammanställts. Se [Kända fel och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Vilka är minimikraven för omdirigeringserbjudanden med A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Implementeringen måste uppfylla följande minimikrav:

* Experience Cloud Visitor ID-tjänst: [!DNL visitorAPI.js] version 2.3.0 eller senare.
* Adobe Analytics: [!DNL appMeasurement.js] version 2.1.
* Adobe Target: [!DNL at.js] version 1.6.2 eller senare.

   Biblioteket [!DNL mbox.js] stöder inte omdirigeringserbjudanden med A4T. Implementeringen måste använda [!DNL at.js].

De tre biblioteken måste finnas på både sidan med omdirigeringserbjudandet och den sida som besökaren omdirigeras till.

## Varför finns det ibland avvikelser i data mellan A4T och Analytics?

Vissa dataavvikelser förväntas. Mer information finns i [Förväntade datavariationer mellan Target och Analytics när A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md) används och inte.

## Varför räknas ibland sidvisningar på originalsidan och på omdirigeringssidan? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

När du använder at.js version 1.6.3 eller senare är det inte något problem att räkna sidvisningar på båda sidorna. Detta konkurrensvillkor påverkar endast kunder som använder tidigare versioner. Target-teamet har två versioner av at.js: den aktuella versionen och den senaste versionen. Uppgradera at.js efter behov för att kontrollera att du kör en [version](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) som stöds.

Om du använder en tidigare version av at.js som inte stöds finns det en risk för att ett konkurrensvillkor kan uppstå som kan få Analytics-anropet att utlösas innan omdirigeringen körs på den första sidan. Detta kan leda till att sidvisningar på den ursprungliga sidan och på omdirigeringssidan räknas. Detta resulterar i en extra sidvy på den första sidan, där besökaren aldrig riktigt &quot;såg&quot; den första sidan.

Vi rekommenderar att du använder den formulärbaserade dispositionen för att skapa en omdirigeringsaktivitet för att öka hastigheten på omdirigeringen på sidan på grund av var koden körs på sidan. Du bör också skapa ett omdirigeringserbjudande för varje upplevelse, även standardupplevelsen, där omdirigeringen skulle returnera originalsidan. Genom att skapa ett omdirigeringserbjudande för varje upplevelse säkerställer du att det sker i alla upplevelser om en felräkning inträffar. Rapportering och analys är fortfarande giltiga för testet.

En anledning till att du kanske vill använda omdirigeringserbjudanden för alla upplevelser i aktiviteten, inklusive standardupplevelsen (kontrollen), är att ange samma villkor för alla upplevelser. Om till exempel standardupplevelsen inte har något omdirigeringserbjudande, men de andra upplevelserna har omdirigeringserbjudanden, har upplevelsen utan omdirigeringserbjudandet en inneboende fördel. Omdirigeringserbjudanden rekommenderas endast för tillfälliga scenarier, till exempel testning. Omdirigeringserbjudanden rekommenderas inte för permanenta scenarier, som personalisering. När du har bestämt vinnaren bör du ta bort omdirigeringen för att förbättra sidladdningsprestanda.

Mer information om det här problemet finns i informationen om omdirigeringserbjudanden i [Kända fel](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Kan jag använda omdirigeringserbjudanden med A4T om jag använder JavaScript-biblioteket mbox.js? {#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

Biblioteket [!DNL mbox.js] stöder inte omdirigeringserbjudanden med A4T. Implementeringen måste använda [!DNL at.js].

## Stöds både Visual Experience Composer (VEC) och Form-Based Experience Experience Composer? {#section_FDA26FE7909B48539DA770559E687677}

Ja, båda dispositionerna stöds så länge du använder de inbyggda omdirigeringserbjudandena.

Om du använder din egen anpassade kod för omdirigeringen måste du se till att du fyller i de två nya parametrar som är associerade med omdirigerings-URL:er ( `adobe_mc_sdid` och `adobe_mc_ref`, som förklaras nedan).

## Vilka nya frågesträngsparametrar läggs till i omdirigerings-URL:erna? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

Följande frågesträngsparametrar är associerade med omdirigeringserbjudanden:

| Parameter | Beskrivning |
|--- |--- |
| `adobe_mc_sdid` | Parametern `adobe_mc_sdid` skickar SDID (Additional Data Id) och Experience Cloud Org Id från standardsidan till den nya sidan. Med dessa ID:n kan A4T&quot;sy ihop&quot; Target-begäran på standardsidan med Analytics-begäran på den nya sidan. |
| `adobe_mc_ref` | Parametern `adobe_mc_ref` skickar den refererande URL-adressen för standardsidan till den nya sidan. När Analytics används med AppMeasurement.js version 2.1 (eller senare) används det här parametervärdet som den refererande URL:en på den nya sidan. |

Parametrarna läggs automatiskt till i omdirigerings-URL:erna när de inbyggda omdirigeringserbjudandena i VEC och formulärbaserad Experience Composer används när besökar-ID-tjänsten implementeras på sidan. Om du använder din egen anpassade omdirigeringskod i VEC eller formulärbaserad disposition måste du se till att skicka de här parametrarna med din anpassade kod.

## Mina webbservrar tar bort de här parametrarna från mina URL:er, vad ska jag göra? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

Samarbeta med IT-avdelningen för att få dessa parametrar ( `adobe_mc_sdid` och `adobe_mc_ref`) tillåtslista.

## Vad händer om jag inte använder A4T med min omdirigeringsaktivitet och inte vill att de här extra parametrarna ska läggas till i mina URL:er? {#section_9E608D75FF9349FE96C65FEDD7539F45}

Använd en anpassad kodad omdirigering om:

* Du använder inte A4T med omdirigeringsaktiviteten
* Tjänsten för besökar-ID är implementerad
* Du vill inte att de här parametrarna ska läggas till automatiskt i dina URL-adresser

Som god praxis kanske du vill behålla parametern `adobe_mc_ref` i URL:en för att kunna rapportera referensinformationen till [!DNL Analytics] korrekt.

## Varför är parametrarna adobe_mc_ref och adobe_mc_sdid dubbelt så URL kodade i min implementering? {#section_5EFE5F012B944C40865731EA18E7E79E}

Om du använder A4T och omdirigeringserbjudanden lägger Target till parametrarna `adobe_mc_ref` och `adobe_mc_sdid` till URL:en. Dessa värden är redan URL-kodade. För det mesta fungerar allt som förväntat, men vissa kunder kan ha belastningsutjämnare eller WEB-servrar som försöker koda frågesträngsparametrarna en gång till.

På grund av den här dubbla kodningen när besökar-API:t försöker avkoda `adobe_mc_sdid`-värdet kan det inte extrahera SDID-värdet och generera ett nytt SDID. Den här processen leder till att felaktiga SDID-värden skickas till Target och Analytics, och du ser en ojämn delning för omdirigeringar i Analytics-rapporter.

Adobe rekommenderar att du pratar med IT-avdelningen för att säkerställa att `adobe_mc_ref` och `adobe_mc_sdid` är tillåtslista så att dessa värden inte förändras på något sätt.

## Varför ska den refererande URL:en skickas till den nya sidan? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Anta att en besökare klickar på en länk på [!DNL `www.google.com`] till din hemsida (`www.mysite.com/index.html`) där en omdirigeringsaktivitet är aktiv och sedan omdirigeras till en ny sida (`www.mysite.com/index2.html`).

Tidigare skulle [!DNL Analytics]-begäran på den nya sidan rapportera den refererande URL:en [!DNL `www.mysite.com/index.html`] i stället för [!DNL `www.google.com`]. Detta orsakade felaktig rapportering i [!DNL Analytics] som är kopplad till de refererande URL:erna (till exempel marknadsföringskanalrapporter). Rapporterna hade förlorat det faktum att du kom till webbplatsen från [!DNL `www.google.com`].

Med [!DNL at.js] version 0.9.6 (eller senare) och [!DNL AppMeasurement.js] 2.1 (eller senare) rapporterar [!DNL Analytics]-begäran på den nya sidan den refererande URL:en [!DNL `www.google.com`].

## Kan jag använda anpassade omdirigeringserbjudanden/HTML? {#section_E49F9A83A286488C8F1098A040203D7E}

Nej, du måste använda ett inbyggt omdirigeringserbjudande för aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T). Från [!DNL Target]-perspektivet är HTML-erbjudanden ogenomskinliga: [!DNL Target] vet inte om en viss del av HTML innehåller JavaScript som initierar en omdirigering.

## Har [!DNL Adobe Experience Platform Web SDK] stöd för omdirigeringserbjudanden för A4T? {#platform}

Följande vanliga frågor och svar innehåller mer information om hur du använder A4T och omdirigeringserbjudanden med [!DNL Platform Web SDK].

>[!NOTE]
>
>Stöd för A4T i en [!DNL Adobe Experience Platform Web SDK]-implementering som beskrivs i den här artikeln är schemalagd att vara tillgänglig med version 2.5.0 av [!DNL Platform Web SDK] (24 maj 2021).

### Har Analytics for Target (A4T) stöd för omdirigeringserbjudanden?

Ja, A4T via Platform Web SDK har stöd för [omdirigeringserbjudanden](/help/c-experiences/c-manage-content/offer-redirect.md).

### Stöds [!UICONTROL Visual Experience Composer] (VEC) och [!UICONTROL Form-Based Experience Composer]?

Ja, både [[!UICONTROL Visual Experience Composer]](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) och [[!UICONTROL Form-Based Experience Composer]](/help/c-experiences/form-experience-composer.md) stöds om du använder inbyggda omdirigeringserbjudanden.

### Kan jag använda anpassade omdirigeringserbjudanden/HTML med [!DNL Platform Web SDK]?

Nej, du måste använda ett inbyggt omdirigeringserbjudande för aktiviteter som använder A4T. Från [!DNL Target]-perspektivet är HTML-erbjudanden ogenomskinliga. [!DNL Target] kan inte veta att en viss del av HTML innehåller JavaScript som initierar en omdirigering.
