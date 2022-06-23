---
keywords: sekretess;ip-adress;geosegmentering;avanmäl dig;avanmäl dig;avanmäl dig;datasekretess;myndighetsregler;regler;gdpr;ccpa
description: Se hur Adobe [!DNL Target] följer gällande datasekretesslagstiftning, inklusive insamling och hantering av IP-adresser, och avanmälningsanvisningar.
title: Hur [!DNL Target] Hantera sekretessproblem?
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 0%

---

# Integritet

[!DNL Adobe Target] har aktiverat processer och inställningar som gör att du kan använda [!DNL Target] i enlighet med gällande datasekretesslagstiftning.

## Samling av funktionsanvändningsdata

Enskilda data om funktionsanvändning samlas in för intern användning [!DNL Adobe] syften för att identifiera om [!DNL Target] funktioner fungerar som avsett eller för att identifiera funktioner som används i alltför liten utsträckning. Olika latensmått samlas in för att bidra till att åtgärda prestandaproblem. Personuppgifter samlas inte in.

Du kan välja bort att rapportera användningsdata i våra SDK:er genom att ange `telemetryEnabled` till false i klientinitieringsalternativen. Mer information finns i [telemetryEnabled in targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

## Samling med IP-adresser {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

IP-adressen till en besökare på din webbplats överförs till ett Adobe Data Processing Center (DPC). Beroende på besökarens nätverkskonfiguration representerar IP-adressen inte nödvändigtvis IP-adressen för besökarens dator. IP-adressen kan till exempel vara den externa IP-adressen för en NAT-brandvägg, HTTP-proxy eller Internet-gateway. Inga IP-adresser för användaren eller någon PII (Personally Identiitable Information) lagras i målet. IP-adresser används endast av Target under sessionen (i minnet, aldrig beständig).

## Ersättning av den senaste oktetten med IP-adresser {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe har utvecklat en ny inställning för &quot;sekretess by design&quot; som kan aktiveras av Adobe Client Care för Adobe Target. När den här inställningen är aktiverad döljs den sista oktetten (den sista delen) i IP-adressen omedelbart när IP-adressen samlas in av Adobe. Denna anonymisering utförs innan någon bearbetning av IP-adressen utförs, inklusive före en valfri geosökning av IP-adressen.

När den här funktionen är aktiverad görs IP-adressen tillräckligt anonym så att den inte längre kan identifieras som personlig information. Därför kan Adobe Target användas i enlighet med lagstiftningen om datasekretess i länder som inte tillåter insamling av personuppgifter. Att få information på stadsnivå kommer sannolikt att påverkas avsevärt av att IP-adressen döljs. Att få information på region- och landsnivå bör endast få en liten inverkan.

Följande inställningar är tillgängliga:

* Ingen förvanskning: Målet döljer inte någon del av IP-adressen.
* Senaste oktett: Mål döljer den sista oktetten i IP-adressen.
* Fullständigt IP: Målet döljer hela IP-adressen.

Målet tar emot den fullständiga IP-adressen och döljer den (om den är inställd på Last octet eller Full IP) enligt specifikationen. Målet innehåller sedan den dolda IP-adressen i minnet under sessionen.

>[!NOTE]
>
>[Kontakta Adobe Client Care](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att avgöra vilken inställning du använder eller för att aktivera funktionen för IP-förfalskning.

## GeoSegmentation {#section_BB69F96559BD44BDA4177537C4A5345A}

Om du aktiverar ersättning av den sista oktetten i IP-adressen kan de återstående värdena för IP-adressen analyseras med hjälp av rapporter i Adobe Target. Om den sista oktetten i IP-adressen inte har dolts kan den fullständiga IP-adressen analyseras i Adobe Target. Du kan använda funktionen GeoSegmentation för att mappa ut besökarnas plats efter geografiskt område. GeoSegmentation-data är endast granulerade till stadsnivån eller postnummernivån, och inte till den enskilda nivån.

Om IP-adresserna är helt dolda är inte GeoSegmentation och geoanpassning tillgängliga.

## Länk för avanmälan {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Du kan lägga till en länk för att avanmäla dig till webbplatserna så att besökarna kan avanmäla sig från allt innehåll och allt som ingår i räkningen.

1. Lägg till följande länk till din webbplats:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. (Villkorligt) Om du använder CNAME bör länken innehålla &quot;client=`clientcode` parameter, till exempel: https://my.cname.domain/optout?client=clientcode.

1. Ersätt `clientcode` med din klientkod och lägg till texten eller bilden som ska länkas till avanmälnings-URL:en.

Besökare som klickar på den här länken tas inte med i några mbox-förfrågningar som anropas från webbläsarsessionerna förrän de tar bort sina cookies, eller under två år, beroende på vilket som inträffar först. Detta fungerar genom att ange en cookie för besökaren som kallas `disableClient` i `clientcode.tt.omtrdc.net` domän.

Även om du använder en cookie-implementering från en annan tillverkare anges den angivna avanmälningen via en cookie från en annan tillverkare. Om klienten bara använder en cookie från en annan tillverkare kontrollerar Target om en cookie för avanmälan har angetts.

## Sekretess- och dataskyddsbestämmelser

Se [Sekretess- och dataskyddsbestämmelser](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/) om du vill ha information om EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra internationella integritetskrav, och hur dessa bestämmelser påverkar din organisation och Adobe Target.
