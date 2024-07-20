---
keywords: aktivitetsinställningar;mål och inställningar;multivariera;mvt
description: Lär dig hur du använder sidan [!UICONTROL Goals & Settings] i [!DNL Adobe Target] för att ange information om målen för en [!UICONTROL Multivariate Test] (MVT) aktivitet.
title: Hur anger jag mål och inställningar i en [!UICONTROL Multivariate Test]-aktivitet (MVT)?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 0%

---

# Mål och inställningar ([!UICONTROL Multivariate Test])

På sidan [!UICONTROL Goals & Settings] i [!DNL Adobe Target] anger du information om målen för dina [!UICONTROL Multivariate Test] (MVT)-aktiviteter.

Följande avsnitt är tillgängliga:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

Vilka inställningar som är tillgängliga i varje avsnitt beror på om du använder [!DNL Target] eller [!DNL Analytics] som rapportkälla.

## Aktivitetsinställningar {#section_DCBDC354261F420EBD4B43EA34947BAC}

Följande inställningar är tillgängliga:

### Syfte

Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera kampanjen.

### Prioritet

Beroende på dina inställningar varierar användargränssnittet för [!DNL Target] och alternativen för [!UICONTROL Priority]. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High], eller så kan du aktivera finjusterade prioriteter från 0 till 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.

Om det här alternativet inte är aktiverat i [!UICONTROL Administration] > [!UICONTROL Reporting] (standard) anger du en prioritet: [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High].

Om du vill aktivera finkorniga prioriteringar klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting] och växlar sedan alternativet [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.

Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:

* 0 = Låg
* 999 = Hög

För aktiviteter som skapats i tidigare versioner av [!DNL Target] konverteras [!UICONTROL Low] prioritet till 0, [!UICONTROL Medium] prioritet konverteras till 5 och [!UICONTROL High] prioritet konverteras till 10. Du kan justera dessa värden om det behövs.

>[!NOTE]
>
>Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10.

### Varaktighet

Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmarsklocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## Rapportinställningar {#section_13119392051044FBA6387D9B3B1C43CF}

Följande inställningar är tillgängliga:

### Rapportera Source

Ange vilka lösningsdata som samlas in från:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Om en rapporteringslösning anges i dina [kontoinställningar](/help/main/administrating-target/reporting.md) används den angivna lösningen och den här inställningen syns inte.

Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa.

**[!DNL Adobe Analytics]**: Se [[!DNL Adobe Analytics]  som rapportkälla för  [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) om du vill veta mer om skillnaderna mellan rapporteringslösningarna och fördelarna med varje.

När du väljer [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T) väljer du en [!DNL Analytics] rapportsvit som ska ta emot [!DNL Target] aktivitetsdata. För att göra detta väljer du först något av de [!DNL Analytics] företag som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till [!DNL Target] är tillgängliga för urval. Om du inte ser den rapportserie du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen. Om rapportsviten fortfarande saknas i listan kontaktar du [kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) kräver en spårningsserver för att rapportera resultaten korrekt. En standardspårningsserver visas i fältet [!UICONTROL Tracking Server]. Om du använder mer än en spårningsserver måste du ta med rätt spårningsserver i det här fältet. Mer information finns i [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

**[!DNL Adobe Customer Journey Analytics]**: Mer information om integrationen mellan [!DNL Adobe Customer Journey Analytics] och [!DNL Target] finns i [[!DNL Target] Rapportera i  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

### Målmått

Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett [!UICONTROL Conversion]-mått och ange sedan parametrarna som avgör när resultatet uppnås.

>[!NOTE]
>
>Om rapporteringslösningen är inställd på [!DNL Analytics] är det enda tillgängliga målmåttet [!UICONTROL Conversion]. Det går inte att välja [!DNL Analytics]-mått som mål.

När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.

Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of the Conversion] (inte tillgängligt för [!UICONTROL Page Score]-måtten) ett värde för ditt mål, men inte för andra mätvärden. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] och [!UICONTROL Orders]) använder uppskattningen [!UICONTROL Revenue per Visitor]. Datatypen är valuta.

När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Det här beteendet skiljer sig från standardbeteendet i [!DNL Target Classic], som räknar besökare som nya om de ser testet igen.

### Ytterligare mått

Skapa fler framgångsmått.

Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på [!DNL Analytics]. I det här fallet används de mått som definierats för rapportsviten [!DNL Analytics].

### Målgrupper för rapportering

Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att bara visa information om specifika målgrupper.

### Avancerade inställningar {#section_E2FE441AFB324E498793ABB025ED9974}

Avancerade inställningar är tillgängliga för [!UICONTROL Multivariate Test] målmått.

![Menyn Avancerade inställningar](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av servern [!DNL Analytics]. Alternativet för avancerade inställningar är inte tillgängligt.

#### Vilket framgångsmått måste uppnås innan mätvärdet ökas?

Använd det här alternativet om du bara vill räkna någon som uppnår framgångsmåttet om de tidigare har nått ett annat framgångsmått. En testkonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen.

Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.

Definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.

Alternativet [!UICONTROL Add Dependency] tillåter att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts.

Så här lägger du till ett beroende:

1. När du har lagt till ytterligare mått klickar du på **[!UICONTROL Advanced Settings]**.
2. Klicka på alternativet **[!UICONTROL Add Dependency]**:

   ![Lägg till beroende](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på **[!UICONTROL Reached]** för att växla mellan Reached och Not Reached (Uppnådd och inte nådd).

   ![Beroende har nåtts](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Du kan redigera eller ta bort beroenden när du har lagt till dem.

### Vad händer efter att en användare har påträffat det här målmåttet?

Det finns tre alternativ för vad som händer när en besökare når målmåttet:

* [!UICONTROL Select Increment Count & Keep User in Activity] för att ange hur antalet ökas.
* [!UICONTROL Select Increment Count, Release User & Allow Reentry] för att ange den upplevelse som användaren ser om han/hon återupptar aktiviteten.
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry] om du vill ange vad användaren ser i stället för aktivitetsinnehållet.

Mer information om avancerade inställningar finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Andra metadata {#section_2E8917BEFB954480A4206B9E9E917F80}

Följande inställning är tillgänglig:

### Anteckningar

Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. Det går att ändra storlek på rutan [!UICONTROL Notes].

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Skapa multivariata tester (9:25)

I den här videon visas hur du skapar ett multivariata test med hjälp av det guidade arbetsflödet i [!DNL Target] i tre steg. Mål och inställningar diskuteras från kl. 7.00.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
