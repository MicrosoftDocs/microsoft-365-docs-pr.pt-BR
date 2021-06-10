---
title: Usar pop-outs enxutos para reduzir a memória usada ao ler mensagens de email
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Este artigo contém informações para usar pop-outs enxutos para melhorar o desempenho de download de mensagens Outlook na Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925251"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Usar pop-outs enxutos para reduzir a memória usada ao ler mensagens de email

Este artigo contém informações para melhorar o desempenho de download de mensagens Outlook na Web. Este artigo faz parte do planejamento de rede e [ajuste de desempenho para Office 365](./network-planning-and-performance.md) projeto.
  
Como um Office 365 global, você pode configurar um Outlook na Web para fornecer _pop-outs_ enxutos , uma versão menor e menos intensa de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer. Quando os pop-outs enxutos são configurados para Outlook na Web, os componentes renderizados do lado do servidor são carregados que otimizam o desempenho.
  
> [!NOTE]
> A partir de março de 2018, os pop-outs enxutos não estão disponíveis para mensagens que especificam restrições de direitos de uso, como o Gerenciamento de Direitos de Informação (IRM).
  
Esses recursos continuarão a funcionar na janela principal, mas não estão disponíveis em pop-outs enxutos:
  
- Suplementos do Outlook
  
- Skype for Business presença
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Para configurar pop-outs enxutos para todos os usuários em sua Office 365 organização
  
1. [Conexão usar Exchange Online PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)
  
2. Execute o cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) com o parâmetro LeanPopoutEnabled da seguinte forma:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Por exemplo, para habilitar pop-outs enxutos para todos os usuários em sua organização:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Para desabilitar os pop-outs enxutos para todos os usuários em sua organização:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```