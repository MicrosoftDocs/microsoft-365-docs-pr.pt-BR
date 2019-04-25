---
title: 'Etapa 2: Configurar classificações de ambiente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar várias maneiras para classificar os dados em sua organização.
ms.openlocfilehash: ca64b98bceb6f969adc964e93a6a1cc872763199
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286969"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="9dea6-103">Etapa 2: Configurar classificações de ambiente</span><span class="sxs-lookup"><span data-stu-id="9dea6-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="9dea6-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9dea6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="9dea6-105">Nesta etapa, você trabalha com as equipes de conformidade e jurídica para definir um esquema de classificação dos dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dea6-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="9dea6-106">Tipos de classificação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9dea6-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="9dea6-107">O Microsoft 365 inclui quatro tipos de classificação:</span><span class="sxs-lookup"><span data-stu-id="9dea6-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="9dea6-108">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="9dea6-108">Sensitive information types</span></span>
- <span data-ttu-id="9dea6-109">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="9dea6-109">Retention labels</span></span>
- <span data-ttu-id="9dea6-110">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="9dea6-110">Sensitivity labels</span></span>
- <span data-ttu-id="9dea6-111">Proteção e rótulos de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="9dea6-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="9dea6-112">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="9dea6-112">Sensitive information types</span></span>

<span data-ttu-id="9dea6-113">Tipos de informações confidenciais para o Microsoft 365 definem como processos automatizados como pesquisar e reconhecer tipos específicos de informações.</span><span class="sxs-lookup"><span data-stu-id="9dea6-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="9dea6-114">Isso inclui informações confidenciais de funcionários ou dados de clientes como números do serviço de saúde e números de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="9dea6-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="9dea6-115">Você usa tipos de informações confidenciais para encontrar dados confidenciais e aplica as regras e políticas da prevenção contra perda de dados (DLP) para protegê-los.</span><span class="sxs-lookup"><span data-stu-id="9dea6-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="9dea6-116">Para saber mais, confira [o que uma política de DLP contém](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="9dea6-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="9dea6-117">Tipos de informações confidenciais são especialmente úteis para cumprir exigências de conformidade e regulatórias, como para o Regulamento Geral de Proteção de Dados (GDPR).</span><span class="sxs-lookup"><span data-stu-id="9dea6-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="9dea6-118">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="9dea6-118">Retention labels</span></span>

<span data-ttu-id="9dea6-119">Parte de definir uma estratégia de governança de dados é decidir por quanto tempo tipos específicos de documentos ou documentos com conteúdos específicos devem ser retidos em conformidade com políticas de organização e regulamentos regionais.</span><span class="sxs-lookup"><span data-stu-id="9dea6-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="9dea6-120">Por exemplo, alguns tipos de documentos devem ser retidos por um período específico de tempo e depois apagados e outros devem ser retidos por tempo indeterminado.</span><span class="sxs-lookup"><span data-stu-id="9dea6-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="9dea6-121">Para documentos armazenados no Microsoft 365, você define e aplica rótulos de retenção a documentos e dados armazenados no email do Exchange, SharePoint, OneDrive for Business e mensagens de canal e chat do Teams.</span><span class="sxs-lookup"><span data-stu-id="9dea6-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> <span data-ttu-id="9dea6-122">Para mais informações, incluindo como criá-los, confira [Visão geral dos rótulos de retenção](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="9dea6-122">For more information, including how to create them, see [Overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

<span data-ttu-id="9dea6-123">Se você usar rótulos de retenção, deve configurar um rótulo para cada categoria de arquivo que precisa de uma política de retenção aplicada.</span><span class="sxs-lookup"><span data-stu-id="9dea6-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="9dea6-124">No rótulo de retenção, você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="9dea6-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="9dea6-125">Um conjunto de descritores para os arquivos (por exemplo, por departamento empresarial, categoria de arquivo ou regulamento).</span><span class="sxs-lookup"><span data-stu-id="9dea6-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>

- <span data-ttu-id="9dea6-126">As configurações de retenção para os arquivos que possuem um rótulo de retenção anexado, como horários e comportamentos de retenção depois que atingirem o tempo de retenção.</span><span class="sxs-lookup"><span data-stu-id="9dea6-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="9dea6-127">Você também pode aplicar automaticamente um rótulo de retenção aos arquivos configurando um site do SharePoint online para aplicar um rótulo de retenção padrão para todos os novos documentos no site.</span><span class="sxs-lookup"><span data-stu-id="9dea6-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="9dea6-128">Para saber mais, veja a [visão geral dos rótulos de retenção](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="9dea6-128">For more information, see this [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="9dea6-129">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="9dea6-129">Sensitivity labels</span></span>

<span data-ttu-id="9dea6-130">Parte de proteger e implementar a segurança para tipos específicos de documentos ou documentos com conteúdos específicos é marcá-los com um rótulo para que a segurança adicional possa ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="9dea6-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="9dea6-131">Com rótulos de confidencialidade no Microsoft 365, você pode:</span><span class="sxs-lookup"><span data-stu-id="9dea6-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="9dea6-132">Impor configurações de proteção como criptografia, permissões ou adicionar uma marca d´água.</span><span class="sxs-lookup"><span data-stu-id="9dea6-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>

- <span data-ttu-id="9dea6-133">Evitar que conteúdo confidencial saia de sua organização em dispositivos executando o Windows, usando a proteção de pontos de extremidade no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="9dea6-133">Prevent sensitive content from leaving your organization on devices running Windows, by using endpoint protection in Microsoft Intune.</span></span> 

- <span data-ttu-id="9dea6-134">Usar a proteção de pontos de extremidade da Proteção de Informações do Windows (WIP) para evitar que um conteúdo seja copiado para um aplicativo de terceiros, como Twitter ou Gmail, ou que seja copiado para armazenamento removível, como uma unidade USB. </span><span class="sxs-lookup"><span data-stu-id="9dea6-134">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>

- <span data-ttu-id="9dea6-135">Usar Segurança no Aplicativo de Nuvem da Microsoft para proteger conteúdo em aplicativos e serviços de terceiros.</span><span class="sxs-lookup"><span data-stu-id="9dea6-135">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 

- <span data-ttu-id="9dea6-136">Classificar conteúdo sem usar nenhuma configuração de proteção.</span><span class="sxs-lookup"><span data-stu-id="9dea6-136">Classify content without using any protection settings.</span></span>

<span data-ttu-id="9dea6-137">Se você usar rótulos de confidencialidade, você deve configurar um rótulo para cada nível de segurança e proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="9dea6-137">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="9dea6-138">Por exemplo, crie três rótulos de confidencialidade para:</span><span class="sxs-lookup"><span data-stu-id="9dea6-138">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="9dea6-139">Linha de base</span><span class="sxs-lookup"><span data-stu-id="9dea6-139">Baseline</span></span>

- <span data-ttu-id="9dea6-140">Confidencial</span><span class="sxs-lookup"><span data-stu-id="9dea6-140">Sensitive</span></span>

- <span data-ttu-id="9dea6-141">Altamente controlado</span><span class="sxs-lookup"><span data-stu-id="9dea6-141">Highly regulated</span></span>

<span data-ttu-id="9dea6-142">Para saber mais, confira a [visão geral de rótulos de confidencialidade](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="9dea6-142">For more information, see [Overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="9dea6-143">Proteção e rótulos de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="9dea6-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="9dea6-144">Você pode usar os rótulos de Proteção de Informações do Azure para classificar e, opcionalmente, proteger os documentos e emails da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dea6-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="9dea6-145">Esses rótulos podem se aplicar a documentos que são armazenados fora do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9dea6-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="9dea6-146">Esses rótulos podem ser aplicados automaticamente por administradores que definem regras e condições manualmente por usuários, ou uma combinação onde usuários recebem recomendações.</span><span class="sxs-lookup"><span data-stu-id="9dea6-146">This can be done automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="9dea6-147">Para planejar e implantar a proteção e os rótulos de Proteção de Informações do Azure, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9dea6-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="9dea6-148">Revise os [Requisitos de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="9dea6-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="9dea6-149">Siga o [Roteiro de implantação para classificação, rotulamento e proteção](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="9dea6-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="9dea6-150">Veja mais informações na [Biblioteca de documentação de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="9dea6-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="9dea6-151">Rótulos existentes de Proteção de Informações do Azure funcionam perfeitamente com rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="9dea6-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="9dea6-152">Por exemplo, você pode manter seus rótulos existentes de Proteção de Informações do Azure e os rótulos que são aplicados aos documentos e email.</span><span class="sxs-lookup"><span data-stu-id="9dea6-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="9dea6-153">Se você tem tanto os rótulos de confidencialidade como os rótulos de Proteção de Informações do Azure, você deve [migrar seus rótulos de Proteção de Informações do Azure para rótulos de confidencialidade](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="9dea6-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="9dea6-154">Exemplo: Classificação para GDPR</span><span class="sxs-lookup"><span data-stu-id="9dea6-154">Classification for GDPR</span></span>

<span data-ttu-id="9dea6-155">Confira um exemplo de esquema de classificação que inclui os dados pessoais para GDPR em [Desenvolver um esquema de classificação para dados pessoais](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="9dea6-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9dea6-157">Guia do Laboratório de Teste: Classificação de dados</span><span class="sxs-lookup"><span data-stu-id="9dea6-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="9dea6-158">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="9dea6-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="9dea6-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9dea6-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="9dea6-160">Configurar mais segurança no Office 365</span><span class="sxs-lookup"><span data-stu-id="9dea6-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

