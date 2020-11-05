---
keywords: faq;frequently asked questions;analytics for target;a4T;inflated;visit;visitor;partial hit;orphaned;orphan;partial-hit
description: Det här avsnittet innehåller svar på frågor som ofta ställs om uppblåst besöks- och besökarantal när Analytics används som rapportkälla för Target (A4T).
title: Uppblåst besök och besökarantal - A4T - vanliga frågor
feature: a4t troubleshooting
topic: Standard
uuid: 5d1b77bb-9053-4533-bd01-d6f53f0751e9
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---


# Uppblåst besök och besökarantal - A4T - vanliga frågor{#inflated-visit-and-visitor-counts-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om uppblåst besöks- och besökarantal när Analytics används som rapportkälla för Target (A4T).

## Varför visar mina analysdata besök som inte har några sidvisningar eller andra variabelvärden? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

När [!DNL Adobe Analytics] används för att mäta [!DNL Target] aktiviteter (kallas A4T), [!DNL Analytics] samlar in ytterligare data som inte är tillgängliga när det inte finns någon [!DNL Target] aktivitet på sidan. Detta beror på att [!DNL Target] aktiviteten utlöser ett anrop längst upp på sidan, men [!DNL Analytics] oftast utlöses anrop till datainsamlingen längst ned på sidan. I implementeringen av A4T hittills har vi tagit med dessa ytterligare data när en [!DNL Target] aktivitet var aktiv.

Mer information finns i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Vad är en partiell dataträff? {#section_59A203E289564576BF6821F96B0B9E11}

En delvis dataträffa inträffar när en tagg [!DNL Target] högst upp på sidan utlöses men en [!DNL Analytics] tagg längst ned på sidan inte utlöses. Det finns olika skäl till att detta händer. I dagens [!DNL A4T] implementering har vi tagit med delvisa data om dessa träffar när en [!DNL Target] aktivitet var aktiv. Framöver kommer vi endast att inkludera dessa ytterligare data när både [!DNL Target] - och [!DNL Analytics] -taggarna har utlösts.

Mer information finns i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Jag ser en topp i besök. Hur vet jag om de har orsakats av deldataträffar? {#section_28506672C6224ED18AC74F6A02F6F811}

Du kan kontakta [Adobe kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att hämta en rapport om partiella data. Den här informationen är inte tillgänglig direkt i [!DNL Analytics] användargränssnittet.

## Vilka är de potentiella orsakerna till deldataträffar? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Deldataträffar är ofta ett resultat av felaktig implementering, t.ex. felanpassade ID:n för rapportsviter. Det finns också befogade orsaker, som långsamma sidor, sidfel, omdirigeringserbjudanden i en aktivitet eller föråldrade biblioteksversioner.

Mer information finns i&quot;What Contributes to Partial Data&quot; (Vad bidrar till partiella data) i [Minimera antalet uppblåsta besök och besökarantal i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Jag har deldataträffar. Vad kan jag göra för att rensa upp mina data? {#section_CBE778A9D07A469E8FF98F68BACC7124}

Du kan skapa ett virtuellt rapportpaket för att exkludera historiska partiella data från dina rapporter.

Mer information finns i&quot;Hur kan jag visa historiska trender utan partiella data?&quot; in [Minimizing Inflated Visit and Visitor Counts in A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Finns det något jag kan göra för att förhindra att mina sidor genererar träffar på delar av data? {#section_4B00E7E618444BE98A0798DE98F08B21}

Efter 14 november 2016 inkluderas data endast när både [!DNL Target] - och [!DNL Analytics] -taggarna har aktiverats. Den här ändringen är inte retroaktiv. Om dina historiska rapporter visar inflaterade räkningar, och du vill utesluta dem från dina rapporter, kan du skapa en virtuell rapportsvit, enligt beskrivningen i&quot;Hur kan jag visa historiska trender utan partiella data?&quot; in [Minimizing Inflated Visit and Visitor Counts in A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Det finns också steg som du kan utföra för att minimera träffar med delar av data. Mer information finns i&quot;Vilka är de bästa sätten att minska partiella data?&quot; in [Minimizing Inflated Visit and Visitor Counts in A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Om data som träffar delvis på data tas bort från rapporter, kommer vi då inte att förlora värdefulla Target- eller Analytics-data? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

Att inkludera partiella data i [!DNL Analytics] rapporteringen ger ytterligare information, men skapar också inkonsekvens med historiska data från perioder när det inte fanns några [!DNL Target] aktiviteter som kördes. Detta kan orsaka problem för [!DNL Analytics] användare som analyserar trender över tid.

Det finns steg som du kan utföra för att minimera träffar med delar av data. Mer information finns i&quot;Vilka är de bästa sätten att minska partiella data?&quot; in [Minimizing Inflated Visit and Visitor Counts in A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Finns det några särskilda typer av Target-aktiviteter som oftare orsakar partiella dataträffar? {#section_69837442A9B84366BEFDA4588B31E574}

Omdirigeringserbjudandena skickar omedelbart en användare till en annan sida, vilket innebär att anropet inte [!DNL Analytics] utlöses på den första sidan.
