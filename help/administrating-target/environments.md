---
keywords: miljö;felsökning;bästa praxis;ubox;omdirigera;omdirigera;vitlista;svartlista;blockeringslista;tillåtelselista
description: Lär dig hur du använder miljöer i Adobe [!DNL Target] för att ordna webbplatser och förproduktionsmiljöer för enkel hantering och separat rapportering.
title: Vad är miljöer och hur använder jag dem?
feature: Administration och konfiguration
role: Administrator
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Miljö

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

Värdar paketeras i miljöer för enkel hantering. Du kan till exempel ha dussintals värdar grupperade i två eller tre miljöer. Förinställningsmiljöerna är [!UICONTROL Production], [!UICONTROL Staging] och [!UICONTROL Development]. Du kan lägga till nya miljöer och byta namn på dina miljöer om du vill.

En miljö, standardmiljön, har förnamnet [!UICONTROL Production]. Den här standardmiljön kan inte tas bort, även om du byter namn på den. [!DNL Target] förutsätter att det är här du kommer att utföra slutgiltiga, godkända aktiviteter och tester.

När en [!DNL Target]-begäran tas emot från nya webbplatser eller domäner visas alltid dessa nya domäner i [!UICONTROL Production]-miljön. [!UICONTROL Production]-miljön kan inte ha sina inställningar ändrade, så okända eller nya webbplatser kan garanterat bara se innehåll som är aktivt och klart. Med värdhantering kan du enkelt säkerställa kvaliteten på nya aktiviteter och innehåll i test-, staging- och utvecklingsmiljöer innan du aktiverar aktiviteterna.

Om du vill hantera miljöer klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Environments]**.

![Miljölista](/help/administrating-target/assets/environments.png)

## Lägg till en miljö {#section_32097D0993724DF3A202D164D3F18674}

1. Klicka på **[!UICONTROL Add Environment]** i listan [!UICONTROL Environments].
1. Ange ett beskrivande namn för miljön.
1. Ange önskat aktivt läge för miljön: [!UICONTROL Active Activities] eller [!UICONTROL Active and Inactive Activities].
1. Klicka på **[!UICONTROL Save]**.

## Ange standardmiljön för rapportering av {#section_4F8539B07C0C45E886E8525C344D5FB0}

Du kan välja den miljö som du vill använda som standard för alla aktivitetsrapporter.

Om du använder [!UICONTROL Production] som standard läggs alla okända värdar automatiskt till här och rapportdata från den inkluderas i standardrapportvyn. Om du i stället skapar en&quot;ren&quot; miljö omfattas bara dina kärnwebbplatser/domäner.

Så här anger du standardmiljön för rapportering:

1. Klicka på ikonen Stjärna i listan [!UICONTROL Environments]

>[!NOTE]
>
>[!DNL Recommendations] -användare måste återskapa sin beteendedatabas och produktdatabas om värdar byter värdgrupper.

## Ändra namnet på en miljö {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Klicka på ikonen **[!UICONTROL Edit]** i listan [!UICONTROL Environment].
1. Ändra miljönamnet.
1. Klicka på **[!UICONTROL Save]**.

## Ta bort en miljö {#section_737F8869612047868D03FC755B1223D3}

Du kan ta bort en miljö när den inte längre behövs.

1. Klicka på ikonen **[!UICONTROL Delete]** i listan [!UICONTROL Environment].
1. Klicka på **[!UICONTROL Delete]** för att bekräfta borttagningen.

>[!NOTE]
>
>Du kan inte ta bort [!UICONTROL Production]-miljön, men du kan byta namn på den.

## Recommendations: filtrera samlingar och uteslutningar efter miljö (värdgrupp)

![Premium-märke](/help/assets/premium.png)

Du kan förhandsgranska innehållet i Recommendations-samlingar och undantag för en vald miljö (värdgrupp).

>[!NOTE]
>
>Recommendations-aktiviteter är tillgängliga som en del av [!DNL Target] Premium-lösningen. De är inte tillgängliga i [!DNL Target] Standard utan en [!DNL Target] Premium-licens.

En miljö kan användas för att separera tillgängliga objekt i katalogen för olika användningsområden. Du kan till exempel använda värdgrupper för [!UICONTROL Development]- och [!UICONTROL Production]-miljöer, olika varumärken eller olika platser. Som standard baseras förhandsgranskningsresultaten i Katalogsökning, Samlingar och Undantag på standardvärdgruppen. (Du kan också välja en annan värdgrupp om du vill förhandsgranska resultaten med hjälp av miljöfiltret.) Som standard är nyligen tillagda objekt tillgängliga i alla värdgrupper om inte ett miljö-ID anges när objektet skapas eller uppdateras. Levererade rekommendationer beror på värdgruppen som anges i begäran.

Om du inte ser dina produkter bör du kontrollera att du använder rätt värdgrupp. Om du t.ex. har konfigurerat din rekommendation att använda en mellanlagringsmiljö och du har angett mellanlagringsgruppen som värdgrupp kan du behöva återskapa dina samlingar i mellanlagringsmiljön för att produkterna ska kunna visas. Om du vill se vilka produkter som är tillgängliga i respektive miljö använder du Katalogsökning för varje miljö. Du kan också förhandsgranska innehållet i Recommendations-samlingar och undantag för en vald miljö (värdgrupp).

>[!NOTE]
>När du har ändrat den valda miljön måste du klicka på Sök för att uppdatera de returnerade resultaten.

Filtret [!UICONTROL Environment] är tillgängligt från följande platser i målgränssnittet:

* Katalogsökning ([!UICONTROL Recommendations > Catalog Search])
* Dialogrutan Skapa samling ([!UICONTROL Recommendations > Collections > Create New])
* Dialogrutan Uppdatera samling ([!UICONTROL Recommendations > Collections > Edit])
* Dialogrutan Skapa undantag ([!UICONTROL Recommendations > Exclusions > Create New])
* Dialogrutan Uppdatera undantag ([!UICONTROL Recommendations > Exclusions > Edit])
