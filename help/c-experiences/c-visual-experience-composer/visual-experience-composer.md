---
description: Information om hur du använder Visual Experience Composer (VEC) i Adobe Target.
title: Adobe Target Visual Experience Composer (VEC)
feature: vec
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: fbb0a4b07f9294846aac88ac692159e658c2c8e2
workflow-type: tm+mt
source-wordcount: '1353'
ht-degree: 0%

---


# Visual Experience Composer (VEC){#visual-experience-composer-vec}

Information om hur du använder Visual Experience Composer (VEC).

VEC är ett WYSIWYG-användargränssnitt som gör det enkelt att skapa och testa personaliserade upplevelser och erbjudanden i webbplatskontexten. Du kan skapa upplevelser och erbjudanden för Target-aktiviteter genom att dra och släppa, byta och ändra layouten och innehållet på en webbsida (eller ett erbjudande) eller en mobilwebbsida.

VEC är en av huvudfunktionerna i [!DNL Adobe Target]. Med VEC kan marknadsförare och designers skapa och ändra innehåll med ett visuellt gränssnitt. Många designalternativ kan göras utan att koden behöver redigeras direkt. Det går också att redigera HTML och JavaScript med de redigeringsalternativ som finns i dispositionen.

På fliken Mål **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** kan du ange standardwebbadressen för Visual Experience Composer.

![Standardinställningar för VEC URL](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

Den här URL:en avgör var du börjar när du öppnar VEC. Om du inte anger något standardvärde börjar du med en tom sida när du öppnar redigeraren och anger en URL vid den tidpunkten.

>[!NOTE]
>
>Vissa webbläsare, till exempel Firefox, kan hindra en sida från att visas i VEC om sidan innehåller blandat innehåll (till exempel en osäker sida på en säker plats). Om sidan inte visas klickar du på ikonen bredvid URL-adressen i webbläsarens adressfält och klickar på **[!UICONTROL Disable protection on this page]**. Problemet påverkar inte hur sidorna visas för webbplatsbesökare.

Innehåll i en iframe på sidan kan inte ändras i VEC. Om du vill redigera innehåll i en iframe kontrollerar du att iframe-dokumentet är Target-aktiverat och läser sedan in iframe-URL:en i VEC.

Du kan använda de nedrullningsbara menyerna längst upp på sidan för att visa sidan så som den skulle se ut för olika målgrupper eller med olika upplevelser. Du kan ange ett namn för varje upplevelse i den andra listrutan. Om du till exempel testar var länken Hem finns i navigeringsfältet kan du ge en upplevelse där länken Hem först visas, till exempel&quot;Hemlänk&quot;, så att det blir enklare att identifiera upplevelserna i listan.

>[!NOTE]
>
>Ändringar i strukturen för en sida som påverkar platserna som används i en aktivitet som skapas på den sidan kan orsaka problem med upplevelseredigering. Om en plats har ändrats utanför VEC kanske inte Target kan hitta platsen där innehållet ändrades.

När du flyttar musen runt sidan följer markören en sammanhangsberoende ruta som markerar elementen på sidan.

![VEC markerat](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

Klicka på **[!UICONTROL Overlays]** ikonen om du vill ändra hur högdagern visas. Du kan t.ex. välja att bara markera bilder, länkar, regionala kryssrutor, ändringar eller JavaScript. Du kan ändra färgen på högdagern. Du kan också ange en markeringsfärg och typ av fyllning som används för att markera olika elementtyper.

![Ändra inställningar för övertäckning](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

Klicka på ett markerat element för en meny med alternativ som är tillgängliga för den elementtypen. Du kan till exempel klicka på en bild och välja **[!UICONTROL Edit > Text/HTML]** att ändra texten eller klicka på en knapp och ändra bakgrundsfärgen. Du kan använda knapparna längst upp till vänster på sidan för att växla mellan att aktivera och inaktivera övertäckningarna.

Du kan också klicka **[!UICONTROL Browse]** och sedan navigera till en sida som är tillgänglig från den primära sidan, till exempel en leveranssida eller en kundvagn, och testa ändringarna på den sidan. Du kan även komma åt sidelement som är tillgängliga när du hovrar, till exempel utfällbara menyer och minikort. När du har bläddrat klart till sidan klickar du på **[!UICONTROL Compose]** för att redigera upplevelsen. Du kanske vill ändra designen för en rullgardinsmeny eller en karusell med bilder.

>[!NOTE]
>
>Om ett hovringsläge är beroende av JavaScript kontrollerar du att **[!UICONTROL Disable JavaScript]** inte är markerat. JavaScript måste vara aktiverat för att du ska kunna redigera JavaScript-element.

Information om de alternativ som är tillgängliga i VEC finns i Alternativ för [Visual Experience Composer](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Du kan göra vissa ändringar på en sida medan sidan läses in (eller när sidan inte kan läsas in), eller avbryta sidinläsningen i VEC. Mer information finns i:

* [Redigera en sida medan sidan läses in eller när sidan inte kan läsas in](#loading)
* [Avbryt inläsning av en sida i VEC](#cancel-loading)

## Redigera en sida medan sidan läses in eller när sidan inte kan läsas in {#loading}

Du kan utföra många åtgärder innan sidan läses in i VEC, eller även om sidan inte läses in helt (t.ex. om anpassad kod inte längre fungerar).

Det kan finnas skäl till att du vill komma åt eller redigera en sida medan den läses in i VEC eller när den inte läses in:

* Du vill göra en enkel ändring på en sida, t.ex. lägga till anpassad kod eller ändra namnet på en upplevelse
* Du vill kopiera befintlig anpassad kod från en sida som inte längre är tillgänglig
* Du vet att en sida inte läses in i VEC, men du vill ändå göra enkla redigeringar

När sidan läses in (eller när den inte kan läsas in) är panelen, [!UICONTROL Experiences] [!UICONTROL Modifications] panelen och inställningarna högst upp i upplevelsen (Övertäckningar, Ändringar, Konfigurera och så vidare) tillgängliga.

Följande bild visar att du kan infoga egen kod eller utföra andra åtgärder medan sidan fortfarande läses in:

![Sidinläsning](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## Avbryt inläsning av en sida i VEC {#cancel-loading}

Du kan avbryta inläsningen av en sida i VEC för att låsa upp redigering av aktiviteten utan att vänta på att sidan ska läsas in. Den här funktionen sparar tid och hjälper dig att göra enkla redigeringar eller infoga anpassad kod effektivare utan att behöva vänta på att sidan ska läsas in i VEC.

Några orsaker till varför du kanske vill avbryta sidinläsning i VEC är:

* Du vill göra mindre ändringar i befintliga ändringar
* Du vill ta bort en eller flera befintliga ändringar
* Du vill infoga eller redigera egen kod
* Du angav fel URL för sidan
* Du vill aktivera eller inaktivera JavaScript innan du läser in sidan i VEC
* Du vill lägga till fler testregler för mallar i villkoren för sidleverans
* Du vill åsidosätta växlingsknappen för den globala funktionen Enhanced Experience Composer (EEC) när du läser in en sida via EEC, eller så kan endast iframe-funktionerna variera sida för sida

När du har avbrutit sidinläsningen i VEC kan du växla mellan upplevelserna i aktiviteten utan att vänta på att sidan ska läsas in. Om du vill visa sidan i VEC igen måste du klicka på **[!UICONTROL Reload]** knappen.

>[!IMPORTANT]
>
>Tänk på att när anpassad kod eller ändringar görs måste du se till att kodningen eller ändringarna görs på rätt sätt genom att välja att avbryta inläsningen i VEC. Se till att du utför rätt kvalitetskontroll för att säkerställa att din egen kod och alla andra ändringar levereras som förväntat.

Om du vill avbryta inläsningen av en sida i VEC klickar du på **[!UICONTROL Cancel Loading]** knappen medan sidan läses in. Sidan läses inte in i VEC för den här aktiviteten under den aktuella redigeringssessionen.

![Knappen Avbryt inläsning](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

Om du vill fortsätta att hantera upplevelser i den aktuella aktiviteten eller lägga till nya ändringar måste du klicka på **[!UICONTROL Reload]** knappen.

![Knappen Läs in igen](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>Det finns ett känt fel med den här funktionen som kommer att åtgärdas i nästa version. Mer information finns i&quot;Avbryt inläsning av en sida i VEC&quot; på sidan [Kända fel och lösta problem](/help/r-release-notes/known-issues-resolved-issues.md#cancel) .

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Visuell Experience Composer (1 av 2) (7:17) - ![självstudiemärke](/help/assets/tutorial.png)

* Ändra innehållet på en sida
* Ändra layouten för en sida

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Visual Experience Composer (2 av 2) (7:29) ![Självstudiemärke](/help/assets/tutorial.png)

* Byta namn på och duplicera en upplevelse
* Skapa en omdirigeringsupplevelse
* Anpassa en aktivitet till en enskild URL-adress eller en grupp URL-adresser
* Skapa en flersidig aktivitet
* Förgranska och skapa upplevelser för responsiva webbplatser
* Använda övertäckningar för att markera typer av element

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Kontorstid: badge för Visual Experience Composer ![Tutorial](/help/assets/tutorial.png)

Den här videon är en inspelning av&quot; [Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Hur VEC fungerar
* Hur man undviker vanliga problem med VEC
* Sätter att kringgå arbetet med VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)