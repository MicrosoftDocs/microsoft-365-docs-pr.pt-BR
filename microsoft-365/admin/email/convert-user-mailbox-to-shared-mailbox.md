---
title: Converter uma caixa de correio do usuário em uma caixa de correio compartilhada
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Saiba como converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por vários usuários. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737960"
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

2. Selecionar  \> **caixas de correio** de destinatários.

3. Selecione a caixa de correio do usuário. Em **converter em caixa de correio compartilhada**, selecione **converter**.

4. Se a caixa de correio for menor do que 50 GB, você poderá remover a [licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela. Não exclua a conta do usuário. A caixa de correio compartilhada precisa dela como uma âncora. Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon. Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> Não é necessário redefinir a senha do usuário durante a conversão da caixa de correio. No entanto, se a senha não for redefinida, **o nome de usuário e a senha originais continuarão funcionando** após a conclusão da conversão da caixa de correio.

Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).

> [!NOTE]
> Caixas de correio compartilhadas não exigem uma licença separada. No entanto, se você deseja habilitar o arquivo de In-Place ou colocar uma In-Place isenção ou uma retenção de litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plan 1 com o arquivamento do Exchange Online ou do Exchange Online Plan 2 à caixa de correio.


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

Para obter mais informações sobre como converter uma caixa de correio de usuário para uma caixa de correio compartilhada em um ambiente híbrido do Exchange, consulte:

 - [Cmdlets para criar ou modificar uma caixa de correio compartilhada remota em um ambiente do Exchange local](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio do usuário após a execução da sincronização de diretório em uma implantação híbrida do Exchange](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Se você é membro do grupo de funções Gerenciamento da organização ou gerenciamento de destinatários, você pode usar o Shell de gerenciamento do Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local. Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)
