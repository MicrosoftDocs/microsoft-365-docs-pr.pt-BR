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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Saiba como criar um arquivo CSV para o piloto automático no Microsoft 365 for Business.
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627855"
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
  
[Introdução ao Microsoft 365 for Business](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[Gerenciar o Microsoft 365 para empresas](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
