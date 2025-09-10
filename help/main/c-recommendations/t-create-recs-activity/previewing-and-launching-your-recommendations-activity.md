---
keywords: Rekommendationer;erbjudande;förhandsvisa;starta;status;villkor;algoritm
description: Lär dig hur du förhandsgranskar din Adobe [!DNL Target] Rekommendationsaktivitet för att se till att resultat finns tillgängliga innan du startar aktiviteten.
title: Hur förhandsgranskar och startar jag en rekommendationsaktivitet?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 26b0c5455e82014dab92c925ecc88bddb3947d2f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Förhandsgranska och starta aktiviteten Rekommendationer

När du har skapat din [!UICONTROL Recommendations]-, [!UICONTROL A/B Test]- eller [!UICONTROL Experience Targeting] (XT)-aktivitet som innehåller [rekommendationer ](/help/main/c-recommendations/recommendations-as-an-offer.md) vill du förhandsgranska dina rekommendationer för att se till att resultaten är tillgängliga innan du startar aktiviteten. [!DNL Target Recommendations] erbjuder flera sätt att förhandsgranska dina rekommendationer.

## Kontrollera algoritmstatus för rekommendationer

När en aktivitet har skapats kör [!DNL Recommendations] en algoritm för att generera rekommendationer. Den här algoritmen kan ta några timmar att köra.

Du kan kontrollera om algoritmen har körts färdigt i översiktsdiagrammet [!UICONTROL Activity], där villkorsstatusen listas. Följande bild visar statusen i aktivitetsdiagrammet på [!DNL Recommendations]-sidan för en [!UICONTROL Overview]-aktivitet:

![Översikt över aktiviteten Rekommendationer](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

Statusresultaten är följande:

* [!UICONTROL Results Ready]: Anger att algoritmen har returnerat resultat
* [!UICONTROL Results Not Ready]: Anger att algoritmen inte har slutförts.
* [!UICONTROL Feed Failure]: Anger att det inte gick att hämta den anpassade villkorsfeeden.

![Dialogrutan Resultat](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Hur lång tid tar det att köra algoritmen?

När en aktivitet som innehåller ett villkor har sparats beräknar [!DNL Target] rekommendationer baserat på den valda samlingen, villkoren, designen och kampanjerna. Beräkningen tar en stund och tidsramen skiljer sig åt beroende på vald rekommendationslogik, dataintervall, antal objekt i katalogen, mängden beteendedata som kunderna har genererat och den valda beteendedatakällan.

Beteendedatakällan har störst inverkan på bearbetningstiden, enligt följande:

### mboxes

Om kryssrutor väljs som datakälla för beteendet körs villkoret omedelbart när det har skapats. Beroende på mängden beteendedata som används och storleken på katalogen kan algoritmen ta upp till 12 timmar att köra. Om du ändrar kriteriekonfigurationen körs vanligtvis algoritmen igen. Beroende på hur ändringarna har gjorts kanske de tidigare beräknade rekommendationerna inte är tillgängliga förrän en omkörning är klar, eller för större ändringar är endast säkerhetskopierings- eller standardinnehåll tillgängligt tills en omkörning är slutförd. Om en algoritm inte ändras körs den automatiskt om med [!DNL Target] var 12:48:e timme, beroende på det valda dataområdet.

### [!DNL Adobe Analytics]

Om villkoret använder [!DNL Adobe Analytics] som beteendedatakälla beror tiden för kriteriernas tillgänglighet på om den valda rapportsviten och uppslagsfönstret har använts för andra villkor när de har skapats.

* **Installation av en engångsrapportsserie**: Första gången en rapportsvit används med ett visst fönster för dataområdessökning kan det ta mellan två och sju dagar för [!DNL Target Recommendations] att helt hämta beteendedata för den valda rapportsviten från [!DNL Analytics]. Den här tidsramen är beroende av systeminläsningen för [!DNL Analytics].
* **Nya eller redigerade villkor med en redan tillgänglig rapportsvit**: När du skapar ett nytt villkor eller redigerar ett befintligt villkor, och den valda rapportsviten redan har använts med [!DNL Target Recommendations], med ett dataintervall som är lika med eller mindre än det valda dataintervallet, är data omedelbart tillgängliga och ingen engångsinställning krävs. I det här fallet, eller om en algoritms inställningar redigeras utan att den valda rapportsviten eller det valda dataintervallet ändras, körs eller körs om inom 12 timmar.
* **Pågående algoritm kör**: Data flödar från [!DNL Analytics] till [!DNL Target Recommendations] dagligen. För rekommendationen [!UICONTROL Viewed Affinity] skickas till exempel ett spårningsanrop i produktvyn till [!DNL Analytics] i närheten av realtid när en användare tittar på en produkt. [!DNL Analytics]-data skickas till [!DNL Target] tidigt nästa dag och [!DNL Target] kör algoritmen på mindre än 12 timmar.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] kräver att ingen offlinealgoritm körs och resultaten är omedelbart tillgängliga. [!UICONTROL Top Viewed]- och [!UICONTROL Top Sellers]-algoritmer som baseras på mbox-data ger i allmänhet resultat mycket snabbt på grund av den enklare beräkning som krävs. Detta kan vara bra alternativ när du vill förhandsgranska en designändring eller bekräfta att beteendedata samlas in korrekt.

## Använda QA-länkar för att förhandsgranska rekommendationer

När algoritmen har resultat klara kan du förhandsgranska dessa resultat med funktionen [QA link](/help/main/c-activities/c-activity-qa/activity-qa.md) i [!DNL Adobe Target]. QA-länkar är tillgängliga i avsnittet [!UICONTROL Activity Location] på översiktssidan för [!UICONTROL Activity]:

>[!NOTE]
>
>Som standard lägger [!DNL Target] automatiskt till dig till den önskade målgruppen för QA-länken. Om den här inställningen är inaktiverad och din aktivitet har målinriktningsregler, måste din användarprofil uppfylla dessa målinriktningsregler för att se upplevelsen som innehåller rekommendationer.

Om du använder en QA-länk kan du förhandsgranska rekommendationerna på sidan:

![Aktuella produkter](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Mål-QA-läget är&quot;klisterlöst&quot; och sparas i en cookie. Om du inte avslutar QA-läget kommer du att fortsätta se QA-resultaten på hela webbplatsen. Om du vill avsluta QA-läget använder du [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* I QA-läge kommer inte din profils [!UICONTROL Recently Viewed Items] eller [!UICONTROL Recently Purchased Items] att påverkas om du bläddrar på webbplatsen. Detta beteende sker genom design för att undvika oavsiktlig förorening av produktionsbeteendedata. Om du vill förhandsgranska resultat från ett [!UICONTROL Recently Viewed Items]- eller [!UICONTROL User-Based Recommendations]-villkor bläddrar du först till webbplatsen utanför QA-läget och använder sedan samma session för att öppna en QA-lägeslänk.

## Använda CSV-nedladdning för att förhandsgranska rekommendationer

I vissa fall kanske du vill granska de specifika objekten som rekommenderas. Detta är särskilt användbart när du använder algoritmer som [!UICONTROL People Who Viewed This, Viewed That], där olika objektuppsättningar rekommenderas beroende på vilket objekt användaren tittar på just nu och du kan ha tusentals eller miljontals olika objekt i katalogen.

Resultat är inte tillgängliga för hämtning förrän en [!UICONTROL Results Ready]-status visas för minst en algoritm i aktiviteten.

Om du vill hämta resultat för förhandsgranskning klickar du på menyikonen i det övre högra hörnet på sidan Aktivitetsöversikt och sedan på **[!UICONTROL Download data]**.

![Alternativet Hämta data](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

En CSV-fil hämtas. Öppna den och se rekommenderade objekt:

![CSV-fil för rekommenderade objekt](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

Från vänster till höger finns en lista med rekommenderade objekt, i det här fallet de som visas mest. Rekommendationerna separeras av miljön, i det här fallet har endast produktionsmiljön rekommendationer.

Om en asterisk (*) är det första värdet på en rad visas [säkerhetskopierade objekt](/help/main/c-recommendations/c-algorithms/backup-recs.md). Säkerhetskopierade objekt visas om inte alla kortplatser i en design kan fyllas med de rekommenderade objekten i algoritmen (villkor).

För andra algoritmtyper som baseras på ett nyckelvärde, till exempel [!UICONTROL People Who Viewed This, Viewed That], listas nyckelvärdena (d.v.s.&quot;This&quot; items) i kolumnen längst till vänster och de rekommenderade objekten (d.v.s.&quot;That&quot; items) listas från vänster till höger i kolumnerna Recommend_X.

>[!NOTE]
>
>Resultathämtningar är inte tillgängliga för aktiviteter som innehåller en [!UICONTROL User-Based Recommendations]-algoritm. Resultathämtningar är inte tillgängliga för villkor som använder rekommendationslogiken [!UICONTROL Recently-Viewed Items].

### Hämtningsformat för CSV för popularitetsbaserade och nyckelbaserade algoritmer {#format}

CSV-nedladdningsfilen återspeglar konsekvent resultat som genererats efter körning av backend-kriterier.

* **För popularitetsbaserade algoritmer (icke-nyckelbaserade) innehåller filen:**

   * En rad med rekommendationer för säkerhetskopiering med * (en asterisk) som prefix
   * En separat rad med rekommendationer baserade på algoritminställningar

* **För nyckelbaserade algoritmer innehåller filen:**

   * En säkerhetskopieringsrad som liknar popularitetsbaserade algoritmer
   * Flera rader i nyckelvärdesformat, där den första posten är produkt-ID för nyckeln, följt av kommaseparerade produkt-ID:n som representerar rekommendationskandidater

## Aktivera aktiviteten Rekommendationer

Klicka på listrutepilen Status på fliken [!UICONTROL Activity Overview] och välj sedan **[!UICONTROL Activate]**.

Om din [!UICONTROL Recommendations]-aktivitet för närvarande är i läget [!UICONTROL Inactive] heter den nedrullningsbara listan [!UICONTROL Inactive].

Efter några sekunder till några minuter växlar statusen till [!UICONTROL Live].

Du kan även inaktivera eller arkivera aktiviteten med samma nedrullningsbara lista.

## Undvika avbrott när du ändrar inställningar för rekommendationer

Om du ändrar [!DNL Recommendations] samlingar, villkor, kampanjer eller designinställningar i en aktiv aktivitet kan algoritmresultaten bli ogiltiga och algoritmens status ändras till [!UICONTROL Results Not Ready].

För att undvika avbrott i en live-aktivitet rekommenderar vi att du använder följande tillvägagångssätt när du ändrar en live-aktivitet:

1. Duplicera den ursprungliga aktiviteten (aktivitet 1) och de villkor du vill ändra för att skapa en ny aktivitet (aktivitet 2).
1. Gör ändringar i den duplicerade aktiviteten (aktivitet 2) och villkoren och vänta tills algoritmen genererar resultat.
1. Förhandsgranska den nya ändrade aktiviteten (aktivitet 2) och bekräfta att resultatet blir som du vill.
1. Aktivera den nya aktiviteten (aktivitet 2).
1. Inaktivera den ursprungliga aktiviteten (aktivitet 1).

Om du behöver behålla historiska rapportresultat i samma aktivitet är ett alternativt tillvägagångssätt möjligt, vilket kan resultera i ett tillfälligt avbrott i tillgängligheten av rekommendationer:

1. Duplicera den ursprungliga aktiviteten (aktivitet 1) och de villkor du vill ändra för att skapa en ny aktivitet (aktivitet 2).
1. Gör ändringar i den duplicerade aktiviteten (aktivitet 2) och villkoren och vänta tills algoritmen genererar resultat.
1. Förhandsgranska den nya ändrade aktiviteten (aktivitet 2) och bekräfta att resultatet blir som du vill.
1. Pausa den nya ändrade aktiviteten (aktivitet 2) och byt ut inställningarna/villkoren mot den ursprungliga aktiviteten (aktivitet 1).
1. Förhandsgranska den ursprungliga aktiviteten (aktivitet 1) och bekräfta att resultatet blir som du vill.
1. Återaktivera den ursprungliga aktiviteten (aktivitet 1).
