---
title: Use o verificador local de prevenção contra perda de dados do Microsoft 365 (pré-visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Aprenda a usar o verificador local de prevenção contra perda de dados do  Microsoft 365 para examinar dados inativos e implementar ações de proteção para compartilhamentos de arquivos locais e pastas e bibliotecas de documentos locais do SharePoint.
ms.openlocfilehash: 0abe36af5588c1828da106779a144b6e7f37d6a8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114149"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="6d817-103">Use o verificador local de prevenção contra perda de dados do Microsoft 365 (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="6d817-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="6d817-104">Para ajudar a se familiarizar com os recursos locais do DLP e como eles aparecem nas políticas DLP, reunimos alguns cenários para você seguir.</span><span class="sxs-lookup"><span data-stu-id="6d817-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d817-105">Esses cenários locais de DLP não são os procedimentos oficiais para criar e ajustar políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="6d817-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="6d817-106">Confira os tópicos a seguir quando você precisar trabalhar com políticas de DLP em situações gerais:</span><span class="sxs-lookup"><span data-stu-id="6d817-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="6d817-107">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="6d817-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="6d817-108">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="6d817-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="6d817-109">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="6d817-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="6d817-110">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="6d817-111">Cenário: descobra arquivos que correspondem às regras de DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="6d817-112">Dados de superfícies de verificação local DLP em várias áreas</span><span class="sxs-lookup"><span data-stu-id="6d817-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="6d817-113">Explorador de atividade </span><span class="sxs-lookup"><span data-stu-id="6d817-113">Activity explorer</span></span>

 <span data-ttu-id="6d817-114">O DLP local da Microsoft detecta correspondências de regras de DLP e as relata ao [Explorador de Atividade](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="6d817-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="6d817-115">Log de auditoria do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d817-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="6d817-116">Durante a visualização pública, as correspondências de regras de DLP estão disponíveis na UI, consulte [Pesquisar o log de auditoria no centro de conformidade](search-the-audit-log-in-security-and-compliance.md)  ou acessíveis por [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d817-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="6d817-117">AIP</span><span class="sxs-lookup"><span data-stu-id="6d817-117">AIP</span></span>

<span data-ttu-id="6d817-118">Os dados de descoberta estão disponíveis em um relatório local no formato csv, que é armazenado em:</span><span class="sxs-lookup"><span data-stu-id="6d817-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="6d817-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="6d817-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="6d817-120">Procure as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="6d817-120">Look for the following columns:</span></span>
- <span data-ttu-id="6d817-121">Modo DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-121">DLP Mode</span></span>
- <span data-ttu-id="6d817-122">Status DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-122">DLP Status</span></span>
- <span data-ttu-id="6d817-123">Comentário DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-123">DLP Comment</span></span>
- <span data-ttu-id="6d817-124">Nome da regra DLP Ações DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="6d817-125">Proprietário</span><span class="sxs-lookup"><span data-stu-id="6d817-125">Owner</span></span>
- <span data-ttu-id="6d817-126">Permissões NTFS atuais (SDDL)</span><span class="sxs-lookup"><span data-stu-id="6d817-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="6d817-127">Permissões NTFS aplicadas (SDDL)</span><span class="sxs-lookup"><span data-stu-id="6d817-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="6d817-128">Tipo de permissões NTFS</span><span class="sxs-lookup"><span data-stu-id="6d817-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="6d817-129">Cenário: impor regra DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="6d817-130">Se você deseja impor regras DLP nos arquivos verificados, a imposição deve ser habilitada tanto no trabalho de verificação de conteúdo no AIP e no nível de política no DLP.</span><span class="sxs-lookup"><span data-stu-id="6d817-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="6d817-131">Configure o DLP para impor ações de política</span><span class="sxs-lookup"><span data-stu-id="6d817-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="6d817-132">Abra a [página de prevenção contra perda de dadose](https://compliance.microsoft.com/datalossprevention?viewid=policies) e selecione a política DLP que é direcionada aos repositórios locais que você configurou no AIP.</span><span class="sxs-lookup"><span data-stu-id="6d817-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="6d817-133">Edite a política.</span><span class="sxs-lookup"><span data-stu-id="6d817-133">Edit the policy.</span></span>
3. <span data-ttu-id="6d817-134">Na página **Testar ou ativar a política**, selecione **Sim, ativá-la imediatamente**.</span><span class="sxs-lookup"><span data-stu-id="6d817-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6d817-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d817-135">See also</span></span>

- [<span data-ttu-id="6d817-136">Saiba mais sobre o verificador local DLP (visualização)</span><span class="sxs-lookup"><span data-stu-id="6d817-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="6d817-137">Começar com a verificação DLP local (visualização)</span><span class="sxs-lookup"><span data-stu-id="6d817-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="6d817-138">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="6d817-138">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="6d817-139">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="6d817-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6d817-140">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="6d817-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)