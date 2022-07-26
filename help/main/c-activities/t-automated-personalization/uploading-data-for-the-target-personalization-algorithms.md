---
keywords: Automated Personalization;ap;upload data;offline data;personaliseringsalgoritm;auto target;auto target;best practices
description: Lär dig hur du överför offlinedata, som CRM-information, när du skapar personaliseringsmodeller i Adobe [!DNL Target] Automated Personalization-aktiviteter.
title: Hur överför jag data för personaliseringsalgoritmer?
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Överför data för [!DNL Target] personaliseringsalgoritmer

Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du bygger personaliseringsmodeller i [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) aktiviteter.

Det finns flera sätt att mata in data i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] personaliseringsalgoritmer. Förutom metoderna i [Metoder för att hämta data till Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}, Experience Cloud delade målgrupper (Adobe Analytics, Audience Management){target=_blank} och rapportmålgrupper i aktivitet används också i våra algoritmer.

Mer information om data som samlas in och används automatiskt av personaliseringsalgoritmer i Automated Personalization och Automatisk målanpassning finns i [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bästa praxis {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

I följande lista visas de bästa sätten att överföra data för Target-personaliseringsalgoritmer:

* Ju mer högkvalitativa data som är tillgängliga för Target personaliseringsalgoritmer, desto bättre kvalitet får de resulterande modellerna i era AP- och Auto Target-aktiviteter.
* Begränsa med flera profilskript eller attribut som har samma syfte.
* Skicka inte ett unikt ID, till exempel ett sessions-ID, om det inte behövs.
* Granska det som data Target automatiskt samlar in ( [Datainsamling för målets personaliseringsalgoritmer](/help/main/c-activities/t-automated-personalization/ap-data.md)) så att du inte skickar duplicerad information. Target använder till exempel IP-adresser för att fastställa besökarnas postnummer. Denna information behöver inte skickas som en separat variabel.
* Skicka inte flera värden i samma attribut/variabel. Om flera variabler är sammanfogade behandlar Target personaliseringsalgoritmer varje sträng som ett unikt värde, vilket minskar värdet på informationen för personalisering.
* Använd en minnesvärd och meningsfull namnkonvention för att skapa [Insikter om personalisering - rapporter](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mer förståeligt.
