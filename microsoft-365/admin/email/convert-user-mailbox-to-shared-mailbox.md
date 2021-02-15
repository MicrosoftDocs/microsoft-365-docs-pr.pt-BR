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
description: 'Aprenda a converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por vários usuários. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737960"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Converter uma caixa de correio do usuário em uma caixa de correio compartilhada

Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todo o email e o calendário existentes são mantidos. Somente agora está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la em vez de uma pessoa. Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta para uma caixa de correio de usuário (privada).

**Aqui estão algumas coisas muito importantes que você precisa saber:**

- A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ela antes de convertê-la em uma caixa de correio compartilhada. Caso contrário, você não verá a opção de converter a caixa de correio. Se você removeu a licença, adicione-a novamente para poder converter a caixa de correio. Depois de converter a caixa de correio em uma compartilhada, você pode remover a licença da conta do usuário.

- As caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a elas. Para manter mais dados do que isso, você precisa de uma licença atribuída a eles. Talvez seja necessário excluir vários emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para reduzi-la para que você possa remover a licença.

- Não exclua a conta do usuário antigo. Isso é necessário para ancorar a caixa de correio compartilhada. Se você já excluiu a conta de usuário, confira [Converter a caixa de correio de um usuário excluído.](#convert-the-mailbox-of-a-deleted-user)

- As regras são intactas depois que a caixa de correio é convertida em uma caixa de correio compartilhada.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Usar o Centro de administração do Exchange para converter uma caixa de correio
 
1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.

2. Selecione **Caixas de Correio de** \> **Destinatários.**

3. Selecione a caixa de correio do usuário. Em **Converter em Caixa de Correio Compartilhada,** selecione **Converter**.

4. Se a caixa de correio for menor que 50 GB, você poderá remover a licença do usuário [e](../manage/remove-licenses-from-users.md)parar de pagar por ela. Não exclua a conta do usuário. A caixa de correio compartilhada precisa dela como uma âncora. Se você estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve seguir etapas adicionais para garantir que ele não possa mais fazer logoff. Confira Remover [um ex-funcionário do Microsoft 365.](../add-users/remove-former-employee.md)
    
> [!NOTE]
> Não é necessário redefinir a senha do usuário durante a conversão de caixa de correio. No entanto, se a senha não for redefinida, o nome de usuário e a senha originais continuarão **a funcionar depois** que a conversão de caixa de correio for concluída.

Para saber mais sobre caixas de correio compartilhadas, confira Sobre caixas de correio compartilhadas [e](about-shared-mailboxes.md) crie uma caixa de [correio compartilhada.](create-a-shared-mailbox.md)

> [!NOTE]
> Caixas de correio compartilhadas não exigem uma licença separada. No entanto, se você quiser habilitar o Arquivamento do In-Place ou colocar uma licença de In-Place Hold ou litígio em uma caixa de correio compartilhada, deverá atribuir uma licença do Exchange Online Plano 1 com Arquivamento do Exchange Online ou Plano 2 do Exchange Online à caixa de correio.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Converter a caixa de correio de um usuário excluído

Digamos que você excluiu uma conta de usuário e agora deseja converter sua caixa de correio antiga em uma caixa de correio de compartilhamento. Aqui está o que você precisa fazer:

1. [Restaure a conta do usuário.](../add-users/restore-user.md)

2. Certifique-se de que uma licença do Microsoft 365 está atribuída a ela.

3. Redefinir a senha do usuário.
    
4. Aguarde de 20 a 30 minutos para que a caixa de correio seja recriada.
    
5. Agora, siga as instruções nesta página para converter sua caixa de correio em uma caixa de correio compartilhada.
    
6. Depois disso, você pode remover a licença da caixa de correio do usuário. Não exclua a caixa de correio antiga do usuário. A caixa de correio compartilhada precisa dela como uma âncora.
    
7. Adicionar membros à caixa de correio compartilhada.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Converter uma caixa de correio compartilhada em uma caixa de correio (privada) de um usuário

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
   
2. Selecione **Destinatários** \> **Compartilhados.**

3. Selecione a caixa de correio compartilhada. Em **Converter em Caixa de Correio Regular,** selecione **Converter**.

4. Volte para o centro de administração. Em **Usuários,** escolha a conta de usuário associada à caixa de correio compartilhada antiga. Atribua uma licença à conta e redefinir a senha.

   A configuração da caixa de correio levará alguns minutos, mas depois disso, a pessoa que usará essa conta estará pronta para começar. Ao entrar, eles verão os itens de email e calendário que estavam na caixa de correio compartilhada.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Converter a caixa de correio de um usuário em um ambiente híbrido

Para obter mais informações sobre como converter uma caixa de correio de usuário em uma caixa de correio compartilhada em um ambiente híbrido do Exchange, consulte:

 - [Cmdlets para criar ou modificar uma caixa de correio compartilhada remota em um ambiente local do Exchange](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuário após a sincronização de diretório ser executado em uma implantação híbrida do Exchange](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Se você for membro do grupo de funções Gerenciamento da Organização ou Gerenciamento de Destinatários, poderá usar o Shell de Gerenciamento do Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada local. Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)
