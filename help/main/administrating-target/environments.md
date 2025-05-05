---
keywords: miljö;felsökning;bästa praxis;ubox;omdirigera;omdirigera;vitlista;svartlista;blockeringslista;tillåtelselista
description: Lär dig hur du använder miljöer i Adobe [!DNL Target] för att ordna dina webbplatser och förproduktionsmiljöer för enkel hantering och separat rapportering.
title: Vad är miljöer och hur använder jag dem?
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---

# Miljö

Organisera sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

Värdar paketeras i miljöer för enkel hantering. Du kan till exempel ha dussintals värdar grupperade i två eller tre miljöer. Förinställningsmiljöerna är bland annat [!UICONTROL Production], [!UICONTROL Staging] och [!UICONTROL Development]. Du kan lägga till nya miljöer och byta namn på dina miljöer om du vill.

En miljö, standardmiljön, har förnamnet [!UICONTROL Production]. Den här standardmiljön kan inte tas bort, även om du byter namn på den. [!DNL Target] antar att det är här du kommer att leverera slutgiltiga, godkända aktiviteter och tester.

När en [!DNL Target]-begäran tas emot från nya webbplatser eller domäner visas alltid dessa nya domäner i [!UICONTROL Production]-miljön. Miljön [!UICONTROL Production] kan inte ha sina inställningar ändrade, så okända eller nya platser garanteras bara se innehåll som är aktivt och klart. Med värdhantering kan du enkelt säkerställa kvaliteten på nya aktiviteter och innehåll i test-, staging- och utvecklingsmiljöer innan du aktiverar aktiviteterna.

{{permissions-update}}

Klicka **[!UICONTROL Administration]** > **[!UICONTROL Environments]** om du vill hantera miljöer.

## Lägga till en miljö {#section_32097D0993724DF3A202D164D3F18674}

1. Klicka på **[!UICONTROL Add Environment]** i listan [!UICONTROL Environments].
1. Ange ett beskrivande namn för miljön.
1. Ange önskat aktivt läge för miljön: [!UICONTROL Active Activities] eller [!UICONTROL Active and Inactive Activities].

   Om du anger [!UICONTROL Active and Inactive Activities] visar värdar från den här miljön även inaktiva aktiviteter.

1. Klicka på **[!UICONTROL Save]**.

## Ange standardmiljö för rapportering {#section_4F8539B07C0C45E886E8525C344D5FB0}

Du kan välja den miljö som du vill använda som standard för alla aktivitetsrapporter.

Om du använder [!UICONTROL Production] som standard läggs alla okända värdar automatiskt till här och rapportdata från det inkluderas i standardrapportvyn. Om du i stället skapar en&quot;ren&quot; miljö omfattas bara dina kärnwebbplatser/domäner.

Så här anger du standardmiljön för rapportering:

1. Klicka på stjärnikonen i listan [!UICONTROL Environments]

>[!NOTE]
>
>[!DNL Recommendations] användare måste återskapa sin beteendedatabas och produktdatabas om värdar byter värdgrupper.
>
>Om du anger en [standardmiljö i en [!DNL Adobe Experience Platform] datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=sv-SE#target){target=_blank} åsidosätter den här inställningen inställningen inställningen i [!DNL Target].

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
>Du kan inte ta bort miljön [!UICONTROL Production], men du kan byta namn på den.

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Se vad som ingår i Target Premium."}

Du kan förhandsgranska innehållet i Recommendations-samlingar och undantag för en vald miljö (värdgrupp).

{{premium-note}}

En miljö kan användas för att separera tillgängliga objekt i katalogen för olika användningsområden. Du kan till exempel använda värdgrupper för [!UICONTROL Development]- och [!UICONTROL Production]-miljöer, olika varumärken eller olika platser. Som standard baseras förhandsgranskningsresultaten i Katalogsökning, Samlingar och Undantag på standardvärdgruppen. (Du kan också välja en annan värdgrupp om du vill förhandsgranska resultaten med hjälp av miljöfiltret.) Som standard är nyligen tillagda objekt tillgängliga i alla värdgrupper om inte ett miljö-ID anges när objektet skapas eller uppdateras.

>[!NOTE]
>
>Levererade rekommendationer beror på värdgruppens eller miljö-ID:t som anges i begäran.


Om du inte ser dina produkter bör du kontrollera att du använder rätt värdgrupp. Om du t.ex. har konfigurerat din rekommendation att använda en mellanlagringsmiljö och du har angett mellanlagringsgruppen som värdgrupp kan du behöva återskapa dina samlingar i mellanlagringsmiljön för att produkterna ska kunna visas. Om du vill se vilka produkter som är tillgängliga i respektive miljö använder du Katalogsökning för varje miljö. Du kan också förhandsgranska innehållet i Rekommendationer-samlingar och undantag för en vald miljö (värdgrupp).

>[!NOTE]
>När du har ändrat den valda miljön måste du klicka på Sök för att uppdatera de returnerade resultaten.

Filtret [!UICONTROL Environment] är tillgängligt från följande platser i målgränssnittet:

* Katalogsökning ([!UICONTROL Recommendations > Catalog Search])
* Dialogrutan Skapa samling ([!UICONTROL Recommendations > Collections > Create New])
* Dialogrutan Uppdatera samling ([!UICONTROL Recommendations > Collections > Edit])
* Dialogrutan Skapa undantag ([!UICONTROL Recommendations > Exclusions > Create New])
* Dialogrutan Uppdatera undantag ([!UICONTROL Recommendations > Exclusions > Edit])
