---
keywords: malltestning;mall;samma upplevelse på liknande sidor;malltest
description: Lär dig använda Adobe [!DNL Target] Visual Experience Composer (VEC) om du vill inkludera samma upplevelse på flera sidor som är strukturerade på liknande sätt eller innehåller samma mallelement.
title: Kan jag inkludera samma upplevelse på liknande sidor?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---

# Inkludera samma upplevelse på liknande sidor

Använda en sidmall i [!DNL Adobe Target] om du vill skapa en struktur för sidorna, eller om sidorna innehåller liknande element, om du vill testa variationer i liknande strukturerade sidelement eller i hela domänen.

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

1. Skapa eller redigera en aktivitet enligt beskrivningen i [Verksamhet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Om du vill ange på vilka sidor upplevelsen ska visas går du till [!UICONTROL Visual Experience Composer] (VEC) klicka på kugghjulsikonen och välj sedan **[!UICONTROL Page Delivery]**.

   ![Kugghjulsikon > Sidleverans](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Klicka **[!UICONTROL Add Template Rule]** anger du sedan villkoren för de sidor som du vill lägga till upplevelsen i.

1. Ange sidintervall. Sidintervallet kan vara något av följande:

   * URL (Mer information om hur Target utvärderar URL:er finns i [Mål och målgrupper Frågor och svar](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
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

   Om du till exempel väljer **[!UICONTROL Domain]** och **[!UICONTROL Is (case sensitive)]** skriver du den domän där du vill att upplevelsen ska läggas till på alla sidor.

   Du kan inkludera flera objekt.

   >[!IMPORTANT]
   >
   >Flera objekt använder ELLER-logik, vilket innebär att villkoret är sant för alla objekt i listan.

1. Om du vill kan du ange ytterligare villkor genom att klicka **[!UICONTROL Add Template Rule]** och upprepa proceduren i föregående steg.

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

1. Skapa eller redigera en aktivitet enligt beskrivningen i [Verksamhet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Om du vill ange den domän där upplevelsen ska visas klickar du på kugghjulsikonen i Visual Experience Composer och väljer sedan **[!UICONTROL Page Delivery]**.

1. Klicka på **[!UICONTROL Add Template Rule]** > **[!UICONTROL Domain]**.

1. Från **[!UICONTROL Choose evaluator]** nedrullningsbar meny, välja **[!UICONTROL Contains]** anger du sedan domian.

   ![Domänen innehåller](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Utbildningsvideo: Visual Experience Composer (2 av 2) (7:29) ![Självstudiemärke](/help/main/assets/tutorial.png)

* Byta namn på och duplicera en upplevelse
* Skapa en omdirigeringsupplevelse
* Anpassa en aktivitet till en enskild URL-adress eller en grupp URL-adresser
* Skapa en flersidig aktivitet
* Förgranska och skapa upplevelser för responsiva webbplatser
* Använda övertäckningar för att markera typer av element

>[!VIDEO](https://video.tv.adobe.com/v/17401)
