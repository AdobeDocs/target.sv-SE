---
keywords: mål;mobil;målmobil;målmobil;enhet;iphone;iphone models;device atlas;displaywidth;display width;display height;device;displayheight;phone;tablet;device model
description: Lär dig skapa målgrupper i [!DNL Adobe Target] för mobila enheter.
title: Kan jag rikta in besökarna baserat på mobilalternativ?
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Mobil

Skapa målgrupper i [!DNL Adobe Target] för mobila enheter baserat på parametrar som mobil enhet, typ av enhet, enhetsleverantör, skärmdimensioner med mera.

Du kanske till exempel vill visa olika innehåll för användare som besöker sidan via en telefon än du skulle visa om de besöker en dator. I så fall kan du välja [!UICONTROL Mobile] väljer du **[!UICONTROL Is Mobile Phone]** alternativ. Du kan sedan lägga till specifik information som är viktig för dig, som telefontyp, skärmstorlek (i pixlar) och så vidare.

Mobil anpassning levereras av [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), en tjänst som tillhör DotMobi. DeviceAtlas är en omfattande databas med mobila enheter som bygger på data från många olika källor, bland annat tillverkare och nätoperatörer. Dessa data verifieras, korsrefereras och valideras för att skapa en stor och korrekt databas för mobila enheter som är tillgänglig.

Enhetsidentifiering görs genom analys av strängar för användaragent. Vissa enhetstillverkare, till exempel Apple, inaktiverar den här funktionen genom att inte tillhandahålla tillräckligt med information i användargränssnittet.

Apple-enheter delar till exempel inte enhetsmodellspecifika tokens i användargränssnittet. Resultatet är att det inte går att identifiera iPhone-modeller (som iPhone 12 Pro, iPhone 12, iPhone 11 Pro Max och så vidare) med en enkel nyckelordsbaserad metod.

För att lösa problemet [!DNL Target] samlar in ytterligare data för att kunna identifiera iPhone och andra Apple-enheter med följande parametrar:

| Parameter | Typ | Beskrivning |
|--- |--- |--- |
| devicePixelRatio | Sträng | Förhållandet mellan fysiska pixlar och enhetsoberoende pixlar (dips) i webbläsaren. Till exempel &quot;1.5&quot; eller &quot;2&quot; |
| screenOrientation | Sträng | Enheten och webbläsarens JavaScript-motor har stöd för Device Orientation (Device Orientation). Kan vara liggande eller stående. |
| webGLRenderer | Sträng | Webbläsaråtergivning av grafikdrivrutinen. |

>[!NOTE]
>
>Kunder som använder Mobile SDK behöver inte göra något för att använda den här funktionen. Kunder som använder at.js måste [uppgradera till at.js version 1.5.0](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} (eller senare).

Du kan välja mer än en mobil enhetsegenskap. Flera markeringar förenas med en OR-operator.

Kunder som använder en anpassad integrering (som inte använder at.js eller Mobile SDK) kan samla in dessa parametrar själva och skicka dem som mbox-parametrar.

1. I [!DNL Target] gränssnitt, klicka **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Mobile]** till målgruppsverktyget.
1. Klicka **[!UICONTROL Select]** väljer du sedan något av följande alternativ:

   * Namn på enhetsmarknadsföring
   * Enhetsmodell
   * Enhetsleverantör
   * Är mobil enhet
   * Är mobiltelefon
   * Är bärbar dator
   * OS
   * Skärmhöjd (px)
   * Skärmbredd (px)

   >[!NOTE]
   >
   >Du kan ange mobiltelefonbäraren som mål med [Geo-inställningar](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

Följande bild visar en målgrupp som riktar sig till besökare med enheter som tillverkats av Google och som är mobila enheter.

![Målmobila enheter](assets/target_mobile.png)

## Överväganden

Tänk på följande när du riktar dig till mobila enheter:

### Målenheter som kör iOS 12.2 eller senare

På grund av de nya ändringarna i iOS 12.2 har en målgrupp med regler som definieras av [!UICONTROL Device Marketing Name] och [!UICONTROL Device Model] som anger att iPhone Models påverkas. [!DNL Target] kan inte längre rikta in sig på användare som har iPhone med iOS 12.2 (eller senare) installerat. Om dessa användare inte har iOS 12.2 (eller senare) fortsätter dock iPhone Model-målsättningen att fungera korrekt.

IOS 12.2-uppdateringen (eller senare) påverkar inte identifieringen av följande modeller eftersom dessa inte stöder uppgradering till iOS 12.2: iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad, iPad 2, iPad/Retina-skärm, iPad Retina (4:e generationen), iPod Touch 4 och iPod Touch 5.

### Målenheter som kör Safari 14.0.2 (eller senare)

När mobilregler används för målenheter som kör Safari version 14.0.2 (eller senare) på macOS på grund av ett känt problem med Apple användaragenter och DeviceAtlas, [!DNL Target] på ett felaktigt sätt identifierar Safari på Mac- och iPad-enheter. Denna fråga kommer att behandlas i framtiden.

## Utbildningsvideo: Skapa publiker

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
