---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Du kan konfigurera en aktivitet i Target Standard/Premium så att Adobe Analytics används som rapportkälla (A4T).
title: Skapa aktivitet
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Skapa aktivitet{#activity-creation}

Du kan konfigurera en aktivitet i Target Standard/Premium så att Adobe Analytics används som rapportkälla (A4T).

Innan du ställer in en aktivitet som använder Analytics som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkterna per besökare eller öka antalet klick i kundvagnen. Välj ett slutligt framgångsmått för aktiviteten. Även om du kan välja ytterligare mått när som helst i Analytics, måste du ändå ange ett visst mått som du förväntar dig att det här testet ska påverka.

Att skapa en Target Standard-aktivitet som använder Analytics som rapportkälla liknar att ställa in en vanlig Target Standard-aktivitet, med några viktiga skillnader. Du kan till exempel inte välja ett segment för rapportering när du skapar aktiviteten eftersom alla segment som är tillgängliga i Analytics kan användas när en rapport visas.

1. Klicka på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Ett aktivitetsnamn får inte innehålla tecknet % om Analytics används som rapportkälla.

1. Välj aktivitetstyp och börja konfigurera aktiviteten.
1. När du kommer till den **[!UICONTROL Settings]** del av aktivitetsskapandet som du skapar väljer du **[!UICONTROL Adobe Analytics]** och anger ditt företag.
1. Välj en rapportsvit.

   Du kan välja vilken rapportserie som helst som är tillgänglig för dig i Adobe Analytics. Rapportsviten definierar var insamlade data ska vara tillgängliga. Virtuella rapportsviter ingår inte i rapportsvitlistan.

   Du kan stöta på två möjliga fel när du väljer rapportsviten:

   * Du får ett fel om att det inte finns några rapportsviter tillgängliga, men att ditt konto är korrekt konfigurerat.
   Ni kanske måste kontrollera ert Analytics-företag. Om ditt Experience Cloud-konto är knutet till mer än ett Analytics-företag loggar du ut från Target och loggar in på Analytics under rätt företag. Återgå sedan till Target så läses rapportsviterna in.

   * Du ser inte den rapportserie som du förväntar dig.
   Endast rapportsviter som har etablerats för att ansluta till Adobe Target kan väljas. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på Adobe Experience Cloud för att försöka igen.

   Om rapportsviten/-sviterna fortfarande saknas i listan, [kontakta kundtjänst](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
1. Ange spårningsservern.

   Se [Använda en analysspårningsserver](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Definiera upplevelsen.
1. Ange aktivitetsmålet.

   Du måste välja ett framgångsmått som ska användas som mål för varje test. Aktivitetens mål är den konverteringsaktivitet som signalerar en lyckad aktivitet. Det är god praxis att aldrig göra ett test utan att ha något mål att förbättra på något specifikt sätt. Du kan välja vilket analysmått som helst som finns i Analytics-mätväljaren.

   >[!NOTE]
   >
   >Du kan skicka ett anpassat målbaserat mått till Analytics i stället för att bara förlita dig på Analytics-data. Du kan till exempel övervaka klickningen på en sida, som vanligtvis inte spåras av Analytics. Detta anpassade mått skickas automatiskt till Analytics från målservern och visas som måttet&quot;Target Conversion&quot; i mätväljaren i Analytics. Måttet för målkonvertering är tomt om du väljer att använda analysstatistik.

   Att du anger ett mål innebär inte att du inte kan använda ett annat mått när du utvärderar testresultat. Målet är dock en påminnelse om det som du vill förbättra med aktiviteten.

   Besökaren är kvar i aktiviteten när de har nått målet. Besökaren fortsätter att se aktivitetsinnehåll men räknas inte som en ny aktivitetspost.

   >[!NOTE]
   >
   >När du skapar en aktivitet efter att ha konfigurerat Analytics som rapportkälla finns det inget alternativ för att konfigurera målgrupper för rapportering. Analyssegment finns i rapporten om målaktiviteter.

1. Klicka på **[!UICONTROL Save]**.

