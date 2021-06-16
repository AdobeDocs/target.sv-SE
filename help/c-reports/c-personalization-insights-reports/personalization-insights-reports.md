---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;auto target;auto target;auto target report;auto target report;personalization;insights;automatic segments;faq;ofta questions;important attributes
description: Lär dig hur du använder specialrapporter för Automated Personalization- (AP) och Auto-Target-aktiviteter (AT) - automatiserade segment och viktiga attribut.
title: Hur använder jag personaliseringsInsights-rapporterna?
feature: Rapporter
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: c0eae79da63e2f269f603b4d9fd2a5a1170e2687
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# ![Rapporter om ](/help/assets/premium.png) PREMIUMPersonalization Insights

Två specialiserade rapporter är tillgängliga för användare av [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] (AT)-aktiviteter: rapporterna [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes].

>[!NOTE]
>
>Tänk på följande när du använder personaliseringsInsights-rapporter:
>
>* AP- och AT-aktiviteter är tillgängliga som en del av [!DNL Target Premium]-lösningen. De ingår inte i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.
   >
   >
* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkt efter att aktiviteten redan var aktiv stöds inte heller.
   >
   >
* [!UICONTROL Personalization Insights] -rapporter är bara tillgängliga om du  [!UICONTROL Primary Goal] har valt dem i  [!UICONTROL Report Metric] listrutan.
   >
   >
* [!UICONTROL Personalization Insights] rapporter stöds endast i  [standardmiljön ](/help/administrating-target/hosts.md) .
   >
   >
* [!UICONTROL Personalization Insights] Rapporterna genereras endast för aktiviteter som har  [!UICONTROL Live] status och har aktiverats och fått trafik i minst 15 dagar.


## Översikt över rapportering av personaliseringsinsikter {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

Målet med [!UICONTROL Personalization Insights]-rapporterna är att ge mer information om hur personaliseringsmodellerna [!UICONTROL Target] bakom era AP- och AT-aktiviteter anpassar besökstrafiken. Algoritmen [Slumpmässig skog](/help/c-activities/t-automated-personalization/algo-random-forest.md) är grunden för personaliseringsmodellerna [!DNL Target].

Eftersom målet för [!UICONTROL Personalization Insights]-rapporterna är att förstå hur personaliseringsmodellerna [!DNL Target] bestämde sig för att skicka vilken besökare till vilka innehållsdelar, återspeglar [!UICONTROL Personalization Insights]-rapporterna endast en undersegment av all trafik som hanteras av AP- eller AT-aktiviteten. De två rapporterna speglar i synnerhet all trafik som använde personaliseringsmodellen. [!UICONTROL Personalization Insights]-rapporter tar med andra ord inte hänsyn till kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen.

Två [!UICONTROL Personalization Insights]-rapporter är tillgängliga:

| Rapport | Detaljer |
|--- |--- |
| [!UICONTROL Automated Segments] | Olika besökare svarar annorlunda på erbjudandena/upplevelserna i er AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definieras av personaliseringsmodellerna [!DNL Target] svarade på erbjudandena/upplevelserna i aktiviteten. |
| [!UICONTROL Important Attributes] | I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse. |

## Tolka attribut i personaliseringsinsikter {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Det finns två typer av attribut i [!UICONTROL Personalization Insights]-rapporter som används i dina AP- eller Auto Target-modeller:

* **Attribut som samlas in automatiskt av Target:** [!DNL Target] använder en basdatauppsättning för att skapa sina personaliseringsalgoritmer i AP- och AT-aktiviteter som återspeglas i personaliseringsinsikter. I [Datainsamling finns målets algoritmer för personalisering](/help/c-activities/t-automated-personalization/ap-data.md) för datatyper, exempelattribut och deras namnkonvention [!UICONTROL Personalization Insights]. Observera att även om dessa attribut beaktas kanske inte alla dessa attribut används i den slutliga modellen för en enskild aktivitet.
* **Attribut som skickas till mål:** Se  [Överföra data för målpersonaliseringsalgoritmer](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] erbjuder många sätt för dig att skicka in ytterligare data för  [!DNL Target] att berika basdatauppsättningen som används för att skapa dess personaliseringsalgoritmer i AP- och AT-aktiviteter:

| Datatyp | Beskrivning | Namnkonvention för datatyp |
|--- |--- |--- |
| Profilattribut, inklusive profilskript, API för profiluppdatering och profilattribut på sidan | All information som du har valt att inkludera i Target-användarprofilen.<br>Den här informationen kan komma från profilskript, information som har överförts med API:t för profiluppdatering eller parametrar för profiler i mbox som har prefixet &quot;profile&quot;. | `Custom - Profile - [parameter name]` |
| Sidparametrar (kallas även&quot;mbox parameters&quot;) | Namn/värde-par som skickas direkt via sidkod som inte lagras i besökarens profil för framtida bruk. | `Custom - Mbox Parameter - [parameter name]` |
| Kundattribut | Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. Använd data i Adobe Analytics och Adobe Target när de har överförts. | `Custom - Customer Attributes - [parameter name]` |
| Delade målgrupper (Adobe Audience Manager eller Adobe Analytics) | Målgrupper skapade med Adobe Audience Manager eller Adobe Analytics och som delas med Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Målgrupper/segment för rapportering i aktivitet | Målgrupper som definieras i din AP- eller Automatiskt mål-aktivitet under konfiguration i&quot;Mål och mått&quot;. | `Custom - Reporting Segment - [segment name]` |

## Vanliga frågor

Lista med vanliga frågor om [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] [!UICONTROL Insights]-rapporter.

### Hur länge bevaras data för modellerna [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target]?

[!UICONTROL Automated Personalization] (AP) och  [!UICONTROL Auto-Target] modeller har utbildats för de senaste 45 dagarna av användarbeteende (användarprofiler, inställningshändelser och konverteringshändelser) för aktiviteten.

[!UICONTROL Automated Personalization] (AP) och  [!UICONTROL Auto-Target] modeller bevarar användarbeteende, utbildningsregister och modellbeslutsdata i 90 dagar för att ta fram  [!UICONTROL Insights] rapporter. Efter 90 dagar tas utbildningsdokumentation och modellbeslut bort. [!UICONTROL Automated Personalization] (AP) och  [!UICONTROL Auto-Target] modeller bevarar också aggregerade uppgifter om upplevelser/exponering och konvertering på erbjudandenivå för rapportering i två år. Dessa data är endast sammanställningsdata och innehåller inga profildata på individuell nivå.

## Utbildningsvideo: Använda personaliseringsinsikter i rapporter ![Självstudiekursidentitet](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Mer information finns i [Använda personaliseringsinsikter i Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe bloggar

* Del 1: [Ta ut mysteriet ur magin med AI-driven personalisering](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Del 2: [En titt bakom draperiet med AI för personalisering i Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Del 3: [MAGIX - Lösning till Black Box-utgåvan av AI-driven personalisering](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
