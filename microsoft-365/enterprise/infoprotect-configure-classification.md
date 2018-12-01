---
title: 'Etapa 2: Configurar classificações de ambiente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar várias maneiras para classificar os dados em sua organização.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864877"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="88cde-103">Etapa 2: Configurar classificações de ambiente</span><span class="sxs-lookup"><span data-stu-id="88cde-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="88cde-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="88cde-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="88cde-105">Nesta etapa, você trabalha com as equipes de conformidade e jurídica para definir um esquema de classificação dos dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="88cde-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="88cde-106">Classificações da Microsoft</span><span class="sxs-lookup"><span data-stu-id="88cde-106">Microsoft classifications</span></span>

<span data-ttu-id="88cde-107">O Microsoft 365 inclui três tipos de classificação:</span><span class="sxs-lookup"><span data-stu-id="88cde-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="88cde-108">Tipos de informações confidenciais no Office 365</span><span class="sxs-lookup"><span data-stu-id="88cde-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="88cde-109">Rótulos do Office 365</span><span class="sxs-lookup"><span data-stu-id="88cde-109">Office 365 labels</span></span>
- <span data-ttu-id="88cde-110">Proteção e rótulos de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="88cde-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="88cde-111">Tipos de informações confidenciais no Office 365</span><span class="sxs-lookup"><span data-stu-id="88cde-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="88cde-p101">Os tipos de informações confidenciais do Office 365 definem como os processos automatizados, como a pesquisa, reconhecem os tipos específicos de informações, como os números da segurança social e de cartões de crédito. Usamos os tipos de informações confidenciais para localizar os dados confidenciais e aplicar regras e políticas de prevenção contra perda de dados para proteger esses dados. Saiba mais em [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Por exemplo, os tipos de informações confidenciais são especialmente úteis para atender aos requisitos de regulamentação e conformidade, como o GDPR (Regulamento Geral sobre a Proteção de Dados).</span><span class="sxs-lookup"><span data-stu-id="88cde-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="88cde-116">Rótulos do Office 365</span><span class="sxs-lookup"><span data-stu-id="88cde-116">Office 365 labels</span></span>
<span data-ttu-id="88cde-p102">É possível usar os rótulos do Office 365 para dados pessoais e para arquivos secretos comerciais e altamente controlados armazenados no SharePoint Online e no OneDrive for Business. Para saber mais, inclusive como criá-los, confira [Visão geral de rótulos](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span><span class="sxs-lookup"><span data-stu-id="88cde-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="88cde-p103">Se decidir usar rótulos do Office 365, configure pelo menos um rótulo para cada nível de proteção. Por exemplo, crie três rótulos para:</span><span class="sxs-lookup"><span data-stu-id="88cde-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="88cde-121">Linha de base</span><span class="sxs-lookup"><span data-stu-id="88cde-121">Baseline</span></span>
- <span data-ttu-id="88cde-122">Confidencial</span><span class="sxs-lookup"><span data-stu-id="88cde-122">Sensitive</span></span>
- <span data-ttu-id="88cde-123">Altamente controlado</span><span class="sxs-lookup"><span data-stu-id="88cde-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="88cde-124">Proteção e rótulos de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="88cde-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="88cde-p104">É possível usar rótulos de Proteção de Informações do Azure para classificar e, opcionalmente, proteger documentos e emails da organização. Eles podem ser aplicados aos documentos que estão armazenados fora do Office 365 e também podem ser aplicados automaticamente pelos administradores que definem as regras e as condições, manualmente por usuários ou uma combinação onde os usuários recebem recomendações.</span><span class="sxs-lookup"><span data-stu-id="88cde-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="88cde-128">Para planejar e implantar a proteção e os rótulos de Proteção de Informações do Azure, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88cde-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="88cde-129">Revise os [Requisitos de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="88cde-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="88cde-130">Siga o [Roteiro de implantação para classificação, rotulamento e proteção](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="88cde-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="88cde-131">Veja mais informações na [Biblioteca de documentação de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="88cde-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="88cde-132">Classificação para GDPR</span><span class="sxs-lookup"><span data-stu-id="88cde-132">Classification for GDPR</span></span>

<span data-ttu-id="88cde-133">Confira um exemplo de esquema de classificação que inclui os dados pessoais para GDPR em [Desenvolver um esquema de classificação para dados pessoais](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="88cde-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="88cde-135">Guia do Laboratório de Teste: Classificação de dados</span><span class="sxs-lookup"><span data-stu-id="88cde-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="88cde-136">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="88cde-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="88cde-137">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="88cde-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="88cde-138">Configurar mais segurança no Office 365</span><span class="sxs-lookup"><span data-stu-id="88cde-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

