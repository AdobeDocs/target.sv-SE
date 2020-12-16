---
keywords: browser options;type;browser type;browser language;language;version;browser version
description: Du kan skapa målgrupper i Adobe Target för målanvändare som använder en viss webbläsare eller särskilda webbläsaralternativ när de besöker din sida.
title: Webbläsaralternativ i Adobe Target
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---


# Webbläsare{#browser}

Du kan rikta in dig på användare som använder en viss webbläsare eller särskilda webbläsaralternativ när de besöker sidan.

Följande webbläsare kan ha följande mål:

* Krom
* Microsoft Edge
* Firefox
* Opera
* Safari
* iPad
* Internet Explorer
* iPhone|

Det finns två sätt att rikta in sig på webbläsare:

**Fördefinierad målgrupp:** Använd den fördefinierade målgruppen om du bara vill rikta dig till besökare som använder en viss webbläsare för att besöka webbplatsen. Om du till exempel erbjuder ett Chrome-tillägg bör du bara rikta dig till Chrome-användare.

1. När du konfigurerar aktiviteten väljer du webbläsaren i listrutan för målgrupper.

   Det här alternativet riktar endast in aktiviteten på besökare som använder den angivna webbläsaren.

**Anpassad målgruppsregel för webbläsare:** En anpassad målgrupp gör att du kan rikta dig till flera webbläsare eller skapa regler eller undantag för specifika webbläsare, webbläsarversioner eller webbläsarspråk. Detta ger stor flexibilitet när det gäller att rikta kampanjer baserat på webbläsarattribut.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Browser]**.

   ![Regler > Bläddra](assets/target_browser.png)

1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

   * **Typ:** Använd eller exkludera en viss webbläsare. Se [Typ](/help/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
   * **Språk:** Använd eller exkludera vissa webbläsare som är inställda på vissa språk. Se [Språk](/help/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
   * **Version:** Aktivera eller inaktivera vissa webbläsarversioner. Se [Version](/help/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** och ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Save]**.

I följande exempel visas en publik som inkluderar Internet Explorer-användare i version 10 eller 11:

![Mål IE 10 och 11](/help/c-target/c-audiences/c-target-rules/assets/target_ie-10-11.png)

## Webbläsaralternativ {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Rikta in eller exkludera aktivitetsdeltagare baserat på webbläsartyp, språk eller version.

### Typ {#section_6ADC758F23F145B3A310151546D83D56}

Ange eller exkludera en viss webbläsare.

Välj **[!UICONTROL Type]** och välj sedan antingen lika med eller inte lika med.

* Lika med: Välj de valda webbläsarna.
* Är inte lika med: Uteslut de valda webbläsarna.

Välj en eller flera webbläsare. Flera alternativ är kopplade till en OR.

### Språk {#section_7520D1AA464A45A6843EABE2D2B431A1}

Använd eller exkludera vissa webbläsare som är inställda på specifika språk.

Om ett erbjudande t.ex. bara finns på engelska kan du rikta dig till webbläsare där språket är engelska. Om sidan inte är aktiverad med dubbla byte kan du utesluta webbläsare som är inställda på östasiatiska språk.

Att inkludera eller exkludera webbläsarspråk kan ge en mer exakt besökaranpassning än att rikta in er baserat på geografisk orientering i fall där språket är viktigare än platsen. Om du t.ex. erbjuder en artikel skriven på engelska kan du antingen rikta dig till engelskspråkiga länder eller till webbläsare som är inställda på engelska. Artikeln blir tillgänglig för engelska talare i länder där engelska inte är det primära språket.

Välj **[!UICONTROL Language]** och välj sedan antingen lika med eller inte lika med.

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

Välj **[!UICONTROL Version]** och välj sedan en operator:

* Lika med
* Är inte lika med
* Är större än
* Är större än eller lika med
* Är mindre än
* Är mindre än eller lika med

Skriv versionsnumret.

Endast större versioner kan anges i textfältet. Den angivna versionen innehåller en delversion av den versionen. Om du till exempel anger version 10 inkluderas besökare i version 10.1.

Flera alternativ är kopplade till en OR.

## Utbildningsvideo: Skapar publik ![Självstudiekursikon](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)