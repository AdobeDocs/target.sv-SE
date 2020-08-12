---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Information om Adobe Target API:er, inklusive API:erna för administration, leverans, rapportering och profil.
title: Adobe Target API - översikt
topic: APIs
translation-type: tm+mt
source-git-commit: 84cd5d41655baaaadeba63954858730ce956e039
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---


# Adobe Target API - översikt

Adobe Target API:er kan grupperas efter typ.

| API-typ | Vad du kan göra | Hämta länk | Andra praktiska länkar |
| --- | --- | --- |--- |
| Administratör | Skapa, ändra och ta bort aktiviteter, målgrupper, erbjudanden och andra objekt (inklusive [!DNL Recommendations] enheter, kriterier, design osv.). API: [!DNL Recommendations] erna är en typ av admin-API.) | <UL><li>[Target Admin API Postman Collection](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Använda Recommendations-API:er](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html) i *Adobe Target Tutorials* |
| Leverans | Hämta optimerat och personaliserat innehåll från [!DNL Target] för leverans till slutanvändare. | [Target Delivery API Postman Collection](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Rapportering | Exportera aktivitetsresultat och andra rapportresultat. | Rapporterings-API:er ingår i [Target Admin API Postman-samlingen](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Profil | Hämta och ändra användarprofiler som lagras i Adobe Target. | [Målprofil-API Postman Collection](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Observera skillnaden mellan **admin-API:er** (inklusive [!DNL Recommendations] API:er), som gör att du kan konfigurera olika aspekter av Adobe Target jämfört med **leverans-API:er**, som du kan använda för att hämta innehåll. Admin-API:er kräver autentisering, men leverans-API:er gör det inte.
>
>Om du vill använda Adobe Target Admin API:er måste du först konfigurera autentiseringen med Adobe I/O. Mer information finns i [Konfigurera autentisering](https://docs.adobe.com/content/help/en/target-learn/tutorials/apis/configure-io-target-integration.html) i *Adobe Target Tutorials*.
