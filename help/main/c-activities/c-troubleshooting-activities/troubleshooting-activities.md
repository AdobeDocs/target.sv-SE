---
keywords: felsöka mål;felsökningsmål;standardinnehåll;testa inte live;aktivitet inte live;målinriktning inte fungerar;föregående upplevelse visas;kan inte skapa aktiviteter;kan inte skapa aktiviteter;skapa aktiviteter;sidstruktur ändrad;sidstruktur ändrad;felmeddelande;felborttagningsprofilskript;ajax fungerar inte
description: Hitta felsökningsförslag om din Adobe [!DNL Target] -aktiviteten visas inte på din plats.
title: Hur felsöker jag aktiviteter?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---

# Felsöka aktiviteter

Om [!DNL Adobe Target] -aktiviteten inte visas på din webbplats. Dessa felsökningsförslag bör hjälpa dig att hitta din lösning.

>[!NOTE]
>
>Förutom följande felsökningsinformation finns mer information i [Felsökningsmål](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) för länkar till ytterligare felsökningsämnen, vanliga frågor och svar och annan användbar information om felsökningsaktiviteter och andra funktioner i [!DNL Adobe Target].

Följande avsnitt innehåller problem som du kan stöta på när du föreslår lösningar.

## Jag skapade en aktivitet med [!DNL Target] Gränssnittet och jag kan inte uppdatera det via API.

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

**Validera:** Granska målinriktningsvillkoren på översiktssidan.

**Alternativ:**

* Kvalificera och försök igen.
* Använd Förhandsgranska länkar för att åsidosätta målinriktningsvillkoren.

## Sidan uppfyller inte villkoren för sidanpassning.

**Validera:** På översiktssidan anger du om sidan ligger utanför målvillkoren.

**Alternativ:**

* Gå till Visual Experience Composer och klicka på URL\> Advanced\>current page.

## En tidigare upplevelse visas i stället för den nya.

**Validera:** Försök med något av alternativen nedan och försök visa upplevelsen igen.

**Alternativ:**

* Rensa cache och cookies och försök sedan igen.

* Prova en annan webbläsare.
* Använd läget Privat/Inkognito.

## Du har nyligen lagts till i [!DNL Target] men kan inte skapa aktiviteter.

**Validera:** Klicka på Skapa aktivitet. Om alternativet inte är tillgängligt har du förmodligen inte fått tillräcklig behörighet för att skapa en aktivitet.

**Alternativ:**

När du har lagts till som användare i Target måste du ha rollen Godkännare för att kunna skapa aktiviteter.

* Be administratören för ditt konto att göra dig till godkännare.
* Om du är administratör kan du ge dig själv rollen som godkännare från **[!UICONTROL Administration]** > **[!UICONTROL Users]** i Target.

   Se [Tilldela dig själv rollen Godkännare](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Sidans struktur har ändrats sedan du konfigurerade aktiviteten.

**Validera:** Gå till Visual Experience Composer för den befintliga aktiviteten. Leta efter ett varningsmeddelande som anger att väljarna (eller strukturen) har ändrats.

**Alternativ:**

* Återskapa aktiviteten.

Mer information om hur sidändringar påverkar Target möjlighet att visa finns i [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Sidans struktur ändras under sidinläsning (vid körning).

**Validera:** Fråga utvecklaren.

**Obs!** För att Target ska kunna identifiera var aktivitetsändringar ska tillämpas bör du undvika att dynamiskt infoga element med samma klass eller dynamiskt ändra klassen för alla objekt på samma nivå.

**Alternativ:**

* Uppdatera sidkoden så att varje element som ska testas identifieras unikt (med ett id).
* Sluta dynamiskt ändra klassen eller jämställda objekt enligt beskrivningen ovan.

Mer information om hur sidändringar påverkar Target möjlighet att visa finns i [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Andra aktiviteter körs på samma sida.

**Validera:** Använd fliken Konflikter för att se om andra aktiviteter körs.

**Obs!** Fliken Konflikter fungerar inte med modulen Malltestning.

**Alternativ:**

* Öka prioriteten för den här aktiviteten.
* Minska prioriteringen för andra aktiviteter.
* Inaktivera andra aktiviteter.

## Ett felmeddelande visas när du tar bort ett profilskript.

**Validera:** Om du tar bort ett profilskript från Target Standard/Premium visas felmeddelandet&quot;Failed to delete profile script&quot;.

**Alternativ:**

Gör något av följande:

* Ta bort igen. Meddelandet om att åtgärden lyckades visas.
* Vänta i ungefär 10 minuter innan Target Standard-/Premium-importeraren körs. Importverktyget uppdaterar profillistan med skript.

## Lite ajax [!DNL Target] samtal fungerar inte.

**Obs!** Flera ajax [!DNL Target] anrop med samma namn men olika parametrar fungerar inte på samma sida. Endast den första samtalet kommer att göras.

## Du har aktiverat en aktivitet med [!DNL Target] API, men aktiviteten visar status för [!UICONTROL Inactive] i [!DNL Target] Gränssnitt.

När du utför vissa åtgärder, t.ex. aktiverar en aktivitet utanför användargränssnittet med Target-API:t, kan det ta upp till tio minuter att uppdatera gränssnittet.