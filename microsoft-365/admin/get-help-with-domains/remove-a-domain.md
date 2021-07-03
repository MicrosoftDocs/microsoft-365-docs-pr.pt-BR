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
description: Saiba como remover um domínio antigo do Microsoft 365 e mover usuários e grupos para outro domínio ou cancelar sua assinatura.
ms.openlocfilehash: ce75be758edf330226692395dbc6a2c332ed9069
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286244"
---
# <a name="remove-a-domain"></a>Excluir um domínio

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.

Você está removendo seu domínio porque deseja adicioná-lo a um plano de assinatura Microsoft 365 diferente? Ou você só deseja cancelar sua assinatura? Você pode [alterar seu plano ou assinatura](../../commerce/subscriptions/switch-to-a-different-plan.md) ou cancelar sua [assinatura](../../commerce/subscriptions/cancel-your-subscription.md).

### <a name="step-1-move-users-to-another-domain"></a>Etapa 1: mover usuários para outro domínio

#### <a name="move-users"></a>Mover usuários

::: moniker range="o365-worldwide"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.

::: moniker-end

2. Selecione **Usuários**  >  **Usuários ativos**.

3. Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.

4. Na parte superior da página e escolha **Alterar domínios**.

5. No painel **Alterar domínios,** selecione um domínio diferente.

Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

#### <a name="move-yourself"></a>Mover a si mesmo

::: moniker range="o365-worldwide"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Acesse o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.

::: moniker-end

2. Vá para **Usuários** \> **Usuários Ativos** e selecione sua conta na lista.

3. Na guia **Conta,** selecione **Gerenciar nome de usuário** e escolha um domínio diferente.

4. Na parte superior, selecione o nome da sua conta e selecione **Sair**.

5. Entre com o novo domínio e sua mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

### <a name="step-2-move-groups-to-another-domain"></a>Etapa 2: Mover grupos para outro domínio

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a>

::: moniker-end
::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Grupos** > **grupos.**

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Grupos** > **grupos.**

::: moniker-end

2. Selecione o nome do grupo e, em seguida, na guia **Geral** em **Endereço de email, Principal**, selecione **Editar**.

3. Use a lista lista listada para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

### <a name="step-3-remove-the-old-domain"></a>Etapa 3: Remover o domínio antigo

::: moniker range="o365-worldwide"

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios de</a> Instalação.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios de</a> Instalação.

::: moniker-end

2. Na página **Domínios,** selecione o domínio que você deseja remover.

3. No painel direito, selecione **Remover**.

4. Siga quaisquer prompts adicionais e selecione **Fechar**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Quanto tempo leva para um domínio ser removido?

Pode levar apenas cinco minutos para Microsoft 365 remover um domínio se ele não for referenciado em muitos locais, como grupos de segurança, listas de distribuição, usuários e grupos Microsoft 365. Se há muitas referências que usam o domínio, pode levar várias horas (um dia) para que ele seja removido.

Se você tem centenas ou milhares de usuários, use o PowerShell para fazer uma consulta de todos os usuários e mova-os para outro domínio. Caso contrário, é possível que alguns usuários fiquem de fora da interface e, quando você tentar remover o domínio, não conseguirá e não saberá por quê. Saiba mais em [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Para definir o domínio padrão, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>Ainda precisa de ajuda?

::: moniker range="o365-worldwide"

> [!NOTE]
> Você não pode remover o domínio [".onmicrosoft.com"](../setup/domains-faq.yml) da sua conta. Quando você remover um domínio, as contas de usuário retornarão para o endereço ".onmicrosoft.com" como o SMTP principal/UserprincipalName.

Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../../business-video/get-help-support.md). Ajudaremos você com essa questão!

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> Não é possível remover o [domínio ".onmicrosoft.de"](../setup/domains-faq.yml) de sua conta. Quando você remover um domínio, as contas de usuário serão revertidas para o endereço ".onmicrosoft.de" como o SMTP/UserprincipalName primário.

Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true). Ajudaremos você com essa questão!

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> Não é possível remover o [domínio ".partner.onmschina.cn"](../setup/domains-faq.yml) de sua conta. Quando você remover um domínio, as contas de usuário retornarão para o endereço ".partner.onmschina.cn" como o SMTP principal/UserprincipalName.

Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true). Ajudaremos você com essa questão!

::: moniker-end

## <a name="related-content"></a>Conteúdo relacionado

[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)

[Alternar para um plano Microsoft 365 para empresas](../../commerce/subscriptions/switch-to-a-different-plan.md) (artigo)

[Cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md) (artigo)
