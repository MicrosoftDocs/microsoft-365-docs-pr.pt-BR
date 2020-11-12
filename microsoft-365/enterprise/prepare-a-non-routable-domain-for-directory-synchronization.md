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
description: Saiba o que fazer se você tiver um domínio não routale associado aos seus usuários locais antes de sincronizar com o Microsoft 365.
ms.openlocfilehash: 21344cb0d495691a96867d401a5262fbbcfd02d4
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002376"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Preparar um domínio não roteável para sincronização de diretórios
Ao sincronizar seu diretório local com o Microsoft 365, você precisa ter um domínio verificado no Azure Active Directory (Azure AD). Somente os nomes principais de usuário (UPN) associados ao domínio local são sincronizados. No entanto, qualquer UPN que contenha um domínio não roteável, por exemplo. local (como billa@contoso. local), será sincronizado com um domínio. onmicrosoft.com (como billa@contoso.onmicrosoft.com). 

Se você usa atualmente um domínio. local para suas contas de usuário nos serviços de domínio do Active Directory (AD DS), recomenda-se alterá-lo para usar um domínio verificado (como o billa@contoso.com) a fim de sincronizar corretamente com seu domínio do Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>E se eu só tiver um domínio. local local?

A ferramenta mais recente que você pode usar para sincronizar seu AD DS com o Azure AD é chamada Azure AD Connect. Para obter mais informações, consulte [integrando suas identidades locais com o Azure ad](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).
  
O Azure AD Connect sincroniza o UPN e a senha dos usuários para que os usuários possam entrar com as mesmas credenciais que usam no local. No entanto, o Azure AD Connect sincroniza apenas os usuários em domínios verificados pelo Microsoft 365. Isso significa que o domínio também é verificado pelo Azure AD porque as identidades do Microsoft 365 são gerenciadas pelo Azure AD. Em outras palavras, o domínio deve ser um domínio válido da Internet (por exemplo,. com,. org, .net,. us, etc.). Se o AD DS interno usar apenas um domínio não roteável (por exemplo,. local), isso não poderá corresponder ao domínio verificado que você tem no Microsoft 365. Você pode corrigir esse problema alterando seu domínio primário no AD DS local ou adicionando um ou mais sufixos UPN.
  
### <a name="change-your-primary-domain"></a>**Alterar seu domínio primário**

Altere o domínio primário para um domínio verificado no Microsoft 365, por exemplo, contoso.com. Todos os usuários que têm o domínio contoso. local é atualizado para o contoso.com. Esse é um processo muito envolvido, no entanto, e uma solução mais fácil é descrita na seção a seguir.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>**Adicionar sufixos UPN e atualizar seus usuários para eles**

Você pode resolver o problema. local registrando novos sufixos de UPN ou sufixos no AD DS para corresponder ao domínio (ou domínios) que você verificou no Microsoft 365. Depois de registrar o novo sufixo, você atualizará os UPNs do usuário para substituir o. local pelo novo nome de domínio, por exemplo, para que uma conta de usuário se pareça com billa@contoso.com.
  
Depois de atualizar os UPNs para usar o domínio verificado, você estará pronto para sincronizar seu AD DS local com o Microsoft 365.
  
 **Etapa 1: Adicionar o novo sufixo UPN**
  
1. No controlador de domínio do AD DS, no Gerenciador de servidores, escolha **ferramentas** \> **domínios e relações de confiança do Active Directory**.
    
    **Ou, se você não tiver o Windows Server 2012**
    
    Pressione a **tecla Windows + R** para abrir a caixa de diálogo **executar** e digite domain. msc e, em seguida, escolha **OK**.
    
    ![Escolha domínios e relações de confiança do Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Na janela **domínios e relações de confiança do Active Directory** , clique com o botão direito em **domínios e relações de confiança do Active Directory** e escolha **Propriedades**.
    
    ![Clique com o botão direito em domínios e relações de confiança do Active Directory e escolha Propriedades](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. Na guia **sufixos UPN** , na caixa **sufixos UPN alternativos** , digite seu novo sufixo UPN ou sufixos e, em seguida, escolha **Adicionar** \> **aplicar**.
    
    ![Adicionar um novo sufixo UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Escolha **OK** quando terminar de adicionar os sufixos. 
    
 **Etapa 2: alterar o sufixo UPN para usuários existentes**
  
1. No controlador de domínio do AD DS, no Gerenciador de servidores, escolha **ferramentas** \> **usuários e computadores do Active Directory**.
    
    **Ou, se você não tiver o Windows Server 2012**
    
    Pressione a **tecla Windows + R** para abrir a caixa de diálogo **executar** e digite dsa. msc e clique em **OK**
    
2. Selecione um usuário, clique com o botão direito do mouse e escolha **Propriedades**.
    
3. Na guia **conta** , na lista suspensa sufixo de UPN, escolha o novo sufixo UPN e, em seguida, escolha **OK**.
    
    ![Adicionar novo sufixo UPN para um usuário](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Conclua estas etapas para cada usuário.
    
   
### <a name="you-can-also-use-windows-powershell-to-change-the-upn-suffix-for-all-users"></a>**Você também pode usar o Windows PowerShell para alterar o sufixo UPN de todos os usuários**

Se você tiver muitos usuários para atualizar, é mais fácil usar o Windows PowerShell. O exemplo a seguir usa os cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) e [set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) para alterar todos os sufixos contoso. local para contoso.com. 

FOE exemplo, você pode executar os seguintes comandos do Windows PowerShell para atualizar todos os sufixos contoso. local para contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Consulte [Active Directory Windows PowerShell Module](https://go.microsoft.com/fwlink/p/?LinkId=624314) para saber mais sobre como usar o Windows PowerShell no AD DS. 

