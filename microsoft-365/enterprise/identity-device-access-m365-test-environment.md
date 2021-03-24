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
ms.openlocfilehash: e90c27edbf4ad5a78c337bf2488956ce82a1ec3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051313"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

[Configurações de identidade](../security/defender-365-security/microsoft-365-policies-configurations.md) e acesso a dispositivos são um conjunto de configurações recomendadas e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).

Para criar um ambiente de teste que tenha as configurações comuns de identidade e acesso a dispositivos:

1. Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:

  - [Apenas nuvem](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronização de hash de senha (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticação de passagem (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [políticas comuns de](../security/defender-365-security/identity-access-policies.md) identidade e acesso a dispositivos para configurar as políticas que se baseam nos pré-requisitos configurados para seu ambiente de teste e explore e verifique a proteção de identidades e dispositivos.

## <a name="see-also"></a>Confira também

[Guias adicionais de laboratório de teste de identidade](m365-enterprise-test-lab-guides.md#identity)

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)
