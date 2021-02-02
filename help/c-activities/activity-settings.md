---
keywords: Mål och inställningar;mål;prioritet;varaktighet
description: Använd Aktivitetsinställningar i Adobe Target för att hantera mål, prioritet och varaktighet för dina aktiviteter.
title: Aktivitetsinställningar
feature: Activities
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---


# Aktivitetsinställningar

Använd [!UICONTROL Activity Settings] i [!DNL Adobe Target] för att hantera mål, prioritet och varaktighet för dina aktiviteter.

1. Skriv anteckningar om aktivitetens mål.

   Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. Dra för att ändra storlek på fältet [!UICONTROL Objective].
1. Ange aktivitetsprioritet.

   Beroende på dina inställningar varierar gränssnittet och alternativen för [!UICONTROL Priority]. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.

   Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.

   Om det här alternativet inte är aktiverat i [!UICONTROL Administration] > [!UICONTROL Reporting] (standardvärdet) anger du en prioritet: Låg, Medel eller Hög.

   Om du vill aktivera detaljerade prioriteringar klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting] och växlar sedan alternativet [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.

   Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:

   * 0 = Låg
   * 999 = Hög

   För aktiviteter som skapats i tidigare versioner av [!DNL Target Standard/Premium] konverteras låg prioritet till 0, Medel konverteras till 5 och Hög konverteras till 10. Du kan justera dessa värden om det behövs.

   >[!NOTE]
   >
   >Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10.

1. Ange aktivitetens varaktighet.

   Du kan aktivera och inaktivera aktiviteten manuellt eller ange datum och tid för leverans av aktiviteten. Tidskontrollen använder en 24-timmars klocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

   >[!NOTE]
   >
   >Schemaläggning av en aktivitet styr aktivitetens leveranstid. Aktiviteten måste dock aktiveras explicit innan den kan levereras enligt angivet schema.

Sidan [!UICONTROL Goal & Settings] innehåller ytterligare inställningar som varierar beroende på vilken typ av aktivitet du skapar. Mer information om de här inställningarna finns i din aktivitetstyp:

* [A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [Experience Targeting](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Multivariata tester](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Utbildningsvideo: Aktivitetsinställningar ![Självstudiekurs](/help/assets/tutorial.png)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

   >[!VIDEO](https://video.tv.adobe.com/v/17381)
