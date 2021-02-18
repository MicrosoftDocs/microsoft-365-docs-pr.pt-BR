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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Os usuários precisam ter permissões no Centro de Conformidade e Segurança do Microsoft 36 & 5 para poder gerenciar qualquer um dos seus recursos de segurança ou conformidade.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289872"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Conceder aos usuários acesso ao Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Os usuários precisam ter permissões no Centro de Conformidade e Segurança & para poder gerenciar qualquer um dos seus recursos de segurança ou conformidade. Como administrador global ou membro do grupo de função OrganizationManage & ment no Centro de Conformidade e Segurança, você pode dar essas permissões aos usuários. Os usuários só podem gerenciar os recursos de segurança ou de conformidade para os quais você conceder acesso.

Para obter mais informações sobre as diferentes permissões que você pode dar aos usuários no Centro de Conformidade e Segurança &, confira Permissões no Centro de Conformidade e & [Segurança.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa ser um administrador global ou um membro do grupo de função OrganizationManage & ment no Centro de Conformidade e Segurança, para concluir as etapas deste artigo.

- Grupos de função para o Centro de Conformidade e Segurança & podem ter nomes semelhantes aos grupos de função no Exchange Online, mas eles não são os mesmos.

- As associações do grupo de funções não são compartilhadas entre o Exchange Online e o Centro de Conformidade & segurança.

- Parceiros com permissões de acesso delegado (DAP) com permissões Administrar em nome de (AOBO) não podem acessar o Centro de Conformidade e Segurança & Segurança.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Usar o Centro de Conformidade & segurança para dar a outro usuário acesso ao Centro de Conformidade & segurança

1. Abra o Centro de Conformidade & segurança <https://protection.office.com> e vá para **Permissões.** Para ir diretamente para a **guia Permissões,** abra <https://protection.office.com/permissions> .

2. Na lista de grupos de função, escolha o grupo de função e clique em **Editar** ![ ícone ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. Na página de propriedades do grupo de funções em **Membros,** clique em Adicionar Ícone e selecione o nome do usuário ![ ](../../media/ITPro-EAC-AddIcon.gif) (ou usuários) que você deseja adicionar.

4. Quando você selecionar todos os usuários que deseja adicionar ao grupo de funções, clique em **adicionar \> e,** em seguida, **OK.**

5. Quando concluir, clique em **Salvar**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Usar o & PowerShell do Centro de Conformidade e Segurança para dar a outro usuário acesso ao Centro de Conformidade & Segurança

1. [Conectar-se ao Windows PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Use a seguinte sintaxe:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Para problemas detalhados de sintaxes e de parâmetros, consulte [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você concedeu com êxito o acesso ao Centro de Conformidade & segurança, faça uma das seguintes etapas:

- No Centro de Conformidade & segurança, vá para **Permissões** e selecione o grupo de funções. No flyout de detalhes que é aberto, verifique os membros do grupo de função.

- No PowerShell & Centro de Conformidade e Segurança, substitua pelo nome do grupo de função \<RoleGroupName\> e execute o seguinte comando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
