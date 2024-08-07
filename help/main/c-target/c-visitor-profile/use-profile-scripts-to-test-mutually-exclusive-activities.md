---
keywords: Profilskript;profilskriptattribut;ömsesidigt uteslutande aktiviteter
description: Lär dig hur du använder profilattribut för att ställa in tester i Adobe [!DNL Target]  som jämför flera aktiviteter men inte låter samma besökare delta i varje aktivitet.
title: Kan jag använda profilskript för att testa aktiviteter som utesluter varandra?
feature: Audiences
exl-id: b0b23887-3339-411e-9f5c-64f9d1ba778c
source-git-commit: 34db233e0790f8ef04309c3f4b5acd12b7cdd5ad
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Använd profilskript för att testa aktiviteter som utesluter varandra

Du kan använda profilattribut i [!DNL Adobe Target] för att konfigurera tester som jämför två eller flera aktiviteter, men inte låter samma besökare delta i varje aktivitet.

Genom att testa aktiviteter som utesluter varandra förhindrar du att en besökare i en aktivitet påverkar testresultaten för de andra aktiviteterna. När en besökare deltar i flera aktiviteter kan det vara svårt att avgöra om en positiv eller negativ ökning beror på besökarens erfarenhet av en aktivitet eller om interaktionen mellan flera aktiviteter påverkade resultatet av en eller flera aktiviteter.

Du kan till exempel testa två områden i e-handelssystemet. Du kan testa att göra knappen&quot;Lägg till i kundvagnen&quot; röd istället för blå. Du kan också testa en ny utcheckningsprocess som minskar antalet steg från fem till två. Om båda aktiviteterna har samma lyckade händelse (ett slutfört köp) kan det vara svårt att avgöra om den röda knappen förbättrar konverteringarna eller om samma konverteringar också ökades på grund av den förbättrade utcheckningsprocessen. Genom att dela upp testerna i aktiviteter som utesluter varandra kan du testa varje ändring separat.

Tänk på följande information när du använder något av följande profilskript:

* Profilskriptet måste köras innan aktiviteten startar och skriptet måste vara oförändrat under aktivitetens varaktighet.
* Den här tekniken minskar mängden trafik i aktiviteten, vilket kan kräva att aktiviteten körs längre. Du måste ta hänsyn till detta när du beräknar aktivitetens varaktighet.

## Konfigurera två aktiviteter

Om du vill sortera besökare i grupper som var och en ser olika aktiviteter måste du skapa ett profilattribut. Ett profilattribut kan sortera en besökare i en eller flera grupper. Om du vill konfigurera ett profilattribut med namnet&quot;twogroups&quot; skapar du följande skript:

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 100); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` avgör om profilattributet *twogroups* är inställt för den aktuella besökaren. Om de gör det krävs ingen ytterligare åtgärd.

* `var ran_number=Math.floor(Math.random() *100)` deklarerar en ny variabel som heter ran_number, anger värdet till ett slumpmässigt decimaltal mellan 0 och 1, multiplicerar den med 100 och avrundar den nedåt för att skapa ett intervall på 100 (0-100), vilket är användbart för att ange en procentandel av besökarna som ser aktiviteten.

* `if (ran_number <= 49)` påbörjar en rutin som avgör vilken grupp besökaren tillhör. Om det returnerade numret är 0-49 tilldelas besökaren GroupA. Om värdet är 50-100 tilldelas besökaren GroupB. Gruppen avgör vilken aktivitet besökaren ser.

När du har skapat profilattributet anger du den första aktiviteten för att rikta in den önskade populationen genom att kräva att användarprofilparametern `user.twogroups` matchar det värde som har angetts för GroupA.

>[!NOTE]
>
>Välj en mbox tidigt på sidan. Den här koden avgör om en besökare upplever aktiviteten. Så länge webbläsaren påträffar en mbox kan den användas för att ange det här värdet.

Konfigurera den andra kampanjen så att användarprofilparametern `user.twogroups` matchar det värde som angetts för GroupB.

## Konfigurera tre eller flera aktiviteter

Att konfigurera tre eller flera aktiviteter som utesluter varandra liknar att ställa in två, men du måste ändra profilattributet JavaScript för att skapa en separat grupp för varje aktivitet och avgöra vem som ser var och en av dem. Genereringen av slumpmässiga tal skiljer sig åt beroende på om du skapar ett ojämnt eller ojämnt antal grupper.

Om du till exempel vill skapa fyra grupper använder du följande JavaScript:

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 100); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

I det här exemplet är den matematik som används för att generera det slumpmässiga tal som tilldelar en besökare till en grupp densamma som den är med bara två grupper. Ett slumpmässigt decimaltal genereras och avrundas sedan nedåt för att skapa ett heltal.

Om du skapar ett ojämnt antal grupper, eller ett tal som 100 inte delar in jämnt, ska du inte runda av decimalvärdet nedåt till ett heltal. Om du inte avrundar decimaltalet kan du ange intervall som inte är heltal. Du gör detta genom att ändra den här raden:

`var ran_number=Math.floor(Math.random()*100);`

till:

`var ran_number=Math.random()*100;`

Om du till exempel vill placera besökare i tre lika grupper använder du följande kod:

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 100; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
