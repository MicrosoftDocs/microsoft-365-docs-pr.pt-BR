---
title: Etapa 4. Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Use o Microsoft Endpoint Manager para gerenciar seus dispositivos, PCs e outros pontos de extremidade.
ms.openlocfilehash: 5c6e433918709a55f03d786891ec0fd7ac62a26b
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377230"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="beee2-104">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="beee2-104">Step 4.</span></span> <span data-ttu-id="beee2-105">Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="beee2-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="beee2-106">Com funcionários remotos, é necessário oferecer suporte a um número crescente de dispositivos pessoais.</span><span class="sxs-lookup"><span data-stu-id="beee2-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="beee2-107">O gerenciamento de pontos de extremidade é uma abordagem de segurança baseada em políticas que exige que os dispositivos obedeçam a critérios específicos antes de receberem acesso aos recursos.</span><span class="sxs-lookup"><span data-stu-id="beee2-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="beee2-108">O Microsoft Endpoint Manager oferece um ambiente de trabalho e recursos de gerenciamento modernos para manter seus dados seguros na nuvem e no local.</span><span class="sxs-lookup"><span data-stu-id="beee2-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="beee2-109">O Endpoint Manager fornece serviços e ferramentas para gerenciar dispositivos móveis, computadores desktop, máquinas virtuais, dispositivos incorporados e servidores combinando os seguintes serviços que você já deve conhecer e estar usando.</span><span class="sxs-lookup"><span data-stu-id="beee2-109">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![Os componentes para o gerenciamento de pontos de extremidade](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="beee2-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="beee2-111">Microsoft Intune</span></span>

<span data-ttu-id="beee2-112">O Microsoft Intune é um serviço baseado em nuvem com foco no gerenciamento de dispositivos móveis (MDM) e no gerenciamento de aplicativos móveis (MAM) que vem incluído no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="beee2-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="beee2-113">**MDM:** Para os dispositivos pertencentes à organização, você pode exercer um controle total, que inclui as configurações, os recursos e a segurança.</span><span class="sxs-lookup"><span data-stu-id="beee2-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="beee2-114">Os dispositivos serão “matriculados” no Intune sempre que utilizarem políticas do Intune referentes a regras e configurações.</span><span class="sxs-lookup"><span data-stu-id="beee2-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="beee2-115">Por exemplo, você pode configurar exigências de senha e PIN, criar uma conexão de VPN, configurar a proteção contra ameaças e muito mais.</span><span class="sxs-lookup"><span data-stu-id="beee2-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="beee2-116">**MAM:** As pessoas que trabalham remotamente podem não querer que você tenha um controle total de seus dispositivos pessoais, também conhecidos como dispositivos “BYOD”, do inglês “traga seu próprio dispositivo”.</span><span class="sxs-lookup"><span data-stu-id="beee2-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="beee2-117">Você pode oferecer opções aos seus funcionários remotos e ainda assim proteger a sua organização.</span><span class="sxs-lookup"><span data-stu-id="beee2-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="beee2-118">Por exemplo, os funcionários remotos podem matricular seus dispositivos se desejarem ter acesso total aos recursos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="beee2-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="beee2-119">Alternativamente, se esses usuários desejarem acesso somente ao email ou ao Microsoft Teams,poderão optar por aplicar políticas de proteção de aplicativos que exigem uma autenticação multifator (MFA) para o uso desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="beee2-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="beee2-120">Para obter mais informações, confira a [visão geral do Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="beee2-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="beee2-121">Gerenciador de Configurações</span><span class="sxs-lookup"><span data-stu-id="beee2-121">Configuration Manager</span></span>

<span data-ttu-id="beee2-122">O Gerenciador de Configurações é uma solução de gerenciamento local para gerenciar desktops, servidores e laptops que estão na sua rede ou baseada na Internet.</span><span class="sxs-lookup"><span data-stu-id="beee2-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="beee2-123">Use o Gerenciador de Configurações para implantar aplicativos, atualizações de software e sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="beee2-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="beee2-124">Você também pode monitorar a conformidade, consultar e agir sobre os clientes em tempo real e muito mais.</span><span class="sxs-lookup"><span data-stu-id="beee2-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="beee2-125">Você pode habilitá-lo na nuvem para integrar-se ao Intune, Azure AD, Microsoft Defender ATP e outros serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="beee2-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> 

<span data-ttu-id="beee2-126">Para obter mais informações, confira a [visão geral do Gerenciador de Configurações](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="beee2-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="beee2-127">Co-gerenciamento</span><span class="sxs-lookup"><span data-stu-id="beee2-127">Co-management</span></span>

<span data-ttu-id="beee2-128">O co-gerenciamento combina seu investimento existente no Gerenciador de Configurações no local com a nuvem, usando o Intune e outros serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="beee2-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="beee2-129">Você decide se a autoridade de gerenciamento para diferentes cargas de trabalho será o Gerenciador de Configurações ou o Intune.</span><span class="sxs-lookup"><span data-stu-id="beee2-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="beee2-130">O gerenciamento compartilhado utiliza recursos na nuvem baseados no Intune, entre eles o acesso condicional e a aplicação da conformidade de dispositivos. </span><span class="sxs-lookup"><span data-stu-id="beee2-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="beee2-131">Algumas tarefas são mantidas no local e outras são executadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="beee2-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="beee2-132">Para mais informações, confira esta [visão geral do co-gerenciamento](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span><span class="sxs-lookup"><span data-stu-id="beee2-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="beee2-133">Análise de Área de Trabalho</span><span class="sxs-lookup"><span data-stu-id="beee2-133">Desktop Analytics</span></span>

<span data-ttu-id="beee2-134">A Análise de Área de Trabalho é um serviço baseado em nuvem que se integra ao Gerenciador de Configurações e fornece informações e inteligência para que você possa tomar decisões informadas sobre seus clientes Windows.</span><span class="sxs-lookup"><span data-stu-id="beee2-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="beee2-135">Ela combina dados da sua organização com dados agregados de milhões de dispositivos conectados aos serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="beee2-135">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="beee2-136">Com a Análise de Área de Trabalho, você pode:</span><span class="sxs-lookup"><span data-stu-id="beee2-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="beee2-137">Criar um inventário das aplicações executadas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="beee2-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="beee2-138">Avaliar a compatibilidade de aplicativos com as atualizações mais recentes dos recursos do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="beee2-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="beee2-139">Identificar problemas de compatibilidade e receber sugestões de atenuação baseadas em insights de dados habilitados para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="beee2-139">Identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="beee2-140">Criar grupos piloto que representem todo o aplicativo e o estado do driver em um conjunto mínimo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="beee2-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="beee2-141">Implantar o Windows 10 em dispositivos piloto e gerenciados em ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="beee2-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="beee2-142">Para obter mais informações, confira a [visão geral da Análise de Área de Trabalho](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).</span><span class="sxs-lookup"><span data-stu-id="beee2-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="beee2-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="beee2-143">Windows Autopilot</span></span>

<span data-ttu-id="beee2-144">O Windows Autopilot é uma plataforma de implantação do Windows de autoatendimento e sem intervenções.</span><span class="sxs-lookup"><span data-stu-id="beee2-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="beee2-145">Inclui um conjunto de tecnologias usadas para instalar e pré-configurar novos dispositivos, preparando-os para uso produtivo.</span><span class="sxs-lookup"><span data-stu-id="beee2-145">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="beee2-146">Você também pode usar o Windows Autopilot para redefinir, redirecionar e recuperar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="beee2-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="beee2-147">O Windows Autopilot permite que o departamento de Ti pré-configure dispositivos com pouca ou nenhuma infraestrutura para gerenciar, por meio de um processo simples e fácil.</span><span class="sxs-lookup"><span data-stu-id="beee2-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="beee2-148">Da perspectiva do usuário, são necessárias apenas algumas operações simples para deixar seu dispositivo pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="beee2-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="beee2-149">Da perspectiva do profissional de TI, a única interação necessária do usuário final é conectar-se a uma rede e verificar suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="beee2-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="beee2-150">Para obter mais informações, confira a [visão geral do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span><span class="sxs-lookup"><span data-stu-id="beee2-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="beee2-151">Recursos técnicos de administração para o gerenciamento de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="beee2-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="beee2-152">Vídeo da parte 3 sobre o gerenciamento de dispositivos Windows 10 para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="beee2-152">The Part 3 video on managing Windows 10 devices for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="beee2-153">Vídeo da parte 5 sobre o gerenciamento de áreas de trabalho e navegadores do usuário para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="beee2-153">The Part 5 video on managing user desktops and browsers for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="beee2-154">Implantar uma infraestrutura de mobilidade para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="beee2-154">Deploy a mobility infrastructure for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="beee2-155">Como registrar diferentes tipos de dispositivos para gerenciamento de dispositivos móveis (MDM)</span><span class="sxs-lookup"><span data-stu-id="beee2-155">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="beee2-156">Como educar seus usuários finais sobre o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="beee2-156">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="beee2-157">Resultados da Etapa 3</span><span class="sxs-lookup"><span data-stu-id="beee2-157">Results of Step 3</span></span>

<span data-ttu-id="beee2-158">Você está usando o conjunto de recursos e funcionalidades do Endpoint Manager para gerenciar dispositivos móveis, computadores desktop, máquinas virtuais, dispositivos incorporados e servidores.</span><span class="sxs-lookup"><span data-stu-id="beee2-158">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="beee2-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="beee2-159">Next step</span></span>

<span data-ttu-id="beee2-160">Prossiga para a [Etapa 5](empower-people-to-work-remotely-teams-productivity-apps.md) para fazer com que seus funcionários remotos usem os aplicativos de produtividade do Microsoft 365, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="beee2-160">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
