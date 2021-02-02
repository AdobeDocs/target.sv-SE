---
keywords: Recommendations;Inställningar;namn;mål;prioritet;varaktighet;rapporteringsinställningar;andra metadata
description: Flera inställningar kan användas för att beskriva och styra en Recommendations-aktivitet i Adobe Target.
title: Inställningar för Recommendations-aktivitet
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---


# ![Inställningar för ](/help/assets/premium.png) PREMIUMRecommendations-aktivitet{#recommendations-activity-settings}

Information om de inställningar du kan använda för att beskriva och styra en [!UICONTROL Recommendations]-aktivitet i [!DNL Adobe Target].

![Recommendations Goals &amp; Settings page](/help/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

I följande avsnitt beskrivs de tillgängliga inställningarna för en [!UICONTROL Recommendations]-aktivitet.

## Namn

Ange ett beskrivande namn som hjälper dig och ditt team att identifiera aktiviteten.

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

Aktiviteten kan starta när den är aktiverad eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmarsklocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## Rapportinställningar

* **Rapporteringskälla:** Välj rapportkälla:  [!DNL Adobe Target] eller  [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). Ändra inte rapportkällan efter att aktiviteten har publicerats. Om du ändrar rapportkällan efter att en aktivitet har publicerats blir rapporteringen inkonsekvent.
* **Målmått:** Välj ett framgångsmått som avgör om aktiviteten lyckas eller inte.
* **Ytterligare mått:** Konfigurera ytterligare framgångsmått som ska användas i dina rapporter.
* **Målgrupper för rapportering:** Definiera målgrupper som kan användas när du filtrerar rapporter.

## Andra metadata

Skriv anteckningar om din aktivitet.

## Utbildningsvideo: Aktivitetsinställningar (3:02) ![Tutorial badge](/help/assets/tutorial.png)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)