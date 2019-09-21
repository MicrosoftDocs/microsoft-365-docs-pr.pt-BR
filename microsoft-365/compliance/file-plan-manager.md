---
title: Visão geral do gerenciador de planos de arquivo
ms.author: stephow
author: stephow-MSFT
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
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: O gerenciador de planos de arquivo fornece recursos avançados de gerenciamento de políticas e rótulos de retenção, políticas de rótulos de retenção e oferece uma maneira integrada de percorrer a atividade de rótulos e de rótulo para conteúdo para todo o seu ciclo de vida de conteúdo, desde a criação à colaboração, declaração de registros, retenção e por fim, à disposição.
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072745"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="ba55b-103">Visão geral do gerenciador de planos de arquivo</span><span class="sxs-lookup"><span data-stu-id="ba55b-103">Overview of file plan manager</span></span>

<span data-ttu-id="ba55b-104">O gerenciador de planos de arquivo fornece recursos avançados de gerenciamento de políticas e rótulos de retenção, políticas de rótulos de retenção e oferece uma maneira integrada de percorrer a atividade de rótulos e de rótulo para conteúdo para todo o seu ciclo de vida de conteúdo, desde a criação à colaboração, declaração de registros, retenção e por fim, à disposição.</span><span class="sxs-lookup"><span data-stu-id="ba55b-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Página de plano de arquivo](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="ba55b-106">Acessar o gerenciador de planos de arquivo</span><span class="sxs-lookup"><span data-stu-id="ba55b-106">Accessing file plan manager</span></span>

<span data-ttu-id="ba55b-107">Há dois requisitos para acessar o gerenciador de planos de arquivo, que são:</span><span class="sxs-lookup"><span data-stu-id="ba55b-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="ba55b-108">Uma assinatura do Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="ba55b-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="ba55b-109">O usuário ter recebido uma das seguintes funções do Centro de Conformidade e Segurança:</span><span class="sxs-lookup"><span data-stu-id="ba55b-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="ba55b-110">Gerenciador de Retenção</span><span class="sxs-lookup"><span data-stu-id="ba55b-110">Retention Manager</span></span>
    - <span data-ttu-id="ba55b-111">Gerenciador de Retenção somente exibição</span><span class="sxs-lookup"><span data-stu-id="ba55b-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="ba55b-112">Rótulos de retenção e política de rótulos padrão</span><span class="sxs-lookup"><span data-stu-id="ba55b-112">Default retention labels and label policy</span></span>

<span data-ttu-id="ba55b-113">Se não houver rótulos de retenção na Central de Conformidade e Segurança, na primeira vez que você escolher **Planejamento de Arquivos** na navegação à esquerda, será criada uma política de rótulo chamada **Política Padrão de Publicação de Governança de Dados**.</span><span class="sxs-lookup"><span data-stu-id="ba55b-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="ba55b-114">Esta política de rótulo contém três etiquetas de retenção:</span><span class="sxs-lookup"><span data-stu-id="ba55b-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="ba55b-115">**Procedimento operacional**</span><span class="sxs-lookup"><span data-stu-id="ba55b-115">**Operational procedure**</span></span>
- <span data-ttu-id="ba55b-116">**Geral de negócios**</span><span class="sxs-lookup"><span data-stu-id="ba55b-116">**Business general**</span></span>
- <span data-ttu-id="ba55b-117">**Contrato**</span><span class="sxs-lookup"><span data-stu-id="ba55b-117">**Contract agreement**</span></span>

<span data-ttu-id="ba55b-118">Estes rótulos de retenção estão configurados apenas para reter conteúdo, e não para excluir conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="ba55b-119">Esta política de rótulos será publicada para toda a organização e poderá ser desativada ou removida.</span><span class="sxs-lookup"><span data-stu-id="ba55b-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="ba55b-120">Você pode determinar quem abriu o gerenciador de planejamento de arquivos e iniciou a primeira experiência de execução examinando as atividades **Política de retenção criada** e **Configuração de retenção criada para uma política de retenção** no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="ba55b-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="ba55b-121">Devido aos comentários dos clientes, removemos esse recurso que cria a política de rótulos de retenção e os rótulos de retenção padrão mencionados acima.</span><span class="sxs-lookup"><span data-stu-id="ba55b-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="ba55b-122">Você só verá os rótulos de retenção e a política de rótulos de retenção caso tenha aberto o gerenciador de planos de arquivo antes de 11 de abril de 2019.</span><span class="sxs-lookup"><span data-stu-id="ba55b-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="ba55b-123">Navegar pelo plano de arquivo</span><span class="sxs-lookup"><span data-stu-id="ba55b-123">Navigating your file plan</span></span>

<span data-ttu-id="ba55b-124">O gerente de plano de arquivo torna mais fácil ver todas as configurações dos seus rótulos e políticas de retenção no mesmo modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="ba55b-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="ba55b-125">Observe que os rótulos de retenção criados fora do plano de arquivamento estarão disponíveis no plano de arquivamento e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="ba55b-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="ba55b-126">Na guia **rótulos de plano de arquivo**, as seguintes informações e recursos adicionais estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ba55b-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="ba55b-127">Colunas de configurações de rótulo</span><span class="sxs-lookup"><span data-stu-id="ba55b-127">Label settings columns</span></span>

- <span data-ttu-id="ba55b-p103">**Com base em** identifica o tipo de gatilho que iniciará o período de retenção. Os valores válidos estão:</span><span class="sxs-lookup"><span data-stu-id="ba55b-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="ba55b-130">Evento</span><span class="sxs-lookup"><span data-stu-id="ba55b-130">Event</span></span>
    - <span data-ttu-id="ba55b-131">Data de criação</span><span class="sxs-lookup"><span data-stu-id="ba55b-131">When created</span></span>
    - <span data-ttu-id="ba55b-132">Data da última modificação</span><span class="sxs-lookup"><span data-stu-id="ba55b-132">When last modified</span></span>
    - <span data-ttu-id="ba55b-133">Data do rótulo</span><span class="sxs-lookup"><span data-stu-id="ba55b-133">When labeled</span></span>
- <span data-ttu-id="ba55b-p104">**Registro** identifica se o item se tornará um registro declarado quando o rótulo for aplicado. Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="ba55b-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="ba55b-136">Não</span><span class="sxs-lookup"><span data-stu-id="ba55b-136">No</span></span>
    - <span data-ttu-id="ba55b-137">Sim</span><span class="sxs-lookup"><span data-stu-id="ba55b-137">Yes</span></span>
    - <span data-ttu-id="ba55b-138">Sim (Regulatório)</span><span class="sxs-lookup"><span data-stu-id="ba55b-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="ba55b-p105">**Retenção** identifica o tipo de retenção. Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="ba55b-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="ba55b-141">Manter</span><span class="sxs-lookup"><span data-stu-id="ba55b-141">Keep</span></span>
    - <span data-ttu-id="ba55b-142">Manter e excluir</span><span class="sxs-lookup"><span data-stu-id="ba55b-142">Keep and delete</span></span>
    - <span data-ttu-id="ba55b-143">Excluir</span><span class="sxs-lookup"><span data-stu-id="ba55b-143">Delete</span></span>
- <span data-ttu-id="ba55b-p106">**Descarte** identifica o que acontecerá com o conteúdo no final do período de retenção. Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="ba55b-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="ba55b-146">null</span><span class="sxs-lookup"><span data-stu-id="ba55b-146">null</span></span>
    - <span data-ttu-id="ba55b-147">Nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="ba55b-147">No action</span></span>
    - <span data-ttu-id="ba55b-148">Excluir automaticamente</span><span class="sxs-lookup"><span data-stu-id="ba55b-148">Auto-delete</span></span>
    - <span data-ttu-id="ba55b-149">Revisão obrigatória (também conhecida como revisão de descarte)</span><span class="sxs-lookup"><span data-stu-id="ba55b-149">Review required (aka Disposition review)</span></span>

![Configurações de rótulos no plano de arquivo](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="ba55b-151">Colunas de descritores de plano de arquivo de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="ba55b-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="ba55b-p107">Agora você pode incluir mais informações na configuração das suas etiquetas de retenção. Inserir descritores de plano de arquivo em rótulos de retenção melhora o gerenciamento e a organização do seu plano de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="ba55b-p108">Para começar, o gerenciador de planos de arquivo fornece alguns valores prontos de origem para: Função/departamento, Categoria, Tipo de autoridade e Provisão/citação. Você pode adicionar novos valores descritores de planos de arquivo ao criar ou editar um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="ba55b-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="ba55b-156">Aqui está uma visão geral da etapa de descritores de plano de arquivo ao criar ou editar um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="ba55b-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descritores de plano de arquivo](media/file-plan-descriptors.png)

<span data-ttu-id="ba55b-158">Aqui está um modo de exibição das colunas de descritores de plano de arquivo na guia Rótulos do gerenciador de planos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="ba55b-160">Exportar todos os rótulos de retenção existentes para analisar e/ou executar revisões offline</span><span class="sxs-lookup"><span data-stu-id="ba55b-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="ba55b-161">No gerenciador de planos de arquivo, você pode exportar os detalhes de todos os rótulos de retenção para um arquivo .csv, para ajudá-lo a facilitar as avaliações de conformidade periódicas com os participantes de governança de dados na sua organização.</span><span class="sxs-lookup"><span data-stu-id="ba55b-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="ba55b-162">Para exportar todos os rótulos de retenção, acesse **gerenciador de planos de arquivo** \> **ações de plano de arquivo** \> **exportar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="ba55b-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opção para exportar o plano de arquivo](media/file-plan-export-labels-option.png)

<span data-ttu-id="ba55b-164">Um arquivo \*.csv que contém todos os rótulos de retenção existentes será aberto.</span><span class="sxs-lookup"><span data-stu-id="ba55b-164">A \*.csv file containing all existing retention labels will open.</span></span>

![Arquivo CSV mostrando todas as etiquetas de retenção](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="ba55b-166">Importar rótulos de retenção para seu plano de arquivo</span><span class="sxs-lookup"><span data-stu-id="ba55b-166">Import labels into your file plan</span></span>

<span data-ttu-id="ba55b-167">No gerenciador de planos de arquivo, você pode importar em massa novos rótulos de retenção, bem como modificar rótulos de retenção existentes.</span><span class="sxs-lookup"><span data-stu-id="ba55b-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="ba55b-168">Para importar novos rótulos de retenção e atualizar rótulos de retenção existentes, acesse **gerenciador de planos de arquivo** \> **ações de plano de arquivo** \> **importar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="ba55b-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opção para importar plano de arquivo](media/file-plan-import-labels-option.png)

![Opção para baixar um modelo de plano de arquivo em branco](media/file-plan-blank-template-option.png)

<span data-ttu-id="ba55b-171">Baixar um modelo em branco (ou começar com base em uma exportação do seu plano de arquivo atual).</span><span class="sxs-lookup"><span data-stu-id="ba55b-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Modelo de plano de arquivo em branco aberto no Excel](media/file-plan-blank-template.png)

<span data-ttu-id="ba55b-173">Preencher o modelo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-173">Fill-out the template.</span></span> <span data-ttu-id="ba55b-174">Esta tabela fornece valores válidos.</span><span class="sxs-lookup"><span data-stu-id="ba55b-174">This table provides valid values.</span></span>

|<span data-ttu-id="ba55b-175">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="ba55b-175">**Property**</span></span>|<span data-ttu-id="ba55b-176">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ba55b-176">**Type**</span></span>|<span data-ttu-id="ba55b-177">**Valores válidos**</span><span class="sxs-lookup"><span data-stu-id="ba55b-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba55b-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="ba55b-178">LabelName</span></span>|<span data-ttu-id="ba55b-179">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-179">String</span></span>|<span data-ttu-id="ba55b-180">Se o valor contiver espaços, coloque-o entre aspas (").</span><span class="sxs-lookup"><span data-stu-id="ba55b-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="ba55b-181">Comentário</span><span class="sxs-lookup"><span data-stu-id="ba55b-181">Comment</span></span>|<span data-ttu-id="ba55b-182">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-182">String</span></span>|<span data-ttu-id="ba55b-183">Se o valor contiver espaços, coloque-o entre aspas (").</span><span class="sxs-lookup"><span data-stu-id="ba55b-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="ba55b-184">Observações</span><span class="sxs-lookup"><span data-stu-id="ba55b-184">Notes</span></span>|<span data-ttu-id="ba55b-185">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-185">String</span></span>|<span data-ttu-id="ba55b-186">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-186">Custom</span></span>|
|<span data-ttu-id="ba55b-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="ba55b-187">IsRecordLabel</span></span>|<span data-ttu-id="ba55b-188">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-188">String</span></span>|<span data-ttu-id="ba55b-189">$true: O rótulo é um rótulo de registro.</span><span class="sxs-lookup"><span data-stu-id="ba55b-189">The label is a record label.</span></span></br><span data-ttu-id="ba55b-190">$false: O rótulo não é um rótulo de registro.</span><span class="sxs-lookup"><span data-stu-id="ba55b-190">The label isn't a record label.</span></span> <span data-ttu-id="ba55b-191">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ba55b-191">This is the default value.</span></span>|
|<span data-ttu-id="ba55b-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="ba55b-192">RetentionAction</span></span>|<span data-ttu-id="ba55b-193">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-193">String</span></span>|<span data-ttu-id="ba55b-194">Excluir</span><span class="sxs-lookup"><span data-stu-id="ba55b-194">Delete</span></span></br><span data-ttu-id="ba55b-195">Manter</span><span class="sxs-lookup"><span data-stu-id="ba55b-195">Keep</span></span></br><span data-ttu-id="ba55b-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="ba55b-196">KeepAndDelete</span></span> |
|<span data-ttu-id="ba55b-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="ba55b-197">RetentionDuration</span></span>|<span data-ttu-id="ba55b-198">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-198">String</span></span>|<span data-ttu-id="ba55b-199">Esta propriedade especifica o número de dias para reter o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="ba55b-200">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="ba55b-200">Valid values are:</span></span></br><span data-ttu-id="ba55b-201">Um inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-201">A positive integer.</span></span></br><span data-ttu-id="ba55b-202">O valor é ilimitado.</span><span class="sxs-lookup"><span data-stu-id="ba55b-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="ba55b-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="ba55b-203">RetentionType</span></span>|<span data-ttu-id="ba55b-204">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-204">String</span></span>|<span data-ttu-id="ba55b-205">Esta propriedade especifica se a duração da retenção é calculada a partir da data de criação de conteúdo, da data rotulada (marcada) ou da data da última modificação.</span><span class="sxs-lookup"><span data-stu-id="ba55b-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="ba55b-206">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="ba55b-206">Valid values are:</span></span></br><span data-ttu-id="ba55b-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ba55b-207">CreationAgeInDays</span></span></br><span data-ttu-id="ba55b-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ba55b-208">EventAgeInDays</span></span></br><span data-ttu-id="ba55b-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ba55b-209">ModificationAgeInDays</span></span></br><span data-ttu-id="ba55b-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ba55b-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="ba55b-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="ba55b-211">ReviewerEmail</span></span>|<span data-ttu-id="ba55b-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="ba55b-212">SmtpAddress</span></span>|<span data-ttu-id="ba55b-213">Esta propriedade especifica o endereço de email de um revisor para as ações de retenção Excluir e KeepAndDelete.</span><span class="sxs-lookup"><span data-stu-id="ba55b-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="ba55b-214">Você pode especificar vários endereços de email separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ba55b-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="ba55b-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="ba55b-215">ReferenceId</span></span>|<span data-ttu-id="ba55b-216">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-216">String</span></span>|<span data-ttu-id="ba55b-217">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-217">Custom</span></span>|
|<span data-ttu-id="ba55b-218">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="ba55b-218">DepartmentName</span></span>|<span data-ttu-id="ba55b-219">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-219">String</span></span>|<span data-ttu-id="ba55b-220">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-220">Custom</span></span>|
|<span data-ttu-id="ba55b-221">Categoria</span><span class="sxs-lookup"><span data-stu-id="ba55b-221">Category</span></span>|<span data-ttu-id="ba55b-222">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-222">String</span></span>|<span data-ttu-id="ba55b-223">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-223">Custom</span></span>|
|<span data-ttu-id="ba55b-224">SubCategory</span><span class="sxs-lookup"><span data-stu-id="ba55b-224">SubCategory</span></span>|<span data-ttu-id="ba55b-225">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-225">String</span></span>|<span data-ttu-id="ba55b-226">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-226">Custom</span></span>|
|<span data-ttu-id="ba55b-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="ba55b-227">AuthorityType</span></span>|<span data-ttu-id="ba55b-228">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-228">String</span></span>|<span data-ttu-id="ba55b-229">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-229">Custom</span></span>|
|<span data-ttu-id="ba55b-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="ba55b-230">CitationName</span></span>|<span data-ttu-id="ba55b-231">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-231">String</span></span>|<span data-ttu-id="ba55b-232">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-232">Custom</span></span>|
|<span data-ttu-id="ba55b-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="ba55b-233">CitationUrl</span></span>|<span data-ttu-id="ba55b-234">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-234">String</span></span>|<span data-ttu-id="ba55b-235">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-235">Custom</span></span>|
|<span data-ttu-id="ba55b-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="ba55b-236">CitationJurisdiction</span></span>|<span data-ttu-id="ba55b-237">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-237">String</span></span>|<span data-ttu-id="ba55b-238">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-238">Custom</span></span>|
|<span data-ttu-id="ba55b-239">Regulatório</span><span class="sxs-lookup"><span data-stu-id="ba55b-239">Regulatory</span></span>|<span data-ttu-id="ba55b-240">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-240">String</span></span>|<span data-ttu-id="ba55b-241">Personalizado</span><span class="sxs-lookup"><span data-stu-id="ba55b-241">Custom</span></span>|
|<span data-ttu-id="ba55b-242">EventType</span><span class="sxs-lookup"><span data-stu-id="ba55b-242">EventType</span></span>|<span data-ttu-id="ba55b-243">String</span><span class="sxs-lookup"><span data-stu-id="ba55b-243">String</span></span>|<span data-ttu-id="ba55b-244">Esta propriedade especifica a regra de retenção associada ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="ba55b-244">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="ba55b-245">É possível usar qualquer valor que identifique a regra com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="ba55b-246">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ba55b-246">For example:</span></span></br><span data-ttu-id="ba55b-247">Nome</span><span class="sxs-lookup"><span data-stu-id="ba55b-247">Name</span></span></br><span data-ttu-id="ba55b-248">DN (nome diferenciado)</span><span class="sxs-lookup"><span data-stu-id="ba55b-248">Distinguished name (DN)</span></span></br><span data-ttu-id="ba55b-249">GUID</span><span class="sxs-lookup"><span data-stu-id="ba55b-249">GUID</span></span> </br><span data-ttu-id="ba55b-250">Você pode usar o cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/pt-BR/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) para exibir as regras de retenção disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ba55b-250">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span>|

![Modelo de plano de arquivo com as informações preenchidas](media/file-plan-filled-out-template.png)

<span data-ttu-id="ba55b-252">Carregue o modelo preenchido, e o gerenciador de plano de arquivo validará as entradas e exibirá as estatísticas de importação.</span><span class="sxs-lookup"><span data-stu-id="ba55b-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Estatísticas de importação de plano de arquivo](media/file-plan-import-statistics.png)

<span data-ttu-id="ba55b-254">Caso haja um erro de validação, a importação do plano de arquivo continuará a validar todas as entradas no arquivo de importação e exibirá todos os erros ao referenciar números de linha no arquivo de importação, copiar os resultados de erros exibidos para que você possa retornar facilmente ao arquivo de importação e corrigir os erros.</span><span class="sxs-lookup"><span data-stu-id="ba55b-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="ba55b-255">Quando a importação for concluída, volte para o gerenciador de planos de arquivo para associar os novos rótulos de retenção a políticas de rótulos de retenção novas ou existentes.</span><span class="sxs-lookup"><span data-stu-id="ba55b-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opção para publicar rótulos](media/file-plan-publish-labels-option.png)

