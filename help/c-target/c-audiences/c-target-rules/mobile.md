---
keywords: targeting;mobile;target mobile;deviceatlas;iphone;iphone models;device atlas;displaywidth;display width;display height;type of device;displayheight;phone;tablet;device model
description: Skapa målgrupper i Adobe Target för att inrikta er på mobila enheter baserat på parametrar som mobilenhet, typ av enhet, enhetsleverantör, skärmdimensioner (i pixlar) med mera.
title: Mobilalternativ i Adobe Target
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---


# Mobil{#mobile}

Skapa målgrupper för mobila enheter baserat på parametrar som mobil enhet, typ av enhet, enhetsleverantör, skärmdimensioner (i pixlar) med mera.

Du kanske vill visa olika innehåll för användare som skriver din sida från en telefon än du skulle göra om de besöker en dator. I så fall kan du välja mobilanvändare, sedan välja alternativet **[!UICONTROL Is Mobile Phone]** och sedan lägga till information som är viktig för dig, t.ex. telefontyp, skärmstorlek (i pixlar) och så vidare.

Mobil anpassning levereras av [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), en tjänst i DotMobi. DeviceAtlas är en omfattande databas med mobila enheter som bygger på data från många olika källor, bland annat tillverkare och nätoperatörer. Dessa data verifieras, korsrefereras och valideras för att skapa en stor och korrekt databas för mobila enheter som är tillgänglig.

Enhetsidentifiering görs genom analys av strängar för användaragent. Vissa enhetstillverkare, till exempel Apple, inaktiverar den här funktionen genom att inte tillhandahålla tillräckligt med information i användargränssnittet.

Apple-enheter delar till exempel inte enhetsmodellspecifika tokens i användargränssnittet. Resultatet är att det inte går att identifiera iPhone-modeller (som iPhone 5S, iPhone SE, iPhone 6 och så vidare) med en enkel nyckelordsbaserad metod.

För att lösa detta samlar Target in ytterligare data för att kunna identifiera iPhone och andra Apple-enheter korrekt med hjälp av följande parametrar:

| Parameter | Typ | Beskrivning |
|--- |--- |--- |
| devicePixelRatio | Sträng | Förhållandet mellan fysiska pixlar och enhetsoberoende pixlar (dips) i webbläsaren.  t.ex. &quot;1.5&quot; eller &quot;2&quot; |
| screenOrientation | Sträng | Enheten och webbläsarens JavaScript-motor har stöd för Device Orientation (Device Orientation). Kan vara liggande eller stående. |
| webGLRenderer | Sträng | Webbläsaråtergivning av grafikdrivrutinen. |

>[!NOTE]
>
>Kunder som använder Mobile SDK behöver inte göra något för att utnyttja den här funktionen. Kunder som använder at.js måste [uppgradera till at.js version 1.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (eller senare).

Du kan välja mer än en mobil enhetsegenskap. Flera markeringar förenas med en OR.

Kunder som använder en anpassad integrering (som inte använder at.js eller Mobile SDK) kan samla in dessa parametrar själva och skicka dem som mbox-parametrar.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Mobile]**.
1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

   * Namn på enhetsmarknadsföring
   * Enhetsmodell
   * Enhetsleverantör
   * Är mobil enhet
   * Är mobiltelefon
   * Är en surfplatta
   * OS
   * Skärmhöjd (px)
   * Skärmbredd (px)

   >[!NOTE]
   >
   >På grund av de nya ändringarna som introducerades i iOS 12.2 påverkas skapandet av en målgrupp med regler definierade av Device Marketing Name och Device Model som anger iPhone Models. Vi kan inte längre rikta in oss på användare som har iPhone med iOS 12.2 installerat. Men om de användarna inte har iOS 12.2 fortsätter iPhone-modellens mål att fungera korrekt.
   >
   >Uppdateringen för iOS 12.2 påverkar inte identifieringen av följande modeller eftersom dessa inte stöder uppgradering till iOS 12.2: iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad, iPad 2, iPad/Retina-skärm, iPad Retina (4:e generationen), iPod Touch 4 och iPod Touch 5.

   >[!NOTE]
   >
   >Du kan ange som mål för mobiltelefonoperatören med [geografiska inställningar](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Save]**.

Följande bild visar en målgrupp som målar besökare med enheter som tillverkats av Google och som är mobila enheter.

![Målmobila enheter](assets/target_mobile.png)

## Utbildningsvideo: Skapa målgrupper

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
