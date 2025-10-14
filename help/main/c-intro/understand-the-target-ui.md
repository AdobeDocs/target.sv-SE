---
keywords: målanvändargränssnitt;användargränssnitt;ui;notiser;händelser;meddelanden
description: Bekanta dig med användargränssnittet och hitta länkar till mer detaljerad information som hjälper dig att få ut maximalt av  [!DNL Target].
title: Hur använder jag  [!DNL Target] gränssnittet?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 3f7c81654d4f7982acf166b314cc332822cc87a6
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 0%

---

# Förstå användargränssnittet för [!DNL Target]

Användargränssnittet är ordnat i ett logiskt och användarvänligt format så att du får ut det mesta av [!DNL Adobe Target]. I följande korta översikt får du hjälp att bekanta dig med [!DNL Target] och länkar till mer detaljerad information och stegvisa instruktioner.

{{updated-ui}}

## [!DNL Target] gränssnittshuvud

Rubriken högst upp i [!DNL Target]-gränssnittet innehåller flikar och alternativ som hjälper dig att navigera i lösningens olika funktioner. Du kan också växla mellan organisationer och [!DNL Adobe Experience Cloud] lösningar, ge feedback om du är en del av ett Beta-program, få tillgång till AI Assistant, få hjälp och meddelanden, hantera din [!DNL Adobe]-profil och logga ut från [!DNL Target].

![Målrubrik](/help/main/c-intro/assets/target-header.png)

Med flikarna till vänster kan du komma åt de olika funktionerna i [!DNL Target], som diskuteras senare. Låt oss börja med att diskutera alternativen till höger innan vi diskuterar flikarna.

### [!UICONTROL Organization]

En *organisation* är den entitet som gör det möjligt för en administratör att konfigurera grupper och användare samt att styra enkel inloggning i [!DNL Adobe Experience Cloud]. Organisationen fungerar som ett inloggningsföretag som omfattar alla [!DNL Experience Cloud]-produkter och -lösningar. Oftast är en organisation ditt företagsnamn. Ett företag kan dock ha många organisationer.

Välj önskad organisation i listrutan [!UICONTROL Organization] om ditt företag har flera organisationer:

![Listrutan Organisation](/help/main/c-intro/assets/organizations.png)

### [!UICONTROL Beta Feedback]

(Villkorligt) Om du är en del av ett officiellt Beta-program för [!DNL Target] kan du se ikonen [!UICONTROL Beta Feedback] .

![Beta Feedback-ikon](/help/main/c-intro/assets/beta-feedback.png)

Ange en beskrivning för din feedback, inkludera tillämpliga filer eller skärmbilder och ytterligare information, efter behov, och klicka sedan på **[!UICONTROL Submit]**.

### [!DNL AI Assistant]

(Villkorligt) Om din organisation har gett dig behörighet att använda [!DNL AI Assistant] klickar du på ikonen [!DNL AI Assistant] .

Mer information finns i [Översikt över Adobe Experience Platform AI Assistant](/help/main/c-intro/ai-assistant.md).

### Hjälp

Om du klickar på ikonen [!UICONTROL Help] ( ![hjälpikon](/help/main/assets/icons/HelpOutline.svg) ) får du tillgång till information, videoklipp, bloggar och mycket annat, så att du kan använda [!DNL Target] på ett mer effektivt sätt. Du kan skapa en supportanmälan, hitta telefonnummer till supporten, ställa frågor via Twitter eller lämna feedback om [!DNL Target] för att tala om för oss hur [!DNL Target]-teamet fungerar.

![Hjälp](/help/main/c-intro/assets/help.png)

### Begäranden, meddelanden och meddelanden {#notifications-announcements}

Panelerna [!UICONTROL Requests], [!UICONTROL Notifications] och [!UICONTROL Announcements] hjälper dig att hålla dig uppdaterad om alla saker [!DNL Adobe Target]. Proaktiva meddelanden hjälper dig att hålla dig à jour med statusen för [!DNL Adobe Experience Cloud]-lösningar och [!DNL Target]-händelser. Proaktiva meddelanden varnar dig för driftavbrott och underhållshändelser.

Klicka på ikonen [!UICONTROL Notifications] ( ![Notifications icon &#x200B;](/help/main/assets/icons/Bell.svg) ) i sidhuvudet för att visa meddelanden:

Panelen innehåller flikar för [!UICONTROL Requests], [!UICONTROL Notifications] och [!UICONTROL Announcements].

![Meddelanden](assets/notifications.png)

Följande avsnitt innehåller information om varje flik och hur du konfigurerar meddelanden och meddelanden:

#### [!UICONTROL Requests]

Ta emot viktig information om [!DNL Adobe] produkter och lösningar, ditt samarbete med andra användare och andra relevanta uppdateringar på panelen [!UICONTROL Requests].

När någon skickar en begäran till dig om att godkänna ett objekt eller bevilja åtkomst till ett objekt, visas den begäran på panelen [!UICONTROL Requests].

#### Meddelanden {#notifications}

[!DNL Target] händelsemeddelanden innehåller följande:

* **Aktiviteter**: Meddelanden för alla aktivitetstyper när en aktivitet godkänns eller inaktiveras, antingen manuellt eller när start- eller slutdatumet nås. Meddelandet innehåller namnet på aktiviteten med en länk till aktivitetens översiktssida.

  Meddelanden kan konfigureras och tas emot som standard av produktadministratörer, utgivare och godkännare på aktivitetens arbetsyta för [!DNL Target Premium]-konton. För [!DNL Target Standard]-konton tas meddelanden emot av alla utgivare och godkännare.

  Meddelanden formateras enligt följande exempel:

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Profilskript**: Meddelanden när ett profilskript aktiveras eller inaktiveras, antingen manuellt eller av [!DNL Target].

  Meddelanden kan konfigureras och tas emot som standard av produktadministratörer och godkännare för både [!DNL Target Premium]- och [!DNL Target Standard]-konton.

  Meddelanden formateras enligt följande exempel:

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Rekommenderade feeds**: Meddelanden när en [!DNL Recommendations]-feed aktiveras eller inaktiveras, antingen manuellt eller av [!DNL Target]. Meddelanden skickas också när en [!DNL Recommendations]-feed misslyckas.

  Meddelanden kan konfigureras och tas emot som standard av produktadministratörer och godkännare för [!DNL Target Premium]-konton. [!DNL Recommendations] är en [!DNL Target Premium]-funktion och är inte tillgänglig i [!DNL Target Standard].

  Meddelanden formateras enligt följande exempel:

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

Du kan markera enskilda meddelanden som lästa genom att hålla muspekaren över det önskade meddelandet och sedan klicka på ikonen [!UICONTROL Mark as Read] ( ![Markera som läst &#x200B;](/help/main/assets/icons/CheckmarkCircle.svg) ). Du kan markera alla meddelanden som lästa eller visa alla meddelanden genom att klicka på [!UICONTROL Mark as Read] eller [!UICONTROL View All] längst ned på panelen.

Du kan också ange att en påminnelse ska meddelas igen genom att hålla pekaren över ett meddelande och klicka på ikonen [!UICONTROL Snooze] ( ![Snoze &#x200B;](/help/main/assets/icons/Clock.svg) ). Du kan sedan välja när du vill bli meddelad: 5 minuter, 15 minuter, en timme eller imorgon.

#### Meddelanden

Proaktiva meddelanden varnar dig för driftavbrott och underhållshändelser.

Mer detaljerad information finns på sidan [Adobe Status](https://status.adobe.com/).

### Konfigurera meddelanden och meddelanden

Så här redigerar du aviseringsinställningarna:

1. Klicka på ikonen [!UICONTROL Edit Preferences] ( ![Redigera inställningar &#x200B;](/help/main/assets/icons/Setting.svg) ) och klicka sedan på **[!UICONTROL Notifications]** i den vänstra listen.
1. Under **[!UICONTROL Target]** väljer du hur du vill bli meddelad:

   * [!UICONTROL In-app]
   * [!UICONTROL Email]
   * [!DNL Slack]

1. Välj de kategorier som du vill ska ha hög prioritet.

   >[!NOTE]
   >
   >[!UICONTROL New releases] och [!UICONTROL Updates on content] är de enda meddelandekategorierna som gäller för [!DNL Target]. De andra kategorierna gäller för andra [!DNL Adobe]-lösningar.

1. Välj de meddelanden som du vill visa aviseringar för i webbläsaren.

   Dessa varningar visas i webbläsarens övre högra hörn under några sekunder. Du kan välja att visa kategorier med hög prioritet, alla kategorier eller att dölja alla popup-meddelanden. Du kan också konfigurera om du vill att meddelandena ska vara synliga tills du stänger dem eller om du kan konfigurera meddelandets varaktighet.

1. Ange hur ofta du vill få e-postmeddelanden:

   * [!UICONTROL Don't send emails]
   * [!UICONTROL Instant notifications]
   * [!UICONTROL Daily digest]
   * [!UICONTROL Weekly digest]

1. Konfigurera Slack-meddelanden för en arbetsyta.

### Appväljaren

Med Apps-väljaren kan du snabbt komma åt de [!DNL Adobe Experience Cloud]-lösningar du har tillgång till.

![Appväljaren](/help/main/c-intro/assets/apps.png)

### Profil

Klicka på din profilavatar om du vill redigera dina [!DNL Adobe Experience Cloud]-inställningar eller logga ut från [!DNL Target]. Du kan även komma åt eller redigera din [!DNL Adobe]-profil.

![Profilavatar](/help/main/c-intro/assets/change-language.png)

Nu ska vi diskutera flikarna till vänster om huvudet [!DNL Target].

## Verksamhet

Listan **[!UICONTROL Activities]** är standardvy när du öppnar [!DNL Target]. Du kan skapa aktiviteter från den här sidan och hantera befintliga aktiviteter.

Se [Aktiviteter](/help/main/c-activities/activities.md) för detaljerad information om aktivitetstyperna i [!DNL Target] och för mer information om användargränssnittet i [!UICONTROL Activity]-listan.

## Målgrupper

Klicka på fliken **[!UICONTROL Audiences]** för att visa listan [!UICONTROL Audiences] där du kan skapa målgrupper och hantera befintliga målgrupper.

En målgrupp är en grupp liknande aktivitetsdeltagare som ser en riktad aktivitet. En publik är en grupp människor med samma egenskaper, till exempel en ny besökare, en återkommande besökare eller återkommande besökare från mellanvästern. Med funktionen [!UICONTROL Audience] kan ni rikta olika innehåll och upplevelser till specifika målgrupper för att optimera er digitala marknadsföring genom att visa rätt budskap till rätt personer vid rätt tidpunkt. Om en besökare identifieras som en del av en målpublik avgör [!DNL Target] vilken upplevelse som ska visas, baserat på kriterier som definieras när aktiviteten skapas.

Se [Skapa målgrupper](/help/main/c-target/c-audiences/create-audience.md) för ingående information om målgruppstyperna i [!DNL Target] och om du vill veta mer om användargränssnittet i [!UICONTROL Audience]-listan.

## Erbjudanden

Klicka på fliken **[!UICONTROL Offers]** för att visa listan [!UICONTROL Offers] där du kan skapa upplevelser och erbjudanden och hantera befintliga upplevelser och erbjudanden.

En upplevelse kan vara ett erbjudande, en bild, text, knapp, video, en kombination av dessa olika element på en sida, en hel webbsida eller en uppsättning sidor som kanske utgör en inköpstratt eller någon annan logisk sekvens av sidor. Det kan också vara svaret från en röstassistent, ett kundskript eller till och med en personlig smak från en dryckesmaskin. Du testar eller personaliserar upplevelser i [!DNL Target]-aktiviteter.

Se [Erbjudanden](/help/main/c-experiences/c-manage-content/manage-content.md) om du vill ha mer information om erbjudandetyperna i [!DNL Target] och om du vill veta mer om användargränssnittet i [!UICONTROL Offer]-listan.

## Rekommendationer

Klicka på fliken **[!UICONTROL Recommendations]** för att komma åt [!DNL Target Recommendations].

>[!NOTE]
>
>[!UICONTROL Recommendations] aktiviteter är tillgängliga som en del av lösningen [!DNL Target Premium]. [!UICONTROL Recommendations] aktiviteter är inte tillgängliga i [!DNL Target Standard] utan licens [!DNL Target Premium]. Mer information finns i [Target Premium](/help/main/c-intro/intro.md#premium) i *Introduktion till Target*.

[!UICONTROL Recommendations]-aktiviteter visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktivitet eller andra algoritmer. Rekommendationer hjälper kunderna att hänvisa till relevanta objekt som de annars kanske inte känner till.

Mer information om [&#x200B; i &#x200B;](/help/main/c-recommendations/recommendations.md) finns i [!UICONTROL Recommendations]Rekommendationer[!DNL Target] och om användargränssnittet i [!UICONTROL Recommendations].

## Administration

Klicka på fliken **[!UICONTROL Administration]** för att komma åt [!UICONTROL Administration]-sidorna.

På sidorna [!UICONTROL Administration] kan du administrera [!DNL Target], inklusive konfigurationsinställningar för [!UICONTROL Visual Experience Composer] (VEC), rapportering, [!DNL Scene7] konfiguration, implementering, värdar, miljöer, svarstoken, användare och rekommendationer.

Mer information och mer information om användargränssnittet finns i [Administrera målöversikt](/help/main/administrating-target/administrating-target.md).

## Visual Experience Composer (VEC)

Utöver användargränssnittet för [!DNL Target] bör du bekanta dig med VEC-gränssnittet. Mer information finns i [[!DNL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).
