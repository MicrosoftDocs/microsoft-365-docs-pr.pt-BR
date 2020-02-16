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
description: Com os relatórios de DLP no Office 365, você pode exibir rapidamente o número de correspondências de política de DLP, substituições ou falsos positivos; Veja se eles estão em tendência de cima ou para baixo ao longo do tempo; filtrar o relatório de formas diferentes; e exiba detalhes adicionais selecionando um ponto em uma linha no gráfico.
ms.openlocfilehash: c00047680f684e3845c4383face09c2cee579721
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068739"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="a5d62-103">Exibir os relatórios de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="a5d62-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="a5d62-104">Após criar as políticas de prevenção de perda de dados (DLP), convém verificar se estão funcionando conforme o esperado e ajudando você a se manter em conformidade.</span><span class="sxs-lookup"><span data-stu-id="a5d62-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="a5d62-105">Com os relatórios de DLP no centro de conformidade &amp; de segurança do Office 365, você pode rapidamente exibir:</span><span class="sxs-lookup"><span data-stu-id="a5d62-105">With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="a5d62-106">**Correspondências de política DLP** Este relatório mostra a contagem de correspondências de política de DLP ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a5d62-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="a5d62-107">Você pode filtrar o relatório por data, local, política ou ação.</span><span class="sxs-lookup"><span data-stu-id="a5d62-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="a5d62-108">Você pode usar este relatório para:</span><span class="sxs-lookup"><span data-stu-id="a5d62-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="a5d62-109">Ajuste ou Refine suas políticas de DLP enquanto as executa no modo de teste.</span><span class="sxs-lookup"><span data-stu-id="a5d62-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="a5d62-110">Você pode exibir a regra específica que correspondeu ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5d62-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="a5d62-111">Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.</span><span class="sxs-lookup"><span data-stu-id="a5d62-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="a5d62-112">Descobrir processos empresariais que violam as políticas DLP da organização.</span><span class="sxs-lookup"><span data-stu-id="a5d62-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="a5d62-113">Entenda qualquer impacto nos negócios das políticas de DLP observando quais ações estão sendo aplicadas ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5d62-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="a5d62-114">Verificar a conformidade com uma determinada política DLP mostrando as correspondências dessa política.</span><span class="sxs-lookup"><span data-stu-id="a5d62-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="a5d62-115">Exibir uma lista dos principais usuários e repetir usuários que estão contribuindo com incidentes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a5d62-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="a5d62-116">Exibir uma lista dos principais tipos de informações confidenciais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a5d62-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="a5d62-117">**Incidentes de DLP** Este relatório também mostra correspondências de política com o tempo, como o relatório de correspondências de política.</span><span class="sxs-lookup"><span data-stu-id="a5d62-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="a5d62-118">No entanto, o relatório de correspondências de política mostra correspondências em um nível de regra; por exemplo, se um email coincidir com três regras diferentes, o relatório de correspondência de política mostrará três itens de linha diferentes.</span><span class="sxs-lookup"><span data-stu-id="a5d62-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="a5d62-119">Por outro lado, o relatório de incidentes mostra correspondências em um nível de item; por exemplo, se um email coincidir com três regras diferentes, o relatório de incidentes mostrará um único item de linha para essa parte do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5d62-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="a5d62-120">Como as contagens de relatórios são agregadas de forma diferente, o relatório de correspondências de política é melhor para identificar correspondências com regras específicas e ajustar as políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="a5d62-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="a5d62-121">O relatório de incidentes é melhor para identificar partes específicas do conteúdo que são problemáticas para suas políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="a5d62-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="a5d62-122">**Falsos positivos e substituições de DLP** Se sua política de DLP permitir que os usuários substituam ou relatem um falso positivo, esse relatório mostrará uma contagem de tais instâncias ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a5d62-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="a5d62-123">Você pode filtrar o relatório por data, local ou política.</span><span class="sxs-lookup"><span data-stu-id="a5d62-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="a5d62-124">Você pode usar este relatório para:</span><span class="sxs-lookup"><span data-stu-id="a5d62-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="a5d62-125">Ajuste ou Refine suas políticas de DLP, conferindo quais políticas provocam um grande número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="a5d62-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="a5d62-126">Exibir as justificativas enviadas pelos usuários quando eles resolverem uma dica de política substituindo a política.</span><span class="sxs-lookup"><span data-stu-id="a5d62-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="a5d62-127">Descubra onde as políticas de DLP entram em conflito com processos de negócios válidos incorrendo um grande número de substituições de usuário.</span><span class="sxs-lookup"><span data-stu-id="a5d62-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="a5d62-128">Todos os relatórios DLP podem mostrar dados do período de tempo de quatro meses mais recente.</span><span class="sxs-lookup"><span data-stu-id="a5d62-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="a5d62-129">Os dados mais recentes podem levar até 24 horas para serem exibidos nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="a5d62-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="a5d62-130">Você &amp; pode encontrar esses relatórios no **painel** **relatórios** \> do centro \> de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5d62-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Relatório de correspondências de política DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="a5d62-132">Exibir a justificativa enviada por um usuário para uma substituição</span><span class="sxs-lookup"><span data-stu-id="a5d62-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="a5d62-133">Se sua política de DLP permitir que os usuários o substituam, você poderá usar o falso positivo e substituir relatório para exibir o texto enviado por usuários na dica de política.</span><span class="sxs-lookup"><span data-stu-id="a5d62-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo de justificativa em detalhes do relatório falso positivo e substituição do DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="a5d62-135">Executar ações em ideias e recomendações</span><span class="sxs-lookup"><span data-stu-id="a5d62-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="a5d62-136">Os relatórios podem mostrar ideias e recomendações onde você pode clicar no ícone de aviso vermelho para ver detalhes sobre possíveis problemas e realizar ações corretivas possíveis.</span><span class="sxs-lookup"><span data-stu-id="a5d62-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Clicando em um ícone do insights para ver detalhes e ações a serem tomadas](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="a5d62-138">Permissões para relatórios de DLP</span><span class="sxs-lookup"><span data-stu-id="a5d62-138">Permissions for DLP reports</span></span>

<span data-ttu-id="a5d62-139">Para exibir relatórios de DLP no centro de conformidade & segurança, você precisa ter a atribuição de:</span><span class="sxs-lookup"><span data-stu-id="a5d62-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="a5d62-140">Função de **leitor de segurança** no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5d62-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="a5d62-141">Por padrão, essa função é atribuída aos grupos de função de gerenciamento de organização e leitor de segurança no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5d62-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="a5d62-142">**Somente exibição** a função de gerenciamento de conformidade DLP no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5d62-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="a5d62-143">Por padrão, essa função é atribuída aos grupos de função Administrador de conformidade, gerenciamento de organização, administrador de segurança e leitor de segurança no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5d62-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="a5d62-144">Função de **destinatários somente para exibição** no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5d62-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="a5d62-145">Por padrão, essa função é atribuída ao gerenciamento de conformidade, ao gerenciamento da organização e aos grupos de função de gerenciamento da organização somente para exibição no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5d62-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="a5d62-146">Localizar os cmdlets dos relatórios de DLP</span><span class="sxs-lookup"><span data-stu-id="a5d62-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="a5d62-147">Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:</span><span class="sxs-lookup"><span data-stu-id="a5d62-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="a5d62-148">Conectar-se ao Centro de Conformidade &amp; Segurança do Office 365 usando o PowerShell Remoto</span><span class="sxs-lookup"><span data-stu-id="a5d62-148">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="a5d62-149">Use qualquer um destes [cmdlets do &amp; centro de conformidade de segurança do Office 365](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="a5d62-149">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="a5d62-150">No entanto, os relatórios DLP precisam extrair dados do Office 365, incluindo o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a5d62-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="a5d62-151">Por esse motivo, os cmdlets dos relatórios DLP estão disponíveis no PowerShell do Exchange Online, e não no &amp; PowerShell do centro de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5d62-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="a5d62-152">Portanto, para usar os cmdlets para os relatórios DLP, você precisa:</span><span class="sxs-lookup"><span data-stu-id="a5d62-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="a5d62-153">Conectar-se ao Exchange Online usando o PowerShell Remoto</span><span class="sxs-lookup"><span data-stu-id="a5d62-153">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="a5d62-154">Usar qualquer um destes cmdlets para os relatórios DLP:</span><span class="sxs-lookup"><span data-stu-id="a5d62-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="a5d62-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="a5d62-155">Get-DlpDetectionsReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="a5d62-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="a5d62-156">Get-DlpDetailReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

