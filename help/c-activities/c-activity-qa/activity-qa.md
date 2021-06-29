---
keywords: qa;qa mode; aktivitet qa;qa url;qa urls;preview url;preview url;preview url
description: Lär dig använda Adobe [!DNL Target] QA-URL:er för att utföra enkel QA-analys från början till slut med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från liveaktivitetsdata.
title: Hur gör jag QA-aktiviteter?
feature: Verksamhet
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 0d24bcf335980291891e3198a13ec283d1dd325f
workflow-type: tm+mt
source-wordcount: '1686'
ht-degree: 0%

---

# Aktivitets-QA

Använd QA-URL:er i [!DNL Adobe Target] för att utföra enkel QA för hela aktiviteten med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från live-aktivitetsdata.

[!UICONTROL Activity QA] gör att du kan testa dina  [!DNL Target] aktiviteter innan du startar dem live. Funktionen [!UICONTROL Activity QA] innehåller:

* Länkar att dela med teammedlemmar som aldrig behöver ändras eller behöver genereras om, oavsett vilka uppdateringar som gjorts för upplevelserna eller aktiviteterna. Med den här funktionen kan du testa dina aktiviteter fullständigt under hela användarresan.
* Målgruppsvillkor kan respekteras så att marknadsförarna kan testa målinriktningskriterier eller ignorera målinriktningskriterier för att få QA att visa hur upplevelserna ser ut utan att behöva uppfylla målgruppsvillkoren.
* QA-rapportering samlas in så att marknadsförarna kan bekräfta att mätvärdena ökar som förväntat och att QA-rapportdata hålls åtskilda från produktionsrapporter (för icke-A4T-rapportering).
* Möjlighet att förgranska en upplevelse separat eller med andra aktiva aktiviteter som uppfyller leveranskriterierna (sid/målbegäran/målgrupp).
* Möjlighet att köra QA under hela användarresan. Du kan komma åt din webbplats en gång med QA-länken och sedan bläddra på hela webbplatsen i Activity QA. Du stannar kvar i Activity QA tills du avslutar sessionen eller tills du använder bokmärket [QA Target](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) för att tvinga dig ut ur [!UICONTROL Activity QA]. Den här funktionen är användbar om du har en aktivitet som sträcker sig över flera webbsidor.

   >[!NOTE]
   >
   >Den här funktionen gäller för at.js-implementeringar med version 2.*Exportera* senare. För at.js 1.*För* implementeringar gäller den här funktionen bara om besökarens webbläsare inte blockerar cookies från tredje part.

## Åtkomst till och delning av en QA-URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. Klicka på länken **[!UICONTROL Activity QA]** på sidan [!UICONTROL Overview] för en aktivitet.

   ![Länk till aktivitets-QA](assets/qa_link.png)

1. Konfigurera följande inställningar:

   ![Konfigurationsalternativ för QA-länk](assets/qa_link_config.png)

   * **[!UICONTROL Match audience rules to see experiences]:** Ibland vill du bekräfta att målgruppsmatchningen fungerar. Andra gånger vill du kontrollera aktivitetens utseende och känsla. Om den här inställningen är aktiverad måste testarna uppfylla målinriktningskraven för att kunna se upplevelserna. För XT-aktiviteter (Experience Targeting) anges en enda aktivitets-URL. Den upplevelse du ser bestäms av om du kvalificerar dig för en av målinriktningsreglerna.

      Om den här inställningen har växlats till&quot;av&quot;-positionen, kan du klicka på länkarna för att visa upplevelserna oavsett om du kvalificerar dig eller inte. När du utför QA kan du växla fram och tillbaka mellan att kräva eller inte kräva att målgruppsanpassningen respekteras.

   * **Visa standardinnehåll för alla andra aktiviteter:** Om det här alternativet är aktiverat visas standardinnehåll för alla andra aktiviteter. Förhandsgranskningen visas till exempel separat utan hänsyn till alla andra aktiva aktiviteter på samma sida/[!DNL Target]-begäran.

      Om den här inställningen är inaktiverad bör du tänka på följande:

      * Om det finns kollisioner mellan aktiviteten som du testar och andra aktiva aktiviteter gäller [normala prioritetsregler](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F). På grund av kollisioner är det möjligt att du inte kan se aktiviteten som du avser att göra till en kvalitetskontroll.
      * Ökning av mätvärden för de visade aktiviteterna, men endast i QA-rapporteringsmiljön.

1. Klicka på **[!UICONTROL Done]** för att spara ändringarna.
1. Dela URL:er för aktivitetslänken med medlemmar i organisationen för testning.

   Aktivitetslänkar upphör aldrig att gälla och du behöver inte skicka om länkar om någon ändrar en aktivitet eller upplevelse. Om du däremot använder en annan målgrupp än [!UICONTROL Audience Library], i stället för att bara redigera aktiviteten, skapas en ny länk som du måste dela om.

   Varje URL för aktivitetslänk (för Experience A, Experience B o.s.v.) gör att du kan starta användarresan från motsvarande upplevelse. Klicka på den URL som genererats för en upplevelse och fortsätt sedan med vanlig surfning för att se upplevelser på flera sidor (om det finns flera sidor). Endast en URL genereras per upplevelse, även om upplevelsen sträcker sig över flera sidor (malltestning eller flersidig testning).

   Du kan navigera på webbplatsen om du vill se de andra sidorna eftersom läget [!UICONTROL Activity QA] är fast. Detta gäller för at.js-implementeringar med version 2.*Exportera* senare. För at.js 1.*För* implementeringar gäller detta bara om besökarens webbläsare inte blockerar cookies från tredje part.

1. Om du vill visa rapporter som skapats från aktivitetslänkens URL:er klickar du på aktivitetens **[!UICONTROL Reports]**-sida, klickar på ikonen **[!UICONTROL Settings]** ( ![](assets/icon_gear.png)) och väljer sedan **[!UICONTROL QA Mode Traffic]** i listrutan **[!UICONTROL Environment]**.

## Överväganden {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* Länken [!UICONTROL Activity QA] visas på sidan [!UICONTROL Overview] för alla aktivitetstyper utom för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] (AP).
* [!UICONTROL Activity QA] det går inte att läsa in förhandsgranskningslänkar för sparade aktiviteter om det finns för många sparade aktiviteter på ditt konto. Det bör fungera att försöka återanvända förhandsvisningslänkarna. Om du vill förhindra att den här situationen fortsätter att inträffa arkiverar du sparade aktiviteter som inte längre används aktivt.
* [!UICONTROL Activity QA] URL:er är tillgängliga med aktiviteter med Analytics som rapportkälla (A4T). Träffar som genereras när du utför QA med [!UICONTROL Activity QA]-flöde till samma rapportsvit där aktivitetens data flödar även efter att aktiviteten publiceras.
* [!UICONTROL Activity QA] visar inte innehåll för arkiverade aktiviteter eller aktiviteter som ligger efter slutdatumet. Om du inaktiverar en avslutad aktivitet måste du spara aktiviteten igen för att [!UICONTROL Activity QA] ska fungera.
* Aktiviteter som importeras till [!DNL Target Standard/Premium] (från till exempel [!DNL Target Classic]) stöder inte URL:er för kvalitetssäkring.
* I [!UICONTROL Auto-Allocate]- och [!UICONTROL Recommendations]-aktiviteter påverkas inte modellen av de besök som gjordes i [!UICONTROL Activity QA].
* [!UICONTROL Activity QA] är klibbig. När du har bläddrat på en webbplats i [!UICONTROL Activity QA] måste din [!DNL Target]-session upphöra att gälla eller du måste ha en [!DNL Target]-release från [!UICONTROL Activity QA] innan du kan visa webbplatsen som en vanlig besökare. Använd [Mål-QA-bokmärket](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) för att tvinga dig ut ur [!UICONTROL Activity QA].

   Du kan också tvinga dig ut manuellt genom att läsa in en sida på webbplatsen med parametern `at_preview_token` med ett tomt värde (till exempel `https://www.mysite.com/?at_preview_token=`).

* Om du angav &quot;URL is&quot; när du skapade aktiviteten [förbättringar i den formulärbaserade dispositionen](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) eller [alternativen för sidleverans i Visual Experience Composer)](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), fungerar inte QA-URL:en eftersom [!UICONTROL Activity QA] lägger till URL-parametrar. Du löser det här problemet genom att klicka på QA-URL:en för att gå till webbplatsen, ta bort de tillagda parametrarna från URL:en och sedan läsa in den nya URL:en.
* Om du har .js 1.*x*,  [!UICONTROL Activity QA] mode är inte tilltalande om du använder Safari eller en annan webbläsare som blockerar cookies från tredje part. I dessa fall måste du lägga till förhandsgranskningsparametrarna i varje URL som du navigerar till. Detsamma gäller om du har implementerat [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md).
* Om en aktivitet använder flera upplevelsemålgrupper (till exempel en amerikansk och brittisk webbplats som ingår i samma aktivitet) genereras inte QA-länkar för de fyra kombinationerna (Experience A/US Site, Experience A/UK Site, Experience B/US Site, Experience B/UK Site). Endast två QA-länkar (Experience A och Experience B) skapas, och användarna måste kvalificera sig för att rätt målgrupp ska kunna se sidan. En brittisk QA-person kan inte se den amerikanska webbplatsen.
* Alla `at_preview`-parametrar och värden är redan URL-kodade. För det mesta fungerar allt som förväntat. Vissa kunder måste dock läsa in utjämnare eller webbservrar som försöker koda frågesträngsparametrarna igen.

   På grund av den här dubbla kodningen går det inte att extrahera rätt tokenvärde när [!DNL Target] försöker avkoda `at_preview_token`, vilket resulterar i att förhandsvisningen inte fungerar.[!DNL Target]

   Adobe rekommenderar att du pratar med IT-avdelningen för att säkerställa att alla förhandsgranskningsparametrar är tillåtslista så att dessa värden inte förändras på något sätt.

   I följande tabell visas de parametrar som kan tillåtslista i din domän:

   | Parameter | Typ | Värde | Beskrivning |
   |--- |--- |--- |--- |
   | `at_preview_token` | Krypterad sträng | Obligatoriskt. inget standardvärde | En krypterad entitet som innehåller listan över kampanj-ID:n som kan köras i QA-läge. |
   | `at_preview_index` | Sträng | Tom | Parameterns format är `<campaignIndex>` eller `<campaignIndex>_< experienceIndex>`<br>Båda indexen börjar med 1. |
   | `at_preview_listed_activities_only` | Boolean (true/false) | Standardvärde: false | Om värdet är &quot;true&quot; bearbetas alla kampanjer som anges i `at_preview_index`-parametrarna.<br>Om värdet är &quot;false&quot; bearbetas alla kampanjer från sidan, även om de inte har angetts i förhandsgranskningstoken. |
   | `at_preview_evaluate_as_true_audience_ids` | Sträng | Tom | Understreckavgränsad (&quot;_&quot;) lista med segment-ID:n som alltid (på målinriktning och på rapporteringsnivå) ska utvärderas som &quot;true&quot; i omfånget för [!DNL Target]-begäran. |
   | `_AT_Debug` | Sträng | Fönster eller konsol | Konsolloggning eller nytt fönster. |
   | `adobe_mc_ref` |  |  | Skickar den refererande URL-adressen för standardsidan till den nya sidan. När det används med `AppMeasurement.js` version 2.1 (eller senare) använder [!DNL Adobe Analytics] det här parametervärdet som den refererande URL:en på den nya sidan. |
   | `adobe_mc_sdid` |  |  | Skickar [!DNL Supplemental Data Id] (SDID) och [!DNL Experience Cloud Org Id] från standardsidan till den nya sidan. Om du skickar dessa ID:n kan [!UICONTROL Analytics for Target] (A4T) sammanfoga [!DNL Target]-begäran på standardsidan med [!DNL Analytics]-begäran på den nya sidan. |

* Gränssnittet [!UICONTROL Target QA Mode] visar bara den första URL:en för en upplevelse i en flersidig aktivitet. Anta att du skapar ett resetest och går från URL1 till URL2. Om du vill gå till URL2 separat kopierar du alla URL-parametrar som finns mot URL1 och använder dem på URL2 efter att du har placerat ett &quot;?&quot; precis som i URL1.

## Kompatibilitet med mål-JavaScript-bibliotek [!UICONTROL QA Mode]

[!DNL Target] stöder följande JavaScript-bibliotek:

* [at.js 1.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

I följande tabell visas de olika aktivitetstyperna och om [!UICONTROL Activity QA]-läget stöds för varje bibliotek:

| Typ av aktivitet | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | Ja | Ja | Ja |
| [!UICONTROL Auto-Allocate] | Ja | Ja | Ja |
| [!UICONTROL Auto-Target] | Nej | Nej | Nej |
| [!UICONTROL Automated Personalization] (AP) | Nej | Nej | Nej |
| [!UICONTROL Experience Targeting] (XT) | Ja | Ja | Ja |
| [!UICONTROL Multivariate Test] (MVT) | Ja | Ja | Ja |
| [!UICONTROL Recommendations] | Ja | Ja | Ja |

## Förhandsgranska URL:er {#preview}

URL:er för förhandsgranskning kan genereras för alla [!DNL Target]-aktivitetstyper. Med förhandsgransknings-URL:er kan du visa innehåll direkt på webbplatsen innan aktiviteten är aktiv för förhandsgranskning och kvalitetskontroll. Förhandsgranska URL:er utan att ange målinriktning för att framtvinga visning av en viss upplevelse.

Mer information om hur förhandsgransknings-URL:er fungerar med [!UICONTROL Automated Personalization] (AP)-aktiviteter finns i [Förhandsgranska Automated Personalization-aktiviteter med förhandsgransknings-URL:er](/help/c-activities/t-automated-personalization/experience-preview.md).

Om du vill få åtkomst till och dela en förhandsgransknings-URL från en aktivitets **[!UICONTROL Overview]**-sida klickar du på länken **[!UICONTROL Activity QA]**.

>[!NOTE]
>
>Länken [!UICONTROL Activity QA] och förhandsgransknings-URL:en är desamma för alla aktiviteter utom [!DNL Target] AP-aktiviteter.

I följande tabell visas de olika aktivitetstyperna och om funktionen för förhandsgransknings-URL:er stöds för varje bibliotek eller API:

| Typ av aktivitet | at.js 1.x | at.js 2.x | Platform Web SDK | Leverans-API | Admin-API |
| --- | --- | --- | --- | --- | --- |
| [!UICONTROL A/B Test] | Ja | Ja | Ja | Ej tillämpligt | Ja |
| [!UICONTROL Auto-Allocate] | Ja | Ja | Ja | Ej tillämpligt | Ja |
| [!UICONTROL Auto-Target] | Ja | Ja | Ja | Ej tillämpligt | Ja |
| [!UICONTROL Automated Personalization] (AP) | Ja | Ja | Nej | Ej tillämpligt | Ja |
| [!UICONTROL Experience Targeting] (XT) | Ja | Ja | Ja | Ej tillämpligt | Ja |
| [!UICONTROL Multivariate Test] (MVT) | Ja | Ja | Ja | Ej tillämpligt | Ja |
| [!UICONTROL Recommendations] | Ja | Ja | Ja | Ej tillämpligt | Ja |






