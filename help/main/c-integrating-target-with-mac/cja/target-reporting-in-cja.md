---
keywords: kundreseanalys;kundreseanalys för mål;rapportkälla för kundreseanalys;kundreseanalys som rapportkälla för mål;målrapportering i cja; målrapportering i Customer Journey Analytics
description: Använd [!DNL Target] rapportering i [!DNL Adobe Customer Journey Analytics] för att skapa aktiviteter baserade på  [!DNL Customer Journey Analytics] konverteringsstatistik och målgruppssegment och använd [!DNL Customer Journey Analytics] rapporter för att undersöka resultaten.
title: Vad är  [!DNL Target] rapportering i [!DNL Adobe Customer Journey Analytics]?
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 0%

---

# [!DNL Target] rapporterar i [!DNL Adobe Customer Journey Analytics]

Integrationen mellan [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} och [!DNL Target] ger kraftfulla analys- och tidsbesparande verktyg för optimeringsprogrammet.

De främsta fördelarna med att använda [!DNL Customer Journey Analytics] som rapportkälla för [!DNL Target] är:

* Marknadsförarna kan när som helst dynamiskt tillämpa [!DNL Customer Journey Analytics]-framgångsmått på [!DNL Target]-aktivitetsrapporter. Du behöver inte ange allt innan du kör aktiviteten.
* Marknadsförarna kan utnyttja [!DNL Customer Journey Analytics] funktioner, som [panelen Experimentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, för att ytterligare analysera webbplatspersonaliseringen.
* Marknadsförare kan ha en enda rapportkälla för [!DNL Adobe Journey Optimizer] och [!DNL Target]. Båda personaliseringsprodukterna kan anslutas till [!DNL Customer Journey Analytics] för en mer helhetsbild av din webbpersonalisering.

## Överväganden

Tänk på följande information innan du använder integreringen [!DNL Customer Journey Analytics] och [!DNL Target]:

>[!IMPORTANT]
>
>Den här integreringen är inte densamma som [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Implementeringen och de aktivitetstyper som stöds är olika. Se till att du läser den här artikeln noggrant innan du använder integreringen för dina [!DNL Target]-aktiviteter.

* Om du vill använda [!DNL Customer Journey Analytics] som rapportkälla för [!DNL Target] måste både du och ditt företag ha tillgång till [!DNL Customer Journey Analytics] och till [!DNL Target]. Om du behöver tillgång till någon av lösningarna kontaktar du organisationens administratör eller din kontorepresentant.
* Om du vill skapa [!DNL Target] aktiviteter med [!DNL Customer Journey Analytics]-rapportering måste du ha rollen [!UICONTROL Approver] eller [!UICONTROL Editor] i [!DNL Target].
   * Om du har ett [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905)-konto kan du läsa [Ange roller och behörigheter](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*.
   * Om du har ett [Target Premium](/help/main/c-intro/intro.md#premium)-konto kan du läsa [Roller och behörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) i *Enterprise-användarbehörigheter*.

* Du måste vara en del av en roll i [!DNL Adobe Experience Platform] för att kunna konfigurera en [!DNL Target]-aktivitet med [!DNL Customer Journey Analytics] som rapportkälla. Mer information finns i [Lägg till en roll i [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank} i *Konfigurera behörigheter* i *Självstudiekursen för dataarkitekter och ingenjörer.*
* Beroende på dina inställningar kan rapporteringen ändras per aktivitet eller på organisationsnivå. Se [Reporting Cloud Solution](/help/main/administrating-target/reporting.md#solution) i *Konfigurera rapportering i Target*.
* Använd en rapportkälla eller en annan. Du kan inte samla in data för en enskild aktivitet till flera rapportkällor.
* När du anger [!DNL Customer Journey Analytics] som rapportkälla uppmanas du att ange sandlådan för rapportering. Under konfigurationen visas bara de sandlådor som du har åtkomst till.
* Befintliga [!DNL Target]-aktiviteter fortsätter att använda datainsamlingen [!DNL Target] och påverkas inte av att den här integreringen aktiveras.
* Om du vill använda den här integreringen är den implementeringsmetod som rekommenderas [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} och [!DNL Target] implementerad via [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Om du för närvarande inte har [!DNL Adobe Experience Platform Web SDK] implementerat kan du även skapa en [[!DNL Adobe Analytics] källanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) som hämtar data till [!DNL Adobe Experience Platform]. Om du tänker använda den här metoden måste du välja en [!DNL Analytics]-rapportsvit bredvid [!DNL Adobe Experience Platform]-sandlådan som du använder med [!DNL Customer Journey Analytics].

  ![Alternativ för sandlåda i dialogrutan Rapporteringsinställningar](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >Om du använder en [!DNL Adobe Analytics]-källanslutning får du rapporter i både [!DNL Adobe Analytics] och [!DNL Customer Journey Analytics]. På grund av olika algoritmer mellan båda lösningarna är det dock inte troligt att resultatet matchar.

* Om du har frågor om timing kan du läsa [Fördröjningsöverväganden](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank} i *Vanliga frågor* i *[!DNL Adobe Customer Analytics]handboken*.

## Aktivitetstyper som stöds {#supported-activities}

Följande aktivitetstyper stöds när du använder JavaScript-biblioteket [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} eller [ at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} :

| Typ av aktivitet | Stöds? |
|--- |--- |
| [A/B-aktivitet med manuell trafikdelning](/help/main/c-activities/t-test-ab/test-ab.md) | Ja |
| [A/B-aktivitet med Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Nej |
| [A/B-aktivitet med Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Nej |
| [Experience Targeting (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Ja |
| [Multivariata tester (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Ja |
| [Automated Personalization-aktivitet (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Nej |
| [Rekommendationsaktivitet](/help/main/c-recommendations/recommendations.md) | Ja |

## Skapa en aktivitet som använder [!DNL Customer Journey Analytics] som rapportkälla

Att skapa en [!DNL Target]-aktivitet som använder [!DNL Customer Journey Analytics] som rapportkälla liknar att konfigurera en vanlig [!DNL Target]-aktivitet.

>[!TIP]
>
>Du kan också ange att [!DNL Target] använder rapportering i [!DNL Customer Journey Analytics] för alla aktiviteter som skapas i ditt konto (**[!UICONTROL Administration]** > **[!UICONTROL Reporting]** > **[!UICONTROL Reporting Experience Cloud Solution]**). Mer information finns i *Reporting Cloud Solution* i [Konfigurera rapportering i [!DNL Target]](/help/main/administrating-target/reporting.md#solution).

1. Klicka på **[!UICONTROL Create Activity]** i listan **[!UICONTROL Activities]**, markera sedan aktivitetstypen (enligt aktivitetsdiagrammet [som stöds ovan](#supported-activities)) och börja konfigurera aktiviteten.
1. När du kommer till sidan **[!UICONTROL Goals & Settings]** i det tredelade arbetsflödet för att skapa aktiviteter väljer du **[!DNL Customer Journey Analytics]** som rapportkälla.

   ![Customer Journey Analytics som alternativ för rapportkälla](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >Rapporteringskällan kan inte ändras efter att en [!DNL Target]-aktivitet har publicerats.

1. Markera en sandlåda.

   Du ser bara de sandlådor som du har åtkomst till i den här listrutan. Om en eller flera av de sandlådor som du har åtkomst till saknas i listan kontrollerar du att du har åtkomst till sandlådan. Kontakta [kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du fortsätter att se problem.

   ![Välj sandlådealternativ](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. Ange aktivitetsmålet.

   Välj ett framgångsmått som ska användas som mål för varje aktivitet. Du kan välja ett av [!DNL Target]-konverteringsmåtten eller använda ett [!DNL Customer Journey Analytics]-mått.

   ![Använd ett Customer Journey Analytics-måttalternativ under Målmått](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. Klicka på **[!UICONTROL Save & Close]**.

## Konfigurera en [!DNL Customer Journey Analytics]-anslutning

När en [!DNL Target]-aktivitet har skapats måste du skapa en anslutning i [!DNL Customer Journey Analytics]. Om du redan har en anslutning kan du använda den befintliga anslutningen och gå vidare till steg 4 nedan. Med anslutningen kan [!DNL Customer Journey Analytics] börja dra data från datauppsättningen för rapportering.

1. Klicka på **[!UICONTROL Create a new connection]** på sidan [!DNL Customer Journey Analytics].**[!UICONTROL Connections]**

   ![Skapa ny anslutningslänk i [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. Konfigurera din [anslutning och dina datainställningar](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank} med rätt information.
1. Lägg till den händelsedatamängd som du använde när du konfigurerade din datastream.
1. Lägg till **[!UICONTROL Adobe Target Classification Events]**-sökdatauppsättningen och klicka sedan på **[!UICONTROL Next]**.

   ![Dialogrutan Lägg till datauppsättningar i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. Konfigurera din händelsedatamängd.

   Mer information finns i [Lägga till och konfigurera datauppsättningar](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} i *Skapa en anslutning* i *[!DNL Adobe Customer Journey Analytics]handboken*.

1. Konfigurera din uppslagsdatauppsättning med fältet [!UICONTROL Key] som&quot;nyckel&quot; och nyckelfältet [!UICONTROL Matching] med följande sökväg:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Dialogrutan Adobe Target Classifications i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. Klicka på **[!UICONTROL Add datasets]** och sedan på **[!UICONTROL Save]** på nästa skärm för att slutföra anslutningen.

## Ställ in datavyer

Konfigurera en datavy i [!DNL Customer Journey Analytics]. En datavy säkerställer att data från anslutningen kan användas på rätt sätt.

1. Konfigurera datavyn och se till att den pekar på anslutningen som du skapade ovan.

   Mer information finns i [Skapa eller redigera en datavy](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} i *[!DNL Adobe Customer Journey Analytics]handboken*.

1. Om du vill visa dina [!DNL Target]-data i [!DNL Customer Journey Analytics] på rätt sätt måste du lägga till följande fält från uppsättningen med uppslagsdata som dimensioner:

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Alternativ för namn och ID:n i Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Om du vill använda [!DNL Target] dimensioner på panelen [!UICONTROL Experimentation] ställer du in följande kontextetiketter:

   * Använd Experimentationsexperiment för [!UICONTROL Activity Name].
   * [!UICONTROL Experience Name], använd Experimentationsvariant.

   ![Kontextetiketter på panelen Experimentation](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. Slutför konfigurationen av andra fält och klicka sedan på **[!UICONTROL Save and continue]** när du är klar.
