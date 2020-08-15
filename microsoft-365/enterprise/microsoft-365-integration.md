---
title: Integração do Microsoft 365 com ambientes locais
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687482"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Integração do Microsoft 365 com ambientes locais

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode integrar o Microsoft 365 com os serviços de diretório existentes e com uma instalação local do Exchange Server, do Skype for Business Server 2015 ou do SharePoint Server.
  
 - Ao se integrar aos serviços de diretório, você pode sincronizar e gerenciar contas de usuário para ambos os ambientes. Você também pode adicionar a sincronização de hash de senha ou SSO (logon único) para que os usuários possam fazer logon em ambos os ambientes com suas credenciais locais.
 - Ao se integrar aos produtos do servidor local, você cria um ambiente híbrido. Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para a Microsoft 365, ou pode continuar a ter alguns usuários ou algumas informações no local e alguns na nuvem. Para obter mais informações sobre ambientes híbridos, consulte [Hybrid Cloud Overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).

Você também pode usar os supervisor do Azure Active Directory (Azure AD) para obter orientação de instalação personalizada (você deve estar conectado ao Microsoft 365):

- [Sincronizar usuários do diretório da sua organização](https://aka.ms/aadconnectpwsync)
- [Supervisor de implantação do AD FS](https://aka.ms/adfsguidance)
- [Guia de instalação do Azure AD](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a>Antes de começar

Antes de integrar o Microsoft 365 e um ambiente local, você também precisará participar do [planejamento de rede e do ajuste de desempenho](network-planning-and-performance.md). Você também vai querer entender os modelos de [identidade](about-microsoft-365-identity.md)disponíveis. 

Confira [onde gerenciar contas da microsoft 365](manage-microsoft-365-accounts.md) para obter uma lista de ferramentas que você pode usar para gerenciar usuários e contas do Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-directory-services"></a>Integrar o Microsoft 365 com os serviços de diretório
Se você tiver contas de usuário existentes em um diretório local, não será necessário recriar todas essas contas no Microsoft 365 e correr o risco de introdução a diferenças ou erros entre os ambientes. A sincronização de diretórios ajuda você a espelhar essas contas entre seus ambientes online e local. Com a sincronização de diretórios, os usuários não precisam se lembrar de novas informações para cada ambiente, e você não precisa criar ou atualizar contas duas vezes. Você precisará [preparar o diretório local para a](prepare-for-directory-synchronization.md) sincronização de diretórios.
  
![Usar a sincronização de diretórios para manter as informações de conta de usuário local e online sincronizadas](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
Se quiser que os usuários possam fazer logon no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO. Com o SSO, a Microsoft 365 é configurada para confiar no ambiente local para autenticação do usuário.
  
![Com o logon único, a mesma conta está disponível nos ambientes local e online](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
Diferentes técnicas de gerenciamento de contas de usuário fornecem experiências diferentes para seus usuários, conforme mostrado na tabela a seguir.
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a>Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem

Um usuário faz logon no seu ambiente local com a conta de usuário (domínio \ nome_de_usuário). Quando eles acessam o Microsoft 365, eles devem fazer logon novamente com sua conta corporativa ou de estudante (user@domain.com). O nome de usuário é o mesmo em ambos os ambientes. Quando você adiciona a sincronização de hash de senha ou a autenticação de passagem, o usuário tem a mesma senha para os dois ambientes, mas precisará fornecer essas credenciais novamente ao fazer logon no Microsoft 365. A sincronização de diretórios com sincronização de hash de senha é o cenário de sincronização de diretório mais comumente usado.

Para configurar a sincronização de diretórios, use o Azure Active Directory Connect. Para obter instruções, leia [Configurar a sincronização de diretório para o Microsoft 365 e o](set-up-directory-synchronization.md) [Azure ad Connect com as configurações expressas](https://go.microsoft.com/fwlink/p/?LinkId=698537).

Saiba mais sobre [a preparação para a sincronização de diretório para o Microsoft 365](prepare-for-directory-synchronization.md) e [integração de seus identificações locais com o Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).

### <a name="directory-synchronization-with-sso"></a>Sincronização de diretórios com SSO

Um usuário faz logon no seu ambiente local com a conta de usuário. Quando eles acessam o Microsoft 365, eles são conectados automaticamente ou fazem logon usando as mesmas credenciais que usam para seu ambiente local (domínio \ nome de usuário).

Para configurar o SSO, você também usa o Azure AD Connect. Para obter instruções, leia [instalação personalizada do Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).

Saiba mais sobre o [logon único para aplicativos no Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).

## <a name="azure-ad-connect"></a>Azure AD Connect

O Azure AD Connect substitui versões antigas das ferramentas de integração de identidades como DirSync e sincronização do Azure AD. Para obter mais informações, consulte [o que é a identidade híbrida com o Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969). Se você deseja atualizar da sincronização do Azure Active Directory para o Azure AD Connect, consulte [as instruções de atualização](https://go.microsoft.com/fwlink/p/?LinkId=733240). 

Confira também a [implantação da sincronização de diretórios do microsoft 365 no Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
