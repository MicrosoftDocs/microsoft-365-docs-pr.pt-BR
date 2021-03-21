---
title: Proteger contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Use estas etapas para proteger contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918877"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteger contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Você pode impedir ataques digitais em sua organização garantindo que suas contas de administrador sejam o mais seguras possível. 

Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.

A proteção de contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas envolve duas fases:
- [Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar políticas de acesso condicional](#phase-2-configure-conditional-access-policies)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar a proteção de conta de administrador global em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a proteção de conta de administrador global não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um AD DS (Serviços de Domínio do Active Directory). Ele é fornecido aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: Configurar políticas de acesso condicional

Primeiro, crie uma nova conta de usuário como um administrador global dedicado.

1. Em uma guia separada, abra o Centro de administração [do Microsoft 365](https://admin.microsoft.com/).
2. Selecione **Usuários**  >  **Usuários ativos** e selecione Adicionar um **usuário**.
3. No painel **Adicionar usuário,** insira **DedicatedAdmin** nas caixas **Nome,** **Nome** de exibição e Nome **de** Usuário.
4. Selecione **Senha**, selecione **Deixe-me criar** a senha e insira uma senha forte. Grave a senha dessa nova conta em um local seguro.
5. Selecione **Avançar**.
6. No painel **Atribuir licenças de** produto, selecione **Microsoft 365 E5** e selecione **Próximo**.
7. No painel **Configurações opcionais,** selecione **Funções**  >  **O Centro de administração acessa o** administrador  >  **global**  >  **Next**.
8. No painel **Você está quase pronto,** selecione **Concluir** a adição e, em seguida, selecione **Fechar**.

Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ela.

1. Na guia Centro de administração do **Microsoft 365,** selecione **Grupos** na navegação à esquerda e selecione **Grupos**.
2. Selecione **Adicionar um grupo**.
3. No painel **Escolher um tipo de** grupo, selecione **Segurança** e, em seguida, selecione **Próximo**.
4. No painel **Configurar as noções básicas,** selecione **Criar grupo** e selecione **Fechar**.
5. No painel **Revisar e concluir a adição de** grupo, insira **GlobalAdmins** e selecione **Next**.
7. Na lista de grupos, selecione o **grupo GlobalAdmins.**
8. No painel **GlobalAdmins,** selecione **Membros** e selecione **Exibir todos e gerenciar membros**.
9. No painel **GlobalAdmins,** selecione **Adicionar** membros, selecione a conta **DedicatedAdmin** e sua conta de administrador global e selecione **Salvar**  >  **Fechar**  >  **Fechar**.

Em seguida, crie políticas de acesso condicional para exigir autenticação multifacional para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.

Esta primeira política exige que todas as contas de administrador global usem MFA.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .
2. Clique em Acesso Condicional de Segurança do **Azure Active**  >    >  Directory.
3. No painel **Acesso condicional – Políticas,** selecione Política de linha de **base: Exigir MFA para administradores (visualização)**.
4. No painel **Política de** Linha de Base, selecione Usar política imediatamente **> Salvar**.

Esta segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.

1. No painel **Acesso Condicional – Políticas,** selecione **Nova política**.
2. No **novo** painel, insira **Administradores globais** em **Nome**.
3. Na seção **Atribuições,** selecione **Usuários e grupos**.
4. Na guia **Incluir** do painel **Usuários e** grupos, selecione Selecionar usuários **e grupos** Usuários e  >  **grupos**  >  **Selecione**.
5. No painel **Selecionar,** selecione o **grupo GlobalAdmins** e selecione **Selecionar**  >  **Feito**.
6. Na seção **Atribuições,** selecione **Condições**.
7. No painel **Condições,** selecione **Risco** de entrar, selecione **Sim** para **Configurar,** **selecione** Alto e Médio **e** selecione **Selecionar** e **Feito**.
8. Na seção **Controles de** acesso do **painel Novo,** selecione **Conceder**.
9. No painel **Conceder,** selecione **Bloquear acesso** e selecione **Selecionar**.
10. No painel **Novo,** selecione **Ativar para** **Habilitar política** e selecione **Criar**.
11. Feche as **guias do portal do Azure** e do Centro de administração do Microsoft **365.**

Para testar a primeira política, saia e entre com a conta DedicatedAdmin. Você deve ser solicitado a configurar o MFA. Isso demonstra que a primeira política está sendo aplicada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)