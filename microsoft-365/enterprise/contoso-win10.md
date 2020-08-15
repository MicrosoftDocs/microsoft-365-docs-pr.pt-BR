---
title: Implantação do Windows 10 Enterprise para a Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usou o Microsoft Endpoint Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.
ms.openlocfilehash: a100eb07408053fd270c26f388265696549fff9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686413"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="a9372-103">Implantação do Windows 10 Enterprise para a Contoso</span><span class="sxs-lookup"><span data-stu-id="a9372-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="a9372-p101">Antes da implantação ampla do Microsoft 365 for Enterprise, a Contoso tinha computadores e dispositivos compatíveis com o Windows que executam uma mistura de Windows 7 (10%), Windows 8,1 (65%) e Windows 10 (25%). A contoso queria atualizar seus computadores para o Windows 10 Enterprise aproveitar a segurança avançada e reduzir a sobrecarga de ti de implantações automatizadas de atualizações.</span><span class="sxs-lookup"><span data-stu-id="a9372-p101">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="a9372-106">Depois de avaliar suas necessidades de infraestrutura e comerciais, a Contoso identificou esses principais requisitos para a implantação:</span><span class="sxs-lookup"><span data-stu-id="a9372-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="a9372-107">O maior número possível de PCs e dispositivos que devem executar o Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9372-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="a9372-108">A distribuição das atualizações in-loco aproveita a infraestrutura existente do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a9372-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="a9372-109">O controle de quais versões do Windows 10 Enterprise implantar e atualizar são feitas por meio de anéis</span><span class="sxs-lookup"><span data-stu-id="a9372-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="a9372-110">Os PCs e dispositivos devem estar atualizados com custos administrativos mínimos de TI e com impacto mínimo para os usuários finais</span><span class="sxs-lookup"><span data-stu-id="a9372-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="a9372-111">A data atual é definida como a versão suportada do Windows 10 Enterprise que atende às necessidades comerciais da Contoso, o que pode ser diferente de ter todos os PCs compatíveis com o Windows que executa a versão mais recente do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a9372-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="a9372-112">Ferramentas de implantação</span><span class="sxs-lookup"><span data-stu-id="a9372-112">Deployment tools</span></span>

<span data-ttu-id="a9372-113">Antes e durante as atualizações in-loco do Windows 10 Enterprise, a Contoso usou as seguintes soluções do Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="a9372-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="a9372-114">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="a9372-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="a9372-115">Coleta dados do sistema, aplicativo e driver para análise e, em seguida, identifica problemas de compatibilidade que podem bloquear uma atualização e correções sugeridas de problemas conhecidos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9372-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="a9372-116">Conformidade de atualização</span><span class="sxs-lookup"><span data-stu-id="a9372-116">Update Compliance</span></span>  

  <span data-ttu-id="a9372-117">Mostra o estado dos dispositivos com relação às atualizações do Windows para que você possa garantir que eles estejam nas atualizações mais recentes conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="a9372-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="a9372-118">Integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a9372-118">Device Health</span></span>  

  <span data-ttu-id="a9372-119">Identifica os dispositivos que falham com frequência e, portanto, talvez precisem ser recriados ou substituídos, e os drivers de dispositivo que estejam falhando, com sugestões de versões alternativas desses drivers, podem reduzir o número de falhas.</span><span class="sxs-lookup"><span data-stu-id="a9372-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="a9372-120">Fornece notificação de configurações incorretas de proteção de informações do Windows que enviam avisos para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="a9372-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="a9372-p103">A Contoso possui uma infraestrutura existente do Configuration Manager (Branch Atual). O Configuration Manager é dimensionado para ambientes grandes e fornece controle extensivo sobre instalações, atualizações e configurações. Ele também possui recursos internos para facilitar e efetivar a implantação e o gerenciamento do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a9372-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="a9372-124">Processo de planejamento</span><span class="sxs-lookup"><span data-stu-id="a9372-124">Planning process</span></span>

<span data-ttu-id="a9372-125">Antes da implantação, a Contoso definiu os seguintes anéis:</span><span class="sxs-lookup"><span data-stu-id="a9372-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="a9372-126">Três anéis para validação e preparação da implantação</span><span class="sxs-lookup"><span data-stu-id="a9372-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="a9372-127">Um para compilações de visualização</span><span class="sxs-lookup"><span data-stu-id="a9372-127">One for preview builds</span></span> 
  - <span data-ttu-id="a9372-128">Um para compilações da nova versão</span><span class="sxs-lookup"><span data-stu-id="a9372-128">One for new release builds</span></span>
  - <span data-ttu-id="a9372-129">Um para compilações anteriores</span><span class="sxs-lookup"><span data-stu-id="a9372-129">One for a previous build</span></span> 
- <span data-ttu-id="a9372-130">Um anel para a implantação geral do Windows 10 Enterprise com base nos dados dos anéis de validação</span><span class="sxs-lookup"><span data-stu-id="a9372-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="a9372-131">A Contoso também usou a solução Upgrade Readiness do Windows Analytics para determinar o conjunto de aplicativos instalados e sua compatibilidade com o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a9372-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="a9372-132">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="a9372-132">Deployment process</span></span>

<span data-ttu-id="a9372-133">Para concluir a implantação da atualização in-loco do Windows 10 Enterprise, a Contoso implementou o seguinte processo, que inclui recomendações de práticas recomendadas da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="a9372-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="a9372-134">Habilitou o cache par para o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a9372-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="a9372-135">Criou pacotes personalizados do Windows com base em imagens do Centro de Atendimento de Licenciamento por Volume.</span><span class="sxs-lookup"><span data-stu-id="a9372-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="a9372-136">Utilizou o Configuration Manager para implantar os pacotes do Windows em pontos de distribuição em toda a rede e em compilações implantadas para os três anéis de armazenamento temporário de validação e implantação.</span><span class="sxs-lookup"><span data-stu-id="a9372-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="a9372-137">Realizou uma avaliação de sucesso para PCs e dispositivos nos três anéis de teste de validação e implantação usando as soluções de Integridade do dispositivos e Conformidade de atualização do Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="a9372-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="a9372-138">Com base nas informações do Windows Analytics, a Contoso determinou qual versão do Windows 10 Enterprise será implantada no anel de implantação geral.</span><span class="sxs-lookup"><span data-stu-id="a9372-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="a9372-139">Executou as sequências das tarefas de implantação do Configuration Manager para implantar o pacote do Windows escolhido no anel de implantação geral.</span><span class="sxs-lookup"><span data-stu-id="a9372-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="a9372-140">Os computadores e dispositivos monitorados na implantação geral usam as soluções de integridade dos dispositivos e conformidade de atualização fornecidas para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="a9372-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="a9372-141">Veja a atualização in-loco e a arquitetura de implantação de atualizações contínuas.</span><span class="sxs-lookup"><span data-stu-id="a9372-141">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Infraestrutura de implantação do Windows 10 Enterprise da Contoso](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="a9372-143">Esta infraestrutura é formada pelo:</span><span class="sxs-lookup"><span data-stu-id="a9372-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="a9372-144">Configuration Manager, que:</span><span class="sxs-lookup"><span data-stu-id="a9372-144">Configuration Manager, which:</span></span>
  - <span data-ttu-id="a9372-145">Obtém imagens para pacotes do Windows 10 Enterprise a partir do Centro de Licenciamento por Volume da Microsoft na Rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9372-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="a9372-146">É o ponto de administração central para pacotes de implantação.</span><span class="sxs-lookup"><span data-stu-id="a9372-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="a9372-147">Pontos de distribuição regionais que normalmente estão localizados nos escritórios secundários da Contoso.</span><span class="sxs-lookup"><span data-stu-id="a9372-147">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="a9372-148">Os dispositivos e computadores Windows em vários locais que recebem e instalam os pacotes de implantação para atualizações in-loco ou atualizações contínuas com base na associação do anel.</span><span class="sxs-lookup"><span data-stu-id="a9372-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="a9372-149">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a9372-149">Next step</span></span>

<span data-ttu-id="a9372-150">[Saiba](contoso-o365pp.md) mais sobre como a Contoso está aproveitando sua infraestrutura do Gerenciador de configurações para implantar e manter os aplicativos atuais do Microsoft 365 para empresas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="a9372-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its Configuration Manager infrastructure to deploy and keep current Microsoft 365 Apps for enterprise across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="a9372-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9372-151">See also</span></span>

[<span data-ttu-id="a9372-152">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9372-152">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="a9372-153">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a9372-153">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a9372-154">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="a9372-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
