---
keywords: Rikting;eec;visual experience disposition;felsök förbättrad experience disposition;felsökning
description: Lär dig hur du felsöker problem som ibland kan uppstå i Adobe [!DNL Target] Enhanced Experience Composer (EEC) under vissa förhållanden.
title: Hur felsöker jag problem som rör den förbättrade Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 7562a1da201b570ee529db9763ef5f4b463f65a8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Felsökning av problem relaterade till [!UICONTROL Enhanced Experience Composer]

Visningsproblem kan ibland uppstå i [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) under vissa villkor.

## EEG läser inte in en intern QA-URL som inte är tillgänglig på offentlig IP. {#section_D29E96911D5C401889B5EACE267F13CF}

Detta kan du lösa genom att tillåtslista följande IP-adresser. Dessa IP-adresser är för Adobe server som används som EEG-proxy. De behövs bara för aktivitetsredigering. Besökare på webbplatsen behöver inte tillåtslista dessa IP-adresser.

Be IT-teamet att tillåtslista följande IP-adresser:

* 34 254 77 200
* 54.73.207.147
* 54.229.152.123
* 3.224.194.242
* 54.90.51.39
* 34.228.136.112
* 54.150.116.11
* 18.178.142.8
* 54.199.107.77
* 99.80.139.221
* 54.78.56.224
* 54.247.179.246
* 54.80.219.243
* 34.201.235.54
* 54.196.224.236
* 35.75.212.45
* 52.199.184.130
* 18.180.161.176

Följande felmeddelande kan visas i [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error-bild](assets/EEC_error.png)

Följande är orsaker till att du kan se det här felmeddelandet och åtgärda problemet:

* **Problem:** Webbplatsdomänen (ISP) blockerar [!UICONTROL Enhanced Experience Composer].

  **Åtgärd:** Tillåtslista de IP-adresser som anges ovan.

* **Problem:** IP-adresserna har tillåtslista men webbplatsen stöder inte TLS version 1.2. [!DNL Target] använder för närvarande standardkonfigurationen 1.2. Före [!DNL Target] 18.4.1 (25 april 2018) hade standardkonfigurationen stöd för TLS 1.0. Mer information finns i [ TLS (Transport Layer Security) Krypteringsändringar ](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **Lösning:** Se följande fråga ([!UICONTROL Enhanced Visual Experience Composer] läses inte in på säkra sidor på min webbplats som använder TLS 1.2).

## EEC laddas inte på säkra sidor som använder TLS 1.0. (endast EEG) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Felmeddelandet som beskrivs ovan kan visas i &quot;[!UICONTROL Enhanced Visual Experience Composer] kommer inte att läsas in på säkra sidor på min webbplats.&quot; om IP-adresserna ovan är tillåtslista men webbplatsen saknar stöd för TLS version 1.2. [!DNL Target] använder för närvarande standardkonfigurationen 1.2. Före [!DNL Target] 18.4.1 (25 april 2018) hade standardkonfigurationen stöd för TLS 1.0. Mer information finns i [ TLS (Transport Layer Security) Krypteringsändringar ](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html) {target=_blank} .

Så här kontrollerar du TLS-versionen på din webbplats med Firefox (andra webbläsare har liknande steg):

1. Öppna den webbplats som påverkas i Firefox.
1. Klicka på ikonen **[!UICONTROL Show Site Information]** i webbläsarens adressfält.

   ![firefox_more_info image](assets/firefox_more_info.png)

1. Klicka på **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![firefox_more_info_2 image](assets/firefox_more_info_2.png)

1. Se TLS-versionsinformationen under Technical Details (Teknisk information):

   ![firefox_more_info_3 image](assets/firefox_more_info_3.png)

1. Om du upptäcker att TLS 1.0 visas på din webbplats kan du läsa [TLS (Transport Layer Security) Krypteringsändringar](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} om du vill ha information om TLS-stödsregler för mål. Om du vill åtgärda situationen för tillfället (gäller till den 12 september 2018){target=_blank} kan du kontakta [kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att få hjälp med konfigurationen för din TLS-version och domänen.

## Jag ser timeout-fel eller&quot;åtkomst nekad&quot;-fel när webbplatser med proxy aktiverat läses in. (endast EEG) {#section_60CBB9022DC449F593606C0E6252302D}

Kontrollera att proxy-IP:n inte är blockerade i din miljö.
