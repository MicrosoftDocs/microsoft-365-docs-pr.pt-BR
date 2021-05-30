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
description: 'Aprenda a habilitar ou desabilitar o recurso Clutter para todos ou usuários específicos em sua organização, usando Exchange PowerShell. '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706101"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar o Clutter para sua organização

> [!TIP]
> [A Caixa de Entrada Focada](../setup/configure-focused-inbox.md) substituirá o Clutter. Saiba mais: [Atualizar a Caixa de Entrada Focada e nossos planos para o Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, talvez seja preciso gerenciar o recurso Clutter no Microsoft 365. Para ativar/desativar o recurso Clutter para usuários em sua organização, você deve usar Exchange PowerShell. (Os indivíduos podem a turn-lo/off usando estas instruções: [Desativar/ativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Confira Usando [o PowerShell com Exchange Online](/powershell/exchange/exchange-online-powershell) e Conexão para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obter detalhes sobre como usar o Exchange PowerShell. Você precisa ter uma conta que tenha pelo menos a função de administrador do serviço Exchange e a capacidade de se conectar ao Exchange Online com o PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Ativar o Clutter usando Exchange PowerShell

Você pode habilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter) Você também pode exibir as configurações do Clutter para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter) 
  
Ativar o Clutter para um único usuário chamado Allie Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desativar o Clutter usando Exchange PowerShell

Você pode desabilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter) Você também pode exibir **as configurações do Clutter** para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter) 
  
Desativar o Clutter para um único usuário chamado Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Se você usar o PowerShell para criar seus usuários em massa, precisará executar [Set-Clutter](/powershell/module/exchange/set-clutter) na caixa de correio de cada usuário para gerenciar o Clutter. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Quando a opção Clutter on/off aparece para os usuários Outlook na Web?
<a name="bkmk_onoff"> </a>

Como administrador, você pode habilitar o Clutter usando Exchange PowerShell. Depois que isso for feito, a Caixa de Entrada Focalizada será desligada e o Clutter estará ativo novamente. 
  
 **Se você estiver usando Outlook na Web com uma assinatura Microsoft 365 Business Premium:**
  
- Se o usuário tiver Atualmente o Clutter habilitado: 
    
  - As configurações de clutter são exibidas
    
- Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada: 
    
  - As configurações de clutter não serão exibidas
    
- Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada: 
    
  - Tanto o Clutter quanto a Caixa de Entrada Focada aparecem como opções na caixa de correio do usuário Configurações
    
 **Se você estiver usando Outlook.com:**
  
- Se o usuário tiver Atualmente o Clutter habilitado: 
    
  - As configurações de clutter são exibidas
    
- Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada: 
    
  - As configurações de clutter não serão exibidas
    
- Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada: 
    
  - Tanto o Clutter quanto a Caixa de Entrada Focada aparecem como opções na caixa de correio do usuário Configurações
    
- Se o usuário habilitar a Caixa de Entrada Focada em algum ponto do passado:
    
  - As configurações de clutter nunca serão exibidas
    
    Caso contrário, 
    
  - As configurações de clutter serão exibidas
    
## <a name="related-content"></a>Conteúdo relacionado

[Use o Clutter para classificar mensagens de baixa prioridade Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (artigo)\
[Use o Clutter para classificar mensagens de baixa prioridade no OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artigo)\
[Desativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artigo)
