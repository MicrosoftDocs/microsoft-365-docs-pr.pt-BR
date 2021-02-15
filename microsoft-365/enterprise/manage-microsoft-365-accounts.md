---
title: Gerenciar contas de usuário do Microsoft 365
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
description: Saiba como gerenciar contas de usuário do Microsoft 365.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327754"
---
# <a name="manage-microsoft-365-user-accounts"></a>Gerenciar contas de usuário do Microsoft 365

Você pode gerenciar contas de usuário do Microsoft 365 de várias maneiras diferentes, dependendo da sua configuração. Você pode gerenciar contas de usuário no centro de administração do [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/add-users/) [PowerShell,](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)nos Serviços de Domínio do Active Directory (AD DS) ou no portal de administração do Azure Active Directory (Azure AD). 

Assim que você comprar o Microsoft 365, o Centro de administração do Microsoft 365 e o PowerShell poderão ser usados para gerenciar contas. Ao gerenciar identidades de nuvem, todas as pessoas em sua organização têm um nome de conta de usuário e senha separados. Se você quiser se integrar à sua infraestrutura local e tiver contas de usuário sincronizadas com o Microsoft 365, poderá usar o Azure AD Connect para fornecer sincronização de identidades e senhas para a funcionalidade de SSO (single sign-on).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planejar onde e como você gerenciará suas contas de usuário

Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para seu Microsoft 365. Os dois modelos gerais são somente na nuvem e híbridos.
  
### <a name="cloud-only"></a>Apenas Nuvem

Você cria e gerencia usuários no centro de administração do Microsoft 365. Você também pode usar o PowerShell ou o centro de administração do Azure AD. 
    
### <a name="hybrid"></a>Híbrido

As contas de usuário são sincronizadas com o Microsoft 365 a partir do AD DS, portanto, você deve usar ferramentas locais do AD DS para gerenciar contas de usuário. 
    
## <a name="managing-accounts"></a>Gerenciando contas

Ao decidir de que forma sua organização criará e gerenciará contas, considere os seguintes requisitos:
  
- O software de sincronização de diretório precisa ser instalado em servidores dentro de seu ambiente local para conectar as identidades entre o Microsoft 365 e seu AD DS.
    
- Qualquer opção de sincronização de diretório, incluindo opções de SSO, exige que seus atributos do AD DS atendem aos padrões. As especificações de quais atributos são usados em seu diretório e quais limpeza (se algum) é necessária são descritas em Preparar para sincronização de diretórios com o [Microsoft 365.](prepare-for-directory-synchronization.md) 
    
- Planeje como você criará contas do Microsoft 365.
    
A tabela a seguir lista as diferentes ferramentas de gerenciamento de conta.
    
|Ferramenta|Observações|
|:-----|:-----|
|Centro de administração do Microsoft 365  <br/> |[Adicionar usuários individualmente ou em massa](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Fornece uma interface da Web simples para adicionar e alterar contas de usuário.  <br/>  Não pode ser usado para alterar usuários se a sincronização de diretórios estiver habilitada (a atribuição de local e licença pode ser definida).  <br/>  Não pode ser usado com opções de SSO.  <br/> |
|Windows PowerShell  <br/> |[Gerenciar o Microsoft 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Permite adicionar usuários em massa usando um script do Windows PowerShell.  <br/>  Pode ser usado para atribuir local e licenças a contas, independentemente de como as contas são criadas.  <br/> |
|Importação em massa  <br/> |[Adicionar vários usuários ao mesmo tempo](add-several-users-at-the-same-time.md) <br/>  Permite importar um arquivo CSV para adicionar um grupo de usuários ao Microsoft 365.  <br/>  Não pode ser usado com opções de SSO.  <br/> |
|Azure Active Directory  <br/> |Você pode obter uma edição gratuita do Azure AD com sua assinatura do Microsoft 365. Você pode executar funções como redefinição de senha de autoatendida para usuários de nuvem e personalização das páginas de Entrada e Painel de Acesso usando a edição gratuita. Para obter funcionalidade avançada, você pode atualizar para a edição básica, Azure AD Premium P1 ou Azure AD Premium P2. Confira [as edições do Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=698465) para ver a lista de recursos com suporte.  <br/> |
|Sincronização de diretório  <br/> |[Integrando suas identidades locais ao Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Para sincronização de diretórios com ou sem sincronização de senha, use [o Azure AD Connect com configurações expressas.](https://go.microsoft.com/fwlink/p/?LinkID=698537)  <br/>  Para várias florestas e opções de SSO, use [a Instalação Personalizada do Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkId=698430)  <br/>  Fornece a infraestrutura necessária para habilitar o SSO.  <br/>  Necessário para muitos cenários híbridos, como migração em estágios e Exchange híbrido  <br/>  Sincroniza grupos habilitados para email e segurança do AD DS.  <br/> |
|||
   
- Independentemente de como você pretende adicionar as contas de usuário ao Microsoft 365, você precisa gerenciar vários recursos de conta, como a atribuição de licenças, a especificação de local e assim por diante. Esses recursos podem ser gerenciados a longo prazo no centro de administração do Microsoft 365 ou você também pode criar contas de [usuário com o PowerShell.](https://go.microsoft.com/fwlink/p/?LinkId=717083)
    
    Se você optar por adicionar e gerenciar todos os seus usuários por meio do centro de administração, você especificará o local e atribuirá licenças ao mesmo tempo que criar a conta do Microsoft 365. Como resultado, não é necessário muito planejamento.
    
    > [!IMPORTANT]
    > Criar contas no Microsoft 365 sem atribuir uma licença (ao SharePoint Online, por exemplo) significa que o proprietário da conta pode exibir o centro do Microsoft 365, mas não pode acessar nenhum dos serviços dentro da assinatura da sua empresa. Depois de atribuir um local e a licença, a conta será replicada para o serviço ou serviços que você atribuiu. O usuário pode entrar em sua conta e usar os serviços que você atribuiu a ele. 
  
## <a name="see-also"></a>Confira também

[Centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
