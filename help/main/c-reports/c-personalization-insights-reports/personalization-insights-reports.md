---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;auto target;auto target;auto target report;auto target report;personalization;insights;automatic segments;faq;ofta questions;important attributes
description: Lär dig hur du använder specialrapporter för Automated Personalization- (AP) och Auto-Target-aktiviteter (AT) - automatiserade segment och viktiga attribut.
title: Hur använder jag Personalization Insights-rapporterna?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---

# [!UICONTROL Personalization Insights] rapporter

Två specialrapporter är tillgängliga för användare av [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT) aktiviteter: [!UICONTROL Automated Segments]- och [!UICONTROL Important Attributes]-rapporterna.

## Överväganden

Tänk på följande när du använder [!UICONTROL Personalization Insights] rapporter:

* AP- och AT-aktiviteter är tillgängliga som en del av [[!DNL Target Premium] lösningen](/help/main/c-intro/intro.md#premium). De ingår inte i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.

* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som har konfigurerats enligt följande:

   * [!DNL Target] rapportering > [!UICONTROL Conversion]

     Exempel:

     ![Målrapportering > Konvertering](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] rapportering > [!DNL Conversion]

     Exempel:

     ![Analysrapportering > Konvertering](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] rapportering > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     Exempel:

     ![Använd ett analysmått > Maximera besökskonverteringsfrekvens](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* Aktiviteter där optimeringsmålet ändrades till konvertering från intäkter efter att aktiviteten redan var aktiv stöds inte heller.

* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga om [!UICONTROL Primary Goal] har valts i listrutan [!UICONTROL Report Metric].

* [!UICONTROL Personalization Insights] rapporter stöds endast i [standardmiljön](/help/main/administrating-target/hosts.md).

* [!UICONTROL Personalization Insights] rapporter genereras bara för aktiviteter som har statusen [!UICONTROL Live] och har aktiverats och tagit emot trafik i minst 15 dagar.

## Personalization Insights Reporting - översikt {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

Målet med [!UICONTROL Personalization Insights]-rapporterna är att ge mer information om hur personaliseringsmodellerna [!UICONTROL Target] bakom dina AP- och AT-aktiviteter anpassar besökstrafiken. Algoritmen [Slumpmässig skog](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) är grunden för personaliseringsmodellerna i [!DNL Target].

Eftersom målet för [!UICONTROL Personalization Insights]-rapporterna är att förstå hur personaliseringsmodellerna i [!DNL Target] bestämde sig för att skicka vilken eller vilka besökare till vilka innehållsdelar, speglar rapporterna i [!UICONTROL Personalization Insights] bara ett undersegment av all trafik som hanteras av din AP- eller AT-aktivitet. De två rapporterna speglar i synnerhet all trafik som använde personaliseringsmodellen. [!UICONTROL Personalization Insights] rapporter tar alltså inte hänsyn till kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen.

Det finns två [!UICONTROL Personalization Insights] rapporter:

| Rapport | Information |
|--- |--- |
| [!UICONTROL Automated Segments] | Olika besökare svarar annorlunda på erbjudandena/upplevelserna i er AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av personaliseringsmodellerna i [!DNL Target] svarade på erbjudandena/upplevelserna i aktiviteten. |
| [!UICONTROL Important Attributes] | I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse. |

## Tolka attribut i Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Det finns två typer av attribut i [!UICONTROL Personalization Insights]-rapporter som används i dina AP- eller Automatiskt mål-modeller:

* **Attribut som samlas in automatiskt av Target:** [!DNL Target] använder en basdatauppsättning för att skapa sina personaliseringsalgoritmer i AP- och AT-aktiviteter som återspeglas i Personalization Insights. Se [Datainsamling för Target&#39;s Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md) för datatyper, exempelattribut och deras [!UICONTROL Personalization Insights] namnkonvention. Observera att även om dessa attribut beaktas, kanske inte alla dessa attribut används i den slutliga modellen för en enskild aktivitet.
* **Attribut som skickas till mål:** Se [Överför data för Personalization-målalgoritmer](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] erbjuder många sätt för dig att skicka in ytterligare data till [!DNL Target] för att berika basdatauppsättningen som används för att skapa dess personaliseringsalgoritmer i AP- och AT-aktiviteter:

| Datatyp | Beskrivning | Namnkonvention för datatyp |
|--- |--- |--- |
| Profilattribut, inklusive profilskript, API för profiluppdatering och profilattribut på sidan | All information som du har valt att inkludera i Target-användarprofilen.<br>Den här informationen kan komma från profilskript, information som har överförts med API:t för profiluppdatering eller parametrar för profiler i mbox som har prefixats med &quot;profile&quot;. | `Custom - Profile - [parameter name]` |
| Sidparametrar (kallas även&quot;mbox parameters&quot;) | Namn/värde-par som skickas direkt via sidkod som inte lagras i besökarens profil för framtida bruk. | `Custom - Mbox Parameter - [parameter name]` |
| Kundattribut | Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. Använd data i Adobe Analytics och Adobe Target när de har överförts. | `Custom - Customer Attributes - [parameter name]` |
| Delade målgrupper (Adobe Audience Manager eller Adobe Analytics) | Målgrupper skapade med Adobe Audience Manager eller Adobe Analytics och som delas med Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Delade målgrupper (Adobe Experience Platform/CDP i realtid) | Målgrupper som skapats med Adobe Experience Platform/CDP i realtid och som delas med Target via Destinations. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Delade attribut (Adobe Experience Platform/CDP i realtid) | Attribut som har skapats med Adobe Experience Platform/Real-time CDP och som delas med Target via Destinations. Den här funktionen finns i Beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Målgrupper/segment för rapportering i aktivitet | Målgrupper som definieras i din AP- eller Automatiskt mål-aktivitet under konfiguration i&quot;Mål och mätvärden&quot;. | `Custom - Reporting Segment - [segment name]` |

## Vanliga frågor

Lista med vanliga frågor om [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] [!UICONTROL Insights] rapporter.

### Hur länge bevaras data för [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] modeller?

[!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target]-modeller har utbildats för de senaste 45 dagarnas användarbeteende (användarprofiler, inställningshändelser och konverteringshändelser) för aktiviteten.

[!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] modeller behåller användarbeteende, utbildningsposter och modellbeslutsdata i 90 dagar för att skapa [!UICONTROL Insights]-rapporter. Efter 90 dagar tas utbildningsdokumentation och modellbeslut bort. [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target]-modeller behåller också aggregerade upplevelse-/erbjudandenivådata för exponering och konvertering för rapportering i två år. Dessa data är endast sammanställningsdata och innehåller inga profildata på individuell nivå.

## Utbildningsvideo: Använda Personalization Insights-rapporter ![Självstudiekurs](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Mer information finns i [Använda Personalization Insights-rapporter i Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe bloggar

* Del 1: [Ta bort mysteriet från magin med AI-driven Personalization](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Del 2: [En titt bakom draperiet med AI för Personalization i Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Del 3: [MAGIX - Lösning till Black Box-utgåvan av AI-driven Personalization](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
