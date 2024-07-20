---
keywords: Mål;rapporter;rapportinställningar;förinställning;målförinställning;målpublik;målgrupp;datumintervall;inställningar;hämta;tabellvy;diagramvy;genomsnittshöjning;lyfta;konfidensintervall;konfidensintervall;platsbidrag;löpande genomsnitt;beräkningsmetod
description: Lär dig hur du konfigurerar rapportinställningar i Adobe Target, inklusive mått, målgrupper, datumintervall med mera.
title: Hur konfigurerar jag rapportinställningar?
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: 7de7bb1b3bc70a559d41edece8cae2d388cb0dda
workflow-type: tm+mt
source-wordcount: '1892'
ht-degree: 0%

---

# Rapportinställningar

Information som hjälper dig att ange de element som du vill ska visas i rapporten i [!DNL Adobe Target]. Rapportinställningarna kan sparas för senare bruk.

Så här visar du en rapport:

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet i listan.
1. Klicka på fliken **[!UICONTROL Reports]**.

   ![Rapportera gränssnitt](/help/main/c-reports/c-report-settings/assets/report_ui-new.png)

## Målförinställning {#section_51F67341465045BEB4F1A2FB638A8EB1}

Du kan spara upp till tio olika förinställningar för en enskild aktivitets rapport efter att du har konfigurerat den som du vill (mått, datumintervall, målgrupper, avancerade inställningar osv.). Alla [!DNL Target]-användare kan visa, redigera och ta bort de olika förinställningarna, oavsett vem som skapade dem.

Du kan också konfigurera rapporten för en enskild aktivitet efter behov och sedan spara konfigurationen som standard-/favoritförinställning. Det här är vyn som visas när du visar aktivitetens rapport som fortsätter.

### Skapa en förinställning eller standardförinställning

1. Konfigurera aktivitetens rapport efter behov.

   De tillgängliga inställningarna, inklusive mått, datumintervall, målgrupper, avancerade inställningar och så vidare, förklaras nedan.

1. Klicka på ikonen för tre lodräta ellipser > **[!UICONTROL Save as New]** bredvid **[!UICONTROL Target Preset]**.

   ![Rapportförinställning](/help/main/c-reports/c-report-settings/assets/report_preset-new.png)

   Dialogrutan Ny förinställning visas:

   ![Dialogrutan Ny förinställning](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Granska informationen i avsnitten **[!UICONTROL Filters]** och **[!UICONTROL Settings]** för att kontrollera att rapporten är konfigurerad som du vill och ange sedan **[!UICONTROL Preset Name]** (upp till 50 tecken).
1. (Villkorligt) Om du vill att det här ska vara din standard-/favoritrapportvy drar du reglaget **[!UICONTROL Set as default preset]** till På-positionen.
1. Klicka på **[!UICONTROL Save]**.

### Välj en annan förinställning

Välj önskad förinställning i listrutan **[!UICONTROL Target Preset]**.

![Listrutan Förinställning](/help/main/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### Redigera en förinställning

1. Markera den förinställning som du vill redigera.
1. Redigera rapportens konfiguration efter behov (mått, datumintervall, målgrupper, avancerade inställningar och så vidare).

   När du har klickat på [!UICONTROL Save] efter att ha redigerat rapportens konfiguration visas en asterisk ( &#42; ) efter förinställningens namn för att ange att förinställningen har ändrats, vilket visas nedan:

   ![Rapportförinställning med asterisk](/help/main/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. Klicka på ikonen för tre lodräta ellipser > **[!UICONTROL Save as New]** för att skapa en ny förinställning.

   eller

   Klicka på ikonen för tre lodräta ellipser > **[!UICONTROL Update]** för att uppdatera den aktuella förinställningen.

   ![Rapportera standarduppdatering](/help/main/c-reports/c-report-settings/assets/report_preset_update-new.png)

### Ta bort en förinställning

1. Markera den förinställning som du vill ta bort.
1. Klicka på ikonen för tre lodräta ellipser > **[!UICONTROL Delete]**.

   ![Rapportera standardborttagning](/help/main/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. Klicka på **[!UICONTROL Delete]** igen för att bekräfta borttagningen (borttagna förinställningar kan inte återställas).

### Felhantering av förinställningar

Varningar och meddelanden i rapporter talar om för dig om en förinställning blir ogiltig. Varningen eller meddelandet instruerar dig att välja en annan målgrupp, mätare, värdgrupp eller upplevelse för att skapa en giltig förinställning.

I följande lista beskrivs några situationer som kan göra att en förinställning blir ogiltig:

* En rapportmålgrupp togs bort från aktiviteten men refereras i förinställningsdefinitionen.
* Ett (eller flera) mätvärde togs bort, men det finns referenser i förinställningsdefinitionen. Du kan till exempel ta bort en eller flera mätvärden från aktiviteten och sedan lägga till nya mätvärden.
* En (eller flera) värdgrupp (miljö) finns inte, men det finns en referens i förinställningsdefinitionen.
* En (eller flera) upplevelse togs bort efter att förinställningen skapades, men det finns referenser i förinställningsdefinitionen.
* En förinställning är semantiskt ogiltig eftersom refererade entiteter fortfarande finns men uppdaterades på ett sätt som förinställningsdefinitionen semantiskt har ändrats. Anta till exempel att du först skapar en förinställning med namnet&quot;Intäkter på Chrome&quot;. Du uppdaterar senare aktiviteten för att mäta konverteringsmåttet i stället för intäkt. Den här uppdateringen av aktivitetsdefinitionen gör förinställningsdefinitionen ogiltig semantiskt.

## Rapportmått {#section_894ABD7148244806B7CE556EBBA2AD62}

Klicka på listrutan **[!UICONTROL Report Metric]** för att välja ett annat [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) eller flera mätvärden som ska visas i diagrammet.

Som standard bestäms det primära måttet i inställningarna för framgångsmått när du skapar aktiviteten. Om du ändrar konfigurationen och sparar aktiviteten igen uppdateras det primära måttet för rapportering.

Mer information om hur du väljer flera mätvärden att visa i rapporter finns i [Visa flera mätvärden i en rapport](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## Målgrupp {#section_70926EB4618945D9AFF2B0564FF3717B}

Klicka på listrutan [!UICONTROL Audience] om du vill ändra rapportens målgrupp.

Mer information finns i [Publiker](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## Datumintervall {#section_A410A768403C4E01891F95CB357E63ED}

I rutan Datumintervall visas rapportens aktuella datumintervall. Klicka på listruteikonen för att visa en kalender där du kan ändra rapportens datumintervall.

![Kalender](/help/main/c-reports/c-report-settings/assets/date_range-new.png)

Välj nya **[!UICONTROL Start]**- och **[!UICONTROL End]**-datum för rapporten. Du kan också använda kryssrutorna **[!UICONTROL From start of Activity]** och **[!UICONTROL Till end of Activity]**.

Klicka på **[!UICONTROL Custom Dates]** för att välja fördefinierade datumintervall: Senaste 7 dagarna, Senaste 15 dagarna eller Senaste 30 dagarna. Dessa fördefinierade datumintervall är rullande intervall. Om startdatumet är mindre än antalet valda dagar visas intervallet från startdatumet i kalendern, men om startdatumet blir äldre än det antal dagar som väljs när aktivitetens varaktighet ökar.

Rapporterna har följande datumbegränsningar:

* Rapportens startdatum måste vara inom de senaste två åren.
* Rapporterna om erbjudandegrupper är begränsade till 99 dagar från dagens datum.
* Timrapporter är begränsade till 15 dagar.

## Inställningar {#section_D99CE462107D45CABE0960F820E1E972}

Så här konfigurerar du rapportinställningar:

1. Klicka på kugghjulsikonen och gör önskade ändringar (enligt anvisningarna nedan).
1. Klicka på **[!UICONTROL Save]** när du är klar.

Följande bild visar dialogrutan Inställningar för en A/B-aktivitet:

![Dialogrutan Inställningar](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

Beroende på den valda aktivitetstypen varierar alternativen:

### Räkningsmetod

Välj metod:

* Besökare
* Besök
* Aktivitetsexponeringar

### Kontroll

Välj den kontrollupplevelse som ska användas vid beräkning och jämförelse av lyft.

### Miljö {#environment}

Välj den miljö (värdgrupp) som ska användas för rapporten. Mer information finns i [Värdar](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

>[!NOTE]
>
>Om din organisation använder [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=_blank} (AEP) för att skicka mätdata till [!DNL Target] bör miljön i AEP-dataströmmen matcha miljön i rapportinställningarna för [!DNL Target].


### Återställ rapportdata

Återställ rapportdata för att ta bort gamla data. Befintliga besökare kommer att stanna kvar i aktiviteten.  Det här alternativet är bara tillgängligt för dem med [!UICONTROL Approver] behörigheter.

>[!IMPORTANT]
>
>Detta är en permanent åtgärd som inte kan ångras.

### Exkludera extrema värden

[!UICONTROL Exclude Extreme Values]-växlingen gäller endast för aktiviteter med måtten Intäkter och engagemang. Mer information finns i [Exkludera extrema order](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Ladda ned {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Klicka på ikonen **[!UICONTROL Download]** om du vill hämta rapportdata i ett [!DNL .csv]-format för snabb import till Excel, Access eller andra dataanalysprogram.

![Ikon för hämtning](/help/main/c-reports/c-report-settings/assets/download-icon.png)

Mer information finns i [Hämta data i en CSV-fil](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md).

## Uppdatera {#section_E203729F2F314DF3856D2EE67C60B370}

Klicka på ikonen **[!UICONTROL Refresh]** om du vill uppdatera en rapports tabell- och diagramvy utan att uppdatera hela sidan, dess konfiguration eller dess datumintervall.

## Fler alternativ {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Klicka på ikonen Fler alternativ (tre lodräta ellipser) för att komma åt alternativen [!UICONTROL Edit Activity] och [!UICONTROL View Experience URLs].

## Visningsalternativ

Du kan visa rapporten i olika format, beroende på aktivitetstypen. Välj önskat alternativ.

![Visa alternativikoner](/help/main/c-reports/c-report-settings/assets/view-options.png)

* **Tabellvy**: Klicka på ikonen **[!UICONTROL Table View]** för att visa rapporten som en tabell.
* **Diagramvy**: Klicka på ikonen **[!UICONTROL Graph View]** för att visa rapporten som ett diagram.
* **Automatiska segment**:(Endast tillgängligt för aktiviteter i Automated Personalization (AP) och Automatiskt mål (AT).) Klicka på ikonen **[!UICONTROL Automated Segments] om du vill visa rapporten [Automatiserade segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).
* **Viktiga attribut**: (Endast tillgängligt för aktiviteter i Automated Personalization (AP) och Automatiskt mål (AT).) Klicka på ikonen **[!UICONTROL Important Attributes] om du vill visa rapporten [Viktiga attribut](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse {#section_0D87615B1D3344B3858BA494EEBC16FB}

Rapporterna innehåller flera datapunkter och visualiseringsrepresentationer som förstår vilka lyftgränser och konfidensnivåer din aktivitet har. På så sätt kan du bättre avgöra en vinnare.

Mer information finns i [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

Tänk på följande:

* Endast tillgängligt när du visar rapporter i tabellvyn.
* Den här funktionen är inte tillgänglig för aktiviteter som använder [Analytics som rapportkälla (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Platsbidrag {#section_5832F126AC114AE1ABFFF4D9B904393B}

Klicka på ikonen **[!UICONTROL Location Contribution]** om du vill växla rapporten för att visa bidrag per plats.

## Erfarenheter {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(Endast tillgängligt när du visar rapporten i diagramvyn)

Markera eller avmarkera upplevelser till vänster om diagrammet för att visa eller dölja motsvarande upplevelser i diagrammet.

Om följande bild visas visas bara Default, Mid-East och Total i rapporten. Asienupplevelsen är dold i diagrammet.

![Erfarenheter](/help/main/c-reports/c-report-settings/assets/report_experiences-new.png)

## Löpande medelvärde {#section_59066693158C4433B87D07402C2BC6CD}

(Endast tillgängligt när du visar rapporten i diagramvyn)

&quot;Löpande medelvärde&quot; motsvarar de kumulativa konverteringarna (från rapportfönstrets början till det datum som anges i diagrammet) dividerat med de kumulativa besökarna.

Markera önskad diagramvy:

* Löpande medelvärde
* Löpande medelstor lyft
* Dagligen
* Daglig lyft

![Rapport som körs i genomsnitt](/help/main/c-reports/c-report-settings/assets/report_running_average-new.png)

Namnet på den här listrutan varierar beroende på den valda vyn, men det är en av vyerna ovan.

## Räkningsmetod {#section_01B0ED5665C74AE1AE97259800190C3E}

(Endast tillgängligt när du visar rapporten i diagramvyn)

Du kan välja beräkningsmetod för diagram i rapporter. Observera att detta inte stöds för [!UICONTROL Automated Personalization] (AP)-aktiviteter.

Om du vill komma åt alternativet [!UICONTROL Counting Methodology] när du visar en rapport i diagramläge klickar du på listrutan **[!UICONTROL My Primary Goal]** och väljer sedan beräkningsmetoden.

Beräkningsmetoden är densamma som den som valts i dialogrutan [!UICONTROL Settings], som beskrivs ovan.

![Räkningsmetod](/help/main/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

Som standard ritas diagrammet i [!UICONTROL Daily]-läge.

Du kan ändra läge genom att klicka på listrutan [!UICONTROL Daily] och sedan välja ett kumulativt alternativ.

![Kumulativ](/help/main/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>Namnet på den här listrutan varierar beroende på det valda läget.

Det finns fyra lägen för Automatiskt mål-aktiviteter: Daglig kontroll, Daglig målkontroll, Kumulativ kontroll och Kumulativ målkontroll.

Standardordningen som diagrammet ritas i är följande:

* **A/B-tester (inklusive Automatisk allokering och Automated Personalization)**: Den ordning i vilken upplevelsen skapas, i fallande ordning.
* **Experience Targeting (XT)**: Upplevelseordning i aktiviteten.
* **Multivariata tester (MVT)**: Alfabetiskt efter upplevelsenamn.
* **Recommendations**: Den ordning i vilken upplevelsen skapas, i fallande ordning.

När du arbetar med alternativen för Räkningsmetod bör du tänka på följande:

* För [Automatisk målaktivitet](/help/main/c-activities/auto-target/auto-target-to-optimize.md) finns det inget alternativ för att välja &quot;Besökare&quot; som beräkningsmetod. Automatiskt mål är den enda aktivitetstypen som du inte kan rita upp av besökare.
* För aktiviteter som använder [Analytics som rapportkälla (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) kan du inte rita in besökare, besök eller Impression kumulativt.

## Arbeta med diagram som har mer än 16 upplevelser i aktiviteten

Om en aktivitet har färre än 16 upplevelser ritas varje upplevelse i en annan färg i diagrammet.

Om en aktivitet har fler än 16 upplevelser visas de färgade linjerna för de första 16 upplevelserna i diagrammet. De återstående upplevelserna är nedtonade i rutan Erfarenheter till vänster och inga motsvarande ritytrader visas i diagrammet. Raderna för endast 16 upplevelser kan visas vid en viss tidpunkt.

Om du hovrar över någon av de grå upplevelserna visas en ny grå ritbordslinje som motsvarar den upplevelsen tillfälligt i diagrammet. Om du vill visa ritlinjen för en gråtonad upplevelse i en färg kan du avmarkera en upplevelse som visas i färg genom att klicka på dess namn och sedan välja önskad gråton genom att klicka på dess namn.

Följande bild visar en aktivitets diagram med 26 upplevelser:

![graph_1 image](assets/graph_1.png)

Diagrammet visar linjerna för de första 16 upplevelserna (vissa överlappar, så det verkar som om det finns färre än 16 linjer). Den färgade punkten i rutan Erfarenheter till vänster bredvid varje upplevelsenamn anger att upplevelsens rityta visas i motsvarande färg.

Om du bläddrar nedåt i rutan Erfarenheter kommer du att märka att namnen för de 17 till 26:e upplevelserna är nedtonade, vilket visas på följande bild:

![graph_2 image](assets/graph_2.png)

Om du hovrar över en av de grå upplevelserna visas en ny grå ritbordslinje som motsvarar den upplevelsen tillfälligt i diagrammet.

Anta att du vill visa ritlinjen för Experience R och att du inte vill se raden för Experience P. Du kan klicka på Experience P:s namn för att avmarkera det och sedan klicka på Experience R:s namn för att markera det, så som visas nedan:

![graph_3 image](assets/graph_3.png)
