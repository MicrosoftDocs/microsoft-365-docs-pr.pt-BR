---
title: 'Etapa 2: Configurar classificações de ambiente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar várias maneiras para classificar os dados em sua organização.
ms.openlocfilehash: ca1b4aefca7ee63f1c8fe098c115fc4f0074d9f6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047294"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="41680-103">Etapa 2: Configurar classificações de ambiente</span><span class="sxs-lookup"><span data-stu-id="41680-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="41680-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="41680-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="41680-105">Nesta etapa, você trabalha com as equipes de conformidade e jurídica para definir um esquema de classificação dos dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="41680-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="41680-106">Tipos de classificação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41680-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="41680-107">O Microsoft 365 inclui quatro tipos de classificação:</span><span class="sxs-lookup"><span data-stu-id="41680-107">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="41680-108">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="41680-108">Sensitive information types</span></span>
- <span data-ttu-id="41680-109">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="41680-109">Retention labels</span></span>
- <span data-ttu-id="41680-110">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="41680-110">Sensitivity labels</span></span>
- <span data-ttu-id="41680-111">Proteção e rótulos de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="41680-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="41680-112">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="41680-112">Sensitive information types</span></span>

<span data-ttu-id="41680-113">Tipos de informações confidenciais para o Microsoft 365 definem como processos automatizados como pesquisar e reconhecer tipos específicos de informações.</span><span class="sxs-lookup"><span data-stu-id="41680-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="41680-114">Isso inclui informações confidenciais de funcionários ou dados de clientes como números do serviço de saúde e números de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="41680-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="41680-115">Você usa tipos de informações confidenciais para encontrar dados confidenciais e aplica as regras e políticas da prevenção contra perda de dados (DLP) para protegê-los.</span><span class="sxs-lookup"><span data-stu-id="41680-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="41680-116">Para saber mais, confira [o que uma política de DLP contém](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="41680-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="41680-117">Tipos de informações confidenciais são especialmente úteis para cumprir exigências de conformidade e regulatórias, como para o Regulamento Geral de Proteção de Dados (GDPR).</span><span class="sxs-lookup"><span data-stu-id="41680-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="41680-118">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="41680-118">Retention labels</span></span>

<span data-ttu-id="41680-119">Parte de definir uma estratégia de governança de dados é decidir por quanto tempo tipos específicos de documentos ou documentos com conteúdos específicos devem ser retidos em conformidade com políticas de organização e regulamentos regionais.</span><span class="sxs-lookup"><span data-stu-id="41680-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="41680-120">Por exemplo, alguns tipos de documentos devem ser retidos por um período específico de tempo e depois apagados e outros devem ser retidos por tempo indeterminado.</span><span class="sxs-lookup"><span data-stu-id="41680-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="41680-121">Para documentos armazenados no Microsoft 365, você define e aplica rótulos de retenção a documentos e dados armazenados no email do Exchange, SharePoint, OneDrive for Business e mensagens de canal e chat do Teams.</span><span class="sxs-lookup"><span data-stu-id="41680-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="41680-122">Se você usar rótulos de retenção, deve configurar um rótulo para cada categoria de arquivo que precisa de uma política de retenção aplicada.</span><span class="sxs-lookup"><span data-stu-id="41680-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="41680-123">No rótulo de retenção, você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="41680-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="41680-124">Um conjunto de descritores para os arquivos (por exemplo, por departamento empresarial, categoria de arquivo ou regulamento).</span><span class="sxs-lookup"><span data-stu-id="41680-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="41680-125">As configurações de retenção para os arquivos que possuem um rótulo de retenção anexado, como horários e comportamentos de retenção depois que atingirem o tempo de retenção.</span><span class="sxs-lookup"><span data-stu-id="41680-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="41680-126">Você também pode aplicar automaticamente um rótulo de retenção aos arquivos configurando um site do SharePoint online para aplicar um rótulo de retenção padrão para todos os novos documentos no site.</span><span class="sxs-lookup"><span data-stu-id="41680-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="41680-127">Para mais informações, confira a [visão geral dos rótulos de retenção](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="41680-127">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="41680-128">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="41680-128">Sensitivity labels</span></span>

<span data-ttu-id="41680-129">Parte de proteger e implementar a segurança para tipos específicos de documentos ou documentos com conteúdos específicos é marcá-los com um rótulo para que a segurança adicional possa ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="41680-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="41680-130">Com rótulos de confidencialidade no Microsoft 365, você pode:</span><span class="sxs-lookup"><span data-stu-id="41680-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="41680-131">Impor configurações de proteção como criptografia, permissões ou adicionar uma marca d´água.</span><span class="sxs-lookup"><span data-stu-id="41680-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="41680-132">Usar a proteção de pontos de extremidade da Proteção de Informações do Windows (WIP) para evitar que um conteúdo seja copiado para um aplicativo de terceiros, como Twitter ou Gmail, ou que seja copiado para armazenamento removível, como uma unidade USB. </span><span class="sxs-lookup"><span data-stu-id="41680-132">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="41680-133">Usar o Microsoft Cloud App Security (CAS) para proteger conteúdo em aplicativos e serviços de terceiros.</span><span class="sxs-lookup"><span data-stu-id="41680-133">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="41680-134">Classificar conteúdo sem usar nenhuma configuração de proteção.</span><span class="sxs-lookup"><span data-stu-id="41680-134">Classify content without using any protection settings.</span></span>

<span data-ttu-id="41680-135">Se você usar rótulos de confidencialidade, você deve configurar um rótulo para cada nível de segurança e proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="41680-135">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="41680-136">Por exemplo, crie três rótulos de confidencialidade para:</span><span class="sxs-lookup"><span data-stu-id="41680-136">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="41680-137">Linha de base</span><span class="sxs-lookup"><span data-stu-id="41680-137">Baseline</span></span>
- <span data-ttu-id="41680-138">Confidencial</span><span class="sxs-lookup"><span data-stu-id="41680-138">Sensitive</span></span>
- <span data-ttu-id="41680-139">Altamente controlado</span><span class="sxs-lookup"><span data-stu-id="41680-139">Highly regulated</span></span>

<span data-ttu-id="41680-140">Caso armazene arquivos com dados altamente regulamentados em um site do SharePoint Online e quiser que esses arquivos tenham as mesmas permissões que o site se os arquivos saírem do site, será necessário criar um rótulo de confidencialidade adicional cujas permissões sejam as mesmas do site.</span><span class="sxs-lookup"><span data-stu-id="41680-140">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="41680-141">Para saber mais, confira a [visão geral de rótulos de confidencialidade](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="41680-141">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="41680-142">Proteção e rótulos de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="41680-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="41680-143">Você pode usar os rótulos de Proteção de Informações do Azure para classificar e, opcionalmente, proteger os documentos e emails da sua organização.</span><span class="sxs-lookup"><span data-stu-id="41680-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="41680-144">Esses rótulos podem se aplicar a documentos que são armazenados fora do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41680-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="41680-145">Esses rótulos podem ser aplicados automaticamente por administradores que definem regras e condições manualmente por usuários, ou uma combinação onde usuários recebem recomendações.</span><span class="sxs-lookup"><span data-stu-id="41680-145">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="41680-146">Para planejar e implantar a proteção e os rótulos de Proteção de Informações do Azure, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="41680-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="41680-147">Revise os [Requisitos de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="41680-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="41680-148">Siga o [Roteiro de implantação para classificação, rotulamento e proteção](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="41680-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="41680-149">Veja mais informações na [Biblioteca de documentação de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="41680-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="41680-150">Rótulos existentes de Proteção de Informações do Azure funcionam perfeitamente com rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="41680-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="41680-151">Por exemplo, você pode manter seus rótulos existentes de Proteção de Informações do Azure e os rótulos que são aplicados aos documentos e email.</span><span class="sxs-lookup"><span data-stu-id="41680-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="41680-152">Se você tem tanto os rótulos de confidencialidade como os rótulos de Proteção de Informações do Azure, você deve [migrar seus rótulos de Proteção de Informações do Azure para rótulos de confidencialidade](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="41680-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="41680-153">Exemplo: Classificação para GDPR</span><span class="sxs-lookup"><span data-stu-id="41680-153">Example: Classification for GDPR</span></span>

<span data-ttu-id="41680-154">Confira um exemplo de esquema de classificação que inclui os dados pessoais para GDPR em [Desenvolver um esquema de classificação para dados pessoais](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="41680-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="41680-155">Levar para um test drive</span><span class="sxs-lookup"><span data-stu-id="41680-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="41680-157">Guia do Laboratório de Teste: Classificação de dados</span><span class="sxs-lookup"><span data-stu-id="41680-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="41680-158">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step2) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="41680-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="41680-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="41680-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="41680-160">Configurar mais segurança no Office 365</span><span class="sxs-lookup"><span data-stu-id="41680-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

