---
title: Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o Azure AD Identity Protection e analise as contas atuais em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068488"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise

*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*

A proteção de identidade do Azure Active Directory (Azure AD) permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização, configurem respostas automatizadas e investigue incidentes. Este artigo descreve como usar a proteção de identidade do Azure AD para exibir a análise de suas contas de ambiente de teste.

Há duas fases para configurar a proteção de identidade do Azure AD no seu ambiente de teste do Microsoft 365 Enterprise:

1. Criar o ambiente de teste do Microsoft 365 Enterprise.
2. Usar a proteção de identidade do Azure AD.

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar a proteção de identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a proteção de identidade do Azure AD em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> O teste da proteção de identidade do Azure AD não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Azure AD e experimentá-lo em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: usar a proteção de identidade do Azure AD

1. Abra uma instância privada do navegador e entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do ambiente de teste do Microsoft 365 Enterprise.
2. No portal do Azure, digite **proteção de identidade** na caixa de pesquisa e clique em **proteção de identidade do Azure ad**.
3. Na folha **proteção de identidade – visão geral** , clique em cada um dos relatórios para ver o que estão subordinados.
4. Em **notificar**, clique em **usuários em risco detectados alertas**.
5. No painel **usuários em risco detectados** , selecione **médio**.
6. Para **emails são enviados para os usuários a seguir**, clique em **incluído** e verifique se sua conta de administrador global está na lista de membros selecionados.
7. Clique em **Salvar**.

Clique nas diferentes políticas em **proteger** para ver como configurá-las. Se você criar e ativar uma política, certifique-se de que ela não está bloqueando o acesso para um escopo de condições muito grande ou talvez você não consiga entrar, mesmo que o administrador global.

Para outros testes e experimentos, consulte [simulating Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Consulte a etapa [proteger contra o comprometimento de credenciais](identity-secure-user-sign-ins.md#identity-ident-prot) na fase de identidade para obter informações e links para implantar a proteção de identidade do Azure AD em produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
