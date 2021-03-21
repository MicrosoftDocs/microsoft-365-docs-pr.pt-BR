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
description: Neste artigo, saiba como integrar o Microsoft 365 com seus serviços de diretório existentes e ambientes locais.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923961"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Integração do Microsoft 365 com ambientes locais

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Você pode integrar o Microsoft 365 com seus Serviços de Domínio do Active Directory (AD DS) existentes e com instalações locais do Exchange Server, Skype for Business Server 2015 ou SharePoint Server.
  
 - Ao integrar o AD DS, você pode sincronizar e gerenciar contas de usuário para ambos os ambientes. Você também pode adicionar a sincronização de hash de senha (PHS) ou logoff único (SSO) para que os usuários possam fazer logoff em ambos os ambientes com suas credenciais locais.
 - Quando você se integra com produtos de servidor local, cria um ambiente híbrido. Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para o Microsoft 365 ou pode continuar a ter alguns usuários ou algumas informações locais e algumas na nuvem. Para obter mais informações sobre ambientes híbridos, consulte [nuvem híbrida](../solutions/cloud-architecture-models.md#hybrid).

Você também pode usar os consultores do Azure Active Directory (Azure AD) para orientação de configuração personalizada no Centro de administração do Microsoft 365 (você deve estar loco no Microsoft 365):

- [Guia de configuração do Azure AD](https://aka.ms/aadpguidance)
- [Sincronizar usuários do diretório da sua organização](https://aka.ms/aadconnectpwsync)
- [Consultor de implantação dos Serviços de Federação do Active Directory (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Antes de começar

Antes de integrar o Microsoft 365 e um ambiente local, você também precisa fazer planejamento de rede e ajuste [de desempenho.](network-planning-and-performance.md) Você também vai querer entender os modelos de identidade [disponíveis.](about-microsoft-365-identity.md) 

Consulte [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrar o Microsoft 365 ao AD DS

Se você tiver contas de usuário existentes no AD DS, não deseja criar todas essas contas no Microsoft 365 e correr o risco de introduzir diferenças ou erros entre os ambientes. A sincronização de diretórios ajuda você a espelhar essas contas entre seus ambientes locais e online. Com a sincronização de diretórios, os usuários não têm que se lembrar de novas informações para cada ambiente e você não precisa criar ou atualizar contas duas vezes. Você precisará preparar [seu diretório local](prepare-for-directory-synchronization.md) para sincronização de diretórios.
  
![Usar a sincronização de diretórios para manter as informações de conta de usuário local e online sincronizadas](../media/microsoft-365-integration/directory-synchronization.png)
  
Se você quiser que os usuários possam fazer logoff no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO. Com o SSO, o Microsoft 365 é configurado para confiar no ambiente local para autenticação do usuário.
  
![Com o login único, a mesma conta está disponível nos ambientes local e online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem (PTA)

Um usuário faz o login em seu ambiente local com sua conta de usuário (domínio\nome de usuário). Quando eles vão para o Microsoft 365, eles devem fazer logoff novamente com sua conta de trabalho ou de estudante (user@domain.com). O nome de usuário é o mesmo em ambos os ambientes. Quando você adiciona PHS ou PTA, o usuário tem a mesma senha para ambos os ambientes, mas terá que fornecer essas credenciais novamente ao entrar no Microsoft 365. A sincronização de diretório com o PHS é a sincronização de diretório mais usada.

Para configurar a sincronização de diretórios, use o Azure AD Connect. Para obter instruções, consulte [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).

Saiba mais sobre [como preparar a sincronização de diretórios para o Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Sincronização de diretório com SSO

Um usuário faz o login em seu ambiente local com sua conta de usuário. Quando eles vão para o Microsoft 365, eles estão conectados automaticamente ou fazem logoff usando as mesmas credenciais que usam para seu ambiente local (domínio\nome de usuário).

Para configurar o SSO, você também usa o Azure AD Connect. Para obter instruções, consulte [Instalação personalizada do Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).

Para obter mais informações, consulte [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="azure-ad-connect"></a>Azure AD Connect

O Azure AD Connect substitui versões mais antigas de ferramentas de integração de identidade, como DirSync e Sincronização do Azure AD. Se você quiser atualizar do Azure Active Directory Sync para o Azure AD Connect, consulte [as instruções de atualização](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started). 

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)