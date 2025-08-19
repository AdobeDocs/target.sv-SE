---
keywords: målgrupp;målgruppsregler;skapa målgrupp;skapa målgrupp
description: Lär dig hur du skapar anpassade målgrupper och sparar dem i biblioteket  [!DNL Adobe Target] [!UICONTROL Audiences] för användning i aktiviteter.
title: Hur skapar jag målgrupper?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: 19d2b14f137fe4dbf95e9f9f9b84f80b93d1e281
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Skapa målgrupper i [!DNL Target]

Skapa anpassade målgrupper och spara dem i biblioteket [!DNL Adobe Target] [!UICONTROL Audiences] för användning i dina aktiviteter. Ni kan också kopiera en befintlig målgrupp som ni sedan kan redigera för att skapa en liknande målgrupp och kombinera flera målgrupper.

## Målgruppsöversikt

Målgrupper definieras av regler som bestämmer vem som är inkluderad eller exkluderad från en [!DNL Target]-aktivitet. En målgruppsdefinition kan innehålla flera regler och varje regel kan innehålla flera parametrar. Komplexa målgruppsdefinitioner använder de booleska operatorerna AND och OR för att kombinera regler och parametrar för att ge dig detaljerad kontroll över vilka webbplatsbesökare som räknas som aktivitetsdeltagare.

När du kombinerar regler eller parametrar med AND måste alla potentiella målgruppsmedlemmar uppfylla *alla* definierade villkor som ska inkluderas som deltagare. Om du till exempel definierar en OS-regel OCH en webbläsarregel inkluderas endast besökare som använder både det definierade operativsystemet *och*, den definierade webbläsaren, i aktiviteten.

När du kombinerar regler eller parametrar med ELLER behöver en potentiell målgruppsmedlem bara uppfylla ett enda definierat villkor som ska ingå som deltagare. Om du till exempel definierar flera mobilregler som är kopplade till OR, inkluderas besökare som uppfyller *något* av de definierade villkoren i aktiviteten.

Du kan blanda båda booleska operatorer för att skapa komplexa regler, men operatorer på samma regelnivå måste matcha. Användargränssnittet använder automatiskt rätt operator.

Följande regel riktar sig till exempel till besökare som använder antingen [!DNL Chrome] *eller* [!DNL Firefox] på en [!DNL Windows]-dator:

![Skapa målgrupp](assets/audience_create.png)

>[!NOTE]
>
>Undvik att skapa regler som utesluter alla potentiella målgruppsmedlemmar. Det är till exempel inte möjligt för någon att besöka en sida med [!DNL Chrome] *och* [!DNL Firefox] samtidigt.

## Skapa en målgrupp

1. Klicka på **[!UICONTROL Audiences]** i den övre menyraden.

   ![audiences_list image](assets/audiences_list.png)

1. Klicka på [!UICONTROL Audiences] i listan **[!UICONTROL Create Audience]**.

   eller

   Om du vill kopiera en befintlig målgrupp går du till listan [!UICONTROL Audiences] och klickar på ikonen **[!UICONTROL More Actions]** ( ![Fler åtgärder-ikon](/help/main/assets/icons/MoreSmallListVert.svg) ) för den målgrupp du vill kopiera och klickar sedan på **[!UICONTROL Duplicate]**. Sedan kan ni redigera målgruppen för att skapa en liknande målgrupp.

1. Skriv ett unikt, beskrivande målgruppsnamn och en valfri beskrivning.

   Målgruppsnamn får inte börja med följande tecken:

   `=  +  -  !  @`

   Målgruppsnamn får inte innehålla någon av följande teckensekvenser:

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  ['  ]'`

1. Dra och släpp önskade attribut från listan **[!UICONTROL Attributes]** till vänster i rutan för målgruppsverktyget.

   ![Dra och släpp attribut](assets/drag-attribute.png)

   Varje regeltyp har sina egna parametrar. Mer information om hur du konfigurerar varje typ av målgruppsregel finns i [Kategorier för målgrupper](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D).

1. Definiera regelparametrarna.

   Följande målgrupp riktar sig till exempel till besökare från Utah som använder operativsystemet [!DNL Macintosh].

   ![Utah/Macintosh-målgrupp](assets/adience-builder.png)

1. (Villkorligt) Fortsätt lägga till och definiera önskade attribut.

   Om du vill skapa en annan behållare klickar du på **[!UICONTROL Add container]** eller drar ett annat attribut till rutan Audience Builder. Du kan sedan justera operatorn (AND eller OR) med hjälp av listrutan.

1. Klicka på **[!UICONTROL Done]**.

   Nyligen skapade målgrupper visas i listan efter några sekunder av bearbetningsfördröjningen. Om målgruppen inte visas omedelbart i listan kan du söka efter målgruppen eller uppdatera listan.

## Utbildningsvideo: Skapar märket ![Översikt](/help/main/assets/overview.png)

Den här videon innehåller information om hur du skapar målgrupper.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
