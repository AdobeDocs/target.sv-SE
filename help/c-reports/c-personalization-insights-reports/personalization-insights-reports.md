---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: Två specialrapporter är tillgängliga för användare av aktiviteterna Automated Personalization (AP) och Auto-Target (AT), Automated Segments och Viktiga attribut.
title: Insikter om personalisering - rapporter
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# ![PREMIUM](/help/assets/premium.png) -rapporter om personaliseringsinsikter{#personalization-insights-reports}

Två specialrapporter är tillgängliga för användare av aktiviteterna Automated Personalization (AP) och Auto-Target (AT): rapporter om automatiserade segment och viktiga attribut.

>[!NOTE]
>
>AP- och AT-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösningen. De ingår inte [!DNL Target Standard] utan [!DNL Target Premium] licens.
>
>Rapporter om personaliseringsinsikter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkt efter att aktiviteten redan var aktiv stöds inte heller.
>
>Insikter-rapporter om personalisering stöds endast i [standardmiljön](../../administrating-target/hosts.md) .
>
>Insikter om personalisering genereras endast för aktiviteter som har Live-status och som har aktiverats och fått trafik i minst 15 dagar.

## Översikt över rapportering av personaliseringsinsikter {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

Syftet med [!UICONTROL Personalization Insights] rapporterna är att ge mer information om hur Target-personaliseringsmodellerna bakom era AP- och AT-aktiviteter personaliserar besökstrafiken. Algoritmen [Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md) är grunden för Target personaliseringsmodeller.

Eftersom målet för personaliseringsinsikterna är att förstå hur Target personaliseringsmodeller bestämde sig för att skicka vilken besökare till vilken eller vilka delar av innehållet, återspeglar personaliseringsinsikterna endast en undergrupp av all trafik som hanteras av er AP- eller AT-aktivitet. De två rapporterna speglar i synnerhet all trafik som använde personaliseringsmodellen. Med andra ord tar personaliseringsinsikter i rapporter inte hänsyn till kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen.

Det finns två rapporter om personaliseringsinsikter:

| Rapport | Detaljer |
|--- |--- |
| Automatiska segment | Olika besökare svarar annorlunda på erbjudandena/upplevelserna i er AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten. |
| Viktiga attribut | I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse. |

## Tolka attribut i personaliseringsinsikter {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Det finns två typer av attribut som visas i [!UICONTROL Personalization Insights] rapporter som används i dina AP- eller Automatiskt mål-modeller:

* **Attribut som samlas in automatiskt av Target:** Target använder en basdatauppsättning för att bygga sina personaliseringsalgoritmer i AP- och AT-aktiviteter som återspeglas i personaliseringsinsikter. Se [Datainsamling för Target&#39;s Personalization Algorithms](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) för datatyper, exempelattribut och deras [!UICONTROL Personalization Insights] namnkonvention. Observera att även om dessa attribut beaktas kanske inte alla dessa attribut används i den slutliga modellen för en enskild aktivitet.
* **Attribut som skickas till mål:** Se [Överföra data för målalgoritmer](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)för personalisering.

Target ger dig många sätt att skicka in ytterligare data till Target för att berika den basdatauppsättning som används för att skapa dess personaliseringsalgoritmer i AP- och AT-aktiviteter:

| Datatyp | Beskrivning | Namnkonvention för datatyp |
|--- |--- |--- |
| Profilattribut, inklusive profilskript, API för profiluppdatering och profilattribut på sidan | All information som du har valt att inkludera i Target-användarprofilen.<br>Den här informationen kan komma från profilskript, information som har överförts med API:t för profiluppdatering eller parametrar för profiler i mbox som har prefixet &quot;profile&quot;. | `Custom - Profile - [parameter name]` |
| Sidparametrar (kallas även&quot;mbox parameters&quot;) | Namn/värde-par som skickas direkt via sidkod som inte lagras i besökarens profil för framtida bruk. | `Custom - Mbox Parameter - [parameter name]` |
| Kundattribut | Med kundattribut kan du överföra besökarprofildata via FTP till Experience Cloud. När du väl har överfört data kan du utnyttja dem i Adobe Analytics och Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Delade målgrupper (Adobe Audience Manager eller Adobe Analytics) | Målgrupper skapade med Adobe Audience Manager eller Adobe Analytics och delade med Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Målgrupper/segment för rapportering i aktivitet | Målgrupper som definieras i din AP- eller Automatiskt mål-aktivitet under konfiguration i&quot;Mål och mått&quot;. | `Custom - Reporting Segment - [segment name]` |

## Utbildningsvideo: Använda ![självstudiekursen Personalization Insights Reports](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Mer information finns i [Använda personaliseringsinsikter i Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe-bloggar

* Del 1: Ta [ut mysteriet ur magin med AI-styrd personalisering](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Del 2: En [titt bakom draperiet med AI för personalisering i Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Del 3: [MAGIX - Lösning på Black Box-problemet med AI-driven personalisering](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
