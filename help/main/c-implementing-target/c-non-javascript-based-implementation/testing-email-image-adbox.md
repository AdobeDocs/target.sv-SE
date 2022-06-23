---
keywords: e-post;adbox;email image adbox
description: Lär dig använda Adobe [!DNL Target] för att dynamiskt testa bilder i e-postmeddelanden och till och med ändra dem när någon öppnar e-postmeddelandet.
title: Hur testar jag en e-postbildsruta?
feature: Implement Email
role: Developer
exl-id: 87a918d7-83dc-4277-821b-d90302c59736
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Testa en e-postbild i Adbox

Testa bilder dynamiskt i e-postmeddelanden och ändra till och med bilderna direkt när någon öppnar e-postmeddelandet.

Omdirigeringar kan användas i e-postmeddelanden för att spåra klick och dynamiskt kontrollera vilka landningssidor som folk når.

Testning av e-postbilder görs med ändrade versioner av adboxar. Eftersom e-postklienter inte tillåter att cookies anges måste en unik identifierare genereras för varje e-postmeddelande. Numret läggs till i adbox-URL:en och till eventuella omdirigeringar som används i e-postmeddelandet för att spåra klick från e-postmeddelandet.

>[!NOTE]
>
>Även om Target tekniskt kan leverera bildoptimering vid öppen tid hanterar varje e-postklient cachelagring på olika sätt, så framgångarna kommer att variera. Oavsett vilken e-postleverantör som används avgör den e-postklient som slutanvändaren använder för att öppna e-postmeddelandet (Gmail-app, Outlook, Hotmail o.s.v.) om bilden hämtas vid öppning. Gmail cachelagrar till exempel det mesta, så bilden som slutanvändaren ser beror på när Gmail väljer att anropa och cachelagra bilden.

**Exempelkod för en e-postbildsruta:**

```
<img src="https://{clientcode}.tt.omtrdc.net/m2/​{clientcode}/ubox/​image?
mbox={email_header}&
mboxDefault=​{http%3A%2F%2Fwww.domain.com%2Fheader.jpg}&
mboxXDomain=disabled&
mboxSession={123456}&
mboxPC={123456}” border=:"0"/>
```

Där nedanstående värden är specifika för dig:

| Värde | Beskrivning |
|--- |--- |
| clientcode | Ditt företags kundkod. Sök efter det här i din at.js som `clientCode='yourclientcode'`. Det här är bara små bokstäver och har inga specialtecken. |
| image | Erbjudandetypen. Det är alltid&quot;bild&quot; för grafiska annonser och&quot;sida&quot; för omdirigeringar. |
| email_header | Namnet på adbox. |
| `mboxDefault=http%3A%2F%2Fwww.domain.com%2Fheader.jpg` | Obligatoriskt. Ersätt URL:en med lämpligt standardinnehåll för din adbox. Detta måste vara en absolut referens och måste vara URL-kodad. |
| `mboxXDomain=disabled` | Anger att Target inte ska försöka ange en cookie. |
| `mboxSession=123456` och `mboxPC=123456` | Två värden krävs av Target för att sammanfoga den här användarens profil med den befintliga profilen för din plats. 123456 är den unika identifierare som genereras per e-post. Infoga det här värdet dynamiskt i varje adbox- och omdirigerings-URL. Det här numret måste vara unikt för varje e-postmeddelande som skickas till varje person. Om ett e-postmeddelande skickas varje vecka till 1 000 personer måste 1 000 unika ID:n genereras.<br>Den unika identifieraren per e-post måste tilldelas mboxSession och mboxPC i varje adbox och omdirigerings-URL. Det rekommenderade formatet för den här identifieraren är timestamp-NNNN där NNNN är ett slumpmässigt 5-siffrigt nummer, men alla alfanumeriska format fungerar. Vissa massutskick och alla programmeringsspråk kan generera denna unika identifierare. |
