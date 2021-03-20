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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Use estes Guias de Laboratório de Teste para configurar a demonstração, prova de conceito ou ambientes de desenvolvimento/teste para o Microsoft 365 para empresas.
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909593"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Guias do Laboratório de Teste do Microsoft 365 para empresas

*Isso se aplica ao Microsoft 365 para empresas e ao Office 365 Enterprise.*

Os TLGs (Guias de Laboratório de Teste) ajudam a aprender rapidamente sobre os produtos da Microsoft. Eles fornecem instruções dirigidas para configurar os ambientes de testes representativos, mas simplificados. Você pode usar esses ambientes para demonstração, personalização ou criação de provas complexas de conceito durante a vigência de uma assinatura de avaliação ou paga.

Os TLGs foram projetados para serem modulares. Eles se baseam uns nos outros para criar várias configurações que mais corresponderem às suas necessidades de aprendizado ou de configuração de teste. A experiência prática "Eu mesmo o construí e funciona" ajuda você a entender os requisitos de implantação de um novo produto ou cenário, para que você possa planejar melhor a hospedagem em produção.

Você também pode usar TLGs para criar ambientes representativos para desenvolver e testar aplicativos, também conhecidos como ambientes de desenvolvimento/teste.
  
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Para um mapa visual de todos os artigos na pilha guia do Laboratório de Teste do Microsoft 365 para empresas, expanda o gráfico a seguir ou vá para [o Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para a pilha de guias de laboratório de teste corporativos.

[![A pilha da Guia do Laboratório de Teste do Microsoft 365 para empresas](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Configuração base

Primeiro, crie um ambiente de teste [para o Microsoft 365 para empresas.](/microsoft-365-enterprise/) Você pode criar dois tipos diferentes de configurações base:

- [Configuração base](lightweight-base-configuration-microsoft-365-enterprise.md) leve - Use isso quando quiser configurar e demonstrar o Microsoft 365 para recursos e recursos corporativos em um ambiente somente na nuvem, que não inclui nenhum componente local.

- [Configuração](simulated-ent-base-configuration-microsoft-365-enterprise.md) de base corporativa simulada - Use isso quando quiser configurar e demonstrar o Microsoft 365 para recursos e recursos corporativos em um ambiente de nuvem híbrido, que usa componentes locais, como um domínio do AD DS (Serviços de Domínio do Active Directory).

Você também pode criar ambientes de teste do Office 365 E5, não adicionando a licença da Microsoft 365 E5 ao seu ambiente de avaliação ou produção.
    
## <a name="identity"></a>Identidade

Para demonstrar recursos e capacidades relacionados à identidade, confira:

- [Sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md)
  
   Habilite e teste a sincronização de diretório baseado em hash de senha de um controlador de domínio do AD DS.

- [Autenticação de passagem](pass-through-auth-m365-ent-test-environment.md)
  
   Habilite e teste a autenticação de passagem para um controlador de domínio do AD DS.

- [Autenticação federada](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   Habilite e teste a autenticação federada para um controlador de domínio do AD DS.

- [Logon único contínuo do Azure Active Directory](single-sign-on-m365-ent-test-environment.md)
  
   Habilitar e testar o Azure AD Seamless Single Sign-on (SSO contínuo) com um controlador de domínio do AD DS.

- [Autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Habilite e teste a autenticação multifator com base em smartphone para uma conta de usuário específica.

- [Proteger contas de administradores globais](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   Bloqueie suas contas globais de administrador com políticas de acesso condicional.

- [Senha write-back](password-writeback-m365-ent-test-environment.md)

   Use senha write-back para alternar a senha na sua conta de usuário do AD DS do Azure AD.

- [Redefinição de senha](password-reset-m365-ent-test-environment.md)

   Use a redefinição de senha de autoatendados para redefinir sua senha.

- [Licenciamento automático e associação de grupo](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Faça com que administrar novas contas seja mais fácil do que nunca com o licenciamento automático e associação dinâmica a grupos.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Verifique a existência de vulnerabilidades na sua conta de usuário atual.

- [Acesso a identidades e dispositivos](identity-device-access-m365-test-environment.md)

   Crie um ambiente para testar configurações recomendadas de acesso a identidades e dispositivos e políticas de acesso condicional.

## <a name="mobile-device-management"></a>Gerenciamento de dispositivo móvel

Para demonstrar recursos relacionados ao gerenciamento de dispositivo móvel, confira:

- [Políticas de conformidade do dispositivo](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Criar uma política de conformidade do dispositivo e um grupo de usuários para dispositivos com Windows 10.
    
- [Registrar dispositivos iOS e Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Registre os dispositivos iOS ou Android e gerencie-os remotamente.

## <a name="information-protection"></a>Proteção de informações

Para demonstrar recursos e capacidades relacionados à proteção da informação, confira:

- [Segurança do Microsoft 365 aumentada](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Defina as configurações para aumentar a segurança do Microsoft 365 e investigar as ferramentas de segurança internas.
  
- [Classificação de dados](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure e aplique rótulos a um documento em um site de equipe do SharePoint Online.
    
- [Gerenciamento de acesso privilegiado](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure o gerenciamento de acesso privilegiado para acesso na hora certa às tarefas elevadas e privilegiadas na sua organização.