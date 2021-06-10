---
title: Arquivo CSV da lista de dispositivos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Saiba como fazer um arquivo CSV para o AutoPilot no Microsoft 365 para empresas.
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579213"
---
# <a name="device-list-csv-file"></a>Arquivo CSV da lista de dispositivos

## <a name="device-list-csv-file-format"></a>Formato de arquivo .csv lista de dispositivos

Para gerenciar e implantar dispositivos Windows autopilot, você precisará de um arquivo .csv que contenha informações específicas sobre os dispositivos.
  
As colunas no arquivo de lista de dispositivos devem ter os seguintes headers na ordem especificada:
  
- Coluna A: Número de série do dispositivo

- Coluna B: deixar em branco

- Coluna C: Hash de hardware

Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV. 

Ao adicionar dispositivos, você também precisa adicioná-los a um Perfil. Um perfil é usado para aplicar perfis de implantação do AutoPilot a um dispositivo ou a um grupo de dispositivos.
  
## <a name="related-articles"></a>Artigos relacionados

[Microsoft 365 para recursos e documentação de negócios](../../business/index.yml)
  
[Começar com o Microsoft 365 para empresas](../../business/microsoft-365-business-overview.md)
  
[Gerenciar Microsoft 365 para empresas](../../business/manage.md)
