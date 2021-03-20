---
title: Limites no principal caso de Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve os limites no caso principal de Descoberta eDiscovery no Microsoft 365.
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905883"
---
# <a name="limits-in-core-ediscovery"></a>Limites na Descoberta Principal da Descoberta

A tabela a seguir lista os limites para os principais casos de Descoberta e Retém associados a um caso de Descoberta eDiscovery principal. Para obter mais informações sobre a Descoberta Básica, consulte [Overview of Core eDiscovery](./get-started-core-ediscovery.md).
    
  | Descrição do limite | Limite |
  |:-----|:-----|
  |Número máximo de casos para uma organização.  <br/> |Sem limite  <br/> |
  |Número máximo de casos retém para uma organização.  <br/> |10.000  <br/> |
  |Número máximo de caixas de correio em uma única caixa de espera. Esse limite inclui o total combinado de caixas de correio de usuário e as caixas de correio associadas aos Grupos do Microsoft 365, Microsoft Teams e Grupos do Yammer.  <br/> |1.000  <br/> |
  |Número máximo de sites em uma única espera de caso. Esse limite inclui o total combinado de sites do OneDrive for Business, sites do SharePoint e os sites associados aos Grupos do Microsoft 365, Microsoft Teams e Grupos do Yammer.  <br/> |100  <br/> |
  |Número máximo de casos exibidos na home page principal da Descoberta Online e o número máximo de itens exibidos nas guias Regiões, Pesquisas e Exportação dentro de uma ocorrência. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para exibir uma lista de mais de 1.000 casos, regiões, pesquisas ou exportações, você pode usar os cmdlets correspondentes do Office 365 Security & Compliance PowerShell:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Para obter mais informações sobre limites relacionados a pesquisas de conteúdo e exportações associadas a um caso de Descoberta Principal de Descoberta e Descoberta, consulte [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).