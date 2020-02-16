---
title: Gerenciar permissões do grupo de funções de administrador no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Os administradores podem saber como atribuir ou remover permissões no centro de administração do Exchange (Eat) na proteção do Exchange Online.
ms.openlocfilehash: 01676fab3ed69120a35687d1c6939cb466b8d672
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082910"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>Gerenciar permissões do grupo de funções de administrador no EOP

No Microsoft Proteção do Exchange Online (EOP), é possível usar o Centro de administração do Exchange (EAC) para tornar um usuário membro de um grupo ou de grupos de funções a fim de atribuir a ele permissões de execução de tarefas administrativas específicas. Também é possível remover um usuário de um grupo ou grupo de funções usando o EAC.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para conclusão: 5 a 10 minutos

- Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Usuários, contatos e funções de grupo" no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>Usar o EAC para atribuir membros a grupos de funções de administração

1. No Eat, vá para **funções de administrador**de **permissões** \> , clique no grupo de funções ao qual você deseja adicionar o usuário ou usuários e, em seguida, clique](../../media/ITPro-EAC-EditIcon.gif)em **Editar** ![ícone de edição.

2. Em membros, clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.gif)de adição. A janela Selecionar Membros será exibida.

3. Procure o usuário ou usuários que você deseja adicionar ou selecione-os na lista.

4. Depois de selecionar o usuário ou usuários que você deseja adicionar, clique em **Adicionar** e clique em **OK**. A janela Selecionar Membros será fechada.

5. Você verá que o usuário foi adicionado ao painel **Membros**. Clique em **Salvar**.

   > [!NOTE]
   > Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>Usar o EAC para remover membros de grupos de funções de administração

1. No Eat, vá para **funções de administrador**de **permissões** \> , clique no grupo de funções do qual você deseja remover um usuário ou usuários e, em seguida, clique](../../media/ITPro-EAC-EditIcon.gif)em **Editar** ![ícone de edição.

2. Em membros, selecione o usuário ou usuários que você deseja remover e clique em **remover** ![Remover ícone](../../media/ITPro-EAC-RemoveIcon.gif).

3. Clique em **Salvar** para salvar a alteração no grupo e retornar à página **Funções de Administração**. Para verificar se você removeu o usuário do grupo de funções de administrador, verifique se o membro não está mais sendo exibido em Membros no painel de detalhes do grupo de funções selecionado.

   > [!NOTE]
   > Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.

## <a name="for-more-information"></a>Para obter mais informações

[Permissões de recurso no EOP](feature-permissions-in-eop.md)
