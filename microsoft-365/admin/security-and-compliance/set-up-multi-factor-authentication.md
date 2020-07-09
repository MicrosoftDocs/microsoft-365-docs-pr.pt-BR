---
title: Configurar a autenticação multifator para usuários
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como configurar a autenticação multifator para a sua organização.
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083533"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar a autenticação multifator
  
Com base no seu conhecimento de [MFA (autenticação multifator) e seu suporte no Microsoft 365](multi-factor-authentication-microsoft-365.md), é hora de configurá-la e distribuí-la para a sua organização.

Antes de começar, determine se estas condições especiais se aplicam a você e execute a ação adequada:

- Se você tem clientes do Office 2013 em dispositivos Windows, [habilitar Autenticação Moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Se você tiver serviços de diretório de terceiros com o AD FS (Serviços de Federação do Active Directory), configure o Servidor do Azure MFA. Confira [cenários avançados com a Autenticação Multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter mais informações.

Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário. Para saber mais, acesse [Método e configurações de verificação de dois fatores](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Etapa 1: Decidir o método de exigir que os usuários usem a MFA

> [!NOTE]
> Você deve ser um administrador global para configurar ou modificar a MFA. Há três maneiras de exigir que os usuários usem a MFA de entradas. Confira [Suporte a MFA no Microsoft 365](multi-factor-authentication-microsoft-365.md) para obter detalhes.

- Padrões de segurança (recomendado para pequenas empresas)

  Se você comprou a sua assinatura ou a versão de avaliação após 21 de outubro de 2019 e for inesperadamente solicitado a executar a MFA, [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para a sua assinatura.
  
  Todos os novos recursos de assinatura do Microsoft 365 terão automaticamente os padrões de segurança ativados. Isso significa que todos os usuários terão que configurar a MFA e instalar o aplicativo Microsoft Authenticator no seu dispositivo móvel.

  Todos os usuários devem usar o aplicativo Microsoft Authenticator como método de verificação adicional e a autenticação herdada será bloqueada. 

- Políticas de acesso condicional (recomendado para empresas)

  Os usuários escolhem o método de verificação adicional durante o registro da MFA.

- Conta por usuário (não recomendado)

  Os usuários escolhem o método de verificação adicional durante o registro da MFA.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Etapa 2. Testar a MFA em seus usuários piloto

Se você estiver usando políticas de acesso condicional ou MFA por usuário (não recomendado), selecione usuários piloto na sua empresa ou organização para testar o registro e as entradas da MFA. Por exemplo:

- Para políticas de acesso condicional, crie um grupo de usuários piloto e uma política que exija MFA para os membros do grupo e para todos os aplicativos. Em seguida, adicione as contas do usuário piloto ao grupo.

- No MFA por usuário, habilite a MFA das contas de usuários do piloto uma vez.

Trabalhe com seus usuários piloto para solucionar problemas e dúvidas sobre como se preparar para a sua organização.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Etapa 3. Informar à sua organização que a MFA está chegando

Use notificações por email, pôsteres de corredor, reuniões da equipe ou treinamento oficial para garantir que seus funcionários compreendam:

- Por que a MFA está sendo necessária para entradas
- [Como se inscrever para obter o método de verificação adicional](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Como entrar após o registro](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Como alterar o método de verificação adicional](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Como lidar com situações como um novo smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

O mais importante, certifique-se de que seus funcionários entendem ***quando o requisito da MFA será imposto*** para que eles não se surpreendam.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Etapa 4. Implementar o requisito da MFA da sua organização ou usuários

Com base no método de requisito da MFA, distribua a autenticação MFA para os funcionários que estão além de seus testadores piloto.

### <a name="security-defaults"></a>Padrões de segurança

Habilite ou desabilite as opções de segurança no painel de **Propriedades** para o Azure Active Directory (Azure AD) no portal do Azure.

1.  Acessar o [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais de administrador global.
2.  Vá para [Azure Active Directory - Página Propriedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.
4.  Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.

Se você estiver usando [políticas de Acesso Condicional da linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), veja aqui como mover para usar padrões de segurança.

1.  Vá para a página [Acesso Condicional - página Políticas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Escolha cada política de linha de base que esteja **Ativada** e defina **Permitir que a política** seja **Desativada**.
2.  Vá para [Azure Active Directory - Página Propriedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.
5.  Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

Crie, configure e habilite as políticas apropriadas que incluem o grupo de usuários que exigem MFA de entrada.

### <a name="per-user-mfa-not-recommended"></a>MFA por usuário (não recomendado)

Habilite as contas de usuário da MFA correspondentes à sua distribuição.

### <a name="supporting-your-employees"></a>Suporte a seus funcionários

À medida que seus funcionários se inscreverem e começarem a entrar com a MFA, certifique-se de que os especialistas de TI, o departamento de TI ou o helpdesk possam responder a perguntas e resolver problemas rapidamente.

Confira este artigo para obter [informações sobre como solucionar problemas de entrada MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


