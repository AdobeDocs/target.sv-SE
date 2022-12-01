---
keywords: frågor och svar;vanliga frågor;analys för mål;a4T;aktivitetsinställning
description: Hitta svar på frågor om aktivitetskonfiguration när du använder Analytics för [!DNL Target] (A4T). Med A4T kan ni använda analysrapporter för [!DNL Target] verksamhet.
title: Var hittar jag frågor och svar om aktivitetsinställningar med A4T?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: ed4fadc338bf5a1afad87e2b245a9b00e225b92c
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---

# Aktivitetsinställningar - vanliga A4T-frågor

Det här avsnittet innehåller svar på frågor som ofta ställs om aktivitetsinställningar och användning [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

## Vilka aktivitetstyper stöder Analytics som rapportkälla (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++Svar En fullständig lista finns i&quot;Aktivitetstyper som stöds&quot; i [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## Varför har jag inte åtkomst till Avancerade inställningar när jag konfigurerar mina målvärden?

+++Besvara aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T) använder målmåttet &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; och &quot;[!UICONTROL On Every Impression]&quot;. Dessa inställningar *not* kan konfigureras.

Mer information finns i&quot;När jag konfigurerar mina målmått, varför kan jag inte komma åt alternativen för Avancerade inställningar?&quot; in [Måttdefinitioner - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Jag har just skapat en aktivitet. Varför ser jag inga data som kommer in? {#section_9F8092BE4225442896F926540292F221}


+++Svar När en aktivitet skapas, [!DNL Target] skickar en klassificeringsfil till [!DNL Analytics]. Fast [!DNL Analytics] hämtar in och bearbetar data, visar det inte i rapporterna förrän klassificeringsfilen har uppdaterats. Denna process kan ta upp till 24 timmar. Om du inte ser dina data inom 48 timmar kan du [kontakta kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Om du vet att du startar en aktivitet kan du skapa aktiviteten några dagar i förväg och klassificeringarna skickas när aktiviteten sparas. På så sätt visas data i rapporterna när programmet startas. Observera att det tar 45-90 minuter för data att behandlas i [!DNL Analytics].

+++

## Varför kan jag inte välja Analytics som rapportkälla när jag skapar en aktivitet? {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++Svar Du kan ändra [!UICONTROL Reporting Settings] alternativ i [!UICONTROL Administration].

1. I [!DNL Target], klicka **[!UICONTROL Administration]**.
1. I **[!UICONTROL Experience Cloud solution used for reporting]** nedrullningsbar lista, klicka **[!UICONTROL Select per Activity]**.

![bild per aktivitet](assets/select-per-activity.png)

The **[!UICONTROL Reporting Source]** nedrullningsbar lista är aktiverad i **[!UICONTROL Goal & Settings]** för att skapa och redigera aktiviteter.

Att alltid använda [!DNL Analytics] som rapportkälla, välj **[!UICONTROL Adobe Analytics]** från listrutan i [!UICONTROL Administration].

+++

## Kan en besökare växla mellan målinriktade och kontrollerade upplevelser vid olika besök i en Auto-Target-aktivitet som använder A4T?

+++Svar Följande gäller om besökar-ID inte ändras för en besökare mellan besök.

Om procentandelen för trafikallokering justeras efter mellanaktiviteten är det möjligt att en besökare kan gå mellan målinriktade upplevelser och kontrollupplevelser.

Om procentsatserna inte justeras efter medelaktiviteten skickas alltid en besökare som från början ser kontrollen till kontrollen. En besökare som skickas till målinriktade upplevelser skickas alltid till målinriktade upplevelser.

* Efter att ha befunnit sig i trafikens avsedda&quot;bucket&quot; kan besökaren få en annan upplevelse vid besök om maskininlärningsmodellerna visar att en annan upplevelse är relevant för det nya besöket.
* Efter att ha tilldelats kontrollens&quot;bucket&quot; för trafik, kommer en besökare alltid att se samma upplevelse eftersom upplevelsetilldelningen baseras på en deterministisk pseudoslumpmässig hash av besökarens visitorId.

+++

## Kan jag använda en binomial [!DNL Analytics] mätvärden med ett segment tillämpat som optimeringsmål i ett [!UICONTROL Auto-Allocate] aktivitet? {#binomial}

+++Svar Du kan inte använda en [!DNL Analytics] mätvärden med ett segment tillämpat som optimeringsmål i ett [!UICONTROL Auto-Allocate] aktivitet. Som en tillfällig lösning kan du definiera en anpassad händelse som uppnår samma mål och använder det som optimeringsmålmåttet.

+++