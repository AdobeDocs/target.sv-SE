---
keywords: Implementering;at.js non javascript;adbox;redirector;mbox
description: Lär dig implementera Adobe [!DNL Target] i icke-JavaScript-scenarier, som att använda en AdBox eller Redirector.
title: Hur implementerar jag [!DNL Target] för e-post?
feature: Implement Email
role: Developer
exl-id: 3287cf3d-3ed4-471f-aa06-25bb12e23ead
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# E-post: implementera mål

Information om hur du implementerar Target i icke-JavaScript-scenarier, som att använda en AdBox eller Redirector.

Ni kan spåra besök i annonser och annat externt innehåll. Ni kan också identifiera samma användare både på och utanför er webbplats och leverera en enhetlig upplevelse genom hela deras webbupplevelse. Med en enda URL-adress kan AdBox testa utan JavaScript eller [!DNL at.js].

En AdBox är användbar för webbplatser som inte har [!DNL at.js], t.ex. filialer. Om din aktivitet behöver dynamisk kreativ (du till exempel behöver visa en produkt i annonsen som övergavs i kundvagnen) kan du inte använda en AdBox.

Annonser och omdirigerare kan användas med alla typer av aktiviteter. I följande tabell jämförs Adbox och Redirector samt när de ska användas:

|  | Syfte | När ska användas | URL-struktur | Erbjudandetyp | Erbjudandeinnehåll |
|--- |--- |--- |--- |--- |--- |
| AdBox | Returnerar olika bilder till annonsen | Ändra innehållet i en annons | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | omdirigeringserbjudande | URL för en bild |
| Omdirigerare | Omdirigerar en besökare till en annan webbsida | Ändra en annons landningssida | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | omdirigeringserbjudande | URL för en sida |

## Bästa praxis för säkerhet {#security}

Observera att med Redirector kan du utsättas för en risk för ett Open Redirect-fel. För att undvika obehörig användning av omdirigeringslänkar av tredje part rekommenderar vi att du använder &quot;auktoriserade värdar&quot; för att tillåtslista standarddomänerna för omdirigering av URL. Target använder värdar för att tillåtslista domäner som du vill tillåta omdirigeringar till. Mer information finns i [Skapa Tillåtelselista som anger värdar som har behörighet att skicka mbox-anrop till Target](/help/main/administrating-target/hosts.md#allowlist) in *Värdar*.

## Begränsningar {#section_38F559DCF1324271926608BCD4AB1227}

* Det finns ingen tidsgräns på klientsidan som med standardrutor. Om Target är helt nedtryckt kommer besökare på annonsen inte att se innehåll, inte ens standard.
* Tredjepartscookies används för att spåra besöken. Om PCIds är annorlunda sammanfogas besökarens tredje part som standard med befintliga förstapartsprofiler.
* Om du vill använda cookies från första part på själva AdBox måste du skicka mBox-sessionen i URL:en. Kontakta din kontorepresentant för att göra detta.
* Om du vill använda cookies från första part för att spåra annonsklickningar skickar du mbox-sessionen i URL:en. Kontakta din kontorepresentant för att göra detta.
* Om du vill använda mer än en AdBox på samma sida måste du skicka Mbox-sessionen i URL:en. Kontakta din kontorepresentant för att göra detta. Du kan ha en AdBox- och en Redirector-länk på samma sida (eftersom Redirector finns på en andra sida).