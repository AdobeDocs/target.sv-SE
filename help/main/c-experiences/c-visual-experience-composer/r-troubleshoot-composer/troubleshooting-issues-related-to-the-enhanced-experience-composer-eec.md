---
keywords: Rikting;eec;visual experience disposition;felsök förbättrad experience disposition;felsökning
description: Lär dig hur du felsöker problem som ibland kan uppstå i Adobe [!DNL Target] Förbättrad Experience Composer (EEC) under vissa förhållanden.
title: Hur felsöker jag problem som rör den förbättrade Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 2%

---

# Felsökning relaterade till [!UICONTROL Enhanced Experience Composer]

Visningsproblem kan ibland uppstå i [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEG) på vissa villkor.

## EEG läser inte in en intern QA-URL som inte är tillgänglig på offentlig IP. {#section_D29E96911D5C401889B5EACE267F13CF}

Detta kan du lösa genom att tillåtslista följande IP-adresser. Dessa IP-adresser är för Adobe server som används som EEG-proxy. De behövs bara för aktivitetsredigering. Besökare på webbplatsen behöver inte tillåtslista dessa IP-adresser.

Be IT-teamet att tillåtslista följande IP-adresser:

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

Följande felmeddelande kan visas i [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Följande är orsaker till att du kan se det här felmeddelandet och åtgärda problemet:

* **Problem:** Din webbplatsdomän (ISP) blockerar [!UICONTROL Enhanced Experience Composer].

   **Åtgärda:** Tillåtslista de IP-adresser som anges ovan.

* **Problem:** IP-adresserna är tillåtslista men din webbplats stöder inte TLS version 1.2. [!DNL Target] använder för närvarande standardkonfigurationen 1.2. Före [!DNL Target] 18.4.1 (25 april 2018), standardkonfigurationen som stöder TLS 1.0. Mer information finns i [Krypteringsändringar för TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

   **Lösning:** Se följande fråga ( [!UICONTROL Enhanced Visual Experience Composer] läses inte in på säkra sidor på min webbplats som använder TLS 1.2).

## EEC laddas inte på säkra sidor på min webbplats som använder TLS 1.0. (endast EEG) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Felmeddelandet som beskrivs ovan finns i [!UICONTROL Enhanced Visual Experience Composer] kommer inte att läsas in på säkra sidor på min webbplats.&quot; om IP-adresserna ovan är tillåtslista men webbplatsen inte stöder TLS version 1.2. [!DNL Target] använder för närvarande standardkonfigurationen 1.2. Före [!DNL Target] 18.4.1 (25 april 2018), standardkonfigurationen som stöder TLS 1.0. Mer information finns i [Krypteringsändringar för TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

Så här kontrollerar du TLS-versionen på din webbplats med Firefox (andra webbläsare har liknande steg):

1. Öppna den berörda webbplatsen i Firefox.
1. Klicka på **[!UICONTROL Show Site Information]** -ikonen i webbläsarens adressfält.

   ![](assets/firefox_more_info.png)

1. Klicka på **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![](assets/firefox_more_info_2.png)

1. Se TLS-versionsinformationen under Technical Details (Teknisk information):

   ![](assets/firefox_more_info_3.png)

1. Om du ser att din webbplats visar TLS 1.0 kan du gå till [Krypteringsändringar för TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank} om du vill ha information om TLS-stödprincipen. För att rätta till situationen (gäller till den 12 september 2018), kontakta [Kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för konfiguration med TLS-versionen och domänen.

## Jag ser timeout-fel eller&quot;åtkomst nekad&quot;-fel när webbplatser med proxy aktiverat läses in. (endast EEG) {#section_60CBB9022DC449F593606C0E6252302D}

Kontrollera att proxy-IP:n inte är blockerade i din miljö.
