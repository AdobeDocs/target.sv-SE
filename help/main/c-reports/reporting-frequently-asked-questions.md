---
keywords: felsökning;måttskillnader;vanliga frågor och svar;rapporter;ny besökare;återkommande besökare;återkommande besökare;återkommande besökare;återbesök;nytt besök
description: Utforska en lista med vanliga frågor och svar om rapportering från Adobe [!DNL Target] .
title: Var hittar jag svar på frågor om  [!DNL Target] rapportering?
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 0%

---

# Vanliga frågor om rapportering

Lista med vanliga frågor om rapportering i [!DNL Adobe Target].

## Hur räknas värdena för nya besökare och återkommande besökare? {#methodology}

En ny besökares första besök varar så länge besökaren är aktiv på webbplatsen.
Om användaren är inaktiv i 30 minuter eller längre återställs sessionen. Om du återställer sessionen innebär det att besökaren blir en återkommande besökare vid nästa besök eller blir aktiv igen efter 30 minuters inaktivitet.
Om besökaren förflyttar sig runt platsen var 29:e minut under en hel dag räknas besökaren som en ny besökare under hela dagen. Sessionen återställdes aldrig eftersom besökaren aldrig överskridit tröskelvärdet på 30 minuter.

I följande information förklaras i detalj hur nya besökare och återkommande besökare räknas. Det finns också exempel på varför summan av dessa två segment inte alltid är lika med antalet besökare totalt.

### Nya besökare

En besökare inkluderas i segmentet Nya besökare om något av följande villkor uppfylls:

* Det är besökarens första besök på webbplatsen.
* Det är besökarens första besök sedan cookies rensades.
* Det är besökarens första besök på webbplatsen sedan [besökarprofilens livstid](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) har gått ut.

### Returnerande besökare

Besökaren inkluderas i segmentet Återkommande besökare om användaren tidigare besökt webbplatsen, lämnat den i minst 30 minuter och återgått till webbplatsen igen med samma cookies. Så länge en besökare återvänder inom sin profillivstid är den här besökaren en återkommande besökare.

Anta att din profillivstid är inställd på 14 dagar (standard). En besökare inkluderas i segmentet Återkommande besökare om följande villkor uppfylls:

* En besökare besöker webbplatsen för första gången och registreras som en ny besökare.
* Besökaren lämnar platsen, men återvänder sex dagar senare.

Eftersom profilens livstid är inställd på 14 dagar inkluderas den här besökaren i segmentet Returning Visitors. Om besökaren har tagit bort cookies inom den sexdagarsperioden, inkluderas besökaren i segmentet Nya besökare.

### Exempel som förklarar avvikelser mellan mätvärden

**Exempel 1**: Om de här två segmenten används i en aktivitet, läggs inte alltid segmenten Nya besökare och Återkommande besökare till det totala antalet besökare.

Ta följande exempel som exempel, med de villkor som anges ovan för nya besökare och återkommande besökare:

* En besökare besöker webbplatsen för första gången och räknas som ny besökare.
* Besökaren återvänder till webbplatsen när villkoren för återkommande besökare är uppfyllda och räknas som återkommande besökare.

Den här besökaren räknas som en enskild besökare i aktivitetens totala besökarantal även om den räknas både i segmenten för nya besökare och återkommande besökare.

**Exempel 2**: Skillnader mellan antalet för nya besökare och återkommande besökare beror också på hur du konfigurerar aktivitetens [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md).

Exempel:

Flera nya besökare besöker er webbplats och är kvalificerade för en aktivitet. Dessa nya besökare räknas in i segmentet Nya besökare. Alla dessa besökare registrerade också ett besök i den aktiviteten.

En del besökare nådde konverteringsmåttet, som konfigurerades som&quot;Öka antal och behåll användare i aktivitet&quot;. Anta att vissa av dessa användare når konverteringsmåttet flera gånger, så ökar inte konverteringsmåttet. Med tanke på konfigurationen kan vissa användare dock komma till konverteringsmåttet och sedan gå tillbaka till startsidan och kvalificera sig för aktiviteten igen för att registrera ett nytt besök.

## Varför innehåller mina [!UICONTROL Experience Targeting] (XT)-rapporter mätvärden för kontrollupplevelser?

XT-aktiviteter ska alltid ha en kontrollupplevelse. Om du använder en XT-aktivitet på ungefär samma sätt som en [!UICONTROL A/B Test]-aktivitet, vilket är ett ganska vanligt scenario, är data för kontrollupplevelsen användbara. Du kan ignorera data om kontrollupplevelsen om du inte tycker att de är användbara i dina rapporter.

## Varför är antalet besök lägre i [!DNL Target] än i andra [!DNL Adobe Experience Cloud]-lösningar? {#section_7E626FDB417E41B8B58BBF30FB207409}

Mätvärden, till exempel besök, som rapporteras av [!DNL Target] är alltid lägre än de rapporterade siffrorna i andra [!DNL Experience Cloud]-lösningar av flera anledningar:

* [!DNL Target] räknar endast besök för besökare som är kvalificerade för aktiviteten. Andra lösningar kräver besök för besökare som visar sidan, oavsett vilken aktivitet som fört dem till sidan.
* Det kan finnas situationer där olika aktiviteter konkurrerar om samma plats (ömsesidigt uteslutande). Det innebär att besökarna ser olika innehåll på en webbsida, vilket påverkar de måttnummer som rapporteras av [!DNL Target].

## Varför finns det inga data tillgängliga för min aktivitetsrapport? {#section_E4722F6445884130951DF79981C8289B}

Om en aktivitets innehåll levererades till besökare men rapporten inte innehåller några data, kan du få följande felmeddelande:&quot;Det finns inga data tillgängliga för de valda rapportinställningarna.&quot;

Det finns några möjliga orsaker till att data saknas i aktivitetsrapporter:

* Du har inte markerat rätt miljö i rapportens inställningar
* Du har ingen trafik tilldelad kontrollupplevelsen

### Du har inte valt rätt miljö i rapportens inställningar:

Om en aktivitets innehåll levererades till användarna men rapporten inte innehåller några data kontrollerar du att rätt miljö ([värdgrupp](/help/main/administrating-target/hosts.md)) är markerad i rapportens inställningar.

Så här ändrar du miljön för en aktivitetsrapport:

1. Klicka på **[!UICONTROL Activities]**, klicka på önskad aktivitet i listan och klicka sedan på fliken **[!UICONTROL Reports]**.
1. Klicka på kugghjulsikonen för att konfigurera rapportinställningar.

   ![Dialogrutan A/B-inställningar](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. I listrutan **[!UICONTROL Environment]** väljer du **[!UICONTROL Production]**.

   Rapportdata kanske inte är tillgängliga om du har valt en utvecklingsmiljö.

1. Klicka på **[!UICONTROL Save]**.

Mer information om miljöer finns i [Värdar](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

### Du har ingen trafik tilldelad kontrollupplevelsen

Om en aktivitets innehåll levererades till användarna men rapporten inte innehåller några data, måste du se till att du använder en upplevelse med trafik som kontrollupplevelse.

1. Klicka på **[!UICONTROL Activities]**, klicka på önskad aktivitet i listan och klicka sedan på fliken **[!UICONTROL Reports]**.
1. Klicka på kugghjulsikonen för att konfigurera rapportinställningar.

1. Välj en upplevelse som tar emot trafik i listrutan **[!UICONTROL Control]**.

1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>Mer information om hur du uppdaterar en [!UICONTROL Automated Personalization]-aktivitet (AP) och ändrar kontrollupplevelsen till en upplevelse som tar emot trafik finns i [Välja kontrollen för din Automated Personalization- eller Auto-Target-aktivitet](/help/main/c-activities/t-automated-personalization/experience-as-control.md).


## Varför är trafiken delad mellan mina upplevelser ojämn i min A/B- eller MVT-aktivitet? {#uneven}

Jag ställer till exempel in att trafikuppdelningen ska vara 50/50 eller 25/25/25/25, men jag ser en oerhört annorlunda fördelning mellan upplevelserna i rapporten. Det finns flera orsaker till ojämnt antal besökare i [!DNL Target]-rapportering:

* När en [!DNL Target]-aktivitet startas för första gången kan trafikfördelningen vara ojämn på grund av edge node-arkitekturen som [!DNL Target] använder för att optimera upplevelseleveransen. Det bästa sättet är att ge en aktivitet lite tid att samla in mer data och distributionen normaliseras. Mer information om [!DNL Adobe Target]-arkitekturen och Edge-noder finns i [Hur Adobe Target fungerar](/help/main/c-intro/how-target-works.md).
* Om du är i [!DNL Target] eller [!DNL Analytics] och använder måttet **[!UICONTROL Visits]** måste du komma ihåg att [!DNL Target] är ett besöksbaserat system och trafikfördelningen för ett A/B- eller MVT-test tilldelas på besökarnivå. Om du undersöker aktivitetsresultat med måttet **[!UICONTROL Visits]** kan trafikfördelningen därför se ojämn ut eftersom vissa besökare kan ha flera besök. Besökare är standardmätvärdet för normalisering när aktivitetsprestanda utvärderas.
* Det bästa sättet att göra A/B- och MVT-tester är att se till att trafikspliterna är jämna. Genom att ändra trafikfördelningen mellan upplevelser (t.ex. från 90/10 till 50/50) under ett test kan besökarna bli ojämna över olika upplevelser. Den lägre trafikupplevelsen kanske aldrig &quot;hinner ikapp&quot;.
* Om du följer ovanstående metodtips och trafikdelningen inte normaliseras över tid bör du kontrollera följande:

   * Använder du det senaste at.js-biblioteket? Mer information om den aktuella versionen och tillhörande versionsinformation finns i [versionsinformationen för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank}.

   * Är det ett omdirigeringstest? Felaktig timing för taggar som utlöses på sidan kan leda till ojämna trafikdelningar, särskilt när [!DNL Analytics] används som datakälla för en [!DNL Target]-aktivitet. Mer information om hur du åtgärdar ojämn trafikfördelning för en omdirigeringsaktivitet med Analytics for Target (A4T) finns i [Omdirigeringserbjudanden - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
