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
description: 'Aprenda a converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por várias pessoas em vez de por apenas uma pessoa. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635469"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Converter uma caixa de correio do usuário em uma caixa de correio compartilhada

Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todo o email e calendário existentes são mantidos. Somente agora ele está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la em vez de uma pessoa. Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta em uma caixa de correio de usuário (privada).

## <a name="before-you-begin"></a>Antes de começar

**Aqui estão algumas coisas realmente importantes que você precisa saber:**

- A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ela antes de convertê-la em uma caixa de correio compartilhada. Caso contrário, você não verá a opção de converter a caixa de correio. Se você tiver removido a licença, adicione-a novamente para poder converter a caixa de correio. Depois de converter a caixa de correio em uma compartilhada, você pode remover a licença da conta do usuário.

- As caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a elas. Para manter mais dados do que isso, você precisa de uma licença atribuída a ele. Talvez seja necessário excluir um monte de emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para reduzi-la para que você possa remover a licença.

- Não exclua a conta do usuário antigo. Isso é necessário para ancorar a caixa de correio compartilhada. Se você já excluiu a conta de usuário, consulte Converter a caixa de [correio de um usuário excluído.](#convert-the-mailbox-of-a-deleted-user)

- As regras ficam intactas depois que a caixa de correio é convertida em uma caixa de correio compartilhada.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Usar o Exchange de administração para converter uma caixa de correio
 
1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.

2. Selecione **Caixas de Correio** de \> **Destinatários.**

3. Selecione a caixa de correio do usuário. Em **Converter em Caixa de Correio Compartilhada,** selecione **Converter**.

4. Se a caixa de correio for menor que 50 GB, você poderá remover a licença do usuário [e](../manage/remove-licenses-from-users.md)parar de pagar por ela. Não exclua a conta do usuário. A caixa de correio compartilhada precisa dela como âncora. Se você estiver convertendo a caixa de correio de um funcionário que está deixando sua organização, você deve tomar etapas adicionais para garantir que ele não possa mais fazer logoff. Confira [Remover um ex-funcionário do Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> Não é necessário redefinir a senha do usuário durante a conversão de caixa de correio. No entanto, se a senha não for redefinida, o nome de usuário e a senha **originais continuarão** a funcionar depois que a conversão de caixa de correio for concluída.

Para saber mais sobre caixas de correio compartilhadas, consulte Sobre caixas de correio [compartilhadas](about-shared-mailboxes.md) e [Criar uma caixa de correio compartilhada.](create-a-shared-mailbox.md)

> [!NOTE]
> Caixas de correio compartilhadas não exigem uma licença separada. No entanto, se você quiser habilitar o In-Place Archive ou colocar uma In-Place ou uma Responsabilidade de Litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plano 1 com Arquivamento do Exchange Online ou Exchange Online Plano 2 à caixa de correio.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Converter a caixa de correio de um usuário excluído

Digamos que você excluiu uma conta de usuário e agora deseja converter sua caixa de correio antiga em uma caixa de correio de compartilhamento. Veja o que você precisa fazer:

1. [Restaure a conta do usuário](../add-users/restore-user.md).

2. Certifique-se de Microsoft 365 uma licença de Microsoft 365 seja atribuída a ela.

3. Redefinir a senha do usuário.
    
4. Aguarde 20 a 30 minutos para que sua caixa de correio seja recriada.
    
5. Agora, siga as instruções nesta página para converter sua caixa de correio em uma caixa de correio compartilhada.
    
6. Após isso, você pode remover a licença da caixa de correio do usuário. Não exclua a caixa de correio antiga do usuário. A caixa de correio compartilhada precisa dela como âncora.
    
7. Adicione membros à caixa de correio compartilhada.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Converter uma caixa de correio compartilhada de volta na caixa de correio (privada) de um usuário

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
   
2. Selecione **Destinatários** \> **Compartilhados**.

3. Selecione a caixa de correio compartilhada. Em **Converter em Caixa de Correio Regular,** selecione **Converter**.

4. Volte para o centro de administração. Em **Usuários**, escolha a conta de usuário associada à caixa de correio compartilhada antiga. Atribua uma licença à conta e redefinir a senha.

   Levará alguns minutos para a caixa de correio ser configurada, mas, depois disso, a pessoa que vai usar essa conta está pronta para ir. Quando eles entrarem, verão os itens de email e calendário que costumavam estar na caixa de correio compartilhada.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Converter a caixa de correio de um usuário em um ambiente híbrido

Para obter mais informações sobre como converter uma caixa de correio de usuário em uma caixa de correio compartilhada em um ambiente Exchange híbrido, consulte:

 - [Cmdlets para criar ou modificar uma caixa de correio compartilhada remota em um ambiente Exchange local](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [As caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuário após a sincronização de diretórios ser Exchange implantação híbrida](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Se você for membro do grupo de função Gerenciamento da Organização ou Gerenciamento de Destinatários, poderá usar o Shell de Gerenciamento Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local. Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-content"></a>Conteúdo relacionado

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md) (artigo)\
[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md) (artigo)\
[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md) (artigo)\
[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md) (artigo)\
[Resolver problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md) (artigo)