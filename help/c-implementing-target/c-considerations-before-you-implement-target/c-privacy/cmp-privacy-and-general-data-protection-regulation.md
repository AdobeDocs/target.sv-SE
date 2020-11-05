---
keywords: gdpr;eu;european union;privacy;faq;frequently asked questions;california consumer privacy act;ccpa;privacy;data protection;opt-out;opt out;government;regulation
description: Information om EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra internationella integritetskrav, och hur dessa bestämmelser påverkar er organisation och Adobe Target.
title: Sekretess- och dataskyddsbestämmelser
feature: privacy and security
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '2248'
ht-degree: 0%

---


# Sekretess- och dataskyddsbestämmelser {#privacy-and-general-data-protection-regulation-gdpr}

Information om EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra internationella integritetskrav, och hur dessa bestämmelser påverkar er organisation och Adobe Target.

## Översikt över dataskyddsförordningen och den allmänna dataskyddsförordningen {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Den 25 maj 2018 trädde Europeiska unionens allmänna dataskyddsprogram i kraft. Mer information om vad detta innebär för dig finns i [GDPR och Ditt företag](https://www.adobe.com/privacy/general-data-protection-regulation.html).

När [!DNL Adobe] tillhandahåller programvara och tjänster till ett företag [!DNL Adobe] fungerar som databehandlare för alla personuppgifter som bearbetas och lagras som en del av tillhandahållandet av dessa tjänster. Som databehandlare behandlar [!DNL Adobe] personuppgifter i enlighet med ditt företags tillstånd och instruktioner (till exempel enligt vad som anges i ditt avtal med [!DNL Adobe]).

Som personuppgiftsansvariga avgör du vilka personuppgifter som [!DNL Adobe] bearbetas och lagras åt dig. Om du använder [!DNL Adobe Experience Cloud] lösningar [!DNL Adobe] kan lagra personuppgifter för dig, beroende på vilka lösningar du använder och vilken information du väljer att skicka till ditt [!DNL Adobe Experience Cloud] konto. En detaljerad lista över exempel finns i [Adobe Experience Cloud Integritet](https://www.adobe.com/privacy/marketing-cloud.html#collect).

[!DNL Adobe Experience Cloud] tillhandahålla GDPR-förberedda API:er för datacentraler som gör att de kan utföra följande uppgifter:

* Åtkomst till information om registrerade personer som lagras i [!DNL Target]
* Ta bort information om registrerade som lagras i [!DNL Target]

Mer information finns i:

* [Adobe webbplats för API:t för allmänna dataskyddsförordningen](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR-dokumentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## California Consumer Privacy Act (CCPA) - översikt

California Consumer Privacy Act (CCPA) ger Kaliforniens konsumenter nya rättigheter när det gäller deras personuppgifter och ålägger vissa enheter som bedriver verksamhet i Kalifornien dataskydd. CCPA träder i kraft den 1 januari 2020.

På en hög nivå ger lagen Kalifornien flera nyckelrättigheter, bland annat rätten att

* Begär information (dataåtkomst)
* Avanmäl dig från försäljningen av personuppgifter (en mycket omfattande rätt att avanmäla sig från delning av information med tredje part)
* Ta bort personlig information
* informeras om att personuppgifter röjs eller säljs

Om du var upptagen med att förbereda dig för Europas integritetslagstiftning (GDPR) förra året kan vissa av dessa rättigheter vara välkända och mycket av det arbete du har gjort kan kanske återanvändas.

>[!NOTE]
>
>Åtkomst och borttagning av data till som det gäller för CCPA följer samma process som för GDPR.

## Adobe Target och [!DNL Experience Platform Launch] deltagande {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] ger support för tillvalsfunktioner via [!DNL Launch] för att hjälpa er strategi för samtyckeshantering. Med avanmälningsfunktionen kan kunderna styra hur och när [!DNL Target] -taggen aktiveras. Det finns också ett alternativ [!DNL Launch] för att förgodkänna [!DNL Target] -taggen. Om du vill aktivera möjligheten att använda Opt-In i [!DNL Target] at.js-biblioteket bör du använda `targetGlobalSettings` och lägga till `optinEnabled=true` inställningen. I [!DNL Launch] måste du välja&quot;enable&quot; i [!UICONTROL GDPR Opt-In] listrutan i installationsvyn för [!DNL Launch] tillägget. Mer information finns i [startdokumentationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) .

I följande kodutdrag visas hur du aktiverar `optinEnabled=true` inställningen:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>Opt-in-funktionaliteten stöds i at.js version 1.7.0 och at.js 2.1.0 eller senare. Opt-in stöds inte i version 2.0.0 och 2.0.1 av at.js.
>
>Vi rekommenderar att du använder [!DNL Experience Platform Launch] för att hantera anmälan. Det finns ytterligare detaljkontroll för [!DNL Launch] att dölja valda delar av sidan före [!DNL Target] lanseringen som kan utnyttjas som en del av er strategi för samtycke.

Det finns tre scenarier att tänka på när du använder Opt-In:

1. **Taggen [!DNL Target] godkänns på förhand [!DNL Launch] (eller den registrerade som tidigare godkänts [!DNL Target]):** Taggen [!DNL Target] sparas inte för samtycke och fungerar som förväntat.
1. **Taggen [!DNL Target] är INTE förgodkänd och `bodyHidingEnabled` är FALSE:** Taggen [!DNL Target] aktiveras först när kunden har gett sitt samtycke. Innan samtycke samlas in är endast standardinnehåll tillgängligt. Efter det att samtycke mottagits [!DNL Target] anropas det och personaliserat innehåll är tillgängligt för den registrerade (besökaren). Eftersom endast standardinnehåll är tillgängligt före samtycke är det viktigt att utnyttja en lämplig strategi, till exempel en välkomstsida som täcker alla delar av sidan eller innehåll som kan personaliseras. Detta garanterar att upplevelsen är enhetlig för den registrerade (besökaren).
1. **Taggen [!DNL Target] är INTE förgodkänd och `bodyHidingEnabled` är TRUE:** Taggen [!DNL Target] aktiveras först när kunden har gett sitt samtycke. Innan samtycke samlas in är endast standardinnehåll tillgängligt. Men eftersom `bodyHidingEnabled` är inställt på true `bodyHiddenStyle` avgör vilket innehåll på sidan som döljs tills [!DNL Target] -taggen aktiveras (eller så avvisar den registrerade möjligheten att välja, vilket innebär att standardinnehåll visas). Som standard `bodyHiddenStyle` anges till `body { opacity:0;}`, vilket döljer HTML-body-taggen. Den rekommenderade sidkonfigurationen visas nedan så att hela sidans innehåll, förutom dialogrutan för hantering av samtycke, döljs genom att sidans innehåll placeras i en behållare och dialogrutan för hantering av samtycke i en separat behållare. Den här inställningen konfigureras [!DNL Target] så att endast sidinnehållsbehållaren döljs. Mer information om hur du konfigurerar de här inställningarna finns i [Startdokumentationen](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html).

   Rekommenderad sidinställning för scenario 3 är:

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   Anta `bodyHiddenStyle` att:

   ```
   #pageContent { opacity:0;}
   ```

## Frågor och svar om sekretess och dataskydd {#concept_41F88DE95D2943178BEC382736B5C038}

Vanliga frågor och svar om EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra internationella integritetskrav som är specifika för Target.

### Vad är Adobe policy för dessa regler? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] uppfyller eller genomför redan våra skyldigheter som databehandlare. Vi har en stark grund för certifierade säkerhets- och integritetskontroller utifrån design och har gjort produktförbättringar före tidsfristen i maj 2018. Företagskunder ansvarar för att implementera dessa förbättringar samt att uppdatera nödvändiga policyer och procedurer.

### Kommer mitt företag, Data Controller, att behöva skicka en GDPR- eller CCPA-begäran till varje [!DNL Adobe Experience Cloud] lösning som det använder? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Nej, [!DNL Adobe] är ett centralt sätt att hjälpa datakontroller att uppfylla sina GDPR- och CCPA-krav. Datakontroller behöver inte gå direkt till varje lösning.

Alla GDPR- och CCPA-förfrågningar över olika [!DNL Experience Cloud] lösningar, inklusive [!DNL Target]dessa, kommer att göras via ett centralt Adobe-API, som för närvarande kallas GDPR-API. API:t slutför sedan begäran i Data Controller- [!DNL Experience Cloud] lösningspaketet.

### Vilken information kommer våra kunder att [!DNL Adobe] kunna radera som svar på en begäran från en registrerade/användare? {#section_4B51D00924EC4166B2442218B69214F0}

Informationen om en enskild besökare i [!DNL Target] finns i [!DNL Target] besökarprofilen. [!DNL Target] gör det möjligt för våra kunder att ta bort alla data som är kopplade till ett ID i deras besökarprofil. Exempel på profildataarkiv [!DNL Target] finns i [Besökarprofil](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Sammanställda eller anonyma data (t.ex. rapportdata) som inte identifierar en viss individ, eller data som inte är kopplade till en viss individ (t.ex. innehållsdata), omfattas inte av en begäran om att ta bort användare.

[!DNL Target] Besökarprofiler som har varit inaktiva i 90 dagar tas bort som standard, utan någon åtgärd.

### Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] har stöd för följande ID-typer för att hitta en kundprofil:

| Användar-ID | Typ av namnutrymmes-ID | Namnområdes-ID | Definition |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud-id, f.d. besökar-ID eller Marketing Cloud-ID. Du kan använda JavaScript-API:t för att hitta detta ID (se informationen nedan). |
| TnT ID/Cookie ID(TNTID) | Standard | 9 | Målidentifieraren anges som en cookie i besökarens webbläsare. Du kan använda JavaScript-API:t för att hitta detta ID (se informationen nedan). |
| Tredjeparts-ID/CRM-ID (TREDJEPARTYID) | Målspecifik | Ej tillämpligt | Om du tillhandahåller Target tillsammans med din CRM eller annan unik identifieringsinformation för dina kunder. |

>[!NOTE]
>
>Även om [!DNL Target] stöd finns för cookies mellan domäner från både första part och från tredje part, rekommenderas endast cookies [!DNL Target] från första part för GDPR och CCPA.

### Hur [!DNL Target] hanterar vi samtyckeshantering? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR och CCPA ändras inte när du behöver få samtycke, utan hur du får det. Varje kunds strategi för samtycke är beroende av dess datainsamling och dataanvändning samt av dess integritetspolicy. Samtyckeshantering stöds inte av och bör inte göras via [!DNL Target] GDPR och CCPA.

[!DNL Adobe] erbjuder för närvarande inte någon lösning för hantering av samtycke, men det finns olika verktyg på marknaden som kan hantera vissa av de nya kraven. Mer information om sekretessverktyg i allmänhet, inklusive medgivandeansvariga, finns i [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) på webbplatsen *International Association of Privacy Professionals (iaap)* .

[!DNL Target] ger support för tillvalsfunktioner via [!DNL Launch] för att ge support för er strategi för samtyckeshantering. Med avanmälningsfunktionen kan kunderna styra hur och när [!DNL Target] -taggen aktiveras. Det finns också ett alternativ [!DNL Launch] för att förgodkänna [!DNL Target] -taggen. Vi rekommenderar att du använder [!DNL Launch] för att hantera anmälan. Det finns ytterligare detaljkontroll för [!DNL Launch] att dölja vissa delar av sidan före [!DNL Target] starten som kan vara till hjälp för att dra nytta av er strategi för samtycke.

Mer information om GDPR, CCPA och [!DNL Launch]finns [i Adobe Privacy JavaScript Library och GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Se även avsnittet om deltagande *för* Adobe Target och Experience Platform Launch ovan.

### Skickar AdobePrivacy.js information till GDPR-API:t? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] skickar *inte* den här informationen till API:t. Kunden måste göra det. Det här biblioteket innehåller bara de ID:n som lagras i webbläsaren för den specifika besökaren.

### Vad tar removeIdentities bort? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *tar bara* bort dessa identiteter från webbläsaren, och det beror bara på om [!DNL Adobe] lösningen har implementerat den.

Tar till exempel [!DNL Target] bort cookies som lagrar sina ID:n, men [!DNL Adobe Audience Manager] (AAM) tar inte bort det demdex-ID som lagras i en cookie från tredje part.

### Vilken information behöver inkluderas i en Target GDPR- eller CCPA-begäran? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Utöver kraven från den centrala Privacy Servicen [!DNL Target] innehåller ett giltigt GDPR- eller CCPA-meddelande:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### Vilka typer av svar kan jag förvänta mig från Target via GDPR API? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Status för begäran | Målsvarsmeddelande | Scenario |
|--- |--- |--- |
| Bearbetar | Bearbetar | Målet tog emot GDPR- eller CCPA-begäran och bearbetar den. |
| Slutförd | Ej tillämpligt - företagskontexten är inte tillämplig | IMS-ID:t i GDPR- eller CCPA-begäran mappas inte till någon målklient.<br>Observera att vissa företag har flera IMS ID:n. Du måste skicka det IMS-ID där Target har etablerats. |
| Slutförd | Ej tillämpligt - användarkontexten hittades inte | Det ID som anges i GDPR- eller CCPA-begäran för den specifika besökaren eller den angivna registrerade personen finns inte i målprofilens arkiv.<br>Observera att det här resultatet också returneras om du försöker skicka en typ av namnområdes-ID som inte stöds av Target (se ovan för vilka ID som stöds). |
| Fel | Felmeddelande (informationen beror på feltypen) | Ett fel uppstod vid hämtning eller borttagning av den begärda dataobjektprofilen.<br>Ett fel uppstod vid överföring till Azure för åtkomstbegäran. |

### Vilket svar skickar Target till GDPR API för en åtkomstbegäran? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Svar på begäran om åtkomst av data innehåller en sammanfattning av den aktuella besökarens [!DNL Target] profil. Observera att denna retur skickas till [!DNL Experience Cloud] GDPR API, som i sin tur skickar ett svar till Data Controllers.

Ett exempel på [!DNL Target] åtkomst-API-svar kan se ut så här:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| Fält | Beskrivning |
|--- |--- |
| jobId | Anger GDPR- eller CCPA-jobb-ID från det centrala GDPR-API:t. |
| imsOrgID | Tillhandahåller en unik identifierare för ditt företag. |
| namespace | Kallas även datakälla. Se&quot;Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för Target?&quot; i det här avsnittet. |
| type | Den typ av ID som du begärde GDPR- eller CCPA-dataåtkomst för. Target accepterar flera ID-typer, varav vissa är standard och vissa är Target-specifika. Se&quot;Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för Target?&quot; i det här avsnittet. |
| value | ID för namnområdet/datakällan. Se&quot;Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för Target?&quot; för godkända värden. |
| integrationskod | Integrationskoder är egna namn för datakällorna och hjälper dig att spåra datakällorna enklare än att använda ID:n för datakällor. |

När flera värden anges för att identifiera profiler har varje giltig identifierare en profilfil. Profilfilerna skickas till den centrala GDPR Azure-blobben via det centrala API:t för GDPR, i formatet JSON- [!DNL Target] profilsvar.

Ett exempel på en JSON- [!DNL Target] profil kan se ut som i följande exempel:

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

Följande tabell innehåller en beskrivning av JSON-fälten för den illustrativa profilen:

| Fält | Beskrivning |
|--- |--- |
| Sample_Parameter | Många informationsdelar i profilen överförs eller tillhandahålls direkt av [!DNL Target] Data Controller. I det här exemplet överfördes en parameter till [!DNL Target] profilen med hjälp av API:t för profiluppdatering. Mer information finns i [Metoder för att hämta data till Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | I det här standardfältet anges tiden på dagen för en användares senaste besök. |
| firstSessionStart | Detta standardfält innehåller den tid på dagen då användarens första session påbörjades. |
| user.sessionCountScript | Många informationsdelar i profilen överförs eller tillhandahålls direkt av [!DNL Target] Data Controller. I det här exemplet ökar ett profilskript antalet sessioner som den här besökaren har gjort på Data Controller-platsen. Mer information finns i [Profilskriptattribut](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Det här är en förkortad version av en JSON- [!DNL Target] profil för illustrationsändamål. Många av profilens fält är inte standard [!DNL Target] . Vad som returneras beror på vilken information som finns i den specifika besökarprofilen.

### Har Target stöd för IP-förfalskning? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] har stöd för IP-förfalskning om du väljer att använda det som en del av GDPR- eller CCPA-implementeringsstrategin. Mer information finns i [Sekretess](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).

### Behöver jag göra något för att förhindra att mina data delas eller säljs till tredje part?

Target har inte möjlighet att tillåta kunder att dela eller sälja data direkt från Target till tredje part, så det finns ingen avanmälan för Target.
