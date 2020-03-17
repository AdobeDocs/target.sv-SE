---
keywords: audience;audience rules;create audience;creating audience
description: Du kan skapa anpassade målgrupper och spara dem i målbiblioteket för att använda dem i dina aktiviteter. Ni kan kopiera en befintlig målgrupp som ni sedan kan redigera för att skapa en liknande målgrupp och kombinera flera målgrupper.
title: Bygg målgrupper i Target
topic: Advanced,Standard,Classic
uuid: 496dbb9d-cb13-47ee-88bd-ba5920b2ca1c
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Bygg målgrupper i Target{#build-audiences-in-target}

Du kan skapa anpassade målgrupper och spara dem i målbiblioteket för att använda dem i dina aktiviteter. Ni kan kopiera en befintlig målgrupp som ni sedan kan redigera för att skapa en liknande målgrupp och kombinera flera målgrupper.

## Målgruppsöversikt

Målgrupper definieras av regler som bestämmer vem som är inkluderad eller utesluten från en [!DNL Target] aktivitet. En målgruppsdefinition kan innehålla flera regler och varje regel kan innehålla flera parametrar. Komplexa målgruppsdefinitioner använder de booleska operatorerna AND och OR för att kombinera regler och parametrar för att ge dig detaljerad kontroll över vilka webbplatsbesökare som räknas som aktivitetsdeltagare.

När du kombinerar regler eller parametrar med AND måste alla potentiella målgruppsmedlemmar uppfylla *alla* definierade villkor som ska ingå som deltagare. Om du till exempel definierar en OS-regel OCH en webbläsarregel inkluderas endast besökare som använder både det definierade operativsystemet *och* den definierade webbläsaren i aktiviteten.

När du kombinerar regler eller parametrar med ELLER behöver en potentiell målgruppsmedlem bara uppfylla ett enda definierat villkor som ska ingå som deltagare. Om du till exempel definierar flera mobilregler som är kopplade till OR, inkluderas besökare som uppfyller *något* av de definierade villkoren i aktiviteten.

Du kan blanda båda booleska operatorer för att skapa komplexa regler; operatorer på samma regelnivå måste dock matcha. Användargränssnittet använder automatiskt rätt operator.

Följande regel riktar sig till exempel till besökare som använder antingen Chrome *eller* Firefox på en Windows-dator:

![Skapa målgrupper](assets/audience_create.png)

>[!NOTE]
>
>Undvik att skapa regler som utesluter alla potentiella målgruppsmedlemmar. Det är till exempel inte möjligt för någon att besöka en sida med Chrome *och* Firefox samtidigt.

## Skapa en ny målgrupp

1. Klicka **[!UICONTROL Audiences]** på den övre menyraden.

   ![](assets/audiences_list.png)

1. From the [!UICONTROL Audiences] list, click **[!UICONTROL + Create Audience]**.

   eller

   Om du vill kopiera en befintlig målgrupp håller du pekaren över den önskade målgruppen i [!UICONTROL Audiences] listan och klickar sedan på **[!UICONTROL Copy]** ikonen . Sedan kan ni redigera målgruppen för att skapa en liknande målgrupp.

1. Skriv ett unikt, beskrivande målgruppsnamn.
1. Klicka på **[!UICONTROL + Add Rule]**.

   Reglerna gör det möjligt att begränsa er målgrupp till en delmängd av era webbplatsbesökare.
1. Välj en regeltyp.

   Varje regeltyp har sina egna parametrar. Mer information om hur du konfigurerar varje typ av målgruppsregel finns i [Kategorier för målgrupper](../../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) .
1. Definiera regelparametrarna.
1. Klicka på **[!UICONTROL Save]**.

   Nyligen skapade målgrupper visas i listan efter några sekunder av bearbetningsfördröjningen. Om målgruppen inte visas omedelbart i listan kan du söka efter målgruppen eller uppdatera listan.

## Utbildningsvideo: Märket Skapa ![publiköversikt](/help/assets/overview.png)

Den här videon innehåller information om hur du skapar målgrupper.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)