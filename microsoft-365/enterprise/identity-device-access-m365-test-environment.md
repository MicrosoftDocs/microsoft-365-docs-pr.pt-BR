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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8f74c-103">Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f74c-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8f74c-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="8f74c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8f74c-105">[As configurações de](../security/office-365-security/microsoft-365-policies-configurations.md) acesso a identidades e dispositivos são um conjunto de recursos e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8f74c-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="8f74c-106">Para criar um ambiente de teste que tenha as configurações comuns de acesso de dispositivo e identidade no local:</span><span class="sxs-lookup"><span data-stu-id="8f74c-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="8f74c-107">Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:</span><span class="sxs-lookup"><span data-stu-id="8f74c-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="8f74c-108">Apenas nuvem</span><span class="sxs-lookup"><span data-stu-id="8f74c-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8f74c-109">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="8f74c-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8f74c-110">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="8f74c-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="8f74c-111">Use [políticas comuns de](identity-access-policies.md) identidade e acesso a dispositivos para configurar as políticas que se baseam nos pré-requisitos configurados para seu ambiente de teste e explore e verifique a proteção de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8f74c-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f74c-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="8f74c-112">See also</span></span>

[<span data-ttu-id="8f74c-113">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="8f74c-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="8f74c-114">Mapa de identidade</span><span class="sxs-lookup"><span data-stu-id="8f74c-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8f74c-115">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8f74c-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8f74c-116">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8f74c-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8f74c-117">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8f74c-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
