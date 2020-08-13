---
keywords: Target;reports;report settings;environment;lift;lift bound;variance;confidence;control
description: Rapporterna innehåller flera datapunkter och visualiseringsrepresentationer som hjälper dig att förstå de lyftgränser och den konfidensnivå som är kopplad till din aktivitet. På så sätt kan du bättre avgöra en vinnare.
title: Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse
feature: report settings
uuid: 2899503a-d81e-4dc3-b258-a5ecafd1d1a4
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---


# Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse{#average-lift-lift-bounds-and-confidence-interval}

Rapporterna innehåller flera datapunkter och visualiseringsrepresentationer som hjälper dig att förstå de lyftgränser och den konfidensnivå som är kopplad till din aktivitet. På så sätt kan du bättre avgöra en vinnare.

## Genomsnittligt intervall för Lyft, Lyft gränser och Bekräftelse {#topic_AFFDC672A8A34D028B100EF6BE5D8129}

Rapporterna innehåller flera datapunkter och visualiseringsrepresentationer som hjälper dig att förstå de lyftgränser och den konfidensnivå som är kopplad till din aktivitet. På så sätt kan du bättre avgöra en vinnare.

>[!NOTE]
>
>Den här funktionen är bara tillgänglig när du visar rapporter i tabellvyn. Den här funktionen är inte tillgänglig för aktiviteter som använder [Analytics som rapportkälla (A4T)](../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Översikt {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

Lyftinformationen i gränssnittet för målrapportering omfattar:

| Element | Detaljer |
|--- |--- |
| Lyft | Det stora talet och pilen återspeglar lyftets förväntade värde. Detta tal är mittpunkten i lyftintervallen. Den förväntade liftpilen visas i grått tills förtroendet passerar 95%. Efter detta tröskelvärde visas pilen som röd eller grön, baserat på negativ respektive positiv lyft. |
| Lyft gränser | Detta är 95% konfidensintervallet för lyften. Den visas som ett intervall under den genomsnittliga lyften. Se Exempel på beräkning nedan för ett exempel på hur dessa lyftegränser beräknas. |
| Boxplot Graph | Kartongdiagrammet i Target-gränssnittet representerar det förväntade värdet och 95 % konfidensintervall för det aktuella framgångsmåttet. Se det som ett grafiskt sätt att visa information om lyft och lyft.<br>Det finns några viktiga sätt som Target hjälper dig att tolka förtroendeinformationen, bland annat genom färg. I diagrammet visas eventuell överlappning i konfidensintervallet för en viss upplevelse med kontrollens konfidensintervall i grått och alla intervall för en specifik upplevelses konfidensintervall som är över eller under kontrollens konfidensintervall i grönt respektive rött.<br>Längden på kartongfältet representerar hur stort konfidensintervallet är på ett lättförståeligt sätt. När du samlar in mer data i din aktivitet ändras fältet och ändras. Konfidensintervallet härleds från variansen och provstorleken (antal besökare). Ju mindre variansen är och desto större samplingsstorlek desto kortare blir konfidensintervallet. |
| Förtroende | Förtroendet hos en upplevelse eller ett erbjudande representerar sannolikheten för att den tillhörande upplevelsen/erbjudandet över kontrollupplevelsen/erbjudandet är&quot;verklig&quot; (inte orsakad av en slumpmässig chans). Normalt är 95% den rekommenderade konfidensnivån för att hissen ska anses signifikant. |

I följande bild visas information om Lyft-gränser och konfidensnivå:

![Rapport om genomsnittlig lyft- och tillförlitlighetsnivå](/help/c-reports/c-report-settings/assets/lift-screenshot-new.png)

## Hur beräknas Lyft-gränser? {#section_1D360781D972483693680BE0F07AEAD1}

Lyftgränserna representerar de 95-procentiga konfidensintervallen för lyften som den specifika upplevelsen eller erbjudandet har över kontrollupplevelsen eller erbjudandet. Det betyder att det faktiskt finns en 95-procentig chans att vara mellan dessa gränser.

Lyftgränserna beräknas med följande formel:

![](assets/lift_diagram.png)

Det finns ytterligare en beräkning som ska komma fram till inmatningen till våra lyft-gränser:

* **t-värde:** Den kritiska statistiken för vår 95-procentiga konfidensnivå är 1,96. Du kan läsa mer om [t-values här](https://en.wikipedia.org/wiki/T-statistic).
* **Lyft varians:** Standardfelet i Experience N:s framgångsmått och standardfelet i kontrollupplevelsens framgångsmått behövs för att fastställa lyftoperationen, som beräknas med följande formel (som illustreras om framgångsmåttet är konvertering).

   ![](assets/lift_variance.png)

* **Standardfel för konverteringsgrad/lyckat mått:** Standardfelet beräknas på samma sätt för Experience N och Control, med följande formel (visas om framgångsmåttet är konvertering). Du kan läsa mer om [standardfel här](https://en.wikipedia.org/wiki/Standard_error).

   ![](assets/standard_error.png)

   >[!NOTE]
   >
   >Standardfelet för resultaträkningsaktiviteter baseras på exempelvariationen för intäkterna.

## Exempelberäkning {#section_35BD6FB7AFD346E28BA093147C248471}

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
>Förvänta dig mindre avvikelser mellan manuella beräkningar med hjälp av formlerna ovan och siffrorna som visas i rapporten. Skillnaden kan tillskrivas det faktum att sidvynumren som används vid manuella beräkningar avrundas. Lyften som visas i Target-rapporten baseras på de exakta siffror som erhållits från det totala engagemanget och antalet engagemang. Du kan hämta ärendenummer via prestandarapportens API.

## När visas inte Lyft-gränser? {#section_C5622E1E94684DAD937249B51A9E42CC}

I vissa fall visas inte lyftgränser i Target:

* För alla aktiviteter, när det totala antalet besök eller besökare är färre än 30.
* För Automatisk allokering visas inga gränser förrän en upplevelse har uppnått 60-procentig säkerhet.

