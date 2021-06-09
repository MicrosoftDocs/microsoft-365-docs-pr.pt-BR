---
title: Barreiras de informações no Microsoft 365
description: Saiba como configurar barreiras de informações em Microsoft 365.
keywords: Microsoft 365, risco interno, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423592"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="7d276-104">Barreiras de informações no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d276-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="7d276-105">Microsoft 365 permite a comunicação e a colaboração entre grupos e organizações e oferece suporte a maneiras de restringir a comunicação e a colaboração entre grupos específicos de usuários quando necessário.</span><span class="sxs-lookup"><span data-stu-id="7d276-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="7d276-106">Isso pode incluir situações ou cenários em que você deseja restringir a comunicação e a colaboração entre dois grupos para evitar que um conflito de interesses ocorra em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d276-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="7d276-107">Isso também pode incluir situações em que você precisa restringir a comunicação e a colaboração entre determinadas pessoas dentro da sua organização para proteger informações internas.</span><span class="sxs-lookup"><span data-stu-id="7d276-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="7d276-108">As barreiras de informações são suportadas no Microsoft Teams, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="7d276-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="7d276-109">Um administrador de conformidade ou barreiras de informações pode definir políticas para permitir ou impedir comunicações entre grupos de usuários em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d276-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="7d276-110">As políticas de barreira de informações podem ser usadas para situações como estas:</span><span class="sxs-lookup"><span data-stu-id="7d276-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="7d276-111">O usuário no grupo de comerciantes de dia não deve se comunicar ou compartilhar arquivos com a equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="7d276-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="7d276-112">Os funcionários financeiros que trabalham em informações confidenciais da empresa não devem se comunicar ou compartilhar arquivos com determinados grupos em sua organização</span><span class="sxs-lookup"><span data-stu-id="7d276-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="7d276-113">Uma equipe interna com material de segredo comercial não deve chamar ou conversar online com pessoas em determinados grupos em sua organização</span><span class="sxs-lookup"><span data-stu-id="7d276-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="7d276-114">Uma equipe de pesquisa só deve chamar ou conversar online com uma equipe de desenvolvimento de produtos</span><span class="sxs-lookup"><span data-stu-id="7d276-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="7d276-115">Configurar barreiras de informações para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d276-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="7d276-116">Use as etapas a seguir para configurar barreiras de informações para sua organização:</span><span class="sxs-lookup"><span data-stu-id="7d276-116">Use the following steps to configure information barriers for your organization:</span></span>

![Etapas de barreiras de informações da solução de risco insider](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="7d276-118">Saiba mais [sobre as barreiras de](information-barriers.md) informações Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d276-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="7d276-119">Configurar [pré-requisitos e permissões](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="7d276-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="7d276-120">Segmentar [usuários em sua organização](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="7d276-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="7d276-121">Criar e configurar políticas [de barreira de informações](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="7d276-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="7d276-122">Aplicar [políticas de barreira de informações](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="7d276-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="7d276-123">Mais informações sobre barreiras de informações</span><span class="sxs-lookup"><span data-stu-id="7d276-123">More information about information barriers</span></span>

- [<span data-ttu-id="7d276-124">Atributos das políticas de barreira de informações</span><span class="sxs-lookup"><span data-stu-id="7d276-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="7d276-125">Editar ou remover políticas de barreira de informações</span><span class="sxs-lookup"><span data-stu-id="7d276-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)