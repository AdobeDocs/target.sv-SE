---
keywords: aktivitetsinställningar;A/B-mål och -inställningar;rapporteringsinställningar;målmått;framgångsmått;beroende framgångsmått;avancerade inställningar;primärt mål;ytterligare mått;mål;prioritet;varaktighet;rapporteringslösning;mål;målgrupper för rapportering;Vilket framgångsmått som måste uppnås innan det här måttet ökas;Vad som händer när en användare påträffar detta målmått;anteckningar
description: Lär dig hur du använder sidan [!UICONTROL Goals and Settings] för att ange information om målen för en A/B-aktivitet.
title: Hur anger jag mål och inställningar i en [!DNL Target] A/B-aktivitet?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 0%

---

# Mål och inställningar

På sidan [!UICONTROL Goals & Settings] i [!DNL Adobe Target] anger du information om aktivitetens mål.

Vilka inställningar som är tillgängliga beror på om du använder Target eller [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) som rapportkälla.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

I avsnittet [!UICONTROL Activity Settings] på sidan [!UICONTROL Goals & Settings] kan du konfigurera följande alternativ:

| Inställningar | Beskrivning |
|--- |--- |
| [!UICONTROL Objective] | Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera aktiviteten. |
| [!UICONTROL Priority] | Beroende på dina inställningar varierar användargränssnittet för [!DNL Target] och alternativen för [!UICONTROL Priority]. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High], eller så kan du aktivera finjusterade prioriteter från 0 till 999.<P>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.<P>Om det här alternativet inte är aktiverat i [!UICONTROL Administration] (standardvärdet) anger du en prioritet: [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High].<P>Om du vill aktivera [finkorniga prioriteter](/help/main/administrating-target/reporting.md) klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting] och växlar sedan alternativet [!UICONTROL Enable Fine-Grained Priorities] till läget &quot;På&quot;. <P>Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999: 0 = [!UICONTROL Low] och 999 = [!UICONTROL High]. <P>För aktiviteter som skapats i tidigare versioner av [!DNL Target] konverteras [!UICONTROL Low] prioritet till 0, [!UICONTROL Medium] konverteras till 5 och [!UICONTROL High] konverteras till 10. Du kan justera dessa värden om det behövs.<P>Obs! Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10. |
| Varaktighet | Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmars klocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren. |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

I avsnittet [!UICONTROL Reporting Settings] på sidan [!UICONTROL Goals & Settings] kan du konfigurera följande alternativ:

| Inställningar | Beskrivning |
|--- |--- |
| [!UICONTROL Reporting Source] | Ange vilka lösningsdata som samlas in från:<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Om en rapportkälla anges i dina [kontoinställningar](/help/main/administrating-target/reporting.md) används den angivna källan och den här inställningen syns inte.<P>Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa.<P>**Adobe Analytics**: Se [Adobe Analytics som Reporting Source för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) om du vill veta mer om skillnaderna mellan rapporteringslösningarna och fördelarna med var och en. När du väljer [!DNL Analytics] som rapportkälla för [!DNL Target] väljer du en [!DNL Analytics]-rapportsvit som ska ta emot [!DNL Target] aktivitetsdata.<P>Om du vill ange en rapportkälla väljer du först något av de [!DNL Analytics] företag som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till [!DNL Adobe Target] är tillgängliga för urval. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen. Kontakta kundtjänst om rapportsviten fortfarande saknas i listan.<P><P>**Adobe Customer Journey Analytics**: Mer information om integrationen mellan [[!DNL Target]  och  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) finns i [!DNL Adobe Customer Journey Analytics]Rapportera i[!DNL Target].<P>[!DNL Target]-rapportering i [!DNL Customer Journey Analytics] stöds i A/B-aktiviteter med manuell trafikdelning. [!UICONTROL Auto-Target] och [!UICONTROL Auto-Allocate] A/B-aktiviteter kan inte använda [!DNL Target]-rapportering i [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett [!UICONTROL Conversion]-mått och ange sedan parametrarna som avgör när resultatet uppnås. Mer information om att ställa in mått finns i [Ange mått](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Obs! Om rapporteringslösningen är inställd på [!DNL Analytics] är det enda tillgängliga målmåttet [!UICONTROL Conversion]. Det går inte att välja [!DNL Analytics]-mått som mål. När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.<P>Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of the Conversion] (inte tillgängligt för [!UICONTROL Page Score]-måtten) ett värde för ditt mål, men inte för andra mätvärden. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] och [!UICONTROL Orders]) använder uppskattningen [!UICONTROL Revenue per Visitor]. Datatypen är valuta.<P>När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Detta skiljer sig från standardbeteendet i [!DNL Target Classic], som räknar besökare som nya om de ser aktiviteten igen. |
| [!UICONTROL Additional Metrics] | Skapa fler framgångsmått. Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på [!DNL Analytics]. I det här fallet används de mått som definierats för rapportsviten [!DNL Analytics]. |
| [!UICONTROL Audiences for Reporting] | Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att visa information om enbart specifika målgrupper. Den här inställningen är inte tillgänglig om du väljer [!DNL Analytics] som rapporteringslösning. Målgruppen som definierats för rapportsviten [!DNL Analytics] används. |

## Avancerade inställningar {#section_E2FE441AFB324E498793ABB025ED9974}

I avsnittet [!UICONTROL Advanced Settings] på sidan [!UICONTROL Goals & Settings] kan du konfigurera följande alternativ:

Om du vill ange avancerade inställningar klickar du på ikonen **[!UICONTROL More]** (den lodräta ellipsen) och sedan på **[!UICONTROL Advanced Settings]**, vilket visas på följande bild.

![Menyn Avancerade inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Om du använder [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av servern [!DNL Analytics]. Alternativet för avancerade inställningar är inte tillgängligt.

![Avancerade inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Inställning | Beskrivning |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | Använd det här alternativet om du bara vill räkna någon som uppnår framgångsmåttet om de tidigare har nått ett annat framgångsmått. En aktivitetskonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen. Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka. Definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan. Alternativet [!UICONTROL Add Dependency] tillåter att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts. Så här lägger du till ett beroende:<ul><li>När du har lagt till ytterligare mått klickar du på [!UICONTROL Advanced Settings].</li><li>Klicka på alternativet [!UICONTROL Add Dependency]:</li><li>Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på [!UICONTROL Reached] för att växla mellan [!UICONTROL Reached] och [!UICONTROL &#x200B; Not Reached].</li><li>Du kan redigera eller ta bort beroenden när du har lagt till dem.</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | Det finns tre alternativ för vad som händer när en besökare når målmåttet:<ul><li>Välj [!UICONTROL Increment Count & Keep User in Activity] om du vill ange hur antalet ska ökas.</li><li>Välj [!UICONTROL Increment Count, Release User & Allow Reentry] om du vill ange vilken upplevelse som användaren ser om aktiviteten återupptas.</li><li>Välj [!UICONTROL Increment Count, Release User & Bar from Reentry] om du vill ange vad användaren ser i stället för aktivitetsinnehållet.</li></ul> |
| [!UICONTROL How will the count be incremented?] | Det finns tre alternativ för hur antalet ökas:<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

Mer information om avancerade inställningar finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Andra metadata {#section_2E8917BEFB954480A4206B9E9E917F80}

I avsnittet [!UICONTROL Other Metadata] på sidan [!UICONTROL Goals & Settings] kan du ange all information om din aktivitet som är användbar för att hålla dig uppdaterad för dig själv eller andra teammedlemmar. Det går att ändra storlek på anteckningsrutan.|

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsinställningar (3:02) ![Självstudiekurs](/help/main/assets/tutorial.png)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

(https://video.tv.adobe.com/v/17381)

### Skapa A/B-tester (8:36) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur aktivitetsinställningarna passar in i det guidade arbetsflödet i tre steg när du skapar en aktivitet. Mål och inställningar diskuteras från och med :30.

* Skapa en A/B-aktivitet i Adobe Target
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
