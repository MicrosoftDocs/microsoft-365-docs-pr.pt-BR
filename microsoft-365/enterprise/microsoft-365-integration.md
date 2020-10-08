---
title: Integração do Microsoft 365 com ambientes locais
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
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: Neste artigo, saiba como integrar o Microsoft 365 com os serviços de diretório existentes e ambientes locais.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384859"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Integração do Microsoft 365 com ambientes locais

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode integrar o Microsoft 365 com os serviços de domínio do Active Directory (AD DS) local existentes e com instalações locais do Exchange Server, do Skype for Business Server 2015 ou do SharePoint Server.
  
 - Ao integrar o AD DS, você pode sincronizar e gerenciar contas de usuário de ambos os ambientes. Você também pode adicionar a sincronização de hash de senha (PHS) ou logon único (SSO) para que os usuários possam fazer logon em ambos os ambientes com suas credenciais locais.
 - Ao se integrar aos produtos do servidor local, você cria um ambiente híbrido. Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para a Microsoft 365, ou pode continuar a ter alguns usuários ou algumas informações no local e alguns na nuvem. Para obter mais informações sobre ambientes híbridos, consulte [nuvem híbrida](../solutions/cloud-architecture-models.md#hybrid).

Você também pode usar os supervisor do Azure Active Directory (Azure AD) para obter orientação de instalação personalizada no centro de administração do Microsoft 365 (você deve estar conectado ao Microsoft 365):

- [Guia de instalação do Azure AD](https://aka.ms/aadpguidance)
- [Sincronizar usuários do diretório da sua organização](https://aka.ms/aadconnectpwsync)
- [Supervisor de implantação dos serviços de Federação do Active Directory (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Antes de começar

Antes de integrar o Microsoft 365 e um ambiente local, você também precisa fazer o [planejamento de rede e o ajuste de desempenho](network-planning-and-performance.md). Você também vai querer entender os modelos de [identidade](about-microsoft-365-identity.md)disponíveis. 

Consulte [Manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) para obter uma lista de ferramentas que você pode usar para gerenciar contas de usuário do Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrar o Microsoft 365 com o AD DS

Se você tiver contas de usuário existentes no AD DS, não desejará recriar todas essas contas no Microsoft 365 e correr o risco de introdução a diferenças ou erros entre os ambientes. A sincronização de diretórios ajuda você a espelhar as contas entre seus ambientes locais e online. Com a sincronização de diretórios, os usuários não precisam se lembrar de novas informações para cada ambiente, e você não precisa criar ou atualizar contas duas vezes. Você precisará [preparar o diretório local para a](prepare-for-directory-synchronization.md) sincronização de diretórios.
  
![Usar a sincronização de diretórios para manter as informações de conta de usuário local e online sincronizadas](../media/microsoft-365-integration/directory-synchronization.png)
  
Se quiser que os usuários possam fazer logon no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO. Com o SSO, a Microsoft 365 é configurada para confiar no ambiente local para autenticação do usuário.
  
![Com o logon único, a mesma conta está disponível nos ambientes local e online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem (PTA)

Um usuário faz logon no seu ambiente local com a conta de usuário (domínio \ nome_de_usuário). Quando eles acessam o Microsoft 365, eles devem fazer logon novamente com sua conta corporativa ou de estudante (user@domain.com). O nome de usuário é o mesmo em ambos os ambientes. Quando você adiciona PHS ou PTA, o usuário tem a mesma senha para ambos os ambientes, mas precisará fornecer essas credenciais novamente ao fazer logon no Microsoft 365. A sincronização de diretórios com o PHS é a sincronização de diretórios mais comumente usada.

Para configurar a sincronização de diretórios, use o Azure AD Connect. Para obter instruções, consulte [Configurar a sincronização de diretórios para o Microsoft 365 e o](set-up-directory-synchronization.md) [Azure ad Connect com as configurações expressas](https://go.microsoft.com/fwlink/p/?LinkId=698537).

Saiba mais sobre [a preparação para a sincronização de diretório para o Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Sincronização de diretórios com SSO

Um usuário faz logon no seu ambiente local com a conta de usuário. Quando eles acessam o Microsoft 365, eles são conectados automaticamente ou fazem logon usando as mesmas credenciais que usam para seu ambiente local (domínio \ nome de usuário).

Para configurar o SSO, você também usa o Azure AD Connect. Para obter instruções, consulte [instalação personalizada do Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).

Para obter mais informações, consulte [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).

## <a name="azure-ad-connect"></a>Azure AD Connect

O Azure AD Connect substitui versões antigas das ferramentas de integração de identidades como DirSync e sincronização do Azure AD. Se você deseja atualizar da sincronização do Azure Active Directory para o Azure AD Connect, consulte [as instruções de atualização](https://go.microsoft.com/fwlink/p/?LinkId=733240). 

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
