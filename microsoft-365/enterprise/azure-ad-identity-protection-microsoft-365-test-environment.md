---
title: Proteção de Identidade do Azure AD para seu ambiente de teste do Microsoft 365 para empresas
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
description: Configure a Proteção de Identidade do Azure AD e analise as contas atuais em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905339"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Proteção de Identidade do Azure AD para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Você pode usar a Proteção de Identidade do Azure Active Directory (Azure AD) para detectar possíveis vulnerabilidades que afetam as identidades da sua organização, configurar respostas automatizadas e investigar incidentes. Este artigo descreve como usar a Proteção de Identidade do Azure AD para exibir a análise de suas contas de ambiente de teste.

Configurar a Proteção de Identidade do Azure AD em seu ambiente de teste do Microsoft 365 para empresas envolve duas fases:

- [Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Usar a Proteção de Identidade do Azure AD](#phase-2-use-azure-ad-identity-protection)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser apenas testar a Proteção de Identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar a Proteção de Identidade do Azure AD em uma empresa simulada, siga as instruções em [Autenticação passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Testar a Proteção de Identidade do Azure AD não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar a Proteção de Identidade do Azure AD e experimentá-la em um ambiente que representa uma organização típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Usar a Proteção de Identidade do Azure AD

1. Abra uma instância privada do navegador e entre no portal do Azure em com a conta de administrador global do seu ambiente de teste [https://portal.azure.com](https://portal.azure.com) do Microsoft 365 para empresas.
2. No portal do Azure, digite **proteção de** identidade na caixa de pesquisa e selecione Proteção de Identidade do **Azure AD**.
3. Na folha **Proteção de Identidade - Visão** geral, selecione cada relatório para ver o que ele está relatando.
4. Em **Notificar**, selecione **Usuários em risco detectados alertas**.
5. No painel **Usuários em risco detectados alertas,** selecione **Médio**.
6. Para **Emails são enviados para os seguintes usuários**, selecione **Incluído** e verifique se sua conta de administrador global está na lista de membros selecionados.
7. Selecione **Salvar**.

Em **Proteger**, selecione várias polícias para ver como configurá-las. Se você criar e ativar uma política, certifique-se de que ela não está bloqueando o acesso para todos os usuários, ou talvez você não consiga entrar. Para evitar isso, exclua contas de usuário específicas, como administradores globais.

Para mais testes e experimentações, consulte [Simulando eventos de risco](/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)