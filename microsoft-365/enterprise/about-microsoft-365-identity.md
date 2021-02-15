---
title: Modelos de identidade do Microsoft 365 e Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Saiba como gerenciar o serviço de identidade de usuário do Azure AD no Microsoft 365 usando modelos de identidade híbrida ou somente na nuvem.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327946"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Modelos de identidade do Microsoft 365 e Azure Active Directory

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft 365 usa o Azure Active Directory (Azure AD), um serviço de autenticação e identidade de usuário baseado em nuvem que está incluído na sua assinatura do Microsoft 365 para gerenciar identidades e autenticação do Microsoft 365. Configurar a infraestrutura de identidade corretamente é essencial para gerenciar o acesso e as permissões de usuário do Microsoft 365 para sua organização.

Antes de começar, assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Sua primeira opção de planejamento é o modelo de identidade do Microsoft 365.

## <a name="microsoft-365-identity-models"></a>Modelos de identidade do Microsoft 365

Para planejar contas de usuário, primeiro você precisa entender os dois modelos de identidade no Microsoft 365. Você pode manter as identidades da sua organização somente na nuvem ou manter suas identidades locais do AD DS (Serviços de Domínio Active Directory) e usá-las para autenticação quando os usuários acessarem os serviços de nuvem do Microsoft 365.  

Aqui estão os dois tipos de identidade e seu melhor ajuste e benefícios.

| Atributo | Identidade somente na nuvem | Identidade híbrida |
|:-------|:-----|:-----|
| **Definição** | A conta de usuário existe apenas no locatário do Azure AD para sua assinatura do Microsoft 365. | A conta de usuário existe no AD DS e uma cópia também está no locatário do Azure AD para sua assinatura do Microsoft 365. A conta de usuário no Azure AD também pode incluir uma versão com hashed da senha da conta de usuário do AD DS já com hashed. |
| **Como o Microsoft 365 autentica as credenciais do usuário** | O locatário do Azure AD para sua assinatura do Microsoft 365 executa a autenticação com a conta de identidade na nuvem. | O locatário do Azure AD para sua assinatura do Microsoft 365 lida com o processo de autenticação ou redireciona o usuário para outro provedor de identidade. |
| **Melhor para** | Organizações que não têm ou precisam de um AD DS local. | Organizações que usam o AD DS ou outro provedor de identidade. |
| **Maior benefício** | Simples de usar. Nenhum servidor ou ferramentas de diretório adicional é necessário. | Os usuários podem usar as mesmas credenciais ao acessar recursos locais ou baseados em nuvem. |
||||

## <a name="cloud-only-identity"></a>Identidade somente na nuvem

Uma identidade somente na nuvem usa contas de usuário que existem somente no Azure AD. A identidade somente na nuvem é normalmente usada por pequenas organizações que não têm servidores locais ou não usam o AD DS para gerenciar identidades locais. 

Aqui estão os componentes básicos da identidade somente na nuvem.
 
![Componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

Os usuários locais e remotos (online) usam suas contas de usuário e senhas do Azure AD para acessar os serviços de nuvem do Microsoft 365. O Azure AD autentica credenciais de usuário com base em suas contas de usuário e senhas armazenadas.

### <a name="administration"></a>Administração
Como as contas de usuário só são armazenadas no Azure AD, você gerencia identidades de nuvem com ferramentas como o Centro de administração do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/) e [o Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md) 

## <a name="hybrid-identity"></a>Identidade híbrida

A identidade híbrida usa contas originadas em um AD DS local e têm uma cópia no locatário do Azure AD de uma assinatura do Microsoft 365. No entanto, a maioria das alterações só flui de uma maneira. As alterações feitas nas contas de usuário do AD DS são sincronizadas com sua cópia no Azure AD. Mas as alterações feitas em contas baseadas em nuvem no Azure AD, como novas contas de usuário, não são sincronizadas com o AD DS.

O Azure AD Connect fornece a sincronização de conta em andamento. Ele é executado em um servidor local, verifica se há alterações no AD DS e encaminha essas alterações para o Azure AD. O Azure AD Connect oferece a capacidade de filtrar quais contas são sincronizadas e se sincronizar uma versão com hash de senhas de usuário, conhecida como sincronização de hash de senha (PHS).

Quando você implementa a identidade híbrida, o AD DS local é a fonte autoritativa para informações da conta. Isso significa que você executa tarefas de administração principalmente no local, que são sincronizadas com o Azure AD. 

Aqui estão os componentes da identidade híbrida.

![Componentes da identidade híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

O locatário do Azure AD tem uma cópia das contas do AD DS. Nessa configuração, os usuários locais e remotos que acessam os serviços de nuvem do Microsoft 365 são autenticados no Azure AD.

>[!Note]
>Você sempre precisa usar o Azure AD Connect para sincronizar contas de usuário para identidade híbrida. Você precisa das contas de usuário sincronizadas no Azure AD para executar a atribuição de licença e o gerenciamento de grupo, configurar permissões e outras tarefas administrativas que envolvam contas de usuário.
>

### <a name="administration"></a>Administração

Como as contas de usuário originais e autoritativas são armazenadas no AD DS local, você gerencia suas identidades com as mesmas ferramentas que gerencia seu AD DS. 

Você não usa o Centro de administração do Microsoft 365 ou o PowerShell para Microsoft 365 para gerenciar contas de usuário sincronizadas no Azure AD.

## <a name="next-step"></a>Próxima etapa

Se você precisar do modelo de identidade somente na nuvem, consulte [Identidade somente na nuvem.](cloud-only-identities.md)

Se você precisar do modelo de identidade híbrida, consulte [Identidade híbrida.](plan-for-directory-synchronization.md)


## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
