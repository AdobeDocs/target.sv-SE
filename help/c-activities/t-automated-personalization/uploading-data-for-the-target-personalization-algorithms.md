---
keywords: Automated Personalization;ap;upload data;offline data;personaliseringsalgoritm;auto target;auto target;best practices
description: Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du skapar personaliseringsmodeller i Adobe Target Automated Personalization-aktiviteter (AP).
title: Överför data för personaliseringsalgoritmer
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---


# Överför data för målpersonaliseringsalgoritmerna

Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du skapar personaliseringsmodeller i [!DNL Adobe Target] [!UICONTROL Automated Personalization]-aktiviteter (AP).

Det finns flera sätt att ange data i personaliseringsalgoritmerna [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target]. Förutom metoderna i [Metoder för att hämta data till Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), används även delade målgrupper (Adobe Analytics, Audience Management) och målgrupper i aktivitetsrapporter i våra algoritmer.

Mer information om de data som samlas in och används automatiskt av personaliseringsalgoritmer i Automated Personalization och Automatisk målgrupp finns i [Automated Personalization Data Collection](/help/c-activities/t-automated-personalization/ap-data.md).

## Bästa praxis {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

I följande lista visas de bästa sätten att överföra data för Target-personaliseringsalgoritmer:

* Ju mer högkvalitativa data som är tillgängliga för Target personaliseringsalgoritmer, desto bättre kvalitet får de resulterande modellerna i era AP- och Auto Target-aktiviteter.
* Begränsa med flera profilskript eller attribut som har samma syfte.
* Skicka inte ett unikt ID, till exempel ett sessions-ID, om det inte behövs.
* Granska vilka data Target automatiskt samlar in ( [Datainsamling för Target&#39;s Personalization Algorithms](/help/c-activities/t-automated-personalization/ap-data.md)) så att du inte skickar duplicerad information. Target använder till exempel IP-adresser för att fastställa besökarnas postnummer. Denna information behöver inte skickas som en separat variabel.
* Skicka inte flera värden i samma attribut/variabel. Om flera variabler är sammanfogade behandlar Target personaliseringsalgoritmer varje sträng som ett unikt värde, vilket minskar värdet på informationen för personalisering.
* Använd en minnesvärd och meningsfull namnkonvention för att göra dina [personaliseringsinsikter](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) lättare att förstå.

