---
title: Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 for Enterprise
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
description: Configure o Azure AD Identity Protection e analise as contas atuais no ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487703"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Você pode usar a proteção de identidade do Azure Active Directory (Azure AD) para detectar possíveis vulnerabilidades que afetam as identidades da sua organização, configurar respostas automatizadas e investigar incidentes. Este artigo descreve como usar a proteção de identidade do Azure AD para exibir a análise de suas contas de ambiente de teste.

A configuração da proteção de identidade do Azure AD no seu ambiente de teste do Microsoft 365 for Enterprise envolve duas fases:

- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: usar a proteção de identidade do Azure AD](#phase-2-use-azure-ad-identity-protection)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você quiser testar apenas a proteção de identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a proteção de identidade do Azure AD em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> O teste da proteção de identidade do Azure AD não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Azure AD e experimentá-lo em um ambiente que representa uma organização típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: usar a proteção de identidade do Azure AD

1. Abra uma instância privada do navegador e entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do seu ambiente de teste do Microsoft 365 for Enterprise.
2. No portal do Azure, digite **proteção de identidade** na caixa de pesquisa e selecione **proteção de identidade do Azure ad**.
3. Na folha **proteção de identidade – visão geral** , selecione cada relatório para ver o que está subordinado.
4. Em **notificar**, selecione **usuários em risco detectados alertas**.
5. No painel **usuários em risco detectados** , selecione **médio**.
6. Para **emails são enviados para os usuários a seguir**, selecione **incluídos** e verifique se sua conta de administrador global está na lista de membros selecionados.
7. Selecione **Salvar**.

Em **proteger**, selecione várias políticas para ver como configurá-las. Se você criar e ativar uma política, certifique-se de que ela não esteja bloqueando o acesso de todos os usuários ou que você não consiga entrar. Para evitar isso, exclua contas de usuário específicas, como administradores globais.

Para outros testes e experimentos, consulte [simulating Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
