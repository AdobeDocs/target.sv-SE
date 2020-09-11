---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: Överför en CSV-fil för att anpassa dina rekommendationer.
title: Överför anpassade villkor
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1794'
ht-degree: 0%

---


# ![Egna villkor för PREMIUM](/help/assets/premium.png) -överföring{#upload-custom-criteria}

Överför en CSV-fil för att anpassa dina rekommendationer.

## Öppna skärmen Skapa nya villkor

Det finns flera sätt att nå [!UICONTROL Create New Criteria] skärmen. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* På skärmen **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** bibliotek klickar du **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Kriterierna som du skapar här blir automatiskt tillgängliga för alla [!DNL Recommendations] aktiviteter.
* När du skapar en [!DNL Recommendations] aktivitet med [!UICONTROL Visual Experience Composer] (VEC) visas du direkt på [!UICONTROL Select Criteria] skärmen när du har markerat ett element på sidan och klickat [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before]eller [!UICONTROL Insert Recommendations After]. Du kan sedan välja ett villkor eller klicka på **[!UICONTROL Create Criteria]**. Om du skapar ett nytt villkor kan du välja att spara villkoret för användning med andra [!DNL Recommendations] aktiviteter. Mer information finns i [Skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* När du redigerar en [!DNL Recommendations] aktivitet klickar du i en [!UICONTROL Recommendations Location] ruta på sidan och väljer **[!UICONTROL Change Criteria]**. Klicka på på [!UICONTROL Select Criteria] skärmen **[!UICONTROL Create Criteria]**. Du kan spara dina nya villkor och använda dem med andra [!DNL Recommendations] aktiviteter.

Följande steg förutsätter att du kommer åt [!UICONTROL Create New Criteria] skärmen med den första metoden: på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärmen.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Upload Custom Criteria]**.

1. Konfigurera informationen i följande avsnitt.

## Grundläggande information {#info}

1. Skriv ett **[!UICONTROL Criteria Name]**.

   Detta är det&quot;interna&quot; namnet som används för att beskriva kriterierna. Du kanske vill kalla villkoren för&quot;Produkter med högsta marginal&quot;, men du vill inte att den titeln ska visas offentligt. Se nästa steg för att ange den offentliga titeln.

   ![Avsnittet Grundläggande information](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Skriv en offentlig sida **[!UICONTROL Display Title]** som ska visas på sidan för rekommendationer som använder det här villkoret.

   Du kan till exempel visa&quot;Personer som visade det här&quot; eller&quot;Liknande produkter&quot; när du använder det här villkoret för att visa rekommendationer.

1. Ange en kort **[!UICONTROL Description]** av villkoren.

   Beskrivningen bör hjälpa dig att identifiera villkoren och kan innehålla information om syftet med kriterierna.

1. Välj en vertikal bransch baserat på målen för dina rekommendationer.

   | Branschvertikal | Mål |
   |--- |--- |
   | Detaljhandel/e-handel | Konvertering som resulterar i inköp |
   | Leadgenerering/B2B/Finansiella tjänster | Konvertering utan köp |
   | Media/publicering | Engagemang |

   Andra kriteriealternativ ändras beroende på vilken vertikal du väljer.

1. Välj en **[!UICONTROL Page Type]**.

   Du kan välja flera sidtyper.

   Tillsammans används de vertikala metoderna och sidtyperna för att kategorisera de sparade villkoren, vilket gör det enklare att återanvända villkor för andra [!DNL Recommendations] aktiviteter.

1. Välj en **[!UICONTROL Recommendation Key]**.

   Mer information om att basera villkor på en nyckel finns i [Basera rekommendationen på en rekommendationsnyckel](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

1. Markera **[!UICONTROL Recommendation Logic]**.

   Mer information om alternativ för rekommendationslogik finns i [Kriterier](../../c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >Om du väljer **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]** kan du ange regler för [innehållets likhet](#similarity).

## Innehåll {#content}

Innehållsreglerna avgör vad som händer om antalet rekommenderade objekt inte uppfyller [rekommendationsdesignen](/help/c-recommendations/c-design-overview/design-overview.md). Kriterierna kan returnera färre rekommendationer än vad din design kräver [!DNL Recommendations] . Om din design till exempel har platser för fyra objekt, men dina villkor bara leder till att två objekt rekommenderas, kan du lämna de återstående platserna tomma eller använda rekommendationer för säkerhetskopiering för att fylla de extra platserna.

![Innehållsavsnitt](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Valfritt) Skjut **[!UICONTROL Partial Design Rendering]** växlingsknappen till&quot;på&quot;-positionen.

   Så många kortplatser som möjligt kommer att fyllas, men designmallen kan innehålla tomt utrymme för återstående kortplatser. Om det här alternativet är inaktiverat och det inte finns tillräckligt med innehåll för att fylla alla tillgängliga platser, kommer inga rekommendationer att visas och standardinnehåll visas i stället.

   Aktivera det här alternativet om du vill att rekommendationer ska hanteras med tomma platser. Använd rekommendationer för säkerhetskopiering om du vill att rekommendationsplatserna ska fyllas med innehåll baserat på dina kriterier med tomma platser fyllda med liknande eller populärt innehåll från platsen, vilket förklaras i nästa steg.

1. (Valfritt) Skjut **[!UICONTROL Show Backup Recommendations]** växlingsknappen till&quot;på&quot;-positionen.

   Fyll eventuella återstående tomma platser i designen med ett slumpmässigt urval av de mest visade produkterna från hela webbplatsen.

   Genom att använda rekommendationer för säkerhetskopiering försäkrar du dig om att din rekommendationsdesign fyller alla tillgängliga platser. Anta att du har en design på 4 x 1 enligt nedan:

   ![4 x 1-design](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Anta att dina kriterier gör att bara två objekt rekommenderas. Om du aktiverar [!UICONTROL Partial Design Rendering] alternativet fylls de två första platserna i, men de återstående två platserna förblir tomma. Om du aktiverar [!UICONTROL Show Backup Recommendations] alternativet fylls de två första kortplatserna i baserat på dina angivna villkor och de återstående två kortplatserna fylls i baserat på dina rekommendationer för säkerhetskopiering.

   I följande matris visas det resultat du får se när du använder alternativen [!UICONTROL Partial Design Rendering] och [!UICONTROL Backup Recommendations] :

   | Delvis designåtergivning | Säkerhetskopiera Recommendations | Resultat |
   |--- |--- |--- |
   | Handikappade | Handikappade | Om färre rekommendationer returneras än vad designen kräver ersätts rekommendationsdesignen med standardinnehåll och inga rekommendationer visas. |
   | Aktiverad | Handikappade | Designen återges, men kan innehålla tomt utrymme om färre rekommendationer returneras än vad designanropen kräver. |
   | Aktiverad | Aktiverad | Rekommendationer för säkerhetskopiering fyller i tillgängliga designfack och återger designen helt.<br>Om inkluderingsregler tillämpas på rekommendationer för säkerhetskopiering, begränsas antalet kvalificerade rekommendationer för säkerhetskopiering till den punkt där designen inte kan fyllas, återges designen delvis.<br>Om villkoret inte returnerar några rekommendationer, och inkluderingsreglerna begränsar rekommendationerna för säkerhetskopiering till noll, ersätts designen med standardinnehåll. |
   | Handikappade | Aktiverad | Rekommendationer för säkerhetskopiering fyller i tillgängliga designfack och återger designen helt.<br>Om inkluderingsregler tillämpas på rekommendationer för säkerhetskopiering, begränsas antalet kvalificerade rekommendationer för säkerhetskopiering till den punkt där designen inte kan fyllas, ersätts designen med standardinnehåll och inga rekommendationer visas. |

   Mer information finns i [Använda en rekommendation](/help/c-recommendations/c-algorithms/backup-recs.md)för säkerhetskopiering.

1. (Villkorligt) Om du valde **[!UICONTROL Show Backup Recommendations]** i föregående steg kan du aktivera **[!UICONTROL Apply inclusion rules to backup recommendations]**.

   Inkluderingsregler avgör vilka objekt som tas med i dina rekommendationer. Vilka alternativ som är tillgängliga beror på var du arbetar vertikalt.

   Mer information finns i [Ange inkluderingsregler](#inclusion) nedan.

1. (Valfritt) Skjut **[!UICONTROL Recommend Previously Purchased Items]** växlingsknappen till&quot;på&quot;-positionen.

   Den här inställningen baseras på `productPurchasedId`. Standardbeteendet är att inte rekommendera tidigare inköpta artiklar. I de flesta fall vill du inte marknadsföra artiklar som en kund nyligen har köpt. Det är användbart om du säljer artiklar som normalt bara köps en gång, t.ex. kajaker. Om du säljer artiklar som personer återkommer till att köpa igen upprepade gånger, som schampo eller andra personliga artiklar, bör du aktivera det här alternativet.

## Inkluderingsregler {#inclusion}

Det finns flera alternativ som du kan använda för att begränsa de objekt som visas i dina rekommendationer. Du kan använda inkluderingsregler när du skapar villkor eller kampanjer.

![Inkluderingsregler](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Inkluderingsregler är frivilliga. Men om du ställer in dessa uppgifter får du bättre kontroll över vilka objekt som visas i dina rekommendationer. Varje detalj som du konfigurerar förminskar visningsvillkoren ytterligare.

Du kan t.ex. välja att bara visa damskor som har en inventering på mer än 50 och ett pris mellan 25 och 45 dollar. Du kan också väga varje attribut så att de objekt som är viktigast för ditt företag visas med största sannolikhet.

Som ett annat exempel kan du välja att visa nya jobb för besökare som besöker webbplatsen endast från vissa städer och som har rätt högskoleutbildning.

Inkluderingsregelalternativen varierar beroende på bransch-vertikal. Som standard tillämpas inkluderingsregler på rekommendationer för säkerhetskopiering.

>[!IMPORTANT]
>
>Du bör använda inkluderingsregler med försiktighet. De är användbara om er organisation till exempel har regler som kräver att ett varumärke inte rekommenderas medan ett annat varumärke visas. Men den här funktionen kostar en möjlighet. Du kan förlora en procentandel av en ökning genom att begränsa vissa objekt från att inte visas när de normalt visas av aktivitetskriterierna.

Inkluderingsreglerna kombineras med en AND. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Så här skapar du en enkel inkluderingsregel, som tidigare nämnts, som endast visar damskor som har en inventering på mer än 50 och ett pris på mellan 25 och 45 dollar:

1. Ange ett prisintervall för de produkter som du vill rekommendera.
1. Ange det minsta lagerbeloppet för de produkter som du vill rekommendera.
1. Konfigurera rekommendationen så att endast objekt visas när de uppfyller vissa villkor.

   ![](assets/Recs_InclusionRules.png)

   Du kan ange att objekt bara ska inkluderas när ett av attributen i listan uppfyller eller inte matchar ett eller flera angivna villkor.

   Vilka utvärderare som är tillgängliga beror på vilket värde du väljer i den första listrutan. Du kan lista flera objekt. Dessa objekt utvärderas med OR.

   Flera regler kombineras med en AND.

   >[!NOTE]
   >
   >Det här alternativet begränsar de objekt som visas i rekommendationen. Det påverkar inte vilka sidor som rekommendationen visas på. Om du vill begränsa var rekommendationen visas markerar du sidorna i upplevelsedispositionen.

Mer information finns i [Använda dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Överför CSV

1. Markera **[!UICONTROL Location]** innehållet i CSV-filen.

   ![Överför CSV-avsnitt](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   CSV-filen måste vara korrekt formaterad för att överföringen ska lyckas. Klicka **[!UICONTROL Download the CSV template]** för att hämta en korrekt formaterad CSV-fil.

   Det finns två platsalternativ:

   * **FTP:** Om du vill överföra din CSV-fil från en FTP-server markerar du **[!UICONTROL FTP]** och anger sedan nödvändig information. Du kan använda SSL, som använder FTPS-protokollet för att överföra CSV-filen på ett säkert sätt.
   * **URL:** Om du vill överföra din CSV-fil från en URL-adress väljer du **[!UICONTROL URL]** och anger sedan en feed-URL.

1. Klicka på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Anpassade villkorsenheter (rader) kan innehålla upp till 1 000 rekommenderade objekt (kolumner).

Uppdateringar av anpassade villkor är som standard&quot;kumulativa&quot;. Nya nyckelvärdepar som anges i CSV-överföringsfilen skriver över befintliga nyckelvärdepar. Befintliga nyckelvärdepar som inte har nycklar angivna i CSV-överföringen är fortfarande tillgängliga för leverans och upphör att gälla om 31 dagar från den tidpunkt då de senast överfördes som en del av CSV-filen.

Kontakta kundtjänst om du vill aktivera inställningen för att ignorera befintliga resultat som inte ingår i nästa CSV-överföring. Om den här inställningen är aktiverad är endast nycklarna i den anpassade CSV-feed-filen tillgängliga för leverans. Den här inställningen gäller för alla anpassade villkor.

Anpassade villkorsfeeds uppdateras en gång var 24:e timme.

Du kan se överförings- och synkroniseringsstatusen för dina anpassade villkorsuppladdningar längst ned på varje kriteriekort på sidan Recommendations > Villkor. Du kan även se statusen i dialogrutan Redigera när du redigerar egna villkor.

Flödet för en felfri överföring ska vara Schemalagd > Hämta feedfil > Importera > Slutförd.

Följande felmeddelanden är möjliga om [!DNL Target] ett problem med överföringen uppstår:

| Felmeddelande | Detaljer |
|--- |--- |
| Okänt fel | Anger ett internt tekniskt fel. |
| Tolkningsfel | Det finns troligen ett problem med feed-filformatet. Korrigera filformatet och spara om algoritmen, vilket startar filhämtningen igen. |
| Servern hittades inte | Ange ett IP- eller värdnamn som visas på Internet. |
| Fel i autentiseringsuppgifter | Ange en giltig användare och ett giltigt lösenord för ett aktivt konto på servern. |
| Katalogen hittades inte | Ange en katalog som finns på servern. |
| Filen hittades inte | Ange namnet på en fil som finns på servern i den angivna katalogen. |

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information (information om hur du överför anpassade villkor börjar vid 11:43):

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)