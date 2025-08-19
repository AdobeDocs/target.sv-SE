---
keywords: målgrupp;målgruppsregler;kombinera målgrupper;exkludering;exkludera;kombinera målgrupper;ad hoc-målgrupper;ad hoc-målgrupper
description: Lär dig kombinera flera målgrupper (inklusive Adobe Experience Cloud-målgrupper och [!DNL Target] målgrupper) direkt för att skapa ad hoc-målgrupper.
title: Kan jag kombinera flera olika målgrupper för att skapa en ny målgrupp?
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 0%

---

# Kombinera flera målgrupper

Kombinera flera målgrupper (inklusive [!DNL Adobe Experience Cloud], [!DNL Adobe Experience Platform] och [!DNL Target] målgrupper) direkt för att skapa ad hoc-målgrupper. Du kan också skapa exkluderingsregler och exkludera målgrupper från en regel.

>[!NOTE]
>
>[!DNL Adobe Experience Platform]-källan är tillgänglig för alla [!DNL Target]-kunder som använder [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=en){target=_blank}. Publiker som är tillgängliga från [!DNL Adobe Experience Platform] kan användas som de är eller kombineras med befintliga målgrupper, vilket förklaras i det här avsnittet.
>
>Mer information finns i [Använda målgrupper från Adobe Experience Platform](/help/main/c-target/c-audiences/audiences.md#aep).

Anta att ni har en&quot;ny besökare&quot; och en&quot;Chrome-användare&quot; som målgrupp. För en viss aktivitet kanske du vill kombinera dessa befintliga målgrupper för att rikta in dig på nya besökare med Chrome webbläsare. I stället för att skapa en tredje målgrupp och lagra den i biblioteket [!UICONTROL Audiences] kan du kombinera de här två målgrupperna när du skapar en aktivitet eller när du redigerar en befintlig aktivitet.

Som ett annat exempel kan ni inrikta er på alla lojalitetskunder. Du kan till exempel inkludera en specifik [!DNL Audience Manager]-målgrupp för lojalitetsstatus och kombinera den med en [!DNL Target]-målgrupp bestående av personer som har registrerat sig för ditt lojalitetsprogram under den aktuella sessionen. Det är enklare att kombinera dessa båda målgrupper än att skapa en tredje permanent målgrupp.

Du kan kombinera upp till 20 målgrupper med operatorerna AND och OR.

Du kan skapa och använda kombinerade målgrupper på olika platser i [!DNL Target]-gränssnittet.

## Skapa en kombinerad målgrupp när du skapar en aktivitet {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

Du kan skapa en ad hoc-målgrupp på aktivitetens [!UICONTROL Target]-sida under det guidade arbetsflödet i tre steg.

1. När du skapar en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) klickar du på de tre lodräta ellipserna på sidan **[!UICONTROL Targeting]** och sedan på **[!UICONTROL Replace Audience]**.

   ![Stegresultat](assets/edit_audience.png)

1. På sidan **[!UICONTROL Choose Audience]** markerar du kryssrutorna bredvid de målgrupper du vill använda som byggstenar för den kombinerade målgruppen.

   Använd rutan [!UICONTROL Search Audiences] om du vill begränsa sökningen efter den önskade målgruppen.

   ![Stegresultat](assets/combine_multiple_audiences1.png)

1. Klicka på **[!UICONTROL Combine Multiple Audiences]** längst upp till höger.

   ![Stegresultat](assets/combine_multiple_audiences2.png)

1. (Villkorligt) Redigera den nya kombinerade målgruppen efter behov.

   I dialogrutan [!UICONTROL Edit Audience] kan du dra och släppa ytterligare målgruppsbyggen från vänster sida till den nya kombinerade målgruppen. Du kan också lägga till exkluderingsregler och exkludera målgrupper.

   1. Använd dra-och-släpp-funktionen för att lägga till målgrupper i ett befintligt avsnitt som nivå 2-byggblock.

      Anta till exempel att du i föregående exempel nu vill inkludera Safari-användare i den kombinerade publiken. Sök efter och dra målgruppen&quot;Safari Browser&quot; till rutan&quot;Firefox Browser&quot; till höger, som i följande exempel:

      ![combin_multiple_audiences3 image](assets/combine_multiple_audiences3.png)

      Observera att operatorn mellan de två målgrupperna av webbläsartyp är&quot;AND&quot;. Välj listrutan [!UICONTROL And] och ändra den till &quot;OR&quot; för att skapa en ny kombinerad målgrupp för nya besökare med antingen Firefox eller Safari. Undvik att skapa regler som utesluter alla potentiella målgruppsmedlemmar. Det är till exempel inte möjligt för någon att besöka en sida med Firefox och Safari samtidigt.

      >[!NOTE]
      >
      >Operatorn (AND eller OR) måste vara densamma som du kombinerar målgrupper. Du kan inte blanda operatorer och matchningsoperatorer.

   1. Klicka på **[!UICONTROL Exclude]** om du vill lägga till ett undantag för en regel.

      ![combin_multiple_audiences3a image](assets/combine_multiple_audiences3a.png)

      Dra och släpp en publik.

      Om du till exempel vill utesluta besökare från USA från nya besökare kan du dra Market: USA-målgruppen till rutan.

      Den här kombinerade publiken innehåller alla nya besökare på din webbplats (utom de som kommer från San Francisco) som använder Safari eller Firefox.

   1. Om du vill utesluta en målgrupp från en regel klickar du på **[!UICONTROL Exclusion]** > **[!UICONTROL Exclude this Audience.]**.

      Du kan till exempel skapa en kombinerad publik som innehåller alla nya besökare på webbplatsen, förutom de som använder Firefox. Det är enklare och snabbare att utesluta besökare som använder Firefox än att skapa en kombinerad publik som uttryckligen inkluderar flera webbläsare (Safari, Chrome och Internet Explorer), men inte Firefox.

1. Ange ett beskrivande namn för den kombinerade målgruppen och klicka sedan på **[!UICONTROL Done]**.

## Skapa en kombinerad målgrupp som kan användas för målinriktning mot mätvärden {#section_A42E795AFCBD4575809C5942039910F0}

Du kan skapa en ad hoc-målgrupp på aktivitetens [!UICONTROL Goals & Settings]-sida som ska användas för målinriktning mot mätvärden. Om du till exempel vill skapa mål baserat på konvertering med en kombinerad målgrupp:

1. När du redigerar eller skapar en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) väljer du **[!UICONTROL Goals & Settings]** som framgångsmått på sidan **[!UICONTROL Conversion]** och sedan **[!UICONTROL Viewed an Mbox]** som åtgärd.
1. Markera önskad mbox i fältet **[!UICONTROL Search mbox]**.

   ![combin_multiple_audiences4 image](assets/combine_multiple_audiences4.png)

1. Klicka på kugghjulsikonen och sedan på **[!UICONTROL Add Audience Targeting]**.
1. Klicka på länken **[!UICONTROL Add Audience/Targeting Condition]** för att visa dialogrutan [!UICONTROL Choose Audience].

   ![combin_multiple_audiences5, bild](assets/combine_multiple_audiences5.png)

1. Fortsätt med [Steg 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under Skapa en kombinerad publik när du skapar en aktivitet för att skapa den kombinerade målgruppen.

## Skapa en kombinerad målgrupp som kan användas vid rapportering {#section_4682D342EFBB43C38E54B99B3A1E14CD}

Du kan skapa en kombinerad ad ad hoc-målgrupp på aktivitetens [!UICONTROL Goals & Settings]-sida som ska användas för rapportering.

1. När du redigerar eller skapar en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) klickar du på ikonen **[!UICONTROL Goals & Settings]** under **[!UICONTROL Add Audience]** på sidan [!UICONTROL Audiences for Reporting] för att visa sidan [!UICONTROL Choose Audience].

   ![combin_multiple_audiences6 image](assets/combine_multiple_audiences6.png)

1. Fortsätt med [Steg 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under Skapa en kombinerad publik när du skapar en aktivitet för att skapa den kombinerade målgruppen.

## Skapa en kombinerad målgrupp när du redigerar en aktivitet {#section_364A12CE96E04B61B7C18113AA586C2C}

Du kan skapa en ad hoc-målgrupp samtidigt som du redigerar en befintlig aktivitet.

1. Håll markören över önskad aktivitet på sidan [!UICONTROL Activities] och klicka sedan på ikonen **[!UICONTROL Edit]** .

   eller

   Klicka på önskad aktivitet för att öppna den och klicka sedan på **[!UICONTROL Edit Activity]**.

1. Klicka på **[!UICONTROL Configure]** > **[!UICONTROL Audiences]** > **[!UICONTROL Multiple Audiences]**.

   ![Konfigurera > Publiker > Flera Publiker](assets/combine_multiple_audiences7.png)

1. Klicka på ikonen med fler alternativ (tre lodräta ellipser) bredvid aktivitetens aktuella målgrupp och klicka sedan på **[!UICONTROL Change Audience]**.

   ![Ändra publik](assets/combine_multiple_audiences8.png)

1. Fortsätt med [Steg 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under Skapa en kombinerad publik när du skapar en aktivitet för att skapa den kombinerade målgruppen.
