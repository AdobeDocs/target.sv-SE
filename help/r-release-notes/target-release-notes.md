---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL-versionerna av Adobe Target.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d45a38376ebe98d212fba3097159a7b89b792c53

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 27 april 2020**

Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!NOTE]
>
>* **borttagning** av mbox.js: 30 augusti 2020 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Se *Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js* nedan om du vill ha information om hur du registrerar dig för en kommande utvecklarchatt om det här ämnet.
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.


## Adobe Target-verktyget för kompetensutveckling: Utvecklarchatt, migrera Adobe Target mbox.js till at.js {#skill-builder}

Träffa David Son, Adobe Target Product Manager, och berätta om fördelarna med att migrera mbox.js till at.js. Hör de senaste at.js-uppdateringarna, läs om de förbättrade funktionerna och hur de är anpassade till större trender inom teknologiområdet, samt några praktiska tips som ser till att du får ut så mycket av Target när du migrerar från mbox.js till at.js. Adobe Target-utvecklare vill inte missa detta!

Tisdag 5 maj 08:00 - 09:00 (PDT)

[Anmäl dig nu!](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard/Premium 20.4.1 (27 april 2020)

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade ett problem som felaktigt kvalificerade en enhet och webbläsartyp för en målgrupp. (TGT-36266)
* Korrigerade ett problem som förhindrade rapportdata från att visas när de visades på skärmar som var mindre än 963 pixlar breda. (TGT-36549)
* Ett problem som orsakade att Automatisk personalisering inte kunde återges korrekt har åtgärdats. (TGT-36619)
* Korrigerade ett problem som gjorde att vissa alternativ i Visual Experience Composer (VEC) inte visades korrekt. (TGT-36571)
* Korrigerade ett problem i målgränssnittet som gjorde att andra rekommendationer erbjuder förhandsvisningar för att visa det redigerade innehållet efter att en användare har ersatt innehållet i en enda upplevelse. (TGT-36053 &amp; TGT-36894)
* Ett problem som gjorde att vissa användare inte kunde ta bort objekt från en rekommendationskatalog har korrigerats. (TGT-36455)
* Ett problem har korrigerats som gjorde att användare inte kunde spara rekommendationskriterier för en flersidig aktivitet. (TGT-36249)
* Korrigerade ett problem som gjorde att alternativknapparna för datakällan för beteendedata försvann när villkoret redigerades en andra gång i rad. (TGT-36796)
* Korrigerade ett visningsfel som medförde att en rekommendationsalgoritm visade &quot;hämtningsresultat&quot; under en längre period. (TGT-36550 &amp; TGT-36551)
* Uppdaterade många gränssnittssträngar som är lokaliserade på olika språk.

## Ändringar i API:t för gruppstatus v2 (4 maj 2020)

I versionen från 4 maj returnerar status för profilgrupp endast feldata på radnivå som går framåt (data om lyckade åtgärder returneras inte). Misslyckade profil-ID:n returneras av API:t som fortsätter.

Föregående och nya API-svar är följande:

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**För närvarande ser vi svaret som:**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**Efter 4 maj kommer svaret att vara:**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
