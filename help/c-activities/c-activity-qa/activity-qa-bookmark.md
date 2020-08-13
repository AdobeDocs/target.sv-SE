---
keywords: qa;preview;bookmarklet;preview links
description: Information som hjälper dig att använda Adobe Target QA-bokmärket för att tvinga Target att släppa dig från QA-läget.
title: Activity QA bookmarklet för Adobe Target
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 1%

---


# Activity QA bookmarklet{#activity-qa-bookmarklet}

Information som hjälper dig att använda [!DNL Target] QA-bokmärket för att tvinga dig [!DNL Target] att släppa dig från QA-läge.

Eftersom [QA-läget](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) är fast måste din [!DNL Target] session förfalla när du har bläddrat på en webbplats i QA-läge, annars måste du ha [!DNL Target] släppt dig från QA-läge innan du kan visa webbplatsen som en vanlig besökare. Använd QA- [!DNL Target] bokmärket för att tvinga dig ut ur QA-läget.

Om du vill använda [!DNL Target] QA-bokmärket skapar du ett bokmärke som innehåller följande JavaScript-kod och lägger till det i webbläsarens bokmärkesverktygsfält:

```
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

Bokmärket ska sedan visas i verktygsfältet för återanvändning.

>[!NOTE]
>
>Hur du skapar ett bokmärke varierar beroende på webbläsartyp och version. Se webbläsarens hjälp eller sök på Internet efter specifika anvisningar.

Du kan också manuellt tvinga dig ut ur QA-läget genom att läsa in en sida på webbplatsen med parametern `at_preview_token` med ett tomt värde.

Exempel:

`https://www.mysite.com/?at_preview_token=`
