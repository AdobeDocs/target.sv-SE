---
keywords: Experience Targeting;Landing Page Test
description: En elementväljare är ett CSS-uttryck som kan identifiera ett eller flera element. Lär dig använda elementväljare i Adobe [!DNL Target] Visual Experience Composer (VEC).
title: Kan jag använda elementväljare i Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Elementväljare som används i Visual Experience Composer

En elementväljare är ett CSS-uttryck som kan identifiera ett eller flera element.

Grundläggande information om CSS-väljare finns i dokumentet [Selectors](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) i Mozilla Developer Network (MDN).

Du kan ange om element-ID:n som klassas eller element-ID:n ska användas i dina kontoinställningar. Klicka på **[!UICONTROL Administration > Visual Experience Composer]** och välj sedan dina önskade CSS-väljare.

![css_selectors image](assets/css_selectors.png)

>[!NOTE]
>
>Elementklasser är tillgängliga som väljare i A/B Test-, Automated Personalization- och Multivariate Test-aktiviteter.

Mer information om när CSS-väljare ska användas och när unika ID:n ska användas finns i [Bästa metoder och begränsningar i Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6).

## Så här genererar Adobe [!DNL Target] en väljare för ett element {#section_D89D954BCBFB486CA081BE183776A475}

Målet använder en enkel algoritm för att skapa en väljare. Här följer en kort beskrivning av genereringslogiken:

1. Om ett element har ett id, till exempel `id="container"`, är väljaren för elementet `#container`.

   Exempel:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. Om ett element innehåller ett klassattribut försöker Target utnyttja den första klassen i alla klasser som finns i elementet.

   Målet försöker tolka det överordnade elementet tills det hittar elementet `<HTML>` eller ett element med ett ID. När ett element innehåller ett id och väljaren beräknas på dess underordnade underordnade objekt, bidrar elementets id till väljaren.

   Exempel:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   I detta exempel:

   Väljare: `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (&quot; > &quot; anger det omedelbara underordnade objektet.)

   `eq` anger för indexet att det finns ett element som har &quot;tagName=UL&quot; och den första klassen är `navigation`. Därför är `index` 0. Mer information finns i artikeln [Väljare](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) i MDN.

1. Om ett element inte innehåller någon klass använder Target `tagName` för elementet och går uppåt i det överordnade elementet tills antingen elementet `<HTML>` eller ett element med ett ID hittas.

   Exempel:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   Väljare: `#container` > `ul.navigation(0)` > `li:nth-of-type(4)`

I ovanstående process:

* Du kan använda valfri CSS-väljare så länge den unikt identifierar ett element i DOM.
* Metoden ovan används av Target. Målet tillåter inte att du använder det här tillvägagångssättet. Du kan lägga till valfri väljare förutsatt att punkt 1 är sann.
* Du kan använda valfritt attribut i väljaren. I det här dokumentet används endast klassnamn som exempel.
