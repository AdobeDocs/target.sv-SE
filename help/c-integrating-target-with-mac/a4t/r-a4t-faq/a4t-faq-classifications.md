---
keywords: frågor och svar;vanliga frågor;analyser för mål;a4T;klassificeringar;klassificering;klassificeringsimportör;efterhandsåtgärd
description: Hitta svar på frågor om klassificeringar och användning av Analytics för [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] aktiviteter.
title: Var hittar jag information om klassificeringar med A4T?
feature: Analyser för mål (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: cdb79c82fe1e7158a2f2014df661bd6fa852df92
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 0%

---

# Klassificeringar - A4T - vanliga frågor och svar

Det här avsnittet innehåller svar på frågor som ofta ställs om klassificeringar och som använder [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

## Hur matchar jag värdet efter åtgärd med ett aktivitetsnamn när jag har hämtat klassificeringar med hjälp av Klassificeringsimporteraren? {#section_6045DAC488B248418F430E663C38D001}

Du kan hämta klassificeringarna för A4T/TNT-strängen från Admin Tools [Klassificeringsimporteraren](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). Variabeln kallas&quot;TNT&quot; i exportlistan. De hämtade data innehåller egna namn för aktiviteter, upplevelser och så vidare.

Den här uppslagsfilen är användbar för kunder som tar emot dataflöde från Adobe clickstream. Filen innehåller egna namn för kolumnerna `post_tnt` och `post_tnt_action`.

TNT-variabelns strängformat är `activityID:experienceID:targettype|event`.

* måltyp = 0 (kontroll/slumpmässig) eller 1 (mål) för [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter.
* Händelse = 0 representerar en upplevelseingång.
* Händelse = 1 representerar ett upplevelsebesök.
* Händelse = 2 representerar ett aktivitetsintryck.
* Händelse = 3-32766 representerar mått för lyckade analysresultat.
* Händelse = 32767 representerar en aktivitetskonvertering.
* Händelsen -1 eller 65535 representerar att användaren tas bort från aktiviteten eller upplevelsen. Detta inträffar ofta när besökaren konverterar. Besökaren frigörs från upplevelsen och är nu tillgänglig för att kvalificera sig för andra upplevelser.

Du kan importera klassificeringsfilen ofta från användargränssnittet med en [webbläsarimport](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) eller en [FTP-import](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). Du kan också använda Engineering Services för att hämta filen som en uppslagstabell tillsammans med en datafeed i klickströmmen.
