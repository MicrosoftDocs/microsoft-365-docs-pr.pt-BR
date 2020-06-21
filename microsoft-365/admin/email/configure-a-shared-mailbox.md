---
title: Definir configurações de caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Depois de criar uma caixa de correio compartilhada, convém definir algumas configurações para seus usuários, como encaminhamento de email e respostas automáticas. Posteriormente, talvez você queira alterar outras configurações, como os membros ou o nome da caixa de correio.
ms.openlocfilehash: 3bde856f4db80192f5ed058a18c7942aa6a724b2
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739207"
---
# <a name="configure-shared-mailbox-settings"></a>Definir configurações de caixa de correio compartilhada

Depois de [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md), convém definir algumas configurações para os usuários de caixa de correio, como encaminhamento de email e respostas automáticas. Posteriormente, talvez você queira alterar outras configurações, como o nome da caixa de correio, membros ou permissões de membro. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Alterar o nome ou o alias de email de uma caixa de correio compartilhada ou alterar o endereço de email principal

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Editar** ao lado de **nome, email, aliases de email**.

3. Insira um novo nome ou adicione outro alias. Se você deseja alterar o endereço de email principal, sua caixa de correio deve ter mais de um alias de email.

4. Selecione **Salvar**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Encaminhar emails enviados para uma caixa de correio compartilhada

Você não precisa atribuir uma licença à caixa de correio compartilhada para encaminhar emails enviados a ela. Você pode encaminhar as mensagens para qualquer endereço de email ou lista de distribuição válida.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione edição de **encaminhamento de email** \> **Edit**.
    
3. Defina **a opção**ativar e digite um endereço de email para encaminhar as mensagens. Pode ser qualquer endereço de email válido. Para encaminhar para vários endereços, você precisa [criar um grupo de distribuição](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) para os endereços e, em seguida, inserir o nome do grupo nessa caixa.
    
4. Selecione **Salvar**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Enviar respostas automáticas de uma caixa de correio compartilhada

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione Editar **respostas automáticas** \> **Edit**.
    
3. Defina a opção Ativar **e escolha**se deseja enviar a resposta para pessoas dentro da sua organização ou fora da organização.

4. Digite a resposta que deseja enviar para as pessoas da organização. Não é possível adicionar imagens, apenas texto.

5. Se você deseja *também* enviar uma resposta para pessoas de fora da sua organização, marque a caixa de seleção, quem deseja obter a resposta e digite o texto. Não é possível enviar apenas para as pessoas de fora da organização, sem enviar também para as pessoas da organização.

6. Selecione **Salvar**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Permitir que todos vejam os Emails enviados (as respostas)

By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.

Se quiser permitir que todos vejam os emails enviados, no centro de administração, edite as configurações da caixa de correio compartilhada e selecione Editar **itens enviados** \> **Edit**.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Escolha os aplicativos que uma caixa de correio compartilhada pode usar para acessar o email da Microsoft

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione Editar **aplicativos de email** \> **Edit**.

3. Defina ativar/desativar **para todos** os aplicativos que você deseja que os membros possam usar para acessar a caixa de correio compartilhada. Defina a **opção** de alternância para qualquer aplicativo que você não deseja que eles usem. 

4. Selecione **Salvar**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Colocar uma caixa de correio compartilhada em retenção de litígio

Para saber mais sobre a retenção de litígio, confira [criar uma retenção de litígio](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione Editar a **retenção de litígio** \> **Edit**.

3. Defina a opção Toggle como **ativado**. 

4. Opcionalmente, insira uma duração, nota sobre a isenção e uma URL com mais informações.  

5. Selecione **Salvar**.


## <a name="add-or-remove-members"></a>Adicionar ou remover membros

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Membros** \> **Editar**.

3. Siga um destes procedimentos:
   - Para adicionar membros, selecione **adicionar membros**, Pesquisar ou selecionar um membro a ser adicionado e, em seguida, selecione **salvar**.
   - Para remover membros, use a caixa de pesquisa para pesquisar o membro, se necessário, selecione o **X** ao lado do nome do membro e, em seguida, selecione **salvar**. 

4. Selecione **salvar** novamente.

## <a name="add-or-remove-permissions-of-members"></a>Adicionar ou remover permissões de membros

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Membros** \> **Personalizar permissões**.

3. Selecione **Editar** ao lado da permissão que você deseja alterar para um membro. 

4. Siga um destes procedimentos:
   - Para conceder essa permissão a um membro adicional, selecione **adicionar permissões**, Pesquisar ou selecionar um membro a ser adicionado e, em seguida, selecione **salvar**.
   - Para remover a permissão de um membro, use a caixa de pesquisa para pesquisar o membro, se necessário, selecione o **X** ao lado do nome do membro e, em seguida, selecione **salvar**. 

4. Selecione **salvar** novamente.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Mostrar ou ocultar uma caixa de correio compartilhada na lista de endereços global

Se você optar por não mostrar a caixa de correio compartilhada na lista de endereços global, a caixa de correio não aparecerá na lista de endereços da sua organização, mas ainda receberá emails enviados para ele. 

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Mostrar na edição da lista de endereços global** \> **Edit**.

3. Define a opção Ativar **ou** **desativar**. 

4. Selecione **Salvar**.

> [!NOTE]
> Ocultar uma caixa de correio compartilhada da lista de endereços impossibilitará que novos membros da caixa de correio compartilhada adicionem a caixa de correio oculta ao seu perfil do Outlook até que a caixa de correio compartilhada seja exibida novamente na lista de endereços. 

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)
