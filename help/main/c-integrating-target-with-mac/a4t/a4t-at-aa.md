---
keywords: a4t;A4T;Analyser som rapportkälla för Target
description: Lär dig hur du skapar aktiviteter för automatisk fördelning och automatisk målanpassning i Adobe [!DNL Target] som använder Analytics som rapportkälla (A4T).
title: Har A4T stöd för automatisk fördelning och automatisk målanpassning?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: e8fc28ef2497c1dfea523a769c9c817cbd74fea2
workflow-type: tm+mt
source-wordcount: '1624'
ht-degree: 0%

---

# A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter

The [!DNL Adobe Target]-till-[!DNL Adobe Analytics] integrering, kallas [Analyser för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) har stöd för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet.

Med A4T-integreringen kan du:

* Använd [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)Flerarmad bandit-kapacitet som driver trafik till vinnande upplevelser.
* Använd [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)En enastående maskininlärningsalgoritm för att välja den bästa upplevelsen för varje besökare. AutoTarget väljer den bästa upplevelsen baserat på användarnas profiler, beteenden och kontext när ett [!DNL Adobe Analytics] målmått och [!DNL Adobe Analytics]- omfattande rapporterings- och analysfunktioner.

Se till att du har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Om du använder `analyticsLogging = client_side`måste du också skicka `sessionId` värde till [!DNL Analytics]. Mer information finns i [Analyser för målrapportering (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} i *Adobe Target SDKs* guide.

Så här kommer du igång:

1. När du skapar en A/B-testaktivitet, på **[!UICONTROL Targeting]** väljer du något av följande alternativ som **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Alternativ för trafikallokeringsmetoder: Manuell, Automatisk fördelning och Automatisk målning](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Mer information och stegvisa instruktioner finns i [Skapa en automatiskt fördelad aktivitet](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) och [Skapa en Automatisk målaktivitet](/help/main/c-activities/auto-target/create-auto-target.md).

1. Välj **[!UICONTROL Adobe Analytics]** för **[!UICONTROL Reporting Source]** på **[!UICONTROL Goals & Settings]** och välj den rapportsvit som motsvarar det optimeringsmål du vill ha.

   ![Avsnittet Rapporteringskälla på sidan Mål och inställningar](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Välj ett primärt målmått. I den första listrutan kan du antingen ange ett mål i [!DNL Adobe Target] (som sedan spåras av [!DNL Adobe Analytics] som måttet&quot;Aktivitetskonverteringar&quot;), eller, om du vill använda en [!DNL Analytics] som ditt mål.

   * Används [!DNL Adobe Target] om du vill ange optimeringsmålet väljer du **[!UICONTROL Conversion]** och ange sedan vilken åtgärd som målgruppen måste vidta för att ange att konverteringsmålet har uppnåtts.
   * Om du väljer **[!UICONTROL Use an Analytics metric]** Då får du välja vilken typ av optimeringskriterium som ska användas.  Se [Målmått och optimeringskriterier som stöds](#supported) nedan om du vill ha mer information. När du har angett optimeringskriteriet kan du välja ett kompatibelt mätvärde från [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda en färdig fil [!DNL Analytics] konverteringsmått eller [!DNL Analytics] anpassad händelse.


1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] använder det valda måttet för att optimera aktiviteten och för besökarna till upplevelsen som maximerar målmåttet.

   eller

   [!UICONTROL Auto-Target] använder de mätvärden du väljer för att optimera aktiviteten och locka besökarna till en personaliserad, bästa upplevelse.

1. Använd **[!UICONTROL Reports]** för att visa aktivitetens rapportering och klicka på **[!UICONTROL View in Analytics]** att fördjupa och ytterligare segmentera rapporteringsdata i en Adobe Analytics Workspace. Du kan följa självstudiekurserna nedan för att se hur du konfigurerar dina rapporter i arbetsytan:
* Automatisk fördelning: se [Ställa in A4T-rapporter i Analysis Workspace för automatisk fördelning av aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*
* Automatiskt mål: se [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.

## Målmått och optimeringskriterier som stöds {#supported}

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] gör att du kan välja någon av följande måtttyper som det primära målmåttet för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

Men [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] modellerna optimeras för **normaliserad** versioner av dessa mätvärden, med exakt normalisering beroende på typ av aktivitet. Alternativen för optimeringskriterier för varje typ av aktivitet förklaras i tabellen nedan:

| Typ av aktivitet | Mätkälla | Optimeringsvillkor | Beskrivning |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Automatisk allokering | Analyser | Maximera konverteringsgraden för unika besökare | Modeller försöker hitta upplevelsen med den högsta unika besökarkonverteringsgraden, som definieras som antalet besökare för vilka analysmåttet inte är noll, dividerat med det totala antalet besökare (som tog emot den upplevelsen). Detta innebär att mätvärdet behandlas som binärt - antingen 0 eller 1 för varje unik besökare i aktiviteten.   Använd det här alternativet om du bara bryr dig om hur mycket användare som gör en viss åtgärd eller när flera konverteringshändelser för en enskild användare inte är meningsfulla. |
| Automatisk allokering | Analyser | Maximera måttvärde per besökare | Modeller försöker hitta upplevelsen med det högsta mätvärdet per besökare, vilket definieras som det totala värdet av mätvärdet för alla användare som exponeras för den upplevelsen, dividerat med det totala antalet besökare som erhöll den upplevelsen. Det innebär att mätvärdena kan ta vilket värde som helst för varje unik besökare i aktiviteten. Om en besökare till exempel konverterar flera gånger räknas varje konvertering.  Använd det här alternativet om du är intresserad av att maximera ett kontinuerligt mått som total intäkt, eller om flera konverteringshändelser för en enskild användare är mer meningsfulla än en (t.ex. flera order är värda mer än en) |
| Automatisk allokering | Mål | (kan inte konfigureras) | Måttet behandlas som binärt och den unika besökarkonverteringsgraden maximeras. |
| Automatiskt mål | Analyser | Maximera konverteringsgraden för unika besök | Till skillnad från automatisk fördelning eller manuella A/B-tester innebär det personliga syftet med Automatiskt mål att upplevelsen som besökaren ser kan ändras för varje nytt besök. Den lämpliga frekvensen är då en omräkningskurs som normaliseras vid besök, vilket definieras som den andel besök där ett mätvärde som inte är noll registreras. Detta är den konverteringsfrekvens som optimeras av Automatiskt mål.   På samma sätt som Automatisk allokering bör det här alternativet väljas när du bryr dig om den del av besöken där en konvertering sker, dvs. när det inte är viktigt med flera konverteringshändelser för ett enda besök. |
| Automatiskt mål | Analyser | Maximera mätvärde per besök | När mätvärdena som optimeras för är kontinuerliga (t.ex. intäkter) eller när det är meningsfullt att ha flera konverteringshändelser vid ett enda besök (t.ex. flera order), kan du välja att maximera mätvärdet per besök. Den &quot;hastighet&quot; som optimeras är det totala värdet av mätvärdet dividerat med antalet besök. |
| Automatiskt mål | Mål | (kan inte konfigureras) | Mätvärdet behandlas som binärt och den unika besökskonverteringsfrekvensen maximeras. |



Observera, att beroende på optimeringskriteriet kan vissa [!DNL Adobe Analytics] Mått stöds inte.

* [!DNL Adobe Analytics] beräknade värden stöds inte.
* [!DNL Adobe Analytics] Mätvärdena måste alltid vara segmenterbara, och om värdet per besökare/besök optimeras måste mätvärdena ha positiv polaritet (dvs. positiva värden är bättre än negativa)
* [!DNL Adobe Analytics] mått som används i [!DNL Auto-Target] Verksamheter måste finnas tillgängliga vid export från DataWarehouse.

## Begränsningar och anteckningar

Vissa begränsningar och anteckningar gäller för båda [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet. Andra begränsningar och anteckningar gäller för en aktivitetstyp eller en annan.

### Automatisk fördelning och Automatisk målgruppsanpassning {#both}

* När du använder [!DNL Adobe Analytics] som rapportkälla för [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target]bör du alltid visa rapporter i [!DNL Analytics].
* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller omvänt efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. Som förklaras i [Målmått och optimeringskriterier som stöds](#supported), beroende på aktivitetstyp och optimeringskriterier, [!DNL Target] normaliserar konverteringsmåtten automatiskt, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normalisering.


### Automatisk allokering {#aa}

* **Utbildningsfrekvens**: [!UICONTROL Auto-Allocate] fortsätter modellerna att träna varje timme som vanligt.
* **Attributionsmodeller**: [!DNL Target] använder [!DNL Adobe Analytics] standardattribueringsmodell för[!UICONTROL  Auto-Allocate] aktiviteter som använder A4T.
* **Förtroende**: Konfidensformeln som används av [!UICONTROL Auto-Allocate] aktiviteterna skiljer sig från formeln som visas som standard i [!DNL Adobe Analytics] [!UICONTROL A4T] -panelen. [Enligt beskrivning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] använder mer försiktiga konfidensintervall än med regelbundna [!UICONTROL A/B Test] verksamhet. Dessa konservativa konfidensnivåer kompenserar för upprepade utvärderingar (peeks) vid data. Därför är standardrapporten i [!DNL Adobe Analytics] visar snävare konfidensintervall jämfört med dem som används av [!UICONTROL Auto-Allocate] algoritm. Ni kan dock avgöra vilken upplevelse som prioriteras av algoritmerna utifrån vilken upplevelse som har fler unika besökare som skickas till den.
* **Vinnarstatus**: För närvarande är [&quot;Ingen vinnare ännu&quot; och &quot;vinnare&quot;-märken](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) är inte tillgängliga i [!UICONTROL A4T] panel i [!DNL Analysis Workspace]. Dessa emblem är inte heller tillgängliga om samma rapport visas i [!DNL Target]. En &quot;stjärna&quot;-bricka som visas i en [!DNL Target] rapport för [!UICONTROL Auto-Allocate] -aktivitet som använder A4T ska ignoreras. Den här ikonen visar vanliga konfidensberäkningar och inte de som används av [!UICONTROL Auto-Allocate].

### Automatiskt mål {#at}

* **Utbildningsfrekvens**: [!UICONTROL Auto-Target] modellerna fortsätter att träna var 24:e timme som vanligt. Konverteringshändelsedata kommer dock från [!DNL Analytics] fördröjs med ytterligare 6 till 24 timmar. Förseningen innebär fördelning av trafik med [!DNL Target] följer de senaste händelser som spelats in i [!DNL Analytics]. Den här fördröjningen har störst effekt de första 48 timmarna efter att en aktivitet initialt har aktiverats. Aktivitetens prestanda kommer att spegla bättre [!DNL Analytics] konverteringsbeteende efter fem dagar. Överväg att använda [!UICONTROL Auto-Allocate] i stället för [!UICONTROL Auto-Target] för korttidsverksamhet där den största trafiken förekommer inom de fem första dagarna av verksamhetens livstid.
* När du använder [!DNL Analytics] som datakälla för en [!UICONTROL Auto-Target] aktivitet, sessionerna avslutas efter sex timmar. Konverteringar som inträffar efter sex timmar räknas inte.

Mer information finns i [Attributmodeller och uppslagsfönster](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) i *Handbok för analysverktyg*.

## Ställa in A4T-rapporter i Analysis Workspace för aktiviteterna Automatiskt mål och Automatisk fördelning {#tutorial}

Även om det finns omfattande analysfunktioner i [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], några ändringar av standardinställningen [!UICONTROL Analytics for Target] för att automatisk allokering och automatisk målning ska kunna tolkas på rätt sätt.

Dessa ändringar är nödvändiga på grund av de nya definitionerna av konverteringsgrader som beskrivs i [Målmått och optimeringskriterier som stöds](#supported)samt skillnaderna mellan experimentella aktiviteter (manuell A/B och [!UICONTROL Auto-Allocate]) och personalisering ([!UICONTROL Auto-Target]).

De här självstudiekurserna vägleder dig igenom de rekommenderade ändringarna för analys [!UICONTROL A4T] [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet i [!UICONTROL Workspace].

Mer information finns i
* [Ställa in A4T-rapporter i Analysis Workspace för automatisk fördelning av aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.
* [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.
