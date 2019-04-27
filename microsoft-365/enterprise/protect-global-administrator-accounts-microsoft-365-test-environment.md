---
title: Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Use estas etapas para proteger contas de administrador global no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 86b2d325fc710fd8b387bc37cad5f8ea60df001d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353053"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise

Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível. Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.

Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:

1.  Criar o ambiente de teste do Microsoft 365 Enterprise.
2.  Proteger sua conta de administrador global dedicado.

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).

  
> [!NOTE]
> Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS). É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurar políticas de acesso condicional

Primeiro, crie uma nova conta de usuário como administrador global dedicado.

1. Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).
2. Em **usuários ativos**, clique em **Adicionar um usuário**.
3. Na página **novo usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.
4. Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte. Registre a senha dessa nova conta em um local seguro.
5. Clear **faça com que este usuário altere sua senha quando entrar pela primeira vez**.
6. Clique em **funções**e, em seguida, clique em **administrador global**.
7. Clique em **licenças de produto**e, em seguida, ative as licenças do **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** no.
8. Clique em **Adicionar**.
9. Na **página usuário foi adicionado**, desmarque **Enviar senha no email**e clique em **Fechar**.

Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.

1. Na guia **centro de administração do Microsoft 365** , clique no ícone de grupos na navegação à esquerda e, em seguida, clique em **grupos**.
2. Clique em **Adicionar um grupo**.
3. Na página **novo grupo** , digite **GlobalAdmins**.
4. Clique em **selecionar proprietário** clique em sua conta de administrador global e, em seguida, clique em **Adicionar > fechar**.
5. Na lista de grupos, clique no grupo **GlobalAdmins** .
6. Na página **GlobalAdmins** , clique em **Editar para membro**e, em seguida, clique em **adicionar membros**.
7. Na lista, clique na conta **DedicatedAdmin** e, em seguida, clique em **salvar _GT_ fechar > fechar o centro de administração do >**.

Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.

Essa primeira política requer que todas as contas de administrador global usem MFA.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com).
2. Clique em **Azure Active Directory > acesso condicional**.
3. Na folha **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.
4. Nas **políticas de linha de base...** lâmina, clique em **usar política imediatamente _GT_ salvar**.

Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.

1. Na folha **acesso condicional – políticas** , clique em **nova política**.
2. Na **nova** folha, digite **administradores globais** em **nome**.
3. Na seção **atribuições** , clique em **usuários e grupos**.
4. Na guia **incluir** da folha **usuários e grupos** , clique em **Selecionar usuários e grupos _GT_ usuários e grupos > selecionar**.
5. Na folha **selecionar** , clique em **GlobalAdmins _GT_ selecionar > concluído**.
6. Na seção **atribuições** , clique em **condições**.
7. Na folha **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.
8. Na seção **controles de acesso** da **nova** folha, clique em **conceder**.
9. Na folha **conceder** , clique em **bloquear acesso**e clique em **selecionar**.
10. Na **nova** folha, clique em **ativado** para **habilitar a política**e clique em **criar**.
11. Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .

Para testar a primeira política, saia e entre com a conta DedicatedAdmin. Você deve ser solicitado a configurar o MFA na conta de usuário. Isso demonstra que a primeira política está sendo aplicada.

Consulte a etapa [proteger contas de administrador global](identity-designate-protect-admin-accounts.md#identity-global-admin) na fase de identidade para obter informações e links para proteger suas contas de administrador global em produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
