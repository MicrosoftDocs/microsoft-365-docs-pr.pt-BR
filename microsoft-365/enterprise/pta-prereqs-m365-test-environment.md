---
title: Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar a identidade e o acesso a dispositivos com os pré-requisitos para a autenticação de passagem.
ms.openlocfilehash: b8c9ebefacf81293b553aecf8ead0a387c18758b
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073017"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365

As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de configurações e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e o Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.

Este artigo descreve como você pode configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos da [Configuração de pré-requisitos de autenticação de passagem](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.

Existem oito fases para configurar este ambiente de teste:

1.  Crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365
2.  Configurar logon único contínuo do Azure AD
3.  Configurar localizações nomeadas
4.  Configurar o write-back de senha
5.  Configurar a redefinição de senha de autoatendimento
6.  Configurar autenticação multifatorial
7.  Habilitar o Azure AD Identity Protection
8.  Habilite a autenticação moderna para o Exchange Online e o Skype for Business Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>Fase 1: crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365

Siga as instruções em [Autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).

Esta é a configuração resultante.

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fase 2: configurar o logon único contínuo do Azure AD

Siga as instruções na [Fase 2 do Guia do Laboratório de Testes de Logon Único Contínuo do Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fase 3: Configurar locais nomeados

Primeiro, determine os endereços IP públicos ou os intervalos de endereços usados por sua organização.

Em seguida, siga as instruções em [Configurar locais nomeados no Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados. 

## <a name="phase-4-configure-password-writeback"></a>Fase 4: Configurar write-back de senha

Siga as instruções da [Fase 2 do Guia do Laboratório de Teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-5-configure-self-service-password-reset"></a>Fase 5: Configurar a redefinição da senha de autoatendimento

Siga as instruções na [Fase 3 do Guia do Laboratório de Teste de redefinição de senha](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:

- Usuário 2
- Usuário 3
- Usuário 4
- Usuário 5

Teste a redefinição de senha somente para a conta do Usuário 2.

## <a name="phase-6-configure-multi-factor-authentication"></a>Fase 6: Configurar a autenticação multifator

Siga as instruções na [Fase 2 do Guia do Laboratório de Teste de autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:

- Usuário 2
- Usuário 3
- Usuário 4
- Usuário 5

Teste a autenticação de vários fatores somente para a conta do Usuário 2.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fase 7: ativar a proteção de identidade do Azure AD

Siga as instruções na [Fase 2 do Guia do Laboratório de Teste do Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 8: habilite a autenticação moderna para o Exchange Online e o Skype for Business Online

Para o Exchange Online, siga [estas instruções](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Para o Skype for Business Online:

1. Conecte-se ao [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Execute este comando.

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Verifique se a mudança foi bem sucedida com este comando.

  ```
  Get-CsOAuthConfiguration
  ```

O resultado é um ambiente de teste que atende aos requisitos da [configuração de pré-requisito de autenticação de passagem](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos. 

## <a name="next-step"></a>Próxima etapa

Use [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.

## <a name="see-also"></a>Confira também

[Guias adicionais de laboratório de teste de identidade](m365-enterprise-test-lab-guides.md#identity)

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

