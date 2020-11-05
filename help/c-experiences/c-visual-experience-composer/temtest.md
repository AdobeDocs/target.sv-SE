---
keywords: template testing;template;same experience on similar pages;template test
description: Använd en sidmall i Adobe Target för att strukturera sidorna, eller om sidorna innehåller liknande element, för att testa variationer i liknande strukturerade sidelement.
title: Inkludera samma upplevelse på liknande sidor med Adobe Target
feature: experiences
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---


# Inkludera samma upplevelse på liknande sidor

Använd en sidmall i [!DNL Adobe Target] för att strukturera sidorna, eller om sidorna innehåller liknande element, för att testa variationer i liknande strukturerade sidelement eller i hela domänen.

För att funktionen ska fungera på rätt sätt måste den användas på sidor som har en liknande struktur eller innehåller mallelement som är strukturerade på samma sätt på alla sidor.

>[!IMPORTANT]
>
>Om du använder den här funktionen för att ändra element mellan olika sidor kommer det troligen att ge oväntade resultat.

Du kan till exempel använda den här funktionen för att göra något av följande:

* Testa ett globalt navigeringsfält genom att ordna om eller ta bort element
* Ta bort ett objekt från alla produktsidor som använder en viss sidmall
* Lägga till en banderoll på alla produktsidor
* Ändra layouten för artikelmallen

Du kan ange sidor som innehåller ändringselementen eller tillämpa ändringen på hela platsen eller domänen.

1. Skapa eller redigera en aktivitet enligt beskrivningen i [Aktiviteter](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Om du vill ange på vilka sidor upplevelsen ska visas klickar du på kugghjulsikonen i [!UICONTROL Visual Experience Composer] (VEC) och väljer **[!UICONTROL Page Delivery]**.

   ![Kugghjulsikon > Sidleverans](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Klicka **[!UICONTROL Add Template Rule]** och ange sedan villkoren för de sidor som du vill lägga till upplevelsen i.

1. Ange sidintervall. Sidintervallet kan vara något av följande:

   * URL (Mer information om hur Target utvärderar URL:er finns i Vanliga frågor om [mål och målgrupper](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * Domän
   * Bana
   * Hash-fragment (#) (ange den del av en URL som följer efter symbolen # som mål.)
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
   >Flera objekt använder ELLER-logik, vilket innebär att villkoret är sant för alla objekt i listan.

1. Om du vill kan du ange ytterligare villkor genom att klicka på **[!UICONTROL Add Template Rule]** och upprepa proceduren i föregående steg.

   Flera villkor förenas med AND-logik. [!DNL Target] lägger till upplevelsen på alla sidor som matchar det angivna villkoret.

>[!IMPORTANT]
>
> [!DNL Target] kan inte kontrollera om sidorna ser ut som förväntat, så det är alltid en viktig vana att testa berörda sidor innan de publiceras med den här funktionen.

## Användningsexempel

Läs följande användningsexempel om du vill se hur du kan använda mallregler på din webbplats:

### Återge samma aktivitet i hela domänen

Du kan överväga att använda mallregler för att återge samma aktivitet i hela domänen för följande användningsområden:

* Inkludera ett globalt sidhuvud eller en sidfot
* Att inkludera en global banderoll (till exempel COVID-19-meddelanden)
* Om du vill delta i ett globalt erbjudande om fri frakt

1. Skapa eller redigera en aktivitet enligt beskrivningen i [Aktiviteter](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Om du vill ange den domän där upplevelsen ska visas klickar du på kugghjulsikonen i Visual Experience Composer och väljer sedan **[!UICONTROL Page Delivery]**.

1. Klicka på **[!UICONTROL Add Template Rule]** > **[!UICONTROL Domain]**.

1. I listrutan **[!UICONTROL Choose evaluator]** väljer du **[!UICONTROL Contains]** och anger sedan domänen.

   ![Domänen innehåller](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Utbildningsvideo: Visual Experience Composer (2 av 2) (7:29) ![Självstudiemärke](/help/assets/tutorial.png)

* Byta namn på och duplicera en upplevelse
* Skapa en omdirigeringsupplevelse
* Anpassa en aktivitet till en enskild URL-adress eller en grupp URL-adresser
* Skapa en flersidig aktivitet
* Förgranska och skapa upplevelser för responsiva webbplatser
* Använda övertäckningar för att markera typer av element

>[!VIDEO](https://video.tv.adobe.com/v/17401)