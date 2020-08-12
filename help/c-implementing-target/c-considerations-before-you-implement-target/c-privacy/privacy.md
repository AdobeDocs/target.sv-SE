---
keywords: privacy;ip address;geosegmentation;opt out;optout;opt-out;data privacy;government regulations;regulations;gdpr;ccpa
description: Adobe Target har aktiverat processer och inställningar som gör att du kan använda Target i enlighet med gällande datasekretesslagstiftning.
title: Integritet
feature: null
subtopic: Getting Started
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 0%

---


# Integritet{#privacy}

Adobe Target har aktiverat processer och inställningar som gör att du kan använda Target i enlighet med gällande datasekretesslagstiftning.

## Samling med IP-adresser {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

IP-adressen till en besökare på din webbplats överförs till ett Adobe Data Processing Center (DPC). Beroende på besökarens nätverkskonfiguration representerar IP-adressen inte nödvändigtvis IP-adressen för besökarens dator. IP-adressen kan till exempel vara den externa IP-adressen för en NAT-brandvägg, HTTP-proxy eller Internet-gateway. Inga IP-adresser för användaren eller någon PII (Personally Identiitable Information) lagras i målet. IP-adresser används endast av Target under hela sessionen (i minnet, aldrig beständig).

## Ersättning av den senaste oktetten med IP-adresser {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe har utvecklat en ny inställning för &quot;sekretess by design&quot; som kan aktiveras av Adobe Client Care för Adobe Target. När den här inställningen är aktiverad döljs den sista oktetten (den sista delen) i IP-adressen omedelbart när IP-adressen samlas in av Adobe. Denna anonymisering utförs innan någon behandling av IP-adressen utförs, inklusive före en valfri geosökning av IP-adressen.

När den här funktionen är aktiverad görs IP-adressen tillräckligt anonym så att den inte längre kan identifieras som personlig information. Därför kan Adobe Target användas i enlighet med lagstiftningen om datasekretess i länder som inte tillåter insamling av personuppgifter. Att få information på stadsnivå kommer sannolikt att påverkas avsevärt av att IP-adressen döljs. Att få information på region- och landsnivå bör endast få en liten inverkan.

Följande inställningar är tillgängliga:

* Ingen förvanskning: Målet döljer inte någon del av IP-adressen.
* Senaste oktett: Mål döljer den sista oktetten i IP-adressen.
* Fullständigt IP: Målet döljer hela IP-adressen.

Målet tar emot den fullständiga IP-adressen och döljer den (om den är inställd på Last octet eller Full IP) enligt specifikationen. Målet innehåller sedan den dolda IP-adressen i minnet under hela sessionen.

>[!NOTE]
>
>[Kontakta Adobe Client Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att avgöra vilken inställning du använder eller för att aktivera funktionen för IP-förfalskning.

## GeoSegmentation {#section_BB69F96559BD44BDA4177537C4A5345A}

Om du aktiverar ersättning av den sista oktetten i IP-adressen kan de återstående värdena för IP-adressen analyseras med hjälp av rapporter i Adobe Target. Om den sista oktetten i IP-adressen inte har dolts kan den fullständiga IP-adressen analyseras i Adobe Target. Du kan använda funktionen GeoSegmentation för att mappa ut besökarnas plats efter geografiskt område. GeoSegmentation-data är endast granulerade till stadsnivån eller postnummernivån, och inte till den enskilda nivån.

Om IP-adresserna är helt dolda är inte GeoSegmentation och geoanpassning tillgängliga.

## Länk för avanmälan {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Du kan lägga till en länk för att avanmäla dig till webbplatserna så att besökarna kan avanmäla sig från allt innehåll och allt som ingår i räkningen.

1. Lägg till följande länk till din webbplats:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`
1. Ersätt texten med din klientkod och lägg till texten eller bilden som ska länkas till avanmälnings-URL:en. `clientcode`

Besökare som klickar på den här länken tas inte med i några mbox-förfrågningar som anropas från webbläsarsessionerna förrän de tar bort sina cookies, eller under två år, beroende på vilket som inträffar först. Detta fungerar genom att ange en cookie för besökaren som anropas `disableClient` i `clientcode.tt.omtrdc.net` domänen.

Även om du använder en cookie-implementering från en annan tillverkare anges den angivna avanmälningen via en cookie från en annan tillverkare. Om klienten bara använder en cookie från en annan tillverkare kontrollerar Target om en cookie för avanmälan har angetts.

## Sekretess- och dataskyddsbestämmelser

Se [Sekretess- och dataskyddsbestämmelser](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) för information om EU:s allmänna dataskyddsförordning (GDPR), California Consumer Privacy Act (CCPA) och andra internationella integritetskrav, och hur dessa bestämmelser påverkar din organisation och Adobe Target.
