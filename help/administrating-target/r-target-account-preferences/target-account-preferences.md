---
keywords: account preferences;preferences;site details;custom mbox name;Experience Cloud solution used for reporting;Show estimated lift in revenue;css selectors;use element classes;Default Visual Experience Composer URL;Enable Enhanced Experience Composer;Generate Experience Snapshots;mobile viewport configuration;Industry Vertical;Filter Incompatible Criteria
description: Ange dina kontoinställningar för att konfigurera Adobe Target Standard eller Target Premium så att det fungerar korrekt med ditt konto.
title: Inställningar
subtopic: Getting Started
topic: Standard
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Inställningar{#preferences}

Ange dina kontoinställningar så att de konfigureras [!DNL Target Standard] eller [!DNL Target Premium] fungerar korrekt med ditt konto.

Om du vill ange dina kontoinställningar klickar du på **[!UICONTROL Setup]** > **[!UICONTROL Preferences]**, konfigurerar dina inställningar och klickar sedan på **[!UICONTROL Submit]**.

Följande bild visar de tillgängliga inställningarna på [!UICONTROL Account Preferences] sidan.

![Sidan Inställningar](/help/administrating-target/r-target-account-preferences/assets/target-account-preferences.png)

>[!NOTE]
>
>Vissa av dessa inställningar är bara tillgängliga om du har [Target Premium](/help/c-intro/intro.md#premium).

## Webbplatsinformation {#section_04A3340FC29B46978DB77058259F4EE0}

Ange hur platsen har konfigurerats.

### Anpassad global mbox

Välj det valfria namnet på den anpassade mbox som du använder för att leverera [!DNL Target] aktiviteter. Den här globala rutan måste vara tom, vilket innebär att den inte har något standardinnehåll. Spara den här inställningen först när den uppdaterade [!DNL at.js] eller [!DNL mbox.js] uppdaterade filen har installerats på platsen.

>[!CAUTION]
>
>Om du konfigurerar den här inställningen felaktigt kan befintliga aktiviteter gå förlorade.

## Resultat och rapportering {#section_47C887AABD704A96BCD1C00BEABF4BCE}

Ange alternativ som avgör vilka data som används för dina resultat och rapporter.

| Alternativ | Beskrivning |
|--- |--- |
| Experience Cloud-lösning som används för rapportering | Välj rapportkälla för dina aktiviteter, antingen [!DNL Target] eller Adobe Analytics. Du kan också välja att välja rapportkälla per aktivitet. Tänk på följande när du väljer rapportkälla:<ul><li>[!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] (AP) kan användas för att skapa, aktivera och inaktivera aktiviteter oavsett vilken rapportkälla som valts. Dessa aktivitetstyper stöds inte när du väljer [Adobe Analytics som rapportkälla för Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Även om du anger Analytics som rapportkälla används det som rapportkälla för [!DNL Target] de här aktivitetstyperna.</li><li>Om rapportkällan är inställd på Analytics (Analys) här, får du inte aktivera en aktivitet som använder [!DNL Target] som rapportkälla (rapportkällan anges som Target per aktivitet). Du måste ändra rapportkällan till Analytics i din aktivitet eller ändra rapporteringsmotorn till Select Per Activity (Välj per aktivitet) i Inställningar > Inställningar.</li><li>Om rapportkällan anges [!DNL Target] här får du inte aktivera en aktivitet som använder Analytics som rapportkälla. Du måste ändra rapportkällan till [!DNL Target] i din aktivitet eller ändra rapportkällan till Välj per aktivitet i Inställningar > Inställningar.</li><li>Om rapportkällan är inställd på Välj per aktivitet här kan du skapa, aktivera och inaktivera aktiviteter som stöds av den valda rapportkällan. En matris med aktiviteter som stöds finns i [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).</li><li>När du växlar från A/B-handbok till [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target]försvinner alla mätvärden och rapportmålgrupper om rapportkällan för A/B-handboken inte stöds i [!UICONTROL Auto-Allocate] - eller [!UICONTROL Auto-Target] -aktiviteter.</li></ul> |
| Visa uppskattad ökning av intäkter | Du kan även välja att visa den beräknade ökningen av intäkterna om du anger ett penningvärde för ditt mål. [!DNL Target] kan beräkna den vinst du skulle uppnå om alla användare såg den vinnande upplevelsen. Den uppskattade lyftfunktionen är inaktiverad som standard.<br>Endast Experience Cloud Admin-användare kan aktivera eller inaktivera den här funktionen. Om den uppskattade höjden är inaktiverad visas inte motsvarande fält i gränssnittet. Om du inaktiverar funktionen går det inte att förlora data, inklusive data som används för dina uppskattningar. Beräkningarna baseras på data som samlas in oavsett om funktionen är aktiverad eller inte.<br>Mer information finns i [Beräkna Lyft i intäkter](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| Aktivera finkorniga prioriteringar | Tillåt numeriska värden för prioritet från 0-999.<br>Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.<br>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten. |

## CSS-väljare {#section_8155EDBF449E4198863235F94D1EA872}

Ange hur CSS-väljare ska [!DNL Target] genereras.

Dessa alternativ hjälper till att [!DNL Target] förstå webbplatsens struktur och generera bättre CSS-väljare för innehållsleverans. Som standard [!DNL Target] genererar väljare baserat på element-ID på sidan. Om bara ett fåtal ID eller ID:n på samma sida används på platsen kan det vara bättre att använda klasser.

Du kan välja ett eller båda av följande alternativ:

| Alternativ | Beskrivning |
|--- |--- |
| Använd element-ID:n | Avmarkera det här alternativet om samma ID används för flera element eller om element-ID kan ändras vid sidinläsning. |
| Använd elementklasser | Som standard använder [!DNL Target] endast element-ID:n. Om sidan är utformad för att använda klasser för att identifiera element, t.ex. en sida som skapats med, [!DNL Adobe Experience Manager]bör du även välja [!UICONTROL Use element classes].<br>**Obs **: Även om allt har gjorts för att säkerställa noggrannheten bör du vara medveten om att användning av klasser kan orsaka fel. Om du inte väljer något av alternativen påverkas även noggrannheten. Precisionsordningen är ID:n > klasser > inget av alternativen. Se alltid till att du testar sidan för att kontrollera att väljarna är korrekta.<br>Du kan åsidosätta den här inställningen per aktivitet (klicka på[!UICONTROL Settings]kugghjulsikonen och välj sedan[!UICONTROL CSS Selectors]). Detta är särskilt användbart om du har flera platser som har konfigurerats på olika sätt.<br>**Obs**: Det går inte att åsidosätta inställningen per aktivitet i [!UICONTROL Automated Personalization] - och [!UICONROL multivariata testningsaktiviteter] .  Mer information om väljare finns i [Elementväljare som används i Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) . |

## Visual Experience Composer {#section_CD9BDD372CF54E678F88E8BA95757A5A}

| Alternativ | Beskrivning |
|--- |--- |
| StandardURL för Visual Experience Composer | Ange den standardwebbadress som används av [!UICONTROL Visual Experience Composer]. Det här är standardsidan, till exempel hemsidan, som används när du skapar en upplevelse för varje ny aktivitet. Om du inte anger någon standardwebbadress (URL) måste du ange en webbadress (URL) för varje aktivitet när du skapar den. |
| Aktivera Förbättrad Experience Composer | Möjliggör redigering på iFrame-busting-webbplatser med blandat innehåll. Vissa webbplatser kanske inte är kompatibla med den förbättrade versionen. Avmarkera det här alternativet om du vill återgå till den ursprungliga Experience Composer. Aktivitetsleverans på webbplatser påverkas inte av det här valet.<br>Mer information finns i [Felsöka Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).<br>**Obs **: Du kan också aktivera Förbättrad Experience Composer på aktivitetsnivå. |
| Läs in blandat innehåll | Aktivera blandat innehåll när du öppnar en webbplats med Enhanced Experience Composer (EEC). Om du aktiverar det här alternativet undviker du den extra kostnaden för att läsa in statiska resurser via Target-proxyservrar.<br>Det här alternativet är användbart om du t.ex. tillåter att CSP-rubriker (Content Security Policy) läser in blandat innehåll utan att använda proxyservrar med EEG aktiverat.<br>Det här alternativet är också användbart om HTTP-webbplatsen har en ökad inläsningstid i EEC, där JavaScript, bilder och så vidare tar längre tid att läsa in via proxy. |
| Generera upplevelseögonblicksbilder | När du aktiverar ögonblicksbilder av upplevelser genereras miniatyrer för dina upplevelser i aktivitetsarbetsflödesdiagrammet. Om du inaktiverar ögonblicksbilder kan vissa användare få bättre prestanda. |

## Konfiguration av mobilvisningsruta {#section_42176D062BCE4A28ADBB784CC4BEF84D}

Du kan lägga till enheter som ska användas när du förhandsgranskar upplevelser. Varje enhet har en associerad målgrupp.

| Alternativ | Beskrivning |
|--- |--- |
| ![Premium badge](/help/assets/premium.png) Add New | Klicka [!UICONTROL Add New], ange ett beskrivande namn för mobilvisningsrutan, ange bredd och höjd, markera önskat operativsystem och klicka sedan på [!UICONTROL Save].  Mer information om hur du lägger till en mobil visningsruta finns i Konfigurera [för](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)mobilvisningsruta. |

## Utbildningsvideo: Kontoinställningar (7:33) ![Översikt, märke](/help/assets/overview.png)

Den här videon innehåller information om kontoinställningar.

* Beskriv de kontoinställningar som är tillgängliga i [!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379)