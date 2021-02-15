---
title: Analisador de Configuração de Conformidade da Microsoft para o Gerenciador de Conformidade
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
description: Entenda como usar o Analisador de Configuração de Conformidade da Microsoft para começar a trabalhar rapidamente com o Gerenciador de Conformidade da Microsoft.
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122391"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="ae98b-103">Analisador de Configuração de Conformidade da Microsoft para o Gerenciador de Conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="ae98b-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="ae98b-104">**Neste artigo:** Saiba como instalar e executar a ferramenta Analisador de Configuração de Conformidade da Microsoft para começar rapidamente com o Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="ae98b-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="ae98b-105">Visão geral do Microsoft Compliance Configuration Analyzer (MCCA) (visualização)</span><span class="sxs-lookup"><span data-stu-id="ae98b-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="ae98b-106">O Microsoft Compliance Configuration Analyzer (MCCA) é uma ferramenta de visualização que pode ajudá-lo a começar a usar o Gerenciador de [Conformidade da Microsoft.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="ae98b-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="ae98b-107">A MCCA é um utilitário baseado no PowerShell que buscará as configurações atuais da sua organização e as validará em relação às práticas recomendadas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae98b-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="ae98b-108">Essas práticas recomendadas são baseadas em um conjunto de controles que incluem os principais regulamentos e padrões de proteção de dados e governança de dados.</span><span class="sxs-lookup"><span data-stu-id="ae98b-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="ae98b-109">A MCCA pode ajudá-lo a ver rapidamente quais ações de melhoria no Manger de Conformidade se aplicam ao seu ambiente atual do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae98b-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="ae98b-110">Cada ação identificada pela MCCA lhe dará recomendações para implementação, com links diretos para o Gerenciador de Conformidade e a solução aplicável para começar a tomar medidas corretivas.</span><span class="sxs-lookup"><span data-stu-id="ae98b-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="ae98b-111">Um recurso adicional para entender a MCCA é visitar as instruções [LEIAME no GitHub.](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="ae98b-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="ae98b-112">Esta página fornece informações detalhadas sobre pré-requisitos e fornece instruções completas de instalação.</span><span class="sxs-lookup"><span data-stu-id="ae98b-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="ae98b-113">Você não precisa de uma conta do GitHub para acessar esta página.</span><span class="sxs-lookup"><span data-stu-id="ae98b-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="ae98b-114">**Disponibilidade**: A MCCA está disponível para todas as organizações com licenças do Office 365 e microsoft 365 e clientes moderados da US Government Community (GCC), com planos em andamento para expandir o serviço para clientes GCC High.</span><span class="sxs-lookup"><span data-stu-id="ae98b-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate customers, with plans underway to expand service to to GCC High customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="ae98b-115">Instalar o MCCA e executar um relatório</span><span class="sxs-lookup"><span data-stu-id="ae98b-115">Install MCCA and run a report</span></span>

<span data-ttu-id="ae98b-116">Você pode instalar a ferramenta MCCA usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae98b-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="ae98b-117">Depois de baixar e instalar a ferramenta, você não precisará repetir essas etapas para executar relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae98b-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="ae98b-118">Sempre que você abrir o MCCA, ele solicitará suas credenciais de logon e gerará um novo relatório atualizado.</span><span class="sxs-lookup"><span data-stu-id="ae98b-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="ae98b-119">Etapa 1: Instalar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae98b-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="ae98b-120">Para começar, você precisará do módulo do PowerShell do Exchange Online (v2.0.3 ou superior) que está disponível na galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae98b-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="ae98b-121">[Obter instruções de instalação.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="ae98b-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="ae98b-122">Etapa 2: Instalar o MCCA</span><span class="sxs-lookup"><span data-stu-id="ae98b-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="ae98b-123">Para instalar o MCCA, comece usando o PowerShell no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="ae98b-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="ae98b-124">Siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="ae98b-124">Follow the steps below:</span></span>

1. <span data-ttu-id="ae98b-125">Selecione o botão **Iniciar do** Windows.</span><span class="sxs-lookup"><span data-stu-id="ae98b-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="ae98b-126">Digite **PowerShell**, clique com o botão direito do mouse **no Windows PowerShell**, em seguida, selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="ae98b-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="ae98b-127">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="ae98b-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="ae98b-128">Etapa 3: Executar um relatório</span><span class="sxs-lookup"><span data-stu-id="ae98b-128">Step 3: Run a report</span></span>

<span data-ttu-id="ae98b-129">Depois de instalar o MCCA, você pode executar o MCCA e gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="ae98b-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="ae98b-130">Para executar um relatório:</span><span class="sxs-lookup"><span data-stu-id="ae98b-130">To run a report:</span></span>

1. <span data-ttu-id="ae98b-131">Abra o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae98b-131">Open PowerShell</span></span>
2. <span data-ttu-id="ae98b-132">Execute o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ae98b-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="ae98b-133">Depois que o MCCA é executado, ele faz uma verificação de versão inicial e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="ae98b-133">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="ae98b-134">No prompt de entrada do nome de usuário, entre com seu endereço de email da conta do Microsoft 365 (veja as funções qualificadas[para criar relatórios).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="ae98b-134">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="ae98b-135">Em seguida, insira sua senha no prompt de senha.</span><span class="sxs-lookup"><span data-stu-id="ae98b-135">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="ae98b-136">Seu relatório levará aproximadamente de 2 a 5 minutos para ser gerado.</span><span class="sxs-lookup"><span data-stu-id="ae98b-136">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="ae98b-137">Quando terminar, uma janela do navegador abre e exibe seu relatório HTML.</span><span class="sxs-lookup"><span data-stu-id="ae98b-137">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="ae98b-138">Sempre que você executar a ferramenta, ela solicitará suas credenciais e gerará um novo relatório.</span><span class="sxs-lookup"><span data-stu-id="ae98b-138">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="ae98b-139">Esse relatório é armazenado localmente no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="ae98b-139">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="ae98b-140">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="ae98b-140">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="ae98b-141">Você pode acessar relatórios gerados anteriormente a partir desse diretório.</span><span class="sxs-lookup"><span data-stu-id="ae98b-141">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="ae98b-142">Noções básicas sobre seu relatório</span><span class="sxs-lookup"><span data-stu-id="ae98b-142">Understanding your report</span></span>

<span data-ttu-id="ae98b-143">Seu relatório reflete os dados com base na data e hora em que ele foi gerado.</span><span class="sxs-lookup"><span data-stu-id="ae98b-143">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="ae98b-144">A seção superior fornece detalhes sobre quando ela foi gerada, o nome da sua organização e a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="ae98b-144">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="ae98b-145">Relatórios baseados em geolocalização</span><span class="sxs-lookup"><span data-stu-id="ae98b-145">Geolocation-based reporting</span></span>

<span data-ttu-id="ae98b-146">A **seção** Observação mostra que seu relatório é personalizado com base na localização geográfica do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ae98b-146">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="ae98b-147">As recomendações listadas na ferramenta serão específicas para seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="ae98b-147">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="ae98b-148">Sua seleção de geolocalização é usada para avaliar os sits (tipos de informações confidenciais) que são relevantes para essa localização geográfica e gerar um relatório que se alinha ao seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="ae98b-148">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="ae98b-149">Escolha localizações geográficas com base nos dados que você tem em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ae98b-149">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="ae98b-150">Para alterar as informações de localização do seu relatório, você precisa fornecer um parâmetro de entrada de geolocalização (-Geo).</span><span class="sxs-lookup"><span data-stu-id="ae98b-150">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="ae98b-151">Você pode escolher uma ou várias localizações geográficas aplicáveis ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ae98b-151">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="ae98b-152">Siga estas instruções para executar um relatório com base em um local específico:</span><span class="sxs-lookup"><span data-stu-id="ae98b-152">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="ae98b-153">Abra o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae98b-153">Open PowerShell</span></span>
2. <span data-ttu-id="ae98b-154">Para especificar uma determinada região, você executará um cmdlet usando os números da tabela abaixo que correspondem ao país ou região.</span><span class="sxs-lookup"><span data-stu-id="ae98b-154">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="ae98b-155">Insira vários números separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="ae98b-155">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="ae98b-156">Por exemplo, o cmdlet abaixo executará um relatório personalizado para o Asia-Pacific e o Japão:</span><span class="sxs-lookup"><span data-stu-id="ae98b-156">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="ae98b-157">Input</span><span class="sxs-lookup"><span data-stu-id="ae98b-157">Input</span></span> |  <span data-ttu-id="ae98b-158">País ou Região</span><span class="sxs-lookup"><span data-stu-id="ae98b-158">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="ae98b-159">1 </span><span class="sxs-lookup"><span data-stu-id="ae98b-159">1</span></span> | <span data-ttu-id="ae98b-160">Ásia – Pacífico</span><span class="sxs-lookup"><span data-stu-id="ae98b-160">Asia-Pacific</span></span> |
  | <span data-ttu-id="ae98b-161">2 </span><span class="sxs-lookup"><span data-stu-id="ae98b-161">2</span></span> | <span data-ttu-id="ae98b-162">Austrália</span><span class="sxs-lookup"><span data-stu-id="ae98b-162">Australia</span></span> |
  | <span data-ttu-id="ae98b-163">3 </span><span class="sxs-lookup"><span data-stu-id="ae98b-163">3</span></span> | <span data-ttu-id="ae98b-164">Canadá</span><span class="sxs-lookup"><span data-stu-id="ae98b-164">Canada</span></span> |
  | <span data-ttu-id="ae98b-165">4 </span><span class="sxs-lookup"><span data-stu-id="ae98b-165">4</span></span> | <span data-ttu-id="ae98b-166">Europa (excluindo a França) / Oriente Médio /África</span><span class="sxs-lookup"><span data-stu-id="ae98b-166">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="ae98b-167">5 </span><span class="sxs-lookup"><span data-stu-id="ae98b-167">5</span></span> | <span data-ttu-id="ae98b-168">França</span><span class="sxs-lookup"><span data-stu-id="ae98b-168">France</span></span> |
  | <span data-ttu-id="ae98b-169">6 </span><span class="sxs-lookup"><span data-stu-id="ae98b-169">6</span></span> | <span data-ttu-id="ae98b-170">Índia</span><span class="sxs-lookup"><span data-stu-id="ae98b-170">India</span></span> |
  | <span data-ttu-id="ae98b-171">7 </span><span class="sxs-lookup"><span data-stu-id="ae98b-171">7</span></span> | <span data-ttu-id="ae98b-172">Japão</span><span class="sxs-lookup"><span data-stu-id="ae98b-172">Japan</span></span> |
  | <span data-ttu-id="ae98b-173">8 </span><span class="sxs-lookup"><span data-stu-id="ae98b-173">8</span></span> | <span data-ttu-id="ae98b-174">Coreia</span><span class="sxs-lookup"><span data-stu-id="ae98b-174">Korea</span></span> |
  | <span data-ttu-id="ae98b-175">9 </span><span class="sxs-lookup"><span data-stu-id="ae98b-175">9</span></span> | <span data-ttu-id="ae98b-176">América do Norte (excluindo o Canadá)</span><span class="sxs-lookup"><span data-stu-id="ae98b-176">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="ae98b-177">10 </span><span class="sxs-lookup"><span data-stu-id="ae98b-177">10</span></span> | <span data-ttu-id="ae98b-178">América do Sul</span><span class="sxs-lookup"><span data-stu-id="ae98b-178">South America</span></span> |
  | <span data-ttu-id="ae98b-179">11 </span><span class="sxs-lookup"><span data-stu-id="ae98b-179">11</span></span> | <span data-ttu-id="ae98b-180">África do Sul</span><span class="sxs-lookup"><span data-stu-id="ae98b-180">South Africa</span></span> |
  | <span data-ttu-id="ae98b-181">12 </span><span class="sxs-lookup"><span data-stu-id="ae98b-181">12</span></span> | <span data-ttu-id="ae98b-182">Suíça</span><span class="sxs-lookup"><span data-stu-id="ae98b-182">Switzerland</span></span> |
  | <span data-ttu-id="ae98b-183">13 </span><span class="sxs-lookup"><span data-stu-id="ae98b-183">13</span></span> | <span data-ttu-id="ae98b-184">Emirados Árabes Unidos</span><span class="sxs-lookup"><span data-stu-id="ae98b-184">United Arab Emirates</span></span> |
  | <span data-ttu-id="ae98b-185">14 </span><span class="sxs-lookup"><span data-stu-id="ae98b-185">14</span></span> | <span data-ttu-id="ae98b-186">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ae98b-186">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="ae98b-187">O relatório sempre incluirá tipos de informações confidenciais internacionais com suporte da MCCA, como código SWIFT, número de cartão de crédito etc.</span><span class="sxs-lookup"><span data-stu-id="ae98b-187">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="ae98b-188">Relatórios baseados em função</span><span class="sxs-lookup"><span data-stu-id="ae98b-188">Role-based reporting</span></span>

<span data-ttu-id="ae98b-189">Seu relatório também será personalizado com base em sua função.</span><span class="sxs-lookup"><span data-stu-id="ae98b-189">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="ae98b-190">A tabela a seguir mostra quais funções têm acesso a quais seções do relatório.</span><span class="sxs-lookup"><span data-stu-id="ae98b-190">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="ae98b-191">Outras funções em sua organização (não listadas na tabela abaixo) podem não ser capazes de executar a ferramenta ou podem executar a ferramenta e ter acesso limitado às informações no relatório final.</span><span class="sxs-lookup"><span data-stu-id="ae98b-191">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="ae98b-192">![MCCA - funções](../media/compliance-manager-mcca-roles.png "Funções MCCA")</span><span class="sxs-lookup"><span data-stu-id="ae98b-192">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="ae98b-193">Exceções:</span><span class="sxs-lookup"><span data-stu-id="ae98b-193">Exceptions:</span></span>
1. <span data-ttu-id="ae98b-194">O usuário não poderá gerar relatório para IP além da seção "Usar IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ae98b-194">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="ae98b-195">O usuário poderá gerar relatório para IP além da seção "Usar IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ae98b-195">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="ae98b-196">O usuário poderá gerar relatório para IP além da seção "Habilitar Conformidade de Comunicação no O365".</span><span class="sxs-lookup"><span data-stu-id="ae98b-196">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="ae98b-197">O usuário não poderá gerar relatório para IP além da seção "Habilitar Auditoria no Office 365".</span><span class="sxs-lookup"><span data-stu-id="ae98b-197">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="ae98b-198">O usuário poderá gerar relatório para IP além da seção "Habilitar Auditoria no Office 365".</span><span class="sxs-lookup"><span data-stu-id="ae98b-198">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="ae98b-199">Seção Resumo de Soluções</span><span class="sxs-lookup"><span data-stu-id="ae98b-199">Solutions Summary section</span></span>

<span data-ttu-id="ae98b-200">A **seção Resumo de** Soluções do relatório fornece uma visão geral das ações de melhoria que sua organização pode tomar no Gerenciador de Conformidade para ajudar a melhorar a postura de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ae98b-200">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="ae98b-201">![MCCA - resumo de soluções](../media/compliance-manager-mcca-solutions.png "Tela Resumo de Soluções MCCA")</span><span class="sxs-lookup"><span data-stu-id="ae98b-201">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="ae98b-202">A MCCA avalia suas configurações atuais em relação às ações de melhoria recomendadas no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="ae98b-202">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="ae98b-203">Qualquer ação de melhoria identificada pela ferramenta MCCA como precisando de atenção será listada nesta seção.</span><span class="sxs-lookup"><span data-stu-id="ae98b-203">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="ae98b-204">Ao lado de cada solução da Microsoft, há caixas codificadas por cores indicando o número de itens que correspondem às ações de melhoria no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="ae98b-204">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="ae98b-205">As ações são divididas em três estados de status:</span><span class="sxs-lookup"><span data-stu-id="ae98b-205">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="ae98b-206">**OK**: as ações que atendem às condições recomendadas e não precisam de atenção no momento</span><span class="sxs-lookup"><span data-stu-id="ae98b-206">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="ae98b-207">**Melhoria**: ações que precisam de atenção</span><span class="sxs-lookup"><span data-stu-id="ae98b-207">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="ae98b-208">**Recomendação:** ações que não precisam de atenção, mas para as quais recomendamos as práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="ae98b-208">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="ae98b-209">Selecione uma caixa para exibir as melhorias e recomendações.</span><span class="sxs-lookup"><span data-stu-id="ae98b-209">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="ae98b-210">**Itens com o status de melhoria**</span><span class="sxs-lookup"><span data-stu-id="ae98b-210">**Items with the Improvement status**</span></span>

<span data-ttu-id="ae98b-211">Selecione o menu suspenso ao lado do **rótulo melhoria** à direita da ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="ae98b-211">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="ae98b-212">Você verá um resumo rápido e detalhes sobre suas configurações atuais e as ações de melhoria recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ae98b-212">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="ae98b-213">O resumo inclui links diretos para o Gerenciador de Conformidade, a solução aplicável no centro de conformidade do Microsoft 365 e documentação relevante.</span><span class="sxs-lookup"><span data-stu-id="ae98b-213">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="ae98b-214">Clicar no link do Gerenciador de Conformidade leva você a uma exibição filtrada de todas as ações de melhoria nessa solução que você ainda não implementou.</span><span class="sxs-lookup"><span data-stu-id="ae98b-214">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="ae98b-215">A partir daí, você pode ver o número [](compliance-score-calculation.md)de pontos que você pode alcançar para aumentar sua pontuação de conformidade e as avaliações às que elas se aplicam e os regulamentos e certificações aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="ae98b-215">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="ae98b-216">Para DLP, há um botão **de Script** de Correção que oferece um script do PowerShell pré-gerado com base no que é recomendado.</span><span class="sxs-lookup"><span data-stu-id="ae98b-216">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="ae98b-217">Você pode copiá-lo e colar diretamente no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae98b-217">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="ae98b-218">Ele criará uma política de DLP no modo de teste</span><span class="sxs-lookup"><span data-stu-id="ae98b-218">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="ae98b-219">**Itens com status de recomendação**</span><span class="sxs-lookup"><span data-stu-id="ae98b-219">**Items with Recommendation status**</span></span>

<span data-ttu-id="ae98b-220">Selecione o menu suspenso ao lado do rótulo **Recomendação** à direita da ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="ae98b-220">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="ae98b-221">Você verá um resumo do ambiente atual do Microsoft 365 da sua organização relacionado à ação de melhoria, juntamente com as práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ae98b-221">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="ae98b-222">Recursos</span><span class="sxs-lookup"><span data-stu-id="ae98b-222">Resources</span></span>

<span data-ttu-id="ae98b-223">Para obter informações mais detalhadas sobre como instalar, configurar e usar o MCCA, consulte as instruções LEIAME no [GitHub](https://github.com/OfficeDev/MCCA#overview) (nenhuma conta do GitHub é necessária).</span><span class="sxs-lookup"><span data-stu-id="ae98b-223">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="ae98b-224">Para obter mais informações sobre o Windows PowerShell, comece em [Como usar a documentação do PowerShell.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="ae98b-224">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="ae98b-225">Consulte também [Iniciando o Windows PowerShell.](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="ae98b-225">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
