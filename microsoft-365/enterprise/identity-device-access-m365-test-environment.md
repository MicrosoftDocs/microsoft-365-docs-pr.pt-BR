---
title: Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar o acesso a identidades e dispositivos.
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398802"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

[As configurações de acesso de dispositivo e identidade](../security/office-365-security/microsoft-365-policies-configurations.md) são um conjunto de recursos e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).

Para criar um ambiente de teste que tenha as configurações comuns de acesso de dispositivo e identidade no local:

1. Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:

  - [Apenas nuvem](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronização de hash de senha (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticação de passagem (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [as políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md) para configurar as políticas que se baseiam nos pré-requisitos configurados para seu ambiente de teste e explorar e verificar a proteção de identidades e dispositivos.

## <a name="see-also"></a>Confira também

[Guias adicionais de laboratório de teste de identidade](m365-enterprise-test-lab-guides.md#identity)

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
