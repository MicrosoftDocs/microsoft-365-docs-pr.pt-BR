---
title: Ambiente de teste de proteção de identidade AD Azure para a sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurar a proteção de identidade do Windows Azure AD e analisar as contas atuais em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864763"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente de teste de proteção de identidade AD Azure para a sua empresa de 365 da Microsoft

Proteção de identidade AD Azure permite detectar possíveis vulnerabilidades afetar identidades da sua organização, configurar respostas automatizadas e investigar incidentes. Este artigo descreve como habilitar a proteção de identidade do Windows Azure AD e exibir a análise de suas contas do ambiente de teste.

Há duas fases à configuração de proteção de identidade do Windows Azure AD no seu ambiente de teste do Microsoft 365 Enterprise:

1. Crie o ambiente de teste do Microsoft 365 Enterprise.
2. Habilitar e usar a proteção de identidade do Windows Azure AD.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja testar a proteção de identidade do Windows Azure AD de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja testar a proteção de identidade do Windows Azure AD em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando a proteção de identidade do Windows Azure AD não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Windows Azure AD e experimentar em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Fase 2: Habilitar e usar a proteção de identidade do Windows Azure AD

1. Abra uma instância particular do navegador e acesse o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do seu ambiente de teste do Microsoft 365 Enterprise.
2. No portal do Azure, clique em **todos os serviços > Marketplace**.
3. Digite **proteção de identidade do Windows Azure AD** e, em seguida, clique nele.
4. No blade **Introdução** , clique em **Onboard** em **configurações**, clique em **Fixar no painel**e, em seguida, clique em **criar**.
5. No portal do Azure, clique em **proteção de identidade do Windows Azure AD** , no painel. 

   Você deverá ver um blade **Azure AD proteção-visão geral da identidade** com um painel. Sob **vulnerabilidades**, observe que ele determinado o número de contas de usuário sem registro a autenticação multifator. Esse número variará com base no anterior Microsoft 365 Enterprise Test Lab Guides que você fez.

6. Clique nas categorias para **investigar** ver se há qualquer usuários ou os eventos que foram detectados.

Para outros testes e experimentação, consulte [Simulating eventos de risco](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Consulte a etapa de [proteger contra credencial comprometer](identity-azure-ad-identity-protection.md) na fase de identidade para obter informações e links para implantar a proteção de identidade do Windows Azure AD na produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
