---
title: Exibição do uso do rótulo com análises de rótulo
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Depois de criar seus rótulos de retenção e rótulos de sensibilidade, você desejará ver como eles estão sendo usados em seu locatário. Com a análise do rótulo no centro de conformidade do Microsoft 365 e no centro de segurança do Microsoft 365, você pode exibir rapidamente os rótulos mais usados e onde foram aplicados.
ms.openlocfilehash: 297987d420b5ed05bf4fdeb86513bc7c4ddec609
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072725"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="0586d-104">Exibição do uso do rótulo com análises de rótulo</span><span class="sxs-lookup"><span data-stu-id="0586d-104">View label usage with label analytics</span></span>

<span data-ttu-id="0586d-105">Depois de criar seus rótulos de retenção e rótulos de sensibilidade, você desejará ver como eles estão sendo usados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="0586d-105">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="0586d-106">Com a análise do rótulo no centro de conformidade do Microsoft 365 e no centro de segurança do Microsoft 365, você pode exibir rapidamente os rótulos mais usados e onde foram aplicados.</span><span class="sxs-lookup"><span data-stu-id="0586d-106">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="0586d-107">Por exemplo, com a análise do rótulo, você pode exibir o:</span><span class="sxs-lookup"><span data-stu-id="0586d-107">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="0586d-108">Total de rótulos de retenção e rótulos de confidencialidade aplicados ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0586d-108">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="0586d-109">Rótulos superiores e a contagem de quantas vezes cada rótulo foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="0586d-109">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="0586d-110">Locais onde os rótulos foram aplicados e a contagem de cada local.</span><span class="sxs-lookup"><span data-stu-id="0586d-110">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="0586d-111">Conta quantos arquivos e pastas tiveram seu rótulo de retenção, alterado ou removido.</span><span class="sxs-lookup"><span data-stu-id="0586d-111">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="0586d-112">Você encontra a análise de rótulo no [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/labelanalytics) ou no [Centro de segurança do Microsoft 365](https://security.microsoft.com/labelanalytics) > **Classificação**  >  \*\* Análise de Rótulo\*\*.</span><span class="sxs-lookup"><span data-stu-id="0586d-112">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![Página análise de rótulo](media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="0586d-114">Uso do rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="0586d-114">Sensitivity label usage</span></span>

<span data-ttu-id="0586d-115">Os dados de uso do rótulo de confidencialidade são extraídos dos Relatórios de Proteção de Informações do Azure – para saber mais, confira [Central de relatórios de Proteção de Informações do Azure](https://docs.microsoft.com/pt-BR/azure/information-protection/reports-aip).</span><span class="sxs-lookup"><span data-stu-id="0586d-115">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/pt-BR/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="0586d-116">Observe que tem os relatórios de Proteção de Informações do Azure possuem [pré-requisitos](https://docs.microsoft.com/pt-BR/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics) que também se aplicam a análise de rótulos nos rótulos de confidencialidade no centro de conformidade do Microsoft 365 e no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0586d-116">Note that the Azure Information Protection reports have [prerequisites](https://docs.microsoft.com/pt-BR/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="0586d-117">Por exemplo, você precisa de uma assinatura do Azure que inclua a Análise de Log, pois esses relatórios são um resultado do envio de eventos de auditoria da Proteção de Informação de clientes de Proteção de Informações do Azure e scanners em um local centralizado com base no serviço de Análise de Log do Azure.</span><span class="sxs-lookup"><span data-stu-id="0586d-117">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="0586d-118">Para uso do rótulo de confidencialidade:</span><span class="sxs-lookup"><span data-stu-id="0586d-118">For sensitivity label usage:</span></span>

- <span data-ttu-id="0586d-119">Não há nenhum latência nos dados.</span><span class="sxs-lookup"><span data-stu-id="0586d-119">There is no latency in the data.</span></span> <span data-ttu-id="0586d-120">Este é um relatório em tempo real.</span><span class="sxs-lookup"><span data-stu-id="0586d-120">This is a real-time report.</span></span>
- <span data-ttu-id="0586d-121">Para ver a contagem de cada rótulo superior, aponte para o gráfico de barras e leia a dica de ferramenta que aparecerá.</span><span class="sxs-lookup"><span data-stu-id="0586d-121">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="0586d-122">O relatório mostra onde os rótulos de confidencialidade são aplicados por aplicativo (enquanto os rótulos de retenção são mostrados por local).</span><span class="sxs-lookup"><span data-stu-id="0586d-122">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![Relatório o uso do rótulo de confidencialidade](media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="0586d-124">Uso do rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="0586d-124">Retention label usage</span></span>

<span data-ttu-id="0586d-125">Este relatório mostra uma exibição rápida do que os rótulos superiores são e onde são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="0586d-125">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="0586d-126">Para saber mais sobre como o conteúdo no SharePoint e OneDrive é rotulado, confira [Exibir a atividade de rótulos para documentos](view-label-activity-for-documents.md).</span><span class="sxs-lookup"><span data-stu-id="0586d-126">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="0586d-127">Para o uso do rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="0586d-127">For retention label usage:</span></span>

- <span data-ttu-id="0586d-128">Os dados são agregados semanalmente, portanto pode levar até sete dias para que os dados sejam exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="0586d-128">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="0586d-129">Para ver a contagem de cada rótulo superior, aponte para o gráfico de barras e leia a dica de ferramenta que aparecerá.</span><span class="sxs-lookup"><span data-stu-id="0586d-129">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="0586d-130">O relatório mostra onde os rótulos de retenção são aplicados por local (enquanto os rótulos de confidencialidade são mostrados por aplicativo).</span><span class="sxs-lookup"><span data-stu-id="0586d-130">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="0586d-131">Para rótulos de retenção, esse é um resumo de todos os dados de tempo em seu locatário; não é filtrado em um intervalo de dados específico.</span><span class="sxs-lookup"><span data-stu-id="0586d-131">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="0586d-132">Por outro lado, o [Explorador de Atividade de Rótulo](view-label-activity-for-documents.md) mostra apenas dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="0586d-132">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![Relatório do uso do rótulo de retenção](media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="0586d-134">Exibir todo o conteúdo com um rótulo de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="0586d-134">View all content with a specific retention label</span></span>

<span data-ttu-id="0586d-135">No relatório de uso do rótulo retenção, você pode rapidamente explorar todo o conteúdo em que esse rótulo foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="0586d-135">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="0586d-136">(Observe que estamos trabalhando nesse recurso, portanto algumas etapas serão necessárias para exibir todo o conteúdo rotulado).</span><span class="sxs-lookup"><span data-stu-id="0586d-136">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="0586d-137">Primeiro, escolha **Exibir Detalhes** na parte inferior do relatório.</span><span class="sxs-lookup"><span data-stu-id="0586d-137">First, choose **View Details** at the bottom of the report.</span></span>

![Opção Exibir Detalhes na parte inferior do relatório de uso do rótulo de retenção](media/retention-label-usage-view-details.png)

<span data-ttu-id="0586d-139">Escolha um rótulo de retenção > **Explorar itens** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="0586d-139">Then choose a retention label > **Explore items** in the right pane.</span></span>

![Opção Explorar itens no painel direito](media/retention-label-usage-explore-items.png)

<span data-ttu-id="0586d-141">Para esse rótulo, você pode escolher a guia **Atividade** para exibir uma contagem de itens com esse rótulo por local.</span><span class="sxs-lookup"><span data-stu-id="0586d-141">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![Guia atividade de um rótulo de retenção](media/retention-label-usage-activity-tab.png)

<span data-ttu-id="0586d-143">Você também pode escolher a guia **Itens com esse rótulo** guia. Em seguida, você pode ir para locais específicos:</span><span class="sxs-lookup"><span data-stu-id="0586d-143">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="0586d-144">Para o Exchange Online, você verá uma lista de caixas de correio com contagem de itens rotulados em cada caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0586d-144">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="0586d-145">Para o SharePoint Online e OneDrive for Business, você verá uma lista de conjuntos de sites e contas do OneDrive com a contagem de itens rotulados em cada local.</span><span class="sxs-lookup"><span data-stu-id="0586d-145">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="0586d-146">Quando você escolher um conjunto de site ou caixa de correio, você pode exibir uma lista de itens com esse rótulo retenção naquele local.</span><span class="sxs-lookup"><span data-stu-id="0586d-146">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![Itens com essa guia de rótulo mostrando todos os itens com esse rótulo de retenção](media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="0586d-148">Permissões</span><span class="sxs-lookup"><span data-stu-id="0586d-148">Permissions</span></span>

<span data-ttu-id="0586d-149">Para exibir a análise do rótulo, você deve ter uma das seguintes funções no Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="0586d-149">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="0586d-150">Administrador global</span><span class="sxs-lookup"><span data-stu-id="0586d-150">Global administrator</span></span>
- <span data-ttu-id="0586d-151">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="0586d-151">Compliance administrator</span></span>
- <span data-ttu-id="0586d-152">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="0586d-152">Security administrator</span></span>
- <span data-ttu-id="0586d-153">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="0586d-153">Security reader</span></span>

<span data-ttu-id="0586d-154">Além disso, observe que esses relatórios usam o Monitor do Azure para armazenar os dados em um espaço de trabalho de Análise de Log pertencente à sua organização.</span><span class="sxs-lookup"><span data-stu-id="0586d-154">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="0586d-155">Portanto, o usuário deve ser adicionado como um leitor ao espaço de trabalho de monitoramento do Azure monitoramento que possui os dados, para saber mais, confira [Permissões necessárias para análise da Proteção de Informações do Azure](https://docs.microsoft.com/pt-BR/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span><span class="sxs-lookup"><span data-stu-id="0586d-155">Therefore, the user should be added as a reader to the Azure Monitoring worksapce that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/pt-BR/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

