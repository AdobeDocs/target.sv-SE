---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;auto target;auto target;auto target report;auto target report;personalization;insights;automatic segments;faq;ofta questions;important attributes
description: Lär dig hur du använder specialrapporter för Automated Personalization- (AP) och Auto-Target-aktiviteter (AT) - automatiserade segment och viktiga attribut.
title: Hur använder jag personaliseringsInsights-rapporterna?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 0%

---

# Insikter om personalisering - rapporter

Två specialrapporter är tillgängliga för användare av [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] AT-verksamhet: den [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] rapporter.

>[!NOTE]
>
>Tänk på följande när du använder personaliseringsInsights-rapporter:
>
>* AP- och AT-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösning. De ingår inte i [!DNL Target Standard] utan [!DNL Target Premium] licens.
>
>* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkt efter att aktiviteten redan var aktiv stöds inte heller.
>
>* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga om [!UICONTROL Primary Goal] är markerat på menyn [!UICONTROL Report Metric] nedrullningsbar lista.
>
>* [!UICONTROL Personalization Insights] rapporter stöds i [standardmiljö](/help/main/administrating-target/hosts.md) endast.
>
>* [!UICONTROL Personalization Insights] rapporter genereras bara för aktiviteter som finns i [!UICONTROL Live] status och har aktiverats och tagit emot trafik i minst 15 dagar.


## Översikt över rapportering av personaliseringsinsikter {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

Målsättningen med [!UICONTROL Personalization Insights] rapporter ska innehålla mer information om hur [!UICONTROL Target] personaliseringsmodeller bakom era AP- och AT-aktiviteter personaliserar besökstrafiken. The [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) är grunden för [!DNL Target] personaliseringsmodeller.

På grund av målet för [!UICONTROL Personalization Insights] rapporterna ska förstå hur [!DNL Target] personaliseringsmodellerna bestämde sig för att skicka besökaren till vilka delar av innehållet, [!UICONTROL Personalization Insights] rapporterna återspeglar endast ett delsegment av all trafik som betjänas av er AP- eller AT-aktivitet. De två rapporterna speglar i synnerhet all trafik som använde personaliseringsmodellen. Med andra ord: [!UICONTROL Personalization Insights] rapporter tar inte hänsyn till kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen.

Två [!UICONTROL Personalization Insights] rapporter finns:

| Rapport | Detaljer |
|--- |--- |
| [!UICONTROL Automated Segments] | Olika besökare svarar annorlunda på erbjudandena/upplevelserna i er AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment definieras av [!DNL Target] personaliseringsmodellerna svarade på aktivitetens erbjudanden/upplevelser. |
| [!UICONTROL Important Attributes] | I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse. |

## Tolka attribut i personaliseringsinsikter {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Det finns två typer av attribut i [!UICONTROL Personalization Insights] rapporter som används i dina AP- eller Auto Target-modeller:

* **Attribut som samlas in automatiskt av Target:** [!DNL Target] använder en basdatauppsättning för att bygga sina personaliseringsalgoritmer i AP- och AT-aktiviteter som återspeglas i personaliseringsinsikter. Se [Datainsamling för målets personaliseringsalgoritmer](/help/main/c-activities/t-automated-personalization/ap-data.md) för datatyper, exempelattribut och deras [!UICONTROL Personalization Insights] namnkonvention. Observera att även om dessa attribut beaktas, kanske inte alla dessa attribut används i den slutliga modellen för en enskild aktivitet.
* **Attribut som skickas till mål:** Se [Överför data för målalgoritmerna för personalisering](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] ger dig många sätt att skicka in ytterligare data till [!DNL Target] för att berika basdatauppsättningen som används för att bygga personaliseringsalgoritmer i AP- och AT-aktiviteter:

| Datatyp | Beskrivning | Namnkonvention för datatyp |
|--- |--- |--- |
| Profilattribut, inklusive profilskript, API för profiluppdatering och profilattribut på sidan | All information som du har valt att inkludera i Target-användarprofilen.<br>Den här informationen kan komma från profilskript, information som har överförts med API:t för profiluppdatering eller parametrar för profiler i mbox som har prefixet &quot;profile&quot;. | `Custom - Profile - [parameter name]` |
| Sidparametrar (kallas även&quot;mbox parameters&quot;) | Namn/värde-par som skickas direkt via sidkod som inte lagras i besökarens profil för framtida bruk. | `Custom - Mbox Parameter - [parameter name]` |
| Kundattribut | Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. Använd data i Adobe Analytics och Adobe Target när de har överförts. | `Custom - Customer Attributes - [parameter name]` |
| Delade målgrupper (Adobe Audience Manager eller Adobe Analytics) | Målgrupper skapade med Adobe Audience Manager eller Adobe Analytics och som delas med Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Delade målgrupper (Adobe Experience Platform/CDP i realtid) | Målgrupper som skapats med Adobe Experience Platform/CDP i realtid och som delas med Target via Destinations. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Delade attribut (Adobe Experience Platform/CDP i realtid) | Attribut som har skapats med Adobe Experience Platform/Real-time CDP och som delas med Target via Destinations. Den här funktionen finns för närvarande i Beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Målgrupper/segment för rapportering i aktivitet | Målgrupper som definieras i din AP- eller Automatiskt mål-aktivitet under konfiguration i&quot;Mål och mått&quot;. | `Custom - Reporting Segment - [segment name]` |

## Vanliga frågor

Lista med vanliga frågor om [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] [!UICONTROL Insights] rapporter.

### Hur lång tid tar data? [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] finns det fortfarande modeller?

[!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] är utbildade i de senaste 45 dagarnas användarbeteende (användarprofiler, inställningshändelser och konverteringshändelser) för aktiviteten.

[!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] modellerna behåller användarbeteende, utbildningsdokumentation och modellbeslutsdata i 90 dagar för att producera [!UICONTROL Insights] rapporter. Efter 90 dagar tas utbildningsdokumentation och modellbeslut bort. [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] Modellerna behåller också aggregerade uppgifter om upplevelser/exponering och konvertering på erbjudandenivå för rapportering i två år. Dessa data är endast sammanställningsdata och innehåller inga profildata på individuell nivå.

## Utbildningsvideo: Använda Insights-rapporter om personalisering ![Självstudiemärke](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Mer information finns i [Använda Insights-rapporter för personalisering i Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe bloggar

* Del 1: [Ta ut mysteriet ur magin med AI-styrd personalisering](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Del 2: [A Peek Behind the Curtain of AI for Personalization in Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Del 3: [MAGIX - Lösning till Black Box Issue of AI-Driven Personalization](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
