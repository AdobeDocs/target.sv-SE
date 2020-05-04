---
keywords: troubleshooting;metric discrepancies;FAQ;reports
description: Lista med vanliga frågor om rapportering i Adobe Target.
title: Vanliga frågor om rapportering för Adobe Target
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 9168a8f14ad45dfc48ad5c314df61ee8c02156d5

---


# Vanliga frågor om rapportering{#reporting-faq}

Lista med vanliga frågor om rapportering i [!DNL Target].

## Varför innehåller XT-rapporter ( [!UICONTROL Experience Targeting] ) mätvärden för kontrollupplevelser?

XT-aktiviteter ska alltid ha en kontrollupplevelse. Om du använder en XT-aktivitet på ungefär samma sätt som en [!UICONTROL A/B-testaktivitet] , vilket är ett ganska vanligt scenario, är data för kontrollupplevelsen användbara. Du kan ignorera data om kontrollupplevelsen om du inte tycker att de är användbara i dina rapporter.

## Varför är antalet besök lägre i [!DNL Target] än i andra [!DNL Adobe Experience Cloud] lösningar? {#section_7E626FDB417E41B8B58BBF30FB207409}

Mätvärden, t.ex. besök, som rapporteras av [!DNL Target] kommer alltid att vara lägre än det rapporterade antalet i andra [!DNL Experience Cloud] lösningar av flera orsaker:

* [!DNL Target] räknar endast besök för besökare som är kvalificerade för aktiviteten. Andra lösningar kräver besök för besökare som visar sidan, oavsett vilken aktivitet som fört dem till sidan.
* Det kan finnas situationer där olika aktiviteter konkurrerar om samma plats (ömsesidigt uteslutande). Det innebär att besökarna ser olika innehåll på en webbsida, vilket påverkar de mätvärden som rapporteras av [!DNL Target].

## Varför finns det inga data tillgängliga för min aktivitetsrapport? {#section_E4722F6445884130951DF79981C8289B}

Om en aktivitets innehåll levererades till användarna men rapporten inte innehåller några data kontrollerar du att rätt miljö ([värdgrupp](/help/administrating-target/hosts.md)) har valts i rapportens inställningar.

Om du har valt en utvecklingsmiljö kan följande felmeddelande visas: &quot;Det finns inga tillgängliga data för de valda rapportinställningarna.&quot;

Så här ändrar du miljön för en aktivitetsrapport:

1. Klicka på **[!UICONTROL Aktiviteter]**, klicka på önskad aktivitet i listan och sedan på fliken **[!UICONTROL Rapporter]** .
1. Klicka på kugghjulsikonen för att konfigurera rapportinställningar.

   ![Dialogrutan A/B-inställningar](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >Kugghjulsikonen är inte tillgänglig för [!UICONTROL Automated Personalization] (AP)-rapporter.

1. Välj **[!UICONTROL Produktion]** i listrutan **[!UICONTROL Miljö]**.

   Rapportdata kanske inte är tillgängliga om du har valt en utvecklingsmiljö.

1. Klicka på **[!UICONTROL Spara]**.

Mer information om miljöer finns i [Värdar](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Varför är trafiken delad mellan mina upplevelser ojämn i min A/B- eller MVT-aktivitet? {#uneven}

Jag ställer till exempel in att trafikdelningen ska vara 50/50 eller 33/33/33, men jag ser en oerhört annorlunda fördelning mellan upplevelserna i rapporten.

Det finns många orsaker till ojämna trafikdelningar i [!DNL Target] rapporteringen:

* När en [!DNL Target] aktivitet startas för första gången kan trafikdistributionen bli ojämn på grund av edge node-arkitekturen som [!DNL Target] använder för att optimera upplevelseleveransen. Det bästa sättet är att ge en aktivitet lite tid att samla in ytterligare data och distributionen normaliseras. Mer information om arkitektur och Edge-noder finns i [!DNL Adobe Target] Så fungerar [](/help/c-intro/how-target-works.md)Adobe Target.
* Vilket normaliserande mätvärde använder du? Om du befinner dig i [!DNL Target] eller [!DNL Analytics] och använder mätvärdet för **[!UICONTROL besök]** måste du komma ihåg att det [!DNL Target] är ett besöksbaserat system och att trafikfördelningen för ett A/B- eller MVT-test tilldelas på besökarnivå. Om du undersöker aktivitetsresultaten med **[!UICONTROL Visits]** -måttet kan trafikfördelningen därför bli ojämn eftersom vissa besökare kan ha flera besök.
* Det bästa sättet att göra A/B- och MVT-tester är att se till att trafikspliterna är jämna. Genom att ändra trafikfördelningen mellan upplevelser (t.ex. från 90/10 till 50/50) under ett test kan besökarna bli ojämna över olika upplevelser.
* Om du följer ovanstående metodtips och trafikdelningen inte normaliseras över tid bör du kontrollera följande:

   * Använder du det senaste at.js-biblioteket? Mer information om den aktuella versionen och tillhörande versionsinformation finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)för at.js.

   * Är det ett omdirigeringstest? Felaktig timing för taggar som utlöses på sidan kan leda till ojämna trafikdelningar, särskilt när du använder [!DNL Analytics] som datakälla för en [!DNL Target] aktivitet. Mer information om hur du åtgärdar ojämn trafikfördelning för en omdirigeringsaktivitet med Analytics for Target (A4T) finns i [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
