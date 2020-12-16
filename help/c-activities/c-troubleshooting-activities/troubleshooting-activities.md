---
keywords: troubleshoot target;troubleshooting target;default content;test not live;activity not live;targeting not working;previous experience displays;cannot create activities;can't create activities;create activities;page structure changed;page structure modified;error message;error delete profile script;ajax not working
description: Om din aktivitet inte visas på din webbplats kan du hitta lösningen med hjälp av de här felsökningsförslagen.
title: Felsöka aktiviteter
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---


# Felsöka aktiviteter{#troubleshoot-activities}

Om din aktivitet inte visas på din webbplats kan du hitta lösningen med hjälp av de här felsökningsförslagen.

>[!NOTE]
>
>Förutom följande felsökningsinformation finns i [Felsökningsmål](/help/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) länkar till ytterligare felsökningsämnen, vanliga frågor och svar samt annan användbar information om felsökningsaktiviteter och andra funktioner i [!DNL Adobe Target].

Följande avsnitt innehåller problem som du kan stöta på när du föreslår lösningar.

## Jag skapade en aktivitet med målgränssnittet och kan inte uppdatera den via API.

Aktiviteter som skapas med målgränssnittet bör uppdateras via målgränssnittet. Aktiviteter som skapas via API ska uppdateras via API. Om du ursprungligen skapade en aktivitet med API, till exempel, men sedan redigerar aktiviteten via målgränssnittet, uppdateras inte alla ändringar. Alla ändringar lagras på serverdelen och kan uppdateras genom att du gör ett annat API-anrop.

Det bästa är att försöka uppdatera aktiviteten med samma metod (UI eller API) som användes för att skapa aktiviteten från början.

## Du ser standardinnehåll.

Kontrollera att aktiviteten är slutförd och att den har aktiverats.

## Aktiviteten är inte aktiv.

**Validera:** Gå till fliken Översikt och se om testet är markerat som inaktivt eller utkast.

**Alternativ:**

* Aktivera test.
* Använd Förhandsgranska länkar om du vill visa ett inaktivt test.

## Ni uppfyller inte villkoren för målgruppsanpassning.

**Validera:** Granska villkor för målinriktning på översiktssidan.

**Alternativ:**

* Kvalificera och försök igen.
* Använd Förhandsgranska länkar för att åsidosätta målinriktningsvillkoren.

## Sidan uppfyller inte villkoren för sidanpassning.

**Validera:** På översiktssidan anger du om sidan ligger utanför målvillkoren.

**Alternativ:**

* Gå till Visual Experience Composer och klicka på URL\> Advanced\>current page.

## En tidigare upplevelse visas i stället för den nya.

**Validera:** Prova något av alternativen nedan och försök visa upplevelsen igen.

**Alternativ:**

* Rensa cache och cookies och försök sedan igen.

* Prova en annan webbläsare.
* Använd läget Privat/Inkognito.

## Du har nyligen lagts till i Target men kan inte skapa aktiviteter.

**validera:** Klicka på Skapa aktivitet. Om alternativet inte är tillgängligt har du förmodligen inte fått tillräcklig behörighet för att skapa en aktivitet.

**Alternativ:**

När du har lagts till som användare i Target måste du ha rollen Godkännare för att kunna skapa aktiviteter.

* Be administratören för ditt konto att göra dig till godkännare.
* Om du är administratör kan du ge dig själv rollen Godkännare från **[!UICONTROL Administration]** > **[!UICONTROL Users]** i Mål.

   Se [Tilldela dig själv rollen Godkännare](/help/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Sidans struktur har ändrats sedan du konfigurerade aktiviteten.

**Validera:** Gå till Visual Experience Composer för den befintliga aktiviteten. Leta efter ett varningsmeddelande som anger att väljarna (eller strukturen) har ändrats.

**Alternativ:**

* Återskapa aktiviteten.

Mer information om hur sidändringar påverkar Target förmåga att visa finns i [Scenarier för sidändring](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Sidans struktur ändras under sidinläsning (vid körning).

**validera:** Fråga utvecklaren.

**Obs!** För att Target ska kunna identifiera var aktivitetsändringar ska tillämpas bör du undvika att dynamiskt infoga element med samma klass eller dynamiskt ändra klassen för alla objekt på samma nivå.

**Alternativ:**

* Uppdatera sidkoden så att varje element som ska testas identifieras unikt (med ett id).
* Sluta dynamiskt ändra klassen eller jämställda objekt enligt beskrivningen ovan.

Mer information om hur sidändringar påverkar Target förmåga att visa finns i [Scenarier för sidändring](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Mbox.js öppnar all efterföljande kod från huvudet och in i kroppen.

**Validera:** Visa källa för att avgöra om en deklaration följer filen mbox.js före den avslutande  `</body>` taggen.

**Alternativ:**

* Placera mbox.js som det sista objektet i `<head>`-avsnittet på sidan.
* Använd unika div-ID:n på elementen på den högsta nivån i kroppen.

## Andra aktiviteter körs på samma sida.

**Validera:** Använd fliken Konflikter för att se om andra aktiviteter körs.

**Obs!** Fliken Konflikter fungerar inte med modulen Malltestning.

**Alternativ:**

* Öka prioriteten för den här aktiviteten.
* Minska prioriteringen för andra aktiviteter.
* Inaktivera andra aktiviteter.

## Ett felmeddelande visas när du tar bort ett profilskript.

**Validera:Om du** tar bort ett profilskript från Target Standard/Premium visas felmeddelandet&quot;Failed to delete profile script&quot;.

**Alternativ:**

Gör något av följande:

* Ta bort igen. Meddelandet om att åtgärden lyckades visas.
* Vänta i ungefär 10 minuter innan Target Standard-/Premium-importeraren körs. Importverktyget uppdaterar profillistan med skript.

## Vissa ajax [!DNL Target]-anrop fungerar inte.

**Obs!** Flera ajax- [!DNL Target] anrop med samma namn men olika parametrar fungerar inte på samma sida. Endast den första samtalet kommer att göras.

## Du har aktiverat en aktivitet med Target API, men aktiviteten visar statusen [!UICONTROL Inactive] i Target-gränssnittet.

När du utför vissa åtgärder, t.ex. aktiverar en aktivitet utanför användargränssnittet med Target-API:t, kan det ta upp till tio minuter att uppdatera gränssnittet.