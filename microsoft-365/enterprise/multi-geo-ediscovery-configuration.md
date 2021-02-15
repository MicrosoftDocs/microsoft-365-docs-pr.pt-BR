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
description: Saiba como usar o parâmetro Region para configurar a Descoberta e para uso em localizações satélites no Microsoft 365 Multi-Geo.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636800"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Configuração do Microsoft 365 Multi-Geo eDiscovery

[As funcionalidades avançadas](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) de Descoberta e Permitem que um administrador de Descobertas Geográficas multi-geográfica pesquise todas as áreas geográficas sem precisar utilizar um filtro de segurança "Região". Os dados são exportados para a instância do Azure da localização central do locatário multi-geo. 

Sem as funcionalidades avançadas de Descoberta eDiscovery, um gerente ou administrador de um locatário multi-geo será capaz de conduzir a descoberta de eDiscovery somente na localização central desse locatário. Para dar suporte à capacidade de conduzir a Descoberta e para localizações via satélite, um novo parâmetro de filtro de segurança de conformidade chamado "Região" está disponível por meio do PowerShell. Esse parâmetro pode ser usado por locatários cuja localização central está na América do Norte, Europa ou Pacífico Asiático. A Descoberta Avançada é recomendada para locatários cuja localização central não está na América do Norte, Europa ou Pacífico Asiático e que precisam realizar a Descoberta eDiscovery em localizações geográficas por satélite. 

O administrador global do Microsoft 365 deve atribuir permissões ao eDiscovery Manager para permitir que outras pessoas executem o eDiscovery e atribuam o parâmetro "Região" no seu Filtro de segurança de conformidade aplicável para especificar a região de execução do eDiscovery como localização do satélite; caso contrário, nenhum eDiscovery será executado na localização por satélite.

Quando a função de gerente ou administrador de Descoberta Eletrônica é definida para uma determinada localização satélite, o gerente ou o administrador só poderá realizar ações de pesquisa de Descoberta Eletrônica em sites do SharePoint e do OneDrive naquela localização satélite. Se ele tentar pesquisar sites do SharePoint ou do OneDrive fora da localização satélite especificada, nenhum resultado será apresentado. Além disso, quando o gerente ou administrador de Descoberta Eletrônica de uma localização satélite aciona uma exportação, os dados são exportados para a instância do Azure daquela região. Isso ajuda as organizações a permanecerem em conformidade, não permitindo que o conteúdo seja exportado para além de fronteiras controladas.

> [!NOTE]
> Caso seja necessário que o gerente de Descoberta Eletrônica pesquise diversas localizações satélites no SharePoint, será necessário criar outra conta de usuário para ele, a qual especifique a localização satélite alternativa onde se encontram os sites do OneDrive ou do SharePoint.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Para configurar o Filtro de Segurança de Conformidade para uma região:

1. [Conecte-se ao Centro de conformidade e segurança do Microsoft 365 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Use a seguinte sintaxe:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Por exemplo:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Confira o artigo sobre o cmdlet [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) para ver os sintaxe e parâmetros adicionais.
