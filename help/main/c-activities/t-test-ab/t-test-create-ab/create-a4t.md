---
keywords: Riktning;analys;spårningsserver;analys för mål;a4t
description: Lär dig hur du konfigurerar en aktivitet i [!DNL Adobe Target] att använda [!DNL Adobe Analytics]  som rapportkälla (A4T).
title: Hur kan jag använda  [!DNL Analytics] data i [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Använder [!DNL Adobe Analytics] data

Du kan konfigurera en aktivitet i [!DNL Adobe Target] att använda [!DNL Adobe Analytics] som rapportkälla (A4T).

Mer information om hur du konfigurerar [!DNL Analytics] som datakälla för [!DNL Target] finns i [Adobe Analytics som Reporting Source för Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Innan du ställer in en aktivitet som använder [!DNL Analytics] som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkten per besökare (RPV) eller öka antalet klick i kundvagnen. Välj ett slutligt framgångsmått för aktiviteten. Du kan när som helst välja ytterligare mått i [!DNL Analytics], men du måste ändå ange ett visst mått som testet ska påverka.

>[!NOTE]
>
>Alternativet [!DNL Adobe Analytics] är tillgängligt om du har länkat ditt [!DNL Adobe Experience Cloud]-konto till både [!DNL Analytics] och [!DNL Target], även om integrering mellan [!DNL Target] och [!DNL Analytics] inte har konfigurerats för ditt konto.

När du väljer [!DNL Analytics] som rapportkälla för [!DNL Target] väljer du en [!DNL Analytics]-rapportsvit som ska ta emot [!DNL Target] aktivitetsdata. Om du vill ange en rapportkälla väljer du först något av de [!DNL Analytics] företag som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till [!DNL Adobe Target] är tillgängliga för urval. Om du inte ser den rapportserie du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen. Kontakta kundtjänst om rapportsviten fortfarande saknas i listan.

[!UICONTROL Analytics for Target] (A4T) kräver en spårningsserver för att rapportera resultaten korrekt. En standardspårningsserver visas i fältet [!UICONTROL Tracking Server]. Om du använder mer än en spårningsserver måste du ta med rätt spårningsserver i det här fältet. Mer information finns i [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar aktiviteter om du använder at.js version 0.9.1 (eller senare). at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När aktiviteten skapas kan du lämna fältet [!UICONTROL Tracking Server] tomt på sidan [!UICONTROL Goals & Settings].

När du konfigurerar aktiviteten efter att ha konfigurerat [!DNL Analytics] som rapportkälla finns det inget alternativ för att konfigurera målgrupper för rapportering. [!DNL Analytics] segment är tillgängliga i rapporten [!DNL Target] [!UICONTROL Activities].

Du måste välja ett framgångsmått som ska användas som mål för varje aktivitet. Aktivitetens mål är den konverteringsaktivitet som signalerar en lyckad aktivitet. Det är god praxis att aldrig göra ett test utan att ha något mål att förbättra på något specifikt sätt. Du kan välja ett [!DNL Analytics]-mått som är tillgängligt i [!DNL Analytics]-metrisk väljaren.

Att du anger ett mål innebär inte att du inte kan använda ett annat mått när du utvärderar testresultat. Målet är dock en påminnelse om det som du vill förbättra med testet.

När en besökare har slutfört ditt mål inkluderas den besökaren inte längre i aktiviteten. Om besökaren återgår till din aktivitet efter att ha slutfört en aktivitet räknas den besökaren som en ny besökare.
