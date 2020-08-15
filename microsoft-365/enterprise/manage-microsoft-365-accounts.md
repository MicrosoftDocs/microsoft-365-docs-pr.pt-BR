---
title: Ferramentas para gerenciar contas de usuário do Microsoft 365
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
description: Saiba mais sobre quais ferramentas usar e como gerenciar contas do Microsoft 365.
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687411"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a>Ferramentas para gerenciar contas de usuário do Microsoft 365

Você pode gerenciar os usuários do Microsoft 365 de várias maneiras diferentes, dependendo de sua configuração. Você pode gerenciar usuários no [centro de administração do Microsoft 365](https://admin.microsoft.com), no Windows PowerShell, nos serviços de domínio do Active Directory (AD DS) ou no portal de administração do Azure Active Directory (Azure AD). 

Assim que você adquirir o Microsoft 365, o centro de administração e o Windows PowerShell podem ser usados para gerenciar contas. Ao gerenciar identidades de nuvem, cada pessoa em sua organização tem uma ID de usuário e senha separada para o Microsoft 365. Se você deseja integrar com sua infraestrutura local e ter contas de usuário sincronizadas com o Microsoft 365, você pode usar o Azure AD Connect para fornecer sincronização de identidades e senhas para a funcionalidade de logon único.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planejar para onde e como você irá gerenciar suas contas de usuário

Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para o seu Microsoft 365. Os dois modelos gerais são autenticação de nuvem e autenticação federada.
  
### <a name="cloud-authentication"></a>Autenticação na nuvem

- Autenticação na nuvem-crie e gerencie usuários no centro de administração do Microsoft 365. Você também pode usar o Windows PowerShell ou o Azure AD. 
    
- Sincronização de hash de senha (PHS) com logon único contínuo-a maneira mais simples de habilitar a autenticação para objetos do AD DS no Azure AD. Com o PHS, você sincroniza seus objetos de conta de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local. 
    
- Autenticação de passagem (PTA) com logon único contínuo – fornece uma validação de senha simples para os serviços de autenticação do Azure AD usando um agente de software em execução em um ou mais servidores locais para validar os usuários diretamente com o AD DS. 
    
### <a name="federated-authentication"></a>Autenticação federada

- Opções de autenticação federada – primariamente para grandes organizações corporativas com requisitos de autenticação mais complexos, os objetos do AD DS são sincronizados com o Microsoft 365 e as contas de usuários são gerenciadas no local. 
    
- [Provedores de autenticação e identidade](about-microsoft-365-identity.md) de terceiros-os objetos do AD DS podem ser sincronizados com o Microsoft 365 e o acesso a recursos em nuvem é basicamente gerenciado por um provedor de identidade de terceiros (IDP). 
    
## <a name="managing-accounts"></a>Gerenciando contas

Ao decidir o modo como sua organização criará e gerenciará contas, considere os seguintes requisitos:
  
- O software de sincronização de diretório precisa ser instalado em servidores dentro do seu ambiente local para conectar as identidades entre o Microsoft 365 e o AD DS.
    
- Qualquer opção de sincronização de diretório, incluindo as opções de SSO, requer que seus atributos do AD DS atendam aos padrões. As informações específicas de quais atributos são usados no seu diretório e qual limpeza (se houver) é necessária são descritas em preparar-se [para provisionar usuários por meio da sincronização de diretório para o Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planejar como você vai criar contas do Microsoft 365.
    
    A tabela a seguir lista as diferentes ferramentas de gerenciamento de contas.
    
|**Opção**|**Observações**|
|:-----|:-----|
|Centro de administração  <br/> |[Adicionar usuários individualmente ou em massa](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Fornece uma interface Web simples para adicionar e alterar contas de usuário.  <br/>  Não pode ser usado para alterar usuários se a sincronização de diretórios estiver habilitada (a atribuição de local e licença pode ser definida).  <br/>  Não pode ser usado com opções de SSO.  <br/> |
|Windows PowerShell  <br/> |[Gerenciar o Microsoft 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Permite adicionar usuários a usuários em massa usando um script do Windows PowerShell.  <br/>  Pode ser usado para atribuir local e licenças a contas, independentemente de como as contas são criadas.  <br/> |
|Importação em massa  <br/> |[Adicionar vários usuários ao mesmo tempo](add-several-users-at-the-same-time.md) <br/>  Permite importar um arquivo CSV para adicionar um grupo de usuários ao Microsoft 365.  <br/>  Não pode ser usado com opções de SSO.  <br/> |
|Azure AD  <br/> |Você Obtém uma edição gratuita do Azure AD com sua assinatura do Microsoft 365. Você pode executar funções como redefinição de senha de autoatendimento para usuários em nuvem e a personalização das páginas de entrada e do painel de acesso usando a edição gratuita. Para obter funcionalidades aprimoradas, você pode atualizar para o Basic Edition, o Azure AD Premium P1 ou o Azure AD Premium P2. Consulte [Azure ad Editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) para obter a lista de recursos com suporte.  <br/> |
|Sincronização de diretório  <br/> |[Integração de suas identidades locais com o Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Para a sincronização de diretórios com ou sem a sincronização de senha, use o [Azure ad Connect com as configurações expressas](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Para várias florestas e opções de SSO, use a [instalação personalizada do Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Fornece a infraestrutura necessária para habilitar o SSO.  <br/>  Obrigatório para vários cenários híbridos:  <br/>  Migração em estágios  <br/>  Híbrida do Exchange  <br/>  Sincroniza os grupos de segurança e habilitado para email do AD DS.  <br/> |
   
- Independentemente de como você pretende adicionar as contas de usuário ao Microsoft 365, precisa gerenciar vários recursos de conta, como atribuir licenças, especificar o local e assim por diante. Esses recursos podem ser gerenciados de longo prazo no centro de administração ou você também pode [criar contas de usuário com o PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Se você optar por adicionar e gerenciar todos os seus usuários por meio do centro de administração, você especificará o local e atribuirá licenças ao mesmo tempo que a criação da conta da Microsoft 365. Como resultado, não é necessário o planejamento.
    
    > [!IMPORTANT]
    > A criação de contas no Microsoft 365 sem a atribuição de uma licença (para o SharePoint Online, por exemplo) significa que o proprietário da conta pode exibir o centro de 365 da Microsoft, mas não pode acessar qualquer um dos serviços dentro da assinatura da empresa. Depois de atribuir um local e a licença, a conta é replicada para o serviço ou serviços que você atribuiu. O usuário pode entrar em sua conta e usar os serviços que você atribuiu a eles. 
  
## <a name="next-steps"></a>Próximas etapas

[Integração do Microsoft 365 com ambientes locais](microsoft-365-integration.md)
  
## <a name="see-also"></a>Confira também

[Gerenciar usuários e grupos no Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
