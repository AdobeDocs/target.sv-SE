---
keywords: Automated Personalization;ap;upload data;offline data;personaliseringsalgoritm;auto target;auto target;best practices
description: Lär dig hur du överför offlinedata när du bygger personaliseringsmodeller i [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] verksamhet.
title: Hur överför jag data för personaliseringsalgoritmer?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Överför data för [!DNL Target] personaliseringsalgoritmer

Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du bygger personaliseringsmodeller i [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] verksamhet.

Det finns flera sätt att mata in data i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] personaliseringsalgoritmer. Förutom metoderna i [Metoder för att hämta data till Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, [!DNL Experience Cloud] delade målgrupper ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]), och rapportmålgrupper används också i [!DNL Target] algoritmer.

För information om data som samlas in och används av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] personaliseringsalgoritmer, se [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bästa praxis {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

I följande lista visas de bästa sätten att överföra data för [!DNL Target] personaliseringsalgoritmer:

* De högkvalitativa data som är tillgängliga för [!DNL Target] personaliseringsalgoritmer, desto högre kvalitet får de modeller i [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] verksamhet.
* Begränsa med flera profilskript eller attribut som har samma syfte.
* Skicka inte ett unikt ID, till exempel ett sessions-ID, om det inte behövs.
* Granska vilka data [!DNL Target] samlas in automatiskt ( [Datainsamling för målets personaliseringsalgoritmer](/help/main/c-activities/t-automated-personalization/ap-data.md)) så att du inte skickar duplicerad information. Till exempel: [!DNL Target] använder IP-adresser för att fastställa besökarnas ZIP-koder. Denna information behöver inte skickas som en separat variabel.
* Skicka inte flera värden i samma attribut eller variabel. Om flera variabler är sammanfogade, [!DNL Target] personaliseringsalgoritmer behandlar varje sträng som ett unikt värde och minskar värdet av informationen för personalisering.
* Använd en minnesvärd och meningsfull namnkonvention för att skapa [Insikter om personalisering - rapporter](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mer förståeligt.
