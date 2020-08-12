---
keywords: response tokens;tokens;plugins;plug-ins;at.js;response
description: Med svarstoken kan du automatiskt generera målspecifik information (aktivitetsinformation, användarprofilinformation, geoinformation o.s.v.) som kan användas vid felsökning eller integrering med tredjepartssystem (som Clicktale)
title: Svarstoken i Adobe Target
feature: null
subtopic: Getting Started
topic: Standard
uuid: 20561673-d762-4c3d-bedc-94aeab5053d7
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1558'
ht-degree: 0%

---


# Svarstoken{#response-tokens}

Med svarstoken kan du automatiskt få ut information som är specifik för [!DNL Target] (aktivitetsinformation, användarprofilinformation, geoinformation o.s.v.) som kan användas vid felsökning eller integrering med tredjepartssystem (som Clicktale).

Med svarstoken kan du välja vilka variabler som ska användas och sedan aktivera dem som en del av ett Target-svar. Om du vill göra det aktiverar du bara en variabel med växeln så skickas variabeln med Target-svar, som kan valideras i nätverksanrop. Svarstoken fungerar även i [!UICONTROL Preview] läge.

En viktig skillnad mellan plugin-program och svarstoken är att medan plugin-program levererar JavaScript till sidan som körs vid leverans, ger svarstoken ett objekt som sedan kan läsas och hanteras med händelseavlyssnare. Mer information finns [i anpassade händelser](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) at.js och exemplen senare i den här artikeln. Responstoken är säkrare och bör underlätta utveckling och underhåll av tredjepartsintegreringar.

>[!NOTE]
>
>Svarstoken är tillgängliga med at.js 1.1 eller senare. Svarstoken stöds inte med mbox.js.

| Målbibliotek som används | Föreslagna funktionsmakron |
|--- |--- |
| at.js | Kontrollera att du använder at.js version 1.1 eller senare. Information om hur du hämtar den senaste versionen av at.js finns i [Hämta på.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md). Mer information om nya funktioner i varje version av at.js finns i [versionsuppgifterna](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)at.js.<br>Kunder som använder at.js uppmuntras att använda svarstoken och gå bort från plugin-program. Vissa plugin-program som är beroende av interna metoder som finns i mbox.js, men inte i at.js, levereras men kommer att misslyckas. Mer information finns i [at.js Begränsningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md). |
| mbox.js | Plugin-program stöds och levereras även fortsättningsvis med mbox.js.<br>Kunder som använder mbox.js och plugins uppmuntras att gå över till at.js och svarstoken. Mer information om fördelarna med att använda at.js framför mbox.js finns i [at.js Vanliga frågor](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md). Mer information om migrering finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).<br>Efter borttagningen av Target Classic (november 2017) kan du behöva kontakta Client Care för att redigera eller inaktivera befintliga plugin-program. Du bör ha granskat dina plugin-program innan Target Classic har tagits bort och inaktiverats för oönskade plugin-program.<br>Du kan inte skapa nya plugin-program i Target Standard/Premium. Använd i stället svarstoken.<br>Gamla SiteCatalyst-plugin-program ska inaktiveras och ersättas med [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). ttMeta-plugin-programmet bör inaktiveras och ersättas med [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |

## Använda svarstoken {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Kontrollera att du använder [!DNL at.js] version 1.1 eller senare.

   Mer information finns i [Hämta på.js](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2).

1. Klicka [!DNL Target]på **[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**.

   ![](assets/response_tokens-new.png)

1. Aktivera önskade svarstoken, t.ex. `activity.id`, `option.id`o.s.v.

   Följande parametrar är tillgängliga som standard:

   | Typ | Parameter | Anteckningar |
   |--- |--- |--- |
   | Inbyggda profiler | `profile.activeActivities` | Returnerar en matris för `activityIds` besökaren som är kvalificerad för. Det ökar efterhand som användarna kvalificerar sig. På en sida med två [!DNL Target] begäranden som levererar två olika aktiviteter, innehåller den andra begäran till exempel båda aktiviteterna. |
   |  | `profile.isFirstSession` | Returnerar &quot;true&quot; eller &quot;false&quot;. |
   |  | `profile.isNewSession` | Returnerar &quot;true&quot; eller &quot;false&quot;. |
   |  | `profile.daysSinceLastVisit` | Returnerar antalet dagar sedan besökarens senaste besök. |
   |  | `profile.tntId` | Returnerar besökarens tntID |
   |  | `profile.marketingCloudVisitorId` | Returnerar besökarens Experience Cloud Visitor-ID. |
   |  | `profile.thirdPartyId` | Returnerar besökarens tredjeparts-ID. |
   |  | `profile.categoryAffinity` | Returnerar besökarens favoritkategori. |
   |  | `profile.categoryAffinities` | Returnerar en array med besökarens fem populäraste kategorier som strängar. |
   | Aktivitet | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`option.name`<br>`option.id` | Information om den aktuella aktiviteten. Observera att&quot;option&quot; är lika med&quot;offer&quot;. |
   | Geo | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Se [Geo](/help/c-target/c-audiences/c-target-rules/geo.md) för mer information om hur du använder geolokalisering i aktiviteter. |
   | Trafikallokeringsmetod<br>(Gäller endast [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] aktiviteter). | `experience.trafficAllocationId` | Returnerar 0 om en besökare har fått en upplevelse av att vara i&quot;kontrolltrafik&quot; och 1 om en besökare har fått en upplevelse av den&quot;riktade&quot; trafikfördelningen. |
   |  | `experience.trafficAllocationType` | Returnera&quot;control&quot; eller&quot;target&quot;. |

   Attribut för användarprofiler och kundattribut visas också i listan.

   >[!NOTE]
   >
   >Parametrar med specialtecken visas inte i listan. Endast alfanumeriska tecken och understreck stöds.

1. (Villkorligt) Om du vill använda en profilparameter som en svarstoken, men parametern inte har skickats via en [!DNL Target] begäran och därför inte har lästs in i målgränssnittet, kan du använda knappen för att lägga till profilen i användargränssnittet [!UICONTROL Add Response Token] .

   Klicka **[!UICONTROL Add Response Token]** och ange tokennamnet. Klicka sedan **[!UICONTROL Activate]**.

   ![](assets/response_token_create.png)

1. Skapa en aktivitet.

Använd anpassade [at.js-händelser](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) för att lyssna efter [!DNL Target] svaret och läsa svarstoken.

I följande kodexempel läggs en anpassad händelsehanterare till direkt på HTML-sidan: [!DNL at.js]

```
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

Följande instruktioner visar hur du lägger till en [!DNL at.js] anpassad händelsehanterare med hjälp av DTM (Dynamic Tag Manager) i Adobe:

1. Logga in på DTM.
1. Bläddra till rätt egenskap.
1. Öppna målverktyget.

   Eftersom DTM inte stöder at.js internt måste du använda kodredigeraren.

1. Lägg till följande kod i kodredigeraren i [!DNL at.js]:

   ```
   document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
     console.log("Request succeeded", e.detail); 
   });
   ```

Du kan lägga till följande kodutdrag på bibliotekets sidfot [på konfigurationssidan](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812) .js om du vill att allt ska vara en enda fil.

```
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
  console.log("Request succeeded", e.detail); 
});
```

## Vanliga frågor om svarstoken {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**Vilken roll krävs för att aktivera eller inaktivera svarstoken?**

Svarstoken kan bara aktiveras eller inaktiveras av användare med rollen Måladministratör.

**Vad händer om jag kör på .js 1.0 eller tidigare?**

Svarstoken visas, men at.js kan inte använda dem.

**Vad händer om jag använder at.js 1.1 (eller senare) på vissa sidor på min webbplats men mbox.js på andra sidor?**

Svarstoken levereras till [!DNL at.js] Target-svaren, men inte till [!DNL mbox.js] svaren.

**Kan jag ha både Target Classic-plugin-program och svarstoken aktiva samtidigt?**

Insticksprogram och svarstoken kommer att finnas tillgängliga parallellt. plugin-program kommer dock att bli inaktuella i framtiden.

**Levereras svarstoken via alla[!DNL Target]svar eller endast via[!DNL Target]svar som levererar en aktivitet?**

Svarstoken levereras endast genom [!DNL Target] svar som levererar en aktivitet.

**Mitt Target Classic-plugin innehåller JavaScript. Hur replikerar jag funktionaliteten med svarstoken?**

När du migrerar till svarstoken måste den här typen av JavaScript finnas i kodbas- eller tagghanteringslösningen. Du kan utlösa den här koden med hjälp av [!DNL at.js] anpassade händelser och skicka svarstokenvärden till dina JavaScript-funktioner.

**Varför visas inte min profil-/kundattributparameter i svarstokenlistan?**

Målet uppdaterar normalt parametrar var 15:e minut. Uppdateringen är beroende av användaråtgärder och data uppdateras bara när du visar svarstokensidan. Om parametrarna inte visas i svarstokenlistan kan det bero på att Target ännu inte har uppdaterat data.

Om parametern innehåller något annat än icke-alfanumeriska tecken eller någon annan symbol än understreck, visas inte parametern i listan. För närvarande stöds endast alfanumeriska tecken och understreck.

**Om jag skapar en svarstoken med hjälp av ett profilskript eller en profilparameter och sedan tar bort profilskriptet eller parametern, kommer svarstoken fortfarande att leverera innehåll?**

Svarstoken extraherar information från användarprofiler och skickar sedan informationen. Om du tar bort ett profilskript eller en parameter innebär det inte att informationen har tagits bort från användarprofilerna. Användarprofilerna kommer fortfarande att ha data som motsvarar profilskriptet. Svarstoken fortsätter att leverera innehållet. För användare som inte har den informationen sparad i sina profiler, eller för nya besökare, kommer denna token inte att levereras eftersom informationen inte finns i deras profiler.

Målet kommer inte att inaktivera token automatiskt. Om du tar bort ett profilskript och inte längre vill att variabeln ska levereras, måste du inaktivera variabeln själv.

**Jag har bytt namn på mitt profilskript, men varför är den token som använder skriptet fortfarande aktiv med det gamla namnet?**

Som nämnts ovan fungerar svarstoken på den profilinformation som har sparats för användare. Även om du har bytt namn på ditt profilskript kommer de användare som har besökt din webbplats att spara det gamla profilskriptvärdet i sina profiler och token kommer att fortsätta att hämta det gamla värdet som redan har sparats i användarprofilerna. Om du nu vill leverera innehåll med det nya namnet måste du inaktivera den tidigare variabeln och aktivera den nya variabeln.

**Om mina attribut har ändrats, när kommer de att tas bort från listan?**

Target utför en uppdatering av attribut med regelbundna intervall. Alla attribut som inte är aktiverade tas bort vid nästa uppdatering. Om du däremot har ett attribut som har aktiverats och tagits bort (du har t.ex. tagit bort ett profilskript som användes som en token), kommer det skriptet inte att tas bort från attributlistan förrän du inaktiverar det. Mål tar bara bort de inaktiverade attributen från listan när de tas bort eller byter namn.

## Skicka data till Google Analytics via at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

Google Analytics kan skicka data via at.js genom att lägga till följande kod på HTML-sidan:

```
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## Felsökning (liknar plug-inen ttMeta) {#section_DB3392B6E80749C1BFB520732EDF3BCE}

Motsvarigheten till ttMeta-plugin-programmet för felsökning kan skapas genom att lägga till följande kod på HTML-sidan:

```
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["option.id"], 
        'OfferName': token["option.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## Utbildningsvideo: Responstoken och at.js Custom Events {#section_3AA0A6C8DBD94A528337A2525E3E05D5} ![Tutorial badge](/help/assets/tutorial.png)

Titta på följande video och lär dig hur du använder svarstoken och anpassade at.js-händelser för att dela profilinformation från Target till tredjepartssystem.

>[!NOTE]
>
>Gränssnittet för [!DNL Target][!UICONTROL Administration] menyer (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är i allmänhet korrekt: alternativen kan dock finnas på något olika platser. Uppdaterade videor kommer snart att publiceras.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
