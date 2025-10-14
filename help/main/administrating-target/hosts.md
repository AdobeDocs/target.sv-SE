---
keywords: värd;värdar;värdgrupp;felsökning;bästa praxis;ubox;omdirigera;omdirigera;vitlista;tillåtelselista;svartlista;blockeringslista
description: Lär dig hur du organiserar dina webbplatser och förproduktionsmiljöer för enkel hantering och separat rapportering i Adobe Target.
title: Vad är värdar och hur använder jag dem?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 0ab5b7d7cbfaef86b9a045883f597900dba72416
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 0%

---

# Värdar

Organisera dina webbplatser och förproduktionsmiljöer för enkel hantering och separat rapportering i [!DNL Adobe Target].

Det främsta målet med värdhantering är att se till att inget inaktivt innehåll av misstag visas på webbplatser. Med värdhantering kan du också separera rapportdata efter [miljö](/help/main/administrating-target/environments.md).

En värd är en domän från vilken en [!DNL Target]-begäran görs. På en webbplats är det vanligtvis egenskapen `location.hostname` för den URL som gör [!DNL Target]-begäran.

Som standard begränsar inte [!DNL Target] en värd som kan göra [!DNL Target] förfrågningar och ta emot [!DNL Target] svar. När nya värdar gör förfrågningar fungerar de automatiskt. Den här processen gör det även möjligt att testa på olika domäner som du inte vet eller inte kan förutse. Om du vill åsidosätta det här standardbeteendet kan du konfigurera en tillåtelselista eller blockeringslista för att begränsa vilka värdar som ska arbeta med [!DNL Target].

{{permissions-update}}

Om du vill hantera värdar klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

## Känna igen värdar {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Om du vill identifiera en värd och lägga till den i listan [!UICONTROL Hosts] måste följande villkor vara uppfyllda:

* Minst en [!DNL Target]-begäran måste finnas på värden
* En sida på värden måste ha följande:

   * En korrekt at.js-referens
   * En [!DNL Target]-begäran eller en autogenererad global [!DNL Target]-begäran

* Sidan med [!DNL Target]-begäran måste visas i en webbläsare

När sidan har visats visas värden i listan [!UICONTROL Hosts], vilket gör att du kan hantera den i en miljö och förhandsgranska och starta aktiviteter och tester.

>[!NOTE]
>
>Detta inkluderar alla personliga utvecklingsservrar.

Kontrollera att värden känns igen när en värd har lagts till i listan [!UICONTROL Host].

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Uppdatera webbläsaren om värden inte visas.

   Som standard placeras en nyligen identifierad värd i miljön [!UICONTROL Production]. Miljön [!UICONTROL Production] är den säkraste miljön eftersom den inte tillåter att inaktiva aktiviteter visas från dessa värdar.

1. (Villkorligt) Klicka på ikonen **[!UICONTROL Move]** ( ![&#x200B; flytta ikon &#x200B;](/help/main/assets/icons/MoveTo.svg) ) för att flytta värden till [!UICONTROL Development], [!UICONTROL Staging] eller någon annan miljö.

>[!NOTE]
>
>Det går inte att ta bort miljön [!UICONTROL Production], även om du byter namn på den. Det antas att det är i den här miljön som du utför slutgiltiga, aktiva aktiviteter och tester. Standardmiljön tillåter inte att inaktiva kampanjer visas.

## Sortera eller söka i listan Värdar {#section_068B23C9D8224EB78BC3B7C8580251B0}

Om du vill sortera listan [!UICONTROL Hosts] klickar du på en kolumnrubrik ([!UICONTROL Name], [!UICONTROL Environment] eller [!UICONTROL Last Requested]) för att sortera listan i stigande eller fallande ordning.

Om du vill söka i listan [!UICONTROL Hosts] skriver du ett sökord i rutan [!UICONTROL Search Hosts].

## Skapa tillåtelselista som anger värdar som har behörighet att skicka [!DNL Target] begäranden till [!DNL Target]. {#allowlist}

Du kan skapa en tillåtelselista som anger värdar (domäner) som har behörighet att skicka [!DNL Target] begäranden till [!DNL Target]. Alla andra värdar som genererar begäranden får ett svar på ett kommenterat auktoriseringsfel. Som standard registreras alla värdar som innehåller en [!DNL Target]-begäran med [!DNL Target] i [!UICONTROL Production]-miljön och har tillgång till alla aktiva och godkända aktiviteter. Om du inte vill använda den här metoden kan du använda tillåtelselista för att registrera specifika värdar som är berättigade att göra [!DNL Target]-förfrågningar och ta emot [!DNL Target]-innehåll. Alla värdar fortsätter att visas i listan [!UICONTROL Hosts], och miljöer kan fortfarande användas för att gruppera dessa värdar och tilldela olika nivåer till varje, till exempel om värden kan se aktiva och/eller inaktiva aktiviteter.

Så här skapar du en tillåtelselista:

1. Klicka på [!UICONTROL Hosts] i listan **[!UICONTROL Authorize Hosts]**.
1. Aktivera växlingsknappen **[!UICONTROL Enable Authorized Hosts for content delivery]**.
1. Lägg till önskade värdar i rutan **[!UICONTROL Host contains]** efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Lägg till önskade värdar i rutan **[!UICONTROL Host does not contains]** efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Klicka på **[!UICONTROL Save]**.

Om en [!DNL Target]-begäran görs på en obehörig värd, svarar samtalet med `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Bästa säkerhetsrutiner**: Om du använder funktionen för lådor i [!DNL Target] styr det här tillåtelselista även listan över domäner som [redirectors](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html?lang=sv-SE){target=_blank} kan navigera till. Se till att du lägger till domäner som du vill omdirigera till när du använder ubox som en del av implementeringen. Om tillåtelselista inte anges kan [!DNL Adobe] inte verifiera omdirigerings-URL:erna och skydda mot potentiella skadliga omdirigeringar.
>
>Tillåtelselista har företräde framför miljöer. Ta bort alla värdar innan du använder funktionen tillåtelselista, så visas bara de värdar som tillåts av tillåtelselista i din värdlista. Du kan sedan flytta värdarna till den önskade miljön.

Ibland visas domäner från andra platser i dina miljöer. En domän visas i listan om domänen anropar at.js. Om någon t.ex. kopierar en av dina webbsidor till sin server, visas den domänen i din miljö. Du kan också se domäner från spindelmotorer, översättarplatser eller lokala diskenheter.

Om `mboxHost` skickas i ett API-anrop registreras konverteringen för den miljö som skickas. Om ingen miljö skickas blir värddatorn i anropet som standard [!UICONTROL Production].

Du kan också skapa ett blockeringslista som anger värdar (domäner) som inte kan skicka [!DNL Target] begäranden till [!DNL Target] genom att lägga till önskade värdar i rutan [!UICONTROL Host Does Not Contain].

>[!NOTE]
>
>Listan [!UICONTROL Authorized Hosts] används för både [!DNL Target]-värdar och standardomdirigeringsvärdar. Lägg till alla befintliga domäner som är godkända för att använda JavaScript SDK [!DNL Adobe Target] (at.js) *AND* för alla domäner som används i Ubox-standardomdirigerings-URL:er. Lägg till liknande domäner i tillåtelselista i framtiden.

## Ta bort en värd {#section_F56355BA4BC54B078A1A8179BC954632}

Du kan ta bort en värd när den inte längre behövs.

1. Klicka på ikonen [!UICONTROL Hosts] ( **[!UICONTROL Delete]** Ta bort ikon![&#x200B; ) i listan &#x200B;](/help/main/assets/icons/DeleteOutline.svg).
1. Klicka på **[!UICONTROL Delete]** för att bekräfta borttagningen.

>[!NOTE]
>
>Värden visas igen om någon bläddrar till en sida som innehåller en [!DNL Target]-begäran på värden.

## Felsökning av värdar {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Prova följande felsökningstips om du får problem med värdarna:

**Värden visas inte i listan för ditt konto.**

* Uppdatera sidan [!UICONTROL Hosts] i webbläsaren.
* Bekräfta att [!DNL Target]-begäran är korrekt, inklusive referensen at.js.
* Försök att bläddra till någon av [!DNL Target]-förfrågningarna på värden. Det är möjligt att ingen [!DNL Target]-begäran på värden någonsin har renderats i en webbläsare.

**Slumpmässiga eller okända domäner visas i listan [!UICONTROL Host].**

En domän visas i listan om en begäran till [!DNL Target] görs från domänen. Ofta kan du se domäner från spindelmotorer, översättarplatser eller lokala diskenheter. Om den listade domänen inte är en som ditt team använder kan du klicka på [!UICONTROL Delete] för att ta bort den.

**Min [!DNL Target]-begäran returnerar /&#42; ingen skärm - oauktoriserad mbox-värd &#42;/.**

Om en [!DNL Target]-begäran görs på en obehörig värd, svarar begäran med /&#42; no display - unauthorized mbox host &#42;/.
