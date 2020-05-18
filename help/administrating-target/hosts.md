---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist
description: Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.
title: Värdar
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 0%

---


# Värdar{#hosts}

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

Det främsta målet med värdhantering är att se till att inget inaktivt innehåll av misstag visas på webbplatser. Med värdhantering kan du också separera rapportdata efter [miljö](/help/administrating-target/environments.md).

En värd är en webbserver (eller webbdomän) varifrån du underhåller innehåll under någon del av projektet. Alla värdar som betjänar en mbox känns igen.

Värdar paketeras i miljöer för enkel hantering. Du kan till exempel ha dussintals värdar grupperade i två eller tre miljöer. De förinställda miljöerna omfattar [!UICONTROL Production], [!UICONTROL Staging]och [!UICONTROL Development]. Du kan lägga till nya miljöer och byta namn på dina miljöer om du vill.

En miljö, standardmiljön, är förnamngiven [!UICONTROL Production]. Den här standardmiljön kan inte tas bort, även om du byter namn på den. [!DNL Target] förutsätter att det är här du kommer att utföra slutgiltiga, godkända aktiviteter och tester.

När en mbox-begäran tas emot från nya webbplatser eller domäner visas alltid dessa nya domäner i [!UICONTROL Production] miljön. Miljöns inställningar kan inte ändras, så okända eller nya webbplatser kan garanterat bara se innehåll som är aktivt och klart. [!UICONTROL Production] Med värdhantering kan du enkelt säkerställa kvaliteten på nya aktiviteter och innehåll i test-, staging- och utvecklingsmiljöer innan du aktiverar aktiviteterna.

[!DNL Target] begränsar inte en värd som kan skicka och ta emot rutor, så när nya servrar eller domäner kommer upp fungerar de automatiskt (såvida du inte har skapat en vitlista eller svartlista). Detta möjliggör även annonstestning på olika domäner som du inte vet eller inte kan förutse.

Om du vill hantera värdar klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Känna igen värdar {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Följande villkor måste vara uppfyllda för att en värd ska identifieras och läggas till i [!UICONTROL Hosts] listan:

* Minst en mbox måste finnas på värden
* En sida på värden måste ha följande:

   * En korrekt at.js- eller mbox.js-referens
   * En mbox eller ett automatiskt genererat globalt mbox-anrop

* Sidan med mbox måste visas i en webbläsare

När sidan har visats listas värden i [!UICONTROL Hosts] listan så att du kan hantera den i en miljö samt förhandsgranska och starta aktiviteter och tester.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>Detta inkluderar alla personliga utvecklingsservrar.

Kontrollera att värden känns igen när en värd har lagts till i [!UICONTROL Host] listan.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Uppdatera webbläsaren om värden inte visas.

   Som standard placeras en nyligen identifierad värd i [!UICONTROL Production] miljön. Det här är den säkraste miljön eftersom den inte tillåter att inaktiva aktiviteter kan ses från dessa värdar.

1. (Villkorligt) Klicka på flyttningsikonen ( ![flyttningsikonen](/help/administrating-target/assets/icon-move.png) ) för att flytta värden till [!UICONTROL Development], [!UICONTROL Staging]eller till någon annan miljö.

>[!NOTE]
>
>Det går inte att ta bort [!UICONTROL Production] miljön även om du byter namn på den. Det antas att det är här du kommer att utföra slutgiltiga, aktiva aktiviteter och tester. Standardmiljön tillåter inte att inaktiva kampanjer visas.

## Sortera eller söka i listan Värdar {#section_068B23C9D8224EB78BC3B7C8580251B0}

Om du vill sortera [!UICONTROL Hosts] listan klickar du på en kolumnrubrik ([!UICONTROL Name], [!UICONTROL Environment]eller [!UICONTROL Last Requested]) för att sortera listan i stigande eller fallande ordning.

Om du vill söka i [!UICONTROL Hosts] listan skriver du ett sökord i [!UICONTROL Search Hosts] rutan.

## Skapa vitlistor som anger värdar som har behörighet att skicka mbox-anrop till Target. {#whitelist}

Du kan skapa en vitlista som anger värdar (domäner) som har behörighet att skicka mbox-anrop till [!DNL Target]. Alla andra värdar som genererar anrop får ett svar på ett kommenterat auktoriseringsfel. Som standard registreras alla värdar som innehåller ett mbox-anrop med [!DNL Target] i produktionsmiljön och har tillgång till alla aktiva och godkända aktiviteter. Om detta inte är det önskade sättet kan du i stället använda vitlistan för att registrera specifika värdar som kan ringa mbox-samtal och ta emot [!DNL Target] innehåll. Alla värdar kommer att fortsätta att visas i [!UICONTROL Hosts] listan, och miljöer kan fortfarande användas för att gruppera dessa värdar och tilldela olika nivåer till varje, till exempel om värden kan se aktiva och/eller inaktiva kampanjer.

Så här skapar du en vitlista:

1. From the [!UICONTROL Hosts] list, click **[!UICONTROL Authorize Hosts]**.
1. Aktivera **[!UICONTROL Enable Authorized Hosts for content delivery]** växlingsknappen.
1. Lägg till önskade värdar i **[!UICONTROL Host contains]** rutan efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Lägg till önskade värdar i **[!UICONTROL Host does not contains]** rutan efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Klicka på **[!UICONTROL Save]**.

Om ett mbox-anrop görs till en obehörig värd besvaras samtalet med `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Bästa praxis** för säkerhet: Om du använder funktionen ubox i [!DNL Target]bör du tänka på att den här vitlistan även styr listan över domäner som [omdirigerarna](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) kan navigera till. Se till att du lägger till domäner som du vill omdirigera till när du använder ubox som en del av implementeringen. Om vitlistan inte anges kan Adobe inte verifiera omdirigerings-URL:erna och skydda mot potentiella skadliga omdirigeringar.
>
>Vitlistan har företräde framför miljöer. Du bör rensa bort alla värdar innan du använder vitlistefunktionen. Då visas bara de värdar som är tillåtna i vitlistan i värdlistan. Du kan sedan flytta värdarna till den önskade miljön.

Ibland visas domäner från andra platser i dina miljöer. En domän visas i listan om domänen gör ett anrop till at.js eller mbox.js. Om någon t.ex. kopierar en av dina webbsidor till sin server, visas den domänen i din miljö. Du kan också se domäner från spindelmotorer, översättarplatser eller lokala diskenheter.

I de fall där `mboxHost` skickas i ett API-anrop registreras konverteringen för den miljö som skickas. Om ingen miljö skickas blir värddatorn i anropet som standard [!UICONTROL Production].

Du kan också skapa en svart lista som anger värdar (domäner) än vad som inte kan skicka mbox-anrop till [!DNL Target] genom att lägga till önskade värdar i [!UICONTROL Host Does Not Contain] rutan.

## Ta bort en värd {#section_F56355BA4BC54B078A1A8179BC954632}

Du kan ta bort en värd när den inte längre behövs.

1. Klicka på [!UICONTROL Hosts] ikonen i **[!UICONTROL Delete]** listan.
1. Klicka **[!UICONTROL Delete]** för att bekräfta borttagningen.

>[!NOTE]
>
>Värden listas igen om någon bläddrar till en sida i kartong på värden.

## Felsökning av värdar {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Bästa tillvägagångssätt för att hantera och felsöka värdar i [!DNL Adobe Target].

Prova följande felsökningstips om du får problem med värdarna:

**Värden visas inte i mbox-listan för ditt konto.**

* Uppdatera [!UICONTROL Hosts] sidan i webbläsaren.
* Kontrollera att mbox-koden är korrekt, inklusive referensen at.js eller mbox.js.
* Försök att bläddra till en av mapparna på värden. Det är möjligt att ingen mbox på värden renderades i en webbläsare.

**Slumpmässiga eller okända domäner visas i[!UICONTROL Host]listan.**

En domän visas i den här listan om ett anrop görs från domänen. [!DNL Target] Ofta kan du se domäner från spindelmotorer, översättarplatser eller lokala diskenheter. Om den listade domänen inte är en som ditt team använder kan du klicka för [!UICONTROL Delete] att ta bort den.

**Min mbox-anrop returnerar /* ingen skärm - oauktoriserad mbox-värd */.**

Om ett mbox-anrop görs på en obehörig värd besvaras samtalet med /* no display - unauthorized mbox host */.
