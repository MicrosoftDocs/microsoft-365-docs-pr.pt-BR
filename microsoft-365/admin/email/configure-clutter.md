---
title: Configurar o Clutter para sua organização
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Aprenda a habilitar ou desabilitar o recurso Clutter para todos ou usuários específicos em sua organização, usando o Exchange PowerShell. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915897"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar o Clutter para sua organização

> [!TIP]
> [A Caixa de Entrada Focada](../setup/configure-focused-inbox.md) substituirá o Clutter. Saiba mais: [Atualizar a Caixa de Entrada Focada e nossos planos para o Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, talvez seja preciso gerenciar o recurso Clutter no Microsoft 365. Para ativar/desativar o recurso Clutter para usuários em sua organização, você deve usar o Exchange PowerShell. (Os indivíduos podem a turn-lo/off usando estas instruções: [Desativar/ativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Confira Usando [o PowerShell com o Exchange Online e](/powershell/exchange/exchange-online-powershell) [Conecte-se ao PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online para obter detalhes sobre como usar o Exchange PowerShell. Você precisa ter uma conta que tenha pelo menos a função de administrador do Exchange Service e a capacidade de se conectar ao Exchange Online com o PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Ativar o Clutter usando o Exchange PowerShell

Você pode habilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter) Você também pode exibir as configurações do Clutter para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter) 
  
Ativar o Clutter para um único usuário chamado Allie Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desativar o Clutter usando o Exchange PowerShell

Você pode desabilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter) Você também pode exibir **as configurações do Clutter** para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter) 
  
Desativar o Clutter para um único usuário chamado Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Se você usar o PowerShell para criar seus usuários em massa, precisará executar [Set-Clutter](/powershell/module/exchange/set-clutter) na caixa de correio de cada usuário para gerenciar o Clutter. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Quando a opção Clutter on/off aparece para os usuários no Outlook na Web?
<a name="bkmk_onoff"> </a>

Como administrador, você pode habilitar o Clutter usando o Exchange PowerShell. Depois que isso for feito, a Caixa de Entrada Focalizada será desligada e o Clutter estará ativo novamente. 
  
 **Se você estiver usando o Outlook na Web com uma assinatura do Microsoft 365 Business Premium:**
  
- Se o usuário tiver Atualmente o Clutter habilitado: 
    
  - As configurações de clutter são exibidas
    
- Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada: 
    
  - As configurações de clutter não serão exibidas
    
- Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada: 
    
  - Tanto o Clutter quanto a Caixa de Entrada Focalizada aparecem como opções nas Configurações de Email do usuário
    
 **Se você estiver usando Outlook.com:**
  
- Se o usuário tiver Atualmente o Clutter habilitado: 
    
  - As configurações de clutter são exibidas
    
- Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada: 
    
  - As configurações de clutter não serão exibidas
    
- Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada: 
    
  - Tanto o Clutter quanto a Caixa de Entrada Focalizada aparecem como opções nas Configurações de Email do usuário
    
- Se o usuário habilitar a Caixa de Entrada Focada em algum ponto do passado:
    
  - As configurações de clutter nunca serão exibidas
    
    Caso contrário, 
    
  - As configurações de clutter serão exibidas
    
## <a name="related-articles"></a>Artigos relacionados
<a name="bkmk_onoff"> </a>

[Usar o Clutter para classificar mensagens de baixa prioridade no Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Usar o Clutter para classificar mensagens de baixa prioridade no OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Desativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
