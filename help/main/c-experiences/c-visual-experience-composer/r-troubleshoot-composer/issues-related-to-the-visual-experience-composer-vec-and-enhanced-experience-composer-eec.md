---
keywords: Riktad;visuell upplevelsedisposition;vitlista;vit lista;tillåtelselista;tillåtelselista;förbättrad kompositör för visuell upplevelse;vec;felsök kompositör för visuell upplevelse;felsökning;eec;enhanced experience disser;tls;tls 1.2
description: Lär dig hur du felsöker problem som ibland kan uppstå i  [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) och [!UICONTROL Enhanced Experience Composer] (EEC) under vissa förhållanden.
title: Hur felsöker jag problem relaterade till [!UICONTROL Visual Experience Composer] och [!UICONTROL Enhanced Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%

---

# Felsökning av problem relaterade till [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] och [!UICONTROL Enhanced Experience Composer]

Visningsproblem och andra problem kan ibland uppstå i [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) och [!UICONTROL Enhanced Experience Composer] (EEC) under vissa villkor.

## Hur påverkar Google Chrome Samma webbplats regler för hur cookies tillämpas VEC? {#samesite}

+++Information
Tänk på de förändringar som påverkar VEC och EEC när du använder följande [!DNL Chrome]-versioner:

>[!NOTE]
>
>Följande ändring påverkar alla tre uppdateringarna som beskrivs nedan:
>
> * Kommer *inte* att kunna använda VEC utan [VEC Helper-tillägget](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) installerat och aktiverat för lösenordsskyddade sidor på dina platser. Dina cookies för webbplatsinloggning betraktas som cookies från tredje part och skickas inte med inloggningsbegäranden i VEC-redigeraren i [!UICONTROL Browse]-läge. Det enda undantaget är när webbplatsens inloggningscookies redan har attributen `SameSite=None` och `Secure` angivna.

**Chrome 94 (21 september 2021)**: Med de kommande förändringarna för Chrome 94 (21 september 2021) påverkar följande ändringar alla användare med webbläsarversioner från Chrome 94+:

* Kommandoradsflaggan `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` tas bort.

**Chrome 91 (25 maj 2021)**: Med de ändringar som implementerats för Chrome 91 (25 maj 2021) påverkar följande ändring alla användare med webbläsarversioner från Chrome 91+:

* Flaggorna `#same-site-by-default-cookies` och `#cookies-without-same-site-must-be-secure` har tagits bort från `chrome://flags`. Detta beteende är nu aktiverat som standard.

**Chrome 80 (augusti 2020)**: Med de ändringar som implementerades i augusti 2020 har alla användare med webbläsarversionerna Chrome 80+:

* Kommer *inte* att kunna hämta [!DNL Target] bibliotek när en aktivitet redigeras (när de inte redan finns på webbplatsen). Detta beror på att nedladdningsanropet görs från kunddomänen till en skyddad [!DNL Adobe]-domän och avvisas som oautentiserat.

* EEG-funktionen *fungerar inte* för alla användare eftersom den inte kan ange attributet SameSite för cookies på `adobemc.com domain`. Utan det här attributet avvisar webbläsaren dessa cookies, vilket gör att EEG misslyckas.

+++

### Kontrollera vilka cookies som är blockerade

+++Information
Använd [!DNL Developer Tools] i [!DNL Chrome] om du vill avgöra vilka cookies som blockeras på grund av samma webbplatsens principer för tvingande av cookies.

1. Om du vill komma åt [!DNL Developer Tools] när du visar VEC i [!DNL Chrome] klickar du på ikonen **[!UICONTROL ellipsis]** längst upp till höger i Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**.
1. Klicka på fliken **[!UICONTROL Network]** > och sök efter blockerade cookies.

   >[!NOTE]
   >
   >Använd kryssrutan **[!UICONTROL Has blocked cookies]** för att göra det enklare att hitta blockerade cookies.

+++

## Stöder [!DNL Target] iframes på flera nivåer?

+++Information
[!DNL Target] stöder inte iframes på flera nivåer. Om webbplatsen läser in en iframe som har en underordnad iframe, interagerar at.js endast med den överordnade iframe. [!DNL Target] bibliotek interagerar inte med den underordnade iframe-instansen.

Som en tillfällig lösning kan du lägga till en sida i upplevelsen med URL:en för den underordnade iframe-instansen.

+++

## När jag försöker redigera en sida ser jag bara en snurra istället för min sida. (VEC och EEC) {#section_313001039F79446DB28C70D932AF5F58}

+++Information
Detta kan inträffa om URL:en innehåller tecknet #. Om du vill åtgärda problemet växlar du till läget [!UICONTROL Browse] i VEC eller EEC och växlar sedan tillbaka till läget [!UICONTROL Compose]. Rotationsrutan ska flyttas och sidan ska läsas in.

+++

## CSP-rubriker (Content Security Policy) blockerar [!DNL Target]-bibliotek på min webbplats. (VEC och EEC) {#section_89A30C7A213D43BFA0822E66B482B803}


+++Information
Om webbplatsens CSP-rubriker blockerar [!DNL Target]-bibliotek läses webbplatsen in, men förhindrar redigering, kontrollerar du att [!DNL Target]-biblioteken inte blockeras.

>[!NOTE]
>
>Utöver följande information kan du använda webbläsartillägget [Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) för [!DNL Google Chrome].

![cps_headers, bild](assets/cps_headers.png)

Som en tillfällig lösning kan du konfigurera en [!DNL Requestly]-regel så att CSP-rubriker tas bort, vilket visas nedan:

![cps_headers_2 image](assets/cps_headers_2.png)

Du kan konfigurera en liknande [!DNL Requestly]-regel för en rubrik som gör att en resurs inte läses in i VEC.

Om du behöver ta bort rubriker i [!DNL Requestly] bör du göra något av följande:

* Lägg till URL-regler för den URL-adress som du vill öppna i VEC så att rubriker bara tas bort för dessa URL-adresser.
* Aktivera regeln när du redigerar i VEC och inaktivera regeln när du inte använder VEC.

+++

## VEC eller EEC verkar vara brutna eller initieras inte när en sparad aktivitet redigeras om. (VEC och EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

+++Information
Om webbplatsen har ändrats utanför VEC efter det att upplevelsen definierades, går det inte att hitta väljare för vilka åtgärder har vidtagits tidigare när aktiviteten öppnas för redigering igen. Sidan visas som bruten och ingen varning visas.

+++

## VEC eller EEC visar inte mina roterande banners och annat innehåll som innehåller JavaScript. (VEC och EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

+++Information
Som standard blockerar VEC JavaScript-element. Du kan arbeta med dessa element om du inaktiverar JavaScript. Beroende på hur webbplatsen är konfigurerad kan vissa objekt fortsätta att visas felaktigt eller vara otillgängliga.

+++

## När jag ändrar ett element på sidan ändras flera element. (VEC och EEC) {#section_309188ACF34942989BE473F63C5710AF}

+++Information
Om samma DOM-element-ID används för flera element på sidan ändras alla element med det ID:t om du ändrar ett av elementen. För att förhindra detta bör ett ID bara användas en gång på varje sida. Det här är en vanlig HTML-praxis. Mer information finns i [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

+++

## Jag kan inte redigera upplevelser för en iFrame-busting-webbplats. (VEC och EEC) {#section_9FE266B964314F2EB75604B4D7047200}

+++Information
Detta problem kan åtgärdas genom att aktivera [!UICONTROL Enhanced Experience Composer] (EEC). Klicka på **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]** och markera sedan kryssrutan som aktiverar [!UICONTROL Enhanced Experience Composer]. EEG använder en [!DNL Adobe]-hanterad proxy för att läsa in din sida för redigering. Den här proxyn tillåter redigering på iFrame-busting-platser och tillåter redigering på webbplatser och sidor där du ännu inte har lagt till [!DNL Adobe Target]-kod. Aktiviteterna levererar inte till webbplatsen förrän koden har lagts till. Vissa sajter kanske inte laddas via EEG, och då kan du avmarkera alternativet för att ladda EEG via en iFrame.

>[!NOTE]
>
>Dina lokalt värdbaserade sidor eller sidor som inte är tillgängliga utanför nätverket är inte tillgängliga för proxyservern [!DNL Adobe] och kan inte öppnas i EEG. De här sidorna kan vara mellanlagrings-URL:er, UAT-URL:er (User Acceptance Testing) eller lokala värdsidor.

+++

## Jag vill konfigurera tester på sidor som inte har mbox/[!DNL Target]-implementeringen klar ännu. (VEC och EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

+++Information
Se&quot;Jag kan inte redigera upplevelser för en iFrame-bursting-webbplats&quot; ovan.

+++

## Fet och kursiv text med [!UICONTROL Edit Text]/[!UICONTROL Edit HTML] eller [!UICONTROL Change Text]/[!DNL Change HTML] visas inte på min sida. Ibland försvinner texten när du har använt de här formatändringarna. (VEC och EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

+++Information
Om du använder **[!UICONTROL Edit Text]/[!UICONTROL Edit HTML]** i VEC för [!UICONTROL A/B Test]- eller [!UICONTROL Experience Targeting]-aktiviteter eller **[!UICONTROL Change Text]/[!UICONTROL Change HTML]** för [!UICONTROL Automated Personalization] - eller [!UICONTROL Multivariate Test]-aktiviteter för att göra text fet eller kursiv, kanske dessa format inte används på sidan eller så försvinner texten från sidan i VEC. Det beror på hur RTF-redigeraren använder formaten och kan påverka webbplatsens kod.

Om du ser detta problem:

1. Klicka på knappen **[!UICONTROL HTML]** i RTF-redigeraren för att öppna källredigeringsläget.
1. Hitta formatets textelement.

   * Ändra `<strong>`-element till `<b>` för fetstil.

   * Ändra `<em>`-element till `<i>` för kursiv text.

+++

## När det gäller Automated Personalization-aktiviteter är bildbytet brutet i VEC eller EEC. (VEC och EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

+++Information
Om du lägger till ett bilderbjudande på en plats får du hela dimensionen av det ursprungliga bildutrymmet i VEC eller EEC. Vid leverans är bilden inte utökad och visas som den är, så det påverkar inte leveransen.

+++
