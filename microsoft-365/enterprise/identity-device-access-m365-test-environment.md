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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="fc76c-103">Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc76c-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="fc76c-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="fc76c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fc76c-105">[Configurações de identidade](../security/defender-365-security/microsoft-365-policies-configurations.md) e acesso a dispositivos são um conjunto de configurações recomendadas e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fc76c-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="fc76c-106">Para criar um ambiente de teste que tenha as configurações comuns de identidade e acesso a dispositivos:</span><span class="sxs-lookup"><span data-stu-id="fc76c-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="fc76c-107">Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:</span><span class="sxs-lookup"><span data-stu-id="fc76c-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="fc76c-108">Apenas nuvem</span><span class="sxs-lookup"><span data-stu-id="fc76c-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="fc76c-109">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="fc76c-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="fc76c-110">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="fc76c-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="fc76c-111">Use [políticas comuns de](../security/defender-365-security/identity-access-policies.md) identidade e acesso a dispositivos para configurar as políticas que se baseam nos pré-requisitos configurados para seu ambiente de teste e explore e verifique a proteção de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fc76c-111">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc76c-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="fc76c-112">See also</span></span>

[<span data-ttu-id="fc76c-113">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="fc76c-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="fc76c-114">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="fc76c-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fc76c-115">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="fc76c-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fc76c-116">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="fc76c-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fc76c-117">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="fc76c-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
