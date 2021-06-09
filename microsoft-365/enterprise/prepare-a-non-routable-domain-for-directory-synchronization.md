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
description: Saiba o que fazer se você tiver um domínio não stável associado às suas contas de usuário locais antes de sincroná-las com seu locatário Microsoft 365 local.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927391"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Preparar um domínio não roteável para sincronização de diretórios

Ao sincronizar seu diretório local com Microsoft 365, você precisa ter um domínio verificado no Azure Active Directory (Azure AD). Somente os UPNs (Nomes de Entidades de Usuário) associados ao domínio do AD DS (Serviços de Domínio do Active Directory) local são sincronizados. No entanto, qualquer UPN que contenha um domínio não stável, como ".local" (exemplo: billa@contoso.local), será sincronizado com um domínio .onmicrosoft.com (exemplo: billa@contoso.onmicrosoft.com). 

Se você usa atualmente um domínio ".local" para suas contas de usuário no AD DS, é recomendável alterá-las para usar um domínio verificado, como o billa@contoso.com, para sincronizar corretamente com seu domínio Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>E se eu tiver apenas um domínio local ".local"?

Você usa o Azure AD Conexão sincronizar seu AD DS com o locatário do Azure AD do seu locatário Microsoft 365 locatário. Para obter mais informações, consulte Integrando suas identidades locais [ao Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).
  
O Azure AD Conexão sincroniza o UPN e a senha dos usuários para que os usuários possam entrar com as mesmas credenciais que usam no local. No entanto, o Azure AD Conexão sincroniza usuários apenas com domínios verificados por Microsoft 365. Isso significa que o domínio também é verificado pelo Azure AD porque as identidades Microsoft 365 são gerenciadas pelo Azure AD. Em outras palavras, o domínio deve ser um domínio válido da Internet (como, .com, .org, .net, .us). Se o AD DS interno usar apenas um domínio não stável (por exemplo, ".local"), isso não poderá corresponder ao domínio verificado que você tem para seu locatário Microsoft 365. Você pode corrigir esse problema alterando seu domínio principal no AD DS local ou adicionando um ou mais sufixos UPN.
  
### <a name="change-your-primary-domain"></a>Alterar seu domínio primário

Altere seu domínio principal para um domínio que você verificou Microsoft 365, por exemplo, contoso.com. Todos os usuários que têm o domínio contoso.local são atualizados para contoso.com. No entanto, esse é um processo muito envolvido e uma solução mais fácil é descrita na seção a seguir.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Adicionar sufixos UPN e atualizar seus usuários para eles

Você pode resolver o problema ".local" registrando novos sufixos ou sufixos UPN no AD DS para corresponder ao domínio (ou domínios) verificado no Microsoft 365. Depois de registrar o novo sufixo, atualize os UPNs do usuário para substituir o ".local" pelo novo nome de domínio, por exemplo, para que uma conta de usuário se pareça com billa@contoso.com.
  
Depois de atualizar os UPNs para usar o domínio verificado, você estará pronto para sincronizar seu AD DS local com Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Etapa 1: Adicionar o novo sufixo UPN**
  
1. No controlador de domínio do AD DS, no Gerenciador de Servidores, escolha **Ferramentas** \> **Domínios e Confiações do Active Directory.**
    
    **Ou, se você não tiver Windows Server 2012**
    
    Pressione **Windows tecla + R** para  abrir a caixa de diálogo Executar e digite Domain.msc e escolha **OK**.
    
    ![Escolha Domínios e Confiações do Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Na janela **Domínios e Confiações** do Active Directory, clique com o botão direito do mouse em **Domínios** e Confiações do Active Directory e escolha **Propriedades**.
    
    ![Clique com o botão direito do mouse em Domínios e Confiações do Active Directory e escolha Propriedades](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. Na guia **Sufixos UPN,** na caixa **Sufixos UPN** alternativos, digite seu novo sufixo ou sufixo UPN e escolha **Adicionar** \> **Aplicar**.
    
    ![Adicionar um novo sufixo UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Escolha **OK** quando terminar de adicionar sufixos. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Etapa 2: Alterar o sufixo UPN para usuários existentes
  
1. No controlador de domínio do AD DS, no Gerenciador de Servidores, escolha **Ferramentas** \> **usuários e computadores do Active Directory.**
    
    **Ou, se você não tiver Windows Server 2012**
    
    Pressione **Windows tecla + R** para abrir a caixa de diálogo **Executar** e digite em Dsa.msc e clique em **OK**
    
2. Selecione um usuário, clique com o botão direito do mouse e escolha **Propriedades**.
    
3. Na guia **Conta,** na lista de sufixos UPN, escolha o novo sufixo UPN e escolha **OK**.
    
    ![Adicionar novo sufixo UPN para um usuário](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Conclua estas etapas para cada usuário.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Use o PowerShell para alterar o sufixo UPN para todos os seus usuários

Se você tiver muitas contas de usuário para atualizar, é mais fácil usar o PowerShell. O exemplo a seguir usa os cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) e [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) para alterar todos os sufixos contoso.local para contoso.com no AD DS. 

Por exemplo, você pode executar os seguintes comandos do PowerShell para atualizar todos os sufixos contoso.local para contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Consulte [o módulo Windows PowerShell do Active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) para saber mais sobre como usar Windows PowerShell no AD DS.