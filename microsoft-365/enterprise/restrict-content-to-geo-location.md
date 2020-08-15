---
title: Restringir o conteúdo do site do SharePoint a um local geográfico
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
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Neste artigo, saiba como restringir sites do SharePoint a um local geográfico especificado em um ambiente multigeográfico.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686984"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Restringir o conteúdo do site do SharePoint a um local geográfico

Em algumas circunstâncias você pode optar por impor que um site e o conteúdo do arquivo permaneça na localização geográfica onde o site foi criado, impedindo que o site movido ou impedindo o cache de conteúdo do arquivo do site em outro local geográfico.

Você pode fazer isso usando o cmdlet [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) com o parâmetro **RestrictedToGeo**. Esse parâmetro possui um valor padrão de NULO, mas você pode alterá-lo para um destes procedimentos:

|Restrição|Descrição|
|:----------|:----------|
|NoRestriction|O site pode ser movido para outro local geográfico.|
|BlockMoveOnly|O site não pode ser movido para outro local geográfico, mas o conteúdo do site pode ser armazenada em cache em outros locais geográficos.|
|BlockFull|Site não pode ser movido para outro local geográfico e o conteúdo do arquivo completo não está armazenado em cache em outros locais geográficos. O título dos arquivos (colhidos do conteúdo), o nome do arquivo e outras propriedades do arquivo ainda podem ser armazenados em cache em outras localizações geográficas.<br>O conteúdo armazenado no site antes de ser configurado para o BlockFull, pode continuar a ser armazenado em cache em outras localizações geográficas.|

Use a seguinte sintaxe:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Por exemplo:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
