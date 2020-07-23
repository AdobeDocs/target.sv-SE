---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.
title: Värdar
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 0%

---


# Värdar{#hosts}

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

Det främsta målet med värdhantering är att se till att inget inaktivt innehåll av misstag visas på webbplatser. Med värdhantering kan du också separera rapportdata efter [miljö](/help/administrating-target/environments.md).

En värd är en domän som en [!DNL Target] begäran görs från. På en webbplats är det vanligtvis egenskapen `location.hostname` för den URL som gör [!DNL Target] begäran.

Som standard begränsar inte [!DNL Target] en värd som kan göra [!DNL Target] förfrågningar och ta emot [!DNL Target] svar. När nya värdar gör förfrågningar fungerar de automatiskt. Det gör det också möjligt att testa på olika domäner som du inte vet eller inte kan förutse. Om du vill åsidosätta det här standardbeteendet kan du ställa in en tillåtelselista eller blockeringslista för att begränsa vilka värdar som ska fungera med [!DNL Target].

Om du vill hantera värdar klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Känna igen värdar {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Följande villkor måste vara uppfyllda för att en värd ska identifieras och läggas till i [!UICONTROL Hosts] listan:

* Minst en [!DNL Target] begäran måste finnas på värden
* En sida på värden måste ha följande:

   * En korrekt at.js- eller mbox.js-referens
   * En [!DNL Target] begäran eller en autogenererad global [!DNL Target] begäran

* Sidan med [!DNL Target] begäran måste visas i en webbläsare

När sidan har visats listas värden i [!UICONTROL Hosts] listan så att du kan hantera den i en miljö, samt förhandsgranska och starta aktiviteter och tester.

>[!NOTE]
>
>Detta inkluderar alla personliga utvecklingsservrar.

Kontrollera att värden känns igen när en värd har lagts till i [!UICONTROL Host] listan.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Uppdatera webbläsaren om värden inte visas.

   Som standard placeras en nyligen identifierad värd i [!UICONTROL Production] miljön. Det här är den säkraste miljön eftersom den inte tillåter att inaktiva aktiviteter kan ses från dessa värdar.

1. (Villkorligt) Klicka på **[!UICONTROL Move]** ikonen ( ![flyttningsikonen](/help/administrating-target/assets/icon-move.png) ) för att flytta värden till [!UICONTROL Development], [!UICONTROL Staging]eller annan miljö.

>[!NOTE]
>
>Det går inte att ta bort [!UICONTROL Production] miljön även om du byter namn på den. Det antas att det är här du kommer att utföra slutgiltiga, aktiva aktiviteter och tester. Standardmiljön tillåter inte att inaktiva kampanjer visas.

## Sortera eller söka i listan Värdar {#section_068B23C9D8224EB78BC3B7C8580251B0}

Om du vill sortera [!UICONTROL Hosts] listan klickar du på en kolumnrubrik ([!UICONTROL Name], [!UICONTROL Environment]eller [!UICONTROL Last Requested]) för att sortera listan i stigande eller fallande ordning.

Om du vill söka i [!UICONTROL Hosts] listan skriver du ett sökord i [!UICONTROL Search Hosts] rutan.

## Skapa tillåtelselista som anger värdar som har behörighet att skicka Target-begäranden till Target. {#allowlist}

Du kan skapa en tillåtelselista som anger värdar (domäner) som har behörighet att skicka [!DNL Target] begäranden till [!DNL Target]. Alla andra värdar som genererar begäranden får ett svar på ett kommenterat auktoriseringsfel. Som standard registreras alla värdar som innehåller en [!DNL Target] begäran [!DNL Target] i [!UICONTROL Production] miljön och har tillgång till alla aktiva och godkända aktiviteter. Om detta inte är den önskade metoden kan du använda tillåtelselista för att registrera specifika värdar som kan göra [!DNL Target] förfrågningar och ta emot [!DNL Target] innehåll. Alla värdar fortsätter att visas i [!UICONTROL Hosts] listan, och miljöer kan fortfarande användas för att gruppera dessa värdar och tilldela olika nivåer till varje, till exempel om värden kan se aktiva och/eller inaktiva aktiviteter.

Så här skapar du en tillåtelselista:

1. From the [!UICONTROL Hosts] list, click **[!UICONTROL Authorize Hosts]**.
1. Aktivera **[!UICONTROL Enable Authorized Hosts for content delivery]** växlingsknappen.
1. Lägg till önskade värdar i **[!UICONTROL Host contains]** rutan efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Lägg till önskade värdar i **[!UICONTROL Host does not contains]** rutan efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Klicka på **[!UICONTROL Save]**.

Om en [!DNL Target] begäran görs på en obehörig värd besvaras samtalet med `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Bästa praxis** för säkerhet: Om du använder funktionen ubox i [!DNL Target]bör du tänka på att den här tillåtelselista även styr listan över domäner som [omdirigeringarna](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) kan navigera till. Se till att du lägger till domäner som du vill omdirigera till när du använder ubox som en del av implementeringen. Om tillåtelselista lämnas ospecificerat kan [!DNL Adobe] inte verifiera omdirigerings-URL:er och skydda mot potentiella skadliga omdirigeringar.
>
>tillåtelselista har företräde framför miljöer. Du bör rensa bort alla värdar innan du använder funktionen tillåtelselista, så visas bara de värdar som tillåts av tillåtelselista i din värdlista. Du kan sedan flytta värdarna till den önskade miljön.

Ibland visas domäner från andra platser i dina miljöer. En domän visas i listan om domänen gör ett anrop till at.js eller mbox.js. Om någon t.ex. kopierar en av dina webbsidor till sin server, visas den domänen i din miljö. Du kan också se domäner från spindelmotorer, översättarplatser eller lokala diskenheter.

I de fall där `mboxHost` skickas i ett API-anrop registreras konverteringen för den miljö som skickas. Om ingen miljö skickas blir värddatorn i anropet som standard [!UICONTROL Production].

Du kan också skapa ett blockeringslista som anger värdar (domäner) än vad som inte kan skicka [!DNL Target] begäranden till [!DNL Target] genom att lägga till önskade värdar i [!UICONTROL Host Does Not Contain] rutan.

>[!NOTE]
>
>Eftersom listan Godkända värdar används för både [!DNL Target] värdar och standardomdirigeringsvärdar måste du lägga till alla befintliga domäner som är godkända för att använda [!DNL Adobe Target] Javascript SDK (at.js) *OCH* alla domäner som används i Ubox-standardomdirigerings-URL:er. Du måste även lägga till nya liknande domäner till tillåtelselista i framtiden.

## Ta bort en värd {#section_F56355BA4BC54B078A1A8179BC954632}

Du kan ta bort en värd när den inte längre behövs.

1. Klicka på [!UICONTROL Hosts] ikonen i **[!UICONTROL Delete]** listan.
1. Klicka **[!UICONTROL Delete]** för att bekräfta borttagningen.

>[!NOTE]
>
>Värden listas igen om någon bläddrar till en sida som innehåller en [!DNL Target] begäran på värden.

## Felsökning av värdar {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Prova följande felsökningstips om du får problem med värdarna:

**Värden visas inte i listan för ditt konto.**

* Uppdatera [!UICONTROL Hosts] sidan i webbläsaren.
* Bekräfta att begäran är korrekt, inklusive referensen at.js eller mbox.js. [!DNL Target]
* Försök att bläddra till en av [!DNL Target] förfrågningarna på värden. Det är möjligt att ingen [!DNL Target] begäran på värden någonsin har återgetts i en webbläsare.

**Slumpmässiga eller okända domäner visas i[!UICONTROL Host]listan.**

En domän visas i den här listan om en begäran [!DNL Target] görs från domänen. Ofta kan du se domäner från spindelmotorer, översättarplatser eller lokala diskenheter. Om den listade domänen inte är en som ditt team använder kan du klicka för [!UICONTROL Delete] att ta bort den.

**Min[!DNL Target]begäran returnerar /* ingen skärm - oauktoriserad mbox-värd */.**

Om en [!DNL Target] begäran görs på en obehörig värd, svarar begäran med /* no display - unauthorized mbox host */.
