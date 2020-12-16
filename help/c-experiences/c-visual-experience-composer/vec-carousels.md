---
keywords: Visual Experience Composer;VEC;carousel
description: I det här avsnittet beskrivs hur du skapar en karusell som kan redigeras i Visual Experience Composer (VEC).
title: Skapa Carousel som fungerar i Visual Experience Composer
feature: vec
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Skapa Carousel som fungerar i Visual Experience Composer{#creating-carousels-that-work-in-the-visual-experience-composer}

I det här avsnittet beskrivs hur du skapar en karusell som kan redigeras i Visual Experience Composer (VEC).

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