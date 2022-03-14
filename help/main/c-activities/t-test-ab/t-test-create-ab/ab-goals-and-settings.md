---
keywords: aktivitetsinställningar;A/B-mål och -inställningar;rapporteringsinställningar;målmått;framgångsmått;beroende framgångsmått;avancerade inställningar;primärt mål;ytterligare mått;mål;prioritet;varaktighet;rapporteringslösning;mål;målgrupper för rapportering;Vilket framgångsmått som måste uppnås innan det här måttet ökas;Vad som händer när en användare påträffar detta målmått;anteckningar
description: Lär dig hur du använder sidan Mål och inställningar i Adobe [!DNL Target] för att ange information om målen för en A/B-aktivitet.
title: Hur anger jag mål och inställningar i en [!DNL Target] A/B-aktivitet?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1325'
ht-degree: 0%

---

# Mål och inställningar

Sidan Mål och inställningar i [!DNL Adobe Target] Här anger du information om testets mål.

Vilka inställningar som är tillgängliga beror på om du använder Target eller [Analyser](/help/main/c-integrating-target-with-mac/a4t/a4t.md) som datakälla.

![Dialogrutan Aktivitetsinställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

## Aktivitetsinställningar {#section_DCBDC354261F420EBD4B43EA34947BAC}

| Inställningar | Beskrivning |
|--- |--- |
| Syfte | Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera kampanjen. |
| Prioritet | Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.<br>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.<br>Om det här alternativet inte är aktiverat i [!UICONTROL Administration] (standard), ange en prioritet: Låg, Medel eller Hög. <br>Om du vill aktivera detaljerade prioriteringar klickar du på  [!UICONTROL Administration] > [!UICONTROL Reporting]och sedan växla alternativet Aktivera finkorniga prioriteringar till läget&quot;På&quot;. <br>Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999: 0 = Låg och 999 = Hög. <br>För aktiviteter som skapats i tidigare versioner av Target Standard/Premium konverteras låg prioritet till 0, Medel konverteras till 5 och Hög konverteras till 10. Du kan justera dessa värden om det behövs.<br>Obs! Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10. |
| Varaktighet | Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmarsklocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren. |

## Rapportinställningar {#section_13119392051044FBA6387D9B3B1C43CF}

| Inställningar | Beskrivning |
|--- |--- |
| Rapporteringskälla | Ange om data samlas in från Adobe Target eller från Adobe Analytics. Se [Adobe Analytics som rapportkälla för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) för att lära sig om skillnaderna mellan rapporteringslösningarna och fördelarna med varje lösning.  När du väljer Analytics som rapportkälla för Target väljer du en Analytics-rapportsserie som tar emot Target-aktivitetsdata.<br>För att göra detta väljer du först något av Analytics-företagen som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till Adobe Target kan väljas. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och logga in på Adobe Experience Cloud för att försöka igen. Kontakta kundtjänst om rapportsviten fortfarande saknas i listan.<br>Om en rapportkälla anges i dina kontoinställningar används den angivna källan och den här inställningen syns inte.<br>Obs! Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa. |
| Mål | Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett konverteringsmått och ange sedan parametrarna som avgör när resultatet uppnås.  Mer information om att ställa in mätvärden finns i [Ange mått](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<br>Obs! Om rapporteringslösningen är inställd på Analytics (Analyser) är det enda tillgängliga målmåttet Konvertering. Analysmått kan inte väljas som mål.   När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.<br>Om det här alternativet är aktiverat ger det beräknade värdet i konverteringsfältet (inte tillgängligt för sidpoängsmått) ett värde för ditt mål, men inte för andra mått. Detta värde gör att Target kan beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. För alla intäktsmått (Intäkt per besökare, Genomsnittligt ordervärde, Total försäljning och Beställningar) används Intäkt per besökare i uppskattningen. Datatypen är valuta.<br>När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Observera att detta inte är standardbeteendet i Target Classic, som räknar besökare som nya om de ser testet igen. |
| Ytterligare mått | Skapa fler framgångsmått.  Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på Analytics. I det här fallet används de mått som definierats för Analytics-rapportsviten. |
| Målgrupper för rapportering | Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att bara visa information om specifika målgrupper.  Den här inställningen är inte tillgänglig om du väljer Analytics som rapporteringslösning. Målgruppen som definierats för Analytics-rapportsviten används. |

## Avancerade inställningar {#section_E2FE441AFB324E498793ABB025ED9974}

Avancerade inställningar är tillgängliga för målmått för A/B-test.

![Menyn Avancerade inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Om du använder Adobe Analytics som rapportkälla hanteras inställningarna av Analytics-servern. Alternativet för avancerade inställningar är inte tillgängligt.

![Avancerade inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Inställning | Beskrivning |
|--- |--- |
| Vilket framgångsmått måste uppnås innan mätvärdet ökas? | Använd det här alternativet om du bara vill räkna någon som uppnår framgångsmåttet om de tidigare har nått ett annat framgångsmått. En testkonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen.  Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.  Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.  Alternativet Lägg till beroende gör att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts.  Så här lägger du till ett beroende:<ul><li>När du har lagt till ytterligare mått klickar du på Avancerade inställningar.</li><li>Klicka på alternativet Lägg till beroende:</li><li>Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på Uppnådd för att växla mellan Uppnådd och Inte nådd.</li><li>Du kan redigera eller ta bort beroenden när du har lagt till dem.</li></ul> |
| Vad händer efter att en användare har påträffat det här målmåttet? | Det finns tre alternativ för vad som händer när en besökare når målmåttet:<ul><li>Välj Öka antal och behåll användare i aktivitet om du vill ange hur antalet ska ökas.</li><li>Välj Öka antal, Frigör användare och Tillåt återinträde om du vill ange vilken upplevelse användaren ser om han/hon återupptar aktiviteten.</li><li>Välj Öka antal, Frigör användare och fält från Inmatning igen om du vill ange vad användaren ser i stället för aktivitetsinnehållet.</li></ul> |
| Hur ska antalet ökas? | Det finns tre alternativ för hur antalet ökas:<ul><li>En gång per tävlingsbidrag</li><li>Vid varje tryck (förutom uppdatering av sidor)</li><li>Vid varje tryck</li></ul> |

Se [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) för mer information om avancerade inställningar.

## Andra metadata {#section_2E8917BEFB954480A4206B9E9E917F80}

| Inställningar | Beskrivning |
|---|---|
| Anteckningar | Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. Det går att ändra storlek på anteckningsrutan. |

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsinställningar (3:02) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

(https://video.tv.adobe.com/v/17381)

### Skapa A/B-tester (8:36) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur aktivitetsinställningarna passar in i det guidade arbetsflödet i tre steg när du skapar en aktivitet. Mål och inställningar diskuteras från 17:30.

* Skapa en A/B-aktivitet i Adobe Target
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
