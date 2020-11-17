---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: Det här avsnittet innehåller svar på frågor som ofta ställs om aktivitetsinställningar och hur Analytics används som rapportkälla för Target (A4T).
title: Aktivitetsinställningar - vanliga A4T-frågor
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 208196b8c0cf11367ad37121c4792a015b396dc7
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 0%

---


# Aktivitetsinställningar - vanliga A4T-frågor

Det här avsnittet innehåller svar på frågor som ofta ställs om aktivitetsinställningar och som används [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

## Vilka aktivitetstyper stöder Analytics som rapportkälla (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

En fullständig lista finns i&quot;Aktivitetstyper som stöds&quot; i [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Jag har just skapat en aktivitet. Varför ser jag inga data som kommer in? {#section_9F8092BE4225442896F926540292F221}

När en aktivitet skapas skickar en klassificeringsfil till [!DNL Target] [!DNL Analytics]. Även om [!DNL Analytics] hämtar in och bearbetar data visas de inte i rapporterna förrän klassificeringsfilen har uppdaterats. Detta kan ta upp till 24 timmar. Om du inte ser dina data inom 48 timmar kan du [kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Om du vet att du kommer att starta en aktivitet kan du skapa aktiviteten några dagar i förväg och klassificeringarna skickas när aktiviteten sparas. På så sätt visas data i rapporterna när programmet startas. Observera att det tar 45-90 minuter för data att behandlas i [!DNL Analytics].

## Varför kan jag inte välja Analytics som rapportkälla när jag skapar en ny aktivitet? {#section_9F4F69C3085F4C2480AF439127EB27CD}

Du kan ändra dina [!UICONTROL Reporting Settings] alternativ i [!UICONTROL Administration].

1. Klicka [!DNL Target]i **[!UICONTROL Administration]**.
1. In the **[!UICONTROL Experience Cloud solution used for reporting]** drop-down list, click **[!UICONTROL Select per Activity]**.

![](assets/select-per-activity.png)

Listrutan **[!UICONTROL Reporting Source]** aktiveras på **[!UICONTROL Goal & Settings]** skärmen för att skapa och redigera aktiviteter.

Om du alltid vill använda [!DNL Analytics] som rapportkälla väljer du **[!UICONTROL Adobe Analytics]** i listrutan i [!UICONTROL Administration].

## Kan en besökare växla mellan målinriktade och kontrollerade upplevelser vid olika besök i en Auto-Target-aktivitet som använder A4T?

Följande är sant om besökarId inte ändras för en besökare mellan besök.

Om trafikallokeringsprocenten justeras efter mellanaktiviteten är det möjligt att en besökare kan gå mellan målinriktade upplevelser och kontrollupplevelser.

Om procentsatserna inte justeras efter medelaktiviteten skickas alltid en besökare som från början ser kontrollen till kontrollen. En besökare som skickas till målinriktade upplevelser skickas alltid till målinriktade upplevelser.

* Efter att ha befunnit sig i trafikens avsedda&quot;bucket&quot; kan besökaren få en annan upplevelse vid besök om maskininlärningsmodellerna visar att en annan upplevelse är relevant för det nya besöket.
* Efter att ha tilldelats kontrollens&quot;bucket&quot; för trafik, kommer en besökare alltid att se samma upplevelse eftersom upplevelsetilldelningen baseras på en deterministisk pseudoslumpmässig hash av besökarens visitorId.

## Rekommenderas det att vi använder den anpassade modellen för Automatiskt mål och A4T med en delning av 90 (Kontroll)/10 (Mål) tills modellerna byggs?

Din optimala trafikallokeringsdelning beror på vad du vill uppnå.

Om målet är att personalisera så mycket trafik som möjligt kan ni hålla er till 90 % målinriktning och 10 % kontroll över aktivitetens livstid. Om målet är att köra ett experiment där man jämför hur väl personaliserade algoritmer fungerar jämfört med kontrollen är en delning på 50/50 bäst.

