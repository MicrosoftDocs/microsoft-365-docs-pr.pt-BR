---
title: Implantação do Windows 10 Enterprise para a Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usou o System Center Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.
ms.openlocfilehash: a63a973bed4bf62ebf7c2534d4c55a4e3b8ef60c
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370468"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="fbda1-103">Implantação do Windows 10 Enterprise para a Contoso</span><span class="sxs-lookup"><span data-stu-id="fbda1-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="fbda1-104">**Resumo:** entenda como a Contoso usou o System Center Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fbda1-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="fbda1-p101">Antes da ampla implantação do Microsoft 365 Enterprise, a Contoso tinha computadores e dispositivos compatíveis com o Windows que executavam uma combinação de Windows 7 (10%), Windows 8.1 (65%) e Windows 10 (25%). A Contoso queria atualizar seus computadores para o Windows 10 Enterprise para aproveitar a segurança aprimorada e reduzir a sobrecarga da TI em implantações automatizadas de atualizações.</span><span class="sxs-lookup"><span data-stu-id="fbda1-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of improved security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="fbda1-107">Depois de avaliar suas necessidades de infraestrutura e comerciais, a Contoso identificou esses principais requisitos para a implantação:</span><span class="sxs-lookup"><span data-stu-id="fbda1-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="fbda1-108">O maior número possível de PCs e dispositivos que devem executar o Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fbda1-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="fbda1-109">A implantação das atualizações in-loco aproveita a infraestrutura existente do System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fbda1-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="fbda1-110">O controle de quais versões do Windows 10 Enterprise implantar e atualizar são feitas por meio de anéis</span><span class="sxs-lookup"><span data-stu-id="fbda1-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="fbda1-111">Os PCs e dispositivos devem estar atualizados com custos administrativos mínimos de TI e com impacto mínimo para os usuários finais</span><span class="sxs-lookup"><span data-stu-id="fbda1-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="fbda1-112">A data atual é definida como a versão suportada do Windows 10 Enterprise que atende às necessidades comerciais da Contoso, o que pode ser diferente de ter todos os PCs compatíveis com o Windows que executa a versão mais recente do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fbda1-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="fbda1-113">Ferramentas de implantação</span><span class="sxs-lookup"><span data-stu-id="fbda1-113">Deployment tools</span></span>

<span data-ttu-id="fbda1-114">Antes e durante as atualizações in-loco do Windows 10 Enterprise, a Contoso usou as seguintes soluções do Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="fbda1-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="fbda1-115">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="fbda1-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="fbda1-116">Coleta dados do sistema, aplicativo e driver para análise e, em seguida, identifica problemas de compatibilidade que podem bloquear uma atualização e correções sugeridas de problemas conhecidos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fbda1-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="fbda1-117">Conformidade de atualização</span><span class="sxs-lookup"><span data-stu-id="fbda1-117">Update Compliance</span></span>  

  <span data-ttu-id="fbda1-118">Mostra o estado dos dispositivos com relação às atualizações do Windows para que você possa garantir que eles estejam nas atualizações mais recentes conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="fbda1-118">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="fbda1-119">Integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="fbda1-119">Device Health</span></span>  

  <span data-ttu-id="fbda1-120">Identifica os dispositivos que falham com frequência e, portanto, talvez precisem ser recriados ou substituídos, e os drivers de dispositivo que estejam falhando, com sugestões de versões alternativas desses drivers, podem reduzir o número de falhas.</span><span class="sxs-lookup"><span data-stu-id="fbda1-120">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="fbda1-121">Fornece notificação de configurações incorretas de proteção de informações do Windows que enviam avisos para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="fbda1-121">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="fbda1-p103">A Contoso possui uma infraestrutura existente do System Center Configuration Manager (Branch Atual). O Configuration Manager é dimensionado para ambientes grandes e fornece controle extensivo sobre instalações, atualizações e configurações. Ele também possui recursos internos para facilitar e efetivar a implantação e o gerenciamento do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fbda1-p103">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="fbda1-125">Processo de planejamento</span><span class="sxs-lookup"><span data-stu-id="fbda1-125">Planning process</span></span>

<span data-ttu-id="fbda1-126">Antes da implantação, a Contoso definiu os seguintes anéis:</span><span class="sxs-lookup"><span data-stu-id="fbda1-126">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="fbda1-127">Três anéis para validação e preparação da implantação</span><span class="sxs-lookup"><span data-stu-id="fbda1-127">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="fbda1-128">Um para compilações de visualização</span><span class="sxs-lookup"><span data-stu-id="fbda1-128">One for preview builds</span></span> 
  - <span data-ttu-id="fbda1-129">Um para compilações da nova versão</span><span class="sxs-lookup"><span data-stu-id="fbda1-129">One for new release builds</span></span>
  - <span data-ttu-id="fbda1-130">Um para compilações anteriores</span><span class="sxs-lookup"><span data-stu-id="fbda1-130">One for a previous build</span></span> 
- <span data-ttu-id="fbda1-131">Um anel para a implantação geral do Windows 10 Enterprise com base nos dados dos anéis de validação</span><span class="sxs-lookup"><span data-stu-id="fbda1-131">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="fbda1-132">A Contoso também usou a solução Upgrade Readiness do Windows Analytics para determinar o conjunto de aplicativos instalados e sua compatibilidade com o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fbda1-132">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="fbda1-133">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="fbda1-133">Deployment process</span></span>

<span data-ttu-id="fbda1-134">Para concluir a implantação da atualização in-loco do Windows 10 Enterprise, a Contoso implementou o seguinte processo, que inclui recomendações de práticas recomendadas da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="fbda1-134">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="fbda1-135">Habilitou o cache par para o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fbda1-135">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="fbda1-136">Criou pacotes personalizados do Windows com base em imagens do Centro de Atendimento de Licenciamento por Volume.</span><span class="sxs-lookup"><span data-stu-id="fbda1-136">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="fbda1-137">Utilizou o Configuration Manager para implantar os pacotes do Windows em pontos de distribuição em toda a rede e em compilações implantadas para os três anéis de armazenamento temporário de validação e implantação.</span><span class="sxs-lookup"><span data-stu-id="fbda1-137">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="fbda1-138">Realizou uma avaliação de sucesso para PCs e dispositivos nos três anéis de teste de validação e implantação usando as soluções de Integridade do dispositivos e Conformidade de atualização do Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="fbda1-138">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="fbda1-139">Com base nas informações do Windows Analytics, a Contoso determinou qual versão do Windows 10 Enterprise será implantada no anel de implantação geral.</span><span class="sxs-lookup"><span data-stu-id="fbda1-139">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="fbda1-140">Executou as sequências das tarefas de implantação do Configuration Manager para implantar o pacote do Windows escolhido no anel de implantação geral.</span><span class="sxs-lookup"><span data-stu-id="fbda1-140">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="fbda1-141">Os computadores e dispositivos monitorados na implantação geral usam as soluções de integridade dos dispositivos e conformidade de atualização fornecidas para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="fbda1-141">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions provided by Windows Analytics to address issues.</span></span>

<span data-ttu-id="fbda1-142">Veja a atualização in-loco e a arquitetura de implantação de atualizações contínuas.</span><span class="sxs-lookup"><span data-stu-id="fbda1-142">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Infraestrutura de implantação do Windows 10 Enterprise da Contoso](./media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="fbda1-144">Esta infraestrutura é formada pelo:</span><span class="sxs-lookup"><span data-stu-id="fbda1-144">This infrastructure consists of:</span></span>

- <span data-ttu-id="fbda1-145">System Center Configuration Manager que:</span><span class="sxs-lookup"><span data-stu-id="fbda1-145">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="fbda1-146">Obtém imagens para pacotes do Windows 10 Enterprise a partir do Centro de Licenciamento por Volume da Microsoft na Rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fbda1-146">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="fbda1-147">É o ponto de administração central para pacotes de implantação.</span><span class="sxs-lookup"><span data-stu-id="fbda1-147">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="fbda1-148">Pontos de distribuição regionais que normalmente estão localizados nos escritórios secundários da Contoso.</span><span class="sxs-lookup"><span data-stu-id="fbda1-148">Regional distribution points that are typically located in Contoso’s satellite offices.</span></span>
- <span data-ttu-id="fbda1-149">Os dispositivos e computadores Windows em vários locais que recebem e instalam os pacotes de implantação para atualizações in-loco ou atualizações contínuas com base na associação do anel.</span><span class="sxs-lookup"><span data-stu-id="fbda1-149">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="fbda1-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="fbda1-150">Next step</span></span>

<span data-ttu-id="fbda1-151">[Saiba](contoso-o365pp.md) mais sobre como a Contoso utiliza a infraestrutura do System Center Configuration Manager para implantar e manter o Office 365 ProPlus atualizado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="fbda1-151">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="fbda1-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="fbda1-152">See also</span></span>

[<span data-ttu-id="fbda1-153">Windows 10 Enterprise para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fbda1-153">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="fbda1-154">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="fbda1-154">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fbda1-155">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="fbda1-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
