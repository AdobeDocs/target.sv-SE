---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: Det här avsnittet innehåller svar på frågor som ofta ställs om aktivitetsinställningar och hur Analytics används som rapportkälla för Target (A4T).
title: Aktivitetsinställningar - vanliga A4T-frågor
topic: Standard
uuid: 3472ab3c-908b-40f8-81a6-512dccde64a6
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Aktivitetsinställningar - vanliga A4T-frågor{#activity-settings-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om aktivitetsinställningar och hur Analytics används som rapportkälla för Target (A4T).

## Vilka aktivitetstyper stöder Analytics som rapportkälla (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

En fullständig lista finns i&quot;Aktivitetstyper som stöds&quot; i [Adobe Analytics som rapportkälla för Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Jag har just skapat en aktivitet. Varför ser jag inga data som kommer in? {#section_9F8092BE4225442896F926540292F221}

När en aktivitet skapas skickar Target en klassificeringsfil till Analytics. Även om Analytics hämtar in och bearbetar data, visas de inte i rapporterna förrän klassificeringsfilen har uppdaterats. Detta kan ta upp till 24 timmar. Om du inte ser dina data inom 48 timmar kan du [kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Om du vet att du kommer att starta en aktivitet kan du skapa aktiviteten några dagar i förväg och klassificeringarna skickas när aktiviteten sparas. På så sätt visas data i rapporterna när programmet startas. Observera att det tar 45-90 minuter för data att behandlas i Analytics.

## Varför kan jag inte välja Analytics som rapportkälla när jag skapar en ny aktivitet? {#section_9F4F69C3085F4C2480AF439127EB27CD}

Du kan ändra dina alternativ för Rapporteringsinställningar under Konfigurera.

1. Klicka på i Adobe Target **[!UICONTROL Setup]**.
1. In the **[!UICONTROL Experience Cloud solution used for reporting]** drop-down list, click **[!UICONTROL Select per Activity]**.

![](assets/select-per-activity.png)

Listrutan **[!UICONTROL Reporting Source]** aktiveras på **[!UICONTROL Goal & Settings]** skärmen för att skapa och redigera aktiviteter.

Om du alltid vill använda Analytics som rapportkälla väljer du **[!UICONTROL Adobe Analytics]** i listrutan i Konfigurera.
