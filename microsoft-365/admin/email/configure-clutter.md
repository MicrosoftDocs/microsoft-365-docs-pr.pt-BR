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
description: 'Saiba como habilitar ou desabilitar o recurso Desorganização para todos ou usuários específicos em sua organização usando o Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780272"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar o Clutter para sua organização

> [!TIP]
> [A Caixa de Entrada](../setup/configure-focused-inbox.md) Focada substituirá o Clutter. Saiba mais: [atualização na Caixa de Entrada Focada e nossos planos para o Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, você pode ter que gerenciar o recurso Desorganização no Microsoft 365. Para ativar/desativar o recurso Desorganização para usuários em sua organização, você deve usar o Exchange PowerShell. (Os indivíduos podem a ativar/desativar usando estas instruções: [Desativar/ativar o Clutter no Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
Confira o [uso do PowerShell com o Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) e [conecte-se ao PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) do Exchange Online para obter detalhes sobre como usar o Exchange PowerShell. Você precisa ter uma conta que tenha pelo menos a função de administrador do Serviço do Exchange e a capacidade de se conectar ao Exchange Online com o PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Ativar o Clutter usando o Exchange PowerShell

Você pode habilitar o Email Desorganizou manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446) Você também pode exibir as configurações de Email de Email de sua organização executando o cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759) 
  
Ativar o Clutter para um único usuário chamado Allie Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desativar o Clutter usando o Exchange PowerShell

Você pode desabilitar o Email Desorganizar manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446) Você também pode exibir as **configurações** de Email de Email de sua organização executando o cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759) 
  
Desativar o Clutter para uma única usuária chamada Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Se você usar o PowerShell para criar seus usuários em massa, precisará executar [o Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) na caixa de correio de cada usuário para gerenciar o Clutter. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Quando a opção Desorganização é exibida para os usuários no Outlook na Web?
<a name="bkmk_onoff"> </a>

Como administrador, você pode reabilitar o Clutter usando o Exchange PowerShell. Quando isso for feito, a Caixa de Entrada Focada será desligada e o Clutter estará ativo novamente. 
  
 **Se você estiver usando o Outlook na Web com uma assinatura do Microsoft 365 Business Premium:**
  
- Se o usuário atualmente tiver o Clutter habilitado: 
    
  - As configurações de desorganização são exibidas
    
- Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada: 
    
  - As configurações de desorganização não serão exibidas
    
- Se nem o Clutter ou a Caixa de Entrada Focada estiver habilitada: 
    
  - O Email e a Caixa de Entrada Focada aparecem como opções nas Configurações de Email do usuário
    
 **Se você estiver usando Outlook.com:**
  
- Se o usuário atualmente tiver o Clutter habilitado: 
    
  - As configurações de desorganização são exibidas
    
- Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada: 
    
  - As configurações de desorganização não serão exibidas
    
- Se nem o Clutter ou a Caixa de Entrada Focada estiver habilitada: 
    
  - O Email e a Caixa de Entrada Focada aparecem como opções nas Configurações de Email do usuário
    
- Se o usuário tiver habilitado a Caixa de Entrada Focada em algum momento no passado:
    
  - As configurações de desorganização nunca serão exibidas
    
    Caso contrário, 
    
  - As configurações de desorganização serão exibidas
    
## <a name="related-articles"></a>Artigos relacionados
<a name="bkmk_onoff"> </a>

[Usar o Clutter para classificar mensagens de baixa prioridade no Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Usar o Clutter para classificar mensagens de baixa prioridade no OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Desativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

