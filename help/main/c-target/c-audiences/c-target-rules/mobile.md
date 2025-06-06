---
keywords: mål;mobil;målmobil;målmobil;enhet;iphone;iphone models;device atlas;displaywidth;display width;display height;device;displayheight;phone;tablet;device model
description: Lär dig hur du skapar målgrupper i [!DNL Adobe Target] för att nå mobila enheter.
title: Kan jag rikta in besökarna baserat på mobilalternativ?
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Mobil

Skapa målgrupper i [!DNL Adobe Target] om du vill rikta in dig på mobila enheter baserat på parametrar som till exempel mobil enhet, typ av enhet, enhetsleverantör, skärmdimensioner med mera.

Du kanske till exempel vill visa olika innehåll för användare som besöker sidan via en telefon än du skulle visa om de besöker en dator. I så fall kan du välja målgruppen [!UICONTROL Mobile] och sedan välja alternativet **[!UICONTROL Is Mobile Phone]**. Du kan sedan lägga till specifik information som är viktig för dig, som telefontyp, skärmstorlek (i pixlar) och så vidare.

Mobil målinriktning levereras av [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), en tjänst i DotMobi. DeviceAtlas är en omfattande databas med mobila enheter som bygger på data från många olika källor, bland annat tillverkare och nätoperatörer. Dessa data verifieras, korsrefereras och valideras för att skapa en stor och korrekt databas för mobila enheter som är tillgänglig.

Enhetsidentifiering görs genom analys av strängar för användaragent. Vissa enhetstillverkare, till exempel Apple, inaktiverar den här funktionen genom att inte tillhandahålla tillräckligt med information i användargränssnittet.

Apple-enheter delar till exempel inte enhetsmodellspecifika tokens i användargränssnittet. Resultatet är att det inte går att identifiera iPhone-modeller (som iPhone 12 Pro, iPhone 12, iPhone 11 Pro Max och så vidare) med en enkel nyckelordsbaserad metod.

För att lösa det här problemet samlar [!DNL Target] in ytterligare data för att korrekt identifiera iPhone och andra Apple-enheter med följande parametrar:

| Parameter | Typ | Beskrivning |
|--- |--- |--- |
| devicePixelRatio | Sträng | Förhållandet mellan fysiska pixlar och enhetsoberoende pixlar (dips) i webbläsaren. Till exempel &quot;1.5&quot; eller &quot;2&quot; |
| screenOrientation | Sträng | Enheten och webbläsarens JavaScript-motor stöder Device Orientation (Device Orientation). Kan vara liggande eller stående. |
| webGLRenderer | Sträng | Webbläsaråtergivning av grafikdrivrutinen. |

>[!NOTE]
>
>Kunder som använder Mobile SDK behöver inte göra något för att använda den här funktionen. Kunder som använder at.js måste [uppgradera till at.js version 1.5.0](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} (eller senare).

Du kan välja mer än en mobil enhetsegenskap. Flera markeringar förenas med en OR-operator.

Kunder som använder en anpassad integrering (som inte använder at.js eller Mobile SDK) kan samla in dessa parametrar själva och skicka dem som mbox-parametrar.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Mobile]** i rutan för målgruppsbyggaren.
1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

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
   >Du kan ange mobiltelefonbärare som mål med hjälp av [geografiska inställningar](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

Följande bild visar en målgrupp som riktar sig till besökare med enheter som tillverkats av Google och som är mobila enheter.

![Anpassa mobila enheter](assets/target_mobile.png)

## Överväganden

Tänk på följande när du riktar dig till mobila enheter:

### Målenheter som kör iOS 12.2 eller senare

På grund av de nya ändringarna i iOS 12.2 påverkas skapandet av en målgrupp med regler definierade av [!UICONTROL Device Marketing Name] och [!UICONTROL Device Model] som anger iPhone-modeller. [!DNL Target] kan inte längre rikta sig till användare som har iPhone med iOS 12.2 (eller senare) installerat på sig. Om dessa användare inte har iOS 12.2 (eller senare) fortsätter dock iPhone Model-målsättningen att fungera korrekt.

IOS 12.2-uppdateringen (eller senare) påverkar inte identifieringen av följande modeller eftersom dessa inte stöder uppgradering till iOS 12.2: iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad, iPad 2, iPad/Retina-skärm, iPad Retina (4:e generationen), iPod Touch 4 och iPod Touch 5.

### Målenheter som kör Safari 14.0.2 (eller senare)

När du använder mobilregler för målenheter som kör Safari version 14.0.2 (eller senare) på macOS identifieras Safari felaktigt på Mac- och iPad-enheter på grund av ett känt problem med Apple användaragenter och DeviceAtlas. [!DNL Target] Denna fråga kommer att behandlas i framtiden.

## Utbildningsvideo: Skapa publiker

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
