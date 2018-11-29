---
title: Implantação do Windows 10 Enterprise para a Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usou o System Center Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.
ms.openlocfilehash: a4b24d55951c83875b9aa08db05fa4f8591472d6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865016"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="b38d8-103">Implantação do Windows 10 Enterprise para a Contoso</span><span class="sxs-lookup"><span data-stu-id="b38d8-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="b38d8-104">**Resumo:** entenda como a Contoso usou o System Center Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b38d8-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="b38d8-p101">Antes da ampla implantação do Microsoft 365 Enterprise, a Contoso tinha PCs e dispositivos compatíveis com o Windows que executavam uma combinação de Windows 7 (10%), Windows 8.1 (65%) e Windows 10 (25%). A Contoso queria atualizar seus PCs para o Windows 10 Enterprise para aproveitar a segurança aprimorada e reduzir a sobrecarga da TI em implantações automatizadas de atualizações.</span><span class="sxs-lookup"><span data-stu-id="b38d8-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of improved security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="b38d8-107">Depois de avaliar suas necessidades de infraestrutura e comerciais, a Contoso identificou esses principais requisitos para a implantação:</span><span class="sxs-lookup"><span data-stu-id="b38d8-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="b38d8-108">O maior número possível de PCs e dispositivos que devem executar o Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b38d8-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="b38d8-109">A implantação das atualizações in-loco aproveita a infraestrutura existente do System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b38d8-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="b38d8-110">O controle de quais versões do Windows 10 Enterprise implantar e atualizar são feitas por meio de anéis</span><span class="sxs-lookup"><span data-stu-id="b38d8-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="b38d8-111">Os PCs e dispositivos devem estar atualizados com custos administrativos mínimos de TI e com impacto mínimo para os usuários finais</span><span class="sxs-lookup"><span data-stu-id="b38d8-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="b38d8-112">A data atual é definida como a versão suportada do Windows 10 Enterprise que atende às necessidades comerciais da Contoso, o que pode ser diferente de ter todos os PCs compatíveis com o Windows que executa a versão mais recente do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b38d8-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="b38d8-113">Ferramentas de implantação</span><span class="sxs-lookup"><span data-stu-id="b38d8-113">Deployment tools</span></span>

<span data-ttu-id="b38d8-114">Antes e durante as atualizações in-loco do Windows 10 Enterprise, a Contoso usou as seguintes soluções do Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="b38d8-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="b38d8-115">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="b38d8-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="b38d8-116">Coleta dados do sistema, aplicativo e driver para análise e, em seguida, identifica problemas de compatibilidade que podem bloquear uma atualização e correções sugeridas de problemas conhecidos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b38d8-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="b38d8-117">Conformidade de atualização</span><span class="sxs-lookup"><span data-stu-id="b38d8-117">Update Compliance</span></span>  

  <span data-ttu-id="b38d8-118">Coleta dados do sistema e de diagnóstico, incluindo o progresso da instalação da atualização, dados de configuração do Windows Update para Empresas (WUfB), dados do Windows Defender Antivírus e outras informações específicas da atualização, e armazena esses dados na análise e uso da nuvem.</span><span class="sxs-lookup"><span data-stu-id="b38d8-118">Collects system and diagnostics data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>

- <span data-ttu-id="b38d8-119">Integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b38d8-119">Device Health</span></span>  

  <span data-ttu-id="b38d8-120">Coleta dados do sistema e de diagnóstico do Windows 10, incluindo o progresso da instalação da atualização, dados de configuração do Windows Update para Empresas (WUfB), dados do Windows Defender Antivírus e outras informações específicas da atualização, e armazena esses dados na análise e uso da nuvem.</span><span class="sxs-lookup"><span data-stu-id="b38d8-120">Collects Windows 10 system and diagnostic data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>
 
<span data-ttu-id="b38d8-p102">A Contoso possui uma infraestrutura existente do System Center Configuration Manager (Branch Atual). O Configuration Manager é dimensionado para ambientes grandes e fornece controle extensivo sobre instalações, atualizações e configurações. Ele também possui recursos internos para facilitar e efetivar a implantação e o gerenciamento do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b38d8-p102">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="b38d8-124">Processo de planejamento</span><span class="sxs-lookup"><span data-stu-id="b38d8-124">Planning process</span></span>

<span data-ttu-id="b38d8-125">Antes da implantação, a Contoso definiu os seguintes anéis:</span><span class="sxs-lookup"><span data-stu-id="b38d8-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="b38d8-126">Três anéis para validação e preparação da implantação</span><span class="sxs-lookup"><span data-stu-id="b38d8-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="b38d8-127">Um para compilações de visualização</span><span class="sxs-lookup"><span data-stu-id="b38d8-127">One for preview builds</span></span> 
  - <span data-ttu-id="b38d8-128">Um para compilações da nova versão</span><span class="sxs-lookup"><span data-stu-id="b38d8-128">One for new release builds</span></span>
  - <span data-ttu-id="b38d8-129">Um para compilações anteriores</span><span class="sxs-lookup"><span data-stu-id="b38d8-129">One for a previous build</span></span> 
- <span data-ttu-id="b38d8-130">Um anel para a implantação geral do Windows 10 Enterprise com base nos dados dos anéis de validação</span><span class="sxs-lookup"><span data-stu-id="b38d8-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="b38d8-131">A Contoso também usou a solução Upgrade Readiness do Windows Analytics para determinar o conjunto de aplicativos instalados e sua compatibilidade com o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b38d8-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="b38d8-132">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="b38d8-132">Deployment process</span></span>

<span data-ttu-id="b38d8-133">Para concluir a implantação da atualização in-loco do Windows 10 Enterprise, a Contoso implementou o seguinte processo, que inclui recomendações de práticas recomendadas da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b38d8-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="b38d8-134">Habilitou o cache par para o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b38d8-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="b38d8-135">Criou pacotes personalizados do Windows com base em imagens do Centro de Atendimento de Licenciamento por Volume.</span><span class="sxs-lookup"><span data-stu-id="b38d8-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="b38d8-136">Utilizou o Configuration Manager para implantar os pacotes do Windows em pontos de distribuição em toda a rede e em compilações implantadas para os três anéis de armazenamento temporário de validação e implantação.</span><span class="sxs-lookup"><span data-stu-id="b38d8-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="b38d8-137">Realizou uma avaliação de sucesso para PCs e dispositivos nos três anéis de teste de validação e implantação usando as soluções de Integridade do dispositivos e Conformidade de atualização do Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="b38d8-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="b38d8-138">Com base nas informações do Windows Analytics, a Contoso determinou qual versão do Windows 10 Enterprise será implantada no anel de implantação geral.</span><span class="sxs-lookup"><span data-stu-id="b38d8-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="b38d8-139">Executou as sequências das tarefas de implantação do Configuration Manager para implantar o pacote do Windows escolhido no anel de implantação geral.</span><span class="sxs-lookup"><span data-stu-id="b38d8-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="b38d8-140">Os computadores e dispositivos monitorados na implantação geral usam as soluções de Integridade do dispositivos e Conformidade de atualização fornecidas pelo Windows Analytics para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="b38d8-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions provided by Windows Analytics to address issues.</span></span>

<span data-ttu-id="b38d8-141">A Figura 1 mostra a atualização in-loco e a arquitetura de implantação de atualizações contínuas.</span><span class="sxs-lookup"><span data-stu-id="b38d8-141">Figure 1 shows the in-place upgrade and ongoing updates deployment architecture.</span></span>

![](./media/contoso-win10/contoso-win10-fig1.png)
 
<span data-ttu-id="b38d8-142">**Figura 1: infraestrutura de implantação do Windows 10 Enterprise da Contoso**</span><span class="sxs-lookup"><span data-stu-id="b38d8-142">**Figure 1: Contoso’s Windows 10 Enterprise deployment infrastructure**</span></span>

<span data-ttu-id="b38d8-143">Esta infraestrutura é formada pelo:</span><span class="sxs-lookup"><span data-stu-id="b38d8-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="b38d8-144">System Center Configuration Manager que:</span><span class="sxs-lookup"><span data-stu-id="b38d8-144">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="b38d8-145">Obtém imagens para pacotes do Windows 10 Enterprise a partir do Centro de Licenciamento por Volume da Microsoft na Rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b38d8-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="b38d8-146">É o ponto de administração central para pacotes de implantação.</span><span class="sxs-lookup"><span data-stu-id="b38d8-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="b38d8-147">Pontos de distribuição regionais que normalmente estão localizados nos escritórios secundários da Contoso.</span><span class="sxs-lookup"><span data-stu-id="b38d8-147">Regional distribution points that are typically located in Contoso’s satellite offices.</span></span>
- <span data-ttu-id="b38d8-148">Os dispositivos e computadores Windows em vários locais que recebem e instalam os pacotes de implantação para atualizações in-loco ou atualizações contínuas com base na associação do anel.</span><span class="sxs-lookup"><span data-stu-id="b38d8-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="b38d8-149">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b38d8-149">Next step</span></span>

<span data-ttu-id="b38d8-150">[Saiba](contoso-o365pp.md) mais sobre como a Contoso utiliza a infraestrutura do System Center Configuration Manager para implantar e manter o Office 365 ProPlus atualizado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="b38d8-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="b38d8-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="b38d8-151">See also</span></span>

[<span data-ttu-id="b38d8-152">Windows 10 Enterprise para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b38d8-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="b38d8-153">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="b38d8-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b38d8-154">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="b38d8-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
