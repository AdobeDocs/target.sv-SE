---
keywords: Rekommendationer;Inställningar;namn;mål;prioritet;varaktighet;rapporteringsinställningar;andra metadata
description: Lär dig hur du konfigurerar inställningarna som används för att beskriva och styra en rekommendationsaktivitet i Adobe Target.
title: Hur konfigurerar jag aktivitetsinställningar för rekommendationer?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 0%

---

# Inställningar för aktiviteten Rekommendationer

Information om de inställningar du kan använda för att beskriva och kontrollera en [!UICONTROL Recommendations]-aktivitet i [!DNL Adobe Target].

I följande avsnitt beskrivs de tillgängliga inställningarna för en [!UICONTROL Recommendations]-aktivitet.

## Namn

Klicka på ikonen Fler åtgärder ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmallListVert.svg) ) och klicka sedan på **[!UICONTROL Rename]** för att ange ett beskrivande namn som hjälper dig och ditt team att identifiera aktiviteten.

Följande tecken tillåts inte i aktivitetsnamn:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

Om du anger ett [!UICONTROL Recommendations]-aktivitetsnamn som redan finns för en annan aktivitet i [!UICONTROL Recommendations Classic] synkroniseras den nya aktiviteten igen med ett nytt namn. Det nya namnet är det ursprungliga namnet som har lagts till med en tidsstämpel för att göra det unikt. Det nya namnet visas både i [!DNL Target Standard/Premium] och [!UICONTROL Recommendations Classic].

## Syfte

(Valfritt) Beskriv aktivitetens mål.

## Prioritet

Ange prioritetsnivån genom att justera skjutreglaget.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.

## Varaktighet

Ange aktivitetens varaktighet.

Aktiviteten kan starta när den är aktiverad eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmars klocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## Rapportinställningar

* **Rapporterar Source:** Ange vilka lösningsdata som ska samlas in från:

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  Om en rapporteringslösning anges i dina [kontoinställningar](/help/main/administrating-target/reporting.md) används den angivna lösningen och den här inställningen syns inte.

  Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa.

  **[!DNL Adobe Analytics]**: Se [[!DNL Adobe Analytics]  som rapportkälla för  [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) om du vill veta mer om skillnaderna mellan rapporteringslösningarna och fördelarna med varje.

  När du väljer [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T) väljer du en [!DNL Analytics] rapportsvit som ska ta emot [!DNL Target] aktivitetsdata. För att göra detta väljer du först något av de [!DNL Analytics] företag som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till [!DNL Target] är tillgängliga för urval. Om du inte ser den rapportserie du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen. Om rapportsviten fortfarande saknas i listan kontaktar du [kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

  [!DNL Analytics for Target] (A4T) kräver en spårningsserver för att rapportera resultaten korrekt. En standardspårningsserver visas i fältet [!UICONTROL Tracking Server]. Om du använder mer än en spårningsserver måste du ta med rätt spårningsserver i det här fältet. Mer information finns i [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

  **[!DNL Adobe Customer Journey Analytics]**: Mer information om integrationen mellan [[!DNL Target]  och  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) finns i [!DNL Adobe Customer Journey Analytics]Rapportera i [!DNL Target].

* **Målmått:** Välj det framgångsmått som avgör om aktiviteten lyckas eller inte.
* **Ytterligare mått:** Konfigurera ytterligare framgångsmått som ska användas i dina rapporter.
* **Publiker för rapportering:** Definiera målgrupper som kan användas för att filtrera rapporter.

## Andra metadata

Skriv anteckningar om din aktivitet.

## Utbildningsvideo: Aktivitetsinställningar (3:02) ![Självstudiekurs &#x200B;](/help/main/assets/tutorial.png)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)
