---
keywords: gdpr;eu;europeisk union;sekretess;faq;vanliga frågor;california-konsumentsekretesslag;ccpa;sekretess;dataskydd;opt out;opt out;government;Regulation
description: Läs mer om [!DNL Target] och EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra integritetskrav.
title: Hur [!DNL Target] Hantera sekretess- och dataskyddsreglerna?
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '2225'
ht-degree: 0%

---

# Sekretess- och dataskyddsbestämmelser

Information om EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra internationella integritetskrav. Läs om hur dessa regler påverkar er organisation och [!DNL Adobe Target].

## Översikt över dataskyddsförordningen och den allmänna dataskyddsförordningen {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Den 25 maj 2018 trädde Europeiska unionens allmänna dataskyddsprogram i kraft. Mer information om vad den här förordningen betyder för dig finns i [GDPR och er verksamhet](https://business.adobe.com/privacy/general-data-protection-regulation.html).

När [!DNL Adobe] tillhandahåller programvara och tjänster till ett företag, [!DNL Adobe] agerar som databehandlare för alla personuppgifter som behandlas och lagras av den som en del av tillhandahållandet av dessa tjänster. Som databehandlare [!DNL Adobe] behandlar personuppgifter i enlighet med ditt företags tillstånd och instruktioner (t.ex. enligt vad som anges i ditt avtal med [!DNL Adobe]).

Som personuppgiftsansvariga avgör du vilka personuppgifter som [!DNL Adobe] processer och butiker åt dig. Om du använder [!DNL Adobe Experience Cloud] lösningar, [!DNL Adobe] kan lagra personuppgifter åt dig, beroende på vilka lösningar du använder och vilken information du väljer att skicka till [!DNL Adobe Experience Cloud] konto. En detaljerad lista med exempel finns i [Adobe Experience Cloud Integritet](https://www.adobe.com/privacy/experience-cloud.html#collect).

[!DNL Adobe Experience Cloud] tillhandahåller GDPR-förberedda API:er för datakontroller som gör att de kan utföra följande uppgifter:

* Åtkomst till information om registrerade personer som lagras i [!DNL Target]
* Ta bort information om registrerade som lagras i [!DNL Target]

Mer information finns i:

* [Översikt över Privacy Servicen Adobe](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [API-guide för Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Översikt över användargränssnittet i Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## California Consumer Privacy Act (CCPA) - översikt

California Consumer Privacy Act (CCPA) ger Kaliforniens konsumenter nya rättigheter när det gäller deras personuppgifter och ålägger vissa enheter som bedriver verksamhet i Kalifornien dataskydd. CCPA trädde i kraft den 1 januari 2020.

På en hög nivå ger lagen Kalifornien flera nyckelrättigheter, bland annat rätten att

* Begär information (dataåtkomst)
* Avanmäl dig från försäljningen av personuppgifter (en vida definierad rätt att avanmäla delning av information med tredje part)
* Ta bort personlig information
* informeras om att personuppgifter röjs eller säljs

Om du var upptagen med att förbereda dig för Europas integritetslagstiftning (GDPR) förra året kan vissa av dessa rättigheter vara välkända och mycket av det arbete du har gjort kan återanvändas.

>[!NOTE]
>
>Åtkomst och borttagning av data som gäller för CCPA följer samma process som för GDPR.

## Adobe [!DNL Target] och [!DNL Adobe Experience Platform] anmälan {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] ger stöd för tillvalsfunktioner via taggar i [!DNL Adobe Experience Platform] för att stödja er strategi för samtyckeshantering. Tack vare avanmälningsfunktionen kan kunderna styra hur och när [!DNL Target] -taggen utlöses. Det finns också ett alternativ via [!DNL Adobe Experience Platform] för att förgodkänna [!DNL Target] -tagg. Så här aktiverar du möjligheten att använda Opt-In i [!DNL Target] at.js-biblioteket bör du använda `targetGlobalSettings` och lägg till `optinEnabled=true` inställning. I [!DNL Adobe ExperiencePlatform]väljer du&quot;enable&quot; på [!UICONTROL GDPR Opt-In] nedrullningsbar lista i installationsvyn för tillägget. Se [Implementera [!DNL Target] använda [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} om du vill ha mer information.

Följande kodfragment visar hur du aktiverar `optinEnabled=true` inställning:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>Opt-in-funktionaliteten stöds i at.js version 1.7.0 och at.js 2.1.0 eller senare. Opt-in stöds inte i version 2.0.0 och 2.0.1 av at.js.
>
>Använda [!DNL Adobe Experience Platform] Vi rekommenderar att du hanterar anmälan. Ytterligare kontroll finns i [!DNL Adobe Experience Platform] om du vill dölja markerade element på sidan före [!DNL Target] som är till hjälp att använda som en del av er strategi för samtycke.

Det finns tre scenarier att tänka på när du använder Opt-In:

1. **The [!DNL Target] -taggen har godkänts i förväg via [!DNL Adobe Experience Platform] (eller den registrerade som tidigare godkänts [!DNL Target]):** The [!DNL Target] -taggen används inte för godkännande och funktioner som förväntat.
1. **The [!DNL Target] -taggen är INTE förgodkänd och `bodyHidingEnabled` är FALSE:** The [!DNL Target] -taggen aktiveras endast efter att kunden har gett sitt samtycke. Innan samtycke samlas in är endast standardinnehåll tillgängligt. När samtycke har erhållits, [!DNL Target] anropas och personaliserat innehåll är tillgängligt för den registrerade (besökaren). Eftersom endast standardinnehåll är tillgängligt före samtycke är det viktigt att använda en lämplig strategi, till exempel en välkomstsida som täcker alla delar av sidan eller innehåll som kan personaliseras. Denna process säkerställer att upplevelsen är enhetlig för den registrerade (besökaren).
1. **The [!DNL Target] -taggen är INTE förgodkänd och `bodyHidingEnabled` är TRUE:** The [!DNL Target] -taggen aktiveras endast efter att kunden har gett sitt samtycke. Innan samtycke samlas in är endast standardinnehåll tillgängligt. Men eftersom `bodyHidingEnabled` är inställt på true, `bodyHiddenStyle` anger vilket innehåll på sidan som är dolt tills [!DNL Target] -taggen utlöses (eller så avböjer den registrerade deltagande, vilket innebär att standardinnehåll visas). Som standard `bodyHiddenStyle` är inställd på `body { opacity:0;}`som döljer body-taggen HTML. Den rekommenderade sidkonfigurationen är under så att hela sidans innehåll, förutom dialogrutan för hantering av samtycke, döljs genom att sidans innehåll placeras i en behållare och dialogrutan för hantering av samtycke i en separat behållare. Denna konfiguration konfigurerar [!DNL Target] så att endast sidinnehållsbehållaren döljs. Se [Översikt över Privacy Servicen](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en).

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

   Anta att `bodyHiddenStyle` av:

   ```
   #pageContent { opacity:0;}
   ```

## Frågor och svar om sekretess och dataskydd {#concept_41F88DE95D2943178BEC382736B5C038}

Frågor och svar om EU:s allmänna dataskyddsförordning (GDPR), Kaliforniens konsumentintegritetslag (CCPA) och andra internationella integritetskrav som är specifika för [!DNL Target].

### Vad är [!DNL Adobe] för reglerna? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] antingen redan uppfyller eller genomför sina skyldigheter som databehandlare. Adobe har en stark grund för certifierade säkerhets- och integritetskontroller genom design och har gjort produktförbättringar före tidsfristen i maj 2018. Företagskunder ansvarar för att implementera dessa förbättringar och uppdatera nödvändiga policyer och procedurer.

### Måste mitt företag, Data Controller, skicka en GDPR- eller CCPA-begäran till varje [!DNL Adobe Experience Cloud] som används? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Nej, [!DNL Adobe] tillhandahåller ett centralt sätt att hjälpa datakontroller att uppfylla sina GDPR- och CCPA-krav. Datakontroller behöver inte gå direkt till varje lösning.

Alla GDPR- och CCPA-förfrågningar över [!DNL Experience Cloud] lösningar, inklusive [!DNL Target], går igenom en central [!DNL Adobe] API, som för närvarande kallas GDPR API. API:t slutför sedan begäran i alla Data Controller-enheter [!DNL Experience Cloud] lösningspaket.

### Vilken information [!DNL Adobe] kan kunderna radera som svar på en begäran från en registrerade/användare? {#section_4B51D00924EC4166B2442218B69214F0}

Informationen om en enskild besökare inom [!DNL Target] finns i [!DNL Target] Besökarprofil. [!DNL Target] används för att låta kunderna ta bort alla data som är kopplade till ett ID i sina besökarprofiler. Exempel på profildata [!DNL Target] butiker, se [Besökarprofil](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Sammanställda eller anonyma data (t.ex. rapportdata) som inte identifierar en viss individ, eller data som inte är kopplade till en viss individ (t.ex. innehållsdata), omfattas inte av en begäran om att ta bort användare.

[!DNL Target] Besökarprofiler som har varit inaktiva i 90 dagar tas bort som standard, utan någon åtgärd.

### Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] har stöd för följande ID-typer för att hitta en kundprofil:

| Användar-ID | Typ av namnutrymmes-ID | Namnområdes-ID | Definition |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID], tidigare Visitor-ID eller Experience Cloud-ID. Du kan använda JavaScript-API:t för att hitta detta ID (se informationen nedan). |
| TnT ID/Cookie ID(TNTID) | Standard | 9 | [!DNL Target] identifieraren anges som en cookie i besökarens webbläsare. Du kan använda JavaScript-API:t för att hitta detta ID (se informationen nedan). |
| Tredjeparts-ID/CRM-ID (TREDJEPARTYID) | [!DNL Target]-Specifik | Ej tillämpligt | Om du anger [!DNL Target] med din CRM eller annan unik identifieringsinformation för dina kunder. |

>[!NOTE]
>
>Fast [!DNL Target] stöder både cookies från andra tillverkare och cookies från andra tillverkare, cookies från andra tillverkare [!DNL Target] Endast cookies rekommenderas för GDPR och CCPA.

### Hur [!DNL Target] hantera samtyckeshantering? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR och CCPA ändras inte när du måste få samtycke, utan hur du får det. Varje kunds strategi för samtycke är beroende av dess rutiner för datainsamling och -användning samt dess integritetspolicy. Hantering av samtycke stöds inte av och bör inte göras via [!DNL Target] för GDPR och CCPA.

[!DNL Adobe] erbjuder för närvarande inte någon lösning för hantering av samtycke, men det finns olika verktyg på marknaden som kan hantera vissa av de nya kraven. Mer information om sekretessverktyg i allmänhet, inklusive samtyckeshanterare, finns i [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) på *International Association of Privacy Professionals (iaap)* webbplats.

[!DNL Target] har stöd för tillvalsfunktioner via [!DNL Adobe Experience Platform] för att stödja er strategi för samtyckeshantering. Tack vare avanmälningsfunktionen kan kunderna styra hur och när [!DNL Target] -taggen utlöses. Det finns också ett alternativ via [!DNL Adobe Experience Platform] för att förgodkänna [!DNL Target] -tagg. Använda [!DNL Adobe Experience Platform] Vi rekommenderar att du hanterar anmälan. Ytterligare kontroll finns i [!DNL Adobe Experience Platform] för att dölja valda element på sidan före [!DNL Target] som kan vara till hjälp för er strategi för samtycke.

Mer information om GDPR, CCPA och [!DNL Adobe Experience Platform], se [Adobe Privacy JavaScript Library och GDPR](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en). Se även *Anmäl dig till Adobe Target och Adobe Experience Platform* ovan.

### Gör `AdobePrivacy.js` skicka information till GDPR API? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] gör *not* skicka den här informationen till API:t. Kunden måste göra det. Det här biblioteket innehåller bara de ID:n som lagras i webbläsaren för den specifika besökaren.

### Vad gör `removeIdentities` ta bort? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] *endast* tar bort dessa identiteter från webbläsaren, och det beror bara på om [!DNL Adobe] lösningen har implementerat den.

Till exempel: [!DNL Target] tar bort cookies som lagrar ID:n, men [!DNL Adobe Audience Manager] (AAM) tar inte bort det demdex-ID som lagras i en cookie från tredje part.

### Vilken information måste finnas i en [!DNL Target] GDPR- eller CCPA-begäran? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Utöver kraven från den centrala Privacy Servicen finns det ett giltigt GDPR- eller CCPA-meddelande för [!DNL Target] innehåller:

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

### Vilka typer av svar kan jag förvänta mig av [!DNL Target] via GDPR API? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Status för begäran | [!DNL Target] Svarsmeddelande | Scenario |
|--- |--- |--- |
| Bearbetar | Bearbetar | [!DNL Target] har tagit emot GDPR- eller CCPA-begäran och behandlas. |
| Slutförd | Ej tillämpligt - företagskontexten är inte tillämplig | IMS-ID:t i GDPR- eller CCPA-begäran mappas inte till något [!DNL Target] klient.<br>Vissa företag har flera IMS-ID:n. Skicka det IMS-ID där [!DNL Target] har etablerats. |
| Slutförd | Ej tillämpligt - användarkontexten hittades inte | Det ID som anges i GDPR- eller CCPA-begäran för den specifika besökaren eller den registrerade finns inte i [!DNL Target] profilarkiv.<br>Det här resultatet returneras också om du försöker skicka en typ av namnområdes-ID som inte stöds av [!DNL Target] (se ovan för ID:n som stöds). |
| Fel | Felmeddelande (informationen beror på feltypen) | Ett fel uppstod vid hämtning eller borttagning av den begärda dataobjektprofilen.<br>Ett fel uppstod vid överföring till Azure för åtkomstbegäran. |

### Vad svar ger [!DNL Target] Vill du skicka till GDPR API för en åtkomstbegäran? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Svar på begäran om dataåtkomst innehåller en sammanfattning av [!DNL Target] profil för besökaren i fråga. Denna retur skickas till [!DNL Experience Cloud] GDPR API, som i sin tur skickar ett svar till Data Controllers.

Ett exempel [!DNL Target] API-svar för åtkomst kan se ut så här:

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
| namespace | Kallas även datakälla. Se&quot;Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för [!DNL Target]?&quot; i det här avsnittet. |
| type | Den typ av ID som du begärde GDPR- eller CCPA-dataåtkomst för. [!DNL Target] godkänner flera ID-typer, varav vissa är standard och vissa är specifika för [!DNL Target]. Se&quot;Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för [!DNL Target]?&quot; i det här avsnittet. |
| value | ID för namnområdet/datakällan. Se&quot;Vilka ID:n stöds för att hjälpa kunderna att slutföra en GDPR- eller CCPA-begäran om åtkomst och borttagning för [!DNL Target]?&quot; för godkända värden. |
| integrationskod | Integrationskoder är egna namn för datakällorna och hjälper dig att spåra datakällorna enklare än att använda ID:n för datakällor. |

När flera värden anges för att identifiera profiler har varje giltig identifierare en profilfil. En eller flera profilfiler skickas till den centrala GDPR Azure-blobben via GDPR Central API, i formatet [!DNL Target] Profil-JSON-svar.

Ett exempel [!DNL Target] Profil-JSON kan se ut som i följande exempel:

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
| Sample_Parameter | Flera informationsdelar i [!DNL Target] profiler överförs eller tillhandahålls direkt av Data Controller. I det här exemplet överfördes en parameter till [!DNL Target] profil med hjälp av API:t för profiluppdatering. Mer information finns i [Metoder som data hämtas till [!DNL Target]](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/). |
| user.ReturnTimeOfDay | I det här standardfältet anges tiden på dagen för en användares senaste besök. |
| firstSessionStart | Detta standardfält innehåller den tid på dagen då användarens första session påbörjades. |
| user.sessionCountScript | Flera informationsdelar i [!DNL Target] profiler överförs eller tillhandahålls direkt av Data Controller. I det här exemplet ökar ett profilskript antalet sessioner som den här besökaren har gjort på Data Controller-platsen. Mer information finns i [Profilskriptattribut](/help/main/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Det här kodexemplet är en förkortad version av en [!DNL Target] profil-JSON för illustration. Många av fälten i [!DNL Target] profilen är inte standard. Vad som returneras beror på vilken information som finns i den specifika besökarprofilen.

### Gör [!DNL Target] Vill du ha stöd för obehörig IP-hantering? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] har stöd för IP-förfalskning om du väljer att använda det som en del av GDPR- eller CCPA-implementeringsstrategin. Mer information finns i [Integritet](https://developer.adobe.com/target/before-implement/privacy/privacy/).

### Bör jag göra något för att förhindra att mina data delas eller säljs till tredje part?

[!DNL Target] tillåter inte kunder att dela eller sälja data direkt från [!DNL Target] till tredje part, så det finns ingen avanmälan från försäljning för [!DNL Target].
