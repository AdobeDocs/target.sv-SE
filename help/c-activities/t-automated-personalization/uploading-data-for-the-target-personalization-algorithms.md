---
description: Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du skapar personaliseringsmodeller.
title: Överför data för Target-personaliseringsalgoritmer
feature: ap
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# Överför data för målpersonaliseringsalgoritmerna{#upload-data-for-target-s-personalization-algorithms}

Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du skapar personaliseringsmodeller.

Det finns flera sätt att ange data i personaliseringsalgoritmerna Automated Personalization (AP) och Auto-Target. Förutom metoderna i [Metoder för att hämta data till Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)används även delade målgrupper (Adobe Analytics, Audience Management) och målgrupper i aktivitetsrapporter i våra algoritmer.

Mer information om de data som samlas in och används automatiskt av personaliseringsalgoritmer i Automated Personalization och Automatiskt mål finns i [Automated Personalization Data Collection](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## Bästa praxis {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

I följande lista visas de bästa sätten att överföra data för Target-personaliseringsalgoritmer:

* Ju mer högkvalitativa data som är tillgängliga för Target personaliseringsalgoritmer, desto bättre kvalitet får de resulterande modellerna i era AP- och Auto Target-aktiviteter.
* Begränsa med flera profilskript eller attribut som har samma syfte.
* Skicka inte ett unikt ID, till exempel ett sessions-ID, om det inte behövs.
* Granska automatiskt vilka data Target samlar in ( [datainsamling för målets personaliseringsalgoritmer](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)) så att du inte skickar duplicerad information. Target använder till exempel IP-adresser för att fastställa besökarnas postnummer. Denna information behöver inte skickas som en separat variabel.
* Skicka inte flera värden i samma attribut/variabel. Om flera variabler är sammanfogade behandlar Target personaliseringsalgoritmer varje sträng som ett unikt värde, vilket minskar värdet på informationen för personalisering.
* Använd en minnesvärd och meningsfull namnkonvention för att göra dina [personaliseringsinsikter](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mer begripliga.

