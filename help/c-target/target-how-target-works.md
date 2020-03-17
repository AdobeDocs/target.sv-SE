---
keywords: targeting;cookie;first-party cookie;1st-party cookie
description: Adobe Target kan integreras med dina webbsidor med hjälp av JavaScript-biblioteket at.js eller mbox.js.
title: Så här fungerar målinriktning
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Så här fungerar målinriktning{#how-targeting-works}

Adobe Target kan integreras med dina webbsidor med hjälp av JavaScript-biblioteket at.js eller mbox.js.

[!DNL Target Classic] använda rutor runt varje område på sidan där du vill visa riktat innehåll eller samla in data. Dessa kryssrutor är inte obligatoriska i [!DNL Target Standard]. I stället behöver du bara köra optimeringsaktiviteterna i ett JavaScript-bibliotek på varje sida.

Varje gång en besökare begär en målaktiverad sida [!DNL Target] använder följande process för att leverera erbjudanden:

1. En kund begär en sida från servern och den visas i webbläsaren.
1. En cookie för första part ställs in i kundens webbläsare för att ange ett unikt besökar-ID.

   Ett värde [!DNL Experience Cloud visitor ID] anges också om du använder masterprofilen för marknadsföring.

1. Sidan anropar [!DNL Target] antingen via [!DNL target.js] filen eller en mbox på sidan.
1. [!DNL Target] refererar till den profil som är associerad med besökaren.
1. [!DNL Target] kör alla profilskript som är associerade med den profilen.
1. [!DNL Target] beräknar svaret.
1. Innehållet visas baserat på reglerna för din aktivitet eller kampanj.

Erbjudandet som visas i ett grundläggande A/B-test väljs slumpmässigt. Som ett resultat av denna slumpmässiga uppdelning av trafiken kan det ta en hel del inledande trafik innan procentandelarna ens tar slut. Om du till exempel har en aktivitet med två upplevelser väljs startupplevelsen slumpmässigt. Om trafiken är liten är det möjligt att andelen besökare kan skevas mot en upplevelse. När trafiken ökar bör procentsatserna bli mer lika.
