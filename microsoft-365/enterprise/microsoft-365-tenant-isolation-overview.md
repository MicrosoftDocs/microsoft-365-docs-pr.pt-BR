---
title: Isolamento de locatário no Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Este artigo contém um resumo de como a Microsoft impõe o isolamento de locatário em serviços de nuvem, como o Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384938"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="b202a-103">Isolamento de locatário no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b202a-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="b202a-104">Um dos principais benefícios da computação em nuvem é o conceito de uma infraestrutura compartilhada e comum em vários clientes simultaneamente, o que leva a uma grande reação de escala.</span><span class="sxs-lookup"><span data-stu-id="b202a-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="b202a-105">Esse conceito é chamado *de multi-tenancy*.</span><span class="sxs-lookup"><span data-stu-id="b202a-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="b202a-106">A Microsoft trabalha continuamente para garantir que as arquiteturas de vários locatários de nossos serviços de nuvem suportem padrões de segurança, confidencialidade, privacidade, integridade e disponibilidade de nível empresarial.</span><span class="sxs-lookup"><span data-stu-id="b202a-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="b202a-107">Com base nos investimentos [](https://www.microsoft.com/trust-center) significativos e na [](https://www.microsoft.com/securityengineering/sdl/)experiência coletada da Computação Confiável e do Ciclo de Vida de Desenvolvimento de Segurança, os serviços de nuvem da Microsoft foram projetados com a suposição de que todos os locatários são potencialmente invasores para todos os outros locatários, e implementamos medidas de segurança para impedir que as ações de um locatário afetem a segurança ou o serviço de outro locatário ou acessem o conteúdo de outro locatário.</span><span class="sxs-lookup"><span data-stu-id="b202a-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="b202a-108">Os dois objetivos principais de manter o isolamento de locatário em um ambiente multi-locatário são:</span><span class="sxs-lookup"><span data-stu-id="b202a-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="b202a-109">Impedir vazamento de conteúdo do cliente entre locatários ou acesso não autorizado; e</span><span class="sxs-lookup"><span data-stu-id="b202a-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="b202a-110">Impedir que as ações de um locatário afetem negativamente o serviço para outro locatário</span><span class="sxs-lookup"><span data-stu-id="b202a-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="b202a-111">Várias formas de proteção foram implementadas em todo o Microsoft 365 para impedir que os clientes comprometem os serviços ou aplicativos do Microsoft 365 ou obtenham acesso não autorizado às informações de outros locatários ou do próprio sistema do Microsoft 365, incluindo:</span><span class="sxs-lookup"><span data-stu-id="b202a-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="b202a-112">O isolamento lógico do conteúdo do cliente em cada locatário dos serviços do Microsoft 365 é obtido por meio da autorização do Azure Active Directory e do controle de acesso baseado em função.</span><span class="sxs-lookup"><span data-stu-id="b202a-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="b202a-113">O SharePoint Online fornece mecanismos de isolamento de dados no nível de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b202a-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="b202a-114">A Microsoft usa segurança física rigorosa, triagem em segundo plano e uma estratégia de criptografia de várias camadas para proteger a confidencialidade e a integridade do conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="b202a-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="b202a-115">Todos os datacenters do Microsoft 365 têm controles de acesso biométrico, com a maioria exigindo impressão digital para obter acesso físico.</span><span class="sxs-lookup"><span data-stu-id="b202a-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="b202a-116">Além disso, todos os funcionários da Microsoft baseados nos EUA devem concluir com êxito uma verificação de plano de fundo padrão como parte do processo de contratação.</span><span class="sxs-lookup"><span data-stu-id="b202a-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="b202a-117">Para obter mais informações sobre os controles usados para acesso administrativo no Microsoft 365, consulte Controles de Acesso Administrativo do [Microsoft 365.](microsoft-365-administrative-access-controls-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b202a-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="b202a-118">O Microsoft 365 usa tecnologias do lado do serviço que criptografam o conteúdo do cliente em repouso e em trânsito, incluindo BitLocker, criptografia por arquivo, TLS (Transport Layer Security) e Internet Protocol Security (IPsec).</span><span class="sxs-lookup"><span data-stu-id="b202a-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="b202a-119">Para obter detalhes específicos sobre criptografia no Microsoft 365, confira Tecnologias de [Criptografia de Dados no Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b202a-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="b202a-120">Juntos, as proteções acima listadas fornecem controles robustos de isolamento lógico que fornecem proteção contra ameaças e mitigação equivalentes às fornecidas apenas pelo isolamento físico.</span><span class="sxs-lookup"><span data-stu-id="b202a-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="b202a-121">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="b202a-121">Related Links</span></span>

- [<span data-ttu-id="b202a-122">Isolamento e controle de acesso do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b202a-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="b202a-123">Isolamento de locatário no Office Graph e Delve</span><span class="sxs-lookup"><span data-stu-id="b202a-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="b202a-124">Isolamento de locatário no Microsoft 365 Search</span><span class="sxs-lookup"><span data-stu-id="b202a-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="b202a-125">Isolamento de locatário no Vídeo do Office 365</span><span class="sxs-lookup"><span data-stu-id="b202a-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="b202a-126">Limites de recurso</span><span class="sxs-lookup"><span data-stu-id="b202a-126">Resource Limits</span></span>](microsoft-365-resource-limits.md)
- [<span data-ttu-id="b202a-127">Monitorando e testando limites do locatário</span><span class="sxs-lookup"><span data-stu-id="b202a-127">Monitoring and Testing Tenant Boundaries</span></span>](microsoft-365-monitoring-and-testing.md)
- [<span data-ttu-id="b202a-128">Isolamento e controle de acesso no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b202a-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)
