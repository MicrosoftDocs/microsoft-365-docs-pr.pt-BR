---
title: Usar Lean pop-ups para reduzir a memória usada ao ler mensagens de email
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
description: Este artigo contém informações sobre como usar o Lean pop-ups para melhorar o desempenho de download de mensagens no Outlook na Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687408"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Usar Lean pop-ups para reduzir a memória usada ao ler mensagens de email

Este artigo contém informações para melhorar o desempenho de download de mensagens no Outlook na Web. Este artigo faz parte do [planejamento de rede e ajuste de desempenho para o projeto do Office 365](https://aka.ms/tune) .
  
Como administrador global do Office 365, você pode configurar o Outlook na Web para fornecer _Lean pop-ups_, uma versão menor e menos intensa de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer. Quando o Lean pop-ups é configurado para o Outlook na Web, os componentes renderizados no servidor são carregados que otimizam o desempenho.
  
> [!NOTE]
> A partir de março de 2018, Lean pop-ups não estão disponíveis para mensagens que especificam restrições de direitos de uso, como gerenciamento de direitos de informação (IRM).
  
Esses recursos continuarão a funcionar na janela principal, mas não estão disponíveis no Lean pop-ups:
  
- Suplementos do Outlook
  
- Presença do Skype for Business
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Para configurar o Lean pop-ups para todos os usuários na sua organização do Office 365
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).
  
2. Execute o cmdlet [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) com o parâmetro LeanPopoutEnabled da seguinte maneira:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Por exemplo, para habilitar o Lean pop-ups para todos os usuários em sua organização:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Para desabilitar o Lean pop-ups para todos os usuários em sua organização:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
