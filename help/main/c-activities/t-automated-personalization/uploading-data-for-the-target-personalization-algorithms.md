---
keywords: Automated Personalization;ap;upload data;offline data;personaliseringsalgoritm;auto target;auto target;best practices
description: Lär dig hur du överför offlinedata när du skapar personaliseringsmodeller i  [!DNL Adobe Target] [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target]-aktiviteter.
title: Hur överför jag data för Personalization algoritmer?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---

# Överför data för personaliseringsalgoritmerna [!DNL Target]

Offlinedata, t.ex. CRM-information eller poängtal för kundbortfall, kan vara oerhört värdefulla när du skapar personaliseringsmodeller i [!DNL Adobe Target] [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] -aktiviteter.

Det finns flera sätt att ange data i personaliseringsalgoritmerna [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target]. Förutom metoderna i [Metoder för att hämta data till Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, används även [!DNL Experience Cloud] delade målgrupper ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) och inaktivitetsrapportmålgrupper i [!DNL Target] algoritmer.

Mer information om de data som samlas in automatiskt och används av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] personaliseringsalgoritmer finns i [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bästa praxis {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

I följande lista visas de bästa sätten att överföra data för [!DNL Target]-personaliseringsalgoritmer:

* Ju mer högkvalitativa data som är tillgängliga för [!DNL Target]-personaliseringsalgoritmer, desto bättre kvalitet får de resulterande modellerna i dina [!UICONTROL Automated Personalization]- och [!UICONTROL Auto-Target]-aktiviteter.
* Begränsa med flera profilskript eller attribut som har samma syfte.
* Skicka inte ett unikt ID, till exempel ett sessions-ID, om det inte behövs.
* Granska vilka data som [!DNL Target] automatiskt samlar in ( [Datainsamling för Target&#39;s Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md)) så att du inte skickar duplicerad information. [!DNL Target] använder till exempel IP-adresser för att fastställa besökarnas ZIP-koder. Denna information behöver inte skickas som en separat variabel.
* Skicka inte flera värden i samma attribut eller variabel. Om flera variabler är sammanfogade behandlar [!DNL Target] personaliseringsalgoritmer varje sträng som ett unikt värde, vilket minskar värdet på informationen för personalisering.
* Använd en minnesvärd och meningsfull namnkonvention för att göra dina [Personalization Insights Reports](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mer förståeliga.
