---
title: Proteger contas de administrador global no ambiente de teste do Microsoft 365 para empresas
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
description: Use estas etapas para proteger as contas de administrador global no ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487631"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteger contas de administrador global no ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Você pode evitar ataques digitais à sua organização garantindo que suas contas de administrador sejam o mais seguras possível. 

Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administradores globais.

A proteção de contas de administrador global no ambiente de teste do Microsoft 365 para empresas envolve duas fases:
- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar políticas de acesso condicional](#phase-2-configure-conditional-access-policies)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser testar a proteção da conta de administrador global de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções na [autenticação de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste da proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: Configurar políticas de acesso condicional

Primeiro, crie uma nova conta de usuário como um administrador global dedicado.

1. Em uma guia separada, abra o Centro [de administração do Microsoft 365.](https://admin.microsoft.com/)
2. Selecione **Usuários**  >  **Ativos e,** em seguida, **adicione um usuário.**
3. In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.
4. Selecione **Senha,** selecione **Permitir que eu crie** a senha e insira uma senha forte. Grave a senha dessa nova conta em um local seguro.
5. Selecione **Avançar**.
6. No painel **Atribuir licenças de** produto, selecione **Microsoft 365 E5** e, em seguida, selecione **Próximo**.
7. No painel **Configurações opcionais,** selecione **Roles**  >  **Admin center access** Global  >  **admin**  >  **Next**.
8. No painel **Você está quase pronto,** selecione **Concluir** a adição e, em seguida, selecione **Fechar**.

Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.

1. Na guia centro de administração do **Microsoft 365,** selecione **Grupos** na navegação à esquerda e selecione **Grupos.**
2. Selecione **Adicionar um grupo.**
3. In the **Choose a group type** pane, select **Security**, and then select **Next**.
4. In the **Set up the basics** pane, select **Create group**, and then select **Close**.
5. In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.
7. Na lista de grupos, selecione o **grupo GlobalAdmins.**
8. No painel **GlobalAdmins,** selecione **Membros** e selecione **Exibir tudo e gerenciar membros.**
9. No painel **GlobalAdmins,** selecione Adicionar **membros,** selecione a conta **DedicatedAdmin** e sua conta de administrador global e, em seguida, selecione **Salvar**  >    >  **Fechar Fechar.**

Em seguida, crie políticas de acesso condicional para exigir a autenticação multifacional para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.

Esta primeira política exige que todas as contas de administrador global usem a MFA.

1. Em uma nova guia do navegador, vá [https://portal.azure.com](https://portal.azure.com) para.
2. Clique em Acesso Condicional de Segurança do **Azure Active**  >    >  Directory.
3. No painel **Acesso condicional – Políticas,** selecione Política de linha de **base: Exigir MFA para administradores (visualização).**
4. No painel **de política de** linha de base, selecione Usar política imediatamente > **Salvar.**

Esta segunda política bloqueia o acesso à autenticação da conta de administrador global quando o risco de entrada é médio ou alto.

1. No painel **Acesso condicional – Políticas,** selecione **Nova política.**
2. In the **New** pane, enter **Global administrators** in **Name**.
3. Na seção **Atribuições,** selecione **Usuários e grupos.**
4. On the **Include** tab of the **Users and groups** pane, select Select users and **groups** Users  >  **and groups**  >  **Select**.
5. No painel **Selecionar,** selecione o grupo **GlobalAdmins** e selecione **Selecionar**  >  **Feito.**
6. Na seção **Atribuições,** selecione **Condições.**
7. In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.
8. Na seção **Controles de** acesso do **novo** painel, selecione **Conceder**.
9. No painel **Conceder,** selecione **Bloquear acesso** e selecione **Selecionar.**
10. No painel **Novo,** selecione Ativado **para** **Habilitar política** e, em seguida, selecione **Criar**.
11. Feche o **portal do Azure e** as guias do Centro de administração do Microsoft **365.**

Para testar a primeira política, saia e entre com a conta DedicatedAdmin. Você deve ser solicitado a configurar a MFA. Isso demonstra que a primeira política está sendo aplicada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Mapa de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
