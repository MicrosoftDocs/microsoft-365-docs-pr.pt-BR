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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar o acesso a identidades e dispositivos.
ms.openlocfilehash: 45749140698553a75df50ed1111cdbfc8eb15684
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153733"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f1d72-103">Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1d72-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f1d72-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f1d72-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f1d72-105">As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de recursos e políticas de Acesso Condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e o Microsoft Intune no Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f1d72-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and Conditional Access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="f1d72-106">Para criar um ambiente de teste que tenha essas políticas em vigor:</span><span class="sxs-lookup"><span data-stu-id="f1d72-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="f1d72-107">Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:</span><span class="sxs-lookup"><span data-stu-id="f1d72-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="f1d72-108">Apenas nuvem</span><span class="sxs-lookup"><span data-stu-id="f1d72-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="f1d72-109">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="f1d72-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="f1d72-110">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="f1d72-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="f1d72-111">Use as [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e testar a proteção de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f1d72-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1d72-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="f1d72-112">See also</span></span>

[<span data-ttu-id="f1d72-113">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="f1d72-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="f1d72-114">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="f1d72-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f1d72-115">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1d72-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f1d72-116">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1d72-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f1d72-117">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1d72-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
