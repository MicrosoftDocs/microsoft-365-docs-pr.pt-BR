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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="115f6-103">Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="115f6-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="115f6-104">As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de recursos e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure AD (Azure AD), incluindo o Office 365 e o Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="115f6-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="115f6-105">Para criar um ambiente de teste que tenha essas políticas em vigor:</span><span class="sxs-lookup"><span data-stu-id="115f6-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="115f6-106">Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:</span><span class="sxs-lookup"><span data-stu-id="115f6-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="115f6-107">Apenas nuvem</span><span class="sxs-lookup"><span data-stu-id="115f6-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="115f6-108">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="115f6-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="115f6-109">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="115f6-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="115f6-110">Use as [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e testar a proteção de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="115f6-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="115f6-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="115f6-111">See also</span></span>

[<span data-ttu-id="115f6-112">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="115f6-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="115f6-113">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="115f6-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="115f6-114">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="115f6-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="115f6-115">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="115f6-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="115f6-116">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="115f6-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
