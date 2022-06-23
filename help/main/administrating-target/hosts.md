---
keywords: värd;värdar;värdgrupp;felsökning;bästa praxis;ubox;omdirigera;omdirigera;vitlista;tillåtelselista;svartlista;blockeringslista
description: Lär dig hur du organiserar dina webbplatser och förproduktionsmiljöer för enkel hantering och separat rapportering i Adobe Target.
title: Vad är värdar och hur använder jag dem?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 0%

---

# Värdar

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering i [!DNL Adobe Target].

Det främsta målet med värdhantering är att se till att inget inaktivt innehåll av misstag visas på webbplatser. Med värdhantering kan du också separera rapportdata med [miljö](/help/main/administrating-target/environments.md).

En värd är en domän från vilken en [!DNL Target] begäran görs. På en webbplats är det vanligtvis `location.hostname` egenskapen för den URL som skapar [!DNL Target] begäran.

Som standard [!DNL Target] begränsar inte en värd som kan [!DNL Target] förfrågningar och ta emot [!DNL Target] svar. När nya värdar gör förfrågningar fungerar de automatiskt. Den här processen gör det även möjligt att testa på olika domäner som du inte vet eller inte kan förutse. Om du vill åsidosätta det här standardbeteendet kan du ställa in en tillåtelselista eller blockeringslista för att begränsa vilka värdar som ska arbeta med [!DNL Target].

Om du vill hantera värdar klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Känna igen värdar {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Så här känner du igen en värd och lägger till den i [!UICONTROL Hosts] skall följande villkor vara uppfyllda:

* Minst en [!DNL Target] begäran måste finnas på värden
* En sida på värden måste ha följande:

   * En korrekt at.js-referens
   * A [!DNL Target] begäran eller en autogenererad global [!DNL Target] förfrågan

* Sidan med [!DNL Target] begäran måste visas i en webbläsare

När sidan har visats visas värden på [!UICONTROL Hosts] som gör att du kan hantera den i en miljö och förhandsgranska och starta aktiviteter och tester.

>[!NOTE]
>
>Detta inkluderar alla personliga utvecklingsservrar.

När en värd har lagts till i [!UICONTROL Host] se till att värden känns igen.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Uppdatera webbläsaren om värden inte visas.

   Som standard placeras en nyligen identifierad värd i [!UICONTROL Production] miljö. The [!UICONTROL Production] miljö är den säkraste miljön eftersom den inte tillåter att inaktiva aktiviteter kan ses från dessa värdar.

1. (Villkorligt) Klicka på **[!UICONTROL Move]** ikon ( ![flytta ikon](/help/main/administrating-target/assets/icon-move.png) ) för att flytta värden till [!UICONTROL Development], [!UICONTROL Staging]eller annan miljö.

>[!NOTE]
>
>The [!UICONTROL Production] -miljön kan inte tas bort, även om du byter namn på den. Det antas att det är i den här miljön som du utför slutgiltiga, aktiva aktiviteter och tester. Standardmiljön tillåter inte att inaktiva kampanjer visas.

## Sortera eller söka i listan Värdar {#section_068B23C9D8224EB78BC3B7C8580251B0}

Sortera [!UICONTROL Hosts] klicka på valfri kolumnrubrik ([!UICONTROL Name], [!UICONTROL Environment], eller [!UICONTROL Last Requested]) för att sortera listan i stigande eller fallande ordning.

Om du vill söka i [!UICONTROL Hosts] anger du ett sökord i listan [!UICONTROL Search Hosts] box.

## Skapa tillåtelselista som anger värdar som har behörighet att skicka [!DNL Target] förfrågningar till [!DNL Target]. {#allowlist}

Du kan skapa ett tillåtelselista som anger värdar (domäner) som har behörighet att skicka [!DNL Target] förfrågningar till [!DNL Target]. Alla andra värdar som genererar begäranden får ett svar på ett kommenterat auktoriseringsfel. Som standard alla värdar som innehåller en [!DNL Target] begäranregister med [!DNL Target] i [!UICONTROL Production] miljö och har tillgång till alla aktiva och godkända aktiviteter. Om du inte vill använda den här metoden kan du använda tillåtelselista för att registrera specifika värdar som är berättigade att göra [!DNL Target] förfrågningar och ta emot [!DNL Target] innehåll. Alla värdar fortsätter att visas i [!UICONTROL Hosts] lista och miljöer kan fortfarande användas för att gruppera dessa värdar och tilldela olika nivåer till varje, till exempel om värden kan se aktiva och/eller inaktiva aktiviteter.

Så här skapar du en tillåtelselista:

1. Från [!UICONTROL Hosts] lista, klicka på **[!UICONTROL Authorize Hosts]**.
1. Aktivera **[!UICONTROL Enable Authorized Hosts for content delivery]** växla.
1. Lägg till önskade värdar i **[!UICONTROL Host contains]** efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Lägg till önskade värdar i **[!UICONTROL Host does not contains]** efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Klicka på **[!UICONTROL Save]**.

Om en [!DNL Target] begäran görs på en obehörig värd, samtalet besvaras med `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Bästa praxis för säkerhet**: Om du använder ubox-funktionen i [!DNL Target]styr den här tillåtelselista även listan över domäner som [redirectors](https://developer.adobe.com/target/implement/email/working-with-redirectors/) kan navigera. Se till att du lägger till domäner som du vill omdirigera till när du använder ubox som en del av implementeringen. Om tillåtelselista lämnas ospecificerat [!DNL Adobe] kan inte verifiera omdirigerings-URL:er och skydda mot potentiella skadliga omdirigeringar.
>
>Tillåtelselista har företräde framför miljöer. Ta bort alla värdar innan du använder funktionen tillåtelselista, så visas bara de värdar som tillåts av tillåtelselista i din värdlista. Du kan sedan flytta värdarna till den önskade miljön.

Ibland visas domäner från andra platser i dina miljöer. En domän visas i listan om domänen anropar at.js. Om någon t.ex. kopierar en av dina webbsidor till sin server, visas den domänen i din miljö. Du kan också se domäner från spindelmotorer, översättarplatser eller lokala diskenheter.

I de fall där `mboxHost` skickas i ett API-anrop, konverteringen registreras för miljön som skickas. Om ingen miljö skickas blir värddatorn i anropet som standard [!UICONTROL Production].

Du kan också skapa ett blockeringslista som anger värdar (domäner) som inte kan skicka [!DNL Target] förfrågningar till [!DNL Target] genom att lägga till önskade värdar i [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>The [!UICONTROL Authorized Hosts] list används för båda [!DNL Target] värdar och standardomdirigeringsvärdar. Lägg till alla befintliga domäner som är godkända för att använda [!DNL Adobe Target] JavaScript SDK (at.js) *OCH* alla domäner som används i Ubox-standardomdirigerings-URL:er. Lägg till liknande domäner i tillåtelselista i framtiden.

## Ta bort en värd {#section_F56355BA4BC54B078A1A8179BC954632}

Du kan ta bort en värd när den inte längre behövs.

1. Från [!UICONTROL Hosts] klickar du på **[!UICONTROL Delete]** ikon.
1. Klicka **[!UICONTROL Delete]** för att bekräfta borttagningen.

>[!NOTE]
>
>Värden visas igen om någon bläddrar till en sida som innehåller en [!DNL Target] begäran på värden.

## Felsökning av värdar {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Prova följande felsökningstips om du får problem med värdarna:

**Värden visas inte i listan för ditt konto.**

* Uppdatera [!UICONTROL Hosts] i webbläsaren.
* Bekräfta att [!DNL Target] begäran är korrekt, inklusive referensen at.js.
* Bläddra till en av [!DNL Target] begäranden på värden. Det är möjligt att ingen [!DNL Target] begäran på värden renderades någonsin i en webbläsare.

**Slumpmässiga eller okända domäner visas i [!UICONTROL Host] lista.**

En domän visas i listan om en begäran till [!DNL Target] görs från domänen. Ofta kan du se domäner från spindelmotorer, översättarplatser eller lokala diskenheter. Om den listade domänen inte är en som teamet använder kan du klicka på [!UICONTROL Delete] för att ta bort den.

**Min [!DNL Target] returer av begäranden /&#42; ingen skärm - obehörig mbox-värd &#42;/.**

Om en [!DNL Target] begäran görs på en obehörig värd, begäran besvaras med /&#42; ingen skärm - obehörig mbox-värd &#42;/.
