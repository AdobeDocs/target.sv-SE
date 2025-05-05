---
keywords: skapa anpassade kriterier;algoritmer;villkor;rekommendationer villkor;csv;ftp;upload csv
description: Lär dig hur du överför en CSV-fil för att anpassa dina rekommendationer i Adobe [!DNL Target] Recommendations.
title: Hur överför jag anpassade villkor i  [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 1%

---

# Överför anpassade villkor

Överför en CSV-fil för att anpassa dina rekommendationer i [!DNL Adobe Target].

Det finns flera sätt att nå skärmen [!UICONTROL Create New Criteria]. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]** på biblioteksskärmen **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**. Kriterier som du skapar här blir automatiskt tillgängliga för alla [!DNL Recommendations]-aktiviteter.
* När du skapar en [!DNL Recommendations]-aktivitet med [!UICONTROL Visual Experience Composer] (VEC) visas du omedelbart på skärmen [!UICONTROL Select Criteria] när du har markerat ett element på sidan och klickat på [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] eller [!UICONTROL Insert Recommendations After]. Du kan sedan välja ett tillgängligt villkor eller klicka på **[!UICONTROL Create Criteria]**. Om du skapar nya villkor kan du spara dina villkor för användning med andra [!DNL Recommendations]-aktiviteter. Mer information finns i [Skapa en Recommendations-aktivitet](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* När du redigerar en [!DNL Recommendations]-aktivitet klickar du i en [!UICONTROL Recommendations Location]-ruta på sidan och väljer **[!UICONTROL Change Criteria]**. Klicka på **[!UICONTROL Create Criteria]** på skärmen [!UICONTROL Select Criteria]. Du kan spara dina nya villkor och använda dem med andra [!DNL Recommendations]-aktiviteter.

Följande steg förutsätter att du kommer åt skärmen [!UICONTROL Create New Criteria] med den första metoden: biblioteksskärmen **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Fyll i informationen i avsnittet [Grundläggande information](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. I listrutan **[!UICONTROL Select Algorithm Type]** väljer du **[!UICONTROL Custom Criteria]**.

1. I listrutan **[!UICONTROL Algorithm]** väljer du **[!UICONTROL Custom Algorithm]**.

   >[!NOTE]
   >
   >Föregående steg gör att avsnittet [!UICONTROL Upload CSV] visas längst ned i dialogrutan [!UICONTROL Create Criteria].

1. (Villkorligt) Fyll i informationen i avsnittet [Säkerhetskopiera innehåll](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Villkorligt) Fyll i informationen i avsnittet [Inkluderingsregler](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) .

1. I avsnittet **[!UICONTROL Upload CSV]** väljer du **[!UICONTROL Location]** för CSV-filen.

CSV-filen måste vara korrekt formaterad för att överföringen ska lyckas. Klicka på **[!UICONTROL Download the CSV template]** om du vill hämta en korrekt formaterad CSV-fil.

Det finns två platsalternativ:

    * **FTP:** Om du vill överföra din CSV-fil från en FTP-server väljer du **[!UICONTROL FTP]** och anger sedan nödvändig information. Du kan använda SSL, som använder FTPS-protokollet för att överföra CSV-filen på ett säkert sätt.
    
    * **URL:** Om du vill överföra din CSV-fil från en URL väljer du **[!UICONTROL URL]** och anger sedan en feed-URL.

1. Klicka på **[!UICONTROL Create]**.

## Överväganden

* Anpassade villkorsenheter (rader) kan innehålla upp till 1 000 rekommenderade objekt (kolumner).

* Uppdateringar av anpassade villkor är som standard&quot;kumulativa&quot;. Nya nyckelvärdepar som anges i CSV-överföringsfilen skriver över befintliga nyckelvärdepar. Befintliga nyckelvärdepar som inte har nycklar angivna i CSV-överföringen är fortfarande tillgängliga för leverans och upphör att gälla 31 dagar efter den tidpunkt då de senast överfördes som en del av CSV-filen.

  Kontakta kundtjänst om du vill aktivera inställningen för att ignorera befintliga resultat som inte ingår i nästa CSV-överföring. Om den här inställningen är aktiverad är endast nycklarna i den anpassade CSV-feed-filen tillgängliga för leverans. Den här inställningen gäller för alla anpassade villkor.

* Anpassade villkorsfeeds uppdateras en gång var 24:e timme.

  Du kan se överförings- och synkroniseringsstatus för dina anpassade villkorsuppladdningar för varje villkor på sidan [!UICONTROL Recommendations] > [!UICONTROL Criteria]. Du kan också se statusen i dialogrutan [!UICONTROL Edit] när du redigerar anpassade villkor.

* Flödet för en felfri överföring ska vara [!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful].

* Följande felmeddelanden är möjliga om [!DNL Target] stöter på problem med överföringen:

  | Felmeddelande | Information |
  |--- |--- |
  | Okänt fel | Anger ett internt tekniskt fel. |
  | Tolkningsfel | Det finns troligen ett problem med feed-filformatet. Korrigera filformatet och spara om algoritmen, som startar om filhämtningen. |
  | Servern hittades inte | Ange ett IP- eller värdnamn som visas på Internet. |
  | Fel i autentiseringsuppgifter | Ange en giltig användare och ett giltigt lösenord för ett aktivt konto på servern. |
  | Katalogen hittades inte | Ange en katalog som finns på servern. |
  | Filen hittades inte | Ange namnet på en fil som finns på servern i den angivna katalogen. |
