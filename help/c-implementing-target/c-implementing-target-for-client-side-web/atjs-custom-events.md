---
keywords: custom events;at.js;request failed;request succeeded;content rendering failed;content rendering succeeded;library loaded;request start;content rendering start;content rendering no offers;content rendering rediret
description: Information om anpassade händelser för Adobe Target JavaScript-bibliotek at.js.
title: Information om anpassade händelser för Adobe Target JavaScript-bibliotek at.js.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8d0faeb83e7fe854dcf99c89081fb656cf16c4c0
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# at.js, anpassade händelser

Information om `at.js custom events`, som talar om för dig när en mbox-begäran eller ett erbjudande misslyckas eller lyckas.

Historiskt sett lät mbox.js inte annan JavaScript-kod som körs på sidan veta vad som händer bakom kulisserna. I och med utvecklingen av at.js hade vi en unik möjlighet att åtgärda det här problemet.

Enligt våra kunder finns det flera scenarier som de vill bli informerade om, bland annat:

* En mbox-begäran misslyckades på grund av timeout, felaktig statuskod, JSON-tolkningsfel osv.
* En mbox-begäran lyckades.
* Det gick inte att återge erbjudandet på grund av att elementet i en omslutningsruta saknas, det går inte att hitta väljaren osv.
* Återgivningen av erbjudandet lyckades. DOM-ändringar har tillämpats.

Fördefinierade händelser har en struktur som gör att du kan extrahera nödvändiga data baserat på händelsetyp.

För att vara säker på att händelser kan användas i olika scenarier har de anpassade händelserna ett nyttolastobjekt som tilldelas till egenskapen detail för händelseobjektet (som skickas till hanteraren). För att undvika att skicka strängar som händelsenamn visas händelserna som konstanter med `adobe.target.event` namnutrymme.

## Struktur {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| Nyckel | Typ | Beskrivning |
|--- |--- |--- |
| type | Sträng | Det finns flera scenarier där du vill bli informerad om hjälp med att spåra, felsöka och anpassa interaktion med at.js.<br>Varje anpassad händelse i listan nedan har två format: en &quot;konstant&quot; och ett &quot;strängvärde&quot;.<ul><li>**Konstanter**: Anges med `adobe.target.event.`, visas med versaler och innehåller understreck. Om du vill prenumerera på anpassade händelser *efter* att at.js har lästs in men *innan* mbox-svaret har tagits emot, använder du konstanten.</li><li>**Strängvärden**: Gemener och innehåller streck. Om du vill prenumerera på anpassade händelser *innan* at.js läses in använder du strängvärdet.</li></ul>**Request**<br> FailedConstant: `adobe.target.event.REQUEST_FAILED`<br>Strängvärde: `at-request-failed`<br>Beskrivning: En mbox-begäran misslyckades på grund av timeout, felaktig statuskod, JSON-tolkningsfel osv.<br>**Begäran**<br> SucceededConstant: `adobe.target.event.REQUEST_SUCCEEDED`<br>Strängvärde: `at-request-succeeded`<br>Beskrivning: En mbox-begäran lyckades.<br>**Innehållsrendering**<br> FailedConstant: `adobe.target.event.CONTENT_RENDERING_FAILED`<br>Strängvärde: `at-content-rendering-failed`<br>Beskrivning: Det gick inte att återge erbjudandet på grund av att elementet i en omslutningsruta saknas, det går inte att hitta väljaren osv.<br>**Innehållsrendering**<br> SucceededConstant: `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>Strängvärde: `at-content-rendering-succeeded`<br>Beskrivning: Återgivningen av erbjudandet lyckades. DOM-ändringar har tillämpats.<br>**Library**<br> LoadedConstant: `adobe.target.event.LIBRARY_LOADED`<br>Strängvärde: `at-library-loaded`<br>Beskrivning: Den här händelsen är idealisk för att spåra när at.js har lästs in helt. Du kan använda den här händelsen för att anpassa den globala mbox-körningen. Du kan också använda den här händelsen för att inaktivera den globala mbox-filen och sedan lyssna efter den här händelsen för att utlösa den globala mbox-filen senare.<br>**Begär**<br> StartConstant: `adobe.target.event.REQUEST_START`<br>Strängvärde: `at-request-start`<br>Beskrivning: Den här händelsen utlöses innan en HTTP-begäran körs. Du kan använda den här händelsen för prestandamätningar med hjälp av API:t för resurstimer.<br>**Content Rendering**<br> StartConstant: `adobe.target.event.CONTENT_RENDERING_START`<br>Strängvärde: `at-content-rendering-start`<br>Beskrivning: Den här händelsen utlöses innan väljaravsökningen startas och innehållet återges på sidan. Du kan använda den här händelsen för att spåra återgivningsförloppet för innehåll.<br>**Innehållsåtergivning No**<br> OffersConstant: `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>Strängvärde: `at-content-rendering-no-offers`<br>Beskrivning: Den här händelsen utlöses när inga erbjudanden returneras.<br>**Content Rendering**<br> RedirectConstant: `adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>Strängvärde: `at-content-rendering-redirect`<br>Beskrivning: Den här händelsen utlöses när ett erbjudande är en omdirigering och Target omdirigeras till en annan URL. |
| mbox | Sträng | mbox name |
| message | Sträng | Innehåller en beskrivning som kan läsas av människor, t.ex. vad som hände, felmeddelandet. |
| spårning | Objekt | Innehåller `sessionId` och `deviceId`. I vissa fall `deviceId` kan saknas eftersom det [!DNL Target] inte gick att hämta det från edge-servern. |

## Användning {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## Utbildningsvideo: Svarstoken och märket ![för anpassade händelser i at.js](/help/assets/tutorial.png) {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

Titta på följande video för att lära dig hur du använder responstoken och anpassade at.js-händelser för att dela profilinformation från Target till tredjepartssystem.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)