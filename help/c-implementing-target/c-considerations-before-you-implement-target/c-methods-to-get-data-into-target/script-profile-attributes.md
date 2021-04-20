---
keywords: implementera;implementera;konfigurera;konfigurera;skriptprofilattribut
description: Hämta data till Target med skriptprofilattribut.
title: Hur hämtar jag data till målet med hjälp av skriptprofilattribut?
feature: Implementation
role: Developer
exl-id: c323fb4c-f263-43d4-8523-9f42c2913542
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# Skriptprofilattribut

Skriptprofilattribut är namn/värde-par som definieras i [!DNL Adobe Target]-lösningen. Värdet avgörs av om ett JavaScript-fragment körs på målservern per serveranrop.

Användare skriver små kodfragment som körs per mbox-anrop och innan en besökare utvärderas för målgrupps- och aktivitetsmedlemskap.

## Format

Skriptprofilattribut skapas i målgruppsavsnittet. Alla attributnamn är giltiga och värdet är resultatet av en JavaScript-funktion som skrivits av Target-användaren. Attributnamnet prefixeras automatiskt av användaren . &quot; i Target för att skilja dem från profilattribut på sidan.

Kodfragmentet är skrivet i JS-språket Rhino och kan referera till tokens och andra värden.

## Exempel på användningsfall

* **Cart Abandonment**: När besökaren når kundvagnen ställer du in profilskriptet på 1. Återställ besökaren till 0 när besökaren konverterar. Om värdet = 1 har besökaren en artikel i kundvagnen.
* **Besök Antal**: Vid varje nytt besök ökar du antalet med 1 för att hålla reda på hur ofta en besökare återvänder till webbplatsen.

## Fördelar med metoden

Inga sidkodsuppdateringar krävs.

Körs före målgrupps- och aktivitetsmedlemskapsbeslut, så dessa profilskriptattribut kan påverka medlemskapet för ett enda serversamtal.

Kan vara mycket robust. Upp till 2 000 instruktioner kan köras per skript.

## Caveats

Kräver JavaScript-kunskaper.

Körningsordningen för profilskript kan inte garanteras, så de kan inte vara beroende av varandra.

Kan vara svårt att felsöka.

## Exempel på koder

Profilskript är relativt flexibla:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Länkar till relevant information

[Profilskriptattribut](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)
