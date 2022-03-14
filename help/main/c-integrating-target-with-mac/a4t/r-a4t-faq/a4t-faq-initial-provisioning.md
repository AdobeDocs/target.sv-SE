---
keywords: frågor och svar;vanliga frågor;analys för mål;a4t;provisionering;provisionering;adobe Experience Cloud
description: Hitta svar på frågor som ofta ställs om provisionering av Analytics för [!DNL Target] (A4T), som gör att du kan använda analysrapporter för [!DNL Target] verksamhet.
title: Var hittar jag information om inledande A4T-etablering?
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Inledande etablering - Vanliga frågor om A4T

Det här avsnittet innehåller svar på frågor som ofta ställs om etablering [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Hur skapar jag en A4T-aktivitet på flera sidor?

Så här implementerar du ett enkelt A4T-fall med flera sidor:

* Implementera JavaScript-biblioteken för både Target och Analytics på aktivitetens landnings-URL/-sida. Genom att implementera båda lösningarna kombineras Target-data med Analytics-data för varje besökare. Dessa data finns kvar i Analytics tills de upphör att gälla med standardinställningen 90 dagar.

* För de återstående sidorna på webbplatsen, där bara analysstatistik ska spåras, implementera Analytics på dessa sidor. Target behöver inte implementeras på dessa sidor. De analysvärden som samlas in på dessa sidor sammanfogas automatiskt med den Target-aktivitet som användaren ursprungligen var kvalificerad för, baserat på den Target-information som bifogas besökaren från den föregående punkten.

## Hur vet jag om A4T är aktiverat på [!DNL Target] konto? {#section_4437D284448F4313BF953D4B6EDBACA6}

Innan du kan välja en rapportsserie när du definierar en Analytics-aktivitet behöver du både ett Analytics-användarkonto och ett Target-användarkonto. Dina användarkonton måste konfigureras enligt anvisningarna i dokumentationen. Se [Krav för användarbehörighet](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

När du är medlem i en eller flera Experience Cloud-grupper som har tillgång till Analytics och Target och har tillgång till alla rapportsviter, bör du se alternativet att skapa ett A/B-test med Analytics under **[!UICONTROL Create Activity]**.

Om det uppstår provisioneringsproblem ska du kontrollera om A4T har etablerats korrekt.

## Varför läses inte mina rapportsviter in? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

Kontrollera följande om något av dessa problem uppstår:

* Se till att era Analytics- och Target-konton är länkade i Experience Cloud.
* Vissa kunder använder flera företagsinloggningar från Analytics i samma Experience Cloud-företag. Om du använder flera inloggningar måste du se till att det sista Analytics-företaget du loggade in på är det som är knutet till Target-kontot för integreringen.
* Om du har varit inloggad på Experience Cloud i flera timmar kan Analytics-sessionen ibland upphöra. Logga ut och logga in igen för att försöka igen.

## Varför ser jag inte Analytics-alternativen i Target? {#section_EDD996AFB08B4DB196DD934BE55BF48D}

Se&quot;Varför laddas inte mina rapportsviter?&quot; Ovanför. Orsaken till det här problemet är densamma.

## Varför ser jag inte A4T-rapporter i Analytics? {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

Se&quot;Varför laddas inte mina rapportsviter?&quot; ovan. Orsaken till det här problemet är densamma.

## Varför är mina rapporter i [!DNL Target] tom? {#section_3837104757464CB488C5A83014A669A1}

Se&quot;Varför laddas inte mina rapportsviter?&quot; ovan. Orsaken till det här problemet är densamma.
