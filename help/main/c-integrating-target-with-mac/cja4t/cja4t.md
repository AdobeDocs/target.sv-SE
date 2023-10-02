---
keywords: cja4t;kundreseanalys;kundreseanalys för mål;kundreseanalys, rapportkälla;kundreseanalys som rapportkälla för mål
description: Använd [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (A4T) för att skapa aktiviteter baserade på [!DNL Customer Journey Analytics] konverteringsstatistik och målgruppssegment samt användning [!DNL Customer Journey Analytics] rapporter för att undersöka resultaten.
title: Vad är [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (CJA4T)?
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 2480578b3e26cfbb5881700c2a09b5b6e2dabba2
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 0%

---

# [!DNL Adobe Customer Journey Analytics] som rapportkälla för [!DNL Adobe Target] (CJA4T)

The [!DNL Customer Journey Analytics for Target] (CJA4T) integration mellan [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} och [!DNL Target] innehåller kraftfulla analys- och tidsbesparande verktyg för optimeringsprogrammet.

De främsta fördelarna med att använda [!DNL Customer Journey Analytics] som rapportkälla för [!DNL Target] är:

* Marknadsförare kan tillämpa [!DNL Customer Journey Analytics] framgångsmått till [!DNL Target] aktivitetsrapporter när som helst. Du behöver inte ange allt innan du kör aktiviteten.
* Utnyttja [!DNL Customer Journey Analytics] funktioner, som [Panelen Experimentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html){target=_blank}för att ytterligare analysera webbplatspersonaliseringen.
* ha en enda rapportkälla för [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/cja-ajo.html){target=_blank} och [!DNL Target]. Båda personaliseringsprodukterna kan kopplas till [!DNL Customer Journey Analytics] för en mer helhetssyn på er webbpersonalisering.

## Överväganden

Tänk på följande information innan du använder CJA4T-integreringen:

* Används [!DNL Customer Journey Analytics] som rapportkälla för [!DNL Target], både du och ditt företag måste ha tillgång till [!DNL Customer Journey Analytics] och till [!DNL Target]. Om du behöver tillgång till någon av lösningarna kontaktar du organisationens administratör eller din kontorepresentant.
* Skapa [!DNL Target] aktiviteter med [!DNL Customer Journey Analytics] måste du ha antingen[!UICONTROL Approver]&quot; eller &quot;[!UICONTROL Editor]&quot; roll i [!DNL Target].
   * Om du har en [Målstandard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) konto, se [Ange roller och behörigheter](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *Användare*.
   * Om du har en [Mål Premium](/help/main/c-intro/intro.md#premium) konto, se [Roller och behörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) in *Enterprise-användarbehörigheter*.

* Du måste ingå i en roll i [!DNL Adobe Experience Platform] för att konfigurera en [!DNL Target] aktivitet med [!DNL Customer Journey Analytics] som rapportkälla. Mer information finns i [Lägg till en roll i [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions.html){target=_blank} in *Konfigurera behörigheter* i *Självstudiekurs om dataarkitekt och ingenjör.*
* Beroende på dina inställningar kan rapporteringen ändras per aktivitet eller på organisationsnivå. Se [Reporting Cloud Solution](/help/main/administrating-target/reporting.md#solution) in *Konfigurera rapportering i mål*.
* Använd en rapportkälla eller en annan. Du kan inte samla in data för en enskild aktivitet till flera rapportkällor.
* När du anger [!DNL Customer Journey Analytics] som rapportkälla uppmanas du att ange sandlådan för rapportering. Under konfigurationen visas bara de sandlådor som du har åtkomst till.
* Alla befintliga [!DNL Target] aktiviteter fortsätter att använda [!DNL Target] datainsamling och påverkas inte av att CJA4T aktiveras.
* Om du vill använda CJA4T har implementeringsmetoden [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. Om du inte har [!DNL Adobe Experience Platform Web SDK] implementerad kan du även skapa en [[!DNL Adobe Analytics] källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) för att föra in data i [!DNL Adobe Experience Platform].
* Om du har frågor om timing kan du läsa [Svarstidsfrågor](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank} in *Vanliga frågor* i *[!DNL Adobe Customer Analytics]Guide*.

## Aktivitetstyper som stöds {#supported-activities}

Följande aktivitetstyper stöds vid användning av [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} JavaScript-bibliotek:

| Typ av aktivitet | CJA4T-kompatibel? |
|--- |--- |
| [A/B-aktivitet med manuell trafikdelning](/help/main/c-activities/t-test-ab/test-ab.md) | Ja |
| [A/B-aktivitet med automatisk fördelning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Nej |
| [A/B-aktivitet med automål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Nej |
| [Experience Targeting (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Ja |
| [Multivariata tester (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Ja |
| [Automated Personalization-aktivitet (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Nej |
| [Recommendations-aktivitet](/help/main/c-recommendations/recommendations.md) | Ja |

## Skapa en aktivitet som använder [!DNL Customer Journey Analytics] som rapportkälla

Skapa en [!DNL Target] aktivitet som använder [!DNL Customer Journey Analytics] eftersom rapporteringskällan liknar att ställa in en vanlig [!DNL Target] aktivitet.

1. Från **[!UICONTROL Activities]** lista, klicka på **[!UICONTROL Create Activity]** väljer du sedan aktivitetstyp (enligt [aktivitetsdiagram som stöds ovan](#supported-activities)) och börja konfigurera aktiviteten.
1. När du kommer till **[!UICONTROL Goals & Settings]** sidan för arbetsflödet för att skapa en aktivitet i tre delar, välja **[!DNL Customer Journey Analytics]** som rapportkälla.

   ![Customer Journey Analytics som alternativ för rapportkälla](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >Rapporteringskällan kan inte ändras efter en [!DNL Target] aktivitet blir verklighet.

1. Markera en sandlåda.

   Du kan bara se de sandlådor som du har åtkomst till i den här listrutan. Om en eller flera av de sandlådor som du har åtkomst till saknas i listan kontrollerar du att du har åtkomst till sandlådan. Kontakt [Kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du fortsätter att se problem.

   ![Välj sandlådealternativ](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Ange aktivitetsmålet.

   Välj ett framgångsmått som ska användas som mål för varje aktivitet. Du kan välja ett av [!DNL Target] konverteringsmått eller använda en [!DNL Customer Journey Analytics] mätvärden.

   ![Använd måttalternativet Customer Journey Analytics under Målmått](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Klicka på **[!UICONTROL Save & Close]**.

## Konfigurera en [!DNL Customer Journey Analytics] anslutning

Efter [!DNL Target] aktivitet har skapats, du måste skapa en anslutning i [!DNL Customer Journey Analytics]. Om du redan har en anslutning kan du använda den befintliga anslutningen och gå vidare till steg 4 nedan. Anslutningen tillåter [!DNL Customer Journey Analytics] för att börja hämta data från datauppsättningen för rapportering.

1. I [!DNL Customer Journey Analytics], på **[!UICONTROL Connections]** sida, klicka **[!UICONTROL Create a new connection]**.

   ![Skapa ny anslutningslänk i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Konfigurera [anslutning och datainställningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} med rätt information.
1. Lägg till den händelsedatamängd som du använde när du konfigurerade din datastream.
1. Lägg till **[!UICONTROL Adobe Target Classification Events]** dataset för sökning och klicka sedan på **[!UICONTROL Next]**.

   ![Dialogrutan Lägg till datauppsättningar i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Konfigurera din händelsedatamängd.

   Mer information finns i [Lägga till och konfigurera datauppsättningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} in *Skapa en anslutning* i *Adobe Customer Journey Analytics Guide*.

1. Konfigurera din uppslagsdatauppsättning med [!UICONTROL Key] fältet som &quot;key&quot; och fältet Matching key med följande sökväg:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Adobe Target Classifications, händelsedialogruta i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Klicka **[!UICONTROL Add datasets]** och sedan klicka **[!UICONTROL Save]** på nästa skärm för att slutföra anslutningen.

## Ställ in datavyer

Konfigurera en datavy i [!DNL Customer Journey Analytics]. En datavy säkerställer att data från anslutningen kan användas på rätt sätt.

1. Konfigurera datavyn och se till att den pekar på anslutningen som du skapade ovan.

   Mer information finns i [Skapa eller redigera en datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} i *Adobe Customer Journey Analytics Guide*.

1. För att kunna se [!DNL Target] data i [!DNL Customer Journey Analytics]måste du lägga till följande fält från uppslagsuppsättningen som dimensioner:

   * Experience Name
   * Experience ID
   * Aktivitetsnamn
   * Aktivitets-ID

   ![Alternativ för namn och ID:n i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Slutför konfigurationen av andra fält och klicka sedan på **[!UICONTROL Save and continue]** när det är klart.
