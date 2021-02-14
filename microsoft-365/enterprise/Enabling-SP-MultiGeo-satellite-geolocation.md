---
title: Ativando as funcionalidades multigeográficas do SharePoint em sua localização geográfica por satélite
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Este artigo fornece informações para administradores globais ou do SharePoint sobre a habilitação do SharePoint Multi-Geo em localizações geográficas por satélite.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687490"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Ativando as funcionalidades multigeográficas do SharePoint em sua localização geográfica por satélite

Este artigo destina-se a administradores Globais ou do SharePoint que tenham criado um local de satélite multigeográfico **antes** dos recursos multigeográficos do SharePoint terem se tornado disponíveis, em 27 de março de 2019, e que não tenham habilitado as funcionalidades multigeográficas do SharePoint em suas localizações geográficas por satélite. 

>[!Note]
>Se você adicionou uma nova localização geográfica **depois de 27 de março**, não será necessário executar estas instruções, pois sua nova localização geográfica já estará habilitada para as funcionalidades geográficas do OneDrive e SharePoint.

Estas instruções permitirão que você habilite o SharePoint em seu local de satélite, para que os seus usuários de satélite multigeográfico aproveitem as funcionalidades multigeográficas do OneDrive e SharePoint no O365. 

>[!IMPORTANT]
>Por favor, note que esta é uma habilitação unidirecional. Depois de definir o modo SPO, você não poderá reverter seu locatário para somente o modo multigeográfico do OneDrive sem um escalonamento com suporte. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Para definir uma localização geográfica no modo SPO

Para definir uma localização geográfica no modo SPO, conecte-se à localização geográfica que você deseja definir no modo SPO:

1.    Abra seu Shell de Gerenciamento do SharePoint Online 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Essa operação normalmente leva cerca de uma hora enquanto executamos vários retornos de publicação no serviço e recarimbamos seu locatário. Após pelo menos 1 hora, execute um Get-SPOMultiGeoExperience.  Isso mostrará se esta localização geográfica está no modo SPO.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Certos caches no serviço são atualizados a cada 24 horas, portanto, é possível que, por um período de até 24 horas, o seu satélite geográfico possa se comportar intermitentemente como se ainda estivesse no modo ODB. Isso não gera problemas técnicos. 
 
Para obter informações adicionais sobre as funcionalidades multigeográficas do SharePoint, consulte [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


