---
keywords: template testing;template;same experience on similar pages;template test
description: Om du använder en sidmall för att skapa en struktur för sidorna, eller om sidorna innehåller liknande element, kan du med den här funktionen testa variationer i liknande strukturerade sidelement.
title: Inkludera samma upplevelse på liknande sidor
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Inkludera samma upplevelse på liknande sidor{#include-the-same-experience-on-similar-pages}

Om du använder en sidmall för att skapa en struktur för sidorna, eller om sidorna innehåller liknande element, kan du med den här funktionen testa variationer i liknande strukturerade sidelement.

För att funktionen ska fungera på rätt sätt måste den användas på sidor med en mycket liknande struktur. eller innehåller mallelement som är strukturerade på samma sätt på alla sidor.

>[!IMPORTANT]
>
>Om du använder den här funktionen för att ändra element mellan olika sidor kommer det troligen att ge oväntade resultat.

Du kan till exempel använda den här funktionen för att göra något av följande:

* Testa ett globalt navigeringsfält genom att ordna om eller ta bort element
* Ta bort ett objekt från alla produktsidor som använder en viss sidmall
* Lägga till en banderoll på alla produktsidor
* Ändra layouten för artikelmallen

I följande demovideo finns information om hur du använder en mall:

Du kan ange sidor som innehåller de ändrade elementen eller använda ändringen på hela webbplatsen.

1. Skapa en aktivitet enligt beskrivningen i [Aktiviteter](../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).
1. Om du vill ange vilka sidor som upplevelsen ska visas på, klickar du på kugghjulsikonen i Visual Experience Composer och väljer sedan **[!UICONTROL Page Delivery]**.
1. Klicka **[!UICONTROL Add Template Rule]** och ange sedan villkoren för de sidor som du vill lägga till upplevelsen i.

1. Ange sidintervall. Sidintervallet kan vara något av följande:

   * URL (Mer information om hur Target utvärderar URL:er finns i Vanliga frågor om [mål och målgrupper](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * Domän
   * Bana
   * Hash-fragment (#) (Ange den del av en URL som följer efter symbolen # som mål.)
   * Fråga
   * Parameter

1. Välj en operator.

   Operatorn anger hur objekten efter operatorn relaterar till sidintervallet. Tillgängliga operatorer:

   * Innehåller
   * Innehåller inte
   * Är (skiftlägeskänsligt)
   * Är inte
   * Börjar med
   * Slutar med

1. Skriv strängarna som definierar var upplevelsen läggs till, till exempel domänen eller strängarna som finns i sidnamnet.

   Om du t.ex. väljer **[!UICONTROL Domain]** och **[!UICONTROL Is (case sensitive)]** skriver du den domän där du vill att upplevelsen ska läggas till på alla sidor.

   Du kan inkludera flera objekt.

   >[!IMPORTANT]
   >
   >Flera objekt använder `OR` logik, vilket innebär att villkoret är sant för alla objekt i listan.

1. Om du vill kan du ange ytterligare villkor genom att klicka på **[!UICONTROL Add Template Rule]** och upprepa proceduren i föregående steg.

   Flera villkor förenas med AND-logik. Adobe Target lägger till upplevelsen på alla sidor som matchar det angivna villkoret.

>[!IMPORTANT]
>
> Målet kan inte kontrollera om sidorna ser ut som förväntat, så det är alltid en viktig vana att testa berörda sidor innan de publiceras med den här funktionen.

## Utbildningsvideo: Visual Experience Composer (2 av 2) (7:29) ![Självstudiemärke](/help/assets/tutorial.png)

* Byta namn på och duplicera en upplevelse
* Skapa en omdirigeringsupplevelse
* Anpassa en aktivitet till en enskild URL-adress eller en grupp URL-adresser
* Skapa en flersidig aktivitet
* Förgranska och skapa upplevelser för responsiva webbplatser
* Använda övertäckningar för att markera typer av element

>[!VIDEO](https://video.tv.adobe.com/v/17401)