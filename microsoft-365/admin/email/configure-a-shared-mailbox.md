---
title: Configurar caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: Depois de criar uma caixa de correio compartilhada, você vai querer configurar algumas configurações para seus usuários, como encaminhamento de email e respostas automáticas. Mais tarde, talvez você queira alterar outras configurações, como o nome da caixa de correio ou os membros.
ms.openlocfilehash: 2d0998ba2bdc95a9f78f59527bd9bd6fa98b4c45
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915909"
---
# <a name="configure-shared-mailbox-settings"></a>Configurar caixa de correio compartilhada

Depois de criar [uma caixa](create-a-shared-mailbox.md)de correio compartilhada, você vai querer configurar algumas configurações para os usuários da caixa de correio, como encaminhamento de email e respostas automáticas. Mais tarde, talvez você queira alterar outras configurações, como o nome da caixa de correio, membros ou permissões de membro. 

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

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Editar** ao lado de **Nome, Email, Aliases de Email.**

3. Insira um novo nome ou adicione outro alias. Se você quiser alterar o endereço de email principal, sua caixa de correio deve ter mais de um alias de email.

4. Selecione **Salvar**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Encaminhar emails enviados para uma caixa de correio compartilhada

Não é necessário atribuir uma licença à caixa de correio compartilhada para encaminhar emails enviados a ela. Você pode encaminhar as mensagens para qualquer endereço de email válido ou lista de distribuição.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Editar encaminhamento de** \> **email.**
    
3. De definir a alternância **como On** e insira um endereço de email para o qual encaminhar as mensagens. Pode ser qualquer endereço de email válido. Para encaminhar para vários endereços, você precisa [criar](/office365/admin/setup/create-distribution-lists) um grupo de distribuição para os endereços e, em seguida, inserir o nome do grupo nesta caixa.
    
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

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Respostas automáticas** \> **Editar**.
    
3. De definir a alternância como On e escolha se a resposta deve ser enviada para pessoas dentro da sua organização ou fora da sua organização.

4. Digite a resposta que deseja enviar para as pessoas da organização. Não é possível adicionar imagens, apenas texto.

5. Se você quiser também *enviar* uma resposta para pessoas de fora da sua organização, selecione a caixa de seleção, quem você deseja obter a resposta e digite o texto. Não é possível enviar apenas para as pessoas de fora da organização, sem enviar também para as pessoas da organização.

6. Selecione **Salvar**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Permitir que todos vejam os Emails enviados (as respostas)

Por padrão, as mensagens enviadas da caixa de correio compartilhada não são salvas na sua pasta Itens enviados. Em vez disso, elas são salvas na pasta Itens enviados da pessoa que enviou a mensagem.

Se você quiser permitir que todos vejam o email enviado, no centro de administração, edite as configurações de caixa de correio compartilhadas e selecione **Itens enviados** \> **Editar**.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Escolha os aplicativos que uma caixa de correio compartilhada pode usar para acessar email da Microsoft

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Aplicativos de email** \> **Editar**.

3. De definir a alternância como **On** para todos os aplicativos que você deseja que os membros sejam capazes de usar para acessar a caixa de correio compartilhada. De definir a alternância **como Off** para todos os aplicativos que você não deseja que eles usem. 

4. Selecione **Salvar**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Colocar uma caixa de correio compartilhada em espera de litígio

Para saber mais sobre a ressarção de litígio, consulte [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Contencioso de espera** \> **Editar**.

3. De definir a alternância como **On**. 

4. Opcionalmente, insira uma duração, uma observação s sobre a espera e uma URL com mais informações.  

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

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Membros** \> **Editar**.

3. Siga um destes procedimentos:
   - Para adicionar membros, selecione **Adicionar membros,** procure ou selecione um membro para adicionar e selecione **Salvar**.
   - Para remover membros, use a caixa Pesquisar para pesquisar o membro, se necessário, selecione **o X** ao lado do nome do membro e selecione **Salvar**. 

4. Selecione **Salvar** novamente.

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

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Membros** \> **Personalizar permissões**.

3. Selecione **Editar** ao lado da permissão que você deseja alterar para um membro. 

4. Siga um destes procedimentos:
   - Para dar essa permissão a um membro adicional, selecione **Adicionar** permissões, procure ou selecione um membro a adicionar e selecione **Salvar**.
   - Para remover a permissão de um membro, use a caixa Pesquisar para pesquisar o membro, se necessário, selecione **o X** ao lado do nome do membro e selecione **Salvar**. 

4. Selecione **Salvar** novamente.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Mostrar ou ocultar uma caixa de correio compartilhada na lista de endereços global

Se você optar por não mostrar a caixa de correio compartilhada na lista de endereços global, a caixa de correio não aparecerá na lista de endereços da sua organização, mas ainda receberá emails enviados a ela. 

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**. 

::: moniker-end

2. Selecione a caixa de correio compartilhada que você deseja editar e selecione **Mostrar na lista de endereços global** \> **Editar**.

3. De definir a alternância **como On**  ou **Off**. 

4. Selecione **Salvar**.

> [!NOTE]
> Ocultar uma caixa de correio compartilhada da lista de endereços fará com que os novos membros da caixa de correio compartilhada adicionem a caixa de correio oculta ao perfil do Outlook até que a caixa de correio compartilhada seja novamente mostrada na lista de endereços. 

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)