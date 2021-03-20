---
title: Arquivo CSV da lista de dispositivos
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
description: Saiba como fazer um arquivo CSV para AutoPilot no Microsoft 365 para empresas.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914733"
---
# <a name="device-list-csv-file"></a>Arquivo CSV da lista de dispositivos

## <a name="device-list-csv-file-format"></a>Formato de arquivo .csv da lista de dispositivos

Para gerenciar e implantar dispositivos por meio do Windows Autopilot, você precisará de um arquivo .csv que contenha informações específicas sobre os dispositivos.
  
As colunas no arquivo de lista de dispositivos devem ter os seguintes headers na ordem especificada:
  
- Coluna A: Número de série do dispositivo

- Coluna B: deixar em branco

- Coluna C: Hash de hardware

Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV. 

Ao adicionar dispositivos, você também precisa adicioná-los a um Perfil. Um perfil é usado para aplicar perfis de implantação do AutoPilot a um dispositivo ou a um grupo de dispositivos.
  
## <a name="related-articles"></a>Artigos relacionados

[Recursos e documentação do Microsoft 365 para empresas](../../business/index.yml)
  
[Começar com o Microsoft 365 para empresas](../../business/microsoft-365-business-overview.md)
  
[Gerenciar o Microsoft 365 para empresas](../../business/manage.md)
