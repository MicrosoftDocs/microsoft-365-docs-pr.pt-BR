---
title: Conceder aos usuários acesso ao Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Os usuários precisam receber permissões no centro de conformidade & segurança da Microsoft 365 antes de poderem gerenciar qualquer um dos seus recursos de segurança ou conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202802"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Conceder aos usuários acesso ao Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Os usuários precisam receber permissões no centro de conformidade e segurança & antes de poderem gerenciar qualquer um dos seus recursos de segurança ou conformidade. Como um administrador global ou membro do grupo de função gerenciamento no centro de conformidade & segurança, você pode conceder essas permissões aos usuários. Os usuários só podem gerenciar os recursos de segurança ou de conformidade para os quais você conceder acesso.

Para obter mais informações sobre as diferentes permissões que você pode dar aos usuários no centro de conformidade & segurança, confira [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa ser um administrador global ou um membro do grupo de função gerenciamento no centro de conformidade & segurança, para concluir as etapas neste artigo.

- Grupos de função para o centro de conformidade & segurança podem ter nomes semelhantes aos grupos de função no Exchange Online, mas eles não são os mesmos.

- As associações do grupo de funções não são compartilhadas entre o Exchange Online e o centro de conformidade & segurança.

- Permissão de acesso delegado (DAP) parceiros com permissões de administração em nome de (AOBO) não podem acessar o centro de conformidade & segurança.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Usar o centro de conformidade de & de segurança para conceder acesso de outro usuário ao centro de conformidade & segurança

1. Abra o centro de conformidade & segurança em <https://protection.office.com> e vá até **permissões**. Para ir diretamente para a guia **permissões** , abra <https://protection.office.com/permissions> .

2. Na lista de grupos de função, escolha o grupo de função e, em seguida, clique em **Editar** ![ ícone de edição ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. Na página de propriedades do grupo de funções, em **Membros**, clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.gif) de adição e selecione o nome do usuário (ou usuários) que você deseja adicionar.

4. Depois de selecionar todos os usuários que você deseja adicionar ao grupo de funções, clique em **Adicionar \> ** e em **OK**.

5. Quando concluir, clique em **Salvar**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Usar o PowerShell do centro de conformidade & a segurança para conceder acesso a outro usuário ao centro de conformidade & segurança

1. [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Use a seguinte sintaxe:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Para problemas detalhados de sintaxe e parâmetro, consulte [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você obteve com êxito o acesso ao centro de conformidade de & de segurança, faça uma das seguintes etapas:

- No centro de conformidade & segurança, acesse **permissões** e selecione o grupo de função. No submenu de detalhes que é aberto, verifique os membros do grupo de função. 

- Em segurança & o PowerShell do centro de conformidade, substitua \<RoleGroupName\> o nome do grupo de função e execute o seguinte comando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
