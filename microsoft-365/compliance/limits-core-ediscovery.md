---
title: Limites no caso de descoberta eletrônica principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve os limites no caso de descoberta eletrônica principal no Microsoft 365.
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551359"
---
# <a name="limits-in-core-ediscovery"></a>Limites na descoberta eletrônica principal

A tabela a seguir lista os limites para os principais casos de descoberta eletrônica e suspensões associados a uma ocorrência de descoberta eletrônica principal. Para obter mais informações sobre a descoberta eletrônica principal, consulte [Overview of Core eDiscovery](ediscovery-cases.md).
    
  |**Descrição do limite**|**Limite**|
  |:-----|:-----|
  |Número máximo de casos para uma organização  <br/> |Sem limite  <br/> |
  |Número máximo de isenções de caso para uma organização  <br/> |10.000  <br/> |
  |Número máximo de caixas de correio em uma única retenção de caso  <br/> |1.000  <br/> |
  |Número máximo de sites do SharePoint e do OneDrive for Business em uma única retenção de caso  <br/> |100  <br/> |
  |Número máximo de casos exibidos na Home Page principal da descoberta eletrônica e o número máximo de itens exibidos nas guias isenções, pesquisas e exportação em um caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> para exibir uma lista de mais de 1.000 casos, isenções, pesquisas ou exportações, você pode usar o cmdlet do PowerShell de segurança & conformidade do Office 365 correspondente:<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
