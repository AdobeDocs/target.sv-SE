---
keywords: Recommendations;erbjudande;förhandsvisa;starta;status;villkor;algoritm
description: 'Lär dig hur du förhandsgranskar din Adobe [!DNL Target] Recommendations-aktivitet för att se till att resultaten är tillgängliga innan du startar aktiviteten. '
title: Hur förhandsgranskar och startar jag en Recommendations-aktivitet?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 0%

---

# Förhandsgranska och starta din Recommendations-aktivitet

När du har skapat din [!UICONTROL Recommendations]-, [!UICONTROL A/B Test]- eller [!UICONTROL Experience Targeting] (XT)-aktivitet som innehåller [Recommendations erbjuder](/help/c-recommendations/recommendations-as-an-offer.md) vill du förhandsgranska dina rekommendationer för att se till att resultaten är tillgängliga innan du startar aktiviteten. [!DNL Target Recommendations] erbjuder flera sätt att förhandsgranska dina rekommendationer.

## Kontrollerar Recommendations-algoritmstatus

När du har skapat en aktivitet kör [!DNL Recommendations] en algoritm för att generera rekommendationer. Den här algoritmen kan ta några timmar att köra.

Du kan kontrollera om algoritmen har körts färdigt i översiktsdiagrammet [!UICONTROL Activity], där villkorsstatusen visas. Följande bild visar statusen i aktivitetsdiagrammet på [!DNL Recommendations]-aktivitetens [!UICONTROL Overview]-sida:

![Översikt över Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

Följande bild visar statusen på en [!UICONTROL A/B Test]- eller XT-aktivitets [!UICONTROL Overview]-sida:

![Översikt över A/B-tester](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Statusresultaten är följande:

* [!UICONTROL Results Ready]: Anger att algoritmen har returnerat resultat
* [!UICONTROL Results Not Ready]: Anger att algoritmen inte har slutförts.
* [!UICONTROL Feed Failure]: Anger att det inte gick att hämta den anpassade villkorsfeed-filen.

![Dialogrutan Resultat](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Hur lång tid tar det att köra algoritmen?

När du har sparat en aktivitet som innehåller ett villkor beräknar [!DNL Target] rekommendationer baserat på den valda samlingen, kriterierna, designen och kampanjerna. Beräkningen tar en stund och tidsramen skiljer sig åt beroende på vald rekommendationslogik, dataintervall, antal objekt i katalogen, mängden beteendedata som kunderna har genererat och den valda beteendedatakällan.

Beteendedatakällan har störst inverkan på bearbetningstiden, enligt följande:

### mboxes

Om kryssrutor väljs som datakälla för beteendet körs villkoret omedelbart när det har skapats. Beroende på mängden beteendedata som används och storleken på katalogen kan algoritmen ta upp till 12 timmar att köra. Om du ändrar kriteriekonfigurationen körs vanligtvis algoritmen igen. Beroende på hur ändringarna har gjorts kanske de tidigare beräknade rekommendationerna inte är tillgängliga förrän en omkörning är klar, eller för större ändringar är endast säkerhetskopierings- eller standardinnehåll tillgängligt tills en omkörning är slutförd. Om en algoritm inte ändras kommer den automatiskt att köras igen med [!DNL Target] var 12-48:e timme, beroende på det valda dataområdet.

### Adobe Analytics

Om villkoret använder [!DNL Adobe Analytics] som beteendedatakälla beror tiden för villkorstillgänglighet på om den valda rapportsviten och uppslagsfönstret har använts för andra villkor när de har skapats.

* **Installation** av engångsrapportsviter: Första gången en rapportsvit används med ett givet fönster för sökning efter dataintervall  [!DNL Target Recommendations] kan det ta mellan två och sju dagar att helt hämta beteendedata för den valda rapportsviten från  [!DNL Analytics]. Tidsramen är beroende av systeminläsningen för [!DNL Analytics].
* **Nya eller redigerade villkor med hjälp av ett rapportpaket** som redan är tillgängligt: När du skapar ett nytt villkor eller redigerar ett befintligt villkor, och om den valda rapportsviten redan har använts med  [!DNL Target Recommendations]ett dataintervall som är lika med eller mindre än det valda dataområdet, är data omedelbart tillgängliga och ingen engångsinställning krävs. I det här fallet, eller om en algoritms inställningar redigeras utan att den valda rapportsviten eller dataintervallet ändras, körs eller körs om inom 12 timmar.
* **Pågående algoritmkörningar**: Data flödar från  [!DNL Analytics] till  [!DNL Target Recommendations] dag. För [!UICONTROL Viewed Affinity]-rekommendationen skickas till exempel ett spårningsanrop för en produktvy till [!DNL Analytics] nära realtid när en användare tittar på en produkt. [!DNL Analytics]-data skickas till [!DNL Target] tidigt nästa dag och [!DNL Target] kör algoritmen på mindre än 12 timmar.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] kräver att ingen offlinealgoritm körs och resultaten är omedelbart tillgängliga. [!UICONTROL Top Viewed] och  [!UICONTROL Top Sellers] algoritmer baserade på mbox-data ger i allmänhet resultat mycket snabbt på grund av den enklare beräkning som krävs. Detta kan vara bra alternativ när du vill förhandsgranska en designändring eller bekräfta att beteendedata samlas in korrekt.

## Använda QA-länkar för att förhandsgranska Recommendations

När algoritmen har resultat klara kan du förhandsgranska dessa resultat med [QA-länken](/help/c-activities/c-activity-qa/activity-qa.md)-funktionen [!DNL Adobe Target]. QA-länkar är tillgängliga i avsnittet [!UICONTROL Activity QA] på sidan Activity overview:

![Länk till aktivitets-QA](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>Som standard lägger [!DNL Target] automatiskt till dig till den önskade målgruppen för QA-länken. Om den här inställningen är inaktiverad och din aktivitet har målinriktningsregler, måste din användarprofil uppfylla dessa målinriktningsregler för att se upplevelsen som innehåller rekommendationer.

Om du använder en QA-länk kan du förhandsgranska rekommendationerna på sidan:

![Produkter](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Mål-QA-läget är&quot;klisterlöst&quot; och sparas i en cookie. Om du inte avslutar QA-läget kommer du att fortsätta se QA-resultaten på hela webbplatsen. Om du vill avsluta QA-läget använder du [bokmärket](/help/c-activities/c-activity-qa/activity-qa-bookmark.md).
   >
   >
* När du är i QA-läge kommer surfning av webbplatsen inte att påverka din profils [!UICONTROL Recently Viewed Items] eller [!UICONTROL Recently Purchased Items].&quot; Detta beteende sker genom design för att undvika oavsiktlig förorening av produktionsbeteendedata. Om du vill förhandsgranska resultat från ett [!UICONTROL Recently Viewed Items]- eller [!UICONTROL User-Based Recommendations]-villkor bläddrar du först till platsen utanför QA-läget och använder sedan samma session för att öppna en länk för QA-läge.


## Använda CSV-nedladdning för att förhandsgranska rekommendationer

I vissa fall kanske du vill granska de specifika objekten som rekommenderas. Detta är särskilt användbart när du använder algoritmer som [!UICONTROL People Who Viewed This, Viewed That], där olika objektuppsättningar rekommenderas beroende på vilket objekt användaren tittar på just nu och du kan ha tusentals eller miljontals olika objekt i katalogen.

Resultaten är inte tillgängliga för hämtning förrän en [!UICONTROL Results Ready]-status visas för minst en algoritm i aktiviteten.

Om du vill hämta resultat för förhandsgranskning klickar du på menyikonen i det övre högra hörnet av sidan Aktivitetsöversikt och sedan på **[!UICONTROL Download data]**.

![Alternativet Hämta data](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

En CSV-fil hämtas. Öppna den och se rekommenderade objekt:

![CSV-fil för rekommenderade objekt](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

Från vänster till höger finns en lista med rekommenderade objekt, i det här fallet de som visas mest. Rekommendationerna separeras av miljön, i det här fallet har endast produktionsmiljön rekommendationer. För den här algoritmen har vi inte tillämpat några begränsningar baserat på nyckelvärde, så raden som är märkt med en asterisk (*) innehåller hela uppsättningen rekommendationer. För andra algoritmtyper som baseras på ett nyckelvärde, t.ex. [!UICONTROL People Who Viewed This, Viewed That], listas nyckelvärdena (t.ex. &quot;This&quot; items) i kolumnen längst till vänster och de rekommenderade objekten (d.v.s. &quot;That&quot; items) listas från vänster till höger i kolumnerna recommendation_X.

>[!NOTE]
>
>Resultathämtningar är inte tillgängliga för aktiviteter som innehåller en [!UICONTROL User-Based Recommendations]-algoritm. Resultathämtningar är inte tillgängliga för villkor som använder rekommendationslogiken [!UICONTROL Recently-Viewed Items].

## Aktivera din Recommendations-aktivitet

På fliken [!UICONTROL Activity Overview] klickar du på listrutepilen bredvid statusen och väljer sedan **[!UICONTROL Activate]**.

![Alternativet Aktivera](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

Observera att statusen blir [!UICONTROL Activating]:

![Aktiverar](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

Efter några sekunder till några minuter ändras statusen till [!UICONTROL Live]:

![Live](/help/c-recommendations/t-create-recs-activity/assets/live.png)

Observera att du även kan inaktivera eller arkivera aktiviteten med samma nedrullningsbara lista.

## Undvik avbrott vid ändring av Recommendations-inställningar

Om du ändrar [!DNL Recommendations]-samlingar, villkor, kampanjer eller designinställningar i en live-aktivitet kan algoritmresultaten bli ogiltiga och algoritmens status ändras till [!UICONTROL Results Not Ready].

För att undvika avbrott i en live-aktivitet rekommenderar vi att du använder följande tillvägagångssätt när du ändrar en live-aktivitet:

1. Duplicera aktiviteten och villkoren som du vill ändra.
1. Gör ändringar i den duplicerade aktiviteten och villkoren och vänta på att algoritmen ska generera resultat.
1. Förhandsgranska den nya ändrade aktiviteten och bekräfta att resultatet blir som du vill.
1. Aktivera den nya aktiviteten.
1. Inaktivera den gamla aktiviteten.

Om du behöver behålla historiska rapportresultat i samma aktivitet är ett alternativt tillvägagångssätt möjligt, vilket kan resultera i ett tillfälligt avbrott i tillgängligheten av rekommendationer:

1. Duplicera aktiviteten och villkoren som du vill ändra.
1. Gör ändringar i den duplicerade aktiviteten och villkoren och vänta på att algoritmen ska generera resultat.
1. Förhandsgranska den nya ändrade aktiviteten och bekräfta att resultatet blir som du vill.
1. Pausa den befintliga aktiviteten och växla inställningarna/villkoren till de nya villkoren.
1. Förhandsgranska den befintliga aktiviteten och bekräfta att resultatet blir som du vill.
1. Återaktivera aktiviteten.
