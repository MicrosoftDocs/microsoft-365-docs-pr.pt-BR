---
title: Proteger contas de administradores globais no seu ambiente de teste do Microsoft 365 for Enterprise
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
description: Use estas etapas para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487631"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteger contas de administradores globais no seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível. 

Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.

A proteção de contas de administrador global no seu ambiente de teste do Microsoft 365 for Enterprise envolve duas fases:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurar políticas de acesso condicional](#phase-2-configure-conditional-access-policies)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS). É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurar políticas de acesso condicional

Primeiro, crie uma nova conta de usuário como administrador global dedicado.

1. Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).
2. Selecione **usuários**  >  **ativos**do usuário e, em seguida, selecione **Adicionar um usuário**.
3. No painel **Adicionar usuário** , digite **DedicatedAdmin** nas caixas **nome**, nome para **exibição**e nome de **usuário** .
4. Selecione **senha**, selecione **deixe-me criar a senha**e, em seguida, digite uma senha forte. Registre a senha dessa nova conta em um local seguro.
5. Selecione **Avançar**.
6. No painel **atribuir licenças de produtos** , selecione **Microsoft 365 E5**e, em seguida, selecione **Avançar**.
7. No painel **configurações opcionais** , selecione o centro de administração de **funções**de  >  **Admin center access**  >  **administrador global**  >  **próximo**.
8. No painel **você está quase concluído** , selecione **concluir adição**e, em seguida, selecione **Fechar**.

Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.

1. Na guia **centro de administração do Microsoft 365** , selecione **grupos** na navegação à esquerda e, em seguida, selecione **grupos**.
2. Selecione **Adicionar um grupo**.
3. No painel **escolher um tipo de grupo** , selecione **segurança**e, em seguida, selecione **Avançar**.
4. No painel **Configurar o básico** , selecione **Criar grupo**e, em seguida, selecione **Fechar**.
5. No painel **revisar e concluir a adição de grupo** , insira **GlobalAdmins**e, em seguida, selecione **Avançar**.
7. Na lista de grupos, selecione o grupo **GlobalAdmins** .
8. No painel **GlobalAdmins** , selecione **Membros**e, em seguida, selecione **Exibir todos e gerenciar Membros**.
9. No painel **GlobalAdmins** , selecione **adicionar membros**, selecione a conta **DedicatedAdmin** e sua conta de administrador global e selecione salvar fechar **Save**  >  **Close**  >  **fechar**.

Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.

Essa primeira política requer que todas as contas de administrador global usem MFA.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .
2. Clique em acesso condicional de segurança **do Azure Active Directory**  >  **Security**  >  **Conditional Access**.
3. No painel **acesso condicional – políticas** , selecione **política de linha de base: exigir MFA para administradores (visualização)**.
4. No painel **política de linha de base** , selecione **usar política imediatamente > salvar**.

Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.

1. No painel **acesso condicional – políticas** , selecione **nova política**.
2. No painel **novo** , insira **administradores globais** em **nome**.
3. Na seção **atribuições** , selecione **usuários e grupos**.
4. Na guia **incluir** do painel **usuários e grupos** , selecione Selecionar **usuários e grupos**  >  **usuários e grupos**  >  **selecionar**.
5. No painel **selecionar** , selecione o grupo **GlobalAdmins** **e selecione**  >  **concluído**.
6. Na seção **atribuições** , selecione **condições**.
7. No painel **condições** , selecione **risco de entrada**, selecione **Sim** para **Configurar**, selecione **alta** e **média**e, em seguida, selecione **selecionar** e **concluir**.
8. Na seção **controles de acesso** do painel **novo** , selecione **conceder**.
9. No painel **conceder** , selecione **bloquear acesso**e selecione **selecionar**.
10. No painel **novo** , selecione **Ativar** para **habilitar política**e, em seguida, selecione **criar**.
11. Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .

Para testar a primeira política, saia e entre com a conta DedicatedAdmin. Você deve ser solicitado a configurar a MFA. Isso demonstra que a primeira política está sendo aplicada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
