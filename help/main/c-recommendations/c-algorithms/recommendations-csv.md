---
keywords: skapa anpassade kriterier;algoritmer;villkor;rekommendationer villkor;csv;ftp;upload csv
description: Lär dig hur du överför en CSV-fil för att anpassa dina rekommendationer i Adobe [!DNL Target] Recommendations.
title: Hur överför jag anpassade kriterier i Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# Överför anpassade villkor

Överför en CSV-fil för att anpassa dina rekommendationer i [!DNL Adobe Target].

Det finns flera sätt att nå [!UICONTROL Create New Criteria] skärm. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* På **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärm, klicka **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Kriterierna som du skapar här blir automatiskt tillgängliga för alla [!DNL Recommendations] verksamhet.
* När du skapar en [!DNL Recommendations] aktivitet med [!UICONTROL Visual Experience Composer] (VEC) kommer du omedelbart till [!UICONTROL Select Criteria] när du har markerat ett element på sidan och klickat [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before], eller [!UICONTROL Insert Recommendations After]. Du kan sedan välja ett tillgängligt villkor eller klicka på **[!UICONTROL Create Criteria]**. Om du skapar ett nytt villkor kan du spara villkoret för användning med andra villkor [!DNL Recommendations] verksamhet. Mer information finns i [Skapa en Recommendations-aktivitet](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* När du redigerar en [!DNL Recommendations] aktivitet, klicka på en [!UICONTROL Recommendations Location] och väljer **[!UICONTROL Change Criteria]**. På [!UICONTROL Select Criteria] skärm, klicka **[!UICONTROL Create Criteria]**. Du kan spara dina nya villkor och använda dem med andra [!DNL Recommendations] verksamhet.

Följande steg förutsätter att du har åtkomst till [!UICONTROL Create New Criteria] skärm med den första metoden: den **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärm.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]**.

1. Fyll i informationen i [Grundläggande information](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) -avsnitt.

   1. Från **[!UICONTROL Select Algorithm]** Listrutan Typ, välj **[!UICONTROL Custom Criteria]**.

   1. I listrutan **[!UICONTROL Algorithm]** väljer du **[!UICONTROL Custom Algorithm]**.

      >[!NOTE]
      >
      >Föregående steg orsakar [!UICONTROL Upload CSV] som ska visas längst ned i [!UICONTROL Create New Criteria] -dialogrutan.

1. (Villkorligt) Fyll i informationen i [Säkerhetskopiera innehåll](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) -avsnitt.

1. (Villkorligt) Fyll i informationen i [Inkluderingsregler](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) -avsnitt.

1. I **[!UICONTROL Upload CSV]** väljer du **[!UICONTROL Location]** av din CSV-fil.

   ![Överför CSV-avsnitt](assets/upload-csv.png)

   CSV-filen måste vara korrekt formaterad för att överföringen ska lyckas. Klicka **[!UICONTROL Download the CSV template]** för att hämta en korrekt formaterad CSV-fil.

   Det finns två platsalternativ:

   * **FTP:** Om du vill överföra din CSV-fil från en FTP-server väljer du **[!UICONTROL FTP]** anger du den information du behöver. Du kan använda SSL, som använder FTPS-protokollet för att överföra CSV-filen på ett säkert sätt.
   * **URL:** Om du vill överföra din CSV-fil från en URL-adress väljer du **[!UICONTROL URL]** anger du sedan en feed-URL.

1. Klicka på **[!UICONTROL Save]**.

## Överväganden

* Anpassade villkorsenheter (rader) kan innehålla upp till 1 000 rekommenderade objekt (kolumner).

* Uppdateringar av anpassade villkor är som standard&quot;kumulativa&quot;. Nya nyckelvärdepar som anges i CSV-överföringsfilen skriver över befintliga nyckelvärdepar. Befintliga nyckelvärdepar som inte har nycklar angivna i CSV-överföringen är fortfarande tillgängliga för leverans och upphör att gälla 31 dagar efter den tidpunkt då de senast överfördes som en del av CSV-filen.

   Kontakta kundtjänst om du vill aktivera inställningen för att ignorera befintliga resultat som inte ingår i nästa CSV-överföring. Om den här inställningen är aktiverad är endast nycklarna i den anpassade CSV-feed-filen tillgängliga för leverans. Den här inställningen gäller för alla anpassade villkor.

* Anpassade villkorsfeeds uppdateras en gång var 24:e timme.

   Du kan se överförings- och synkroniseringsstatus för dina anpassade villkorsuppladdningar längst ned på varje kriteriekort på [!UICONTROL Recommendations] > [!UICONTROL Criteria] sida. Du kan även se statusen i [!UICONTROL Edit] när du redigerar anpassade villkor.

* Flödet för en felfri överföring bör vara [!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful].

* Följande felmeddelanden är möjliga om du får [!DNL Target] påträffar ett problem med överföringen:

   | Felmeddelande | Detaljer |
   |--- |--- |
   | Okänt fel | Anger ett internt tekniskt fel. |
   | Tolkningsfel | Det finns troligen ett problem med feed-filformatet. Korrigera filformatet och spara om algoritmen, vilket startar om filhämtningsprocessen. |
   | Servern hittades inte | Ange ett IP- eller värdnamn som visas på Internet. |
   | Fel i autentiseringsuppgifter | Ange en giltig användare och ett giltigt lösenord för ett aktivt konto på servern. |
   | Katalogen hittades inte | Ange en katalog som finns på servern. |
   | Filen hittades inte | Ange namnet på en fil som finns på servern i den angivna katalogen. |

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller följande information (information om hur du överför anpassade villkor börjar vid 11:43):

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
