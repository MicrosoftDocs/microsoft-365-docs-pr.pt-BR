---
title: Infraestrutura do Windows 10 Enterprise para o Microsoft 365 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas de que você precisa para implantar o Windows 10 Enterprise em PCs como parte do Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, Windows 10 Enterprise, implantação
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 3cdb5fd6644d76a843e109ff53f73eb9ec4638f8
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627535"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="533f5-104">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="533f5-104">Phase 3: Windows 10 Enterprise</span></span>

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="533f5-106">O Microsoft 365 Enterprise inclui o Windows 10 Enterprise, que oferece as ferramentas para fazer mais e permanecer protegido.</span><span class="sxs-lookup"><span data-stu-id="533f5-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="533f5-107">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="533f5-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="533f5-108">O **é integrado para simplificar** a sua capacidade de aproveitar a nuvem para ajudar a reduzir a complexidade do gerenciamento do atual ambiente de dispositivos de ti modernos, não importa o tamanho.</span><span class="sxs-lookup"><span data-stu-id="533f5-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="533f5-109">A **segurança inteligente** é a versão mais segura do Windows, com recursos de segurança inteligente projetados para trabalhar juntos para proteger melhor sua organização.</span><span class="sxs-lookup"><span data-stu-id="533f5-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="533f5-110">**Permite a criatividade e o trabalho em equipe** – desbloqueia a criatividade e o trabalho em equipe para fornecer a experiência mais produtiva que os usuários e vão adorar.</span><span class="sxs-lookup"><span data-stu-id="533f5-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="533f5-111">Você precisará entender as diferentes maneiras de implantar o sistema operacional Windows 10 e escolher o correto para sua organização.</span><span class="sxs-lookup"><span data-stu-id="533f5-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="533f5-112">Dependendo da sua assinatura do Microsoft 365 Enterprise, há também os serviços do Windows 10 e os recursos de segurança que você precisará configurar para aproveitar ao máximo o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="533f5-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="533f5-113">Para implantar o Windows 10 Enterprise e o Office 365 ProPlus em conjunto e mudar para um [computador moderno](https://www.microsoft.com/microsoft-365/modern-desktop), confira o [Centro de Implantação de Computador Moderno](https://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="533f5-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="533f5-114">Implantação do Windows 10</span><span class="sxs-lookup"><span data-stu-id="533f5-114">Windows 10 deployment</span></span>

<span data-ttu-id="533f5-115">Há várias maneiras de implantar o Windows 10 Enterprise para sua organização.</span><span class="sxs-lookup"><span data-stu-id="533f5-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="533f5-116">Aqui, vamos nos concentrar em como você pode configurar e implantar uma imagem do Windows 10 Enterprise por meio desses cenários de implantação modernos.</span><span class="sxs-lookup"><span data-stu-id="533f5-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="533f5-117">Cenário da implantação</span><span class="sxs-lookup"><span data-stu-id="533f5-117">Deployment scenario</span></span> | <span data-ttu-id="533f5-118">Quando usá-la</span><span class="sxs-lookup"><span data-stu-id="533f5-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="533f5-119">Usando o Microsoft Endpoint Configuration Manager como uma atualização in-loco</span><span class="sxs-lookup"><span data-stu-id="533f5-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="533f5-120">Selecione esta opção se você precisar atualizar computadores com Windows 7 ou Windows 8,1 para a <a href="https://aka.ms/windows-10-release-information" target="_blank">versão atual</a> do Windows 10 Enterprise e seus computadores estiverem atualmente gerenciados com o <a href="https://aka.ms/introtosccm" target="_blank">Gerenciador de configurações (ramificação atual)</a>.</span><span class="sxs-lookup"><span data-stu-id="533f5-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="533f5-121">Usando o Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="533f5-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="533f5-122">Selecione essa opção se estiver configurando novos computadores Windows que tenham o Windows 10 Enterprise, versão 1703 ou posterior pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="533f5-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="533f5-123">Os usuários finais iniciarão a instalação usando a configuração desejada inserindo suas credenciais de conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="533f5-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="533f5-124">Se esses cenários de implantação não atenderem às necessidades da sua organização, você poderá aprender sobre outros cenários e entender os recursos e as limitações de cada um nos [cenários de implantação do Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="533f5-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="533f5-125">Você também pode <a href="https://aka.ms/planforwin10deployment" target="_blank">planejar a implantação do Windows 10</a> por conta própria.</span><span class="sxs-lookup"><span data-stu-id="533f5-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="533f5-126">Você pode saber mais sobre o Windows 10 com estes artigos:</span><span class="sxs-lookup"><span data-stu-id="533f5-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="533f5-127">Página do produto do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="533f5-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="533f5-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="533f5-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="533f5-129">Implantar e atualizar o Windows 10</span><span class="sxs-lookup"><span data-stu-id="533f5-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="533f5-130">Serviços e recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="533f5-130">Additional services and features</span></span>
<span data-ttu-id="533f5-131">Como parte de sua implantação do Windows 10 Enterprise, você pode adicionar esses serviços e recursos adicionais.</span><span class="sxs-lookup"><span data-stu-id="533f5-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="533f5-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="533f5-132">Windows Analytics</span></span>

<span data-ttu-id="533f5-133">O Windows usa dados de diagnóstico para fornecer informações ricas e acionáveis para ajudá-lo a obter ideias profundas sobre a eficiência operacional e a integridade de dispositivos Windows 10 em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="533f5-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="533f5-134">Preparação para atualização-preparação para atualização ajudará você a migrar para o Windows 10 e ficar atualizado com as novas atualizações de recursos do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="533f5-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="533f5-135">Update Compliance-Update conformidade é direcionado para o administrador de ti que deseja obter uma visão holística de todos os seus dispositivos Windows 10, sem requisitos de infraestrutura adicionais.</span><span class="sxs-lookup"><span data-stu-id="533f5-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="533f5-136">Integridade do dispositivo-você pode usar a integridade do dispositivo para detectar e corrigir problemas de impacto do usuário final de forma proativa.</span><span class="sxs-lookup"><span data-stu-id="533f5-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="533f5-137">Consulte [visão geral do Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="533f5-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="533f5-138">Segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="533f5-138">Windows security</span></span>

<span data-ttu-id="533f5-139">O Windows 10 fornece recursos para ajudar a proteger contra ameaças, ajudá-lo a proteger seus dispositivos e a ajudar no controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="533f5-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="533f5-140">Com o Windows 10, você obtém recursos de segurança críticos que protegem o seu dispositivo diretamente do início.</span><span class="sxs-lookup"><span data-stu-id="533f5-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="533f5-141">O Microsoft 365 E3 adiciona recursos de segurança como o Windows Hello para empresas, controle de aplicativos do Windows Defender e proteção de informações do Windows.</span><span class="sxs-lookup"><span data-stu-id="533f5-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="533f5-142">Com o Microsoft 365 e5, você obtém toda a proteção do Microsoft 365 E3 Security Plus e dos recursos de segurança baseados em nuvem e proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="533f5-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="533f5-143">Para saber mais sobre os recursos de segurança obtidos com o Windows 10 Enterprise e obter orientação sobre como implantar, gerenciar, configurar e solucionar problemas de três recursos de ecurity principais, consulte [etapa 5: implantar recursos de segurança do Windows 10 Enterprise](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="533f5-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="533f5-144">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="533f5-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="533f5-145">Inspecione dentro da Microsoft e saiba como a empresa [implantou o Windows 10 Enterprise e está usando autenticação forte, Intune e Microsoft defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="533f5-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="533f5-146">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="533f5-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="533f5-147">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou o Windows 10 Enterprise](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="533f5-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![A Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="533f5-149">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="533f5-149">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="533f5-151">Preparar sua organização para o Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="533f5-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
