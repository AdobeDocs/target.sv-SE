---
keywords: activity settings;mvt goals and settings;multivariate goals and settings;reporting settings;goal metrics;success metrics;dependent success metrics;advanced settings;primary goal;additional metrics;objective;priority;duration;reporting solution;goal;audiences for reporting;Which success metric must be reached before incrementing this metric;What will happen after a user encounters this goal metric;notes
description: På sidan Mål och inställningar anger du information om målet för testet.
title: Mål och inställningar
feature: null
topic: Standard
uuid: 710c64bf-aa28-412e-a933-3845892f457e
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---


# Mål och inställningar{#goals-and-settings}

På sidan Mål och inställningar anger du information om målet för testet.

* Aktivitetsinställningar
* Rapportinställningar
* Andra metadata

Vilka inställningar som är tillgängliga beror på om du använder Target eller Analytics som datakälla.

![](assets/mvt_settings.png)

## Aktivitetsinställningar {#section_DCBDC354261F420EBD4B43EA34947BAC}

Följande inställningar är tillgängliga:

### Syfte

Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera kampanjen.

### Prioritet

Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.

Om det här alternativet inte är aktiverat i S[!UICONTROL Administration] > [!UICONTROL Reporting] (standardvärdet) anger du en prioritet: Låg, Medel eller Hög.

Om du vill aktivera finkorniga prioriteringar klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting]och växlar sedan alternativet Aktivera finkorniga prioriteringar till På-positionen.

Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:

* 0 = Låg
* 999 = Hög

För aktiviteter som skapats i tidigare versioner av Target Standard/Premium konverteras låg prioritet till 0, Medel konverteras till 5 och Hög konverteras till 10. Du kan justera dessa värden om det behövs.

>[!NOTE]
>
>Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10.

### Varaktighet

Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmarsklocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## Rapportinställningar {#section_13119392051044FBA6387D9B3B1C43CF}

Följande inställningar är tillgängliga:

### Rapporteringslösning

Ange om data samlas in från Adobe Target eller från Adobe Analytics. Se [Adobe Analytics som rapportkälla för Target](/help/c-integrating-target-with-mac/a4t/a4t.md) om du vill veta mer om skillnaderna mellan rapporteringslösningarna och fördelarna med var och en av dem.

När du väljer Analytics som rapportkälla för Target väljer du en Analytics-rapportsserie som tar emot Target-aktivitetsdata. För att göra detta väljer du först något av Analytics-företagen som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till Adobe Target kan väljas. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på Adobe Experience Cloud för att försöka igen. Kontakta kundtjänst om rapportsviten fortfarande saknas i listan.

Analyser för Target kräver en spårningsserver för att kunna rapportera resultaten korrekt. En standardspårningsserver visas i fältet Spårningsserver. Om du använder mer än en spårningsserver bör du kontrollera att du inkluderar rätt spårningsserver i det här fältet. Mer information finns i [Använda en analysspårningsserver](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) .

Om en rapporteringslösning anges i dina kontoinställningar används den angivna lösningen och den här inställningen syns inte.

>[!NOTE]
>
>Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa.

### Mål

Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett konverteringsmått och ange sedan parametrarna som avgör när resultatet uppnås.

>[!NOTE]
>
>Om rapporteringslösningen är inställd på Analytics (Analyser) är det enda tillgängliga målmåttet Konvertering. Analysmått kan inte väljas som mål.

När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.

Om det här alternativet är aktiverat ger det beräknade värdet i konverteringsfältet (inte tillgängligt för sidpoängsmått) ett värde för ditt mål, men inte för andra mått. Detta värde gör att Target kan beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. För alla intäktsmått (Intäkt per besökare, Genomsnittligt ordervärde, Total försäljning och Beställningar) används Intäkt per besökare i uppskattningen. Datatypen är valuta.

När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Observera att detta inte är standardbeteendet i Target Classic, som räknar besökare som nya om de ser testet igen.

### Ytterligare mått

Skapa fler framgångsmått.

Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på Analytics. I det här fallet används de mått som definierats för Analytics-rapportsviten.

Målgrupper för rapportering

### Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att bara visa information om specifika målgrupper.

## Avancerade inställningar {#section_E2FE441AFB324E498793ABB025ED9974}

Avancerade inställningar är tillgängliga för multivariata testmålmått.

![Menyn Avancerade inställningar](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Om du använder Adobe Analytics som rapportkälla hanteras inställningarna av Analytics-servern. Alternativet för avancerade inställningar är inte tillgängligt.

### Vilket framgångsmått måste uppnås innan mätvärdet ökas?

Använd det här alternativet om du bara vill räkna någon som uppnår framgångsmåttet om de tidigare har nått ett annat framgångsmått. En testkonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen.

Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.

Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.

Alternativet Lägg till beroende gör att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts.

Så här lägger du till ett beroende:

1. När du har lagt till ytterligare mätvärden klickar du på **[!UICONTROL Advanced Settings]**.
2. Klicka på alternativet Lägg till beroende:

   ![Lägg till beroende](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på **[!UICONTROL Reached]** för att växla mellan Reached och Not Reached.

   ![Beroende har nåtts](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Du kan redigera eller ta bort beroenden när du har lagt till dem.

### Vad händer efter att en användare har påträffat det här målmåttet?

Det finns tre alternativ för vad som händer när en besökare når målmåttet:

* Välj Öka antal och behåll användare i aktivitet om du vill ange hur antalet ska ökas.
* Välj Öka antal, Frigör användare och Tillåt återinträde om du vill ange vilken upplevelse användaren ser om han/hon återupptar aktiviteten.
* Välj Öka antal, Frigör användare och fält från Inmatning igen om du vill ange vad användaren ser i stället för aktivitetsinnehållet.

Mer information om avancerade inställningar finns i [Success Metrics](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) .

## Andra metadata {#section_2E8917BEFB954480A4206B9E9E917F80}

Följande inställning är tillgänglig:

### Anteckningar

Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. Det går att ändra storlek på anteckningsrutan.

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsinställningar (3:02) - ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Skapa multivariata tester (9:25) ![självstudiemärke](/help/assets/tutorial.png)

I den här videon visas hur du skapar ett multivariata test med det guidade arbetsflödet i tre steg för Target. Mål och inställningar diskuteras från kl. 7.00.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)