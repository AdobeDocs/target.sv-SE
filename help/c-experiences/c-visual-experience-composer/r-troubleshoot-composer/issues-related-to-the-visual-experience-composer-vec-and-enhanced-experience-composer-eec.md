---
keywords: Targeting;visual experience composer;whitelist;white list;allowlist;allow list;enhanced visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;eec;enhanced experience composer;tls;tls 1.2
description: Visningsproblem kan ibland uppstå i Visual Experience Composer (VEC) och Enhanced Experience Composer (EEC) under vissa förhållanden.
title: Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer
feature: vec
uuid: 93f646d9-fcbc-43f0-9f84-0ce8e486ff7f
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 0%

---


# Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer{#troubleshooting-issues-related-to-the-visual-experience-composer-and-enhanced-experience-composer}

Visningsproblem och andra problem kan ibland uppstå i Visual Experience Composer (VEC) och Enhanced Experience Composer (EEC) under vissa förhållanden.

## Hur påverkar den nyligen lanserade policyn för tillämpning av Google Chrome SameSite-cookies VEC? {#samesite}

Med de senaste ändringarna (augusti 2020) har alla användare med webbläsarversionen Chrome 80+:

* Kan *inte* använda VEC (med eller utan VEC Helper-tillägget installerat och aktiverat) på lösenordsskyddade sidor på sina webbplatser. Detta beror på att deras cookies för webbplatsinloggning kommer att betraktas som en cookie från tredje part och inte skickas med inloggningsbegäran. Det enda undantaget är när inloggningscookien för kundplatsen redan har parametern SameSite inställd på &quot;none&quot;.
* Kommer *inte* att kunna hämta [!DNL Target] bibliotek när du redigerar en aktivitet (när dessa inte redan finns på webbplatsen). Detta beror på att nedladdningsanropet görs från kundens domän mot en skyddad Adobe-domän och avvisas som oautentiserat.
* EEC fungerar *inte* för alla användare eftersom det inte går att ange attributet SameSite för cookies `adobemc.com domain`. Utan det här attributet kommer webbläsaren att avvisa dessa cookies, vilket gör att EEG misslyckas.

Adobe har skickat ett uppdaterat VEC Helper-tillägg till Google Chrome Store. Det här tillägget skriver över cookie-attributen för att ställa in `SameSite="none"` attributet vid behov. Det [uppdaterade tillägget finns här](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en). Mer information om hur du installerar och använder VEC Helper Extension finns i [hjälptillägget](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)för Visual Experience Composer.

För dina egna webbplatscookies måste du ange cookies efter namn. Växla skjutreglaget åt [!UICONTROL Cookie] positionen och ange sedan cookien efter namn och cookie-domän. Cookie-namnet är &quot;mbox&quot; och cookie-domänen är den andra och översta nivån i domänerna som du använder för mbox. Eftersom cookie används av ditt företags domän är den en cookie från första part. Exempel: `mycompany.com`. Mer information finns i [Adobe Target Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) i användarhandboken *för* Experience Cloud-gränssnittet.

![Cookies i VEC-hjälptillägget](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### Alternativ och tillfälliga lösningar

Använd något av följande alternativ för att säkerställa att ditt VEC och EEC fortsätter att fungera som förväntat:

* Ladda ned och använd det uppdaterade [VEC Helper-tillägget](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en).
* Använd webbläsaren Mozilla Firefox. Firefox tillämpar inte den här principen ännu.
* Fortsätt använda Chrome, men ange `chrome://flags/#same-site-by-default-cookies` flaggan till Inaktiverad.

   >[!NOTE]
   >
   >Detta räcker *inte* om cookies redan har attributet SameSite inställt på &quot;Lax&quot; eller &quot;Strict&quot; från servern.

## Stöder Target iframes på flera nivåer?

Målet stöder inte iframes på flera nivåer. Om webbplatsen läser in en iframe som har en underordnad iframe, samverkar Target-biblioteken (at.js och mbox.js) endast med den överordnade iframe-instansen. Målbiblioteken samverkar inte med den underordnade iframe-instansen.

Som en tillfällig lösning kan du lägga till en sida i upplevelsen med URL:en för den underordnade iframe-instansen.

## När jag försöker redigera en sida ser jag bara en snurra istället för min sida. (VEC och EEC) {#section_313001039F79446DB28C70D932AF5F58}

Det här kan hända om URL:en innehåller tecknet #. Åtgärda problemet genom att växla till bläddringsläge i Visual Experience Composer och sedan växla tillbaka till Compose-läge. Rotationsrutan ska flyttas och sidan ska läsas in.

## CSP-rubriker (Content Security Policy) blockerar Target-biblioteken på min webbplats. (VEC och EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

Om webbplatsens CSP-rubriker blockerar Target-bibliotek läses webbplatsen in, men förhindrar redigering, kontrollerar du att Target-biblioteken inte blockeras.

>[!NOTE]
>
>Utöver följande information kan du använda webbläsartillägget [](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) Adobe Target VEC Helper för Google Chrome.

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

## Min target.js-fil på värdservern kan inte läsas in vid efterföljande sidomladdningar. (VEC och EEC) {#section_87F6418C2CD142A7B4D1E7037935F81F}

Problemet inträffar när kunderna har en mbox.js-version som är tidigare än 57 (d.v.s. version 56 eller tidigare).

Vi rekommenderar att alla VEC-användare uppgraderar till den [senaste versionen av mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A), eller åtminstone uppgraderar till version 57. Du bör också överväga [att göra övergången till at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).

## När jag ändrar ett element på sidan ändras flera element. (VEC och EEC) {#section_309188ACF34942989BE473F63C5710AF}

Om samma DOM-element-ID används för flera element på sidan ändras alla element med det ID:t om du ändrar ett av elementen. För att förhindra detta bör ett ID bara användas en gång på varje sida. Det här är en vanlig HTML-praxis. Mer information finns i Scenarier för [sidändring](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Jag kan inte redigera upplevelser för en iFrame-busting-sajt. (VEC och EEC) {#section_9FE266B964314F2EB75604B4D7047200}

Problemet kan åtgärdas genom att du aktiverar Förbättrad Experience Composer. Klicka **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]** och markera sedan kryssrutan som aktiverar Förbättrad Experience Composer. Förbättrad Experience Composer använder en Adobe-hanterad proxy för att läsa in sidan för redigering. Detta gör att du kan redigera på iFrame-busting-webbplatser och redigera på webbplatser och sidor där du ännu inte har lagt till Adobe Target-kod. Aktiviteterna levererar inte till webbplatsen förrän koden har lagts till. Vissa webbplatser kanske inte läses in via Förbättrad Experience Composer. I så fall kan du avmarkera det här alternativet för att läsa in Visual Experience Composer via en iFrame. []

>[!NOTE]
>
>Dina lokalt lagrade sidor eller sidor som inte är tillgängliga utanför nätverket är inte tillgängliga för proxyservern i Adobe och kan inte öppnas i EEG. De här sidorna kan vara mellanlagrings-URL:er, UAT-URL:er (User Acceptance Testing) eller lokala värdsidor.

## Jag vill konfigurera tester på sidor som inte har mbox/target-implementeringen klar ännu. (VEC och EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

Se&quot;Jag kan inte redigera upplevelser för en iFrame-bursting-sajt&quot; ovan.

## Fet och kursiv text med Redigera text/HTML eller Ändra text/HTML visas inte på min sida. Ibland försvinner texten när du har använt de här formatändringarna. (VEC och EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

Om du använder **[!UICONTROL Edit Text/HTML]** i Visual Experience Composer för A/B- eller Experience Targeting-aktiviteter eller **[!UICONTROL Change Text/HTML]** för Automated Personalization- eller Multivariate Test-aktiviteter för att göra text fet eller kursiv, kanske dessa format inte används på sidan eller så försvinner texten från sidan i Visual Experience Composer. Det beror på att det sätt som RTF-redigeraren använder dessa format kan störa webbplatsens kod.

Om du ser detta problem:

1. Klicka på **[!UICONTROL HTML]** knappen i RTF-redigeraren för att gå till källredigeringsläget.
1. Hitta formatets textelement.

   * För fet text ändrar du elementen `<strong>` till `<b>`.

   * För kursiv text ändrar du elementen `<em>` till `<i>`.

## När det gäller Automated Personalization-aktiviteter är bildbytet brutet i VEC eller EEC. (VEC och EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

Om du lägger till ett bilderbjudande på en plats får du hela dimensionen av det ursprungliga bildutrymmet i VEC eller EEC. Vid leverans är bilden inte utökad och visas som den är, så det påverkar inte leveransen.
