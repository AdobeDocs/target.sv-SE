---
keywords: målgrupp;målgruppsregler;skapa målgrupp;skapa målgrupp
description: Lär dig skapa anpassade målgrupper och spara dem i [!DNL Adobe Target] [!UICONTROL Audiences] bibliotek för användning i aktiviteter.
title: Hur skapar jag målgrupper?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: aac542bd5adfb60a97a090a0e98f3e883eb49bd1
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Bygg målgrupper i [!DNL Target]

Du kan skapa anpassade målgrupper och spara dem i [!DNL Adobe Target] [!UICONTROL Audiences] bibliotek som du kan använda i dina aktiviteter. Ni kan också kopiera en befintlig målgrupp som ni sedan kan redigera för att skapa en liknande målgrupp och kombinera flera målgrupper.

## Målgruppsöversikt

Målgrupper definieras av regler som bestämmer vem som är inkluderad i eller utesluten från en [!DNL Target] aktivitet. En målgruppsdefinition kan innehålla flera regler och varje regel kan innehålla flera parametrar. Komplexa målgruppsdefinitioner använder de booleska operatorerna AND och OR för att kombinera regler och parametrar för att ge dig detaljerad kontroll över vilka webbplatsbesökare som räknas som aktivitetsdeltagare.

När ni kombinerar regler eller parametrar med AND måste alla potentiella målgruppsmedlemmar uppfylla *alla* definierade villkor som ska ingå som deltagare. Om du till exempel definierar en OS-regel OCH en webbläsarregel, är det bara besökare som använder båda de definierade operativsystemen *och* den definierade webbläsaren ingår i aktiviteten.

När du kombinerar regler eller parametrar med ELLER behöver en potentiell målgruppsmedlem bara uppfylla ett enda definierat villkor som ska ingå som deltagare. Om du till exempel definierar flera mobilregler som är kopplade av ELLER, ska besökare mötas *alla* av de definierade kriterierna ingår i aktiviteten.

Du kan blanda båda booleska operatorer för att skapa komplexa regler; operatorer på samma regelnivå måste dock matcha. Användargränssnittet använder automatiskt rätt operator.

Följande regel riktar sig till exempel till besökare som använder antingen Chrome *eller* Firefox på en Windows-dator:

![Skapa målgrupper](assets/audience_create.png)

>[!NOTE]
>
>Undvik att skapa regler som utesluter alla potentiella målgruppsmedlemmar. Det är till exempel inte möjligt för någon att besöka en sida med Chrome *och* Firefox samtidigt.

## Skapa en målgrupp

1. Klicka **[!UICONTROL Audiences]** i den övre menyraden.

   ![audiences_list image](assets/audiences_list.png)

1. Från [!UICONTROL Audiences] lista, klicka på **[!UICONTROL Create Audience]**.

   eller

   Kopiera en befintlig målgrupp från [!UICONTROL Audiences] klickar du på **[!UICONTROL More Actions]** ikon (ellipsikonen) och klicka sedan på **[!UICONTROL Duplicate]**. Sedan kan ni redigera målgruppen för att skapa en liknande målgrupp.

1. Skriv ett unikt, beskrivande målgruppsnamn och en valfri beskrivning.

   Målgruppsnamn får inte börja med följande tecken:

   `=  +  -  !  @`

   Målgruppsnamn får inte innehålla någon av följande teckensekvenser:

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  [  ]`

1. Dra och släpp önskade attribut från **[!UICONTROL Attributes]** till höger om målgruppsbyggaren.

   ![Dra och släpp attribut](assets/drag-attribute.png)

   Varje regeltyp har sina egna parametrar. Se [Kategorier för målgrupper](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) om du vill ha mer information om hur du konfigurerar varje typ av målgruppsregel.

1. Definiera regelparametrarna.

   Följande målgrupp riktar sig till exempel till besökare från Utah som använder operativsystemet Macintosh.

   ![Utah/Macintosh](assets/adience-builder.png)

1. (Villkorligt) Fortsätt lägga till och definiera önskade attribut.

   Om du vill skapa en annan behållare klickar du på **[!UICONTROL Add container]** eller dra ett annat attribut till rutan Audience Builder. Du kan sedan justera operatorn (AND eller OR) med hjälp av listrutan.

1. Klicka på **[!UICONTROL Done]**.

   Nyligen skapade målgrupper visas i listan efter några sekunder av bearbetningsfördröjningen. Om målgruppen inte visas omedelbart i listan kan du söka efter målgruppen eller uppdatera listan.

## Utbildningsvideo: Skapa målgrupper ![Märket Översikt](/help/main/assets/overview.png)

Den här videon innehåller information om hur du skapar målgrupper.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
