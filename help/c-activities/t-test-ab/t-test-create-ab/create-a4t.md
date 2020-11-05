---
keywords: Targeting;analytics;tracking server
description: Du kan konfigurera en aktivitet i Target Standard så att den använder Adobe Analytics som rapportkälla (A4T).
title: Använda analysdata
feature: a4t general
uuid: 4ac0c181-030b-4cf5-b138-acf02c7af4f6
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---


# Använda analysdata{#using-analytics-data}

Du kan konfigurera en aktivitet i Target Standard så att den använder Adobe Analytics som rapportkälla (A4T).

Mer information om hur du konfigurerar Analytics som datakälla för Target finns i [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Innan du ställer in en aktivitet som använder Analytics som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkterna per besökare eller öka antalet klick i kundvagnen. Välj ett slutresultat för kampanjen. Även om du kan välja ytterligare mått när som helst i Analytics, måste du ändå ange ett visst mått som du förväntar dig att det här testet ska påverka.

>[!NOTE]
>
>Alternativet Adobe Analytics är tillgängligt om du har länkat ditt Adobe Experience Cloud-konto till både Analytics och Target, även om integrering mellan Target och Analytics inte har konfigurerats för ditt konto.

När du väljer Analytics som rapportkälla för Target väljer du en Analytics-rapportsserie som tar emot Target-aktivitetsdata. För att göra detta väljer du först något av Analytics-företagen som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till Adobe Target kan väljas. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på Adobe Experience Cloud för att försöka igen. Kontakta kundtjänst om rapportsviten fortfarande saknas i listan.

Analyser för Target kräver en spårningsserver för att kunna rapportera resultaten korrekt. En standardspårningsserver visas i fältet Spårningsserver. Om du använder mer än en spårningsserver bör du kontrollera att du inkluderar rätt spårningsserver i det här fältet. Mer information finns i [Använda en analysspårningsserver](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) .

>[!NOTE]
>
>Om du använder Adobe Analytics som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar en aktivitet om du använder mbox.js version 61 (eller senare) eller at.js version 0.9.1 (eller senare). Mbox.js- eller at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När du skapar en aktivitet kan du lämna [!UICONTROL Tracking Server] fältet tomt på [!UICONTROL Goals & Settings] sidan.

När du konfigurerar aktivitet efter att ha konfigurerat Analytics som rapportkälla finns det inget alternativ för att konfigurera målgrupper för rapportering. Analyssegment finns i rapporten om målaktiviteter.

Du måste välja ett framgångsmått som ska användas som mål för varje test. Ditt verksamhetsmål är konverteringsaktiviteten som signalerar en lyckad kampanj. Det är god praxis att aldrig göra ett test utan att ha något mål att förbättra på något specifikt sätt. Du kan välja vilket analysmått som helst som finns i Analytics-mätväljaren.

Att du anger ett mål innebär inte att du inte kan använda ett annat mått när du utvärderar testresultat. Målet är dock en påminnelse om det som du vill förbättra med testet.

När en besökare har slutfört ditt mål inkluderas den besökaren inte längre i kampanjen. Om besökaren återgår till kampanjen efter att ha slutfört en aktivitet räknas han eller hon som en ny besökare.
