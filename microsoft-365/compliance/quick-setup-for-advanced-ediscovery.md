---
title: Instalação rápida para Descoberta Eletrônica Avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: Saiba como acessar a Descoberta Eletrônica Avançada no Centro de Conformidade &amp; Segurança e como analisar o fluxo de trabalho típico para usar a Descoberta Eletrônica avançada.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936254"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="7239d-103">Configuração rápida da Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="7239d-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7239d-104">À medida que continuamos investindo em versões mais recentes da Descoberta Eletrônica Avançada, anunciamos a retirada da Descoberta Eletrônica Avançada, também conhecida como *Descoberta Eletrônica Avançada (clássica)* ou *Descoberta Eletrônica Avançada v1.0*.</span><span class="sxs-lookup"><span data-stu-id="7239d-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="7239d-105">Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como \* solução de Descoberta Eletrônica Avançada no Microsoft 365\*) o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="7239d-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="7239d-106">O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão.</span><span class="sxs-lookup"><span data-stu-id="7239d-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="7239d-107">Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="7239d-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="7239d-108">Esta seção de configuração mostra a um gerente de Descoberta Eletrônica do Centro de Conformidade e Segurança &amp;do Microsoft 365 como começar a usar a Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="7239d-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="7239d-109">Pressupõe-se um conhecimento prático de ambos.</span><span class="sxs-lookup"><span data-stu-id="7239d-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="7239d-110">Como acessar um caso na Descoberta Eletrônica Avançada</span><span class="sxs-lookup"><span data-stu-id="7239d-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="7239d-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="7239d-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span></span> <span data-ttu-id="7239d-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7239d-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span></span> <span data-ttu-id="7239d-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="7239d-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="7239d-114">Para ir a um caso na Descoberta Eletrônica Avançada:</span><span class="sxs-lookup"><span data-stu-id="7239d-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="7239d-115">[Acesse o Centro de Conformidade &amp; Segurança](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7239d-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="7239d-116">No Centro de Conformidade e Segurança, clique em **Pesquisa e investigação** \> **Descoberta Eletrônica** para exibir a lista de casos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7239d-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="7239d-117">Na página **Descoberta Eletrônica**, clique em **Abrir** ao lado do caso ao qual deseja ir na Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="7239d-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="7239d-118">Na página **Início** do caso, clique em **Alternar para Avançar o eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="7239d-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="7239d-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span><span class="sxs-lookup"><span data-stu-id="7239d-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="7239d-120">When you're connected, the case is opened in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7239d-120">When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="7239d-121">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7239d-121">Workflow</span></span>

<span data-ttu-id="7239d-122">O diagrama a seguir ilustra o fluxo de trabalho comum para gerenciar e usar os casos de Descoberta Eletrônica no Centro de Conformidade e Segurança e na Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="7239d-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![Diagrama que mostra o fluxo de trabalho da Descoberta Eletrônica Avançada com quatro fases de instalação, inclusive a configuração de usuários &amp; casos, identificação dos dados de caso, exportação e processamento, além das fases de análise e exportação para o computador local.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="7239d-124">This setup section describes the first four steps in the workflow.</span><span class="sxs-lookup"><span data-stu-id="7239d-124">This setup section describes the first four steps in the workflow.</span></span> <span data-ttu-id="7239d-125">For a description of the other steps in the workflow, see the following.</span><span class="sxs-lookup"><span data-stu-id="7239d-125">For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="7239d-126">Análise</span><span class="sxs-lookup"><span data-stu-id="7239d-126">Analyze</span></span>

<span data-ttu-id="7239d-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span><span class="sxs-lookup"><span data-stu-id="7239d-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span></span> <span data-ttu-id="7239d-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span><span class="sxs-lookup"><span data-stu-id="7239d-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="7239d-129">Configuração da relevância e relevância</span><span class="sxs-lookup"><span data-stu-id="7239d-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="7239d-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span><span class="sxs-lookup"><span data-stu-id="7239d-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span></span> <span data-ttu-id="7239d-131">Calculates and displays interim results while monitoring statistical validity of the process.</span><span class="sxs-lookup"><span data-stu-id="7239d-131">Calculates and displays interim results while monitoring statistical validity of the process.</span></span> <span data-ttu-id="7239d-132">Displays the results to facilitate in making review decisions.</span><span class="sxs-lookup"><span data-stu-id="7239d-132">Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="7239d-133">Exportação</span><span class="sxs-lookup"><span data-stu-id="7239d-133">Export</span></span>

<span data-ttu-id="7239d-134">[Exportar dados de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar o conteúdo e os resultados da Descoberta Eletrônica Avançada para revisão externa.</span><span class="sxs-lookup"><span data-stu-id="7239d-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="7239d-135">Relatório</span><span class="sxs-lookup"><span data-stu-id="7239d-135">Report</span></span>

<span data-ttu-id="7239d-136">[Execução de relatórios](run-reports-in-advanced-ediscovery.md) Habilita a geração de relatórios selecionados que estão relacionados ao processamento da Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="7239d-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7239d-137">Também consulte</span><span class="sxs-lookup"><span data-stu-id="7239d-137">See also</span></span>

[<span data-ttu-id="7239d-138">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="7239d-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7239d-139">Configurar usuários e casos</span><span class="sxs-lookup"><span data-stu-id="7239d-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7239d-140">Preparação de dados</span><span class="sxs-lookup"><span data-stu-id="7239d-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

