---
keywords: Rekommendationer;Rekommendationskriterier;rekommendationer, algoritmer;rekommendationer, aktivitet;kriterier;rekommendationer målinriktning;recs
description: Läs mer om rekommendationsaktiviteter i Adobe [!DNL Target] som automatiskt visar innehåll som kan intressera dina kunder baserat på tidigare användaraktivitet eller andra algoritmer.
title: Vad är  [!DNL Target] rekommendationer?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---

# Rekommendationer

[!DNL Adobe Target Recommendations]-aktiviteter visar automatiskt produkter, tjänster eller innehåll som kan intressera dina besökare baserat på tidigare användaraktivitet, inställningar eller andra kriterier. [!DNL Target Recommendations] hjälper besökaren att dirigera till relevanta objekt som de annars kanske inte känner till. Med [!DNL Recommendations] kan du ge besökarna relevant innehåll vid rätt tidpunkt och på rätt plats.

>[!NOTE]
>
>[!DNL Recommendations] aktiviteter är tillgängliga som en del av [Target Premium-lösningen](/help/main/c-intro/intro.md#premium). De är inte tillgängliga i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.
>
>Om du för närvarande har [!DNL Recommendations Classic] kan du läsa [Rekommendationer, klassiska och Rekommendationer, aktiviteter i Target Premium](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5) om du vill ha mer information om de två lösningarna.

[!DNL Recommendations] hjälper dig att optimera och anpassa realtidsförslag för olika kanaler, appar, sidor, e-postmeddelanden och andra leveransalternativ för att öka engagemanget och konverteringsgraden samtidigt som du minskar hanteringen.

[!DNL Recommendations] hjälper dig att:

* Skapa avancerade kriterier (regler) för att automatisera rekommendationer
* Visa rekommendationerna automatiskt med några JavaScript-utdrag
* Testa och optimera rekommendationskriterier och -designer som visar rekommendationerna
* Rapportera resultaten av dina rekommendationer

Följande bild visar rekommendationer på en webbsida:

![velocity_example image](assets/velocity_example.png)

En rekommendation avgör hur en produkt föreslås för en besökare, beroende på besökarens aktiviteter på webbplatsen. Exempel:

| Önskad åtgärd | Rekommendation |
|--- |--- |
| Uppmuntra människor som köper en ryggsäck att överväga att köpa vandrande skor och leksaker. | Skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av villkoret&quot;Personer som köpt detta även köpte det&quot;. |
| Öka den tid besökarna lägger på er mediematerial genom att rekommendera innehåll som liknar det de tittar på. | Skapa en rekommendation som föreslår andra videoklipp med villkoret&quot;Personer som visade det här&quot;. |
| Föreslå att kunder som har tittat på information om sparplaner på din bank även läser om IRA-konton. | Visa andra produkter som köpts in efter att ha tittat på en produkt utan att visa den första produkten i rekommendationerna, med hjälp av&quot;personer som tittade på den här produkten också&quot;. |

Mer information om dessa och andra [!DNL Recommendations]-villkor finns i [Kriterier](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Villkor

Innan du börjar använda [!DNL Recommendations] kan det vara bra att bekanta sig med några av de termer som används i det här avsnittet. Du behöver inte oroa dig om du inte förstår villkoren fullständigt än. Du kommer att bli mer bekant med dem när du konfigurerar dina [!DNL Recommendations]-aktiviteter.

| Villkor | Definition |
| --- | --- |
| Aktivitet | Med aktiviteter i [!DNL Target] kan du anpassa innehåll efter specifika målgrupper och testa siddesign. [!DNL Recommendations] är bara en av de många aktivitetstyper som är tillgängliga i [!DNL Target]. Mer information finns i [Målaktivitetstyper](/help/main/c-activities/target-activities-guide.md). |
| Enheter | Enheter refererar till de objekt som du vill rekommendera. Enheter kan vara vad som helst, t.ex. produkter, innehåll (artiklar, bildspel, bilder, filmer och tv-program), jobblistor, restauranger osv. Mer information finns i [Enheter](/help/main/c-recommendations/c-products/products.md). |
| Feeds | Feeds används för att hämta entiteter som importerats till [!DNL Recommendations]. Enheter kan skickas med CSV-filer, Google produktsökningsformat och Adobe Analytics produktklassificeringar. Mer information finns i [Feeds](/help/main/c-recommendations/c-products/feeds.md). |
| Katalog | Kataloger avser hela produktuppsättningen (enheter). Katalogen kan innehålla många samlingar - ett sätt att ordna produkterna i logiska intervall. |
| Samling | Samlingar avser en uppsättning liknande eller relaterade artiklar, till exempel en enda produktkategori. Du kan dock gruppera vilka objekt som helst i en kategori som passar ditt företag, till exempel produkter i ett visst prisintervall eller en viss färg, eller objekt som kan vara intressanta i ett visst geografiskt område. Mer information finns i [Samlingar](/help/main/c-recommendations/c-products/collections.md). |
| Kriterier | Kriterier är regler som bestämmer vilka produkter som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden.<br>Några exempel på villkor är: <ul><li>Folk som köpte den här, köpte den där</li><li>Folk som tittade på det här, såg det</li><li>Objekt med liknande attribut</li><li>Senast köpta artikel</li><li>Favoritkategori</li></ul>  Mer information finns i [Villkor](/help/main/c-recommendations/c-algorithms/algorithms.md). |
| Designer | Designer definierar utseendet på rekommendationerna i en [!DNL Recommendations]-aktivitet, till exempel en rad, kolumn, tabell eller rutnät. Bilden högst upp i den här artikeln visar en design på 4 x 1. Mer information finns i [Skapa en design](/help/main/c-recommendations/c-design-overview/create-design.md). |
| Platser | Platser avser ett visst innehållsområde på en webbsida, i en mobilapp eller i ett e-postmeddelande där du utför en aktivitet i personaliserings- och optimeringssyfte. |
| Målgrupper | Målgrupper är grupper med liknande aktivitetsdeltagare som kommer att se en riktad verksamhet. En målgrupp är en grupp människor med samma egenskaper, till exempel en ny besökare, en återkommande besökare eller återkommande besökare från mellanvästern. Med funktionen Målgrupp kan ni rikta olika innehåll och upplevelser till specifika målgrupper för att optimera er digitala marknadsföring genom att visa rätt budskap till rätt personer vid rätt tidpunkt. Mer information finns i [Publiker](/help/main/c-target/target.md). |
| Rekommendationer som ett erbjudande | En funktion som gör att du kan ta med rekommendationer i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Target). Mer information finns i [Rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md). |

## Utbildningsvideo: Aktivitetstyper ![Översikt &#x200B;](/help/main/assets/overview.png)

I den här videon förklaras de aktivitetstyper som är tillgängliga i [!DNL Target Standard/Premium]. [!DNL Recommendations] diskuteras med början vid 7:20.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe Target Basics Webinar: Introduktion till rekommendationer ![Tutorial badge](/help/main/assets/tutorial.png) {#intro-to-recs}

Webbseminariet *Introduktion till rekommendationer* innehåller en fördjupad genomgång av hur du kan utnyttja värdet för [!DNL Adobe Target Recommendations]. Ta reda på hur den här [!DNL Target]-aktiviteten automatiskt visar produkter eller innehåll som kan intressera dina kunder genom att optimera realtidsförslag baserat på tidigare besök. Gå vidare till användargränssnittet för [!DNL Target] för att få en stegvis översikt över hur du skapar en [!DNL Recommendations]-aktivitet.

[Introduktion till rekommendationer](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
