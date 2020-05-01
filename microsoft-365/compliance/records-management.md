---
title: Gerenciamento de registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Com o gerenciamento de registros no Microsoft 365, você pode aplicar a agenda de retenção específica da sua organização em um plano de arquivo para gerenciar a retenção, a declaração de registros e o descarte no suporte de todo o ciclo de vida do conteúdo.
ms.openlocfilehash: e4454ba5940d9a67d9f160d90d0a9db14563bcf7
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949244"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="8b315-103">Gerenciamento de registros no Office 365</span><span class="sxs-lookup"><span data-stu-id="8b315-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="8b315-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="8b315-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8b315-105">Organizações de todos os tipos exigem uma solução de gerenciamento de registros para gerenciar registros reguladores, jurídicos e corporativos em seus dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="8b315-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="8b315-106">O gerenciamento de registros no Microsoft 365 ajuda a sua organização a gerenciar suas obrigações legais, oferecer a capacidade de demonstrar a conformidade com as regulamentações e aumentar a eficiência com o descarte regular de itens que não precisam mais ser mantidos, não são mais importantes ou obrigatórios para fins comerciais.</span><span class="sxs-lookup"><span data-stu-id="8b315-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="8b315-107">A solução de gerenciamento de registros é compatível com os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="8b315-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="8b315-108">**Conteúdo do rótulo como um registro**.</span><span class="sxs-lookup"><span data-stu-id="8b315-108">**Label content as a record**.</span></span> <span data-ttu-id="8b315-109">Crie e publique rótulos de retenção que declarem o conteúdo como um [registro](records.md) que possa ser aplicado por usuários finais ou [aplicados automaticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) identificando informações confidenciais, palavras-chave ou tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8b315-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="8b315-110">**Migrar e gerenciar seu plano de retenção com o plano de arquivo** e usar o [gerenciador de planos de arquivo](file-plan-manager.md) para reunir seu plano de retenção existente ou criar um novo com os descritores de arquivo e expandir as hierarquias.</span><span class="sxs-lookup"><span data-stu-id="8b315-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="8b315-111">**Estabeleça políticas de retenção e exclusão**.</span><span class="sxs-lookup"><span data-stu-id="8b315-111">**Establish retention and deletion policies**.</span></span> <span data-ttu-id="8b315-112">Defina os períodos de [retenção](retention-policies.md#retaining-content-for-a-specific-period-of-time) e [disposição](retention-policies.md#deleting-content-thats-older-than-a-specific-age) com base em vários fatores, incluindo a data da última modificação ou criação.</span><span class="sxs-lookup"><span data-stu-id="8b315-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="8b315-113">**Acione a retenção baseada em eventos** com [retenção baseada em eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="8b315-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="8b315-114">**Examine e valide o descarte** com [revisões de descarte](disposition.md#disposition-reviews) e a prova de [exclusão de registros](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="8b315-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="8b315-115">**Exportar informações sobre todos os itens descartados** com a [opção exportar](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="8b315-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="8b315-116">**Defina permissões** específicas para as funções do Gerenciador de registros em [sua organização para que](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ele tenha o acesso certo.</span><span class="sxs-lookup"><span data-stu-id="8b315-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="8b315-117">Com a solução de gerenciamento de registros no Microsoft 365, você pode incorporar as agendas de retenção da sua organização ao plano de arquivo para gerenciar a retenção, a declaração de registros e o descarte para apoiar todo o ciclo de vida do seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8b315-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
