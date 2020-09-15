---
keywords: qa;preview;bookmarklet;preview links
description: Information som hjälper dig att använda Adobe Target QA-bokmärket för att tvinga Target att släppa dig från QA-läget.
title: Activity QA bookmarklet för Adobe Target
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: d858f17baff9a7d863be0888200800b3f0d0f301
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# Activity QA bookmarklet{#activity-qa-bookmarklet}

Information som hjälper dig att använda [!DNL Target] QA-bokmärket för att tvinga dig [!DNL Target] att släppa dig från QA-läge.

>[!NOTE]
>
>Hur du skapar ett bokmärke varierar beroende på webbläsartyp och version. Se webbläsarens hjälp eller sök på Internet efter specifika anvisningar.

## Activity QA bookmarklet for at.js 1.*x*

Eftersom [QA-läget](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) är fast måste din [!DNL Target] session förfalla när du har bläddrat på en webbplats i QA-läge, annars måste du ha [!DNL Target] släppt dig från QA-läge innan du kan visa webbplatsen som en vanlig besökare. Använd QA- [!DNL Target] bokmärket för att tvinga dig ut ur QA-läget.

Om du vill använda [!DNL Target] QA-bokmärket skapar du ett bokmärke som innehåller följande JavaScript-kod och lägger till den i webbläsarens bokmärkesverktygsfält:

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

Du kan också manuellt tvinga dig ut ur QA-läget genom att läsa in en sida på webbplatsen med parametern `at_preview_token` med ett tomt värde.

Exempel:

`https://www.mysite.com/?at_preview_token=`

## Activity QA bookmarklet for at.js 2.*x*

Till skillnad från at.js 1.*x*, at.js 2.*x* stöder inte cookies från tredje part, och QA-läget är bara klisterlöst för förstahandsdomänen (genom en cookie som har angetts av at.js). I at.js 2.*x*, session i QA-läge hanteras bara på klientsidan och inga QA-lägescookies skickas till Target.

Om du vill använda [!DNL Target] QA-bokmärket skapar du ett bokmärke som innehåller följande JavaScript-kod och lägger till den i webbläsarens bokmärkesverktygsfält:

```
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Max-Age=-99999999;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.location.href = url.substring(0, url.length - 1);
        }
    })();
```

## Använda Activity QA-bokmärket

Klicka på bokmärket i webbläsarens verktygsfält.

