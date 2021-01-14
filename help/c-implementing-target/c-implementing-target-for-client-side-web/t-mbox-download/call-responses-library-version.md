---
description: Det sätt på vilket Target gör och svarar på samtal från din sida beror på vilken version av målbiblioteket du använder, om implementeringen av besökar-ID:t för Experience Cloud finns och om besökar-ID:t finns.
title: Målsidesmetoder med mbox.js biblioteksversion
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---


# Målsidsmetoder av mbox.js biblioteksversion{#target-page-methods-by-mbox-js-library-version}

Det sätt på vilket Target gör och svarar på samtal från din sida beror på vilken version av målbiblioteket du använder, om implementeringen av besökar-ID:t för Experience Cloud finns och om besökar-ID:t finns.

>[!NOTE]
>
>Om du använder [!DNL at.js] sker alla anrop med JSON. Den här sidan innehåller information om [!DNL mbox.js] biblioteksversioner. De beteenden som beskrivs i scenarierna nedan gäller inte för [!DNL at.js].

Det här avsnittet innehåller information om hur varje version av [!DNL Target]-biblioteket svarar på [!DNL Target]-anropet från din sida i följande scenarier.

Det finns flera typer eller slutpunkter, beroende på implementering och biblioteksversion. Du bör känna till alla typer för att förstå hur [!DNL Target] svarar på anrop i varje scenario.

| Typ/slutpunkt | Anropsmetod | Svarsinnehåll |
|--- |--- |--- |
| skapa global mbox automatiskt - synkron | document.write to make call | JavaScript utan document.write() |
| skapa global mbox automatiskt - asynkron | createElement() för att lägga till anrop till brödtexten | JavaScript utan document.write() |
| standard | document.write to make call | JavaScript med document.write() |
| ajax | createElement() för att lägga till anrop till brödtexten | JavaScript utan document.write() |
| json | XMLHTTPrequest() för anrop | returnerar JSON-svar |

>[!IMPORTANT]
>
>För alla typer utom standardtyper ska all anpassad kod och erbjudanden skrivas för att stödja en ajax-miljö. Om du till exempel använder ett JavaScript som innehåller `document.write()` kommer skriptet inte att fungera som förväntat.

## Ingen implementering av besökar-ID {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

Om du använder [!DNL Target Standard] eller [!DNL Premium] med [!DNL mbox.js], och du har aktiverat [!UICONTROL Create Global Mbox] för ditt konto, görs ett **synkront**-anrop och svar av den globala mbox-typen, oavsett [!DNL mbox.js]-version.

Om du skriver egen anpassad kod i stället för att använda [!UICONTROL Visual Experience Composer]-åtgärderna, måste du se till att koden passar för en ajax-miljö. Om du till exempel använder ett JavaScript som innehåller `document.write()` kommer skriptet inte att fungera som förväntat.

>[!NOTE]
>
>Flera ajax-anrop med samma mbox-namn men olika parametrar fungerar inte på samma sida. Endast den första samtalet kommer att göras.

Om du använder&quot;autoskapa global mbox&quot; men även har `mboxCreate` anrop på sidan, till exempel om du implementerar [!DNL Target Standard] eller [!DNL Premium] på en sida som tidigare användes i en äldre implementering, görs globala mbox-anrop med hjälp av** autocreate global mbox - standard** slutpunkt och `mboxCreate` anrop görs med **standard** punkt. Slutpunkten **standard** använder `document.write()` för att ringa och svara. Detta blockerar sidinläsningen, inklusive innehåll som levereras i ajaxsvaret, tills all information har hämtats.

Om du bara använder mboxCreate, till exempel på sidor som skapats med [!DNL Target Classic], fungerar sidan som den alltid har gjort.

| Skapandemetod | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| skapa global mbox automatiskt | skapa global mbox automatiskt - synkron | skapa global mbox automatiskt - synkron | skapa global mbox automatiskt - synkron | skapa global mbox automatiskt - synkron |
| mboxCreate | standard | standard | standard | standard |

## Implementering av besökar-ID finns, men inget besökar-ID har angetts {#section_29888A119C7A4753AD287FC845AA63F4}

Om inget besökar-ID har angetts finns det ingen [!DNL Experience Cloud] besöks-cookie för användaren. Sidan anropar besökar-ID-tjänsten för att hämta besökar-ID:t. Målet väntar på svar med ID:t som anropar [!DNL Target].

>[!NOTE]
>
>[!DNL Mbox.js] Vi rekommenderar v58 för att säkerställa att besökar-ID:t returneras innan Target-anropet görs.

Om du använder [!DNL mbox.js] version 57 i det här scenariot fungerar allting som det gör om det inte finns någon implementering av besökar-ID, vilket beskrivs i det föregående scenariot. Från och med [!DNL mbox.js] version 58 returnerar [!DNL Experience Cloud Visitor ID]-tjänsten med ett besökar-ID innan [!DNL Target]-anrop görs. Detta garanterar att målgruppsdata som delas via huvudtjänsten Profiler och Publiker är tillgängliga för det första [!DNL Target]-anropet i besökarens session. För att undvika flimmer av standardinnehållet innan testinnehållet returneras döljs [!DNL Target] `<BODY>` tills besökar-ID-tjänsten returnerar. I version 58 används `display:none` för att dölja sidan. Detta skapar problem med responsiva webbplatser, så från och med version 59 används `opacity:0` för att dölja innehållet.

| Skapandemetod | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| skapa global mbox automatiskt | skapa global mbox automatiskt - synkron | skapa global mbox automatiskt - asynkron | skapa global mbox automatiskt - asynkron | skapa global mbox automatiskt - asynkron |
| mboxCreate | standard | ajax | ajax | ajax |

## Implementering av besökar-ID finns, och besökar-ID finns {#section_9CD4AE4C8186425D886398BC3CE6C46D}

Om det finns en cookie för besökar-ID behöver [!DNL Target] inte ringa något anrop till besökar-ID-tjänsten. I det här fallet behöver du inte vänta på besökar-ID-tjänsten innan innehållet visas. För versionerna 57 till 59 används typen **autoskapa global mbox - synkron**, så sidan väntar på att anropet till [!DNL Target] ska returneras innan inläsningen fortsätter. På så sätt ser du till att ingen flimmer av standardinnehållet visas. För v60 används **den globala mbox-asynkrona typen** för att säkerställa att [!DNL Target] väntar på att avanmälningstjänsten [!DNL Experience Cloud] ska svara. Avanmälningstjänsten ingår i Data Co-op-lanseringen hösten 2016. Eftersom alla anrop returneras med ajax ska `document.write()` inte användas med [!DNL mbox.js] version 60.

| Skapandemetod | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| skapa global mbox automatiskt | skapa global mbox automatiskt - synkron | skapa global mbox automatiskt - synkron | skapa global mbox automatiskt - synkron | skapa en global mbox automatiskt - asynkron (för att stödja utvecklingen av Data Co-op, som kommer att släppas senare under 2016) |
| mboxCreate | standard | standard | standard | ajax |