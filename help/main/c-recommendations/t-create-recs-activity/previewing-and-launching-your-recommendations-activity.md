---
keywords: Recommendations;erbjudande;förhandsvisa;starta;status;villkor;algoritm
description: 'Lär dig förhandsgranska Adobe [!DNL Target] Recommendations-aktivitet för att säkerställa att resultaten är tillgängliga innan du startar aktiviteten. '
title: Hur förhandsgranskar och startar jag en Recommendations-aktivitet?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 7732f3af0fd995309035a8a214afd438ab7a1823
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 0%

---

# Förhandsgranska och starta din Recommendations-aktivitet

När du har skapat [!UICONTROL Recommendations], [!UICONTROL A/B Test], eller [!UICONTROL Experience Targeting] (XT) aktivitet som innehåller [Recommendations erbjuder](/help/main/c-recommendations/recommendations-as-an-offer.md)vill du förhandsgranska dina rekommendationer för att se till att resultaten är tillgängliga innan du startar aktiviteten. [!DNL Target Recommendations] erbjuder flera sätt att förhandsgranska dina rekommendationer.

## Kontrollerar Recommendations-algoritmstatus

När du har skapat en aktivitet [!DNL Recommendations] kör en algoritm för att generera rekommendationer. Den här algoritmen kan ta några timmar att köra.

Du kan kontrollera om algoritmen har körts färdigt i [!UICONTROL Activity] översiktsdiagram, där villkorsstatusen listas. Följande bild visar statusen i aktivitetsdiagrammet på en [!DNL Recommendations] aktivitet [!UICONTROL Overview] sida:

![Översikt över Recommendations-aktivitet](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

Följande bild visar statusen för en [!UICONTROL A/B Test] eller XT-aktiviteter [!UICONTROL Overview] sida:

![Översikt över A/B-tester](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Statusresultaten är följande:

* [!UICONTROL Results Ready]: Anger att algoritmen har returnerat resultat
* [!UICONTROL Results Not Ready]: Anger att algoritmen inte har slutförts.
* [!UICONTROL Feed Failure]: Anger att det inte gick att hämta den anpassade villkorsfeed-filen.

![Dialogrutan Resultat](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Hur lång tid tar det att köra algoritmen?

När du har sparat en aktivitet som innehåller ett villkor, [!DNL Target] beräknar rekommendationer baserat på den valda samlingen, de valda kriterierna, designen och kampanjerna. Beräkningen tar en stund och tidsramen skiljer sig åt beroende på vald rekommendationslogik, dataintervall, antal objekt i katalogen, mängden beteendedata som kunderna har genererat och den valda beteendedatakällan.

Beteendedatakällan har störst inverkan på bearbetningstiden, enligt följande:

### mboxes

Om kryssrutor väljs som datakälla för beteendet körs villkoret omedelbart när det har skapats. Beroende på mängden beteendedata som används och storleken på katalogen kan algoritmen ta upp till 12 timmar att köra. Om du ändrar kriteriekonfigurationen körs vanligtvis algoritmen igen. Beroende på hur ändringarna har gjorts kanske de tidigare beräknade rekommendationerna inte är tillgängliga förrän en omkörning är klar, eller för större ändringar är endast säkerhetskopierings- eller standardinnehåll tillgängligt tills en omkörning är slutförd. Om en algoritm inte ändras körs den automatiskt igen av [!DNL Target] var 12-48:e timme, beroende på vilket dataområde som valts.

### Adobe Analytics

Om kriterierna använder [!DNL Adobe Analytics] När den har skapats som en beteendedatakälla beror tiden för villkorstillgänglighet på om den valda rapportsviten och uppslagsfönstret har använts för andra villkor.

* **Installation av engångsavisering**: Första gången en rapportsvit används med ett visst fönster för dataintervallsökning, [!DNL Target Recommendations] kan ta mellan två och sju dagar att helt hämta beteendedata för den valda rapportsviten från [!DNL Analytics]. Tidsramen är beroende av [!DNL Analytics] systembelastning.
* **Nya eller redigerade villkor med hjälp av ett rapportpaket som redan är tillgängligt**: När du skapar ett nytt villkor eller redigerar ett befintligt villkor, om den valda rapportsviten redan har använts med [!DNL Target Recommendations], med ett dataintervall som är lika med eller mindre än det markerade dataintervallet, är data omedelbart tillgängliga och ingen engångsinställning krävs. I det här fallet, eller om en algoritms inställningar redigeras utan att den valda rapportsviten eller dataintervallet ändras, körs eller körs om inom 12 timmar.
* **Pågående algoritmkörningar**: Dataflöden från [!DNL Analytics] till [!DNL Target Recommendations] dagligen. För [!UICONTROL Viewed Affinity] när en användare tittar på en produkt skickas ett spårningsanrop till produktvyn till [!DNL Analytics] nära realtid. The [!DNL Analytics] data skickas till [!DNL Target] tidigt nästa dag och [!DNL Target] kör algoritmen på mindre än 12 timmar.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] kräver att ingen offlinealgoritm körs och resultaten är omedelbart tillgängliga. [!UICONTROL Top Viewed] och [!UICONTROL Top Sellers] algoritmer som bygger på mbox-data ger i allmänhet resultat mycket snabbt på grund av den enklare beräkning som krävs. Detta kan vara bra alternativ när du vill förhandsgranska en designändring eller bekräfta att beteendedata samlas in korrekt.

## Använda QA-länkar för att förhandsgranska Recommendations

När algoritmen har fått resultat klara kan du förhandsgranska dessa resultat med [QA-länk](/help/main/c-activities/c-activity-qa/activity-qa.md) funktionaliteten i [!DNL Adobe Target]. QA-länkar finns i [!UICONTROL Activity QA] på sidan Activity overview:

![Länk till aktivitets-QA](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>Som standard [!DNL Target] lägger automatiskt till dig till den önskade målgruppen för QA-länken. Om den här inställningen är inaktiverad och din aktivitet har målinriktningsregler, måste din användarprofil uppfylla dessa målinriktningsregler för att se upplevelsen som innehåller rekommendationer.

Om du använder en QA-länk kan du förhandsgranska rekommendationerna på sidan:

![Produkter](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Mål-QA-läget är&quot;klisterlöst&quot; och sparas i en cookie. Om du inte avslutar QA-läget kommer du att fortsätta se QA-resultaten på hela webbplatsen. Om du vill avsluta QA-läget använder du [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* När du är i QA-läge kommer surfning av webbplatsen inte att påverka din profils [!UICONTROL Recently Viewed Items] eller [!UICONTROL Recently Purchased Items]. Detta beteende sker genom design för att undvika oavsiktlig förorening av produktionsbeteendedata. Förhandsgranska resultat från en [!UICONTROL Recently Viewed Items] eller [!UICONTROL User-Based Recommendations] -villkor, bläddra först på webbplatsen utanför QA-läget och använd sedan samma session för att öppna en QA-lägeslänk.


## Använda CSV-nedladdning för att förhandsgranska rekommendationer

I vissa fall kanske du vill granska de specifika objekten som rekommenderas. Detta är särskilt användbart när du använder algoritmer som [!UICONTROL People Who Viewed This, Viewed That], där olika objektuppsättningar rekommenderas beroende på vilket objekt användaren visar just nu, och du kan ha tusentals eller miljontals olika objekt i katalogen.

Resultaten kan inte hämtas förrän en [!UICONTROL Results Ready] status visas för minst en algoritm i aktiviteten.

Om du vill hämta resultat för förhandsgranskning klickar du på menyikonen i det övre högra hörnet av sidan Aktivitetsöversikt och sedan på **[!UICONTROL Download data]**.

![Alternativet Hämta data](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

En CSV-fil hämtas. Öppna den och se rekommenderade objekt:

![CSV-fil för rekommenderade objekt](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

Från vänster till höger finns en lista med rekommenderade objekt, i det här fallet de som visas mest. Rekommendationerna separeras av miljön, i det här fallet har endast produktionsmiljön rekommendationer. För den här algoritmen har vi inte tillämpat några begränsningar baserat på nyckelvärde, så raden som är märkt med en asterisk (*) innehåller hela uppsättningen rekommendationer. För andra algoritmtyper baserade på ett nyckelvärde, som [!UICONTROL People Who Viewed This, Viewed That], listas nyckelvärdena (d.v.s.&quot;This&quot; items) i kolumnen längst till vänster och de rekommenderade objekten (t.ex.&quot;That&quot;-objekten) listas från vänster till höger i kolumnerna recommendation_X.

>[!NOTE]
>
>Resultathämtningar är inte tillgängliga för aktiviteter som innehåller en [!UICONTROL User-Based Recommendations] algoritm. Resultathämtningar är inte tillgängliga för villkor som använder [!UICONTROL Recently-Viewed Items] rekommendationslogik.

## Aktivera din Recommendations-aktivitet

Från [!UICONTROL Activity Overview] klickar du på listrutepilen bredvid statusen och väljer **[!UICONTROL Activate]**.

![Alternativet Aktivera](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

Observera att statusen blir [!UICONTROL Activating]:

![Aktiverar](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

Efter några sekunder till några minuter ändras statusen till [!UICONTROL Live]:

![Live](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

Observera att du även kan inaktivera eller arkivera aktiviteten med samma nedrullningsbara lista.

## Undvik avbrott vid ändring av Recommendations-inställningar

Ändrar [!DNL Recommendations] samlingar, villkor, kampanjer eller designinställningar i en aktiv aktivitet kan göra att algoritmresultaten blir ogiltiga och algoritmens status ändras till [!UICONTROL Results Not Ready].

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
