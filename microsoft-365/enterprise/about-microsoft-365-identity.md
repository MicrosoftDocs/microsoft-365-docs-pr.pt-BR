---
title: Microsoft 365 e modelos de identidade Azure Active Directory
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
description: Saiba como gerenciar o serviço de identidade do usuário do Azure AD Microsoft 365 usando modelos de identidade híbrida ou somente na nuvem.
ms.openlocfilehash: 93a37f39a4d96d7c2e434ed6edf4df588e672a0f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228490"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 e modelos de identidade Azure Active Directory

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Microsoft 365 usa Azure Active Directory (Azure AD), um serviço de autenticação e identidade de usuário baseado em nuvem que está incluído na sua assinatura do Microsoft 365, para gerenciar identidades e autenticação para Microsoft 365. A configuração correta da infraestrutura de identidade é fundamental para gerenciar Microsoft 365 acesso e permissões do usuário para sua organização.

Antes de começar, assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Sua primeira opção de planejamento é o Microsoft 365 de identidade.

## <a name="microsoft-365-identity-models"></a>Microsoft 365 de identidade

Para planejar contas de usuário, primeiro você precisa entender os dois modelos de identidade no Microsoft 365. Você pode manter as identidades da sua organização somente na nuvem ou pode manter suas identidades locais dos Serviços de Domínio do Active Directory (AD DS) e usá-las para autenticação quando os usuários acessarem Microsoft 365 serviços de nuvem.

Aqui estão os dois tipos de identidade e seus melhores benefícios e ajuste.

| Atributo | Identidade somente na nuvem | Identidade híbrida |
|:-------|:-----|:-----|
| **Definição** | A conta de usuário só existe no locatário do Azure AD para sua Microsoft 365 assinatura. | A conta de usuário existe no AD DS e uma cópia também está no locatário do Azure AD para sua Microsoft 365 assinatura. A conta de usuário no Azure AD também pode incluir uma versão com hashed da senha de conta de usuário do AD DS já com hashed. |
| **Como Microsoft 365 autentica credenciais de usuário** | O locatário do Azure AD para sua assinatura Microsoft 365 executa a autenticação com a conta de identidade na nuvem. | O locatário do Azure AD para sua assinatura Microsoft 365 lida com o processo de autenticação ou redireciona o usuário para outro provedor de identidade. |
| **Melhor para** | Organizações que não têm ou precisam de um AD DS local. | Organizações que usam o AD DS ou outro provedor de identidade. |
| **Maior benefício** | Simples de usar. Nenhuma ferramenta de diretório adicional ou servidores necessários. | Os usuários podem usar as mesmas credenciais ao acessar recursos locais ou baseados em nuvem. |
||||

## <a name="cloud-only-identity"></a>Identidade somente na nuvem

Uma identidade somente na nuvem usa contas de usuário que existem somente no Azure AD. A identidade somente na nuvem é geralmente usada por pequenas organizações que não têm servidores locais ou não usam o AD DS para gerenciar identidades locais.

Aqui estão os componentes básicos da identidade somente na nuvem.

![Componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

Usuários locais e remotos (online) usam suas contas de usuário e senhas do Azure AD para acessar Microsoft 365 de nuvem. O Azure AD autentica credenciais de usuário com base em suas contas de usuário e senhas armazenadas.

### <a name="administration"></a>Administração
Como as contas de usuário são armazenadas apenas no Azure AD, você gerencia identidades de nuvem com ferramentas como o Centro de administração do Microsoft 365 [e](../admin/add-users/index.yml) [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).

## <a name="hybrid-identity"></a>Identidade híbrida

A identidade híbrida usa contas que se originam em um AD DS local e têm uma cópia no locatário do Azure AD de uma assinatura Microsoft 365 local. No entanto, a maioria das alterações só flui de uma maneira. As alterações feitas nas contas de usuário do AD DS são sincronizadas com a cópia no Azure AD. Mas as alterações feitas em contas baseadas em nuvem no Azure AD, como novas contas de usuário, não são sincronizadas com o AD DS.

O Azure AD Conexão fornece a sincronização de conta em andamento. Ele é executado em um servidor local, verifica se há alterações no AD DS e encaminha essas alterações para o Azure AD. O Azure AD Conexão a capacidade de filtrar quais contas são sincronizadas e se sincronizar uma versão com hash de senhas de usuário, conhecida como sincronização de hash de senha (PHS).

Quando você implementa a identidade híbrida, seu AD DS local é a fonte autoritativa para informações da conta. Isso significa que você executa tarefas de administração principalmente locais, que são sincronizadas com o Azure AD.

Aqui estão os componentes da identidade híbrida.

![Componentes da identidade híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

O locatário do Azure AD tem uma cópia das contas do AD DS. Nesta configuração, usuários locais e remotos acessando Microsoft 365 serviços de nuvem autenticados no Azure AD.

> [!NOTE]
> Você sempre precisa usar o Azure AD Conexão sincronizar contas de usuário para identidade híbrida. Você precisa das contas de usuário sincronizadas no Azure AD para executar a atribuição de licença e gerenciamento de grupo, configurar permissões e outras tarefas administrativas que envolvam contas de usuário.

### <a name="administration"></a>Administração

Como as contas de usuário originais e autoritativas são armazenadas no AD DS local, você gerencia suas identidades com as mesmas ferramentas que gerencia seu AD DS.

Você não usa o Centro de administração do Microsoft 365 ou o PowerShell para Microsoft 365 gerenciar contas de usuário sincronizadas no Azure AD.

## <a name="next-step"></a>Próxima etapa

Se você precisar do modelo de identidade somente na nuvem, consulte [Cloud-only identity](cloud-only-identities.md).

Se você precisar do modelo de identidade híbrida, consulte [Identidade híbrida](plan-for-directory-synchronization.md).

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
