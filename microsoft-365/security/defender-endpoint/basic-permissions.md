---
title: Usar permissões básicas para acessar o Centro de Segurança do Microsoft Defender
description: Saiba como usar permissões básicas para acessar o portal do Microsoft Defender para Ponto de Extremidade.
keywords: atribuir funções de usuário, atribuir acesso de leitura e gravação, atribuir acesso somente leitura, usuário, funções de usuário, funções
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163666"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Usar permissões básicas para acessar o portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- Azure Active Directory
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Consulte as instruções abaixo para usar o gerenciamento de permissões básicas.

Você pode usar uma das seguintes soluções:
- Azure PowerShell
- Portal do Azure

Para controle granular sobre permissões, [alternar para o controle de](rbac.md)acesso baseado em função .

## <a name="assign-user-access-using-azure-powershell"></a>Atribuir acesso ao usuário usando o Azure PowerShell
Você pode atribuir usuários com um dos seguintes níveis de permissões:
- Acesso completo (Leitura e Gravação)
- Acesso somente leitura

### <a name="before-you-begin"></a>Antes de começar

- Instale o Azure PowerShell. Para obter mais informações, consulte [Como instalar e configurar o Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).<br>

    > [!NOTE]
    > Você precisa executar os cmdlets do PowerShell em uma linha de comando elevada.

- Conecte-se ao Azure Active Directory. Para obter mais informações, consulte [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).

**Acesso total** <br>
Os usuários com acesso total podem fazer logon, exibir todas as informações do sistema e resolver alertas, enviar arquivos para análise profunda e baixar o pacote de integração.
A atribuição de direitos de acesso total requer a adição dos usuários às funções internas "Administrador de Segurança" ou "Administrador Global" do AAD.

**Acesso somente leitura** <br>
Os usuários com acesso somente leitura podem fazer logoff, exibir todos os alertas e informações relacionadas.
Eles não poderão alterar estados de alerta, enviar arquivos para análise profunda ou executar operações de alteração de estado.
A atribuição de direitos de acesso somente leitura requer a adição dos usuários à função interna "Leitor de Segurança" do Azure AD.

Use as etapas a seguir para atribuir funções de segurança:

- Para **acesso de leitura e** gravação, atribua usuários à função de administrador de segurança usando o seguinte comando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Para **acesso somente leitura,** atribua usuários à função de leitor de segurança usando o seguinte comando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Para obter mais informações, consulte Adicionar ou remover membros do grupo [usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Atribuir acesso ao usuário usando o portal do Azure

Para obter mais informações, [consulte Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="related-topic"></a>Tópicos relacionados

- [Gerenciar o acesso ao portal usando o RBAC](rbac.md)
