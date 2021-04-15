---
title: Começar com o painel de alertas de prevenção contra perda de dados
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Começar a definir e gerenciar alertas para políticas de prevenção contra perda de dados.
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760681"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="729d9-103">Começar com o painel de alertas de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="729d9-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="729d9-104">As políticas de prevenção contra perda de dados (DLP) podem tomar ações de proteção para evitar o compartilhamento não intencional de itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="729d9-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="729d9-105">Quando uma ação é realizada em um item sensível, você pode ser notificado configurando alertas para DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="729d9-106">Este artigo mostra como definir políticas de alerta rich que estão vinculadas às políticas de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="729d9-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="729d9-107">Você verá como usar o painel de gerenciamento de alertaS [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) no centro de conformidade do [Microsoft 365](https://compliance.microsoft.com/) para exibir alertas, eventos e metadados associados para violações de política DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="729d9-108">Se você for novo em alertas de DLP, revise Saiba mais sobre o [painel de alertas](dlp-alerts-dashboard-learn.md) de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="729d9-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="729d9-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="729d9-109">Before you begin</span></span>

<span data-ttu-id="729d9-110">Antes de começar, certifique-se de ter os pré-requisitos necessários:</span><span class="sxs-lookup"><span data-stu-id="729d9-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="729d9-111">Licenciamento para o painel de gerenciamento de alertas de DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="729d9-112">Licenciamento para opções de configuração de alerta</span><span class="sxs-lookup"><span data-stu-id="729d9-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="729d9-113">Funções</span><span class="sxs-lookup"><span data-stu-id="729d9-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="729d9-114">Licenciamento para o painel de gerenciamento de alertas DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="729d9-115">Todos os locatários qualificados para a DLP do Office 365 podem acessar o painel de gerenciamento de alertas DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="729d9-116">Para começar, você deve estar qualificado para o Office 365 DLP para Exchange Online, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="729d9-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="729d9-117">Para obter mais informações sobre os requisitos de licenciamento para a DLP do Office 365, consulte Quais licenças fornecem os direitos para um usuário se [beneficiar do serviço?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span><span class="sxs-lookup"><span data-stu-id="729d9-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="729d9-118">Os clientes que usam [a DLP](endpoint-dlp-learn-about.md) do Ponto de Extremidade que estão qualificados para a DLP do Teams verão seus alertas de política de [DLP](dlp-microsoft-teams.md) de ponto de extremidade e alertas de política de DLP do Teams no painel de gerenciamento de alertas DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="729d9-119">O **recurso de visualização** de conteúdo está disponível apenas para essas licenças:</span><span class="sxs-lookup"><span data-stu-id="729d9-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="729d9-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="729d9-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="729d9-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="729d9-121">Office 365 (E5)</span></span>
- <span data-ttu-id="729d9-122">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="729d9-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="729d9-123">Proteção e Governança de Informações do Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="729d9-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="729d9-124">Conformidade com o Microsft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="729d9-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="729d9-125">Licenciamento para opções de configuração de alerta</span><span class="sxs-lookup"><span data-stu-id="729d9-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="729d9-126">**Configuração de** alerta de evento único : organizações que têm uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 podem criar políticas de alerta somente onde um alerta é disparado sempre que uma atividade ocorre.</span><span class="sxs-lookup"><span data-stu-id="729d9-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="729d9-127">**Configuração de alerta agregada**: Para configurar políticas de alerta agregadas com base em um limite, você deve ter uma destas configurações de licenciamento:</span><span class="sxs-lookup"><span data-stu-id="729d9-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="729d9-128">Uma assinatura E5 ou G5</span><span class="sxs-lookup"><span data-stu-id="729d9-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="729d9-129">Uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 que inclui um dos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="729d9-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="729d9-130">Plano 2 de proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="729d9-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="729d9-131">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="729d9-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="729d9-132">Licença de complemento descoberta e auditoria do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="729d9-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="729d9-133">Funções</span><span class="sxs-lookup"><span data-stu-id="729d9-133">Roles</span></span>


<span data-ttu-id="729d9-134">Se você quiser exibir o painel de gerenciamento de alertaS DLP ou editar as opções de configuração de alerta em uma política de DLP, você deve ser membro de um desses grupos de função:</span><span class="sxs-lookup"><span data-stu-id="729d9-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="729d9-135">Administrador de Conformidade</span><span class="sxs-lookup"><span data-stu-id="729d9-135">Compliance Administrator</span></span>
- <span data-ttu-id="729d9-136">Administrador de Dados de Conformidade</span><span class="sxs-lookup"><span data-stu-id="729d9-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="729d9-137">Administrador de Segurança</span><span class="sxs-lookup"><span data-stu-id="729d9-137">Security Administrator</span></span>
- <span data-ttu-id="729d9-138">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="729d9-138">Security Operator</span></span>
- <span data-ttu-id="729d9-139">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="729d9-139">Security Reader</span></span>

<span data-ttu-id="729d9-140">Para acessar o painel de gerenciamento de alertas DLP, você precisa:</span><span class="sxs-lookup"><span data-stu-id="729d9-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="729d9-141">Gerenciar alertas</span><span class="sxs-lookup"><span data-stu-id="729d9-141">Manage alerts</span></span>

<span data-ttu-id="729d9-142">e uma dessas duas funções:</span><span class="sxs-lookup"><span data-stu-id="729d9-142">and either of these two roles:</span></span>

- <span data-ttu-id="729d9-143">Gerenciamento de Conformidade de DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-143">DLP Compliance Management</span></span>
- <span data-ttu-id="729d9-144">View-Only gerenciamento de conformidade de DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="729d9-145">Para acessar o recurso de visualização de conteúdo e os recursos de contexto e conteúdo confidenciais associados, você deve ser membro de:</span><span class="sxs-lookup"><span data-stu-id="729d9-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="729d9-146">Grupo de função do Visualizador de Conteúdo do Explorador de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="729d9-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="729d9-147">que tem a função de visualizador de conteúdo de classificação de dados pré-atribuída.</span><span class="sxs-lookup"><span data-stu-id="729d9-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="729d9-148">Configuração de alerta DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-148">DLP alert configuration</span></span>

<span data-ttu-id="729d9-149">Para saber como configurar um alerta em sua política de DLP, consulte [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span><span class="sxs-lookup"><span data-stu-id="729d9-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="729d9-150">Configuração de alerta de evento agregado</span><span class="sxs-lookup"><span data-stu-id="729d9-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="729d9-151">Se sua organização estiver licenciada para opções [de](#licensing-for-alert-configuration-options)configuração de alerta agregada, você verá essas opções ao criar ou editar uma política de DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para opções de configuração de alerta agregadas." border="false":::

<span data-ttu-id="729d9-153">Essa configuração permite configurar uma política para gerar um alerta sempre que uma atividade corresponde às condições da política ou quando um determinado limite é excedido, com base no número de atividades ou com base no volume de dados exfiltrados.</span><span class="sxs-lookup"><span data-stu-id="729d9-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="729d9-154">Configuração de alerta de evento único</span><span class="sxs-lookup"><span data-stu-id="729d9-154">Single event alert configuration</span></span>

<span data-ttu-id="729d9-155">Se sua organização estiver licenciada para opções de configuração de alerta de evento [único,](#licensing-for-alert-configuration-options)você verá essas opções ao criar ou editar uma política de DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="729d9-156">Use essa opção para criar um alerta que é gerado sempre que uma combinação de regra de DLP acontece.</span><span class="sxs-lookup"><span data-stu-id="729d9-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para opções de configuração de alerta de evento único." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="729d9-158">Investigar um alerta DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-158">Investigate a DLP alert</span></span>

<span data-ttu-id="729d9-159">Para trabalhar com o painel de gerenciamento de alertas DLP:</span><span class="sxs-lookup"><span data-stu-id="729d9-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="729d9-160">No Centro de conformidade do [Microsoft 365,](https://www.compliance.microsoft.com)acesse **Prevenção** contra Perda de Dados .</span><span class="sxs-lookup"><span data-stu-id="729d9-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="729d9-161">Selecione a **guia Alertas** para exibir o painel de alertas DLP.</span><span class="sxs-lookup"><span data-stu-id="729d9-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="729d9-162">Selecione um alerta para ver detalhes:</span><span class="sxs-lookup"><span data-stu-id="729d9-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Captura de tela mostrando detalhes do alerta no painel de gerenciamento de alertas DLP." border="false":::

4. <span data-ttu-id="729d9-164">Selecione a **guia Eventos** para exibir todos os eventos associados ao alerta.</span><span class="sxs-lookup"><span data-stu-id="729d9-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="729d9-165">Você pode escolher um evento específico para exibir seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="729d9-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="729d9-166">Para obter uma lista de alguns dos detalhes do evento disponíveis, consulte Learn [about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span><span class="sxs-lookup"><span data-stu-id="729d9-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="729d9-167">Selecione **Detalhes** para abrir a página **Visão** Geral do alerta.</span><span class="sxs-lookup"><span data-stu-id="729d9-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="729d9-168">A página de visão geral fornece um resumo:</span><span class="sxs-lookup"><span data-stu-id="729d9-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="729d9-169">do que aconteceu</span><span class="sxs-lookup"><span data-stu-id="729d9-169">of what happened</span></span>
    1. <span data-ttu-id="729d9-170">que realizou as ações que causaram a combinação de política</span><span class="sxs-lookup"><span data-stu-id="729d9-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="729d9-171">informações sobre a política de combinação e muito mais</span><span class="sxs-lookup"><span data-stu-id="729d9-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="729d9-172">Escolha a **guia Eventos** para acessar:</span><span class="sxs-lookup"><span data-stu-id="729d9-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="729d9-173">conteúdo envolvido</span><span class="sxs-lookup"><span data-stu-id="729d9-173">content involved</span></span>
    1. <span data-ttu-id="729d9-174">tipos de informações confidenciais que corresponderam</span><span class="sxs-lookup"><span data-stu-id="729d9-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="729d9-175">metadados</span><span class="sxs-lookup"><span data-stu-id="729d9-175">metadata</span></span>

7. <span data-ttu-id="729d9-176">Selecione a **guia Tipos de Informações Confidenciais** para exibir detalhes sobre os tipos de informações confidenciais detectados no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="729d9-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="729d9-177">Os detalhes incluem confiança, contagem e o conteúdo que corresponde ao tipo de informação confidenciais.</span><span class="sxs-lookup"><span data-stu-id="729d9-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="729d9-178">Depois de investigar o alerta, volte para a guia **Visão** geral, onde você pode gerenciar a triagem e gerenciar a disposição do alerta e adicionar comentários.</span><span class="sxs-lookup"><span data-stu-id="729d9-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="729d9-179">Para ver o histórico de gerenciamento de fluxo de trabalho, escolha **Log de gerenciamento.**</span><span class="sxs-lookup"><span data-stu-id="729d9-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="729d9-180">Depois de tomar a ação necessária para o alerta, de definir o status do alerta como **Resolvido**.</span><span class="sxs-lookup"><span data-stu-id="729d9-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="729d9-181">Confira também</span><span class="sxs-lookup"><span data-stu-id="729d9-181">See also</span></span>

- [<span data-ttu-id="729d9-182">Saiba mais sobre alertas de prevenção contra perda de dados e o painel de alertas</span><span class="sxs-lookup"><span data-stu-id="729d9-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="729d9-183">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="729d9-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)