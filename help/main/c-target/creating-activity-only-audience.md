---
keywords: målgrupp;målgruppsregler;skapa målgrupp;skapa målgrupp;endast aktivitet;endast aktivitet;adhoc
description: Lär dig hur du skapar målgrupper som bara är aktiva i Adobe [!DNL Target] som är för engångsbruk.
title: Kan jag skapa en publik som bara kan användas en gång?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Skapa en målgrupp som bara är aktiv

Skapa målgrupper som bara är aktiva inifrån [!DNL Adobe Target] guidat arbetsflöde i tre steg när du skapar en aktivitet. Dessa ad hoc-målgrupper kan användas på andra platser inom samma aktivitet, men lagras inte i [!UICONTROL Audiences Library] för användning i andra verksamheter.

Målgrupper som bara är aktiva har följande fördelar:

* Du kan använda målgrupper som bara innehåller aktivitet för att skapa en målgrupp som du bara vill använda en gång och du inte vill lagra den i [!UICONTROL Audiences Library]. Målgrupper som bara är aktiva hjälper till att förhindra [!UICONTROL Audiences Library] från att bli rörig med målgrupper som ni aldrig vill använda igen.
* Målgrupper som bara är aktiva visas inte i [!UICONTROL Audiences Library]. Eftersom dessa målgrupper inte syns i biblioteket skyddas de från oönskade ändringar av andra i organisationen.

1. När en [aktivitet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), på **[!UICONTROL Targeting]** klickar du på de tre lodräta ellipserna och sedan på **[!UICONTROL Replace Audience]**.

   ![Stegresultat](assets/edit_audience.png)

1. Klicka på **[!UICONTROL Create Audience]**.

1. Klicka på **[!UICONTROL This activity only]**.

   ![endast-ljudbild för aktivitet](assets/activity-only-aud.png)

1. Skriv ett beskrivande målgruppsnamn.
1. Dra och släpp önskade attribut i målgruppsverktyget.

   Reglerna gör det möjligt att begränsa er målgrupp till en delmängd av era webbplatsbesökare. Varje regeltyp har sina egna parametrar. Se [Kategorier för målgrupper](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) om du vill ha mer information om hur du konfigurerar varje typ av målgruppsregel.

1. Klicka på **[!UICONTROL Done]**.

## Överväganden

Tänk på följande när du arbetar med målgrupper som bara är aktiva:

* Du kan skapa målgrupper som bara är aktiva i [!UICONTROL Visual Experience Composer] (VEC) eller i [!UICONTROL Form-Based Experience Composer]. Den här funktionen ersätter förfiningsreglerna i tidigare versioner av [!DNL Target].
* Du kan skapa en aktivitet att lagra i [!UICONTROL Audience Library] för återanvändning i andra aktiviteter eller för att skapa en målgrupp som bara innehåller aktiviteter. När du har sparat målgruppen kan du inte ändra målgruppstypen.
* Förfiningar av befintliga aktiviteter migreras till målgrupper som bara är aktiva.
* Målgrupper som bara är aktiva har statusen [!UICONTROL Used] eller [!UICONTROL Unused]. Oanvända målgrupper med endast aktivitet visas tills aktiviteten sparas. Om aktiviteten inte används och du försöker spara den visas ett varningsmeddelande som talar om att oanvända målgrupper endast för aktiviteter kommer att tas bort.
* Du kan visa information om målgruppsdefinitioner på ett popup-kort som du når från målgruppsväljaren utan att öppna målgruppen.
* Du kan [kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) för att skapa målgrupper som bara är aktiva.
* Målgrupper som bara är aktiva saknar stöd för exkluderingsregler.

   Du kan använda följande alternativ för att exkludera regler:

   * [Skapa och använda en bibliotekspublik](/help/main/c-target/c-audiences/create-audience.md) i stället för en målgrupp som bara är aktiv.
   * [Kombinera flera](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) (upp till 20) biblioteksmålgrupper till en målgrupp som bara är aktiv. När du kombinerar målgrupper kan du inkludera och exkludera regler i enskilda bibliotekspubliker, även när den kombinerade målgruppen sparas som en målgrupp som bara är aktiv.
