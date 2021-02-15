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
description: Neste artigo, saiba como integrar o Microsoft 365 com seus serviços de diretório e ambientes locais existentes.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384859"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Integração do Microsoft 365 com ambientes locais

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode integrar o Microsoft 365 com seus Active Directory Domain Services (AD DS) locais existentes e com instalações locais do Exchange Server, Skype for Business Server 2015 ou SharePoint Server.
  
 - Ao integrar o AD DS, você pode sincronizar e gerenciar contas de usuário para ambos os ambientes. Você também pode adicionar a sincronização de hash de senha (PHS) ou o logoff único (SSO) para que os usuários possam fazer logoff em ambos os ambientes com suas credenciais locais.
 - Ao se integrar aos produtos de servidor local, você cria um ambiente híbrido. Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para o Microsoft 365 ou pode continuar a ter alguns usuários ou algumas informações locais e algumas na nuvem. Para obter mais informações sobre ambientes híbridos, consulte [nuvem híbrida.](../solutions/cloud-architecture-models.md#hybrid)

Você também pode usar os consultores do Azure Active Directory (Azure AD) para obter orientações de configuração personalizadas no Centro de administração do Microsoft 365 (você deve estar assinado no Microsoft 365):

- [Guia de configuração do Azure AD](https://aka.ms/aadpguidance)
- [Sincronizar usuários do diretório da sua organização](https://aka.ms/aadconnectpwsync)
- [Consultor de implantação dos Serviços de Federação do Active Directory (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Antes de começar

Antes de integrar o Microsoft 365 e um ambiente local, você também precisa fazer planejamento de rede e ajuste [de desempenho.](network-planning-and-performance.md) Você também vai querer entender os modelos de [identidade disponíveis.](about-microsoft-365-identity.md) 

Confira [gerenciar contas do Microsoft 365](manage-microsoft-365-accounts.md) para ver uma lista de ferramentas que você pode usar para gerenciar contas de usuário do Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrar o Microsoft 365 ao AD DS

Se você tiver contas de usuário existentes no AD DS, não será necessário criar todas essas contas no Microsoft 365 com risco de introduzir diferenças ou erros entre os ambientes. A sincronização de diretórios ajuda a espelhar essas contas entre seus ambientes locais e online. Com a sincronização de diretórios, os usuários não têm que se lembrar de novas informações para cada ambiente e você não precisa criar ou atualizar contas duas vezes. Você precisará preparar [seu diretório local](prepare-for-directory-synchronization.md) para a sincronização de diretórios.
  
![Usar a sincronização de diretórios para manter as informações da conta de usuário local e online sincronizadas](../media/microsoft-365-integration/directory-synchronization.png)
  
Se quiser que os usuários possam fazer logoff no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO. Com o SSO, o Microsoft 365 é configurado para confiar no ambiente local para autenticação do usuário.
  
![Com o single sign-on, a mesma conta está disponível nos ambientes local e online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem (PTA)

Um usuário faz o login em seu ambiente local com sua conta de usuário (domínio /nome de usuário). Ao acessar o Microsoft 365, eles devem fazer logoff novamente com a conta de trabalho ou de estudante (user@domain.com). O nome de usuário é o mesmo em ambos os ambientes. Quando você adiciona PHS ou PTA, o usuário tem a mesma senha para ambos os ambientes, mas terá que fornecer essas credenciais novamente ao fazer logor no Microsoft 365. A sincronização de diretórios com o PHS é a sincronização de diretório mais usada.

Para configurar a sincronização de diretórios, use o Azure AD Connect. Para obter instruções, confira Configurar a sincronização de diretórios para [o Microsoft 365](set-up-directory-synchronization.md) e [o Azure AD Connect com configurações expressas.](https://go.microsoft.com/fwlink/p/?LinkId=698537)

Saiba mais sobre [como se preparar para a sincronização de diretórios com o Microsoft 365.](prepare-for-directory-synchronization.md)

### <a name="directory-synchronization-with-sso"></a>Sincronização de diretório com SSO

Um usuário faz o login em seu ambiente local com sua conta de usuário. Quando eles vão para o Microsoft 365, eles estão conectados automaticamente ou fazem logoff usando as mesmas credenciais que usam para seu ambiente local (domínio /nome de usuário).

Para configurar o SSO, você também usa o Azure AD Connect. Para obter instruções, [confira Instalação personalizada do Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkID=698430)

Para obter mais informações, [consulte o single sign-on.](https://go.microsoft.com/fwlink/p/?LinkId=698604)

## <a name="azure-ad-connect"></a>Azure AD Connect

O Azure AD Connect substitui versões mais antigas das ferramentas de integração de identidade, como DirSync e Azure AD Sync. Se você quiser atualizar da Sincronização do Azure Active Directory para o Azure AD Connect, confira [as instruções de atualização.](https://go.microsoft.com/fwlink/p/?LinkId=733240) 

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
