---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: Det här avsnittet innehåller svar på frågor som ofta ställs om klassificeringar och hur Analytics används som rapportkälla för Target (A4T).
title: Klassificeringar - A4T - vanliga frågor och svar
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Klassificeringar - A4T - vanliga frågor och svar{#classifications-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om klassificeringar och hur Analytics används som rapportkälla för Target (A4T).

## Hur matchar jag värdet efter åtgärd med ett aktivitetsnamn när jag har hämtat klassificeringar med hjälp av Klassificeringsimporteraren? {#section_6045DAC488B248418F430E663C38D001}

Du kan hämta klassificeringarna för A4T/TNT-strängen från Admin Tools [Classification Importer](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html). Variabeln kallas&quot;TNT&quot; i exportlistan. De hämtade data innehåller egna namn för aktiviteter, upplevelser och så vidare.

Den här sökfilen är användbar för kunder som tar emot Adobes dataflöde för klickströmmar. Filen innehåller egna namn för kolumnerna `post_tnt` och `post_tnt_action` .

TNT-variabelns strängformat är `activityID:experienceID:targettype|event`.

* targetType är alltid 0 för A4T.
* Händelse = 0 representerar en upplevelseingång.
* Händelse = 1 representerar ett upplevelsebesök.
* Händelse = 2 representerar ett aktivitetsintryck.
* Händelse = 32767 representerar en aktivitetskonvertering.

Du kan importera klassificeringsfilen ofta från användargränssnittet med en [webbläsarimport](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) eller en [FTP-import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). Du kan också använda Engineering Services för att hämta filen som en uppslagstabell tillsammans med en datafeed i klickströmmen.
