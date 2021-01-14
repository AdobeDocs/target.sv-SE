---
keywords: recommendation;backup;back up
description: Om du använder funktionen för rekommenderad säkerhetskopiering i Adobe Target kommer standardinnehåll inte att visas i rekommendationer som inte har tillräckligt många rekommenderade objekt. Rekommendationer visar i stället resultatet av säkerhetskopieringsalgoritmen.
title: Använd en rekommendation för säkerhetskopiering i Adobe Target Recommendations
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMUse en rekommendation för säkerhetskopiering{#use-a-backup-recommendation}

Om du använder funktionen för rekommenderad säkerhetskopiering i Adobe Target kommer standardinnehåll inte att visas i rekommendationer som inte har tillräckligt många rekommenderade objekt. Rekommendationer visar i stället resultatet av säkerhetskopieringsalgoritmen.

Om du inte använder en rekommendation för säkerhetskopiering och en rekommendation inte har tillräckligt många objekt för att fylla skärmen, visas standardinnehållet för användaren.

>[!NOTE]
>
>Ytterligare information finns i avsnittet [Innehåll i avsnittet Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content), inklusive en matris som förklarar de resultat du får när du använder alternativen [!UICONTROL Partial Design Rendering] och [!UICONTROL Show Backup Recommendations] tillsammans eller separat.

Funktionen för rekommendation av säkerhetskopiering använder alltid de mest visade objekten på webbplatsen för att fylla i återstående platser efter att algoritmens data har använts. Mallen är till exempel konfigurerad att visa fem rekommenderade objekt och du använder algoritmen *Inköpstillhörigheter*. Men du har bara tillräckligt med data för att fylla två av de fem kortplatserna, så funktionen för rekommendation av säkerhetskopiering fyller de andra tre platserna med toppvisade objekt.

Rekommendationer för säkerhetskopiering väljs slumpmässigt bland de 500 mest visade produkterna på hela webbplatsen. Datatidperioden för rekommendationer för säkerhetskopiering är en vecka.

De 500 mest visade resultaten ordnas sekventiellt och delas sedan upp i grupper om 20. Facken serveras i ordning, men resultaten inom varje hink slumpmässigt och returneras till sidan. Om användarna uppdaterar sidan visas nya, slumpmässiga resultat. Om resultatmängden från samlingens union och filtreringsreglerna är mindre än 20, väljs den slumpmässigt från samlingen.

Denna låsningsprocess innebär att rekommendationer för säkerhetskopiering visas i följande ordning:

1. Visa de 20 mest visade objekten, slumpmässigt och sedan
1. Visa de nästa 20 mest visade objekten, slumpmässigt och sedan
1. Visa de nästa 20 mest visade objekten, slumpmässigt,
1. Och så vidare

Utan att behöva buckalisera rekommendationerna för säkerhetskopiering skulle det ha varit möjligt att visa det 499:e mest visade objektet, följt av det 200:e mest visade objektet, följt av det 380:e mest visade objektet och så vidare. Med låsningsprocessen säkerställs att de mest visade objekten rekommenderas först.

>[!NOTE]
>
>Om du grupperar dina objekt i kataloger används även katalogen i de säkerhetskopieringsrekommendationer som genereras för varje algoritm i rekommendationen, så endast objekt i katalogen inkluderas i säkerhetskopieringsrekommendationen.

Objekt som utesluts av globala undantagsregler används inte som rekommendation för säkerhetskopiering.

Rekommendationer för säkerhetskopiering är aktiverade som standard och fyller i de extra platserna i en mall med ett slumpmässigt urval av de vanligaste objekten på platsen.

Dubbletter tas bort från grupper med rekommendationer.

Att använda rekommendationer för säkerhetskopiering är vanligtvis en del av diskussionen med implementeringsteamet under din första konfiguration. Kontakta din kontoansvarige om du vill ändra inställningen för rekommenderad säkerhetskopiering efter implementeringen.

Om Aktivera partiell designåtergivning (se [Innehållsinställningar](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)) inte är aktiverat och mallen inte visas, visas antingen rekommendationen eller standardinnehållet.
