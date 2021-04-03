---
title: Analisador de Configuração de Conformidade da Microsoft para Gerenciador de Conformidade
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Entenda como usar o Analisador de Configuração de Conformidade da Microsoft para começar a funcionar rapidamente com o Microsoft Compliance Manager.
ms.openlocfilehash: 2b91ac274d7270f5be9530742cf711a3918b287d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570370"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="ca8f4-103">Analisador de Configuração de Conformidade da Microsoft para Gerenciador de Conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="ca8f4-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="ca8f4-104">**Neste artigo:** Saiba como instalar e executar a ferramenta Analisador de Conformidade da Microsoft para começar rapidamente com o Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="ca8f4-105">Visão geral do Microsoft Compliance Configuration Analyzer (MCCA) (visualização)</span><span class="sxs-lookup"><span data-stu-id="ca8f4-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="ca8f4-106">O Microsoft Compliance Configuration Analyzer (MCCA) é uma ferramenta de visualização que pode ajudá-lo a começar a usar o [Microsoft Compliance Manager.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="ca8f4-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="ca8f4-107">O MCCA é um utilitário baseado no PowerShell que buscará as configurações atuais da sua organização e as validará em relação às práticas recomendadas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="ca8f4-108">Essas práticas recomendadas se baseiam em um conjunto de controles que incluem os principais regulamentos e padrões de proteção de dados e governança de dados.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="ca8f4-109">O MCCA pode ajudá-lo a ver rapidamente quais ações de melhoria no Compliance Manger se aplicam ao seu ambiente atual do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="ca8f4-110">Cada ação identificada pelo MCCA dará recomendações para implementação, com links diretos para o Gerenciador de Conformidade e a solução aplicável para começar a tomar medidas corretivas.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="ca8f4-111">Um recurso adicional para entender o MCCA é visitar as instruções [README no GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="ca8f4-112">Esta página fornece informações detalhadas sobre pré-requisitos e fornece instruções de instalação completas.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="ca8f4-113">Você não precisa de uma conta do GitHub para acessar esta página.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="ca8f4-114">**Disponibilidade**: O MCCA está disponível para todas as organizações com licenças do Office 365 e microsoft 365 e clientes do GCC (Us Government Community), GCC High e Department of Defense (DoD).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="ca8f4-115">Instalar o MCCA e executar um relatório</span><span class="sxs-lookup"><span data-stu-id="ca8f4-115">Install MCCA and run a report</span></span>

<span data-ttu-id="ca8f4-116">Você pode instalar a ferramenta MCCA usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="ca8f4-117">Depois de baixar e instalar a ferramenta, não é necessário repetir essas etapas para executar relatórios.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="ca8f4-118">Sempre que você abrir o MCCA, ele solicitará suas credenciais de logon e gerará um novo relatório atualizado.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="ca8f4-119">Etapa 1: Instalar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca8f4-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="ca8f4-120">Para começar, você precisará do módulo do PowerShell do Exchange Online (v2.0.3 ou superior) que está disponível na galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="ca8f4-121">[Obter instruções de instalação](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="ca8f4-122">Etapa 2: Instalar o MCCA</span><span class="sxs-lookup"><span data-stu-id="ca8f4-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="ca8f4-123">Para instalar o MCCA, comece usando o PowerShell no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="ca8f4-124">Siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-124">Follow the steps below:</span></span>

1. <span data-ttu-id="ca8f4-125">Selecione o botão Iniciar **do** Windows.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="ca8f4-126">Digite **PowerShell**, clique com o botão direito **do mouse Windows PowerShell**, em seguida, selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="ca8f4-127">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="ca8f4-128">Etapa 3: Executar um relatório</span><span class="sxs-lookup"><span data-stu-id="ca8f4-128">Step 3: Run a report</span></span>

<span data-ttu-id="ca8f4-129">Depois de instalar o MCCA, você pode executar o MCCA e gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="ca8f4-130">Para executar um relatório:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-130">To run a report:</span></span>

1. <span data-ttu-id="ca8f4-131">Abrir o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca8f4-131">Open PowerShell</span></span>
2. <span data-ttu-id="ca8f4-132">Execute o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="ca8f4-133">Se você for um cliente GCC High, precisará fornecer um parâmetro de entrada adicional para executar o relatório:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="ca8f4-134">Depois que o MCCA é executado, ele faz uma verificação de versão inicial e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="ca8f4-135">No prompt De entrada do nome de usuário, entre com seu endereço de email da conta do Microsoft 365 ( exibir as funções qualificadas[para criar relatórios](#role-based-reporting)).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="ca8f4-136">Em seguida, insira sua senha no prompt de senha.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="ca8f4-137">Seu relatório levará aproximadamente 2 a 5 minutos para gerar.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="ca8f4-138">Quando terminar, uma janela do navegador será aberta e exibirá seu relatório HTML.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="ca8f4-139">Sempre que você executar a ferramenta, ela solicitará suas credenciais e gerará um novo relatório.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="ca8f4-140">Este relatório é armazenado localmente no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="ca8f4-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="ca8f4-142">Você pode acessar relatórios gerados anteriormente a partir deste diretório.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="ca8f4-143">Noções básicas sobre seu relatório</span><span class="sxs-lookup"><span data-stu-id="ca8f4-143">Understanding your report</span></span>

<span data-ttu-id="ca8f4-144">Seu relatório reflete dados com base na data e hora em que foram gerados.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="ca8f4-145">A seção superior fornece detalhes sobre quando ele foi gerado, o nome da sua organização e a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="ca8f4-146">Relatórios baseados em geolocalização</span><span class="sxs-lookup"><span data-stu-id="ca8f4-146">Geolocation-based reporting</span></span>

<span data-ttu-id="ca8f4-147">A **seção Observação** mostra que seu relatório é personalizado com base na localização geográfica do locatário.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="ca8f4-148">As recomendações listadas na ferramenta serão específicas para seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="ca8f4-149">Sua seleção de localização geográfica é usada para avaliar os SITs (tipos de informações confidenciais) que são relevantes para essa localização geográfica e gerar um relatório que se alinha ao seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="ca8f4-150">Escolha localizações geográficas com base nos dados que você tem em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="ca8f4-151">Para alterar as informações de localização do relatório, você precisa fornecer um parâmetro de entrada de localização geográfica (-Geo).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="ca8f4-152">Você pode escolher uma ou várias localizações geográficas aplicáveis ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="ca8f4-153">Siga estas instruções para executar um relatório com base em um local específico:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="ca8f4-154">Abrir o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca8f4-154">Open PowerShell</span></span>
2. <span data-ttu-id="ca8f4-155">Para especificar uma determinada região, você executará um cmdlet usando os números da tabela abaixo que correspondem ao país ou região.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="ca8f4-156">Insira vários números separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="ca8f4-157">Por exemplo, o cmdlet abaixo executará um relatório personalizado para o Asia-Pacific e o Japão:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="ca8f4-158">Input</span><span class="sxs-lookup"><span data-stu-id="ca8f4-158">Input</span></span> |  <span data-ttu-id="ca8f4-159">País ou Região</span><span class="sxs-lookup"><span data-stu-id="ca8f4-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="ca8f4-160">1</span><span class="sxs-lookup"><span data-stu-id="ca8f4-160">1</span></span> | <span data-ttu-id="ca8f4-161">Ásia – Pacífico</span><span class="sxs-lookup"><span data-stu-id="ca8f4-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="ca8f4-162">2</span><span class="sxs-lookup"><span data-stu-id="ca8f4-162">2</span></span> | <span data-ttu-id="ca8f4-163">Austrália</span><span class="sxs-lookup"><span data-stu-id="ca8f4-163">Australia</span></span> |
  | <span data-ttu-id="ca8f4-164">3</span><span class="sxs-lookup"><span data-stu-id="ca8f4-164">3</span></span> | <span data-ttu-id="ca8f4-165">Canadá</span><span class="sxs-lookup"><span data-stu-id="ca8f4-165">Canada</span></span> |
  | <span data-ttu-id="ca8f4-166">4 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-166">4</span></span> | <span data-ttu-id="ca8f4-167">Europa (excluindo a França) / Oriente Médio / África</span><span class="sxs-lookup"><span data-stu-id="ca8f4-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="ca8f4-168">5 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-168">5</span></span> | <span data-ttu-id="ca8f4-169">França</span><span class="sxs-lookup"><span data-stu-id="ca8f4-169">France</span></span> |
  | <span data-ttu-id="ca8f4-170">6 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-170">6</span></span> | <span data-ttu-id="ca8f4-171">Índia</span><span class="sxs-lookup"><span data-stu-id="ca8f4-171">India</span></span> |
  | <span data-ttu-id="ca8f4-172">7 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-172">7</span></span> | <span data-ttu-id="ca8f4-173">Japão</span><span class="sxs-lookup"><span data-stu-id="ca8f4-173">Japan</span></span> |
  | <span data-ttu-id="ca8f4-174">8 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-174">8</span></span> | <span data-ttu-id="ca8f4-175">Coreia</span><span class="sxs-lookup"><span data-stu-id="ca8f4-175">Korea</span></span> |
  | <span data-ttu-id="ca8f4-176">9 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-176">9</span></span> | <span data-ttu-id="ca8f4-177">América do Norte (excluindo o Canadá)</span><span class="sxs-lookup"><span data-stu-id="ca8f4-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="ca8f4-178">10 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-178">10</span></span> | <span data-ttu-id="ca8f4-179">América do Sul</span><span class="sxs-lookup"><span data-stu-id="ca8f4-179">South America</span></span> |
  | <span data-ttu-id="ca8f4-180">11</span><span class="sxs-lookup"><span data-stu-id="ca8f4-180">11</span></span> | <span data-ttu-id="ca8f4-181">África do Sul</span><span class="sxs-lookup"><span data-stu-id="ca8f4-181">South Africa</span></span> |
  | <span data-ttu-id="ca8f4-182">12 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-182">12</span></span> | <span data-ttu-id="ca8f4-183">Suíça</span><span class="sxs-lookup"><span data-stu-id="ca8f4-183">Switzerland</span></span> |
  | <span data-ttu-id="ca8f4-184">13</span><span class="sxs-lookup"><span data-stu-id="ca8f4-184">13</span></span> | <span data-ttu-id="ca8f4-185">Emirados Árabes Unidos</span><span class="sxs-lookup"><span data-stu-id="ca8f4-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="ca8f4-186">14 </span><span class="sxs-lookup"><span data-stu-id="ca8f4-186">14</span></span> | <span data-ttu-id="ca8f4-187">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ca8f4-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="ca8f4-188">O relatório sempre incluirá tipos de informações confidenciais internacionais com suporte da MCCA, como código SWIFT, número de cartão de crédito, etc.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="ca8f4-189">Relatórios baseados em função</span><span class="sxs-lookup"><span data-stu-id="ca8f4-189">Role-based reporting</span></span>

<span data-ttu-id="ca8f4-190">Seu relatório também será personalizado com base em sua função.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="ca8f4-191">A tabela a seguir mostra quais funções têm acesso a quais seções do relatório.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="ca8f4-192">Outras funções em sua organização (não listadas na tabela abaixo) podem não ser capazes de executar a ferramenta, ou podem executar a ferramenta e ter acesso limitado às informações no relatório final.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="ca8f4-193">![MCCA - funções](../media/compliance-manager-mcca-roles.png "Funções MCCA")</span><span class="sxs-lookup"><span data-stu-id="ca8f4-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="ca8f4-194">Exceções:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-194">Exceptions:</span></span>
1. <span data-ttu-id="ca8f4-195">Os usuários não poderão gerar relatório para IP além da seção "Usar IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ca8f4-195">Users won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="ca8f4-196">Os usuários poderão gerar relatório para IP além da seção "Usar IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ca8f4-196">Users will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="ca8f4-197">Os usuários poderão gerar relatório para IP além da seção "Habilitar a Conformidade de Comunicação no O365".</span><span class="sxs-lookup"><span data-stu-id="ca8f4-197">Users will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="ca8f4-198">Os usuários não poderão gerar relatório para IP além da seção "Habilitar auditoria no Office 365".</span><span class="sxs-lookup"><span data-stu-id="ca8f4-198">Users won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="ca8f4-199">Os usuários poderão gerar relatório para IP além da seção "Habilitar auditoria no Office 365".</span><span class="sxs-lookup"><span data-stu-id="ca8f4-199">Users will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="ca8f4-200">Seção Resumo de Soluções</span><span class="sxs-lookup"><span data-stu-id="ca8f4-200">Solutions Summary section</span></span>

<span data-ttu-id="ca8f4-201">A **seção Resumo de** Soluções do relatório fornece uma visão geral das ações de melhoria que sua organização pode tomar no Gerenciador de Conformidade para ajudar a melhorar a postura de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="ca8f4-202">![MCCA - resumo das soluções](../media/compliance-manager-mcca-solutions.png "Tela Resumo de Soluções MCCA")</span><span class="sxs-lookup"><span data-stu-id="ca8f4-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="ca8f4-203">O MCCA avalia suas configurações atuais em relação às ações de melhoria recomendadas no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="ca8f4-204">Qualquer ação de melhoria identificada pela ferramenta MCCA como que precisa de atenção será listada nesta seção.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="ca8f4-205">Ao lado de cada solução da Microsoft estão caixas codificadas por cores indicando o número de itens que correspondem às ações de melhoria no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="ca8f4-206">As ações são divididas em três estados de status:</span><span class="sxs-lookup"><span data-stu-id="ca8f4-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="ca8f4-207">**OK**: as ações que atendem às condições recomendadas e não precisam de atenção no momento</span><span class="sxs-lookup"><span data-stu-id="ca8f4-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="ca8f4-208">**Aperfeiçoamento**: ações que precisam de atenção</span><span class="sxs-lookup"><span data-stu-id="ca8f4-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="ca8f4-209">**Recomendação**: ações que não precisam de atenção, mas para as quais recomendamos práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="ca8f4-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="ca8f4-210">Selecione uma caixa para exibir melhorias e recomendações.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="ca8f4-211">**Itens com o status De aperfeiçoamento**</span><span class="sxs-lookup"><span data-stu-id="ca8f4-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="ca8f4-212">Selecione o menu suspenso ao lado do **rótulo De aperfeiçoamento** à direita da ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="ca8f4-213">Você verá um resumo rápido e detalhes sobre suas configurações atuais e as ações de melhoria recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="ca8f4-214">O resumo inclui links diretos para o Gerenciador de Conformidade, a solução aplicável no centro de conformidade do Microsoft 365 e documentação relevante.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="ca8f4-215">Clicar no link Gerenciador de Conformidade o leva a uma exibição filtrada de todas as ações de melhoria dentro dessa solução que você ainda não implementou.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="ca8f4-216">A partir daí, você pode ver o número de pontos que você pode alcançar para aumentar sua pontuação de conformidade [e](compliance-score-calculation.md)as avaliações às que se aplicam e os regulamentos e certificações aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="ca8f4-217">Para DLP, há um botão Script de **Correção** que fornece um script do PowerShell pré-gerado com base no que é recomendado.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="ca8f4-218">Você pode copiá-lo e colar diretamente no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="ca8f4-219">Ele criará uma política DLP no modo de teste</span><span class="sxs-lookup"><span data-stu-id="ca8f4-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="ca8f4-220">**Itens com status de recomendação**</span><span class="sxs-lookup"><span data-stu-id="ca8f4-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="ca8f4-221">Selecione o menu suspenso ao lado do rótulo **Recomendação** à direita da ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="ca8f4-222">Você verá um resumo do ambiente atual do Microsoft 365 da sua organização relacionado à ação de melhoria, juntamente com as práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ca8f4-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="ca8f4-223">Recursos</span><span class="sxs-lookup"><span data-stu-id="ca8f4-223">Resources</span></span>

<span data-ttu-id="ca8f4-224">Para obter informações mais detalhadas sobre como instalar, configurar e usar o MCCA, consulte as instruções README no [GitHub](https://github.com/OfficeDev/MCCA#overview) (nenhuma conta do GitHub necessária).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="ca8f4-225">Para obter mais informações Windows PowerShell, comece em [Como usar a documentação do PowerShell.](/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="ca8f4-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="ca8f4-226">Consulte também [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ca8f4-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>