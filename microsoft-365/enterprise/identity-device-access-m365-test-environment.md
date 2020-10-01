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
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327802"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3b885-103">Acesso a identidades e dispositivos para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b885-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3b885-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="3b885-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3b885-105">[As configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) são um conjunto de recursos e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3b885-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="3b885-106">Para criar um ambiente de teste que tenha as configurações comuns de acesso de dispositivo e identidade no local:</span><span class="sxs-lookup"><span data-stu-id="3b885-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="3b885-107">Configure seu ambiente de teste com os recursos de identidade e segurança de pré-requisito com base na sua opção de modelo de identidade e método de autenticação:</span><span class="sxs-lookup"><span data-stu-id="3b885-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="3b885-108">Apenas nuvem</span><span class="sxs-lookup"><span data-stu-id="3b885-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="3b885-109">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="3b885-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="3b885-110">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="3b885-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="3b885-111">Use [as políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md) para configurar as políticas que se baseiam nos pré-requisitos configurados para seu ambiente de teste e explorar e verificar a proteção de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3b885-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b885-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b885-112">See also</span></span>

[<span data-ttu-id="3b885-113">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="3b885-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="3b885-114">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="3b885-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3b885-115">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="3b885-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3b885-116">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="3b885-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3b885-117">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="3b885-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
