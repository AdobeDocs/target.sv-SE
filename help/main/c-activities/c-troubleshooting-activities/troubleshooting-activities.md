---
keywords: felsöka mål;felsökningsmål;standardinnehåll;testa inte live;aktivitet inte live;målinriktning inte fungerar;föregående upplevelse visas;kan inte skapa aktiviteter;kan inte skapa aktiviteter;skapa aktiviteter;sidstruktur ändrad;sidstruktur ändrad;felmeddelande;felborttagningsprofilskript;ajax fungerar inte
description: Hitta felsökningsförslag om din Adobe [!DNL Target] aktivitet inte skulle visas på din webbplats.
title: Hur felsöker jag aktiviteter?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 0%

---

# Felsöka aktiviteter

Om din [!DNL Adobe Target]-aktivitet inte visas på din webbplats bör dessa felsökningsförslag hjälpa dig att hitta din lösning.

>[!NOTE]
>
>Förutom följande felsökningsinformation finns det i [Felsökningsmål](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) länkar till ytterligare felsökningsämnen, vanliga frågor och svar samt annan användbar information om felsökningsaktiviteter och andra funktioner i [!DNL Adobe Target].

Följande avsnitt innehåller problem som du kan stöta på när du föreslår lösningar.

## Jag skapade en aktivitet med användargränssnittet för [!DNL Target] och kan inte uppdatera den via API.

Aktiviteter som skapats med användargränssnittet för [!DNL Target] bör uppdateras via användargränssnittet för [!DNL Target]. Aktiviteter som skapas via API ska uppdateras via API. Om du ursprungligen skapade en aktivitet med API, till exempel, men sedan redigerar aktiviteten via användargränssnittet i [!DNL Target], uppdateras inte alla ändringar. Alla ändringar lagras på serverdelen och kan uppdateras genom att du gör ett annat API-anrop.

Det bästa sättet är att försöka uppdatera aktiviteten med samma metod (UI eller API) som användes för att skapa aktiviteten från början.

## Du ser standardinnehåll.

Se till att din aktivitet är slutförd och har aktiverats.

## Aktiviteten är inte aktiv.

**Validera:** Gå till fliken [!UICONTROL Overview] och kontrollera om testet är markerat som inaktivt eller utkast.

**Alternativ:**

* Aktivera test.
* Använd Förhandsgranska länkar om du vill visa ett inaktivt test.

## Ni uppfyller inte villkoren för målgruppsanpassning.

**Verifiera:** Granska målinriktningsvillkoren på översiktssidan.

**Alternativ:**

* Kvalificera och försök igen.
* Använd Förhandsgranska länkar för att åsidosätta målinriktningsvillkoren.

## Sidan uppfyller inte villkoren för sidanpassning.

**Verifiera:** På sidan [!UICONTROL Overview] kontrollerar du om sidan ligger utanför målvillkoren.

**Alternativ:**

* Gå till [!UICONTROL Visual Experience Composer], klicka på URL > Avancerat > aktuell sida.

## En tidigare upplevelse visas i stället för den nya.

**Verifiera:** Försök med något av alternativen nedan och försök visa upplevelsen igen.

**Alternativ:**

* Rensa cache och cookies och försök sedan igen.
* Prova en annan webbläsare.
* Använd läget Privat/Inkognito.

## Du har nyligen lagts till i [!DNL Target] men kan inte skapa aktiviteter.

**Verifiera:** Klicka på [!UICONTROL Create Activity]. Om alternativet inte är tillgängligt har du förmodligen inte fått tillräcklig behörighet för att skapa en aktivitet.

**Alternativ:**

När du har lagts till som användare i [!DNL Target] måste du ha rollen [!UICONTROL Approver] för att kunna skapa aktiviteter.

* Be kontoadministratören att göra dig till godkännare.
* Om du är administratör kan du ge dig själv rollen [!UICONTROL Approver] från **[!UICONTROL Administration]** > **[!UICONTROL Users]** i [!DNL Target].

  Se [Tilldela dig själv rollen Godkännare](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Sidans struktur har ändrats sedan du konfigurerade aktiviteten.

**Verifiera:** Gå till [!UICONTROL Visual Experience Composer] för den befintliga aktiviteten. Leta efter ett varningsmeddelande som anger att väljarna (eller strukturen) har ändrats.

**Alternativ:**

* Återskapa aktiviteten.

Mer information om hur sidändringar påverkar [!DNL Target] möjlighet att visa finns i [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Sidans struktur ändras under sidinläsning (vid körning).

**Verifiera:** Fråga utvecklaren.

**Obs!** För att [!DNL Target] ska kunna identifiera var aktivitetsändringar ska tillämpas bör du undvika att dynamiskt infoga ett element med samma klass eller dynamiskt ändra klassen för alla objekt på samma nivå.

**Alternativ:**

* Uppdatera sidkod så att varje element som testas identifieras unikt (med ett id).
* Sluta dynamiskt ändra klassen eller jämställda objekt enligt beskrivningen ovan.

Mer information om hur sidändringar påverkar [!DNL Target] möjlighet att visa finns i [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Andra aktiviteter körs på samma sida.

**Verifiera:** Använd fliken [!UICONTROL Collisions] för att se om andra aktiviteter körs.

**Obs!** Fliken [!UICONTROL Collisions] fungerar inte med modulen Malltestning.

**Alternativ:**

* Öka prioriteten för den här aktiviteten.
* Minska prioriteringen för andra aktiviteter.
* Inaktivera andra aktiviteter.

## Ett felmeddelande visas när du tar bort ett profilskript.

**Verifiera:** Om du tar bort ett profilskript från [!DNL Target] visas felmeddelandet&quot;Det gick inte att ta bort profilskriptet&quot;.

**Alternativ:**

Gör något av följande:

* Ta bort profilskriptet igen. Meddelandet om att åtgärden lyckades visas.
* Vänta i ungefär 10 minuter innan importeraren [!DNL Target] körs. Importverktyget uppdaterar profillistan med skript.

## Vissa ajax [!DNL Target]-anrop fungerar inte.

**Obs!** Flera ajax [!DNL Target]-anrop med samma namn, men olika parametrar fungerar inte på samma sida. Endast första anropet görs.

## Du har aktiverat en aktivitet med API:t [!DNL Target], men aktiviteten visar statusen [!UICONTROL Inactive] i användargränssnittet för [!DNL Target].

När du utför vissa åtgärder, t.ex. aktiverar en aktivitet utanför användargränssnittet med API:t [!DNL Target], kan det ta upp till tio minuter att sprida uppdateringen till användargränssnittet.

## Efter aktivitetskonverteringen har besökaren ingen erfarenhet.

I sällsynta fall, om aktivitetens konverteringsmått för att kvalificera sig för en upplevelse skickas i samma begäran som en aktivitetskvalifikation, kanske besökaren inte har någon erfarenhet efter att begäran har skickats. I den här situationen ser besökaren att standardinnehålls- och upplevelse-ID som hämtas via tokens blir -1. [!DNL Adobe] rekommenderar inte att aktivitetskvalificering och konvertering skickas i samma [!DNL Target]-begäran.

Om du vill skicka båda måtten i samma begäran kan du använda [!UICONTROL Advanced Settings] för att ange att besökaren ska förbli i samma upplevelse efter konverteringen.
