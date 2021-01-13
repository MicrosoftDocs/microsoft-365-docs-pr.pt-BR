---
title: Limites no caso principal de Descoberta eDiscovery
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
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799658"
---
# <a name="limits-in-core-ediscovery"></a>Limites na Descoberta eDiscovery Principal

A tabela a seguir lista os limites para os principais casos de Descoberta e retém associados a um caso de Descoberta eDiscovery principal. Para obter mais informações sobre a Descoberta Principal, consulte [Visão Geral da Descoberta Principal do eDiscovery.](ediscovery-cases.md)
    
  | Descrição do limite | Limite |
  |:-----|:-----|
  |Número máximo de casos para uma organização  <br/> |Sem limite  <br/> |
  |Número máximo de retém de caso para uma organização  <br/> |10.000  <br/> |
  |Número máximo de caixas de correio em um único caso de espera  <br/> |1.000  <br/> |
  |Número máximo de sites do SharePoint e do OneDrive for Business em um único caso de espera  <br/> |100  <br/> |
  |Número máximo de casos exibidos na home page principal da Descoberta e o número máximo de itens exibidos nas guias Regiões, Pesquisas e Exportação em uma ocorrência. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para exibir uma lista de mais de 1.000 casos, regiões, pesquisas ou exportações, você pode usar os cmdlets correspondentes do PowerShell de Conformidade e Segurança do Office 36 & 5:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Para obter mais informações sobre limites relacionados a pesquisas de conteúdo e exportações associadas a um caso de Descoberta eDiscovery Principal, consulte Limites para Pesquisa de Conteúdo e Descobertas Principais [de eDiscovery](limits-for-content-search.md).