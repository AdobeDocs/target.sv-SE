---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;klassificeringar;klassificering;klassificeringsimportör;post-action;händelsekoder
description: Hitta svar på frågor om klassificeringar och användning av [!UICONTROL Analytics for Target] (A4T).
title: Var hittar jag information om klassificeringar med A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Klassificeringar - A4T - vanliga frågor

Det här avsnittet innehåller svar på frågor som ofta ställs om klassificeringar och som använder [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

## När jag har använt [!UICONTROL Classifications Importer] för att hämta klassificeringar, hur matchar jag värdet efter åtgärd med ett aktivitetsnamn? {#section_6045DAC488B248418F430E663C38D001}

+++Svar
Du kan hämta klassificeringarna för A4T/TNT-strängen från Admin Tools [Classification Importer](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html?lang=sv-SE). Variabeln kallas&quot;TNT&quot; i exportlistan. De hämtade data innehåller egna namn för aktiviteter, upplevelser och så vidare.

Den här sökfilen är användbar för kunder som tar emot dataflödet från [!DNL Adobe]. Filen innehåller egna namn för kolumnerna `post_tnt` och `post_tnt_action`.

För standardaktiviteter i [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) är formatet för TNT-strängen:

```
activityID:experienceID:targettype|event
```

För [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter är formatet för TNT-strängen:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` och `algorithmId` är interna identifierare som används av [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter.
* Händelse = 0 representerar en upplevelseingång.
* Händelse = 1 representerar ett upplevelsebesök.
* Händelse = 2 representerar ett aktivitetsintryck.
* Händelse = 3-32766 representerar mått för lyckade analysresultat.
* Händelse = 32767 representerar en aktivitetskonvertering.
* Händelsen -1 eller 65535 representerar att användaren tas bort från aktiviteten eller upplevelsen. Detta inträffar ofta när besökaren konverterar. Besökaren frigörs från upplevelsen och är nu tillgänglig för att kvalificera sig för andra upplevelser.

Du kan importera klassificeringsfilen ofta från gränssnittet med hjälp av en [webbläsarimport](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=sv-SE) eller en [FTP-import](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=sv-SE). Du kan också använda Engineering Services för att hämta filen som en uppslagstabell tillsammans med en datafeed i klickströmmen.

+++
