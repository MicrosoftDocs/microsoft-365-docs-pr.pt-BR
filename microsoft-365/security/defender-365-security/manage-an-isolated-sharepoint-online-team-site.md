---
title: Gerenciar um site de equipe do SharePoint Online isolado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Gerencie um site de equipe isolado do SharePoint Online, adicione novos usuários e grupos, remova usuários e grupos e crie uma subpasta de documentos com permissões personalizadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99b773547fa67068d75a79260af14010e456cb01
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054147"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Gerenciar um site de equipe do SharePoint Online isolado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Microsoft Defender para Office 365 Plano 1](defender-for-office-365.md)
- SharePoint Online 

 **Resumo:** Gerencie seu site de equipe isolado do SharePoint Online com esses procedimentos.

Este artigo descreve operações de gerenciamento comuns para um site de equipe isolado do SharePoint Online.

## <a name="add-a-new-user"></a>Adicionar um novo usuário

Quando alguém novo ingressar no site, você deve decidir seu nível de participação no site:

- Administração: adicionar a nova conta de usuário ao grupo de acesso de administradores de site

- Colaboração ativa: adicionar a conta de usuário ao grupo de acesso de membros do site

- Exibição: adicionar a conta de usuário ao grupo de acesso de visualizadores de site

Se você estiver gerenciando contas e grupos de usuários por meio dos Serviços de Domínio do Active Directory (AD DS), adicione os usuários apropriados aos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.

Se você estiver gerenciando contas e grupos de usuários por meio do Microsoft 365, poderá usar o Centro de administração do Microsoft 365 ou o Microsoft PowerShell:

- Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para adicionar os usuários apropriados aos grupos de acesso apropriados.

- Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) Para adicionar uma conta de usuário a um grupo de acesso com seu nome principal de usuário (UPN), use o seguinte bloco de comando do PowerShell:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para adicionar uma conta de usuário a um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Para adicionar acesso a um grupo inteiro, você deve decidir o nível de participação de todos os membros do grupo no site:

- Administração: adicionar o grupo ao grupo de acesso de administradores de site

- Colaboração ativa: adicionar o grupo ao grupo de acesso de membros do site

- Exibição: adicionar o grupo ao grupo de acesso de visualizadores de site

Se você estiver gerenciando contas de usuário e grupos por meio do AD DS, adicione os grupos apropriados aos grupos apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.

Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell:

- Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para adicionar os grupos apropriados aos grupos de acesso apropriados.

- Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 Em seguida, use os seguintes comandos do PowerShell:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Remover um usuário

Quando o acesso de alguém deve ser removido do site, você os remove do grupo de acesso para o qual ele é membro no momento com base em sua participação no site:

- Administração: Remover a conta de usuário do grupo de acesso de administradores de site

- Colaboração ativa: remover a conta de usuário do grupo de acesso de membros do site

- Exibição: Remover a conta de usuário do grupo de acesso de visualizadores de site

Se você estiver gerenciando contas e grupos de usuários por meio do AD DS, remova os usuários apropriados dos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.

Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell:

- Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para remover os usuários apropriados dos grupos de acesso apropriados.

- Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Para remover uma conta de usuário de um grupo de acesso com seu UPN, use o seguinte bloco de comando do PowerShell:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para remover uma conta de usuário de um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Remover um grupo

Para remover o acesso de um grupo inteiro, remova o grupo do grupo de acesso para o qual ele é membro no momento com base em sua participação no site:

- Administração: Remover o grupo do grupo de acesso de administradores de site

- Colaboração ativa: Remover o grupo do grupo de acesso de membros do site

- Exibição: Remover o grupo do grupo de acesso de visualizadores de site

Se você estiver gerenciando contas e grupos de usuários por meio do Windows Server Active Directory, remova os grupos apropriados dos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.

Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell:

- Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para remover os grupos apropriados dos grupos de acesso apropriados.

- Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Para remover um grupo de um grupo de acesso usando seus nomes de exibição, use o seguinte bloco de comando do PowerShell:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Criar uma subpasta de documentos com permissões personalizadas

Em alguns casos, um subconjunto das pessoas que trabalham no site isolado precisa de um local mais privado para colaborar. Para sites do SharePoint Online, você pode criar uma subpasta na pasta Documentos do site e atribuir permissões personalizadas. Aqueles sem permissões não verão a subpasta.

Para criar uma subpasta de documentos com permissões personalizadas, faça o seguinte:

1. Entre em uma conta que seja membro do grupo de acesso de administradores do site. Para obter ajuda, consulte [Como entrar no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Vá para o site de equipe isolado e clique em **Documentos**.

3. Navegue até a pasta na pasta documentos que conterá a subpasta com permissões personalizadas, crie a pasta e abra-a.

4. Clique em **Compartilhar**.

5. Clique **em Compartilhado com > Avançado**.

6. Clique **em Parar de herdar permissões** e clique em **OK**.

7. Clique em **Compartilhar**.

8. Clique **em Compartilhado com > Avançado**.

9. Clique **em Conceder Permissões > Compartilhado com > Avançado**.

10. Na página permissões, clique em **\<site name> Membros na lista**.

11. Na página **\<site name> Membros,** selecione a marca de seleção ao lado do grupo de acesso de membros do site, clique em **Ações,** clique em **Remover** usuários do grupo e clique em **OK**.

12. Para adicionar membros específicos a essa subpasta, clique em **Novo > Adicionar usuários**.

13. Na caixa **de diálogo** Compartilhar, digite os nomes das contas de usuário que podem colaborar em arquivos na subpasta e clique em **Compartilhar**.

14. Atualize a página da Web para ver os novos resultados.

15. Em **Grupos** na navegação à **\<site name>** esquerda, clique no grupo Visitantes e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem exibir os arquivos na subpasta (conforme necessário).

16. Em **Grupos** na navegação à **\<site name>** esquerda, clique no grupo Proprietários e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem administrar as permissões na subpasta (conforme necessário).

17. Feche a **guia Pessoas e Grupos** no navegador.

## <a name="see-also"></a>Confira também

[Sites de equipe do SharePoint Online isolados](isolated-sharepoint-online-team-sites.md)

[Configurar uma equipe com isolamento de segurança](/microsoft-365/solutions/secure-teams-security-isolation)
