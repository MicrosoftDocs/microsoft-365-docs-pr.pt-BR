---
title: Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar o acesso a identidades e dispositivos.
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233723"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

[As configurações de](../security/office-365-security/microsoft-365-policies-configurations.md) acesso a identidades e dispositivos são um conjunto de configurações recomendadas e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).

Para criar um ambiente de teste que tenha as configurações comuns de acesso de dispositivo e identidade no local:

1. Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:

  - [Apenas nuvem](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronização de hash de senha (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticação de passagem (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [políticas comuns de](identity-access-policies.md) identidade e acesso a dispositivos para configurar as políticas que se baseiem nos pré-requisitos configurados para seu ambiente de teste e explore e verifique a proteção de identidades e dispositivos.

## <a name="see-also"></a>Confira também

[Guias adicionais de laboratório de teste de identidade](m365-enterprise-test-lab-guides.md#identity)

[Mapa de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
