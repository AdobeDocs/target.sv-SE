---
keywords: Recommendations;rekommendationsalgoritmer;rekommendationer aktivitet;rekommendationer klassiska
description: Granska informationen och se skillnaderna mellan de gamla Recommendations Classic- och Recommendations-aktiviteterna i [!DNL Target] Premium.
title: Vad är skillnaden mellan Recommendations Classic och Recommendations i [!DNL Target] Premium?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 07548155-9548-4870-b886-6cb4ff37a0bd
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Recommendations Classic jämfört med Recommendations-aktiviteter i [!DNL Target] Premium

Information som hjälper dig att välja mellan Recommendations Classic- och Recommendations-aktiviteter i Target Premium.

>[!NOTE]
>
>Recommendations-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösning. De är inte tillgängliga i [!DNL Target Standard] utan [!DNL Target Premium] licens.

I klassiska [!DNL Recommendations] -produkten visades rekommendationer genom att en mbox för datainsamling skapades på en sida och sedan lades en visningsruta till på en viss plats. The [!DNL Recommendations] aktivitet i [!DNL Target Premium] kan du samla in besöksinformation och skapa rekommendationer var som helst på sidan utan att behöva skapa en mbox för varje plats där du vill rekommendera produkter eller innehåll. En enkel JavaScript-referens i sidhuvudet ger rekommendationer var som helst på sidan. Använd den här JavaScript-referensen för att skicka nycklar till den globala [!DNL Target] mbox, till exempel `entity.id` och `entity.categoryId` nycklar.

[!DNL Recommendations Classic] visas som ett eget kort i [!DNL Experience Cloud] Gränssnitt. A [!DNL Recommendations] aktiviteten är tillgänglig inifrån [!DNL Target Premium] arbetsflöde.

[!DNL Recommendations Classic] användare kan fortsätta använda sina [!DNL Recommendations] mbox in [!DNL Target Recommendations]. De kan också kombinera de klassiska [!DNL Target] metoder genom att behålla sina rutor och använda JavaScript-koden i huvudet för att aktivera [!DNL Recommendations] för de andra elementen på sidan. Att få full [!DNL Target] funktionalitet, [!DNL Recommendations Classic] kan föredra att ta bort sin gamla mbox och enbart använda [!DNL Target Recommendations].

The [!DNL Recommendations] aktivitet i [!DNL Target] förbättrar på [!DNL Recommendations Classic] i följande huvudområden:

## Recommendations som erbjudande

Du kan inkludera rekommendationer i [!UICONTROL A/B Test] (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) och [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med olika rekommendationer på sidan, t.ex. i vilken ordning olika rekommendationer ska ges.
* Skicka automatiskt trafik till den bästa rekommenderade upplevelsen med [!UICONTROL Auto-Allocate].
* Tilldela besökare dynamiskt skräddarsydda rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

Skapa en [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] aktivitet med [!UICONTROL Visual Experience Composer] och använder [!UICONTROL Insert Before], [!UICONTROL Insert After], eller [!UICONTROL Replace With] åtgärd för att lägga till rekommendationer i en upplevelse.

Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).

## Kriterier {#section_117709846DAA404580EBE879FFCBD9BA}

[!DNL Target Recommendations] innehåller ett kriteriebibliotek som innehåller förpaketerade uppsättningar regler och konfigurationer. I [!DNL Recommendations Classic]skapades varje rekommendation manuellt genom att ett formulär fylldes i och sedan valdes i den stora listan med regler. Nu när du skapar en [!DNL Recommendations] väljer du bara en förkonfigurerad villkorsuppsättning. Du kan fortfarande skapa anpassade rekommendationer, men kriteriebiblioteket innehåller många av de vanligaste konfigurationerna, fördefinierade för att förenkla processen och använda språk som folk förstår. Dessa förpaketerade villkor kan användas som de är eller kopieras och redigeras efter dina behov.

![overview_conditions image](assets/overview_criteria.png)

Kriterierna är förkonfigurerade och sorterade efter vertikaler, sidtyper och implementering i branschen. Du kan t.ex. söka efter de kriterier som gäller för vertikal försäljning, för användning på en produktsida, och visa produkter från en viss kategori (enligt definitionen i `entity.categoryID` parameter).

Mer information om hur du använder och skapar villkor finns i [Kriterier](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Arbetsflöde {#section_76B4A26297BF422382DE2C79A2713D3C}

The [!DNL Recommendations] arbetsflödet har förenklats. Istället för att fylla i komplicerade formulär följer du ett visuellt arbetsflöde för att:

1. Välj villkor.
1. Välj en förkonfigurerad [design](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).
1. Förhandsgranska de resulterande rekommendationerna.

## Visuell förhandsgranskning {#section_639B9E38C9EC4093BF9023EE0F2A15AC}

Du kan förhandsgranska dina rekommendationer när du har konfigurerat dem och göra nödvändiga ändringar utan att behöva skapa dem på sidan och sedan testa dem. Förhandsgranskningar är tillgängliga inifrån [!DNL Target].

## Målinriktning {#section_93295EA0DBA14210B8518AF4802A459F}

I [!DNL Recommendations Classic], det fanns sex alternativ för målinriktning. Recommendations-aktiviteter utnyttjar Target alla sina målinriktningsalternativ. Definiera en målgrupp med antingen [!DNL Target] eller andra [!DNL Adobe Experience Cloud] målgrupper (som [!DNL Audience Manager] och [!DNL Analytics]) väljer du sedan hur många procent aktivitetsdeltagare som ska se respektive design och hur många procent som ska se kontrollen.

![overview_targeting image](assets/overview_targeting.png)

## Rapportering {#section_25C2FCCE4BC1488496C517C0470B5CD6}

I [!DNL Target], [!DNL Recommendations] ger förbättrad rapportering som utnyttjar funktionerna i [!DNL Target] och [!DNL Experience Cloud]. I stället för att bara visa lyften från [!DNL Recommendations] jämfört med resultaten utan dem kan du visa fullständig information om [!DNL Recommendations] aktivitet.

![overview_report image](assets/overview_report.png)
