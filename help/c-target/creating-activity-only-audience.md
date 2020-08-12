---
keywords: audience;audience rules;create audience;creating audience;activity only;activity-only;adhoc
description: Skapa målgrupper som bara är aktiva inifrån Adobe Target trestegsbaserade guidade arbetsflöde när du skapar en aktivitet. Dessa ad hoc-målgrupper kan användas på andra platser inom samma aktivitet, men lagras inte i publikbiblioteket för användning i andra aktiviteter.
title: Skapa en målgrupp som bara är aktiv i Adobe Target
feature: null
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---


# Skapa en målgrupp som bara är aktiv{#create-an-activity-only-audience}

Skapa målgrupper som bara är aktiva i det guidade arbetsflödet i tre steg när du skapar en aktivitet. Dessa ad hoc-målgrupper kan användas på andra platser inom samma aktivitet, men lagras inte i [!UICONTROL Audiences Library] för användning i andra aktiviteter.

Målgrupper som bara är aktiva har följande fördelar:

* Ni kan använda målgrupper som bara innehåller aktivitet för att skapa en målgrupp som ni bara vill använda en gång och inte vill lagra den i [!UICONTROL Audiences Library]. Detta förhindrar att [!UICONTROL Audiences Library] kunderna blir förvirrade av målgrupper som du aldrig vill använda igen.
* Målgrupper som bara är aktiva visas inte i [!UICONTROL Audiences Library]. På grund av detta skyddas de från oönskade ändringar av andra i organisationen.

1. När du skapar en [aktivitet](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)klickar du på de tre lodräta ellipserna på **[!UICONTROL Target]** sidan och sedan på **[!UICONTROL Replace Audience]**.

   ![Stegresultat](assets/edit_audience.png)

1. På [!UICONTROL Choose Audience] sidan klickar du på **[!UICONTROL Activity Only Audience]**.

   ![](assets/activity-only-aud.png)

1. Klicka på **[!UICONTROL Create Audience]**.
1. Skriv ett beskrivande målgruppsnamn.
1. Klicka på **[!UICONTROL + Add Rule]**.

   Reglerna gör det möjligt att begränsa er målgrupp till en delmängd av era webbplatsbesökare.

1. Välj en regeltyp.

   Varje regeltyp har sina egna parametrar. Mer information om hur du konfigurerar varje typ av målgruppsregel finns i [Kategorier för målgrupper](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) .

1. Definiera regelparametrarna.
1. Klicka på **[!UICONTROL Save]**.

## Överväganden

Tänk på följande när du arbetar med målgrupper som bara är aktiva:

* Du kan skapa målgrupper som bara är aktiva i Visual Experience Composer (VEC) eller i den formulärbaserade Experience Composer. Den här funktionen ersätter förfiningsreglerna i tidigare versioner av Target.
* Du kan skapa en aktivitet som ska lagras i programmet [!UICONTROL Audience Library] för återanvändning i andra aktiviteter eller så kan du skapa en målgrupp som bara innehåller aktiviteter. När du har sparat målgruppen kan du inte ändra målgruppstypen.
* Förfiningar av befintliga aktiviteter migreras till målgrupper som bara är aktiva.
* Målgrupper som bara är aktiva har statusen [!UICONTROL Used] eller [!UICONTROL Unused]. Oanvända målgrupper med endast aktivitet visas tills aktiviteten sparas. Om aktiviteten inte används och du försöker spara den visas ett varningsmeddelande som talar om att oanvända målgrupper endast för aktiviteter kommer att tas bort.
* Du kan visa information om målgruppsdefinitioner på ett popup-kort som du når från målgruppsväljaren utan att öppna målgruppen.
* Ni kan [kombinera flera målgrupper](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) för att skapa målgrupper som bara är aktiva.

