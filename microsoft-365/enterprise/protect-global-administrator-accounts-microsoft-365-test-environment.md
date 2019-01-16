---
title: Proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise
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
description: Use estas etapas para proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 4d444e217c5a232811701f6519c2eb3ebe86df70
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864702"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise

Você pode evitar ataques digitais em sua organização, garantindo que suas contas de administrador mais seguras possível. Este artigo descreve como usar políticas de acesso condicional de segurança de aplicativo de nuvem do Office 365 e o Azure AD para proteger as contas de administrador global.

Há duas fases a proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:

1.  Crie o ambiente de teste do Microsoft 365 Enterprise.
2.  Protege a sua conta de administrador global dedicado.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando a conta de administrador global proteção não requer que o ambiente de teste simulado enterprise, que inclui uma intranet simulada conectado à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentar em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>Fase 2: Configurar a segurança de aplicativo de nuvem e políticas de acesso condicional

Primeiro, crie uma política de segurança de aplicativo de nuvem do Office 365 para monitorar a atividade da conta de administrador global e enviar alertas para o endereço de email da sua conta de administrador global. 

1. Entrar no portal do Office em [http://portal.office.com](http://portal.office.com) usando sua conta de administrador global.
2. Clique no lado do **Admin** . Na guia do **Centro de administração do Office** , clique em **centrais de Admin > segurança e conformidade**.
3. No painel de navegação à esquerda, clique em **alertas > Gerenciar avançadas alertas**.
4. Na página **Gerenciar alertas de avançadas** , clique em **Ativar de segurança de aplicativo de nuvem do Office 365**e, em seguida, clique em **Ir para segurança de aplicativo de nuvem do Office 365**.
5. Na guia nova **painel** , clique em **controle > políticas**.
6. Na página **política** , clique em **Criar política**e clique em **política de atividade**.
7. Em **nome da política**, digite **atividades administrativas**.
8. Em **Severidade da política**, clique em **Alta**.
9. Em **categoria**, clique em **contas privilegiadas**.
10. Em **criar filtros para a política**, em **atividades correspondência das ações a seguir**, clique em **atividades administrativas**.
11. Em **Alertas**, clique em **Enviar alerta como email**. Em **Para**, digite o endereço de email da conta de administrador global.
12. Na parte inferior da página, clique em **Criar**.
13. Feche a guia do **painel** .
    
Em seguida, crie uma nova conta de usuário como um administrador global dedicado.

1. Na guia do **Centro de administração do Office** , em **usuários ativos**, clique em **Adicionar um usuário**.
2. Na página **novo usuário** , digite **DedicatedAdmin** em **nome**, **nome para exibição**e **Username**.
3. Clique em **senha**, clique em **Deixe-me criar a senha**e, em seguida, digite uma senha forte. Registre a senha para esta nova conta em um local seguro.
4. Desmarque **tornar este usuário alterar suas senhas quando eles entrarem pela primeira vez**.
5. Clique em **funções**e, em seguida, clique em **Administrador Global**.
6. Clique em **licenças do produto**e ative o **Mobility Enterprise + E5 de segurança** e **licenças do Office 365 Enterprise E5** .
7. Clique em **Adicionar**.
8. Em que o **usuário foi adicionado a página**, desmarque **Enviar senha em email**e clique em **Fechar**.

Em seguida, criar um novo grupo chamado GlobalAdmins e adicione a conta de DedicatedAdmin a ela.

1. Na guia do **Centro de administração do Office** , clique no ícone de grupos no painel de navegação esquerdo e, em seguida, clique em **grupos**.
2. Clique em **Adicionar um grupo**.
3. Na página **Novo grupo** , digite **GlobalAdmins**.
4. Clique em click **proprietário selecione** sua conta de administrador global e, em seguida, clique em **Adicionar > fechar**.
5. Na lista de grupos, clique no grupo de **GlobalAdmins** .
6. Na página **GlobalAdmins** , clique em **Editar para membro**e, em seguida, clique em **Adicionar membros**.
7. Na lista, clique na conta de **DedicatedAdmin** e, em seguida, clique em **Salvar > fechar > fechar > Centro de administração**.

Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e negar autenticação, se o risco de entrada for média ou alta.

Essa diretiva primeira requer que todas as contas de administrador global usam MFA.

1. Em uma nova guia do seu navegador, vá para [https://portal.azure.com](https://portal.azure.com).
2. Clique em **Azure Active Directory > acesso condicional**.
3. No blade **acesso condicional – políticas** , clique em **diretiva base: exigem MFA para os administradores (preview)**.
4. No blade **… políticas de linha de base** , clique em **usar imediatamente a política > Salvar**.

Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é a média ou alta.

1. No blade **acesso condicional – políticas** , clique em **nova diretiva**.
2. No blade **New** , digite **administradores globais** no **nome**.
3. Na seção de **atribuições** , clique em **usuários e grupos**.
4. Na guia **incluir** do blade **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecione**.
5. No blade **Selecionar** , clique no **GlobalAdmins > selecione > feito**.
6. Na seção de **atribuições** , clique em **condições**.
7. No blade **condições** , clique em **entrar risco**, clique em **Sim** para **Configurar**, clique em **alta** e **Médio**e, em seguida, clique em **Selecionar** e **feito**.
8. Na seção de **acessar os controles** do blade **novo** , clique em **conceder**.
9. No blade **Grant** , clique em **Bloquear acesso**e clique em **Selecionar**.
10. No blade **novo** , clique **em** para **Ativar a política**e clique em **criar**.
11. Feche as guias **portal Azure** e o **Centro de administração do Office** .

Para testar a primeira diretiva, sair e entrar com a conta DedicatedAdmin. Você deve ser solicitado para configurar MFA na conta de usuário. Isso demonstra que a primeira diretiva está sendo aplicada.

Consulte a etapa de [proteger contas de administrador global](identity-designate-protect-admin-accounts.md) na fase de identidade para obter informações e links para proteger suas contas de administrador global na produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
