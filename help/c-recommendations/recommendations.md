---
keywords: Recommendations;Recommendations criteria;recommendations algorithms;recommendations activity;criteria;recommendations targeting;recs
description: Recommendations-aktiviteter i Adobe Target visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter eller andra algoritmer. Recommendations hjälper kunderna att hänvisa till relevanta saker som de annars kanske inte känner till.
title: Adobe Target Recommendations
feature: recommendations general
uuid: 2aefd118-8fec-493d-ae4e-c1139c877a3f
translation-type: tm+mt
source-git-commit: 90a224475c645f9b5fcfd4aaeab6d189dd1ce9b1
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations{#recommendations}

[!DNL Adobe Target Recommendations] aktiviteter visar automatiskt produkter, tjänster eller innehåll som kan intressera besökarna baserat på tidigare användaraktivitet, inställningar eller andra kriterier. [!DNL Target Recommendations] hjälper besökaren att hänvisa till relevanta objekt som de annars kanske inte känner till. [!DNL Recommendations] gör att ni kan ge besökarna relevant innehåll vid rätt tidpunkt och på rätt plats.

>[!NOTE]
>
>[!DNL Recommendations] aktiviteter finns tillgängliga som en del av [Target Premium-lösningen](/help/c-intro/intro.md#premium). De finns inte i [!DNL Target Standard] utan [!DNL Target Premium] licens.
>
>Om du har [!DNL Recommendations Classic]det läser du [Recommendations Classic jämfört med Recommendations Activity i Target Premium](../c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5) för mer information om de två lösningarna.

[!DNL Recommendations] hjälper er att optimera och anpassa realtidsförslag för olika kanaler, appar, sidor, e-postmeddelanden och andra leveransalternativ för att öka engagemanget och konverteringsgraden samtidigt som ni minskar hanteringen.

[!DNL Recommendations] hjälper dig att:

* Skapa sofistikerade kriterier (regler) för att automatisera rekommendationer
* Visa rekommendationerna automatiskt med några få JavaScript-kodfragment
* Testa och optimera rekommendationskriterier och -design som visar rekommendationerna
* Rapportera resultaten av dina rekommendationer

Följande bild visar rekommendationer på en webbsida:

![](assets/velocity_example.png)

En rekommendation avgör hur en produkt föreslås för en besökare, beroende på besökarens aktiviteter på webbplatsen. Exempel:

| Önskad åtgärd | Rekommendation |
|--- |--- |
| Uppmuntra människor som köper en ryggsäck att överväga att köpa vandrande skor och leksaker. | Skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av villkoret&quot;Personer som köpt detta även köpte det&quot;. |
| Öka den tid besökarna lägger på er mediematerial genom att rekommendera mediematerial som liknar det de tittar på. | Skapa en rekommendation som föreslår andra videoklipp med villkoret&quot;Personer som visade det här&quot;. |
| Föreslå att kunder som har tittat på information om sparplaner på din bank även läser om IRA-konton. | Visa andra produkter som köpts in efter att ha tittat på en produkt utan att visa den första produkten i rekommendationerna, med hjälp av&quot;personer som tittade på den här produkten även har köpt&quot;-kriterierna. |

Mer information om dessa och andra [!DNL Recommendations] villkor finns i [Kriterier](../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

## Villkor

Innan du börjar använda [!DNL Recommendations]kan det vara bra att bekanta sig med några av de termer som används i det här avsnittet. Du behöver inte oroa dig om du inte förstår villkoren fullständigt än så kommer du att bli mer bekant med dem när du skapar dina [!DNL Recommendations] aktiviteter.

| Villkor | Definition |
| --- | --- |
| Aktivitet | Med hjälp av aktiviteter i kan ni personalisera innehåll efter specifika målgrupper och testa siddesign. [!DNL Target] [!DNL Recommendations] är bara en av många aktivitetstyper som finns i [!DNL Target]. Mer information finns i [Målaktivitetstyper](/help/c-activities/target-activities-guide.md). |
| Enheter | Enheter refererar till de objekt som du vill rekommendera. Enheter kan vara vad som helst, t.ex. produkter, innehåll (artiklar, bildspel, bilder, filmer och tv-program), jobblistor, restauranger osv. Mer information finns i [Enheter](/help/c-recommendations/c-products/products.md). |
| Feeds | Feeds används för att importera enheter till [!DNL Recommendations]. Enheter kan skickas med CSV-filer, Googles produktsökningsformat och Adobe Analytics produktklassificeringar. Mer information finns i [Feeds](/help/c-recommendations/c-products/feeds.md). |
| Katalog | Kataloger avser hela produktuppsättningen (enheter). Katalogen kan innehålla många samlingar - ett sätt att ordna produkterna i logiska intervall. |
| Samling | Samlingar avser en uppsättning liknande eller relaterade artiklar, till exempel en enda produktkategori. Du kan dock gruppera vilka objekt som helst i en kategori som passar ditt företag, till exempel produkter i ett visst prisintervall eller en viss färg, eller objekt som kan vara intressanta i ett visst geografiskt område. Mer information finns i [Samlingar](/help/c-recommendations/c-products/collections.md). |
| Kriterier | Kriterier är regler som bestämmer vilka produkter som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden.<br>Några exempel på kriterier är: <ul><li>Folk som köpte den här, köpte den där</li><li>Folk som tittade på det här, såg det</li><li>Objekt med liknande attribut</li><li>Senast köpta artikel</li><li>Favoritkategori</li></ul>  Mer information finns i [Kriterier](/help/c-recommendations/c-algorithms/algorithms.md). |
| Designs | Designer definierar utseendet på rekommendationerna i en [!DNL Recommendations] aktivitet, till exempel en rad, kolumn, tabell eller rutnät. Bilden högst upp i den här artikeln visar en design på 4 x 1. Mer information finns i [Skapa en design](/help/c-recommendations/c-design-overview/create-design.md). |
| Platser | Platser avser ett visst innehållsområde på en webbsida, i en mobilapp eller i ett e-postmeddelande där du utför en aktivitet i personaliserings- och optimeringssyfte. |
| Målgrupper | Målgrupper är grupper med liknande aktivitetsdeltagare som kommer att se en riktad verksamhet. En målgrupp är en grupp människor med samma egenskaper, till exempel en ny besökare, en återkommande besökare eller återkommande besökare från mellanvästern. Med funktionen Målgrupp kan ni rikta olika innehåll och upplevelser till specifika målgrupper för att optimera er digitala marknadsföring genom att visa rätt budskap till rätt personer vid rätt tidpunkt. Mer information finns i [Publiker](/help/c-target/target.md). |
| Recommendations som erbjudande | En funktion som gör att du kan ta med rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting). Mer information finns i [Recommendations som erbjudande](/help/c-recommendations/recommendations-as-an-offer.md). |

## Utbildningsvideo: Symbolen ![Översikt över aktivitetstyper](/help/assets/overview.png)

I den här videon förklaras vilka aktivitetstyper som finns i [!DNL Target Standard/Premium]. [!DNL Recommendations] behandlas med början kl. 7.20.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe Target Basics Webinar: Introduktion till Recommendations ![självstudiekurs](/help/assets/tutorial.png) {#intro-to-recs}

Introduktionen *till Recommendations* webbinarium innehåller en fördjupad genomgång av hur du kan utnyttja fördelarna med [!DNL Adobe Target Recommendations]. Ta reda på hur den här [!DNL Target] aktiviteten automatiskt visar produkter eller innehåll som kan intressera dina kunder genom att optimera realtidsförslag baserat på tidigare besök. Gå vidare till [!DNL Target] användargränssnittet för att få en stegvis översikt över hur du skapar en [!DNL Recommendations] aktivitet.

[Introduktion till Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)