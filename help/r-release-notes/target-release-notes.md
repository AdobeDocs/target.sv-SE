---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL-versionerna av Adobe Target.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ae97b36e9a5aaa0394fb3b4ab1ad40b38a0c97be
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 4 maj 2020**

Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!NOTE]
>
>* **borttagning** av mbox.js: 30 augusti 2020 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Se *Adobe Target SKompetensverktyg: Utvecklarchatt: migrera Adobe Target mbox.js till at.js* nedan för mer information.
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.


## Adobe Target-verktyget för kompetensutveckling: Utvecklarchatt, migrera Adobe Target mbox.js till at.js {#skill-builder}

I och med den kommande utfasningen av mbox.js den 30 augusti 2020 var David Son, var Adobe Target Product Manager nyligen värd för en utvecklarchatt för att diskutera fördelarna med att migrera mbox.js till at.js. Under de närmaste 30 dagarna kan du [visa inspelningen](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)av webbinariet.

## Target Standard/Premium 20.5.1 (10 juni 2020)

Information om den här versionen kommer att publiceras här.

## Ändringar i API:t för gruppstatus (datum-TBD)

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
