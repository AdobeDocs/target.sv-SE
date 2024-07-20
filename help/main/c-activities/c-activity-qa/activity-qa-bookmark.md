---
keywords: qa;förhandsvisa;bokmärkesdiagram;förhandsvisa länkar
description: Lär dig hur du använder bokmärket Adobe [!DNL Target] QA för att tvinga [!DNL Target]  att släppa dig från QA-läget.
title: Hur använder jag Activity QA Bookmarklet?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Activity QA bookmarklet

Information som hjälper dig att använda [!DNL Target] QA-bokmärket för att tvinga [!DNL Target] att släppa dig från QA-läget.

>[!NOTE]
>
>Hur du skapar ett bokmärke varierar beroende på webbläsartyp och version. Se webbläsarens hjälp eller sök på Internet efter specifika anvisningar.

## Activity QA bookmarklet for at.js 1.*x*

Eftersom [QA-läget](/help/main/c-activities/c-activity-qa/activity-qa.md) fortfarande är kladdigt måste din [!DNL Target]-session förfalla när du har bläddrat på en webbplats i QA-läge, annars måste du ha [!DNL Target] släppt dig från QA-läge innan du kan visa webbplatsen som en vanlig besökare. Använd QA-bokmärket [!DNL Target] för att tvinga dig själv från QA-läget.

Om du vill använda [!DNL Target] QA-bokmärket skapar du ett bokmärkesdiagram som innehåller följande JavaScript-kod och lägger till det i webbläsarens bokmärkesverktygsfält:

```javascript
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

Till skillnad från at.js 1.*x*, at.js 2.*x* stöder inte cookies från tredje part, och QA-läget är bara klisterlöst för förstahandsdomänen (genom en cookie som har angetts av at.js). I at.js 2.*x*, QA-lägessessionen hanteras bara på klientsidan och inga QA-lägescookies skickas till Target.

Om du vill använda [!DNL Target] QA-bokmärket skapar du ett bokmärkesdiagram som innehåller följande JavaScript-kod och lägger till det i webbläsarens bokmärkesverktygsfält:

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## Använda Activity QA-bokmärket

Klicka på bokmärket i webbläsarens verktygsfält.
