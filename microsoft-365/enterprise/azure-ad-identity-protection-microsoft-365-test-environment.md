---
title: Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o Azure AD Identity Protection e analise as contas atuais em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673237"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise

*Este guia de laboratório de teste só pode ser usado para ambientes de teste do Microsoft 365 Enterprise.*

O Azure AD Identity Protection permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização, configure respostas automatizadas e investigue incidentes. Este artigo descreve como habilitar a proteção de identidade do Azure AD e exibir a análise de suas contas de ambiente de teste.

Há duas fases para configurar a proteção de identidade do Azure AD no seu ambiente de teste do Microsoft 365 Enterprise:

1. Criar o ambiente de teste do Microsoft 365 Enterprise.
2. Habilitar e usar a proteção de identidade do Azure AD.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar a proteção de identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a proteção de identidade do Azure AD em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> O teste da proteção de identidade do Azure AD não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Azure AD e experimentá-lo em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Fase 2: habilitar e usar a proteção de identidade do Azure AD

1. Abra uma instância privada do navegador e entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do ambiente de teste do Microsoft 365 Enterprise.
2. No portal do Azure, clique em **todos os serviços > Marketplace**.
3. Digite **proteção de identidade do Azure ad** e clique nele.
4. Na folha **introdução** , clique em em **configurações** **, clique em** **fixar no painel**e clique em **criar**.
5. No portal do Azure, clique em **proteção de identidade do Azure ad** no painel. 

   Você deve ver uma lâmina **do Azure ad Identity Protection-visão geral** com um painel. Em **vulnerabilidades**, observe que ela determinou o número de contas de usuário sem registro de autenticação multifator. Esse número varia de acordo com os guias anteriores do laboratório de teste do Microsoft 365 Enterprise que você fez.

6. Clique nas categorias para **investigar** para ver se há usuários ou eventos detectados.

Para outros testes e experimentos, consulte [simulating Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Consulte a etapa [proteger contra o comprometimento de credenciais](identity-secure-user-sign-ins.md#identity-ident-prot) na fase de identidade para obter informações e links para implantar a proteção de identidade do Azure AD em produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
