---
keywords: Visual Experience Composer;VEC;carousel
description: Lär dig hur du skapar en karusell som kan redigeras i Adobe [!DNL Target] Visual Experience Composer (VEC).
title: Hur skapar jag Carousel i Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Skapa Carousel som fungerar i Visual Experience Composer

I det här avsnittet visas hur du skapar en karusell som kan redigeras i [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).

När du använder stegen nedan vet [!DNL Target] alltid att den valda bildrutan kommer att ha väljaren för rätt bildruta, även om den ändras i Visual Experience Composer efter några sekunder.

1. Skapa statiska HTML-platshållare.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Lägg till CSS för att utforma utseendet och känslan.

   Använd inte JavaScript för detta.

   >[!NOTE]
   >
   >Alternativet [!UICONTROL Render Using JavaScript] stöds för närvarande inte om det används tillsammans med anpassad kod i Visual Experience Composer.

1. Uppdatera bara classNames för att dölja andra och visa nästa med timern/animeringen.

   Uppdatera aldrig DOM-strukturen med JavaScript.
