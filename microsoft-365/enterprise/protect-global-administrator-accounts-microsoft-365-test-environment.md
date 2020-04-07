---
title: Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise
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
description: Use estas etapas para proteger contas de administrador global no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: e6b93e3888873b6d78fec1802d179ed9624ffa63
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153863"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise

*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*

Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível. Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.

Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:

1.  Criar o ambiente de teste do Microsoft 365 Enterprise.
2.  Proteger sua conta de administrador global dedicado.

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS). É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurar políticas de acesso condicional

Primeiro, crie uma nova conta de usuário como administrador global dedicado.

1. Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).
2. Clique em **usuários > usuários ativos**e, em seguida, clique em **Adicionar um usuário**.
3. No painel **Adicionar usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.
4. Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte. Registre a senha dessa nova conta em um local seguro.
5. Clique em **Avançar**.
6. No painel **atribuir licenças de produtos** , selecione **Microsoft 365 E5** ou **Office 365 E5**e clique em **Avançar**.
7. No painel **configurações opcionais** , clique em **funções**e selecione **acesso do centro de administração** e **administrador global**. Clique em **Avançar**.
8. No painel **você está quase concluído** , clique em **concluir adição**e, em seguida, clique em **Fechar**.

Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.

1. Na guia **centro de administração do Microsoft 365** , clique em **grupos** na navegação à esquerda e, em seguida, clique em **grupos**.
2. Clique em **Adicionar um grupo**.
3. No painel **escolher um tipo de grupo** , selecione **segurança**e clique em **Avançar**.
4. No painel **Configurar o básico** , clique em **Criar grupo**e, em seguida, clique em **Fechar**.
5. No painel **revisar e concluir a adição de grupo** , digite **GlobalAdmins**e clique em **Avançar**.
7. Na lista de grupos, clique no grupo **GlobalAdmins** .
8. No painel **GlobalAdmins** , clique em **Membros**e, em seguida, clique em **Exibir todos e gerenciar Membros**.
9. No painel **GlobalAdmins** , clique em **adicionar membros**, selecione a conta **DedicatedAdmin** e a conta de administrador global e clique em **salvar > fechar > fechar**.

Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.

Essa primeira política requer que todas as contas de administrador global usem MFA.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com).
2. Clique em **Azure Active Directory > segurança > acesso condicional**.
3. No painel **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.
4. No painel **diretiva de linha de base** , clique em **usar política imediatamente > salvar**.

Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.

1. No painel **acesso condicional – políticas** , clique em **nova política**.
2. No painel **novo** , digite **administradores globais** em **nome**.
3. Na seção **atribuições** , clique em **usuários e grupos**.
4. Na guia **incluir** do painel **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecionar**.
5. No painel **selecionar** , clique no grupo **GlobalAdmins** e, em seguida, clique em **selecionar > concluído**.
6. Na seção **atribuições** , clique em **condições**.
7. No painel **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.
8. Na seção **controles de acesso** do painel **novo** , clique em **conceder**.
9. No painel **conceder** , clique em **bloquear acesso**e, em seguida, clique em **selecionar**.
10. No painel **novo** , **clique em ativar** para **habilitar a política**e clique em **criar**.
11. Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .

Para testar a primeira política, saia e entre com a conta DedicatedAdmin. Você deve ser solicitado a configurar a MFA. Isso demonstra que a primeira política está sendo aplicada.

Consulte a etapa [proteger contas de administrador global](identity-create-protect-global-admins.md#identity-global-admin) na fase de identidade para obter informações e links para proteger suas contas de administrador global em produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
