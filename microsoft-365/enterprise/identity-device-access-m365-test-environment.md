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
ms.openlocfilehash: 5a9e9ef9ea6b8f6dc80aa7fea225f3573b8fcadc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197870"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ad23e-103">Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad23e-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ad23e-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="ad23e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ad23e-105">[Configurações de identidade](../security/office-365-security/microsoft-365-policies-configurations.md) e acesso a dispositivos são um conjunto de configurações recomendadas e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ad23e-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="ad23e-106">Para criar um ambiente de teste que tenha as configurações comuns de identidade e acesso a dispositivos:</span><span class="sxs-lookup"><span data-stu-id="ad23e-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="ad23e-107">Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:</span><span class="sxs-lookup"><span data-stu-id="ad23e-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="ad23e-108">Apenas nuvem</span><span class="sxs-lookup"><span data-stu-id="ad23e-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="ad23e-109">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="ad23e-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="ad23e-110">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="ad23e-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="ad23e-111">Use [políticas comuns de](../security/office-365-security/identity-access-policies.md) identidade e acesso a dispositivos para configurar as políticas que se baseam nos pré-requisitos configurados para seu ambiente de teste e explore e verifique a proteção de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ad23e-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad23e-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="ad23e-112">See also</span></span>

[<span data-ttu-id="ad23e-113">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="ad23e-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="ad23e-114">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="ad23e-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ad23e-115">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ad23e-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ad23e-116">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ad23e-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ad23e-117">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ad23e-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
