---
title: Excluir um domínio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Aprenda a remover um domínio antigo de Microsoft 365 e mova usuários e grupos para outro domínio.
ms.openlocfilehash: 3586cc8b288b77725c0dd3484629688e98e0a218
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572112"
---
# <a name="remove-a-domain"></a>Excluir um domínio
  
 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Você está removendo seu domínio porque deseja adicioná-lo a um plano de assinatura Microsoft 365 diferente? Ou você só quer cancelar sua assinatura? Você pode [alterar seu plano ou assinatura](../../commerce/subscriptions/switch-to-a-different-plan.md) ou cancelar sua [assinatura](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Passo 1: Mova os usuários para outro domínio

#### <a name="move-users"></a>Mover usuários

::: moniker range="o365-worldwide"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>.

2. Selecione **usuários** > **ativos**.

3. Selecione as caixas ao lado dos nomes de todos os usuários que deseja mover.

4. No topo da página e, em seguida, escolha **domínios de alterar**.

5. No painel **de domínios Alterar,** selecione um domínio diferente.

Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

::: moniker-end

::: moniker range="o365-germany"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>.  

2. Selecione **usuários** > **ativos**.

3. Selecione as caixas ao lado dos nomes de todos os usuários que deseja mover.

4. No topo da página, escolha **mais** > **domínios Editar**.

5. No painel **de domínios Editar,** selecione um domínio diferente.
  
Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

::: moniker-end

::: moniker range="o365-21vianet"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.  

2. Selecione **usuários** > **ativos**.

3. Selecione as caixas ao lado dos nomes de todos os usuários que deseja mover.

4. No topo da página, escolha **mais** > **domínios Editar**.

5. No painel **de domínios Editar,** selecione um domínio diferente.
  
Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

::: moniker-end

#### <a name="move-yourself"></a>Mova-se

::: moniker range="o365-worldwide"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.

2. Vá para **usuários** \> **usuários ativos** e selecione sua conta na lista.

3. Na guia **Conta,** selecione **Gerenciar o nome de usuário** e, em seguida, escolha um domínio diferente.
  
4. Na parte superior, selecione o nome da sua conta e selecione **Sair de sinal**.

5. Faça login com o novo domínio e sua mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Vá para **usuários** \> **usuários ativos** e selecione seu nome na lista.

2. Na seção **Nome de usuário /E-mail,** selecione **Editar** e, em seguida, escolha um domínio diferente.

3. Selecione **Definir como principal** > **Salvar** > **Close**.
  
4. Na parte superior, selecione o nome da sua conta e selecione **Sair de sinal**.

5. Faça login com o novo domínio e sua mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para **usuários** \> **usuários ativos** e selecione seu nome na lista.

2. Na seção **Nome de usuário /E-mail,** selecione **Editar** e, em seguida, escolha um domínio diferente.

3. Selecione **Definir como principal** > **Salvar** > **Close**.
  
4. Na parte superior, selecione o nome da sua conta e selecione **Sair de sinal**.

5. Faça login com o novo domínio e sua mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Passo 2: Mova grupos para outro domínio

::: moniker range="o365-worldwide"

1. No centro administrativo, acesse a página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a>
  
2. Selecione o nome do grupo e, em seguida, na guia **Geral** em **endereço de e-mail, principal,** selecione **Editar**.

3. Use a lista de drop-down para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

::: moniker-end

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro administrativo,</a>acesse a página **Grupos** > **grupos.**

2. Selecione o nome do grupo e selecione **Editar** ao lado **de Name**.

3. Use a lista de drop-down para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro administrativo,</a>acesse a página **Grupos** > **grupos.**

2. Selecione o nome do grupo e selecione **Editar** ao lado **de Name**.

3. Use a lista de drop-down para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Passo 3: Remova o domínio antigo

::: moniker range="o365-worldwide"

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro administrativo, vá para  a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios de</a> configuração.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro administrativo, vá para  a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios de</a> configuração.

::: moniker-end
  
2. Na página **Domínios,** selecione o domínio que deseja remover.

3. No painel direito, selecione **Remover**.

4. Siga quaisquer solicitações adicionais e selecione **Fechar**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Quanto tempo leva para um domínio ser removido?

Pode levar apenas 5 minutos para Microsoft 365 remover um domínio se não for referenciado em muitos lugares, como grupos de segurança, listas de distribuição, usuários e grupos de Microsoft 365. Se há muitas referências que usam o domínio, pode levar várias horas (um dia) para que ele seja removido.
  
Se você tem centenas ou milhares de usuários, use o PowerShell para fazer uma consulta de todos os usuários e mova-os para outro domínio. Caso contrário, é possível que alguns usuários fiquem de fora da interface e, quando você tentar remover o domínio, não conseguirá e não saberá por quê. Saiba mais em [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Para definir o domínio padrão, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Ainda precisa de ajuda?

::: moniker range="o365-worldwide"

> [!NOTE]
> Você não pode remover o domínio [".onmicrosoft.com"](../setup/domains-faq.yml) da sua conta. Quando você remover um domínio, as contas de usuário voltarão ao endereço ".onmicrosoft.com" como o SMTP/UserprincipalName primário.
  
Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../../business-video/get-help-support.md). Ajudaremos você com essa questão!
  
::: moniker-end

## <a name="related-articles"></a>Artigos relacionados

[Perguntas frequentes sobre domínios](../setup/domains-faq.yml)

[Mudar para outro plano do Microsoft 365 for business](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md)