---
title: Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365
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
description: Crie um ambiente do Microsoft 365 para testar o acesso a identidades e dispositivos.
ms.openlocfilehash: 9195f532222511fc9dce474617ed52916d8e382a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073591"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365

As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de recursos e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure AD (Azure AD), incluindo o Office 365 e o Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.

Para criar um ambiente de teste que tenha essas políticas em vigor:

1. Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:

  - [Apenas nuvem](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronização de hash de senha (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticação de passagem (PTA)](pta-prereqs-m365-test-environment.md)

2. Use as [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e testar a proteção de identidades e dispositivos.

## <a name="see-also"></a>Confira também

[Guias adicionais de laboratório de teste de identidade](m365-enterprise-test-lab-guides.md#identity)

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
