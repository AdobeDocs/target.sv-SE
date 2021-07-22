---
keywords: målgrupp;målgruppsregler;skapa målgrupp;skapa målgrupp
description: Lär dig hur du skapar anpassade målgrupper och sparar dem i [!DNL Adobe Target] [!UICONTROL Audiences] biblioteket för användning i dina aktiviteter.
title: Hur skapar jag målgrupper?
feature: Målgrupper
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: 20a5201b5c05b1f083252ac73b3b4bbc91e97aaa
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Bygg målgrupper i [!DNL Target]

Du kan skapa anpassade målgrupper och spara dem i [!DNL Adobe Target] [!UICONTROL Audiences]-biblioteket för användning i dina aktiviteter. Ni kan också kopiera en befintlig målgrupp som ni sedan kan redigera för att skapa en liknande målgrupp och kombinera flera målgrupper.

## Målgruppsöversikt

Målgrupper definieras av regler som bestämmer vem som är inkluderad eller utesluten från en [!DNL Target]-aktivitet. En målgruppsdefinition kan innehålla flera regler och varje regel kan innehålla flera parametrar. Komplexa målgruppsdefinitioner använder de booleska operatorerna AND och OR för att kombinera regler och parametrar för att ge dig detaljerad kontroll över vilka webbplatsbesökare som räknas som aktivitetsdeltagare.

När du kombinerar regler eller parametrar med AND måste alla potentiella målgruppsmedlemmar uppfylla *alla* definierade villkor som ska inkluderas som deltagare. Om du till exempel definierar en OS-regel OCH en webbläsarregel inkluderas endast besökare som använder både det definierade operativsystemet *och* den definierade webbläsaren i aktiviteten.

När du kombinerar regler eller parametrar med ELLER behöver en potentiell målgruppsmedlem bara uppfylla ett enda definierat villkor som ska ingå som deltagare. Om du till exempel definierar flera mobilregler som är kopplade till OR, inkluderas besökare som uppfyller *något* av de definierade villkoren i aktiviteten.

Du kan blanda båda booleska operatorer för att skapa komplexa regler; operatorer på samma regelnivå måste dock matcha. Användargränssnittet använder automatiskt rätt operator.

Följande regel riktar sig till exempel till besökare som använder antingen Chrome *eller* Firefox på en Windows-dator:

![Skapa målgrupper](assets/audience_create.png)

>[!NOTE]
>
>Undvik att skapa regler som utesluter alla potentiella målgruppsmedlemmar. Det är till exempel inte möjligt för någon att besöka en sida med Chrome *och* Firefox samtidigt.

## Skapa en målgrupp

1. Klicka på **[!UICONTROL Audiences]** i den övre menyraden.

   ![](assets/audiences_list.png)

1. Klicka på **[!UICONTROL Create Audience]** i listan [!UICONTROL Audiences].

   eller

   Om du vill kopiera en befintlig målgrupp går du till listan [!UICONTROL Audiences], klickar på ikonen **[!UICONTROL More Actions]** (ellipsikonen) och sedan på **[!UICONTROL Duplicate]**. Sedan kan ni redigera målgruppen för att skapa en liknande målgrupp.

1. Skriv ett unikt, beskrivande målgruppsnamn och en valfri beskrivning.
1. Dra och släpp önskade attribut från **[!UICONTROL Attributes]**-listan till höger om målgruppsbyggaren.

   ![Dra och släpp attribut](assets/drag-attribute.png)

   Varje regeltyp har sina egna parametrar. Mer information om hur du konfigurerar varje typ av målgruppsregel finns i [Kategorier för målgrupper](/help/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D).

1. Definiera regelparametrarna.

   Följande målgrupp riktar sig till exempel till besökare från Utah som använder operativsystemet Macintosh.

   ![Utah/Macintosh](assets/adience-builder.png)

1. (Villkorligt) Fortsätt lägga till och definiera önskade attribut.

   Om du vill skapa en annan behållare klickar du på **[!UICONTROL Add container]** eller drar ett annat attribut till den mittersta ramen. Du kan sedan justera operatorn (AND eller OR) med hjälp av listrutan.

1. Klicka på **[!UICONTROL Done]**.

   Nyligen skapade målgrupper visas i listan efter några sekunder av bearbetningsfördröjningen. Om målgruppen inte visas omedelbart i listan kan du söka efter målgruppen eller uppdatera listan.

## Utbildningsvideo: Skapar publikation ![Översikt](/help/assets/overview.png)

Den här videon innehåller information om hur du skapar målgrupper.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
