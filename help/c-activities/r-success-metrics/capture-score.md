---
keywords: capture score;score
description: Mätvärdet för Capture Score-engagemang beräknar en sammanställd poäng baserad på värdet som tilldelats till de sidor som besöks på webbplatsen, från den punkt besökaren först ser kampanjens första visningsruta.
title: Hämtningspoäng
subtopic: Getting Started
topic: Standard
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Hämtningspoäng{#capture-score}

Mätvärdet för Capture Score-engagemang beräknar en sammanställd poäng baserad på värdet som tilldelats till de sidor som besöks på webbplatsen, från den punkt besökaren först ser kampanjens första visningsruta.

Följande exempel visar hur poängengagemang beräknas i en kampanj som testar två upplevelser, en med en kattbild och en med en hundbild.

![](assets/example_score.png)

I det här exemplet upplever den första besökaren kattupplevelsen. Anta att en global mbox passerar i ett sidnummer baserat på sidans värde. Om marknadsföraren har hämtat sidantal för ett framgångsmått som är kopplat till `**any mbox**`så ackumuleras besökspoängen för varje mbox-begäran som visas efter visningsrutan runt kattbilden.

Den första sidan lägger till 1 i poängen, den andra sidan 0.25, den tredje 0.10 och den fjärde 0.10 för totalt 1,45. Detta kan tolkas som antingen valuta eller poäng. Vid ett separat besök upplever besökaren Dog-upplevelsen, och även om besökaren visar färre sidor är poängen 2,10, vilket är större än vid det andra besöket, eftersom besökaren visade mer värdefulla sidor.

Du kan ta hänsyn till anskaffningskostnader och intäkter från länken genom att skicka adboxes och redirectors, vilket framgår av nästa sidflöde. Observera att båda rutorna på artikelsidan i det här exemplet skickar ett poängtal som kanske representerar en känd CPM.

![](assets/example_score2.png)

**Tilldela en sidpoäng**

Du kan tilldela ett värde till en sida på webbplatsen baserat på vad sidan är värd för dig. En matlagningssajt kan till exempel sälja annonser för mer pengar på sina artikelsidor än i sina upplevelseavsnitt. Funktionsartiklarna är därför mer värdefulla än upplevelseavsnittet. Med hjälp av sidpoäng kan du skapa ett totalt&quot;värde&quot; av ett besök, så att den som läser fler artiklar får fler&quot;poäng&quot; än den som bara bläddrar i upplevelsen.

Det finns två metoder för att tilldela en spets till en sida:

* Skapa en mbox-parameter med namnet `mboxPageValue`i mbox-koden.

   Exempel: `('global_mbox', 'mboxPageValue=10');`

   Det angivna värdet läggs till i poängen varje gång sidan med rutan visas. Om flera rutor på sidan innehåller poängvärden är poängen för sidan summan av alla mbox-värden. `mboxPageValue` är en reserverad parameter som används för att skicka värden i en mbox för att hämta ett engagemangsmoment. Positiva och negativa värden kan skickas. Summan beräknas i slutet av varje besökares besök för att beräkna den totala poängen för besöket.

* Skicka `?mboxPageValue=n` parametern i sidans URL.

   Exempel: `https://www.mydomain.com?mboxPageValue=5`

   Med den här metoden läggs det angivna värdet till i poängen för varje ruta på sidan. Om du till exempel skickar parametern `?mboxPageValue=10`och det finns tre rutor på sidan, blir poängen för sidan 30.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>Rutor ovanför kampanjens första visningsruta inkluderas inte i poängen.

Det bästa sättet är att tilldela värden i mbox-koden. På så sätt kan du vara exakt i de värden som du mäter, beroende på innehållet i varje ruta.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>För enklare underhåll kan du konfigurera webbplatsens tilldelningar av sidpoängsvärden i [!DNL at.js] - eller [!DNL mbox.js] filen med viss villkorsstyrd JavaScript-logik. På så sätt slipper du lägga till mer kod på sidorna. Kontakta din kontokonsult om du behöver hjälp.

Du kan kombinera de två metoderna, men det kan resultera i ett högre poäng än förväntat. Om du till exempel tilldelar värdet 10 till var och en av de tre rutorna och ingen poäng till en fjärde mbox skickar du URL-parametern `?mboxPageValue=5`blir sidpoängen 50, 30 för de tre rutorna med tilldelade värden och sedan 5 för var och en av de fyra rutorna på sidan.

Räknaren börjar med den första visningsrutan, inte med postrutan. Om du till exempel anger kampanjen på hemsidan som inte har någon visningsruta, och sedan länkar till katalogsidan som innehåller en visningsruta, börjar räknaren när du flyttar till katalogsidan.

Du kan också ange negativa värden på vissa sidor som kostar pengar eller inte är bra för besökaren att se. De negativa värdena påverkar också det övergripande poängtalet. Den här tekniken kan användas på en sida som besökarna når från en annons, så att du vet hur mycket CPC:n var. Den kan till exempel användas för en support- eller kontaktsida där du vet att besökarna kan ringa eller begära hjälp från den här sidan.
