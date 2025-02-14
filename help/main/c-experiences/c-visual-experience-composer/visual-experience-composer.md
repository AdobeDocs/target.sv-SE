---
keywords: Visual experience disposition;vec;wysiwyg
description: Lär dig grunderna i hur du använder Visual Experience Composer (VEC) i Adobe Target. VEC är en WYSIWYG-editor där ni enkelt kan skapa personaliserade upplevelser.
title: Hur använder jag Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: 3aeac3344c2bbc2a44da80b5a359e55c9419b59b
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 0%

---

# Visual Experience Composer (VEC)

Information om hur du använder [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target].

>[!NOTE]
>
>Versionen [!DNL Target Standard/Premium] 25.2.1 (17 februari 2025) innehöll en uppdaterad version av VEC. Mer information om hur den uppdaterade VEC skiljer sig från den tidigare versionen finns i [Ändringar i Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md).

VEC är ett WYSIWYG-användargränssnitt där man enkelt kan skapa och testa personaliserade upplevelser och erbjudanden i webbplatskontexten. Du kan skapa upplevelser och erbjudanden för [!DNL Target]-aktiviteter genom att dra och släppa, byta och ändra layouten och innehållet på en webbsida (eller ett erbjudande) eller en mobilwebbsida.

VEC är en av huvudfunktionerna i [!DNL Adobe Target]. Med VEC kan marknadsförare och designers skapa och ändra innehåll med ett visuellt gränssnitt. Många designalternativ kan göras utan att koden behöver redigeras direkt. Det går också att redigera HTML och JavaScript med de redigeringsalternativ som finns i dispositionen.

På fliken Mål **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** kan du ange standardwebbadressen för [!UICONTROL Visual Experience Composer].

![VEC markerat](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

Den här URL:en avgör var du börjar när du öppnar VEC. Om du inte anger något standardvärde börjar du med en tom sida när du öppnar redigeraren och anger en URL vid den tidpunkten.

>[!NOTE]
>
>Vissa webbläsare, till exempel [!DNL Firefox], kan blockera en sida från att visas i VEC om sidan innehåller blandat innehåll (till exempel en osäker sida på en säker webbplats). Om sidan inte visas klickar du på ikonen bredvid URL-adressen i webbläsarens adressfält och klickar på **[!UICONTROL Disable protection on this page]**. Problemet påverkar inte hur sidorna visas för webbplatsbesökare.

Innehåll i en iframe på sidan kan inte ändras i VEC. Om du vill redigera innehåll i en iframe kontrollerar du att iframe-dokumentet är [!DNL Target]-aktiverat och läser sedan in iframe-URL:en i VEC.

Du kan använda flikarna i bildrutan [!UICONTROL Experiences] för att visa sidan så som den skulle visas för olika målgrupper eller med olika upplevelser. Du kan ange ett namn för varje upplevelse. Om du till exempel testar var länken Hem finns i navigeringsfältet kan du ge en upplevelse där länken Hem först visas, till exempel&quot;Hemlänk&quot;, så att det blir enklare att identifiera upplevelserna i listan.

>[!NOTE]
>
>Ändringar i strukturen för en sida som påverkar platserna som används i en aktivitet som skapas på den sidan kan orsaka problem med upplevelseredigering. Om en plats har ändrats utanför VEC kanske [!DNL Target] inte kan hitta platsen där innehållet ändrades.

När du flyttar musen runt sidan följer markören en sammanhangsberoende ruta som markerar elementen på sidan.

<!--Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)-->

Klicka på ett markerat element om du vill se en meny med alternativ som är tillgängliga för den elementtypen. Du kan till exempel klicka på en bild och välja **[!UICONTROL Change Image]** om du vill ändra bilden till en annan bild. Eller klicka på en knapp och ändra textfärgen.

Du kan också klicka på **[!UICONTROL Browse]**, navigera till en sida som är tillgänglig från den primära sidan, till exempel en leveranssida eller en kundvagn, och testa ändringarna på den sidan. Du kan även komma åt sidelement som är tillgängliga när du hovrar, till exempel utfällbara menyer och minikort. När du har bläddrat klart till sidan klickar du på **[!UICONTROL Design]** för att redigera upplevelsen. Du kanske vill ändra designen för en rullgardinsmeny eller en karusell med bilder.

>[!NOTE]
>
>Om ett hovringstillstånd är beroende av JavaScript kontrollerar du att **[!UICONTROL Disable JavaScript]** inte är markerat. JavaScript måste vara aktiverat för att du ska kunna redigera JavaScript-element.

Mer information om de alternativ som är tillgängliga i VEC finns i [Alternativ för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Du kan göra vissa ändringar på en sida medan sidan läses in (eller när sidan inte kan läsas in), eller avbryta sidinläsningen i VEC. Mer information finns i:

* [Redigera en sida medan sidan läses in eller när sidan inte kan läsas in](#loading)
* [Avbryt inläsning av en sida i VEC](#cancel-loading)

## Redigera en sida medan sidan läses in eller när sidan inte kan läsas in {#loading}

Du kan utföra många åtgärder innan sidan läses in i VEC, eller även om sidan inte läses in helt (t.ex. om anpassad kod inte längre fungerar).

Det kan finnas skäl till att du vill komma åt eller redigera en sida medan den läses in i VEC eller när den inte läses in:

* Du vill göra en enkel ändring på en sida, t.ex. lägga till anpassad kod eller ändra namnet på en upplevelse
* Du vill kopiera befintlig anpassad kod från en sida som inte längre är tillgänglig
* Du vet att en sida inte läses in i VEC, men du vill ändå göra enkla redigeringar

När sidan läses in (eller när den inte kan läsas in) är panelen [!UICONTROL Experiences], panelen [!UICONTROL Modifications] och inställningarna högst upp i upplevelsen (Övertäckningar, Ändringar, Konfigurera och så vidare) tillgängliga.

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

När du har avbrutit sidinläsningen i VEC kan du växla mellan upplevelserna i aktiviteten utan att vänta på att sidan ska läsas in. Om du vill visa sidan i VEC igen måste du klicka på knappen **[!UICONTROL Reload]**.

>[!IMPORTANT]
>
>Tänk på att när anpassad kod eller ändringar görs måste du se till att kodningen eller ändringarna görs på rätt sätt genom att välja att avbryta inläsningen i VEC. Se till att du utför rätt kvalitetskontroll för att säkerställa att din egen kod och alla andra ändringar levereras som förväntat.

Om du vill avbryta inläsningen av en sida i VEC klickar du på knappen **[!UICONTROL Cancel Loading]** medan sidan läses in. Sidan läses inte in i VEC för den här aktiviteten under den aktuella redigeringssessionen.

Om du vill fortsätta att hantera upplevelser i den aktuella aktiviteten eller lägga till nya ändringar måste du klicka på knappen **[!UICONTROL Reload]**.
