---
keywords: webbläsaralternativ;typ;webbläsartyp;webbläsarspråk;språk;version;webbläsarversion
description: Lär dig skapa målgrupper i [!DNL Adobe Target] för användare som använder en viss webbläsare eller särskilda webbläsaralternativ när de besöker sidan.
title: Kan jag rikta in besökarna baserat på webbläsartyp?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 0%

---

# [!UICONTROL Browser]

Du kan rikta in dig på användare som använder en viss webbläsare eller särskilda webbläsaralternativ när de besöker sidan.

Följande webbläsare kan ha följande mål:

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>Börja med [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024), inbyggda målgrupper som skapats med målgränssnittet, som `Browser:iPad` och `Browser:iPhone` har uppdaterats för att kunna utföra korrekt målinriktning för [!DNL iPad] och [!DNL iPhone] använda `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone`och `profile.mobile.isTablet`.
>
>Uppdateringen kräver inga åtgärder från kundens sida. Etiketterna i [!DNL Target] Gränssnittet kommer att ändras i framtiden och kommer att tillkännages i [[!DNL Target] versionsinformation (aktuell)](/help/main/r-release-notes/release-notes.md) när dessa ändringar görs.
>
>Information om inställningar för tillfällig lösning finns i [Uppdateringar för [!DNL iPad] och [!DNL iPhone] in [!UICONTROL Browser] publikattribut (30 april 2024)](#updates) nedan.

Det finns två sätt att rikta in sig på webbläsare:

* **Fördefinierad målgrupp:** Använd den fördefinierade målgruppen om du bara vill rikta dig till besökare som använder en viss webbläsare för att besöka webbplatsen. Om du till exempel erbjuder en [!DNL Chrome] tillägg, du bara aktiverar [!DNL Chrome] -användare.

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

  I följande exempel visas en publik som innehåller [!DNL Microsoft Edge] användare i version 91 eller 92:

  ![Målkant 91 eller 92](assets/target_edge.png)

## Webbläsaralternativ {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Rikta in eller exkludera aktivitetsdeltagare baserat på webbläsartyp, språk eller version.

### Typ {#section_6ADC758F23F145B3A310151546D83D56}

Ange eller exkludera en viss webbläsare.

Välj **[!UICONTROL Type]** väljer du antingen lika med eller inte lika med.

* [!UICONTROL Equals]: Ange de valda webbläsarna som mål.
* [!UICONTROL Does not equal]: Uteslut de valda webbläsarna.

Välj en eller flera webbläsare. Flera alternativ är kopplade till en OR.

### Språk {#section_7520D1AA464A45A6843EABE2D2B431A1}

Använd eller exkludera vissa webbläsare som är inställda på specifika språk.

Om ett erbjudande t.ex. bara finns på engelska kan du rikta dig till webbläsare där språket är engelska. Om sidan inte är aktiverad med dubbla byte kan du utesluta webbläsare som är inställda på östasiatiska språk.

Att inkludera eller exkludera webbläsarspråk kan ge en mer exakt besökaranpassning än att rikta in er baserat på geografisk orientering i fall där språket är viktigare än platsen. Om du t.ex. erbjuder en artikel skriven på engelska kan du antingen rikta dig till engelskspråkiga länder eller till webbläsare som är inställda på engelska. Artikeln är avsedd för webbläsare och är tillgänglig för engelska talare i länder där engelska inte är det primära språket.

Välj **[!UICONTROL Language]** väljer du antingen lika med eller inte lika med.

* [!UICONTROL Equals]: Ange de valda webbläsarspråken som mål.
* [!UICONTROL Does not equal]: Uteslut de valda webbläsarspråken.

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

Om sidan inte visas korrekt i [!DNL Internet Explorer] version 11 eller tidigare kan du skapa en målgrupp som utesluter dessa versioner. I så fall skapar du en regel där webbläsartypen är lika med [!DNL Internet Explorer] och lägger till en andra regel där versionen är mindre än eller lika med 11.

Välj **[!UICONTROL Version]** väljer du sedan en operator:

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* Är större än eller lika med
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

Skriv versionsnumret. Endast större versioner kan anges i textfältet. Den angivna versionen innehåller en delversion av den versionen. Om du till exempel anger version 10 inkluderas även besökare i version 10.1.

Flera alternativ är kopplade till en OR.

## Utbildningsvideo: Skapa publiker ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Uppdateringar för [!DNL iPad] och [!DNL iPhone] in [!UICONTROL Browser] publikattribut (30 april 2024) {#updates}

[!DNL Adobe Target] låter dig [mål för någon av flera kategoriattribut](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), inklusive användare som använder en viss webbläsare eller webbläsaralternativ när de besöker din sida.

Börja med [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024), inbyggda målgrupper som skapats med målgränssnittet, som `Browser:iPad` och `Browser:iPhone` har uppdaterats för att kunna utföra korrekt målinriktning för [!DNL iPad] och [!DNL iPhone] använda `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` och `profile.mobile.isTablet`.

Inbyggda målgrupper skapade med [!DNL Target] användargränssnitt, som `Browser:iPad` och `Browser:iPhone`, flyttas automatiskt över till den nya målgruppsdefinitionen och kräver inga åtgärder från kundens sida. Om du fortsätter bör du dock använda inställningarna [beskrivs nedan](#ui).

Om du `user.browserType` i alla profilskript för att kontrollera om det är ett [!DNL iPhone] eller [!DNL iPad] (till exempel `user.browserType == 'iphone'` eller `user.browserType != 'ipad'`) ska dessa profilskript ändras som [instrueras nedan](#profile-scripts) före 30 april 2024 för att säkerställa att dessa målgrupper fortsätter att fungera som förväntat.

JavaScript-målgrupper är äldre målgrupper som använder [!DNL Target] uttryck som har tagits bort med [!DNL Target Classic] Gränssnitt. Dessa målgrupper kan endast ändras via API. Kunderna måste uppdatera dessa målgrupper endast om de fortsätter att använda äldre målgrupper i aktiviteter.

### Målgrupper skapade med [!DNL Target] UI {#ui}

Följande inställningar kan användas framåt:

* **För webbläsarmatchningar[!DNL Apple]**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **För webbläsare matchar surfplattan**: [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![mobil är surfplatta](/help/main/r-release-notes/assets/is-tablet.png)

* **För webbläsare som matchar iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] med en And-behållare med [!UICONTROL Mobile] > [!UICONTROL Is Tablet] är [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **För webbläsare som matchar iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] med en And-behållare med [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] är [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Det finns många andra inställningar som kan användas, till exempel när villkoren negeras. Exempel på negerade förhållanden kan se ut så här:

* **Webbläsaren matchar inte iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] med en Eller-behållare med [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] är [!UICONTROL false]

  ![Inte mobiltelefon](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Webbläsaren matchar inte iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] med en Eller-behållare med [!UICONTROL Mobile] > [!UICONTROL Is Tablet] är [!UICONTROL false].

  ![Inte surfplatta](/help/main/r-release-notes/assets/tablet-false.png)

### Målgrupper skapade med profilskript {#profile-scripts}

Om du `user.browserType` i äldre [!DNL Target Classic] målgrupper eller i profilskript bör ändringarna omfatta följande:

* **BrowserType är iPhone**:

  Ersätt:

  `user.browserType=="iphone"`

  Med:

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType är inte iPhone**:

  Ersätt:

  `user.browserType!="iphone"`

  Med:

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType är iPad**:

  Ersätt:

  `user.browserType=="ipad"`

  Med:

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType är inte iPad**:

  Ersätt:

  `user.browserType!="ipad"`

  Med:

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`