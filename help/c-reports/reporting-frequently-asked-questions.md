---
keywords: troubleshooting;metric discrepancies;FAQ;reports
description: Lista med vanliga frågor om rapportering i Adobe Target.
title: Vanliga frågor om rapportering för Adobe Target
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Vanliga frågor om rapportering{#reporting-faq}

Lista med vanliga frågor om rapportering i [!DNL Target].

## Varför innehåller mina [!UICONTROL Experience Targeting] (XT)-rapporter mätvärden för kontrollupplevelser?

XT-aktiviteter ska alltid ha en kontrollupplevelse. Om du använder en XT-aktivitet på ungefär samma sätt som en [!UICONTROL A/B Test] aktivitet, vilket är ett ganska vanligt scenario, är data för kontrollupplevelsen användbara. Du kan ignorera data om kontrollupplevelsen om du inte tycker att de är användbara i dina rapporter.

## Varför är antalet besök lägre i [!DNL Target] än i andra [!DNL Adobe Experience Cloud] lösningar? {#section_7E626FDB417E41B8B58BBF30FB207409}

Mätvärden, t.ex. besök, som rapporteras av [!DNL Target] kommer alltid att vara lägre än det rapporterade antalet i andra [!DNL Experience Cloud] lösningar av flera orsaker:

* [!DNL Target] räknar endast besök för besökare som är kvalificerade för aktiviteten. Andra lösningar kräver besök för besökare som visar sidan, oavsett vilken aktivitet som fört dem till sidan.
* Det kan finnas situationer där olika aktiviteter konkurrerar om samma plats (ömsesidigt uteslutande). Det innebär att besökarna ser olika innehåll på en webbsida, vilket påverkar de mätvärden som rapporteras av [!DNL Target].

## Varför finns det inga data tillgängliga för min aktivitetsrapport? {#section_E4722F6445884130951DF79981C8289B}

Om en aktivitets innehåll levererades till användarna men rapporten inte innehåller några data kontrollerar du att rätt miljö ([värdgrupp](/help/administrating-target/hosts.md)) har valts i rapportens inställningar.

Om du har valt en utvecklingsmiljö kan följande felmeddelande visas: &quot;Det finns inga tillgängliga data för de valda rapportinställningarna.&quot;

Så här ändrar du miljön för en aktivitetsrapport:

1. Klicka **[!UICONTROL Activities]** på önskad aktivitet i listan och klicka sedan på **[!UICONTROL Reports]** fliken.
1. Klicka på kugghjulsikonen för att konfigurera rapportinställningar.

   ![Dialogrutan A/B-inställningar](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >Kugghjulsikonen är inte tillgänglig för [!UICONTROL Automated Personalization] (AP)-rapporter.

1. I listrutan **[!UICONTROL Environment]** väljer du **[!UICONTROL Production]**.

   Rapportdata kanske inte är tillgängliga om du har valt en utvecklingsmiljö.

1. Klicka på **[!UICONTROL Save]**.

Mer information om miljöer finns i [Värdar](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
