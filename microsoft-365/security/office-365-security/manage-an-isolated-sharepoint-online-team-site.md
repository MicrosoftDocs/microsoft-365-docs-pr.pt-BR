---
title: Gerenciar um site de equipe do SharePoint Online isolado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Resumo: Gerencie seu site de equipe do SharePoint Online isolado com estes procedimentos.'
ms.openlocfilehash: 1b033d8c08b4b263c854213ce7b2a9fc2c0baede
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971729"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Gerenciar um site de equipe do SharePoint Online isolado

 **Resumo:** Gerencie seu site de equipe do SharePoint Online isolado com estes procedimentos.
  
Este artigo descreve as operações de gerenciamento comuns para um site de equipe do SharePoint Online isolado.
  
## <a name="add-a-new-user"></a>Adicionar um novo usuário

Quando alguém novo ingressar no site, você deverá decidir o nível de participação no site:
  
- Administração: adicionar a nova conta de usuário ao grupo de acesso de administradores de site
    
- Colaboração ativa: adicionar a conta de usuário ao grupo de acesso de membros do site
    
- Exibindo: adicionar a conta de usuário ao grupo de acesso de visualizadores de sites
    
Se você estiver gerenciando contas de usuário e grupos por meio de serviços de domínio do Active Directory (AD DS), adicione os usuários apropriados aos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com o seu Office 365 scriçõe.
  
Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o Microsoft PowerShell:
  
- Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido a função Administrador de conta de usuário ou administrador da empresa e use grupos para adicionar os usuários apropriados aos grupos de acesso apropriados.
    
- Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Para adicionar uma conta de usuário a um grupo de acesso com seu nome de usuário principal (UPN), use o seguinte bloco de comando do PowerShell:
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para adicionar uma conta de usuário a um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Para adicionar acesso a um grupo inteiro, você deve decidir o nível de participação de todos os membros do grupo no site:
  
- Administração: Adicionar o grupo ao grupo de acesso de administradores de site
    
- Colaboração ativa: Adicionar o grupo ao grupo de acesso de membros do site
    
- Exibindo: Adicionar o grupo ao grupo de acesso visualizadores de sites
    
Se você estiver gerenciando contas de usuário e grupos através do AD DS, adicione os grupos apropriados aos grupos apropriados usando seus procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com sua assinatura do Office 365.
  
Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell:
  
- Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido o administrador da conta de usuário ou a função de administrador da empresa e use grupos para adicionar os grupos apropriados aos grupos de acesso apropriados.
    
- Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Em seguida, use os seguintes comandos do PowerShell:
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Remover um usuário

Quando o acesso de alguém precisa ser removido do site, você os remove do grupo de acesso para o qual eles são membros atualmente, com base na sua participação no site:
  
- Administração: Remova a conta de usuário do grupo de acesso de administradores de site
    
- Colaboração ativa: Remova a conta de usuário do grupo de acesso de membros do site
    
- Exibição: remover a conta de usuário do grupo de acesso de visualizadores de sites
    
Se você estiver gerenciando contas de usuário e grupos por meio do AD DS, remova os usuários apropriados dos grupos de acesso apropriados usando seus procedimentos de gerenciamento de usuário e grupo do AD DS normal e aguarde a sincronização com sua assinatura do Office 365.
  
Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell:
  
- Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido a função Administrador de conta de usuário ou administrador da empresa e use grupos para remover os usuários apropriados dos grupos de acesso apropriados.
    
- Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Para remover uma conta de usuário de um grupo de acesso com seu UPN, use o seguinte bloco de comando do PowerShell:
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para remover uma conta de usuário de um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Remover um grupo

Para remover o acesso de um grupo inteiro, remova o grupo do grupo de acesso para o qual eles são membros atualmente com base em sua participação no site:
  
- Administração: remover o grupo do grupo de acesso de administradores de site
    
- Colaboração ativa: remover o grupo do grupo de acesso de membros do site
    
- Exibição: remover o grupo do grupo de acesso de visualizadores de sites
    
Se você estiver gerenciando contas de usuário e grupos por meio do Windows Server Active Directory, remova os grupos apropriados dos grupos de acesso apropriados usando seus procedimentos de gerenciamento de usuário e grupo do AD DS normal e aguarde a sincronização com o seu Office 365 scriçõe.
  
Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell:
  
- Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido a função Administrador de conta de usuário ou administrador da empresa e use grupos para remover os grupos apropriados dos grupos de acesso apropriados.
    
- Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Para remover um grupo de um grupo de acesso usando seus nomes de exibição, use o seguinte bloco de comando do PowerShell:
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Criar uma subpasta documentos com permissões personalizadas

Em alguns casos, um subconjunto das pessoas que trabalham dentro do site isolado precisa de um local mais privado para colaborar. Para sites do SharePoint Online, você pode criar uma subpasta na pasta documentos do site e atribuir permissões personalizadas. Aqueles sem permissões não verão a subpasta.
  
Para criar uma subpasta documentos com permissões personalizadas, faça o seguinte:
  
1. Entre no Office 365 com uma conta que seja membro do grupo de acesso de administradores para o site. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Vá para o site de equipe isolado e clique em **documentos**.
    
3. Navegue até a pasta na pasta documentos que conterá a subpasta com permissões personalizadas, crie a pasta e, em seguida, abra-a.
    
4. Clique em **Compartilhar**.
    
5. Clique em **compartilhado com > avançado**.
    
6. Clique em **parar de herdar permissões**e clique em **OK**.
    
7. Clique em **Compartilhar**.
    
8. Clique em **compartilhado com > avançado**.
    
9. Clique em **conceder permissões > compartilhado com > avançado**.
    
10. Na página permissões, clique em ** \<nome do site> membros da lista**.
    
11. Na página ** \<nome do site> Membros** , selecione a marca de seleção ao lado do grupo de acesso de membros do site, clique em **ações**, clique em **remover usuários do grupo**e clique em **OK**.
    
12. Para adicionar membros específicos a essa subpasta, clique em **novo > adicionar usuários**.
    
13. Na caixa de diálogo **compartilhar** , digite os nomes das contas de usuário que podem colaborar em arquivos na subpasta e, em seguida, clique em **compartilhar**.
    
14. Atualize a página da Web para ver os novos resultados.
    
15. Em **grupos** na navegação à esquerda, clique no grupo ** \<nome do site> visitantes** e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem exibir os arquivos na subpasta (conforme necessário).
    
16. Em **grupos** na navegação à esquerda, clique no grupo ** \<nome do site> proprietários** e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem administrar as permissões na subpasta (conforme necessário).
    
17. Feche a guia **pessoas e grupos** no navegador.
    
## <a name="see-also"></a>Confira também

[Sites de equipe do SharePoint Online isolados](isolated-sharepoint-online-team-sites.md)
  
[Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md)

[Implantar um site de equipe do SharePoint Online isolado](deploy-an-isolated-sharepoint-online-team-site.md)



