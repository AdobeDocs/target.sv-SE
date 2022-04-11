---
keywords: målgrupp;målgruppsregler;kombinera målgrupper;exkludering;exkludera;kombinera målgrupper;ad hoc-målgrupper;ad hoc-målgrupper
description: Lär dig kombinera olika målgrupper (inklusive Adobe Experience Cloud-målgrupper och [!DNL Target] målgrupper) i farten för att skapa ad hoc-målgrupper.
title: Kan jag kombinera flera olika målgrupper för att skapa en ny målgrupp?
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
source-git-commit: 866455ac115b6797b5f103cdf1ae10c8a68f7234
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---

# Kombinera flera målgrupper

Kombinera olika målgrupper (inklusive [!DNL Adobe Experience Cloud], [!DNL Adobe Experience Platform]och [!DNL Target] målgrupper) i farten för att skapa ad hoc-målgrupper. Du kan också skapa exkluderingsregler och exkludera målgrupper från en regel.

>[!NOTE]
>
>The [!DNL Adobe Experience Platform] källan är tillgänglig för alla [!DNL Target] kunder som använder [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Publiker som finns på [!DNL Adobe Experience Platform] kan användas som det är eller kombineras med befintliga målgrupper, vilket förklaras i detta avsnitt.
>
>Mer information finns i [Använda målgrupper från Adobe Experience Platform](/help/main/c-target/c-audiences/audiences.md#aep).

Anta att du har en&quot;New Visitors&quot;-målgrupp och en&quot;Chrome Users&quot;-målgrupp. För en viss aktivitet kanske du vill kombinera dessa befintliga målgrupper för att rikta in dig på nya besökare med Chrome-webbläsare. Istället för att skapa en tredje målgrupp och lagra den i [!UICONTROL Audiences] kan du kombinera dessa två målgrupper när du skapar en aktivitet eller när du redigerar en befintlig aktivitet.

Som ett annat exempel kan ni inrikta er på alla lojalitetskunder. Du kan till exempel inkludera en viss [!DNL Audience Manager] målgrupp för lojalitetsstatus och kombinera dem med [!DNL Target] målgrupp bestående av personer som har anmält sig till ditt lojalitetsprogram under den aktuella sessionen. Det är enklare att kombinera dessa båda målgrupper än att skapa en tredje permanent målgrupp.

Du kan kombinera upp till 20 målgrupper med operatorerna AND och OR.

Du kan skapa och använda kombinerade målgrupper på olika platser i [!DNL Target] Gränssnitt.

## Skapa en kombinerad målgrupp när du skapar en aktivitet {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

Du kan skapa en ad hoc-målgrupp för aktivitetens [!UICONTROL Target] under det guidade arbetsflödet i tre steg.

1. När en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), på **[!UICONTROL Targeting]** klickar du på de tre lodräta ellipserna och sedan på **[!UICONTROL Replace Audience]**.

   ![Stegresultat](assets/edit_audience.png)

1. På **[!UICONTROL Choose Audience]** markerar du kryssrutorna bredvid de målgrupper du vill använda som byggstenar för den kombinerade målgruppen.

   Använd [!UICONTROL Search Audiences] för att begränsa sökningen efter den önskade målgruppen.

   ![Stegresultat](assets/combine_multiple_audiences1.png)

1. Klicka **[!UICONTROL Combine Multiple Audiences]** i det övre högra hörnet.

   ![Stegresultat](assets/combine_multiple_audiences2.png)

1. (Villkorligt) Redigera den nya kombinerade målgruppen efter behov.

   The [!UICONTROL Edit Audience] kan du dra och släppa ytterligare byggstenar från vänster sida till den nya kombinerade publiken. Du kan också lägga till exkluderingsregler och exkludera målgrupper.

   1. Använd dra-och-släpp-funktionen för att lägga till målgrupper i ett befintligt avsnitt som nivå 2-byggblock.

      Anta till exempel att du i föregående exempel nu vill inkludera Safari-användare i den kombinerade publiken. Sök efter och dra målgruppen&quot;Safari Browser&quot; till rutan&quot;Firefox Browser&quot; till höger, som i följande exempel:

      ![](assets/combine_multiple_audiences3.png)

      Observera att operatorn mellan de två målgrupperna av webbläsartyp är&quot;AND&quot;. Välj [!UICONTROL And] nedrullningsbar lista och ändra den till &quot;OR&quot; för att skapa en ny kombinerad målgrupp för nya besökare med antingen Firefox eller Safari. Undvik att skapa regler som utesluter alla potentiella målgruppsmedlemmar. Det är till exempel inte möjligt för någon att besöka en sida med Firefox och Safari samtidigt.

      >[!NOTE]
      >
      >Operatorn (AND eller OR) måste vara densamma som du kombinerar målgrupper. Du kan inte blanda och matcha operatorer.

   1. Om du vill lägga till ett undantag för en regel klickar du på **[!UICONTROL Exclude]**.

      ![](assets/combine_multiple_audiences3a.png)

      Dra och släpp en publik.

      Om du till exempel vill utesluta besökare från USA från nya besökare kan du dra Market: Amerikansk publik i lådan.

      Den här kombinerade publiken innehåller alla nya besökare på din webbplats (utom de som kommer från San Francisco) som använder Safari eller Firefox.

   1. Om du vill utesluta en målgrupp från en regel klickar du på **[!UICONTROL Exclusion]** > **[!UICONTROL Exclude this Audience.]**.

      Du kan till exempel skapa en kombinerad publik som innehåller alla nya besökare på webbplatsen, förutom de som använder Firefox. Det är enklare och snabbare att utesluta besökare som använder Firefox än att skapa en kombinerad publik som uttryckligen inkluderar flera webbläsare (Safari, Chrome och Internet Explorer), men inte Firefox.

1. Ange ett beskrivande namn för den kombinerade målgruppen och klicka sedan på **[!UICONTROL Done]**.

## Skapa en kombinerad målgrupp som kan användas för målinriktning mot mätvärden {#section_A42E795AFCBD4575809C5942039910F0}

Du kan skapa en ad hoc-målgrupp för aktivitetens [!UICONTROL Goals & Settings] sida som ska användas för målinriktning mot mätvärden. Om du till exempel vill skapa mål baserat på konvertering med en kombinerad målgrupp:

1. När du redigerar eller skapar en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), på **[!UICONTROL Goals & Settings]** sida, markera **[!UICONTROL Conversion]** för framgångsmåttet väljer du **[!UICONTROL Viewed an Mbox]** som åtgärden.
1. Markera önskad mbox i dialogrutan **[!UICONTROL Search mbox]** fält.

   ![](assets/combine_multiple_audiences4.png)

1. Klicka på kugghjulsikonen och sedan på **[!UICONTROL Add Audience Targeting]**.
1. Klicka på **[!UICONTROL Add Audience/Targeting Condition]** länk för att visa [!UICONTROL Choose Audience] -dialogrutan.

   ![](assets/combine_multiple_audiences5.png)

1. Fortsätt med [Steg 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under&quot;Skapa en kombinerad publik när du skapar en aktivitet&quot; för att skapa den kombinerade målgruppen.

## Skapa en kombinerad målgrupp som kan användas vid rapportering {#section_4682D342EFBB43C38E54B99B3A1E14CD}

Du kan skapa en ad hoc-målgrupp för aktivitetens [!UICONTROL Goals & Settings] sida som ska användas vid rapportering.

1. När du redigerar eller skapar en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), på **[!UICONTROL Goals & Settings]** klickar du på **[!UICONTROL Add Audience]** ikon under [!UICONTROL Audiences for Reporting] för att visa [!UICONTROL Choose Audience] sida.

   ![](assets/combine_multiple_audiences6.png)

1. Fortsätt med [Steg 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under&quot;Skapa en kombinerad publik när du skapar en aktivitet&quot; för att skapa den kombinerade målgruppen.

## Skapa en kombinerad målgrupp när du redigerar en aktivitet {#section_364A12CE96E04B61B7C18113AA586C2C}

Du kan skapa en ad hoc-målgrupp samtidigt som du redigerar en befintlig aktivitet.

1. Från [!UICONTROL Activities] hovra över önskad aktivitet och klicka sedan på **[!UICONTROL Edit]** ikon.

   eller

   Klicka på önskad aktivitet för att öppna den och klicka sedan på **[!UICONTROL Edit Activity]**.

1. Klicka på **[!UICONTROL Configure]** > **[!UICONTROL Audiences]** > **[!UICONTROL Multiple Audiences]**.

   ![Konfigurera > Målgrupper > Flera målgrupper](assets/combine_multiple_audiences7.png)

1. Klicka på ikonen med fler alternativ (tre lodräta ellipser) bredvid aktivitetens nuvarande målgrupp och klicka sedan på **[!UICONTROL Change Audience]**.

   ![Ändra målgrupp](assets/combine_multiple_audiences8.png)

1. Fortsätt med [Steg 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under&quot;Skapa en kombinerad publik när du skapar en aktivitet&quot; för att skapa den kombinerade målgruppen.
