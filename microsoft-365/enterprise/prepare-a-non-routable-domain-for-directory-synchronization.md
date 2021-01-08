---
title: Preparar um domínio não roteável para sincronização de diretórios
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Saiba o que fazer se você tiver um domínio não-rouável associado às suas contas de usuário locais antes de sincronisá-las com seu locatário do Microsoft 365.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780327"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Preparar um domínio não roteável para sincronização de diretórios

Ao sincronizar seu diretório local com o Microsoft 365, você precisa ter um domínio verificado no Azure Active Directory (Azure AD). Somente os NOMES DE USUÁRIO (UPNs) associados ao domínio local dos Serviços de Domínio do Active Directory (AD DS) são sincronizados. No entanto, qualquer UPN que contenha um domínio não-rouável, como ".local" (exemplo: billa@contoso.local), será sincronizado com um domínio .onmicrosoft.com (exemplo: billa@contoso.onmicrosoft.com). 

Se você usa atualmente um domínio ".local" para suas contas de usuário no AD DS, é recomendável alterá-los para usar um domínio verificado, como o billa@contoso.com, para sincronizar corretamente com seu domínio do Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>E se eu tiver apenas um domínio local ".local"?

Você usa o Azure AD Connect para sincronizar seu AD DS com o locatário do Azure AD do locatário do Microsoft 365. Para obter mais informações, [consulte Integrando suas identidades locais com o Azure AD.](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)
  
O Azure AD Connect sincroniza o UPN e a senha dos usuários para que eles possam entrar com as mesmas credenciais que usam no local. No entanto, o Azure AD Connect sincroniza apenas os usuários com domínios verificados pelo Microsoft 365. Isso significa que o domínio também é verificado pelo Azure AD porque as identidades do Microsoft 365 são gerenciadas pelo Azure AD. Em outras palavras, o domínio deve ser um domínio válido da Internet (como.com, .org, .net, .us). Se o AD DS interno usa apenas um domínio não-rouável (por exemplo, ".local"), isso possivelmente não pode corresponder ao domínio verificado que você tem para seu locatário do Microsoft 365. Você pode corrigir esse problema alterando seu domínio principal no AD DS local ou adicionando um ou mais sufixos UPN.
  
### <a name="change-your-primary-domain"></a>Alterar seu domínio principal

Altere seu domínio principal para um domínio que você verificou no Microsoft 365, por exemplo, contoso.com. Todos os usuários que têm o domínio contoso.local são atualizados para contoso.com. No entanto, esse é um processo muito envolvido, e uma solução mais fácil é descrita na seção a seguir.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Adicionar sufixos UPN e atualizar seus usuários para eles

Você pode resolver o problema ".local" registrando novos sufixos ou sufixos UPN no AD DS para corresponder ao domínio (ou domínios) verificado no Microsoft 365. Depois de registrar o novo sufixo, atualize os UPNs dos usuários para substituir ".local" pelo novo nome de domínio, por exemplo, para que uma conta de usuário se pareça com billa@contoso.com.
  
Depois de atualizar os UPNs para usar o domínio verificado, você estará pronto para sincronizar seu AD DS local com o Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Etapa 1: Adicionar o novo sufixo UPN**
  
1. No controlador de domínio do AD DS, no Gerenciador do Servidor, escolha **Ferramentas** Domínios e Confianças do \> **Active Directory.**
    
    **Ou, se você não tiver o Windows Server 2012**
    
    Pressione **a tecla Windows + R** para abrir a caixa **de** diálogo Executar, digite Domain.msc e escolha **OK.**
    
    ![Escolha Domínios e Confianças do Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Na janela **Domínios e Confianças** do Active Directory, clique com o botão direito do mouse em Domínios e **Confianças** do Active Directory e escolha **Propriedades.**
    
    ![Clique com o botão direito do mouse em Domínios e Confianças do Active Directory e escolha Propriedades](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. Na guia Sufixos  **UPN,** na caixa Sufixos **UPN** Alternativos, digite seu novo sufixo OU sufixos UPN e escolha Adicionar \> Aplicar.
    
    ![Adicionar um novo sufixo UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Escolha **OK** quando terminar de adicionar sufixos. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Etapa 2: Alterar o sufixo UPN para usuários existentes
  
1. No controlador de domínio do AD DS, no Gerenciador do Servidor, escolha **Ferramentas** Usuários e Computadores \> **do Active Directory.**
    
    **Ou, se você não tiver o Windows Server 2012**
    
    Pressione **a tecla Windows + R** para abrir a caixa de diálogo Executar, digite Dsa.msc e clique em **OK** 
    
2. Selecione um usuário, clique com o botão direito do mouse e escolha **Propriedades.**
    
3. Na guia **Conta,** na lista drop-down de sufixos UPN, escolha o novo sufixo UPN e escolha **OK**.
    
    ![Adicionar novo sufixo UPN para um usuário](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Conclua estas etapas para cada usuário.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Usar o PowerShell para alterar o sufixo UPN para todos os seus usuários

Se você tiver muitas contas de usuário para atualizar, será mais fácil usar o PowerShell. O exemplo a seguir usa os cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) e [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) para alterar todos os sufixos contoso.local para contoso.com no AD DS. 

Por exemplo, você pode executar os seguintes comandos do PowerShell para atualizar todos os sufixos contoso.local contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Consulte [o módulo Windows PowerShell do Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=624314) para saber mais sobre como usar o Windows PowerShell no AD DS. 

