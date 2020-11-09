---
keywords: Target;reports;report settings;environment;lift;lift bound;variance;confidence;control
description: Rapporterna innehåller flera datapunkter och visualiseringsrepresentationer som hjälper dig att förstå vilka lyftgränser och konfidensnivå som är kopplade till din Adobe Target-aktivitet, så att du kan avgöra en vinnare på ett mer korrekt sätt.
title: Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse
feature: report settings
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---


# Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse

Rapporterna innehåller flera datapunkter och visualiseringsrepresentationer som hjälper dig att förstå de lyftgränser och den konfidensnivå som är kopplad till din [!DNL Adobe Target] aktivitet, så att du bättre kan avgöra en vinnare.

>[!NOTE]
>
>Den här funktionen är bara tillgänglig när du visar rapporter i [!UICONTROL Table] vyn. Den här funktionen är inte tillgänglig för aktiviteter som använder [Analytics som rapportkälla (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Tolka data {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

Följande bild visar [!UICONTROL Lift Bounds and Confidence Level] information:

![Rapport om genomsnittlig lyft- och tillförlitlighetsnivå](/help/c-reports/c-report-settings/assets/lift-screenshot-new.png)

Lyften och förtroendeinformationen i det [!DNL Target] rapporterande användargränssnittet omfattar:

### Lyft

Det stora talet och pilen återspeglar lyftets förväntade värde. Detta tal är mittpunkten i lyftintervallen. Den förväntade liftpilen visas i grått tills förtroendet passerar 95%. Efter detta tröskelvärde visas pilen som röd eller grön, baserat på negativ respektive positiv lyft.

### Lyft gränser

Detta är 95% konfidensintervallet för lyften. Den visas som ett intervall under den genomsnittliga lyften. Se [Exempelberäkning](#example) nedan för ett exempel på hur dessa lyftegränser beräknas.

### Diagramdiagram

Kartongdiagrammet i gränssnittet representerar det förväntade värdet och 95 % konfidensintervall för det aktuella framgångsmåttet. [!DNL Target] Se det som ett grafiskt sätt att visa information om lyft och lyft.

Det finns några viktiga sätt [!DNL Target] att tolka förtroendeinformationen, bland annat genom färg. I diagrammet visas eventuell överlappning i konfidensintervallet för en viss upplevelse med kontrollens konfidensintervall i grått och alla intervall för en specifik upplevelses konfidensintervall som är över eller under kontrollens konfidensintervall i grönt respektive rött.

Längden på kartongfältet representerar hur stort konfidensintervallet är på ett lättförståeligt sätt. När du samlar in mer data i din aktivitet ändras fältet och ändras. Konfidensintervallet härleds från variansen och provstorleken (antal besökare). Ju mindre variansen är och desto större samplingsstorlek desto kortare blir konfidensintervallet.

### Förtroende

Förtroendet hos en upplevelse eller ett erbjudande representerar sannolikheten för att den tillhörande upplevelsen/erbjudandet över kontrollupplevelsen/erbjudandet är&quot;verklig&quot; (inte orsakad av en slumpmässig chans). Normalt är 95% den rekommenderade konfidensnivån för att hissen ska anses signifikant.

## Hur beräknas lyftgränser? {#section_1D360781D972483693680BE0F07AEAD1}

Lyftgränserna representerar de 95-procentiga konfidensintervallen för lyften som den specifika upplevelsen eller erbjudandet har över kontrollupplevelsen eller erbjudandet. Det betyder att det faktiskt finns en 95-procentig chans att vara mellan dessa gränser.

Lyftgränserna beräknas med följande formel:

![](assets/lift_diagram.png)

Det finns ytterligare en beräkning som kommer fram till inmatningen till våra lyft-gränser:

* **t-värde:** Den kritiska statistiken för vår 95-procentiga konfidensnivå är 1,96. Du kan läsa mer om [t-values här](https://en.wikipedia.org/wiki/T-statistic).
* **Lyft varians:** Standardfelet i Experience N:s framgångsmått och standardfelet i kontrollupplevelsens framgångsmått behövs för att fastställa lyftoperationen, som beräknas med följande formel (som illustreras om framgångsmåttet är konvertering).

   ![](assets/lift_variance.png)

* **Standardfel för konverteringsgrad/lyckat mått:** Standardfelet beräknas på samma sätt för Experience N och Control, med följande formel (visas om framgångsmåttet är konvertering). Du kan läsa mer om [standardfel här](https://en.wikipedia.org/wiki/Standard_error).

   ![](assets/standard_error.png)

   >[!NOTE]
   >
   >Standardfelet för resultaträkningsaktiviteter baseras på exempelvariationen för intäkterna.

## Exempel på beräkning {#example}

Låt oss titta på en exempelaktivitet med två upplevelser och följande resultat:

| Upplevelse | Besökare | Konverteringar | Konverteringsgrad |
|--- |--- |--- |--- |
| Upplevelse A (kontroll) | 219, 328 | 2,466 | 1.12% |
| Upplevelse B | 218, 362 | 3,040 | 1.39% |

Baserat på våra formler kan vi beräkna de inmatningar vi behöver för lyft-gränserna.

**Standardfel för Experience A (Kontroll)**

![](assets/standard_error_A.png)

**Standardfel för Experience B**

![](assets/standard_error_B.png)

**Lyft avvikelse för upplevelse B**

![](assets/lift_variance_B.png)

**Lyft gränser för upplevelse B**

Lyft för upplevelse B förväntades:

![](assets/lift_bounds_B.png)

Lyftgränserna för Experience B skulle därför vara:

![](assets/lift_bounds_B2.png)

>[!NOTE]
>
>Förvänta dig mindre avvikelser mellan manuella beräkningar med hjälp av formlerna ovan och siffrorna som visas i rapporten. Skillnaden kan tillskrivas det faktum att sidvynumren som används vid manuella beräkningar avrundas. Lyften som visas i [!DNL Target] rapporten baseras på de exakta siffrorna från det totala engagemanget och antalet engagemang. Du kan hämta ärendenummer via prestandarapportens API.

## När visas inte lyftgränser? {#section_C5622E1E94684DAD937249B51A9E42CC}

I vissa fall [!DNL Target] visas inte lyftegränser:

* För alla aktiviteter, när det totala antalet besök eller besökare är färre än 30.
* För [!UICONTROL Auto-Allocate] aktiviteter visas inga gränser förrän en upplevelse har uppnått 60 % förtroende.
