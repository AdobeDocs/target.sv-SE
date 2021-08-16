---
keywords: serversida;serversida;sdk;sdk;on-device;decisioning;on device;ondevice;zero latency;latency;near-zero;node.js
description: Lär dig hur du använder enhetsspecifik decimering för att cachelagra dina [!DNL Target] A/B- och MVT-aktiviteter på servern för att utföra minnesbaserad decimering vid nästan noll latens.
title: Vad är On-Device Decision?
feature: Implementera serversidan
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: fe70f357e2298f1656d713aae5fae800e6775d64
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Enhetsbeslut

Med enhetsbaserad beslutsfattande kan du cachelagra dina [!DNL Adobe Target] [!UICONTROL A/B Test]- och [!UICONTROL Experience Targeting] (XT)-aktiviteter på servern och utföra minnesbaserad decimering med nästan noll latens, utan att blockera nätverksbegäranden till [!DNL Adobe Target] Edge Network.

Mer information finns i [Introduktion till enhetsbeslut](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) i *[dokumentationen för Adobe Target SDK](https://adobetarget-sdks.gitbook.io/docs/)*.

## Webbseminarium: Anpassa och testa vid nolltidsfördröjning med beslut på enheten från [!DNL Adobe Target]

Nu mer än någonsin har marknadsförare, produktägare och utvecklare fått i uppgift att optimera den övergripande kundupplevelsen på webbplatser, i appar och på alla andra sätt de har kontakt med sina kunder. Det finns inte tillräckligt med flera verktyg med vattentäta skott och komplicerade implementeringar.

I det här inspelade webbinariet diskuterar [!DNL Adobe Target] produktexperter hur flyttande beslut om optimering av kritiska upplevelser på enheter som körs lokalt med nästan ingen fördröjning kan öppna dörrar för spännande nya användningsfall samtidigt som webbplatsens prestanda förbättras för dina kunder.

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## God praxis

Adobe rekommenderar följande metodtips när du använder enhetsbeslut:

### Bästa tillvägagångssätt vid beslut är &quot;på enheten&quot; {#best-practices-on-device}

När du använder&quot;på enheten&quot; som beslutsmetod hämtas artefakten när besökaren läser in webbsidan för första gången. Alla aktivitetskvalifikationer som behöver göras på första sidan läses in (inget cacheminne) inträffar först när artefakten har hämtats helt. Det finns vissa tips du kan följa för att se till att aktivitetskvalifikationerna sker snabbt för en ny anonym besökare.

* Inaktivera aktiviteter som inte ska ingå i artefakten och som kan användas på en enhet.
* Om du har [!DNL Target Premium] kan du använda [egenskaper/arbetsytor](/help/administrating-target/c-user-management/property-channel/property-channel.md) för att skapa olika artefaktfiler för olika arbetsytor.
* Om dina artefaktfiler blir mycket stora av legitima skäl kan du använda den&quot;hybridmetoden&quot; för beslut. Med den här metoden kan du hämta artefakten parallellt och alla [!DNL Target] API-anrop går över tråden tills artefakten har hämtats. Läs det bästa avsnittet [praxis om &quot;Hybrid&quot;-beslutsläge](#best-practices-hybrid) nedan om du vill veta mer om den här metoden.
* Om du har ett Single Page-program (SPA) rekommenderar [!DNL Adobe] att du läser in och initierar at.js innan du läser in programmets JavaScript-huvudfil under den första sidinläsningen. Den här metoden initierar artefaktnedladdningen mycket tidigare, vilket ger en snabbare upplevelserendering.

### Bästa tillvägagångssätt vid beslut av metod är &quot;hybrid&quot; {#best-practices-hybrid}

När du använder&quot;hybrid&quot; som beslutsmetod hämtas artefakten parallellt. Tills artefakten har hämtats går alla [!DNL Target] API-anrop igenom tråden även om &quot;platserna&quot; är kompatibla på enheten. Detta beteende är standard för alla `getOffers()`-anrop och ger bästa prestanda i de flesta situationer. Om du ändrar standardbeteendet för `getOffers()` genom att ställa in `decisioningMethod` på `on-device` bör du följa dessa metodtips för att undvika fel och säkerställa bästa prestanda.

* Om du bestämmer dig för att anropa `getOffers()` med `decisioningMethod` som `on-device` när sidan läses in för första gången, måste du göra det i händelsehanteraren &quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot; at.js för att undvika fel. Om din artefakt är mycket stor återges alla&quot;platser&quot; som använder den här metoden först när artefakten har hämtats helt, vilket kan fördröja återgivningen. [!DNL Adobe] rekommenderar att du sällan använder den här metoden. Följ de bästa sätten att minska artefaktstorleken i avsnittet [&quot;On Device&quot; (på enhet)](#best-practices-on-device) ovan när du använder det här arbetssättet.

## Självstudiekurs: Enhetsbeslut

[!DNL Adobe Target] beslutsfattande på enheter möjliggör innehållsleverans med nästan noll latens.

Den här 7-minutersvideon:

* Beskriver enhetsbeslut, inklusive hur det jämförs med andra metoder för [!DNL Target]-implementering
* Visar hur du kan aktivera enhetsbeslut i [!DNL Target]
* Undersöker en formulärbaserad dispositionsaktivitet som har konfigurerats med JSON-innehåll
* Visar exempelkoden Node.JS SDK som innehåller den nyckelkonfiguration som krävs för enhetsbeslut
* Visar resultat i en webbläsare

>[!VIDEO](https://video.tv.adobe.com/v/329032)

Fler videoklipp och självstudiekurser finns i guiden [Adobe Target Tutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html).

## Adobe Tech Blog - Del 1: Kör [!DNL Adobe Target] NodeJS SDK för experiment och personalisering på kantplattformar (Akamai Edge Workers)

[Klicka här för att komma åt blogginlägget](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9).

## Adobe Tech Blog - Del 2: Kör [!DNL Adobe Target] NodeJS SDK för experiment och personalisering på kantplattformar (AWS Lambda@Edge)

[Klicka här för att komma åt blogginlägget](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563).