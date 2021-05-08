---
title: Governança de Informações da Microsoft no Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: Implementar recursos de Governança de Informações da Microsoft para controlar seus dados para conformidade ou requisitos regulatórios.
ms.openlocfilehash: 304b4e57702c55242e49fae7fdf4a36e9b2f7cdb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244559"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a><span data-ttu-id="d8b92-103">Governança de Informações da Microsoft no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d8b92-103">Microsoft Information Governance in Microsoft 365</span></span>

><span data-ttu-id="d8b92-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="d8b92-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="d8b92-105">Use os recursos da Governança de Informações da Microsoft (às vezes, abreviado como MIG) para controlar seus dados e atender aos requisitos normativos ou de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d8b92-105">Use Microsoft Information Governance (sometimes abbreviated to MIG) capabilities to govern your data for compliance or regulatory requirements.</span></span>

![Controle seus dados: governança de informações e gerenciamento de registros](../media/information-governance-records-management.png)

<span data-ttu-id="d8b92-107">Deseja proteger seus dados?</span><span class="sxs-lookup"><span data-stu-id="d8b92-107">Looking to protect your data?</span></span> <span data-ttu-id="d8b92-108">Confira [Proteção de Informações da Microsoft no Microsoft 365](information-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d8b92-108">See [Microsoft Information Protection in Microsoft 365](information-protection.md).</span></span>

<span data-ttu-id="d8b92-109">Para ajudá-lo a estar em conformidade com os regulamentos de privacidade de dados, criamos um fluxo de trabalho para orientá-lo em um processo de ponta a ponta para planejar e implementar recursos no Microsoft 365, incluindo acesso seguro, proteção contra ameaças, proteção de informações e governança de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b92-109">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including secure access, threat protection, information protection, and data governance.</span></span> <span data-ttu-id="d8b92-110">Para obter mais informações, consulte [Implantar a proteção de informações para regulamentos de privacidade de dados com o Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="d8b92-110">For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 

## <a name="information-governance"></a><span data-ttu-id="d8b92-111">Governança de informações</span><span class="sxs-lookup"><span data-stu-id="d8b92-111">Information governance</span></span>

<span data-ttu-id="d8b92-112">Para manter o que você precisa e excluir o que não:</span><span class="sxs-lookup"><span data-stu-id="d8b92-112">To keep what you need and delete what you don't:</span></span>
 
|<span data-ttu-id="d8b92-113">Recursos</span><span class="sxs-lookup"><span data-stu-id="d8b92-113">Capability</span></span>|<span data-ttu-id="d8b92-114">Que problemas ela resolve?</span><span class="sxs-lookup"><span data-stu-id="d8b92-114">What problems does it solve?</span></span>|<span data-ttu-id="d8b92-115">Introdução</span><span class="sxs-lookup"><span data-stu-id="d8b92-115">Get started</span></span>|
|:------|:------------|:--------------------|:-----------------------------|
|[<span data-ttu-id="d8b92-116">Políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="d8b92-116">Retention policies and retention labels</span></span>](retention.md)| <span data-ttu-id="d8b92-117">Manter ou excluir conteúdo com o gerenciamento de políticas e um fluxo de trabalho de exclusão para emails, documentos, mensagens instantâneas e muito mais</span><span class="sxs-lookup"><span data-stu-id="d8b92-117">Retain or delete content with policy management and a deletion workflow for email, documents, instant messages, and more</span></span> <br /><br /><span data-ttu-id="d8b92-118">Cenário de exemplo: [Aplicar um rótulo de retenção ao conteúdo automaticamente](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="d8b92-118">Example scenario: [Apply a retention label to content automatically](apply-retention-labels-automatically.md)</span></span> | [<span data-ttu-id="d8b92-119">Introdução às políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="d8b92-119">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)|
|[<span data-ttu-id="d8b92-120">Serviço de importação</span><span class="sxs-lookup"><span data-stu-id="d8b92-120">Import service</span></span>](importing-pst-files-to-office-365.md)| <span data-ttu-id="d8b92-121">Importar em massa arquivos PST para as caixas de correio do Exchange Online para manter e pesquisar mensagens de email e atender aos requisitos normativos ou de conformidade</span><span class="sxs-lookup"><span data-stu-id="d8b92-121">Bulk-import PST files to Exchange Online mailboxes to retain and search email messages for compliance or regulatory requirements</span></span> | [<span data-ttu-id="d8b92-122">Usar o carregamento de rede para importar arquivos PST da organização para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d8b92-122">Use network upload to import your organization's PST files to Microsoft 365</span></span>](use-network-upload-to-import-pst-files.md)|
|[<span data-ttu-id="d8b92-123">Arquivar dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="d8b92-123">Archive third-party data</span></span>](archiving-third-party-data.md)| <span data-ttu-id="d8b92-124">Importe, arquive e aplique soluções de conformidade a dados de terceiros a partir de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos</span><span class="sxs-lookup"><span data-stu-id="d8b92-124">Import, archive, and apply compliance solutions to third-party data from social media platforms, instant messaging platforms, and document collaboration platforms</span></span>| [<span data-ttu-id="d8b92-125">Conectores de terceiros</span><span class="sxs-lookup"><span data-stu-id="d8b92-125">Third-party connectors</span></span>](archiving-third-party-data.md#third-party-data-connectors)|
|[<span data-ttu-id="d8b92-126">Caixas de correio inativas</span><span class="sxs-lookup"><span data-stu-id="d8b92-126">Inactive mailboxes</span></span>](inactive-mailboxes-in-office-365.md)| <span data-ttu-id="d8b92-127">Manter o conteúdo da caixa de correio após sair da organização</span><span class="sxs-lookup"><span data-stu-id="d8b92-127">Retain mailbox content after employees leave the organization</span></span> | [<span data-ttu-id="d8b92-128">Criar e gerenciar caixas de correio inativas</span><span class="sxs-lookup"><span data-stu-id="d8b92-128">Create and manage inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a><span data-ttu-id="d8b92-129">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="d8b92-129">Records management</span></span>

<span data-ttu-id="d8b92-130">Para gerenciar o conteúdo de alto valor para obrigações legais, comerciais ou normativas:</span><span class="sxs-lookup"><span data-stu-id="d8b92-130">To manage high-value content for legal, business, or regulatory obligations:</span></span>

|<span data-ttu-id="d8b92-131">Recursos</span><span class="sxs-lookup"><span data-stu-id="d8b92-131">Capability</span></span>|<span data-ttu-id="d8b92-132">Que problemas ela resolve?</span><span class="sxs-lookup"><span data-stu-id="d8b92-132">What problems does it solve?</span></span>|<span data-ttu-id="d8b92-133">Introdução</span><span class="sxs-lookup"><span data-stu-id="d8b92-133">Get started</span></span>|
|:------|:------------|---------------------|:----------------------------|
|[<span data-ttu-id="d8b92-134">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="d8b92-134">Records management</span></span>](records-management.md)| <span data-ttu-id="d8b92-135">Uma solução única para emails e documentos que incorpora cronogramas e requisitos de retenção em um plano de arquivo que oferece suporte a todo o ciclo de vida do conteúdo com declaração, retenção e descarte de registros</span><span class="sxs-lookup"><span data-stu-id="d8b92-135">A single solution for email and documents that incorporates retention schedules and requirements into a file plan that supports the full lifecycle of your content with records declaration, retention, and disposition</span></span> <br /><br /><span data-ttu-id="d8b92-136">Cenário de exemplo: [descarte de registros](disposition.md#disposition-of-records)</span><span class="sxs-lookup"><span data-stu-id="d8b92-136">Example scenario: [Disposition of records](disposition.md#disposition-of-records)</span></span>|[<span data-ttu-id="d8b92-137">Introdução ao gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="d8b92-137">Get started with records management</span></span>](get-started-with-records-management.md) |