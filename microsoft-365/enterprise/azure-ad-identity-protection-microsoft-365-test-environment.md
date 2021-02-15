---
title: Azure AD Identity Protection para seu ambiente de teste do Microsoft 365 para empresas
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
description: Configure o Azure AD Identity Protection e analise as contas atuais em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487703"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Você pode usar a Proteção de Identidade do Azure Active Directory (Azure AD) para detectar possíveis vulnerabilidades que afetam as identidades da sua organização, configurar respostas automatizadas e investigar incidentes. Este artigo descreve como usar o Azure AD Identity Protection para exibir a análise de suas contas de ambiente de teste.

Configurar o Azure AD Identity Protection no ambiente de teste do Microsoft 365 para empresas envolve duas fases:

- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Usar o Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser testar apenas o Azure AD Identity Protection de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar o Azure AD Identity Protection em uma empresa simulada, siga as instruções na autenticação [de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste do Azure AD Identity Protection não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar o Azure AD Identity Protection e experimentá-lo em um ambiente que representa uma organização típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Usar o Azure AD Identity Protection

1. Abra uma instância privada do navegador e entre no portal do Azure com a conta de administrador global do seu ambiente de teste do [https://portal.azure.com](https://portal.azure.com) Microsoft 365 para empresas.
2. No portal do Azure, digite **a proteção de** identidade na caixa de pesquisa e selecione **Azure AD Identity Protection.**
3. Na folha **Proteção de Identidade - Visão** geral, selecione cada relatório para ver o que está relatando.
4. Em **Notificar,** **selecione Usuários em risco alertas detectados.**
5. No painel **Usuários em risco detectado alertas,** selecione **Médio**.
6. For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.
7. Selecione **Salvar**.

Em **Proteger,** selecione várias polícias para ver como configurá-las. Se você criar e ativar uma política, certifique-se de que ela não está bloqueando o acesso de todos os usuários ou talvez não consiga entrar. Para evitar isso, exclua contas de usuário específicas, como administradores globais.

Para mais testes e experimentação, consulte [Simulando eventos de risco.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Mapa de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
