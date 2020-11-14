---
title: Analisador de configuração de conformidade da Microsoft para o gerente de conformidade
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
description: Saiba como usar o analisador de configuração de conformidade da Microsoft para começar a trabalhar rapidamente com o Gerenciador de conformidade da Microsoft.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071990"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a><span data-ttu-id="dc3c8-103">Analisador de configuração de conformidade da Microsoft para o gerente de conformidade</span><span class="sxs-lookup"><span data-stu-id="dc3c8-103">Microsoft Compliance Configuration Analyzer for Compliance Manager</span></span>

<span data-ttu-id="dc3c8-104">**Neste artigo:** Saiba como instalar e executar a ferramenta Microsoft Compliance configure Analyzer para começar rapidamente com o Microsoft Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a><span data-ttu-id="dc3c8-105">Visão geral do MCCA (Microsoft Compliance Configuration Analyzer)</span><span class="sxs-lookup"><span data-stu-id="dc3c8-105">Microsoft Compliance Configuration Analyzer (MCCA) overview</span></span>

<span data-ttu-id="dc3c8-106">O analisador de configuração de conformidade da Microsoft (MCCA) é uma ferramenta que pode ajudá-lo a começar a usar [o gerente de conformidade da Microsoft](compliance-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="dc3c8-107">O MCCA é um utilitário baseado no PowerShell que buscará as configurações atuais da sua organização e as validará em relação às práticas recomendadas da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="dc3c8-108">Essas práticas recomendadas baseiam-se em um conjunto de controles que incluem normas e padrões fundamentais para proteção de dados e governança de dados.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="dc3c8-109">O MCCA pode ajudá-lo a ver rapidamente quais ações de melhoria no Gerenciador de conformidade se aplicam ao seu ambiente atual do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="dc3c8-110">Cada ação identificada por MCCA fornecerá recomendações para implementação, com links diretos para o Gerenciador de conformidade e a solução aplicável para começar a realizar ações corretivas.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="dc3c8-111">Um recurso adicional para entender o MCCA é visitar as [instruções Leiame no GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="dc3c8-112">Esta página fornece informações detalhadas sobre os pré-requisitos e fornece instruções de instalação completas.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="dc3c8-113">Você não precisa de uma conta do GitHub para acessar essa página.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-113">You don’t need a GitHub account to access this page.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="dc3c8-114">Instalar o MCCA e executar um relatório</span><span class="sxs-lookup"><span data-stu-id="dc3c8-114">Install MCCA and run a report</span></span>

<span data-ttu-id="dc3c8-115">Você pode instalar a ferramenta MCCA usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-115">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="dc3c8-116">Depois de baixar e instalar a ferramenta, não será necessário repetir essas etapas para executar relatórios.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-116">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="dc3c8-117">Cada vez que você abrir o MCCA, ele solicitará suas credenciais de login e gerará um relatório novo e atualizado.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-117">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="dc3c8-118">Etapa 1: instalar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc3c8-118">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="dc3c8-119">Para começar, você precisará do módulo do PowerShell do Exchange Online (v 2.0.3 ou superior) que está disponível na galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-119">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="dc3c8-120">[Obtenha instruções de instalação](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-120">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="dc3c8-121">Etapa 2: instalar o MCCA</span><span class="sxs-lookup"><span data-stu-id="dc3c8-121">Step 2: Install MCCA</span></span>

<span data-ttu-id="dc3c8-122">Para instalar o MCCA, comece usando o PowerShell no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-122">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="dc3c8-123">Siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-123">Follow the steps below:</span></span>

1. <span data-ttu-id="dc3c8-124">Selecione o botão **Iniciar** do Windows.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-124">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="dc3c8-125">Digite **PowerShell** , clique com o botão direito do mouse no **Windows PowerShell** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-125">Type **PowerShell** , right-click on **Windows PowerShell** , then select **Run as administrator**.</span></span>
1. <span data-ttu-id="dc3c8-126">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-126">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="dc3c8-127">Etapa 3: executar um relatório</span><span class="sxs-lookup"><span data-stu-id="dc3c8-127">Step 3: Run a report</span></span>

<span data-ttu-id="dc3c8-128">Após instalar o MCCA, você pode executar o MCCA e gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-128">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="dc3c8-129">Para executar um relatório:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-129">To run a report:</span></span>

1. <span data-ttu-id="dc3c8-130">Abrir o PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc3c8-130">Open PowerShell</span></span>
2. <span data-ttu-id="dc3c8-131">Execute o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-131">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="dc3c8-132">Após o MCCA ser executado, uma versão inicial verifica e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-132">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="dc3c8-133">No prompt de entrada de nome de usuário, entre com seu endereço de email da conta do Microsoft 365 ([exiba as funções qualificadas para criar relatórios](#role-based-reporting)).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-133">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="dc3c8-134">Em seguida, insira sua senha no prompt de senha.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-134">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="dc3c8-135">O relatório levará aproximadamente 2-5 minutos para ser gerado.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-135">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="dc3c8-136">Quando ela é concluída, uma janela do navegador abre e exibe o relatório HTML.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-136">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="dc3c8-137">Toda vez que você executar a ferramenta, ela solicitará suas credenciais e gerará um novo relatório.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-137">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="dc3c8-138">Esse relatório é armazenado localmente no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-138">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="dc3c8-139">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-139">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="dc3c8-140">Você pode acessar os relatórios gerados anteriormente desse diretório.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-140">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="dc3c8-141">Noções básicas sobre o relatório</span><span class="sxs-lookup"><span data-stu-id="dc3c8-141">Understanding your report</span></span>

<span data-ttu-id="dc3c8-142">O relatório reflete os dados com base na data e hora em que foi gerado.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-142">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="dc3c8-143">A seção superior fornece detalhes sobre quando ele foi gerado, o nome da sua organização e a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-143">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="dc3c8-144">Relatórios baseados em geolocalização</span><span class="sxs-lookup"><span data-stu-id="dc3c8-144">Geolocation-based reporting</span></span>

<span data-ttu-id="dc3c8-145">A seção **Observação** mostra que o relatório é personalizado com base na localização geográfica do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-145">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="dc3c8-146">As recomendações listadas na ferramenta serão específicas do seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-146">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="dc3c8-147">A seleção de localização geográfica é usada para avaliar os tipos de informações confidenciais (no) que são relevantes para a localização geográfica e gerar um relatório que se alinhe ao seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-147">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="dc3c8-148">Escolha geolocations com base nos dados que você tem em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-148">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="dc3c8-149">Para alterar as informações de local de seu relatório, você precisa fornecer um parâmetro de entrada de localização geográfica (-GEO).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-149">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="dc3c8-150">Você pode escolher uma ou várias geolocalidades aplicáveis ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-150">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="dc3c8-151">Siga estas instruções para executar um relatório baseado em um local específico:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-151">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="dc3c8-152">Abrir o PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc3c8-152">Open PowerShell</span></span>
2. <span data-ttu-id="dc3c8-153">Para especificar uma determinada região, você executará um cmdlet usando os números da tabela abaixo que correspondem ao país ou à região.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-153">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="dc3c8-154">Insira vários números separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-154">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="dc3c8-155">Por exemplo, o cmdlet abaixo executará um relatório personalizado para o Asia-Pacific e o Japão:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-155">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="dc3c8-156">Input</span><span class="sxs-lookup"><span data-stu-id="dc3c8-156">Input</span></span> |  <span data-ttu-id="dc3c8-157">País ou Região</span><span class="sxs-lookup"><span data-stu-id="dc3c8-157">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="dc3c8-158">1</span><span class="sxs-lookup"><span data-stu-id="dc3c8-158">1</span></span> | <span data-ttu-id="dc3c8-159">Ásia – Pacífico</span><span class="sxs-lookup"><span data-stu-id="dc3c8-159">Asia-Pacific</span></span> |
  | <span data-ttu-id="dc3c8-160">duas</span><span class="sxs-lookup"><span data-stu-id="dc3c8-160">2</span></span> | <span data-ttu-id="dc3c8-161">Austrália</span><span class="sxs-lookup"><span data-stu-id="dc3c8-161">Australia</span></span> |
  | <span data-ttu-id="dc3c8-162">3D</span><span class="sxs-lookup"><span data-stu-id="dc3c8-162">3</span></span> | <span data-ttu-id="dc3c8-163">Canadá</span><span class="sxs-lookup"><span data-stu-id="dc3c8-163">Canada</span></span> |
  | <span data-ttu-id="dc3c8-164">4 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-164">4</span></span> | <span data-ttu-id="dc3c8-165">Europa (exceto França)/Oriente Médio/África</span><span class="sxs-lookup"><span data-stu-id="dc3c8-165">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="dc3c8-166">5 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-166">5</span></span> | <span data-ttu-id="dc3c8-167">França</span><span class="sxs-lookup"><span data-stu-id="dc3c8-167">France</span></span> |
  | <span data-ttu-id="dc3c8-168">6 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-168">6</span></span> | <span data-ttu-id="dc3c8-169">Índia</span><span class="sxs-lookup"><span data-stu-id="dc3c8-169">India</span></span> |
  | <span data-ttu-id="dc3c8-170">7 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-170">7</span></span> | <span data-ttu-id="dc3c8-171">Japão</span><span class="sxs-lookup"><span data-stu-id="dc3c8-171">Japan</span></span> |
  | <span data-ttu-id="dc3c8-172">8 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-172">8</span></span> | <span data-ttu-id="dc3c8-173">Coreia</span><span class="sxs-lookup"><span data-stu-id="dc3c8-173">Korea</span></span> |
  | <span data-ttu-id="dc3c8-174">9 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-174">9</span></span> | <span data-ttu-id="dc3c8-175">América do Norte (exceto Canadá)</span><span class="sxs-lookup"><span data-stu-id="dc3c8-175">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="dc3c8-176">10 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-176">10</span></span> | <span data-ttu-id="dc3c8-177">América do Sul</span><span class="sxs-lookup"><span data-stu-id="dc3c8-177">South America</span></span> |
  | <span data-ttu-id="dc3c8-178">11 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-178">11</span></span> | <span data-ttu-id="dc3c8-179">África do Sul</span><span class="sxs-lookup"><span data-stu-id="dc3c8-179">South Africa</span></span> |
  | <span data-ttu-id="dc3c8-180">12 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-180">12</span></span> | <span data-ttu-id="dc3c8-181">Suíça</span><span class="sxs-lookup"><span data-stu-id="dc3c8-181">Switzerland</span></span> |
  | <span data-ttu-id="dc3c8-182">13 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-182">13</span></span> | <span data-ttu-id="dc3c8-183">Emirados Árabes Unidos</span><span class="sxs-lookup"><span data-stu-id="dc3c8-183">United Arab Emirates</span></span> |
  | <span data-ttu-id="dc3c8-184">14 </span><span class="sxs-lookup"><span data-stu-id="dc3c8-184">14</span></span> | <span data-ttu-id="dc3c8-185">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="dc3c8-185">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="dc3c8-186">O relatório sempre incluirá tipos de informações confidenciais internacionais suportados, como código SWIFT, número de cartão de crédito, etc.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-186">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="dc3c8-187">Relatórios baseados em função</span><span class="sxs-lookup"><span data-stu-id="dc3c8-187">Role-based reporting</span></span>

<span data-ttu-id="dc3c8-188">O relatório também será personalizado com base em sua função.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-188">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="dc3c8-189">A tabela abaixo mostra quais funções têm acesso a quais seções do relatório.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-189">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="dc3c8-190">Outras funções dentro da sua organização (não listadas na tabela abaixo) podem não ser capazes de executar a ferramenta ou podem executar a ferramenta e ter acesso limitado às informações no relatório final.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-190">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="dc3c8-191">![MCCA-funções](../media/compliance-manager-mcca-roles.png "Funções MCCA")</span><span class="sxs-lookup"><span data-stu-id="dc3c8-191">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="dc3c8-192">Exceções</span><span class="sxs-lookup"><span data-stu-id="dc3c8-192">Exceptions:</span></span>
1. <span data-ttu-id="dc3c8-193">O usuário não conseguirá gerar relatórios de IP separados da seção "usar o IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="dc3c8-193">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="dc3c8-194">O usuário poderá gerar relatórios de IP separados da seção "usar o IRM para Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="dc3c8-194">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="dc3c8-195">O usuário poderá gerar o relatório de IP separado da seção "Habilitar conformidade de comunicação no O365".</span><span class="sxs-lookup"><span data-stu-id="dc3c8-195">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="dc3c8-196">O usuário não conseguirá gerar relatórios de IP separados da seção "habilitar auditoria no Office 365".</span><span class="sxs-lookup"><span data-stu-id="dc3c8-196">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="dc3c8-197">O usuário poderá gerar o relatório para o IP separado da seção "habilitar auditoria no Office 365".</span><span class="sxs-lookup"><span data-stu-id="dc3c8-197">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="dc3c8-198">Seção Resumo de soluções</span><span class="sxs-lookup"><span data-stu-id="dc3c8-198">Solutions Summary section</span></span>

<span data-ttu-id="dc3c8-199">A seção **Resumo das soluções** do relatório fornece uma visão geral das ações de aperfeiçoamento que sua organização pode executar no gerente de conformidade para ajudar a melhorar a postura de conformidade.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-199">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="dc3c8-200">![Resumo do MCCA-Solutions](../media/compliance-manager-mcca-solutions.png "Tela de Resumo de soluções do MCCA")</span><span class="sxs-lookup"><span data-stu-id="dc3c8-200">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="dc3c8-201">O MCCA avalia suas configurações atuais em relação às ações de melhoria recomendadas no Gerenciador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-201">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="dc3c8-202">Qualquer ação de melhoria identificada pela ferramenta MCCA como precisa de atenção será listada nesta seção.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-202">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="dc3c8-203">Ao lado de cada solução da Microsoft são caixas com códigos de cores que indicam o número de itens que correspondem às ações de melhoria no Gerenciador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-203">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="dc3c8-204">As ações são divididas em três Estados de status:</span><span class="sxs-lookup"><span data-stu-id="dc3c8-204">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="dc3c8-205">**OK** : as ações que atendem às condições recomendadas e não precisam de atenção no momento</span><span class="sxs-lookup"><span data-stu-id="dc3c8-205">**OK** : the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="dc3c8-206">**Melhoria** : ações que precisam de atenção</span><span class="sxs-lookup"><span data-stu-id="dc3c8-206">**Improvement** : actions that need attention</span></span>
- <span data-ttu-id="dc3c8-207">**Recomendação** : ações que não precisam de atenção, mas para as quais recomendamos práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="dc3c8-207">**Recommendation** : actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="dc3c8-208">Selecione uma caixa para exibir melhorias e recomendações.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-208">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="dc3c8-209">**Itens com o status de melhoria**</span><span class="sxs-lookup"><span data-stu-id="dc3c8-209">**Items with the Improvement status**</span></span>

<span data-ttu-id="dc3c8-210">Selecione o menu suspenso ao lado do rótulo de **melhoria** à direita da ação de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-210">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="dc3c8-211">Você verá um resumo rápido e detalhes sobre as configurações atuais e as ações de melhoria recomendadas.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-211">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="dc3c8-212">O resumo inclui links diretos no gerente de conformidade, a solução aplicável no centro de conformidade da Microsoft 365 e a documentação relevante.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-212">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="dc3c8-213">Clicar no link do Gerenciador de conformidade leva você a uma exibição filtrada de todas as ações de aprimoramento dentro dessa solução que você ainda não tenha implementado.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-213">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="dc3c8-214">A partir daí, você pode ver o número de pontos que você pode alcançar para aumentar sua [Pontuação de conformidade](compliance-score-calculation.md)e as avaliações às quais eles se aplicam e as regulamentações e certificações aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-214">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="dc3c8-215">Para DLP, há um botão de **script de correção** que fornece um script do PowerShell gerado previamente com base no que é recomendado.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-215">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="dc3c8-216">Você pode copiá-lo e colá-lo diretamente no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-216">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="dc3c8-217">Ele criará uma política de DLP no modo de teste</span><span class="sxs-lookup"><span data-stu-id="dc3c8-217">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="dc3c8-218">**Itens com status de recomendação**</span><span class="sxs-lookup"><span data-stu-id="dc3c8-218">**Items with Recommendation status**</span></span>

<span data-ttu-id="dc3c8-219">Selecione o menu suspenso ao lado do rótulo de **recomendação** à direita da ação de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-219">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="dc3c8-220">Você verá um resumo do ambiente atual do Microsoft 365 da sua organização relacionado à ação de melhoria, juntamente com as práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="dc3c8-220">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="dc3c8-221">Recursos</span><span class="sxs-lookup"><span data-stu-id="dc3c8-221">Resources</span></span>

<span data-ttu-id="dc3c8-222">Para obter informações mais detalhadas sobre como instalar, configurar e usar o MCCA, consulte as [instruções de Leiame no GitHub](https://github.com/OfficeDev/MCCA#overview) (nenhuma conta do GitHub necessária).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-222">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="dc3c8-223">Para obter mais informações sobre o Windows PowerShell, comece a [usar a documentação do PowerShell](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-223">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="dc3c8-224">Consulte também [iniciando o Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="dc3c8-224">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
