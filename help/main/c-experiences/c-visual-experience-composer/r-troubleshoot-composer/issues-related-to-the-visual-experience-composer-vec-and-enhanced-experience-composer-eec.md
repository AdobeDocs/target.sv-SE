---
keywords: Riktad;visuell upplevelsedisposition;vitlista;vit lista;tillåtelselista;tillåtelselista;förbättrad kompositör för visuell upplevelse;vec;felsök kompositör för visuell upplevelse;felsökning;eec;enhanced experience disser;tls;tls 1.2
description: Lär dig hur du felsöker problem som ibland kan uppstå i Adobe [!DNL Target] Visual Experience Composer (VEC) och Enhanced Experience Composer (EEC) under vissa förhållanden.
title: Hur felsöker jag problem som rör Visual Experience Composer och Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: d3e6ec7fc65bde2c82f830111d40622cd8bc8a4d
workflow-type: tm+mt
source-wordcount: '1389'
ht-degree: 0%

---

# Felsökning relaterade till [!UICONTROL Visual Experience Composer] och [!UICONTROL Enhanced Experience Composer]

Visningsproblem och andra problem kan förekomma i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) och [!UICONTROL Enhanced Experience Composer] (EEG) på vissa villkor.

## Hur påverkar Google Chrome SameSite cookie-reglerna VEC och EEC? {#samesite}

Tänk på de förändringar som påverkar VEC och EEC när du använder följande Chrome-versioner:

>[!NOTE]
>
>Följande ändring påverkar alla tre uppdateringarna som beskrivs nedan:
>
> * Will *not* kan använda VEC utan VEC Helper-tillägget installerat och aktiverat för lösenordsskyddade sidor på dina webbplatser. Dina cookies för webbplatsinloggning betraktas som cookies från tredje part och skickas inte med inloggningsbegäranden i VEC-redigeraren i bläddringsläge. Det enda undantaget är när webbplatsens inloggningscookies redan har `SameSite=None` och `Secure` attribut.


**Chrome 94 (21 september 2021)**: Med de kommande förändringarna för Chrome 94 (21 september 2021) påverkar följande ändring alla användare med Chrome 94+-webbläsarversioner:

* Kommandoradsflaggan `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` tas bort.

**Chrome 91 (25 maj 2021)**: Med de ändringar som implementerats för Chrome 91 (25 maj 2021) påverkar följande ändring alla användare med webbläsarversionen Chrome 91+:

* Flaggorna `#same-site-by-default-cookies` och `#cookies-without-same-site-must-be-secure` har tagits bort från `chrome://flags`. Detta beteende är nu aktiverat som standard.

**Chrome 80 (augusti 2020)**: Med de ändringar som implementerades i augusti 2020 har alla användare med webbläsarversionen Chrome 80+:

* Will *not* kan ladda ned [!DNL Target] bibliotek när en aktivitet redigeras (när de inte redan finns på webbplatsen). Detta beror på att nedladdningsanropet görs från kundens domän mot en skyddad [!DNL Adobe] och nekas som ej autentiserad.
* EEG kommer att *not* för alla användare eftersom det inte går att ange attributet SameSite för cookies på `adobemc.com domain`. Utan det här attributet avvisar webbläsaren dessa cookies, vilket gör att EEG misslyckas.

### Kontrollera vilka cookies som är blockerade

Om du vill ta reda på vilka cookies som blockeras på grund av samma principer för att genomdriva cookies på samma webbplats använder du utvecklingsverktygen i Chrome.

1. Klicka på knappen **[!UICONTROL ellipsis]** ikonen längst upp till höger i Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**.
1. Klicka på **[!UICONTROL Network]** och sedan leta efter blockerade cookies.

   >[!NOTE]
   >
   >Använd **[!UICONTROL Has blocked cookies]** för att göra det enklare att hitta blockerade cookies.

   I följande bild visas en blockerad cookie:

   ![Utvecklarverktyg > fliken Nätverk med en blockerad cookie](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] VEC Helper extension

Från och med version 0.7.1 [!DNL Adobe Target] VEC Helper-webbläsartillägget lägger till `SameSite=None` och `Secure` attribut till alla cookies i svar som kommer från webbsidor som redigeras inuti VEC när växeln&quot;Cookies&quot; är PÅ i tilläggsgränssnittet:

![Adobe Target VEC Helper extension UIAdobe Target VEC Helper extension UI](assets/cookies-vec-helper.png)

### Alternativ och tillfälliga lösningar

Använd något av följande alternativ för att säkerställa att ditt VEC och EEC fortsätter att fungera som förväntat:

* Ladda ned och använd den uppdaterade [VEC Helper extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en).
* Använd webbläsaren Mozilla Firefox. Firefox tillämpar inte den här principen ännu.
* Använd följande flaggor för att köra Google Chrome från kommandoraden till och med 21 september 2021. Efter den 21 september kommer funktioner som kräver cookies inte längre att fungera i VEC, som inloggning eller popup-fönster med cookie-samtycke. Om du uppdaterar till Chrome 94 måste du generera cookies manuellt med `SameSite=none` och `Secure` på era webbplatser.

   ```
   --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
   ```

## Gör [!DNL Target] stöder iframes på flera nivåer?

[!DNL Target] stöder inte iframes på flera nivåer. Om webbplatsen läser in en iframe som har en underordnad iframe, interagerar at.js endast med den överordnade iframe. [!DNL Target] Biblioteken samverkar inte med den underordnade iframe-instansen.

Som en tillfällig lösning kan du lägga till en sida i upplevelsen med URL:en för den underordnade iframe-instansen.

## När jag försöker redigera en sida ser jag bara en snurra istället för min sida. (VEC och EEC) {#section_313001039F79446DB28C70D932AF5F58}

Detta kan inträffa om URL:en innehåller tecknet #. Åtgärda problemet genom att växla till bläddringsläge i Visual Experience Composer och sedan växla tillbaka till Compose-läge. Rotationsrutan ska flyttas och sidan ska läsas in.

## CSP-rubriker (Content Security Policy) blockerar [!DNL Target] bibliotek på min webbplats. (VEC och EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

Om webbplatsens CSP-rubriker blockerar Target-bibliotek läses webbplatsen in, men förhindrar redigering, kontrollerar du att Target-biblioteken inte blockeras.

>[!NOTE]
>
>Förutom följande information kan du använda [Webbläsartillägg för Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) för Google Chrome.

![](assets/cps_headers.png)

Som en tillfällig lösning kan du konfigurera en regel för att begära att ta bort CSP-rubriker, så som visas nedan:

![](assets/cps_headers_2.png)

Du kan konfigurera en liknande begäranderegel för en rubrik som gör att en resurs inte läses in i VEC.

Om du vill ta bort rubriker ska du göra något av följande:

* Lägg till URL-regler för den URL-adress som du vill öppna i VEC så att rubriker bara tas bort för dessa URL-adresser.
* Aktivera regeln när du redigerar i VEC och inaktivera regeln när du inte använder VEC.

## VEC eller EEC verkar vara brutna eller initieras inte när en sparad aktivitet redigeras om. (VEC och EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Om webbplatsen har ändrats utanför Visual Experience Composer efter att upplevelsen har definierats, går det inte att hitta väljare för vilka åtgärder har vidtagits tidigare när aktiviteten öppnas för redigering igen. Sidan visas som bruten och ingen varning visas.

## VEC eller EEC visar inte mina roterande banners och annat innehåll som innehåller JavaScript. (VEC och EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

Som standard blockerar Visual Experience Composer JavaScript-element. Du kan arbeta med dessa element om du inaktiverar JavaScript i inställningarna för Visual Experience Composer. Beroende på hur webbplatsen är konfigurerad kan vissa objekt fortsätta att visas felaktigt eller vara otillgängliga.

## När jag ändrar ett element på sidan ändras flera element. (VEC och EEC) {#section_309188ACF34942989BE473F63C5710AF}

Om samma DOM-element-ID används för flera element på sidan ändras alla element med det ID:t om du ändrar ett av elementen. För att förhindra detta bör ett ID bara användas en gång på varje sida. Detta är en standardmetod som är HTML bästa. Mer information finns i [Scenarier för sidändring](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Jag kan inte redigera upplevelser för en iFrame-busting-sajt. (VEC och EEC) {#section_9FE266B964314F2EB75604B4D7047200}

Problemet kan åtgärdas genom att du aktiverar Förbättrad Experience Composer. Klicka **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]** markerar du sedan kryssrutan Förbättrad Experience Composer. Förbättrad Experience Composer använder en Adobe-hanterad proxy för att läsa in sidan för redigering. Med den här proxyn kan du redigera på iFrame-busting-platser och redigera på webbplatser och sidor där du ännu inte har lagt till Adobe Target-kod. Aktiviteterna levererar inte till webbplatsen förrän koden har lagts till. Vissa webbplatser kanske inte läses in via Förbättrad Experience Composer. I så fall kan du avmarkera det här alternativet för att läsa in Visual Experience Composer via en iFrame.

>[!NOTE]
>
>Dina lokalt lagrade sidor eller sidor som inte är tillgängliga utanför nätverket är inte tillgängliga för proxyservern i Adobe och kan inte öppnas i EEG. De här sidorna kan vara mellanlagrings-URL:er, UAT-URL:er (User Acceptance Testing) eller lokala värdsidor.

## Jag vill konfigurera tester på sidor som inte har mbox/target-implementeringen klar ännu. (VEC och EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

Se&quot;Jag kan inte redigera upplevelser för en iFrame-bursting-sajt&quot; ovan.

## Fet och kursiv text med Redigera text/HTML eller Ändra text/HTML visas inte på min sida. Ibland försvinner texten när du har använt de här formatändringarna. (VEC och EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

Om du använder **[!UICONTROL Edit Text/HTML]** i Visual Experience Composer för A/B- eller Experience Targeting-aktiviteter eller **[!UICONTROL Change Text/HTML]** för Automated Personalization- eller Multivariate Test-aktiviteter för att göra text fet eller kursiv kanske dessa format inte används på sidan eller så försvinner texten från sidan i Visual Experience Composer. Det beror på hur RTF-redigeraren använder formaten och kan påverka webbplatsens kod.

Om du ser detta problem:

1. Klicka på **[!UICONTROL HTML]** i textredigeraren för att gå till källredigeringsläge.
1. Hitta formatets textelement.

   * Ändra för fet text `<strong>` element till `<b>`.

   * Ändra för kursiv text `<em>` element till `<i>`.

## När det gäller Automated Personalization-aktiviteter är bildbytet brutet i VEC eller EEC. (VEC och EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

Om du lägger till ett bilderbjudande på en plats får du hela dimensionen av det ursprungliga bildutrymmet i VEC eller EEC. Vid leverans är bilden inte utökad och visas som den är, så det påverkar inte leveransen.
