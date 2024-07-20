---
keywords: a4t;A4T;Analyser som rapportkälla för Target
description: Lär dig hur du konfigurerar en aktivitet i Adobe [!DNL Target]  som använder Adobe Analytics som rapportkälla (A4T).
title: Hur skapar jag en aktivitet som använder A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Skapa en aktivitet som använder Analytics som rapportkälla

Du kan konfigurera en aktivitet i [!DNL Adobe Target] att använda [!DNL Adobe Analytics] som rapportkälla (A4T).

Innan du ställer in en aktivitet som använder [!DNL Analytics] som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkten per besökare eller öka antalet klick i kundvagnen. Välj ett slutligt framgångsmått för aktiviteten. Du kan när som helst välja fler mätvärden i [!DNL Analytics], men du måste ändå ange ett visst mätvärde som testet ska påverka.

## Skapa aktiviteten

Att skapa en [!DNL Target]-aktivitet som använder [!DNL Analytics] som rapportkälla liknar att konfigurera en vanlig [!DNL Target]-aktivitet, med några viktiga skillnader. Du kan till exempel inte välja ett segment för rapportering när aktiviteten skapas eftersom alla segment som är tillgängliga i [!DNL Analytics] kan användas när en rapport visas.

1. Klicka på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Ett aktivitetsnamn får inte innehålla tecknet % om [!DNL Analytics] används som rapportkälla.
   >
   >Använd inte samma aktivitetsnamn för två aktiviteter från separata [arbetsytor](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) som använder A4T-rapportering.

1. Välj aktivitetstyp och börja konfigurera aktiviteten.

   Om du vill skapa en [!UICONTROL Auto-Allocate]- eller [!UICONTROL Auto-Target]-aktivitet kan du läsa [A4T-stöd för aktiviteterna Automatisk allokering och Automatiskt mål](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) för mer information.

1. När du kommer till delen **[!UICONTROL Settings]** av aktivitetsskapandet väljer du **[!UICONTROL Adobe Analytics]** och anger ditt företag.
1. Välj en rapportsvit.

   Du kan välja vilken rapportserie som helst som är tillgänglig för dig i [!DNL Analytics]. Rapportsviten definierar var insamlade data är tillgängliga. Virtuella rapportsviter ingår inte i rapportsvitlistan.

   Du kan stöta på två möjliga fel när du väljer rapportsviten:

   * Du får ett fel om att det inte finns några rapportsviter tillgängliga, men att ditt konto är korrekt konfigurerat.

     Kontrollera ditt [!DNL Analytics]-företag. Om ditt [!DNL Adobe Experience Cloud]-konto är knutet till mer än ett [!DNL Analytics]-företag loggar du ut från [!DNL Target] och loggar in på [!DNL Analytics] under rätt företag. Återgå sedan till [!DNL Target] och rapportsviterna läses in.

   * Du ser inte den rapportserie som du förväntar dig.

     Endast rapportsviter som har etablerats för att ansluta till [!DNL Target] är tillgängliga för urval. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen.

   [Kontakta kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om en eller flera rapportsviter fortfarande saknas i listan.

1. Ange spårningsservern.

   Se [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Definiera upplevelsen.
1. Ange aktivitetsmålet.

   Du måste välja ett framgångsmått som ska användas som mål för varje aktivitet. Aktivitetens mål är den konverteringsaktivitet som signalerar en lyckad aktivitet. Det är god praxis att aldrig göra ett test utan att ha något mål att förbättra på något specifikt sätt. Du kan välja ett [!DNL Analytics]-mått som är tillgängligt i [!DNL Analytics]-metrisk väljaren.

   >[!NOTE]
   >
   >Du kan skicka ett anpassat målbaserat mått till [!DNL Analytics] i stället för att bara förlita dig på [!DNL Analytics]-data. Du kan till exempel övervaka att klicka på en sida, som vanligtvis inte spåras av [!DNL Analytics]. Det här anpassade måttet skickas automatiskt till [!DNL Analytics] från servern [!DNL Target] och visas som [!DNL Target]-konverteringsmåttet i måttväljaren i [!DNL Analytics]. Konverteringsmåttet [!DNL Target] är tomt om du väljer att använda [!DNL Analytics]-mått.

   Att du anger ett mål innebär inte att du inte kan använda ett annat mått när du utvärderar testresultat. Målet är dock en påminnelse om det som du vill förbättra med aktiviteten.

   Besökaren är kvar i aktiviteten när de har nått målet. Besökaren fortsätter att se aktivitetsinnehåll men räknas inte som en ny aktivitetspost.

   >[!NOTE]
   >
   >När du konfigurerar en aktivitet efter att ha konfigurerat [!DNL Analytics] som rapportkälla finns det inget alternativ för att konfigurera målgrupper för rapportering. [!DNL Analytics] segment är tillgängliga i [!DNL Target]-aktivitetsrapporten.

1. Klicka på **[!UICONTROL Save]**.

## A4T- och Automatisk fördelning- och Automatisk målaktiviteter

Mer information finns i [Stöd för A4T för aktiviteter som automatisk allokering och automatisk målning](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
