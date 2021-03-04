---
keywords: a4t;A4T;Analyser som rapportkälla för Target
description: Lär dig hur du konfigurerar en aktivitet i Adobe Target som använder Adobe Analytics som rapportkälla (A4T).
title: Hur skapar jag en aktivitet som använder A4T?
feature: Analyser för mål (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---


# Skapa en aktivitet som använder Analytics som rapportkälla

Du kan konfigurera en aktivitet i [!DNL Adobe Target] så att [!DNL Adobe Analytics] används som rapportkälla (A4T).

Innan du ställer in en aktivitet som använder [!DNL Analytics] som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkterna per besökare eller öka antalet klick i kundvagnen. Välj ett slutligt framgångsmått för aktiviteten. Du kan när som helst välja fler mätvärden i [!DNL Analytics], men du måste ändå ange ett visst mätvärde som testet ska påverka.

## Skapa aktiviteten

Att skapa en [!DNL Target]-aktivitet som använder [!DNL Analytics] som rapportkälla liknar att ställa in en vanlig [!DNL Target]-aktivitet, med några viktiga skillnader. Du kan till exempel inte välja ett segment för rapportering när du skapar aktiviteten eftersom alla segment som är tillgängliga i [!DNL Analytics] kan användas när en rapport visas.

1. Klicka på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Ett aktivitetsnamn får inte innehålla tecknet % om [!DNL Analytics] används som rapportkälla.

1. Välj aktivitetstyp och börja konfigurera aktiviteten.

   Om du vill skapa en [!UICONTROL Auto-Allocate]- eller [!UICONTROL Auto-Target]-aktivitet kan du läsa [A4T-stöd för aktiviteterna Automatisk allokering och Automatisk målning](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) för mer information.

1. När du kommer till **[!UICONTROL Settings]**-delen av aktivitetsskapandet väljer du **[!UICONTROL Adobe Analytics]** och anger ditt företag.
1. Välj en rapportsvit.

   Du kan välja vilken rapportserie som helst som är tillgänglig i [!DNL Analytics]. Rapportsviten definierar var insamlade data är tillgängliga. Virtuella rapportsviter ingår inte i rapportsvitlistan.

   Du kan stöta på två möjliga fel när du väljer rapportsviten:

   * Du får ett fel om att det inte finns några rapportsviter tillgängliga, men att ditt konto är korrekt konfigurerat.

      Kontrollera ditt [!DNL Analytics]-företag. Om ditt [!DNL Adobe Experience Cloud]-konto är knutet till mer än ett [!DNL Analytics]-företag loggar du ut från [!DNL Target] och loggar in på [!DNL Analytics] under rätt företag. Återgå sedan till [!DNL Target] så läses rapportsviterna in.

   * Du ser inte den rapportserie som du förväntar dig.

      Endast rapportsviter som har etablerats för att ansluta till [!DNL Target] är tillgängliga för urval. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] och försöka igen.
   Om en eller flera rapportsviter fortfarande saknas i listan, [kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Ange spårningsservern.

   Se [Använda en analysspårningsserver](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Definiera upplevelsen.
1. Ange aktivitetsmålet.

   Du måste välja ett framgångsmått som ska användas som mål för varje aktivitet. Aktivitetens mål är den konverteringsaktivitet som signalerar en lyckad aktivitet. Det är god praxis att aldrig göra ett test utan att ha något mål att förbättra på något specifikt sätt. Du kan välja valfritt [!DNL Analytics]-mått som är tillgängligt i [!DNL Analytics]-mätväljaren.

   >[!NOTE]
   >
   >Du kan skicka ett anpassat målbaserat mått till [!DNL Analytics] i stället för att bara förlita dig på [!DNL Analytics]-data. Du kan till exempel övervaka att klicka på en sida, som vanligtvis inte spåras av [!DNL Analytics]. Det här anpassade måttet skickas automatiskt till [!DNL Analytics] från [!DNL Target]-servern och visas som [!DNL Target]-konverteringsmåttet i mätväljaren i [!DNL Analytics]. Konverteringsmåttet [!DNL Target] är tomt om du väljer att använda [!DNL Analytics]-mått.

   Att du anger ett mål innebär inte att du inte kan använda ett annat mått när du utvärderar testresultat. Målet är dock en påminnelse om det som du vill förbättra med aktiviteten.

   Besökaren är kvar i aktiviteten när de har nått målet. Besökaren fortsätter att se aktivitetsinnehåll men räknas inte som en ny aktivitetspost.

   >[!NOTE]
   >
   >När du konfigurerar en aktivitet efter att du har konfigurerat [!DNL Analytics] som rapportkälla finns det inget alternativ för att konfigurera målgrupper för rapportering. [!DNL Analytics] segment är tillgängliga i  [!DNL Target] verksamhetsrapporten.

1. Klicka på **[!UICONTROL Save]**.

## A4T- och Automatisk fördelning- och Automatisk målaktiviteter

Mer information finns i [A4T-stöd för aktiviteterna Automatisk allokering och Automatisk målning](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).