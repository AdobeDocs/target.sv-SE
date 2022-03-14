---
keywords: anpassade händelser;at.js;begäran misslyckades;begäran lyckades;innehållsåtergivningen misslyckades;innehållsåtergivningen lyckades;biblioteket lästes in;begäran startades;återgivning av innehåll startades;återgivning av innehåll misslyckades;omdirigering av innehållsåtergivning
description: Använd anpassade händelser för Adobe [!DNL Target] at.js JavaScript-bibliotek som ska meddelas när en mbox-begäran eller ett erbjudande misslyckas eller lyckas.
title: Hur använder jag anpassade at.js-händelser?
feature: at.js
role: Developer
exl-id: 4073210b-b782-48a7-8b69-29eb5cd98fd5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# at.js, anpassade händelser

Information om `at.js custom events`som talar om för dig när en mbox-begäran eller ett erbjudande misslyckas eller lyckas.

Tidigare tillät inte mbox.js (nu föråldrat) annan JavaScript-kod som körs på sidan vad som händer bakom scenerna. I och med utvecklingen av at.js hade vi en unik möjlighet att åtgärda det här problemet.

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
| type | Sträng | Det finns flera scenarier där du vill bli informerad om hjälp med att spåra, felsöka och anpassa interaktion med at.js.<br>Varje anpassad händelse i listan nedan har två format: en &quot;konstant&quot; och ett &quot;strängvärde&quot;.<ul><li>**Konstanter**: Förberedd med `adobe.target.event.`, visas med versaler och innehåller understreck. Så här prenumererar du på anpassade händelser *efter* at.js laddas men *före* Använd konstanten när mbox-svaret har tagits emot.</li><li>**Strängvärden**: Gemener och innehåller streck. Så här prenumererar du på anpassade händelser *före* at.js läses in, använd strängvärdet.</li></ul>**Begäran misslyckades**<br> Konstant: `adobe.target.event.REQUEST_FAILED`<br>Strängvärde: `at-request-failed`<br>Beskrivning: En mbox-begäran misslyckades på grund av timeout, felaktig statuskod, JSON-tolkningsfel osv.<br>**Begäran lyckades**<br> Konstant: `adobe.target.event.REQUEST_SUCCEEDED`<br>Strängvärde: `at-request-succeeded`<br>Beskrivning: En mbox-begäran lyckades.<br>**Innehållsåtergivning misslyckades**<br> Konstant: `adobe.target.event.CONTENT_RENDERING_FAILED`<br>Strängvärde: `at-content-rendering-failed`<br>Beskrivning: Det gick inte att återge erbjudandet på grund av att elementet i en omslutningsruta saknas, det går inte att hitta väljaren osv.<br>**Innehållsåtergivning lyckades**<br> Konstant: `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>Strängvärde: `at-content-rendering-succeeded`<br>Beskrivning: Återgivningen av erbjudandet lyckades. DOM-ändringar har tillämpats.<br>**Bibliotek inläst**<br> Konstant: `adobe.target.event.LIBRARY_LOADED`<br>Strängvärde: `at-library-loaded`<br>Beskrivning: Den här händelsen är idealisk för att spåra när at.js har lästs in helt. Du kan använda den här händelsen för att anpassa den globala mbox-körningen. Du kan också använda den här händelsen för att inaktivera den globala mbox-filen och sedan lyssna efter den här händelsen för att utlösa den globala mbox-filen senare.<br>**Begär start**<br> Konstant: `adobe.target.event.REQUEST_START`<br>Strängvärde: `at-request-start`<br>Beskrivning: Den här händelsen utlöses innan en HTTP-begäran körs. Du kan använda den här händelsen för prestandamätningar med hjälp av API:t för resurstimer.<br>**Start för innehållsåtergivning**<br> Konstant: `adobe.target.event.CONTENT_RENDERING_START`<br>Strängvärde: `at-content-rendering-start`<br>Beskrivning: Den här händelsen utlöses innan väljaravsökningen startas och innehållet återges på sidan. Du kan använda den här händelsen för att spåra återgivningsförloppet för innehåll.<br>**Innehållsåtergivning - inga erbjudanden**<br> Konstant: `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>Strängvärde: `at-content-rendering-no-offers`<br>Beskrivning: Den här händelsen utlöses när inga erbjudanden returneras.<br>**Omdirigering av innehållsåtergivning**<br> Konstant: `adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>Strängvärde: `at-content-rendering-redirect`<br>Beskrivning: Den här händelsen utlöses när ett erbjudande är en omdirigering och Target omdirigeras till en annan URL. |
| mbox | Sträng | mbox name |
| message | Sträng | Innehåller en beskrivning som kan läsas av människor, t.ex. vad som hände, felmeddelandet. |
| spårning | Objekt | Innehåller `sessionId` och `deviceId`. I vissa fall `deviceId` kan saknas eftersom [!DNL Target] det gick inte att hämta den från edge-servern. |
| type | Sträng | **Beslutsartifakt på enheten har slutförts**<br> Konstant:<br>`adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`<br>Strängvärde: `artifactDownloadSucceeded`<br>Beskrivning: Anropas när den enhetsspecifika beslutsartefakten har hämtats.<br>**Avvikelsefakt på enheten misslyckades**<br> Konstant: `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`<br>Strängvärde: `artifactDownloadFailed`<br>Beskrivning: Anropas när det inte gick att ladda ned enhetens beslutsartefakt. |

## Användning {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```javascript
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## Utbildningsvideo: Svarstoken och anpassade at.js-händelser ![Självstudiemärke](/help/main/assets/tutorial.png) {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

Titta på följande video för att lära dig hur du använder responstoken och anpassade at.js-händelser för att dela profilinformation från Target till tredjepartssystem.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
