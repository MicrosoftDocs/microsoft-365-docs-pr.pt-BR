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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como configurar a autenticação multifator para sua organização.
monikerRange: o365-worldwide
ms.openlocfilehash: 893a4ae535dfb781a4f77ee57c0ead40fda8454f
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340769"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar a autenticação multifator
  
Com base na sua compreensão da [MFA (autenticação multifator) e de seu suporte no Microsoft 365](multi-factor-authentication-microsoft-365.md), é hora de configurá-la e revertê-la em sua organização.

Antes de começar, determine se essas condições especiais se aplicam a você e execute a ação apropriada:

- Se você tiver clientes do Office 2013 em dispositivos Windows, [habilite a autenticação moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Se você tiver serviços de diretório de terceiros com o AD FS (serviços de Federação do Active Directory), configure o servidor do Azure MFA. Consulte [cenários avançados com a autenticação multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter mais informações.

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Etapa 1: decida o método de exigir que seus usuários usem a MFA

Há três maneiras de exigir que os usuários utilizem a MFA para entradas. Confira [suporte da MFA no Microsoft 365](multi-factor-authentication-microsoft-365.md) para obter os detalhes.

- Padrões de segurança (recomendado para pequenas empresas)

  Se você comprou sua assinatura ou avaliação após 21 de outubro de 2019, e se você for solicitado inesperadamente pela MFA, [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para sua assinatura.
  
  Todas as novas assinaturas do Microsoft 365 terão automaticamente os padrões de segurança ativados. Isso significa que cada usuário terá que configurar a MFA e instalar o aplicativo Microsoft Authenticator em seu dispositivo móvel.

  Todos os usuários devem usar o aplicativo Microsoft Authenticator, pois o método adicional de verificação e a autenticação herdada são bloqueados. 

- Políticas de acesso condicional (recomendadas para empresas)

  Os usuários escolhem o método de verificação adicional durante o registro de MFA.

- Conta por usuário (não recomendado)

  Os usuários escolhem o método de verificação adicional durante o registro de MFA.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Etapa 2. Teste MFA nos seus usuários pilotos

Se você estiver usando políticas de acesso condicional ou por usuário (não recomendado), selecione usuários piloto em sua empresa ou organização para testar o registro e as entradas da MFA. Por exemplo:

- Para políticas de acesso condicional, crie um grupo de usuários piloto e uma política que exija MFA para os membros do grupo e para todos os aplicativos. Em seguida, adicione as contas do usuário piloto ao grupo.

- Para a MFA por usuário, habilite a MFA para as contas de usuário de seus usuários pilotos uma vez.

Trabalhe com seus usuários pilotos para resolver dúvidas e problemas para se preparar para a sua organização.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Etapa 3. Informar à sua organização que a MFA está chegando

Use notificações por email, cartazes de corredor, reuniões de equipe ou treinamento formal para garantir que seus funcionários compreendam:

- Por que a MFA é necessária para os logins
- [Como se registrar para o método de verificação adicional](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [Como entrar após o registro](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [Como alterar o método de verificação adicional](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [Como lidar com situações como um novo telefone inteligente](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

Mais importante, certifique-se de que seus funcionários entendam ***quando o requisito da MFA será imposto*** para que ele não seja surpresa.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Etapa 4. Distribuir o requisito da MFA para sua organização ou usuários

Com base no método de solicitação de MFA escolhido, distribua a autenticação MFA para os funcionários além dos seus testadores piloto.

### <a name="security-defaults"></a>Padrões de segurança

Habilite ou desabilite os padrões de segurança no painel de **Propriedades** do Azure Active Directory (Azure AD) no portal do Azure.

1.  Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) com as credenciais de administrador global.
2.  Vá para a [página Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Na parte inferior da página, clique em **Gerenciar padrões de segurança**.
4.  Escolha **Sim** para habilitar os padrões de segurança e **não** para desabilitar os padrões de segurança e, em seguida, escolha **salvar**.

Se você estiver usando [políticas de acesso condicional da linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), veja como mover para usar os padrões de segurança.

1.  Vá para a [página de políticas de acesso condicional](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Escolha cada política de linha de base que está **ativada** e defina **habilitar política** como **desativado**.
2.  Vá para a [página Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Na parte inferior da página, clique em **Gerenciar padrões de segurança**.
5.  Escolha **Sim** para habilitar os padrões de segurança e **não** para desabilitar os padrões de segurança e, em seguida, escolha **salvar**.

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

Crie, configure ou habilite as políticas apropriadas que incluem o grupo de usuários que exigem MFA de entrada.

### <a name="per-user-mfa-not-recommended"></a>MFA por usuário (não recomendado)

Habilitar contas de usuário para MFA correspondente à sua distribuição.

### <a name="supporting-your-employees"></a>Suporte aos seus funcionários

À medida que seus funcionários se registram e começam a entrar com a MFA, certifique-se de que seus especialistas de ti, departamento de ti ou helpdesk podem responder perguntas e resolver problemas rapidamente.

Confira este artigo para obter [informações sobre como solucionar problemas de entradas MFA](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2). 


