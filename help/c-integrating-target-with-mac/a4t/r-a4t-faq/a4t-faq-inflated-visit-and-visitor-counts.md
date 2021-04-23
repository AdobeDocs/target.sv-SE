---
keywords: vanliga frågor;vanliga frågor;analys för mål;a4T;inflated;besök;besökare;delvis träffad;överbliven;överbliven;delvis träffad
description: Hitta svar på frågor om ökat antal besökare och besökare när du använder Analytics for [!DNL Target] (A4T). Lär dig att minimera"partiella data".
title: Var hittar jag frågor om uppblåsta besök och besöksräkningar med A4T?
feature: Analyser för mål (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Uppblåst besök och besökarantal - A4T - vanliga frågor

Det här avsnittet innehåller svar på frågor som ofta ställs om uppblåst besöks- och besökarantal när Analytics används som rapportkälla för Target (A4T).

## Varför visar mina analysdata besök som inte har några sidvisningar eller andra variabelvärden? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

När [!DNL Adobe Analytics] används för att mäta [!DNL Target]-aktiviteter (kallas A4T), samlar [!DNL Analytics] in data som inte är tillgängliga när det inte finns någon [!DNL Target]-aktivitet på sidan. Detta beror på att aktiviteten [!DNL Target] utlöser ett anrop längst upp på sidan, men [!DNL Analytics] utlöser vanligtvis sina datainsamlingsanrop längst ned på sidan. I implementeringen av A4T hittills inkluderar Adobe dessa ytterligare data när en [!DNL Target]-aktivitet var aktiv.

Mer information finns i [Minimera antal uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Vad är en partiell dataträff? {#section_59A203E289564576BF6821F96B0B9E11}

En partiell dataträffar inträffar när en [!DNL Target]-tagg längst upp på sidan utlöses men en [!DNL Analytics]-tagg längst ned på sidan inte utlöses. Det finns olika skäl till att denna situation uppstår. I [!DNL A4T]-implementeringen hittills inkluderar Adobe partiella data om dessa träffar när en [!DNL Target]-aktivitet var aktiv. Framöver kommer Adobe endast att inkludera dessa ytterligare data när både [!DNL Target]- och [!DNL Analytics]-taggarna har utlösts.

Mer information finns i [Minimera antal uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Jag ser en topp i besök. Hur vet jag om de här besöken orsakas av partiella dataträffar? {#section_28506672C6224ED18AC74F6A02F6F811}

Du kan kontakta [Adobe kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att hämta en rapport om partiella data. Den här informationen är inte tillgänglig direkt i användargränssnittet för [!DNL Analytics].

## Vilka är de potentiella orsakerna till deldataträffar? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Deldataträffar är ofta ett resultat av felaktig implementering, t.ex. felanpassade ID:n för rapportsviter. Det finns också befogade orsaker, som långsamma sidor, sidfel, omdirigeringserbjudanden i en aktivitet eller föråldrade biblioteksversioner.

Mer information finns i&quot;What Contributes to Partial Data&quot; i [Minimera antal uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Jag har deldataträffar. Vad kan jag göra för att rensa upp mina data? {#section_CBE778A9D07A469E8FF98F68BACC7124}

Du kan skapa ett virtuellt rapportpaket för att exkludera historiska partiella data från dina rapporter.

Mer information finns i&quot;Hur kan jag visa historiska trender utan partiella data?&quot; i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Finns det något jag kan göra för att förhindra att mina sidor genererar träffar på delar av data? {#section_4B00E7E618444BE98A0798DE98F08B21}

Efter 14 november 2016 kommer Adobe endast att inkludera data när både [!DNL Target]- och [!DNL Analytics]-taggarna har utlösts. Den här ändringen är inte retroaktiv. Om dina historiska rapporter visar inflaterade räkningar kan du utesluta dem från dina rapporter genom att skapa en virtuell rapportserie. Se&quot;Hur kan jag visa historiska trender utan partiella data?&quot; i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Det finns också steg som du kan utföra för att minimera träffar med delar av data. Mer information finns i&quot;Vilka är de bästa sätten att minska partiella data?&quot; i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Om data som träffar delvis på data tas bort från rapporteringen, förlorar jag då inte värdefulla [!DNL Target]- eller Analytics-data? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

Att inkludera partiella data i [!DNL Analytics]-rapportering ger ytterligare information, men skapar också inkonsekvens med historiska data från perioder när det inte fanns några [!DNL Target]-aktiviteter som kördes. Att inkludera data med partiella träffar kan orsaka problem för [!DNL Analytics]-användare som analyserar trender över tid.

Det finns steg som du kan utföra för att minimera träffar med delar av data. Mer information finns i&quot;Vilka är de bästa sätten att minska partiella data?&quot; i [Minimera antalet uppblåsta besök och besökare i A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Finns det några särskilda typer av [!DNL Target]-aktiviteter som är mer benägna att orsaka partiella dataträffar? {#section_69837442A9B84366BEFDA4588B31E574}

Omdirigeringserbjudanden skickar omedelbart en användare till en annan sida, vilket innebär att [!DNL Analytics]-anropet inte utlöses på den första sidan.
