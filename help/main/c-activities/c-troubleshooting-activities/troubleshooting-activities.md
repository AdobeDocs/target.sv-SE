---
keywords: felsöka mål;felsökningsmål;standardinnehåll;testa inte live;aktivitet inte live;målinriktning inte fungerar;föregående upplevelse visas;kan inte skapa aktiviteter;kan inte skapa aktiviteter;skapa aktiviteter;sidstruktur ändrad;sidstruktur ändrad;felmeddelande;felborttagningsprofilskript;ajax fungerar inte
description: Hitta felsökningsförslag om din Adobe [!DNL Target] -aktiviteten visas inte på din plats.
title: Hur felsöker jag aktiviteter?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: 8890d29a71506095a166321e324a000b5ad862a6
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Felsöka aktiviteter

Om [!DNL Adobe Target] -aktiviteten inte visas på din webbplats. Dessa felsökningsförslag bör hjälpa dig att hitta din lösning.

>[!NOTE]
>
>Förutom följande felsökningsinformation finns mer information i [Felsökningsmål](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) för länkar till ytterligare felsökningsämnen, vanliga frågor och svar och annan användbar information om felsökningsaktiviteter och andra funktioner i [!DNL Adobe Target].

Följande avsnitt innehåller problem som du kan stöta på när du föreslår lösningar.

## Jag skapade en aktivitet med [!DNL Target] Gränssnittet och jag kan inte uppdatera det via API.

Aktiviteter som skapats med [!DNL Target] Gränssnittet bör uppdateras via [!DNL Target] Gränssnitt. Aktiviteter som skapas via API ska uppdateras via API. Om du ursprungligen skapade en aktivitet med API:t, till exempel, men sedan redigerar aktiviteten via [!DNL Target] Alla ändringar uppdateras inte. Alla ändringar lagras på serverdelen och kan uppdateras genom att du gör ett annat API-anrop.

Det bästa är att försöka uppdatera aktiviteten med samma metod (UI eller API) som användes för att skapa aktiviteten från början.

## Du ser standardinnehåll.

Se till att din aktivitet är slutförd och har aktiverats.

## Aktiviteten är inte aktiv.

**Validera:** Gå till [!UICONTROL Overview] och se om testet är markerat som inaktivt eller utkast.

**Alternativ:**

* Aktivera test.
* Använd Förhandsgranska länkar om du vill visa ett inaktivt test.

## Ni uppfyller inte villkoren för målgruppsanpassning.

**Validera:** Granska målinriktningsvillkoren på översiktssidan.

**Alternativ:**

* Kvalificera och försök igen.
* Använd Förhandsgranska länkar för att åsidosätta målinriktningsvillkoren.

## Sidan uppfyller inte villkoren för sidanpassning.

**Validera:** På [!UICONTROL Overview] bestämmer du om sidan ligger utanför målvillkoren.

**Alternativ:**

* Gå till [!UICONTROL Visual Experience Composer], klicka på URL > Avancerat > aktuell sida.

## En tidigare upplevelse visas i stället för den nya.

**Validera:** Försök med något av alternativen nedan och försök visa upplevelsen igen.

**Alternativ:**

* Rensa cache och cookies och försök sedan igen.
* Prova en annan webbläsare.
* Använd läget Privat/Inkognito.

## Du har nyligen lagts till i [!DNL Target] men kan inte skapa aktiviteter.

**Validera:** Klicka [!UICONTROL Create Activity]. Om alternativet inte är tillgängligt har du förmodligen inte fått tillräcklig behörighet för att skapa en aktivitet.

**Alternativ:**

När du har lagts till som användare i [!DNL Target]måste du ha [!UICONTROL Approver] roll för att skapa aktiviteter.

* Be administratören för ditt konto att göra dig till godkännare.
* Om du är administratör, ge dig själv [!UICONTROL Approver] roll från **[!UICONTROL Administration]** > **[!UICONTROL Users]** in [!DNL Target].

   Se [Tilldela dig själv rollen Godkännare](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Sidans struktur har ändrats sedan du konfigurerade aktiviteten.

**Validera:** Gå till [!UICONTROL Visual Experience Composer] för den befintliga aktiviteten. Leta efter ett varningsmeddelande som anger att väljarna (eller strukturen) har ändrats.

**Alternativ:**

* Återskapa aktiviteten.

Mer information om hur sidändringar påverkar [!DNL Target]kan visas, se [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Sidans struktur ändras under sidinläsning (vid körning).

**Validera:** Fråga utvecklaren.

**Obs!** För att [!DNL Target] för att ta reda på var aktivitetsändringar ska tillämpas bör du undvika att dynamiskt infoga ett element med samma klass eller dynamiskt ändra klassen för alla objekt på samma nivå.

**Alternativ:**

* Uppdatera sidkod så att varje element som testas identifieras unikt (med ett id).
* Sluta dynamiskt ändra klassen eller jämställda objekt enligt beskrivningen ovan.

Mer information om hur sidändringar påverkar [!DNL Target]kan visas, se [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Andra aktiviteter körs på samma sida.

**Validera:** Använd [!UICONTROL Collisions] för att se om andra aktiviteter körs.

**Obs!** The [!UICONTROL Collisions] Fliken fungerar inte med modulen Malltestning.

**Alternativ:**

* Öka prioriteten för den här aktiviteten.
* Minska prioriteringen för andra aktiviteter.
* Inaktivera andra aktiviteter.

## Ett felmeddelande visas när du tar bort ett profilskript.

**Validera:** Ta bort ett profilskript från [!DNL Target] I visas felmeddelandet&quot;Det gick inte att ta bort profilskriptet&quot;.

**Alternativ:**

Gör något av följande:

* Ta bort profilskriptet igen. Meddelandet om att åtgärden lyckades visas.
* Vänta i ungefär 10 minuter med [!DNL Target] importfunktion. Importverktyget uppdaterar profillistan med skript.

## Lite ajax [!DNL Target] samtal fungerar inte.

**Obs!** Flera ajax [!DNL Target] anrop med samma namn men olika parametrar fungerar inte på samma sida. Endast första anropet görs.

## Du har aktiverat en aktivitet med [!DNL Target] API, men aktiviteten visar status för [!UICONTROL Inactive] i [!DNL Target] Gränssnitt.

När du utför vissa åtgärder, t.ex. aktiverar en aktivitet utanför användargränssnittet, med [!DNL Target] API: uppdateringen kan ta upp till tio minuter att sprida till användargränssnittet.

## Efter aktivitetskonverteringen har besökaren ingen erfarenhet.

Om aktivitetens konverteringsmått för att kvalificera sig för en upplevelse skickas i samma [!DNL Target] begär som aktivitetskvalificering kanske besökaren inte har någon erfarenhet efter att begäran har skickats. I det här fallet ser besökaren standardinnehåll. [!DNL Adobe] rekommenderar att aktivitetskonvertering och -kvalificering inte skickas i samma begäran.

Om du vill skicka båda inställningarna i samma begäran kan du använda [!UICONTROL Advanced Settings] för att ange att besökaren ska behålla samma upplevelse efter konverteringen.
