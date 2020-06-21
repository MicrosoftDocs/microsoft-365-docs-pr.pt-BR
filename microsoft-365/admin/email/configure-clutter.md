---
title: Configurar resíduos para sua organização
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
description: 'Saiba como habilitar ou desabilitar o recurso de desordem para todos ou usuários específicos em sua organização, usando o Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780272"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar resíduos para sua organização

> [!TIP]
> A [caixa de entrada destaques](../setup/configure-focused-inbox.md) vai substituir resíduos. Saiba mais: [Atualizar na caixa de entrada destaques e nos nossos planos de email secundário](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, você pode ter que gerenciar o recurso de desordem no Microsoft 365. Para ativar/desativar o recurso de aglomeração para usuários em sua organização, você deve usar o Exchange PowerShell. (As pessoas podem ativá-la/desligar usando estas instruções: [desative/desobstruída no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Confira [usando o PowerShell com o Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) e [Conecte-se ao PowerShell do Exchange Online](https://go.microsoft.com/fwlink/?LinkID=722415) para obter detalhes sobre como usar o Exchange PowerShell. Você precisa ter uma conta que tenha pelo menos a função Administrador de serviços do Exchange e a capacidade de se conectar ao Exchange Online com o PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Tornar o email secundário usando o Exchange PowerShell

Você pode habilitar resíduos manualmente para uma caixa de correio executando o cmdlet [set-desordem](https://go.microsoft.com/fwlink/?LinkID=834446) . Você também pode exibir configurações de resíduos para caixas de correio em sua organização executando o cmdlet de [obtenção-desordem](https://go.microsoft.com/fwlink/?LinkID=834759) . 
  
Ative o email secundário para um único usuário chamado Leonor Marques
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desligar resíduos usando o Exchange PowerShell

Você pode desabilitar a desordem manualmente para uma caixa de correio executando o cmdlet [set-desordem](https://go.microsoft.com/fwlink/?LinkID=834446) . Você também pode exibir configurações de **resíduos** para caixas de correio em sua organização executando o cmdlet de [obtenção-desordem](https://go.microsoft.com/fwlink/?LinkID=834759) . 
  
Desative o email secundário para um único usuário chamado Leonor Marques:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Se você usar o PowerShell para criar seus usuários em massa, será necessário executar [set-desordem](https://go.microsoft.com/fwlink/?LinkID=834446) em relação à caixa de correio de cada usuário para gerenciar o email secundário. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Quando a opção de truncar/desligar aparece para os usuários no Outlook na Web?
<a name="bkmk_onoff"> </a>

Como administrador, você pode reabilitar resíduos usando o Exchange PowerShell. Depois disso, a caixa de entrada destaques será desativada e a desordem ficará ativa novamente. 
  
 **Se você estiver usando o Outlook na Web com uma assinatura do Microsoft 365 Business Premium:**
  
- Se o usuário está com aglomeração habilitada: 
    
  - As configurações de resíduos aparecem
    
- Se o usuário tem atualmente a caixa de entrada destaques habilitada: 
    
  - Configurações de resíduos não serão exibidas
    
- Se nenhuma caixa de entrada de email secundário ou prioritário estiver habilitada: 
    
  - A desordem e a caixa de entrada destaques aparecem como opções nas configurações de email do usuário
    
 **Se você estiver usando o Outlook.com:**
  
- Se o usuário está com aglomeração habilitada: 
    
  - As configurações de resíduos aparecem
    
- Se o usuário tem atualmente a caixa de entrada destaques habilitada: 
    
  - Configurações de resíduos não serão exibidas
    
- Se nenhuma caixa de entrada de email secundário ou prioritário estiver habilitada: 
    
  - A desordem e a caixa de entrada destaques aparecem como opções nas configurações de email do usuário
    
- Se o usuário habilitou a caixa de entrada destaques em algum momento no passado:
    
  - As configurações de resíduos nunca serão exibidas
    
    Outro 
    
  - As configurações de resíduos serão exibidas
    
## <a name="related-articles"></a>Artigos relacionados
<a name="bkmk_onoff"> </a>

[Usar email secundário para classificar mensagens de baixa prioridade no Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Usar email secundário para classificar mensagens de baixa prioridade no OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Desligar resíduos no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

