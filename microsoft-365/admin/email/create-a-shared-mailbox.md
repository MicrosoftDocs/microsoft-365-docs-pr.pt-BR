---
title: Criar uma caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Crie uma caixa de correio compartilhada para permitir que vários usuários da sua empresa compartilhem a responsabilidade de ler e responder a emails enviados para um endereço.
ms.openlocfilehash: 3ffe24cc263c6f58899b3c293793aa231132e411
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780260"
---
# <a name="create-a-shared-mailbox"></a>Criar uma caixa de correio compartilhada 

> [!NOTE]
> Se a sua organização usa um ambiente híbrido do Exchange, você deverá usar o centro de administração do Exchange (EAC) no local para criar e gerenciar caixas de correio compartilhadas. Ver [Criar caixas de correio compartilhadas no centro de administração do Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> Se você não tiver certeza se deve criar uma caixa de correio compartilhada ou um grupo do Microsoft 365 para o Outlook, consulte [Comparar grupos](../create-groups/compare-groups.md) para orientação. Observe que, no momento, não é possível migrar uma caixa de correio compartilhada para um grupo do Microsoft 365. Se isso é algo que você deseja, informe-nos [votando aqui](https://go.microsoft.com/fwlink/?linkid=871518).

É muito fácil criar caixas de correio compartilhadas para que um grupo de pessoas possa monitorar e enviar emails de endereços de email comuns, como info@contoso.com. Quando um membro do grupo responde a uma mensagem enviada para a caixa de correio compartilhada, o email é exibido como sendo da caixa de correio compartilhada, e não do usuário individual.

As caixas de correio compartilhadas incluem um calendário compartilhado. Várias empresas de pequeno porte preferem usar os calendários compartilhados como um local em que todos possam inserir compromissos. Por exemplo, se você tem três usuários que fazem atendimento presencial a clientes, todos eles podem usar o calendário compartilhado para inserir os respectivos compromissos. Essa é uma maneira fácil de manter todos informados.

Antes de criar uma caixa de correio compartilhada, não deixe de ler [Sobre caixas de correio compartilhadas](about-shared-mailboxes.md) para mais informações.

## <a name="create-a-shared-mailbox-and-add-members"></a>Criar uma caixa de correio compartilhada e adicionar membros
  
1. Entre com uma conta de administrador global ou conta de administrador do Exchange. Caso receba a mensagem "**Você não possui permissão para acessar esta página ou realizar esta ação**", então você não é um administrador. 

::: moniker range="o365-worldwide"

2. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end

::: moniker range="o365-germany"

2. No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=848041), acesse a página **Grupos**\>**Caixas de correio compartilhadas**.

::: moniker-end

::: moniker range="o365-21vianet"

2. No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=850627), acesse a página **Grupos**\>**Caixas de correio compartilhadas**.

::: moniker-end
    
3. Na página **Caixas de correio compartilhadas**, selecione **+ Adicionar uma caixa de correio**. Digite um nome para a caixa de correio compartilhada. Em seguida, o assistente escolhe o endereço de email, mas você pode editá-lo.
    
    ![Nomeie sua caixa de correio compartilhada.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Selecione **Adicionar**. Pode levar alguns minutos até que você possa adicionar membros.

5. Em **Próximas etapas**, selecione **Adicionar membros a esta caixa de correio**. Os membros são as pessoas que poderão visualizar o email de entrada nesta caixa de correio compartilhada e as respostas enviadas.

   ![Selecionar Adicionar Membros](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Selecione o botão **+Adicionar membros**. Marque a caixa de seleção ao lado da pessoa à qual pretende permitir o uso da caixa de correio compartilhada e clique em **Salvar**.

   ![Atribuir membros à caixa de correio compartilhada](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Selecione **Fechar**.

Você tem uma caixa de correio compartilhada e inclui um calendário compartilhado. Agora vá para a próxima etapa: bloqueie a entrada na conta da caixa de correio compartilhada.

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Bloquear entrada para a conta de caixa de correio compartilhada

Toda caixa de correio compartilhada tem uma conta de usuário correspondente. Observe como você não foi solicitado a fornecer uma senha ao criar a caixa de correio compartilhada? A conta tem uma senha, mas é gerada pelo sistema (desconhecido). Você não deve usar a conta para fazer logon na caixa de correio compartilhada.

Mas e se um administrador simplesmente redefinir a senha da conta de usuário da caixa de correio compartilhada? Ou se um invasor obtiver acesso às credenciais da conta de caixa de correio compartilhada? Isso permite que a conta de usuário faça logon na caixa de correio compartilhada e envie emails. Para evitar isso, é necessário bloquear a entrada para a conta que está associada à caixa de correio compartilhada.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na lista de contas de usuários, localize a conta da caixa de correio compartilhada (por exemplo, altere o filtro para **Usuários não licenciados**).

3. Selecione o usuário para abrir o painel propriedades e, em seguida, selecione o ícone **Bloquear este usuário** ![Captura de tela do ícone Bloquear este usuário](../../media/block-user-icon.png).

   **Observação**: Se a conta já estiver bloqueada, a mensagem **Entrada bloqueada** aparecerá na parte superior e o ícone exibirá **Desbloquear este usuário**.

4. No painel **Bloquear este usuário?**, selecione **Bloquear a entrada do usuário** e, em seguida, selecione **Salvar alterações**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Na lista de contas de usuários, localize a conta da caixa de correio compartilhada (por exemplo, altere o modo de exibição para **Usuários não licenciados**) e selecione a conta.

3. No submenu propriedades, selecione **Bloquear entrada**.

    **Observação:** Se a conta já estiver bloqueada, o botão indicará **Desbloquear entrada**.

4. No submenu **Editar o status de entrada**, verifique se a opção Bloquear a entrada do usuário está marcada, selecione **Salvar** e, em seguida, **Fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Na lista de contas de usuários, localize a conta da caixa de correio compartilhada (por exemplo, altere o modo de exibição para **Usuários não licenciados**) e selecione a conta.

3. No submenu propriedades, selecione **Bloquear entrada**.

    **Observação:** Se a conta já estiver bloqueada, o botão indicará **Desbloquear entrada**.

4. No submenu **Editar o status de entrada**, verifique se a opção Bloquear a entrada do usuário está marcada, selecione **Salvar** e, em seguida, **Fechar**.
::: moniker-end

Para obter instruções sobre como bloquear a entrada de contas usando o Azure AD PowerShell (incluindo várias contas ao mesmo tempo), confira [Bloquear contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).

## <a name="add-the-shared-mailbox-to-outlook"></a>Adicionar a caixa de correio compartilhada ao Outlook

Se habilitar o mapeamento automático em sua empresa (por padrão, a maioria das pessoas faz isso), a caixa de correio compartilhada será exibida automaticamente no aplicativo Outlook dos usuários, depois que eles fecharem e reiniciarem o Outlook. 

O mapeamento automático é definido na caixa de correio do usuário, não na caixa de correio compartilhada.   Isso significa que se você tentar usar o grupo de segurança para gerenciar quem tem acesso à caixa de correio compartilhada, o mapeamento automático não funcionará. Portanto, se quiser habilitar o mapeamento automático, atribua permissões. O mapeamento automático está ativado por padrão. Para saber como desativá-lo, confira [Remover o mapeamento automático de uma caixa de correio compartilhada](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Para saber mais sobre caixas de correio compartilhadas no Outlook, confira:

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Abrir e usar uma caixa de correio no Outlook</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook na Web</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Abrir uma pasta compartilhada ou caixa de correio no Outlook para Mac</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Adicionar regras para uma caixa de correio compartilhada</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Usar uma caixa de correio compartilhada no dispositivo móvel (telefone ou tablet)

Você pode acessar uma caixa de correio compartilhada em um dispositivo móvel de duas maneiras:
- Adicione a caixa de correio compartilhada no <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">aplicativo Outlook para iOS</a> ou no <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">aplicativo móvel Outlook para Android</a>. 
    
    Para obter instruções, confira <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook Mobile</a>.

- Abra seu navegador, entre e vá para o Outlook na Web. Em Outlook na Web, você poderá acessar a caixa de correio compartilhada.

    Para obter instruções, confira <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook na Web</a>.

## <a name="use-the-shared-calendar"></a>Usar o calendário compartilhado

Ao criar a caixa de correio compartilhada, você cria automaticamente um calendário compartilhado. Preferimos o calendário da caixa de correio compartilhada a um calendário do SharePoint para acompanhar os compromissos e onde as pessoas estão. Um calendário compartilhado é integrado ao Outlook e é muito mais fácil de usar do que um calendário do SharePoint.

1. No aplicativo Outlook, vá para o modo de exibição Calendário e selecione a caixa de correio compartilhada.

2. Quando você insere compromissos, todos os membros da caixa de correio compartilhada podem vê-los. 

3. Qualquer membro da caixa de correio compartilhada pode criar, exibir e gerenciar compromissos no calendário da mesma maneira que como é feito com seus compromissos pessoais. Todos os membros da caixa de correio compartilhada podem ver as alterações no calendário compartilhado.

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)





