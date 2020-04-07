---
title: Guias do Laboratório de Teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Use estes Guias de Laboratório de Teste para configurar a demonstração, prova de conceito ou ambientes de desenvolvimento/teste para o Microsoft 365 para empresas.
ms.openlocfilehash: 1ea41cd3553c70b2a8bb99e08da43fd45b1aa558
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153911"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Guias do Laboratório de Teste do Microsoft 365 para empresas

*Isso se aplica ao Microsoft 365 para empresas e ao Office 365 Enterprise.*

Os TLGs (Guias de Laboratório de Teste) ajudam a aprender rapidamente sobre os produtos da Microsoft. Eles fornecem instruções dirigidas para configurar os ambientes de testes representativos, mas simplificados. Você pode usar esses ambientes para demonstração, personalização ou criação de provas complexas de conceito durante a vigência de uma assinatura de avaliação ou paga. 

Os TLGs foram projetados para serem modulares. Eles se complementam para criar várias configurações que correspondem melhor às suas necessidades de configuração de teste ou aprendizado. A experiência prática no estilo "criei por conta própria e funciona" ajuda você a entender os requisitos de implantação de um novo produto ou cenário para poder planejar melhor sua hospedagem em produção.

Você também pode usar os TLGs para criar ambientes representativos de desenvolvimento e teste de aplicativos, conhecidos como ambientes de desenvolvimento/teste.
  
![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.

[![A pilha da Guia do Laboratório de Teste do Microsoft 365 para empresas](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Configuração base

Primeiro, crie um ambiente de teste para o [Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/) que inclua o Office 365 E5, o Enterprise Mobility+Security (EMS) E5 e o Windows 10 Enterprise. Você pode criar dois tipos diferentes de configurações básicas:

- Use a [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md) quando quiser configurar e demonstrar recursos e capacidades do Microsoft 365 para empresas em um ambiente exclusivamente em nuvem, que não inclui nenhum componente local.

- Use a [configuração básica corporativa simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) quando quiser configurar e demonstrar recursos e capacidades do Microsoft 365 para empresas em um ambiente exclusivamente em nuvem híbrida, que usa componentes locais como o domínio dos Serviços de Domínio do Active Directory (AD DS).

Você também pode criar ambientes de teste do Office 365 E5, não adicionando a licença da Microsoft 365 E5 ao seu ambiente de avaliação ou produção.
    
## <a name="identity"></a>Identidade

Para demonstrar recursos e capacidades relacionados à identidade, confira:

- [Sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md)
  
   Habilite e teste a sincronização de diretório baseado em hash de senha de um controlador de domínio do AD DS.

- [Autenticação de passagem](pass-through-auth-m365-ent-test-environment.md)
  
   Habilite e teste a autenticação de passagem para um controlador de domínio do AD DS.

- [Autenticação federada](federated-identity-for-your-office-365-dev-test-environment.md)
  
   Habilite e teste a autenticação federada para um controlador de domínio do AD DS.

- [Logon único contínuo do Azure Active Directory](single-sign-on-m365-ent-test-environment.md)
  
   Habilite e teste o Logon Único Contínuo (SSO) do Azure AD com um controlador de domínio do AD DS.

- [Autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Habilite e teste a autenticação multifator com base em smartphone para uma conta de usuário específica.

- [Proteger contas de administradores globais](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Bloqueie suas contas globais de administrador com políticas de Acesso Condicional.

- [Senha write-back](password-writeback-m365-ent-test-environment.md)

   Use senha write-back para alternar a senha na sua conta de usuário do AD DS do Azure AD.

- [Redefinição de senha](password-reset-m365-ent-test-environment.md)

   Use SSPR (Redefinição de senha de autoatendimento) para redefinir sua senha.

- [Licenciamento automático e associação de grupo](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Faça com que administrar novas contas seja mais fácil do que nunca com o licenciamento automático e associação dinâmica a grupos.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Verifique a existência de vulnerabilidades na sua conta de usuário atual.

- [Acesso a identidades e dispositivos](identity-device-access-m365-test-environment.md)

   Crie um ambiente para testar configurações recomendadas de acesso a identidades e dispositivos e políticas de Acesso Condicional.


## <a name="mobile-device-management"></a>Gerenciamento de dispositivo móvel

Para demonstrar recursos relacionados ao gerenciamento de dispositivo móvel, confira:

- [Políticas de conformidade do dispositivo](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Criar uma política de conformidade do dispositivo e um grupo de usuários para dispositivos com Windows 10.
    
- [Registrar dispositivos iOS e Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Registre os dispositivos iOS ou Android e gerencie-os remotamente.


## <a name="information-protection"></a>Proteção de informações

Para demonstrar recursos e capacidades relacionados à proteção da informação, confira:

- [Segurança ampliada do Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure definições de segurança ampliada no Office 365 e investigue ferramentas internas de segurança.
  
- [Classificação de dados](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure e aplique rótulos do Office 365 a um documento em um site de equipe do SharePoint Online.
    
- [Gerenciamento de acesso privilegiado](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure o gerenciamento de acesso privilegiado com acesso just-in-time para tarefas elevadas e privilegiadas na sua organização do Office 365.


