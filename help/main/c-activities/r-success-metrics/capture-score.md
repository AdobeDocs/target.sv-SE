---
keywords: inspelningspoäng;poäng
description: Läs mer om Capture Score Engagement Metric i Adobe [!DNL Target] som beräknar ett aggregerat poängvärde baserat på det värde som tilldelats de sidor som besöks på webbplatsen.
title: Vad är mätvärdet för Capture Score?
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 0%

---

# Hämtningspoäng

Interaktionsstatistik för Capture Score i [!DNL Adobe Target] beräknar ett aggregerat poängvärde baserat på det värde som tilldelats de sidor som besöks på webbplatsen, från den punkt där besökaren först ser kampanjens första visning [!DNL Target] begäran.

Följande exempel visar hur poängengagemang beräknas i en kampanj som testar två upplevelser, en med en kattbild och en med en hundbild.

![example_score image](assets/example_score.png)

I det här exemplet upplever den första besökaren kattupplevelsen. Anta att en global [!DNL Target] begäran skickas i en sidpoäng som baseras på sidans värde. Om marknadsföraren har hämtat sidantalsengagemang för ett framgångsmått som är kopplat till `**any Target request**`läggs besökspoängen på alla förfrågningar som visas efter visningsbegäran runt kattbilden.

Den första sidan lägger till 1 i poängen, den andra sidan 0.25, den tredje 0.10 och den fjärde 0.10 för totalt 1,45. Detta kan tolkas som antingen valuta eller poäng. Vid ett separat besök upplever besökaren Dog-upplevelsen, och även om besökaren visar färre sidor är poängen 2,10, vilket är större än vid det andra besöket, eftersom besökaren visade mer värdefulla sidor.

Du kan ta hänsyn till anskaffningskostnader och intäkter från länken genom att skicka adboxes och redirectors, vilket framgår av nästa sidflöde. Observera att i det här exemplet gäller båda [!DNL Target] begäranden på artikelsidan skickar ett poängtal, som kanske representerar en känd CPM.

![example_score2 image](assets/example_score2.png)

## Tilldela en sidpoäng

Du kan tilldela ett värde till en sida på webbplatsen baserat på vad sidan är värd för dig. En matlagningssajt kan till exempel sälja annonser för mer pengar på sina artikelsidor än i sina upplevelseavsnitt. Funktionsartiklarna är därför mer värdefulla än upplevelseavsnittet. Med hjälp av sidpoäng kan du skapa ett totalt&quot;värde&quot; av ett besök, så att den som läser fler artiklar får fler&quot;poäng&quot; än den som bara bläddrar i upplevelsen.

Det finns två metoder för att tilldela en spets till en sida:

* I [!DNL Target] begäran, skapa en parameter som kallas `mboxPageValue`.

   Exempel: `('global_mbox', 'mboxPageValue=10');`

   Det angivna värdet läggs till i poängen varje gång sidan med det [!DNL Target] begäran visas. Om flera begäranden på sidan innehåller poängvärden, är poängen för sidan summan av alla begärandevärden. `mboxPageValue` är en reserverad parameter som används för att skicka värden i en Target-begäran för att hämta ett engagemangsmoment. Positiva och negativa värden kan skickas. Summan beräknas i slutet av varje besökares besök för att beräkna den totala poängen för besöket.

* Skicka `?mboxPageValue=n` i sidans URL.

   Exempel: `https://www.mydomain.com?mboxPageValue=5`

   Med den här metoden läggs det angivna värdet till i poängen för varje [!DNL Target] begäran på sidan. Om du till exempel skickar parametern `?mboxPageValue=10`och det finns tre [!DNL Target] på sidan är poängen för sidan 30.

>[!NOTE]
>
>Målbegäranden som finns ovanför aktivitetens första skärm [!DNL Target] begäran kommer inte att inkluderas i poängen.

Det bästa är att tilldela värden i [!DNL Target] begäran. På så sätt kan du vara exakt i de värden som du mäter, beroende på innehållet i varje begäran.

>[!NOTE]
>
>För enklare underhåll kan du konfigurera webbplatsens tilldelningar av sidpoängsvärden i [!DNL at.js] -fil med viss villkorsstyrd JavaScript-logik. På så sätt slipper du lägga till mer kod på sidorna. Kontakta din kontokonsult om du behöver hjälp.

Du kan kombinera de två metoderna, men det kan resultera i ett högre poäng än förväntat. Om du till exempel tilldelar värdet 10 till var och en av tre [!DNL Target] begäranden och ingen poäng till en fjärde begäran, skicka sedan URL-parametern `?mboxPageValue=5`blir sidpoängen 50, 30 för de tre förfrågningarna med tilldelade värden och 5 för var och en av de fyra förfrågningarna på sidan.

Räknaren börjar med den första visningsbegäran, inte med anmälningsbegäran. Om du till exempel anger aktiviteten på hemsidan som inte har någon visningsbegäran och sedan länkar till katalogsidan som innehåller en visningsbegäran, börjar räknaren när du flyttar till katalogsidan.

Du kan också ange negativa värden på vissa sidor som kostar pengar eller inte är bra för besökaren att se. De negativa värdena påverkar också det övergripande poängtalet. Den här tekniken kan användas på en sida som besökarna når från en annons, så att du vet hur mycket CPC:n var. Den kan till exempel användas för en support- eller kontaktsida där du vet att besökarna kan ringa eller begära hjälp från den här sidan.
