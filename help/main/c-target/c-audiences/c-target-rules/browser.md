---
keywords: webbläsaralternativ;typ;webbläsartyp;webbläsarspråk;språk;version;webbläsarversion
description: Lär dig skapa målgrupper i [!DNL Adobe Target] för användare som använder en viss webbläsare eller särskilda webbläsaralternativ när de besöker sidan.
title: Kan jag rikta in besökarna baserat på webbläsartyp?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Webbläsare

Du kan rikta in dig på användare som använder en viss webbläsare eller särskilda webbläsaralternativ när de besöker sidan.

Följande webbläsare kan ha följande mål:

* Krom
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad
* iPhone|

Det finns två sätt att rikta in sig på webbläsare:

* **Fördefinierad målgrupp:** Använd den fördefinierade målgruppen om du bara vill rikta dig till besökare som använder en viss webbläsare för att besöka webbplatsen. Om du till exempel erbjuder ett Chrome-tillägg bör du bara rikta dig till Chrome-användare.

   1. När du konfigurerar aktiviteten väljer du webbläsaren i listrutan.

      Det här alternativet riktar endast in aktiviteten på besökare som använder den angivna webbläsaren.

      ![Användare av målfärg](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Anpassad målgruppsregel för webbläsare:** Med en anpassad målgrupp kan ni inrikta er på flera olika webbläsare eller skapa regler eller undantag för specifika webbläsare, webbläsarversioner eller webbläsarspråk. Den här funktionen ger stor flexibilitet när det gäller att rikta in en aktivitet baserat på webbläsarattribut.

   1. I [!DNL Target] gränssnitt, klicka **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
   1. Namnge målgruppen och lägg till en valfri beskrivning.
   1. Dra och släpp **[!UICONTROL Browser]** i Audience Builder.

      ![Regler > Webbläsare](assets/target_browser.png)

   1. Klicka **[!UICONTROL Select]** väljer du sedan något av följande alternativ:

      * **Typ:** Ange eller exkludera en viss webbläsare. Se [Typ](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Språk:** Använd eller exkludera vissa webbläsare som är inställda på specifika språk. Se [Språk](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Version:** Ange eller exkludera vissa webbläsarversioner. Se [Version](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).
   1. (Valfritt) Ange ytterligare regler för målgruppen.
   1. Klicka på **[!UICONTROL Done]**.

   I följande exempel visas en publik som inkluderar Microsoft Edge-användare i version 91 eller 92:

   ![Målkant 91 eller 92](assets/target_edge.png)

## Webbläsaralternativ {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Rikta in eller exkludera aktivitetsdeltagare baserat på webbläsartyp, språk eller version.

### Typ {#section_6ADC758F23F145B3A310151546D83D56}

Ange eller exkludera en viss webbläsare.

Välj **[!UICONTROL Type]** väljer du antingen lika med eller inte lika med.

* Lika med: Välj de valda webbläsarna.
* Är inte lika med: Uteslut de valda webbläsarna.

Välj en eller flera webbläsare. Flera alternativ är kopplade till en OR.

### Språk {#section_7520D1AA464A45A6843EABE2D2B431A1}

Använd eller exkludera vissa webbläsare som är inställda på specifika språk.

Om ett erbjudande t.ex. bara finns på engelska kan du rikta dig till webbläsare där språket är engelska. Om sidan inte är aktiverad med dubbla byte kan du utesluta webbläsare som är inställda på östasiatiska språk.

Att inkludera eller exkludera webbläsarspråk kan ge en mer exakt besökaranpassning än att rikta in er baserat på geografisk orientering i fall där språket är viktigare än platsen. Om du t.ex. erbjuder en artikel skriven på engelska kan du antingen rikta dig till engelskspråkiga länder eller till webbläsare som är inställda på engelska. Artikeln blir tillgänglig för engelska talare i länder där engelska inte är det primära språket.

Välj **[!UICONTROL Language]** väljer du antingen lika med eller inte lika med.

* Lika med: Ange de valda webbläsarspråken.
* Är inte lika med: Uteslut de valda webbläsarspråken.

Markera ett eller flera språk. Flera alternativ är kopplade till en OR.

Följande webbläsarspråk kan anges som mål eller utelämnas:

* Engelska
* Franska
* Tyska
* Japanska
* Koreanska
* Portugisiska
* Ryska
* Spanska
* Traditionell kinesiska

### Version {#section_37CC8CE45DA04E8682AE6388321BA6EF}

Ange eller exkludera vissa webbläsarversioner.

Om sidan inte visas som den ska i Internet Explorer version 11 eller tidigare kan du skapa en publik som inte innehåller dessa versioner. I så fall skapar du en regel där webbläsartypen är lika med Internet Explorer och lägger till en andra regel där versionen är mindre än eller lika med 11.

Välj **[!UICONTROL Version]** väljer du sedan en operator:

* Lika med
* Är inte lika med
* Är större än
* Är större än eller lika med
* Är mindre än
* Är mindre än eller lika med

Skriv versionsnumret. Endast större versioner kan anges i textfältet. Den angivna versionen innehåller en delversion av den versionen. Om du till exempel anger version 10 inkluderas även besökare i version 10.1.

Flera alternativ är kopplade till en OR.

## Utbildningsvideo: Skapa målgrupper ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
