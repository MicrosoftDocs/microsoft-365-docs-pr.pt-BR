---
title: Pré-requisitos de acesso ao dispositivo e identidade somente nuvem no seu ambiente de teste do Microsoft 365.
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar o acesso de dispositivo e identidade com os pré-requisitos para autenticação somente nuvem.
ms.openlocfilehash: 2d40eca964cc338186f17b1b03423526e36ac196
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068478"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Pré-requisitos de acesso ao dispositivo e identidade somente nuvem no seu ambiente de teste do Microsoft 365.

*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*

As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de configurações e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e o Microsoft Intune no Microsoft 365 Enterprise.

Este artigo descreve como configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos das [ configurações com pré-requisitos somente nuvem ](identity-access-prerequisites.md#prerequisites) para acesso ao dispositivo e identidade.

Há sete fases para configurar esse ambiente de teste:

1.  Criar seu ambiente de teste simples
2.  Configurar localizações nomeadas
3.  Configurar o write-back de senha
4.  Configurar a redefinição de senha de autoatendimento
5.  Configurar autenticação multifator
6.  Habilitar o Azure AD Identity Protection
7.  Habilitar a autenticação moderna do Exchange Online e Skype for Business Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fase 1: Criar seu ambiente de teste simples do Microsoft 365 

Siga as instruções em [Configuração de base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
Esta é a configuração resultante.

![O ambiente de teste leve do Microsoft 3656 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Fase 2: Configurar localizações nomeadas

Primeiro, determine os endereços IP públicos ou intervalos de endereços usados pela sua organização.

Em seguida, siga as instruções em [Configurar locais nomeados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados. 

## <a name="phase-3-configure-password-writeback"></a>Fase 3: Configurar o write-back de senha

Siga as instruções em [Fase 2 do write-back de senha do Guia de Laboratório de Teste](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-4-configure-self-service-password-reset"></a>Fase 4: Configurar a redefinição de senha de autoatendimento

Siga as instruções em [Fase 3 da redefinição de senha do Guia do Laboratório de Teste](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:

- Usuário 2
- Usuário 3
- Usuário 4
- Usuário 5

Teste a redefinição de senha apenas na conta do Usuário 2.

## <a name="phase-5-configure-multi-factor-authentication"></a>Fase 5: Configurar autenticação multifator

Siga as instruções na [Fase 2 de autenticação multifator do Guia de Laboratório de Teste](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:

- Usuário 2
- Usuário 3
- Usuário 4
- Usuário 5

Teste a autenticação multifator apenas para a conta de Usuário 2.

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Fase 6: Habilitar o Azure AD Identity Protection

Siga as instruções em [Fase 2 Azure AD Identity Protection do Guia do Laboratório de Teste](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 7: Habilitar a autenticação moderna do Exchange Online e do Skype for Business Online

Para o Exchange Online, siga [estas instruções](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Para o Skype for Business Online:

1. Conecte-se ao [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Execute este comando.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Verifique se a alteração foi bem-sucedida com esse comando.

  ```powershell
  Get-CsOAuthConfiguration
  ```

O resultado é um ambiente de teste que atende aos requisitos das [ configurações com pré-requisitos somente nuvem ](identity-access-prerequisites.md#prerequisites) para acesso ao dispositivo e identidade. 

## <a name="next-step"></a>Próxima etapa

Use [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.

## <a name="see-also"></a>Confira também

[Guias adicionais de laboratório de teste de identidade](m365-enterprise-test-lab-guides.md#identity)

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
