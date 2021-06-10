---
title: Gerenciar Microsoft 365 contas de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Saiba como gerenciar contas de Microsoft 365 de usuário.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909557"
---
# <a name="manage-microsoft-365-user-accounts"></a>Gerenciar Microsoft 365 contas de usuário

Você pode gerenciar Microsoft 365 contas de usuário de várias maneiras diferentes, dependendo da configuração. Você pode gerenciar contas de usuário no centro de administração do [Microsoft 365](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), no Active Directory Domain Services (AD DS) ou no portal de administração Azure Active Directory (Azure AD). 

Assim que você comprar Microsoft 365, o centro de administração Microsoft 365 e o PowerShell podem ser usados para gerenciar contas. Ao gerenciar identidades na nuvem, cada pessoa em sua organização tem um nome de conta de usuário e senha separados. Se você quiser integrar-se à sua infraestrutura local e ter contas de usuário sincronizadas com o Microsoft 365, você pode usar o Azure AD Conexão para fornecer sincronização de identidades e senhas para a funcionalidade de SSO (login único).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planejar onde e como você gerenciará suas contas de usuário

Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para sua Microsoft 365. Os dois modelos gerais são somente na nuvem e híbridos.
  
### <a name="cloud-only"></a>Apenas Nuvem

Crie e gerencie usuários no Microsoft 365 de administração. Você também pode usar o PowerShell ou o centro de administração do Azure AD. 
    
### <a name="hybrid"></a>Híbrido

As contas de usuário são sincronizadas com Microsoft 365 do AD DS, portanto, você deve usar as ferramentas locais do AD DS para gerenciar contas de usuário. 
    
## <a name="managing-accounts"></a>Gerenciando contas

Ao decidir qual maneira sua organização criará e gerenciará contas, considere os seguintes requisitos:
  
- O software de sincronização de diretório precisa ser instalado em servidores em seu ambiente local para conectar as identidades entre Microsoft 365 e seu AD DS.
    
- Qualquer opção de sincronização de diretório, incluindo opções de SSO, exige que seus atributos do AD DS atendem aos padrões. As especificidades de quais atributos são usados no diretório e quais limpeza (se algum) é necessária são descritas em [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planeje como você criará Microsoft 365 contas.
    
A tabela a seguir lista as diferentes ferramentas de gerenciamento de conta.
    
|Ferramenta|Observações|
|:-----|:-----|
|Centro de administração do Microsoft 365  <br/> |[Adicionar usuários individualmente ou em massa](../admin/add-users/add-users.md) <br/>  Fornece uma interface da Web simples para adicionar e alterar contas de usuário.  <br/>  Não é possível usar para alterar usuários se a sincronização de diretório estiver habilitada (a atribuição de local e licença pode ser definida).  <br/>  Não pode ser usado com opções de SSO.  <br/> |
|Windows PowerShell  <br/> |[Gerenciar Microsoft 365 com Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Permite adicionar usuários em massa usando Windows PowerShell script.  <br/>  Pode ser usado para atribuir local e licenças a contas, independentemente de como as contas são criadas.  <br/> |
|Importação em massa  <br/> |[Adicionar vários usuários ao mesmo tempo](add-several-users-at-the-same-time.md) <br/>  Permite importar um arquivo CSV para adicionar um grupo de usuários a Microsoft 365.  <br/>  Não pode ser usado com opções de SSO.  <br/> |
|Azure Active Directory  <br/> |Você tem uma edição gratuita do Azure AD com sua assinatura Microsoft 365 assinatura. Você pode executar funções como redefinição de senha de autoatendida para usuários de nuvem e personalização das páginas Entrar e Painel de Acesso usando a edição gratuita. Para obter funcionalidade avançada, você pode atualizar para a edição básica, Azure AD Premium P1 ou Azure AD Premium P2. Consulte [edições do Azure AD](/azure/active-directory/fundamentals/active-directory-whatis) para ver a lista de recursos com suporte.  <br/> |
|Sincronização de diretório  <br/> |[Integrando suas identidades locais ao Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  Para sincronização de diretório com ou sem sincronização de senha, use [o Azure AD Conexão com configurações expressas](/azure/active-directory/hybrid/how-to-connect-install-express).  <br/>  Para várias florestas e opções de SSO, use [Instalação Personalizada do Azure AD Conexão](/azure/active-directory/hybrid/how-to-connect-install-custom).  <br/>  Fornece a infraestrutura necessária para habilitar o SSO.  <br/>  Necessário para muitos cenários híbridos, como migração em estágios e Exchange  <br/>  Sincroniza grupos habilitados para email e segurança do AD DS.  <br/> |
|||
   
- Independentemente de como você pretende adicionar as contas de usuário ao Microsoft 365, você precisa gerenciar vários recursos de conta, como a atribuição de licenças, a especificação de local e assim por diante. Esses recursos podem ser gerenciados a longo prazo a partir do centro de administração Microsoft 365 ou você também pode criar contas de [usuário com o PowerShell](./create-user-accounts-with-microsoft-365-powershell.md).
    
    Se você optar por adicionar e gerenciar todos os seus usuários por meio do centro de administração, especificará o local e atribuirá licenças ao mesmo tempo que criar a conta Microsoft 365. Como resultado, não é necessário muito planejamento.
    
    > [!IMPORTANT]
    > Criar contas no Microsoft 365 sem atribuir uma licença (ao SharePoint Online, por exemplo) significa que o proprietário da conta pode exibir o centro de Microsoft 365, mas não pode acessar nenhum dos serviços dentro da assinatura da sua empresa. Depois de atribuir um local e a licença, a conta será replicada para o serviço ou serviços atribuídos. O usuário pode entrar em sua conta e usar os serviços atribuídos a eles. 
  
## <a name="see-also"></a>Confira também

[Centro de administração do Microsoft 365](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)