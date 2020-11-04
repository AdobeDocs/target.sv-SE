---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: Två specialrapporter är tillgängliga för användare av Automated Personalization (AP) och Auto-Target (AT)-aktiviteter, rapporterna Automated Segments och Viktiga attribut.
title: Insikter om personalisering - rapporter
feature: reports
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
translation-type: tm+mt
source-git-commit: 6278a01928fcb9dd0b34d7a8b5313f09f1e8da0f
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Insights - rapporter om personalisering{#personalization-insights-reports}

Två specialrapporter är tillgängliga för användare av [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT) aktiviteter: rapporter [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] rapporter.

>[!NOTE]
>
>Tänk på följande när du använder personaliseringsInsights-rapporter:
>
>* AP- och AT-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösningen. De ingår inte [!DNL Target Standard] utan [!DNL Target Premium] licens.
   >
   >
* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkt efter att aktiviteten redan var aktiv stöds inte heller.
   >
   >
* [!UICONTROL Personalization Insights] -rapporter är bara tillgängliga om du [!UICONTROL Primary Goal] har valt dem i [!UICONTROL Report Metric] listrutan.
   >
   >
* [!UICONTROL Personalization Insights] rapporter stöds endast i [standardmiljön](../../administrating-target/hosts.md) .
   >
   >
* [!UICONTROL Personalization Insights] Rapporterna genereras endast för aktiviteter som är i [!UICONTROL Live] status och har aktiverats och tagit emot trafik i minst 15 dagar.


## Översikt över rapportering av personaliseringsinsikter {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

Syftet med [!UICONTROL Personalization Insights] rapporterna är att ge mer information om hur personaliseringsmodellerna bakom era AP- och AT-aktiviteter personaliserar besökstrafiken [!UICONTROL Target] . Algoritmen [](/help/c-activities/t-automated-personalization/algo-random-forest.md) Random Forest utgör grunden för [!DNL Target] personaliseringsmodellerna.

Eftersom målet för [!UICONTROL Personalization Insights] rapporterna är att förstå hur personaliseringsmodellerna [!DNL Target] bestämde sig för att skicka besökare till vilka delar av innehållet, återspeglar [!UICONTROL Personalization Insights] rapporterna endast en undergrupp av all trafik som hanteras av er AP- eller AT-aktivitet. De två rapporterna speglar i synnerhet all trafik som använde personaliseringsmodellen. Man [!UICONTROL Personalization Insights] tar med andra ord inte i rapporterna hänsyn till kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen.

Två [!UICONTROL Personalization Insights] rapporter finns:

| Rapport | Detaljer |
|--- |--- |
| [!UICONTROL Automated Segments] | Olika besökare svarar annorlunda på erbjudandena/upplevelserna i er AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definieras av personaliseringsmodellerna har svarat på erbjudanden/upplevelser i aktiviteten. [!DNL Target] |
| [!UICONTROL Important Attributes] | I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse. |

## Tolka attribut i personaliseringsinsikter {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Det finns två typer av attribut som visas i [!UICONTROL Personalization Insights] rapporter som används i dina AP- eller Automatiskt mål-modeller:

* **Attribut som samlas in automatiskt av Target:** [!DNL Target] använder en basdatauppsättning för att bygga sina personaliseringsalgoritmer i AP- och AT-aktiviteter som återspeglas i personaliseringsinsikter. Se [Datainsamling för Target&#39;s Personalization Algorithms](/help/c-activities/t-automated-personalization/ap-data.md) för datatyper, exempelattribut och deras [!UICONTROL Personalization Insights] namnkonvention. Observera att även om dessa attribut beaktas kanske inte alla dessa attribut används i den slutliga modellen för en enskild aktivitet.
* **Attribut som skickas till mål:** Se [Överföra data för målalgoritmer](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)för personalisering.

[!DNL Target] erbjuder många sätt för dig att skicka in ytterligare data för [!DNL Target] att berika den basdatauppsättning som används för att skapa dess personaliseringsalgoritmer i AP- och AT-aktiviteter:

| Datatyp | Beskrivning | Namnkonvention för datatyp |
|--- |--- |--- |
| Profilattribut, inklusive profilskript, API för profiluppdatering och profilattribut på sidan | All information som du har valt att inkludera i Target-användarprofilen.<br>Den här informationen kan komma från profilskript, information som har överförts med API:t för profiluppdatering eller parametrar för profiler i mbox som har prefixet &quot;profile&quot;. | `Custom - Profile - [parameter name]` |
| Sidparametrar (kallas även&quot;mbox parameters&quot;) | Namn/värde-par som skickas direkt via sidkod som inte lagras i besökarens profil för framtida bruk. | `Custom - Mbox Parameter - [parameter name]` |
| Kundattribut | Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. Använd data i Adobe Analytics och Adobe Target när de har överförts. | `Custom - Customer Attributes - [parameter name]` |
| Delade målgrupper (Adobe Audience Manager eller Adobe Analytics) | Målgrupper skapade med Adobe Audience Manager eller Adobe Analytics och som delas med Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Målgrupper/segment för rapportering i aktivitet | Målgrupper som definieras i din AP- eller Automatiskt mål-aktivitet under konfiguration i&quot;Mål och mått&quot;. | `Custom - Reporting Segment - [segment name]` |

## Utbildningsvideo: Använda ![självstudiekursen Personalization Insights Reports](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Mer information finns i [Använda personaliseringsinsikter i Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe bloggar

* Del 1: [Ta ut mysteriet ur magin med AI-styrd personalisering](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Del 2: [A Peek Behind the Curtain of AI for Personalization in Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Del 3: [MAGIX - Lösning till Black Box Issue of AI-Driven Personalization](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
