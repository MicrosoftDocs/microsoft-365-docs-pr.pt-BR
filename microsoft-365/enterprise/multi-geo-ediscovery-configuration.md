---
title: Configurar o Microsoft 365 Multi-Geo eDiscovery
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Saiba como usar o parâmetro Region para configurar a Descoberta e Para uso em locais de satélite em Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923715"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Configuração do Microsoft 365 Multi-Geo eDiscovery

[Advanced eDiscovery recursos](../compliance/overview-ediscovery-20.md) permitem que um administrador de Descoberta eDiscoveria multi-geográfica pesquise todos os geos sem precisar usar um filtro de segurança "Região". Os dados são exportados para a instância do Azure da localização central do locatário multi-geo. 

Sem recursos avançados de Descoberta e, um gerente de Descoberta e/ou administrador de um locatário multi-geo será capaz de conduzir a Descoberta eDiscovery somente no local central desse locatário. Para dar suporte à capacidade de conduzir a Descoberta Digital para locais satélite, um novo parâmetro de filtro de segurança de conformidade chamado "Região" está disponível por meio do PowerShell. Esse parâmetro pode ser usado por locatários cuja localização central está na América do Norte, Europa ou Pacífico Asiático. Advanced eDiscovery é recomendado para locatários cuja localização central não está na América do Norte, Europa ou Pacífico Asiático e que precisam executar a Descoberta eDiscovery em locais geo-satélite. 

O administrador global do Microsoft 365 deve atribuir permissões ao eDiscovery Manager para permitir que outras pessoas executem o eDiscovery e atribuam o parâmetro "Região" no seu Filtro de segurança de conformidade aplicável para especificar a região de execução do eDiscovery como localização do satélite; caso contrário, nenhum eDiscovery será executado na localização por satélite.

Quando a função de gerente ou administrador de Descoberta Eletrônica é definida para uma determinada localização satélite, o gerente ou o administrador só poderá realizar ações de pesquisa de Descoberta Eletrônica em sites do SharePoint e do OneDrive naquela localização satélite. Se ele tentar pesquisar sites do SharePoint ou do OneDrive fora da localização satélite especificada, nenhum resultado será apresentado. Além disso, quando o gerente ou administrador de Descoberta Eletrônica de uma localização satélite aciona uma exportação, os dados são exportados para a instância do Azure daquela região. Isso ajuda as organizações a permanecerem em conformidade, não permitindo que o conteúdo seja exportado para além de fronteiras controladas.

> [!NOTE]
> Caso seja necessário que o gerente de Descoberta Eletrônica pesquise diversas localizações satélites no SharePoint, será necessário criar outra conta de usuário para ele, a qual especifique a localização satélite alternativa onde se encontram os sites do OneDrive ou do SharePoint.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Para configurar o Filtro de Segurança de Conformidade para uma região:

1. [Conecte-se ao Centro de conformidade e segurança do Microsoft 365 PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. Use a seguinte sintaxe:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Por exemplo:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Confira o artigo sobre o cmdlet [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) para ver os sintaxe e parâmetros adicionais.