---
title: Converter uma caixa de correio do usuário em uma caixa de correio compartilhada
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Saiba como converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por vários usuários. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521024"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Converter uma caixa de correio do usuário em uma caixa de correio compartilhada

Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todos os emails e calendários existentes são mantidos. Agora, ela está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la, em vez de uma pessoa. Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta para uma caixa de correio de usuário (privada).

**Veja algumas coisas realmente importantes que você precisa saber:**

- A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ele antes de convertê-lo em uma caixa de correio compartilhada. Caso contrário, você não verá a opção de converter a caixa de correio. Se você tiver removido a licença, adicione-a de volta para que possa converter a caixa de correio. Após converter a caixa de correio para uma compartilhada, você pode remover a licença da conta do usuário.

- Caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a eles. Para armazenar mais dados do que isso, você precisa de uma licença atribuída a ele. Você pode precisar excluir um monte de emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para diminuí-lo para que você possa remover a licença.

- Não exclua a conta do usuário antigo. Isso é necessário para ancorar a caixa de correio compartilhada. Se você já tiver excluído a conta de usuário, consulte [converter a caixa de correio de um usuário excluído](#convert-the-mailbox-of-a-deleted-user).

- As regras ficam intactas após a conversão da caixa de correio em uma caixa de correio compartilhada.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Usar o centro de administração do Exchange para converter uma caixa de correio
 
1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.

2. Selecionar **Recipients** \> **caixas de correio**de destinatários.

3. Selecione a caixa de correio do usuário. Em **converter em caixa de correio compartilhada**, selecione **converter**.

4. Se a caixa de correio for menor do que 50 GB, você poderá remover a [licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela. Não exclua a conta do usuário. A caixa de correio compartilhada precisa dela como uma âncora. Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon. Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).
    
5. Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a>Usar o centro de administração do Microsoft 365 para converter uma caixa de correio

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione o nome do usuário cuja caixa de correio você deseja converter.

3. Redefinir a senha do usuário.

   > [!NOTE]
   > Não é necessário redefinir a senha do usuário durante a conversão da caixa de correio. No entanto, se a senha não for redefinida, **o nome de usuário e a senha originais continuarão funcionando** após a conclusão da conversão da caixa de correio.

4. Na guia **email** , em **mais ações**, selecione **converter para caixa de correio compartilhada**. 

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o usuário cuja caixa de correio você deseja converter.

3. No painel direito, expanda **configurações de email**. Ao lado de **mais configurações**, selecione **converter para caixa de correio compartilhada**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o usuário cuja caixa de correio você deseja converter.

3. No painel direito, expanda **configurações de email**. Ao lado de **mais configurações**, selecione **converter para caixa de correio compartilhada**.

::: moniker-end


Se a caixa de correio for menor do que 50 GB, você poderá [remover a licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela. Não exclua a caixa de correio antiga do usuário. A caixa de correio compartilhada precisa dela como uma âncora. Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon. Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).
    
Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).

> [!NOTE]
> Caixas de correio compartilhadas não exigem uma licença separada. No entanto, se você deseja habilitar o arquivo morto in-loco ou colocar um bloqueio in-loco ou uma retenção de litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plan 1 com o arquivamento do Exchange Online ou do Exchange Online Plan 2 à caixa de correio.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Converter a caixa de correio de um usuário excluído

Digamos que você tenha excluído uma conta de usuário e agora deseja converter sua caixa de correio antiga para uma caixa de correio de compartilhamento. Veja o que você precisa fazer:

1. [Restaure a conta do usuário](../add-users/restore-user.md).

2. Verifique se uma licença da Microsoft 365 está atribuída a ele.

3. Redefinir a senha do usuário.
    
4. Aguarde 20-30 minutos para que a caixa de correio seja recriada.
    
5. Agora siga as instruções nesta página para converter a caixa de correio em uma caixa de correio compartilhada.
    
6. Depois disso, você pode remover a licença da caixa de correio do usuário. Não exclua a caixa de correio antiga do usuário. A caixa de correio compartilhada precisa dela como uma âncora.
    
7. Adicionar membros à caixa de correio compartilhada.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Converter uma caixa de correio compartilhada de volta para a caixa de correio de um usuário (privado)

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
   
2. Selecione **destinatários** \> **compartilhados**.

3. Selecione a caixa de correio compartilhada. Em **converter em caixa de correio normal**, selecione **converter**.

4. Volte para o centro de administração. Em **usuários**, escolha a conta de usuário associada à caixa de correio compartilhada antiga. Atribua uma licença à conta e redefina a senha.

   Levará alguns minutos para que a caixa de correio seja configurada, mas depois dela, a pessoa que usará a conta está pronta para começar. Quando eles entrarem, eles verão os itens de email e calendário que usaram a caixa de correio compartilhada.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Converter a caixa de correio de um usuário em um ambiente híbrido

Se essa caixa de correio compartilhada estiver em um ambiente híbrido, **recomendamos enfaticamente** (quase exigir!) que você mova a caixa de correio do usuário de volta para o local, converta a caixa de correio do usuário em uma caixa de correio compartilhada e, em seguida, mova a caixa de correio compartilhada de volta para a nuvem. 

Veja por quê: se você converter a caixa de correio na nuvem, ela poderá ser convertida, mas o local ainda acha que a caixa de correio é a caixa de correio do usuário, porque a nova realidade não é sincronizada para o local.

Normalmente, isso não é um problema, mas há alguns cenários em que os atributos locais (que acreditam que a caixa de correio é a caixa de correio do usuário) podem substituir as novas versões de nuvem desses atributos e, como resultado, a caixa de correio pode ser convertida novamente. Isso é um problema porque as caixas de correio do usuário exigem licenças **ou são excluídas de forma reversível após 30 dias**!

Abordamos a maioria dos motivos pelos quais isso acontece, mas ele ainda pode acontecer, embora com frequência. É melhor ser seguro e mover a caixa de correio de volta para o local, convertê-la e, em seguida, mover a caixa de correio compartilhada de volta para a nuvem. Essa solução recomendada não está violando o contrato de licenciamento para ambientes híbridos porque a existência da caixa de correio de usuário local é apenas temporária. Você estaria violando sua licença se manteve a caixa de correio do usuário ou a caixa de correio compartilhada em sua organização local e não a moveu de volta para a nuvem.

> [!NOTE]
> Se você é membro do grupo de funções Gerenciamento da organização ou gerenciamento de destinatários, você pode usar o Shell de gerenciamento do Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local. Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Consulte a solução alternativa nesta solução de suporte para instâncias quando [caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuários](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).
  
## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)
