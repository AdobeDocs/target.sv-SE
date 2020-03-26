---
keywords: host;hosts;host group;environment;troubleshooting;best practices
description: Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.
title: Värdar
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Värdar{#hosts}

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

## Värdar {#concept_516BB01EBFBD4449AB03940D31AEB66E}

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

Det främsta målet med värdhantering är att se till att inget inaktivt innehåll av misstag visas på webbplatser. Med värdhantering kan du också separera rapportdata efter miljö.

En värd är en webbserver (eller webbdomän) varifrån du underhåller innehåll under någon del av projektet. Alla värdar som betjänar en mbox känns igen.

Värdar paketeras i miljöer för enkel hantering. Du kan till exempel ha dussintals värdar grupperade i två eller tre miljöer. I förinställda miljöer ingår produktion, mellanlagring och utveckling. Du kan lägga till nya miljöer och byta namn på dina miljöer om du vill.

En miljö, standardmiljön, heter Production i förväg. Den här standardmiljön kan inte tas bort, även om du byter namn på den. [!DNL Target] förutsätter att det är här du kommer att utföra slutgiltiga, godkända aktiviteter och tester.

När en mbox-begäran tas emot från nya webbplatser eller domäner visas alltid dessa nya domäner i produktionsmiljön. Inställningarna för produktionsmiljön kan inte ändras, så okända eller nya webbplatser kan garanterat bara se aktivt och klart innehåll. Med värdhantering kan du enkelt säkerställa kvaliteten på nya aktiviteter och innehåll i test-, staging- och utvecklingsmiljöer innan du aktiverar aktiviteterna.

Målet begränsar inte en värd som kan skicka och ta emot rutor, så när nya servrar eller domäner kommer upp fungerar de automatiskt (såvida du inte har ställt in en vitlista eller svartlista). Detta möjliggör även annonstestning på olika domäner som du inte vet eller inte kan förutse.

Om du vill hantera värdar och miljöer klickar du på **[!UICONTROL Konfigurera]** > **[!UICONTROL Värdar]**.

![](assets/hosts_list.png)

## Identifiera värdar {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Information om villkoren som måste uppfyllas för [!DNL Target] att en värd ska identifieras och läggas till i listan Värdar.

Följande villkor måste vara uppfyllda för att en värd ska kunna identifieras:

* Minst en mbox måste finnas på värden
* En sida på värden måste ha följande:

   * En korrekt [!DNL mbox.js] referens
   * En mbox eller ett automatiskt genererat globalt mbox-anrop

* Sidan med mbox måste visas i en webbläsare

När sidan har visats listas värden i listan [!UICONTROL Värdar] , vilket gör att du kan hantera den i en miljö samt förhandsgranska och starta aktiviteter och tester.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>Detta inkluderar alla personliga utvecklingsservrar.

Kontrollera att värden känns igen när en värd har lagts till i [!UICONTROL värdlistan] .

1. Klicka på **[!UICONTROL Konfigurera]** > **[!UICONTROL Värdar]**.
1. Uppdatera webbläsaren om värden inte visas.
Som standard placeras en nyligen identifierad värd i produktionsmiljön. Det här är den säkraste miljön eftersom den inte tillåter att inaktiva aktiviteter kan ses från dessa värdar.
1. (Villkorligt) Flytta värden till utvecklings- eller mellanlagringsmiljön.

>[!NOTE]
>
>Det går inte att ta bort produktionsmiljön även om du byter namn på den. Det antas att det är här du kommer att utföra slutgiltiga, aktiva aktiviteter och tester. Standardmiljön tillåter inte att inaktiva kampanjer visas.

## Hantera värdar och miljöer {#concept_90573F5A52E04600A8C3C5897880C10F}

Information som hjälper dig att hantera värdar och miljöer (värdgrupper), inklusive att ange standardvärden för rapportering, skapa vitlistor, ändra en miljös namn, flytta en värd till en annan miljö och ta bort en värd eller miljö.


Du öppnar listan [!UICONTROL Värdar] genom att klicka på **[!UICONTROL Inställningar]** > **[!UICONTROL Värdar]**.

![](assets/hosts_list.png)

## Filtrera, sortera eller söka i värdlistan {#section_068B23C9D8224EB78BC3B7C8580251B0}

Om du vill filtrera [!UICONTROL värdlistorna] efter miljö klickar du på listrutan **[!UICONTROL Alla]** och väljer sedan önskad miljö (Produktion, Förproduktion, Utveckling eller en anpassad miljö som du har skapat).

Om du vill sortera listan [!UICONTROL Värdar] klickar du på en kolumnrubrik (Namn, Miljö eller Senast begärd) för att sortera listan i stigande eller fallande ordning.

Om du vill söka i listan [!UICONTROL Värdar] skriver du en sökterm i sökrutan.

## Välj flera värdar {#section_EF3B458475184B7EA997C3559714397C}

Om du vill välja flera värdar markerar du kryssrutorna bredvid kolumnen [!UICONTROL Namn] för önskade värdar. Du kan sedan flytta eller ta bort alla markerade värdar.

## Skapa en miljö {#section_32097D0993724DF3A202D164D3F18674}

1. Klicka på fliken [!UICONTROL Miljö] i listan **[!UICONTROL Värdar]** .
1. Klicka på **[!UICONTROL Skapa miljö]**.
1. Ange ett beskrivande namn för miljön.
1. Ange önskat aktivt läge för miljön: [!UICONTROL Aktiva aktiviteter] eller [!UICONTROL Aktiva och inaktiva aktiviteter].
1. Klicka på **[!UICONTROL Spara]**.

## Ange standardvärd för rapportering {#section_4F8539B07C0C45E886E8525C344D5FB0}

Du kan välja den miljö som du vill använda som standard för alla aktivitetsrapporter.

Om du använder Produktion som standard läggs alla okända värdar automatiskt till här och rapportdata från den inkluderas i standardrapportvyn. Om du i stället skapar en&quot;ren&quot; miljö omfattas bara dina kärnwebbplatser/domäner.

Så här anger du standardmiljön för rapportering:

1. Klicka på fliken [!UICONTROL Inställningar] i listan **[!UICONTROL Värdar]** .
1. Välj standardvärden i listrutan **[!UICONTROL Miljöinställningar]** .
1. Klicka på **[!UICONTROL Spara]**.

>[!NOTE]
>
>[!DNL Recommendations] -användare måste återskapa sin beteendedatabas och produktdatabas om värdar byter värdgrupper.

## Skapa vitlistor som anger värdar som är auktoriserade att skicka mbox-anrop till mål. {#section_0AF7F56C386A42C381AF704DEF08D5CC}

Du kan skapa en vitlista som anger värdar (domäner) som har behörighet att skicka mbox-anrop till [!DNL Target]. Alla andra värdar som genererar anrop får ett svar på ett kommenterat auktoriseringsfel. Som standard registreras alla värdar som innehåller ett mbox-anrop med [!DNL Target] i produktionsmiljön och har tillgång till alla aktiva och godkända aktiviteter. Om detta inte är det önskade sättet kan du i stället använda vitlistan för att registrera specifika värdar som kan ringa mbox-samtal och ta emot [!DNL Target] innehåll. Alla värdar fortsätter att visas i listan [!UICONTROL Värdar] , och miljöer kan fortfarande användas för att gruppera dessa värdar och tilldela olika nivåer till varje, till exempel om värden kan se aktiva och/eller inaktiva kampanjer.

Så här skapar du en vitlista:

1. Klicka på fliken [!UICONTROL Inställningar] i listan **[!UICONTROL Värdar]** .
1. Markera **[!UICONTROL kryssrutan Aktivera auktoriserade värdar för innehållsleverans]** .
1. Lägg till önskade värdar i rutan **[!UICONTROL Värd innehåller]** efter behov.

   Flera värdar kan listas, var och en på sin egen rad.

1. Klicka på **[!UICONTROL Spara]**.

Om ett mbox-anrop görs till en obehörig värd besvaras samtalet med `/* no display - unauthorized mbox host */`.

Vitlistan har företräde framför miljöer. Du bör rensa bort alla värdar innan du använder vitlistefunktionen. Då visas bara de värdar som är tillåtna i vitlistan i värdlistan. Du kan sedan flytta värdarna till den önskade miljön.

Ibland visas domäner från andra platser i dina miljöer. En domän visas i listan om domänen anropar din mbox.js. Om någon t.ex. kopierar en av dina webbsidor till sin server, visas den domänen i din miljö. Du kan också se domäner från spindelmotorer, översättarplatser eller lokala diskenheter.

I de fall där `mboxHost` skickas i ett API-anrop registreras konverteringen för den miljö som skickas. Om ingen miljö skickas används standardvärdet Production som värd i anropet.

Du kan också skapa en svart lista som anger värdar (domäner) än vad som inte kan skicka mbox-anrop till [!DNL Target] genom att lägga till önskade värdar i rutan [!UICONTROL Värden innehåller] inte.

## Ändra namnet på en miljö {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Klicka på fliken [!UICONTROL Miljö] i listan **[!UICONTROL Värdar]** .
1. Håll markören över den önskade miljön och klicka sedan på **[!UICONTROL Redigera]** -ikonen.
1. Ändra miljönamnet.
1. Klicka på **[!UICONTROL Spara]**.

## Flytta en värd till en annan miljö {#section_9F52549958BD485EB74FE78C32773D2A}

1. I listan [!UICONTROL Värdar] hovrar du över värden som du vill flytta.
1. Klicka på ikonen **[!UICONTROL Flytta]** .
1. Välj önskad miljö i listrutan och klicka sedan på bockmarkeringsikonen.

## Ta bort en värd {#section_F56355BA4BC54B078A1A8179BC954632}

Du kan ta bort en värd när den inte längre behövs.

1. I listan [!UICONTROL Värdar] håller du pekaren över den värd som du vill ta bort.
1. Klicka på ikonen **[!UICONTROL Ta bort]** .
1. Bekräfta borttagningen genom att klicka på **[!UICONTROL Ta bort]** .

>[!NOTE]
>
>Värden listas igen om någon bläddrar till en sida i kartong på värden.

## Ta bort en miljö {#section_737F8869612047868D03FC755B1223D3}

Du kan ta bort en miljö när den inte längre behövs.

1. Klicka på fliken [!UICONTROL Miljö] i listan **[!UICONTROL Värdar]** .
1. Håll pekaren över den miljö du vill ta bort.
1. Klicka på ikonen **[!UICONTROL Ta bort]** .
1. Bekräfta borttagningen genom att klicka på **[!UICONTROL Ta bort]** .

>[!NOTE]
>
>Du kan inte ta bort produktionsmiljön, men du kan byta namn på den.

## Felsökning av värdar {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Bästa tillvägagångssätt för att hantera och felsöka värdar i [!DNL Adobe Target].

Prova följande felsökningstips om du får problem med värdarna:

**Värden visas inte i mbox-listan för ditt konto.**

* Uppdatera sidan [!UICONTROL Värdar] i webbläsaren.
* Bekräfta att mbox-koden är korrekt, inklusive [!DNL mbox.js] referensen.
* Försök att bläddra till en av mapparna på värden. Det är möjligt att ingen mbox på värden renderades i en webbläsare.

**Slumpmässiga eller okända domäner visas i[!UICONTROL värdlistan].**

En domän visas i den här listan om ett anrop görs från domänen. [!DNL Target] Ofta kan du se domäner från spindelmotorer, översättarplatser eller lokala diskenheter. Om den listade domänen inte är en som teamet använder kan du ta bort den genom att klicka på [!UICONTROL Ta bort] .

**Min mbox-anrop returnerar /* ingen skärm - oauktoriserad mbox-värd */.**

Om ett mbox-anrop görs på en obehörig värd besvaras samtalet med /* no display - unauthorized mbox host */.

## Rekommendationer: filtrera samlingar och uteslutningar efter miljö (värdgrupp)

![Premium-märke](/help/assets/premium.png)

Du kan förhandsgranska innehållet i Recommendations-samlingar och undantag för en vald miljö (värdgrupp).

>[!NOTE]
>Rekommendationsaktiviteter finns tillgängliga som en del av Target Premium-lösningen. De är inte tillgängliga i Target Standard utan en Target Premium-licens.

Värdgruppen kan användas för att skilja de tillgängliga objekten i katalogen åt för olika användningsområden. Du kan till exempel använda värdgrupper för utvecklings- och produktionsmiljöer, olika varumärken eller olika geografiska platser. Som standard baseras förhandsgranskningsresultaten i Katalogsökning, Samlingar och Undantag på standardvärdgruppen. (Du kan också välja en annan värdgrupp om du vill förhandsgranska resultaten med hjälp av miljöfiltret.) Som standard är nyligen tillagda objekt tillgängliga i alla värdgrupper om inte ett miljö-ID anges när objektet skapas eller uppdateras. Levererade rekommendationer beror på värdgruppen som anges i begäran.

Om du inte ser dina produkter bör du kontrollera att du använder rätt värdgrupp. Om du t.ex. har konfigurerat din rekommendation att använda en mellanlagringsmiljö och du har angett mellanlagringsgruppen som värdgrupp kan du behöva återskapa dina samlingar i mellanlagringsmiljön för att produkterna ska kunna visas. Om du vill se vilka produkter som är tillgängliga i respektive miljö använder du Katalogsökning för varje miljö. Du kan också förhandsgranska innehållet i Rekommendationer-samlingar och undantag för en vald miljö (värdgrupp).

>[!NOTE]
>När du har ändrat den valda miljön måste du klicka på Sök för att uppdatera de returnerade resultaten.

Miljöfiltret är tillgängligt från följande platser i målgränssnittet:

* Katalogsökning ([!UICONTROL Rekommendationer > Katalogsökning])
* Dialogrutan Skapa samling ([!UICONTROL Rekommendationer > Samlingar > Skapa ny])
* Dialogrutan Uppdatera samling ([!UICONTROL Rekommendationer > Samlingar > Redigera])
* Dialogrutan Skapa undantag ([!UICONTROL Rekommendationer > Undantag > Skapa nytt])
* Dialogrutan Uppdatera undantag ([!UICONTROL Rekommendationer > Undantag > Redigera])
