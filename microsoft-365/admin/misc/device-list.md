---
title: Arquivo CSV de lista de dispositivos
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Saiba como criar um arquivo CSV para o piloto automático no Microsoft 365 for Business.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399357"
---
# <a name="device-list-csv-file"></a>Arquivo CSV de lista de dispositivos

## <a name="device-list-csv-file-format"></a>Formato de arquivo. csv de lista de dispositivos

Para gerenciar e implantar dispositivos por meio do Windows AutoPilot, você precisará de um arquivo. csv que contenha informações específicas sobre os dispositivos.
  
As colunas no arquivo de lista de dispositivos devem ter os seguintes cabeçalhos na ordem especificada:
  
- Coluna A: Número de série do dispositivo

- Coluna B: deixar em branco

- Coluna C: Hash de hardware

Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV. 

Ao adicionar dispositivos, você também precisa adicioná-los a um perfil. Um perfil é usado para aplicar perfis de implantação do piloto automático a um dispositivo ou a um grupo de dispositivos.
  
## <a name="related-articles"></a>Artigos relacionados

[Documentação e recursos do Microsoft 365 for Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introdução ao Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[Gerenciar o Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/business/manage)
  
