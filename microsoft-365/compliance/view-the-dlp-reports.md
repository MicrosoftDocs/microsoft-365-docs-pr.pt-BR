---
title: Exibir os relatórios de prevenção contra perda de dados
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Use os relatórios de DLP no Office 365 para exibir o número de jogos de política de DLP, substituições ou falsos positivos e ver se eles estão em tendência para cima ou para baixo com o tempo.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928385"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="7dcdd-103">Exibir os relatórios de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="7dcdd-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="7dcdd-104">Depois de criar suas políticas de prevenção contra perda de dados (DLP), você vai querer verificar se elas estão funcionando conforme você pretendia e ajudá-lo a permanecer em conformidade.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="7dcdd-105">Com os relatórios de DLP no Centro &amp; de Conformidade e Segurança, você pode exibir rapidamente:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="7dcdd-106">**A política DLP corresponde** Este relatório mostra a contagem de combinações de política de DLP ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="7dcdd-107">Você pode filtrar o relatório por data, local, política ou ação.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="7dcdd-108">Você pode usar este relatório para:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="7dcdd-109">Ajuste ou refine suas políticas de DLP conforme você as executar no modo de teste.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="7dcdd-110">Você pode exibir a regra específica que corresponderá ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="7dcdd-111">Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="7dcdd-112">Descobrir processos empresariais que violam as políticas DLP da organização.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="7dcdd-113">Entenda qualquer impacto comercial das políticas de DLP vendo quais ações estão sendo aplicadas ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="7dcdd-114">Verificar a conformidade com uma determinada política DLP mostrando as correspondências dessa política.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="7dcdd-115">Exibir uma lista dos principais usuários e repetir usuários que estão contribuindo para incidentes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="7dcdd-116">Exibir uma lista dos principais tipos de informações confidenciais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="7dcdd-117">**Incidentes DLP** Este relatório também mostra as combinações de política ao longo do tempo, como o relatório de corresponde à política.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="7dcdd-118">No entanto, o relatório de corresponde à política mostra as combinações em um nível de regra; por exemplo, se um email correspondeu a três regras diferentes, o relatório de corresponder à política mostrará três itens de linha diferentes.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="7dcdd-119">Por outro lado, o relatório de incidentes mostra as combinações em um nível de item; por exemplo, se um email corresponder a três regras diferentes, o relatório de incidentes mostrará um único item de linha para esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="7dcdd-120">Como as contagens de relatório são agregadas de forma diferente, o relatório de combinações de política é melhor para identificar as combinações com regras específicas e ajustar as políticas DLP de ajuste fino.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="7dcdd-121">O relatório de incidentes é melhor para identificar partes específicas de conteúdo que são problemáticas para suas políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="7dcdd-122">**DLP falsos positivos e substituições** Se sua política de DLP permitir que os usuários a substituam ou reportem um falso positivo, este relatório mostrará uma contagem dessas instâncias ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="7dcdd-123">Você pode filtrar o relatório por data, local ou política.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="7dcdd-124">Você pode usar este relatório para:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="7dcdd-125">Ajuste ou refine suas políticas de DLP vendo quais políticas incorrem em um alto número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="7dcdd-126">Exibir as justificativas enviadas pelos usuários quando resolverem uma dica de política substituindo a política.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="7dcdd-127">Descubra onde as políticas de DLP conflitam com processos comerciais válidos incorrendo em um alto número de substituições de usuários.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="7dcdd-128">Todos os relatórios de DLP podem mostrar dados do período de quatro meses mais recente.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="7dcdd-129">Os dados mais recentes podem levar até 24 horas para aparecerem nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="7dcdd-130">Você pode encontrar esses relatórios no Painel de Relatórios do Centro &amp; de Conformidade \>  \> **e Segurança.**</span><span class="sxs-lookup"><span data-stu-id="7dcdd-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Relatório de corresponde à política de DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="7dcdd-132">Exibir a justificativa enviada por um usuário para uma substituição</span><span class="sxs-lookup"><span data-stu-id="7dcdd-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="7dcdd-133">Se sua política de DLP permitir que os usuários a substituam, você poderá usar o relatório falso positivo e substituir para exibir o texto enviado pelos usuários na dica de política.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo Justification em detalhes do relatório de falso positivo e substituição de DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="7dcdd-135">Tomar medidas sobre insights e recomendações</span><span class="sxs-lookup"><span data-stu-id="7dcdd-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="7dcdd-136">Os relatórios podem mostrar insights e recomendações em que você pode clicar no ícone de aviso vermelho para ver detalhes sobre possíveis problemas e realizar uma possível ação corretiva.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Clicando em um ícone de insights para ver detalhes e ações a ser tomadas](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="7dcdd-138">Permissões para relatórios DLP</span><span class="sxs-lookup"><span data-stu-id="7dcdd-138">Permissions for DLP reports</span></span>

<span data-ttu-id="7dcdd-139">Para exibir relatórios de DLP no Centro de Conformidade & segurança, você precisa ter o:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="7dcdd-140">**Função leitor de** segurança no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="7dcdd-141">Por padrão, essa função é atribuída aos grupos de função Gerenciamento da Organização e Leitor de Segurança no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="7dcdd-142">**Função de Gerenciamento de Conformidade de DLP** somente exibição no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="7dcdd-143">Por padrão, essa função é atribuída aos grupos de função Administrador de Conformidade, Gerenciamento da Organização, Administrador de Segurança e Leitor de Segurança no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="7dcdd-144">**Função Somente exibição Destinatários** no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="7dcdd-145">Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade, Gerenciamento da Organização e gerenciamento View-Only Organização no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="7dcdd-146">Encontre os cmdlets para os relatórios DLP</span><span class="sxs-lookup"><span data-stu-id="7dcdd-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="7dcdd-147">Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="7dcdd-148">Conectar-se ao Centro &amp; de Conformidade de Segurança usando o PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="7dcdd-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="7dcdd-149">Use qualquer um desses [ &amp; cmdlets](/powershell/exchange/exchange-online-powershell) do Centro de Conformidade de Segurança</span><span class="sxs-lookup"><span data-stu-id="7dcdd-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="7dcdd-150">No entanto, os relatórios DLP precisam extrair dados do Office 365, incluindo o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="7dcdd-151">Por esse motivo, os cmdlets para os relatórios DLP estão disponíveis no Powershell do Exchange Online, não no Centro de &amp; Conformidade de Segurança do Powershell.</span><span class="sxs-lookup"><span data-stu-id="7dcdd-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="7dcdd-152">Portanto, para usar os cmdlets para os relatórios DLP, você precisa:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="7dcdd-153">Conectar-se ao Exchange Online usando o PowerShell Remoto</span><span class="sxs-lookup"><span data-stu-id="7dcdd-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="7dcdd-154">Usar qualquer um destes cmdlets para os relatórios DLP:</span><span class="sxs-lookup"><span data-stu-id="7dcdd-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="7dcdd-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="7dcdd-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="7dcdd-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="7dcdd-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
