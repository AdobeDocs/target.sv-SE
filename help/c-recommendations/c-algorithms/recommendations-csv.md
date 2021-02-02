---
keywords: skapa anpassade kriterier;algoritmer;villkor;rekommendationer villkor;csv;ftp;upload csv
description: Överför en CSV-fil för att anpassa dina rekommendationer.
title: Överför anpassade villkor
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---


# ![Egna villkor för ](/help/assets/premium.png) PREMIUMUpload{#upload-custom-criteria}

Överför en CSV-fil för att anpassa dina rekommendationer.

Det finns flera sätt att nå skärmen [!UICONTROL Create New Criteria]. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* På **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärmen klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. De villkor som du skapar här är automatiskt tillgängliga för alla [!DNL Recommendations]-aktiviteter.
* När du skapar en [!DNL Recommendations]-aktivitet med [!UICONTROL Visual Experience Composer] (VEC) visas du omedelbart på skärmen [!UICONTROL Select Criteria] när du har valt ett element på sidan och klickat på [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] eller [!UICONTROL Insert Recommendations After]. Du kan sedan välja ett tillgängligt villkor eller klicka på **[!UICONTROL Create Criteria]**. Om du skapar ett nytt villkor kan du välja att spara villkoret för användning med andra [!DNL Recommendations]-aktiviteter. Mer information finns i [Skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* När du redigerar en [!DNL Recommendations]-aktivitet klickar du i en [!UICONTROL Recommendations Location]-ruta på sidan och väljer **[!UICONTROL Change Criteria]**. Klicka på **[!UICONTROL Create Criteria]** på skärmen [!UICONTROL Select Criteria]. Du kan spara dina nya villkor och använda dem med andra [!DNL Recommendations]-aktiviteter.

Följande steg förutsätter att du kommer åt skärmen [!UICONTROL Create New Criteria] med den första metoden: **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärmen.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Upload Custom Criteria]**.

1. Fyll i informationen i [avsnittet Grundläggande information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Fyll i informationen i avsnittet [Datakälla](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source).

1. Fyll i informationen i [Content](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)-avsnittet.

1. (Villkorligt) Fyll i informationen i avsnittet [Likhet för innehåll](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

1. (Villkorligt) Fyll i informationen i [Inkluderingsregler](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)-avsnittet.

1. (Villkorligt) Fyll i informationen i avsnittet [Attributviktning](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting).

1. I avsnittet **[!UICONTROL Upload CSV]** väljer du **[!UICONTROL Location]** för CSV-filen.

   ![Överför CSV-avsnitt](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   CSV-filen måste vara korrekt formaterad för att överföringen ska lyckas. Klicka på **[!UICONTROL Download the CSV template]** för att få en korrekt formaterad CSV-fil.

   Det finns två platsalternativ:

   * **FTP:** Om du vill överföra CSV-filen från en FTP-server markerar du  **[!UICONTROL FTP]** och anger sedan den information som krävs. Du kan använda SSL, som använder FTPS-protokollet för att överföra CSV-filen på ett säkert sätt.
   * **URL:** Om du vill överföra CSV-filen från en URL-adress väljer du  **[!UICONTROL URL]** och anger sedan en feed-URL.

1. Klicka på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Anpassade villkorsenheter (rader) kan innehålla upp till 1 000 rekommenderade objekt (kolumner).

Uppdateringar av anpassade villkor är som standard&quot;kumulativa&quot;. Nya nyckelvärdepar som anges i CSV-överföringsfilen skriver över befintliga nyckelvärdepar. Befintliga nyckelvärdepar som inte har nycklar angivna i CSV-överföringen är fortfarande tillgängliga för leverans och upphör att gälla om 31 dagar från den tidpunkt då de senast överfördes som en del av CSV-filen.

Kontakta kundtjänst om du vill aktivera inställningen för att ignorera befintliga resultat som inte ingår i nästa CSV-överföring. Om den här inställningen är aktiverad är endast nycklarna i den anpassade CSV-feed-filen tillgängliga för leverans. Den här inställningen gäller för alla anpassade villkor.

Anpassade villkorsfeeds uppdateras en gång var 24:e timme.

Du kan se överförings- och synkroniseringsstatusen för dina anpassade villkorsuppladdningar längst ned på varje kriteriekort på sidan Recommendations > Villkor. Du kan även se statusen i dialogrutan Redigera när du redigerar egna villkor.

Flödet för en felfri överföring ska vara Schemalagd > Hämta feedfil > Importera > Slutförd.

Följande felmeddelanden kan visas om [!DNL Target] påträffar ett problem med överföringen:

| Felmeddelande | Detaljer |
|--- |--- |
| Okänt fel | Anger ett internt tekniskt fel. |
| Tolkningsfel | Det finns troligen ett problem med feed-filformatet. Korrigera filformatet och spara om algoritmen, vilket startar filhämtningen igen. |
| Servern hittades inte | Ange ett IP- eller värdnamn som visas på Internet. |
| Fel i autentiseringsuppgifter | Ange en giltig användare och ett giltigt lösenord för ett aktivt konto på servern. |
| Katalogen hittades inte | Ange en katalog som finns på servern. |
| Filen hittades inte | Ange namnet på en fil som finns på servern i den angivna katalogen. |

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

Den här videon innehåller följande information (information om hur du överför anpassade villkor börjar vid 11:43):

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)