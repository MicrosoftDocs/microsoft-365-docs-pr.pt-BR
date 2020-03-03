---
title: Remover um domínio do Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Saiba como remover um domínio antigo do Office 365 e mover usuários e grupos para outro domínio.
ms.openlocfilehash: c012d7a8484026d04bbe216ff28715e9df0de15c
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362206"
---
# <a name="remove-a-domain-from-office-365"></a>Remover um domínio do Office 365

Colaboradores: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)
  
 **[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Você está removendo seu domínio porque deseja adicioná-lo a um plano de assinatura diferente do Office 365 ou deseja apenas cancelar a assinatura? É possível [alterar o plano ou a assinatura](../../commerce/subscriptions/switch-to-a-different-plan.md) ou [cancelar a assinatura](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Etapa 1: mover usuários para outro domínio

#### <a name="move-users"></a>Mover usuários

::: moniker range="o365-worldwide"

> [!NOTE]
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>.

2. Selecione usuários **ativos**do **usuário** > .

3. Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.

4. Selecione **mais opções** (**...**), na parte superior da página, e, em seguida, escolha **alterar domínios**.

5. No painel **alterar domínios** , selecione um domínio diferente.

Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

::: moniker-end

::: moniker range="o365-germany"

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>.  

2. Selecione usuários **ativos**do **usuário** > .

3. Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.

4. Na parte superior da página, escolha **mais** > **domínios de edição**.

5. No painel **Editar domínios** , selecione um domínio diferente.
  
Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.  

2. Selecione usuários **ativos**do **usuário** > .

3. Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.

4. Na parte superior da página, escolha **mais** > **domínios de edição**.

5. No painel **Editar domínios** , selecione um domínio diferente.
  
Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.

::: moniker-end

#### <a name="move-yourself"></a>Mover-se

::: moniker range="o365-worldwide"

> [!NOTE]
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.

2. Vá para usuários **ativos**do **usuário** \> e selecione sua conta na lista.

3. Na guia **conta** , selecione **gerenciar nome de usuário**e, em seguida, escolha um domínio diferente.
  
4. Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.

5. Entre com o novo domínio e a mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Vá para **** \> **usuários ativos**do usuário e selecione seu nome na lista.

2. Na seção **nome de usuário/email** , selecione **Editar**e, em seguida, escolha um domínio diferente.

3. Selecione **definir como fechamento de** > **salvamento** > **** principal.
  
4. Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.

5. Entre com o novo domínio e a mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para **** \> **usuários ativos**do usuário e selecione seu nome na lista.

2. Na seção **nome de usuário/email** , selecione **Editar**e, em seguida, escolha um domínio diferente.

3. Selecione **definir como fechamento de** > **salvamento** > **** principal.
  
4. Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.

5. Entre com o novo domínio e a mesma senha.

Você também pode usar o PowerShell para mover os usuários para outro domínio. Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais. Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Etapa 2: mover grupos para outro domínio

::: moniker range="o365-worldwide"

1. No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .
  
2. Selecione o nome do grupo e, na guia **geral** , em **endereço de email, principal**, selecione **Editar**.

3. Use a lista suspensa para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

::: moniker-end

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para **a página grupos** de **grupos** > .

2. Selecione o nome do grupo e, em seguida, selecione **Editar** ao lado de **nome**.

3. Use a lista suspensa para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para **a página grupos** de **grupos** > .

2. Selecione o nome do grupo e, em seguida, selecione **Editar** ao lado de **nome**.

3. Use a lista suspensa para escolher outro domínio.

4. Selecione **Salvar**, **Feche**. Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Etapa 3: remover o domínio antigo

::: moniker range="o365-worldwide"

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .

::: moniker-end
  
2. Na página **domínios** , selecione o domínio que você deseja remover.

3. No painel direito, selecione **remover**.

4. Siga os avisos adicionais e selecione **fechar**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Quanto tempo leva para um domínio ser removido?

Pode levar apenas 5 minutos para que o Office 365 remova um domínio se ele não for referenciado em muitos lugares, como grupos de segurança, listas de distribuição, usuários e grupos do Office 365. Se há muitas referências que usam o domínio, pode levar várias horas (um dia) para que ele seja removido.
  
Se você tem centenas ou milhares de usuários, use o PowerShell para fazer uma consulta de todos os usuários e mova-os para outro domínio. Caso contrário, é possível que alguns usuários fiquem de fora da interface e, quando você tentar remover o domínio, não conseguirá e não saberá por quê. Saiba mais em [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Ainda precisa de ajuda?

::: moniker range="o365-worldwide"

> [!NOTE]
> Você não pode remover o domínio [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) da sua conta.
  
Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../contact-support-for-business-products.md). Ajudaremos você com essa questão!
  
::: moniker-end

## <a name="related-articles"></a>Artigos relacionados

[Perguntas frequentes sobre domínios](../setup/domains-faq.md)

[Obter ajuda com os domínios do Office 365](get-help-with-domains.md)

[Migrar para outro plano do Office 365 para empresas](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md)
