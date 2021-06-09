---
title: Verificar se os dispositivos estão configurados corretamente
description: Configure corretamente dispositivos para aumentar a resiliência geral contra ameaças e aprimorar sua capacidade de detectar e responder a ataques.
keywords: onboard, gerenciamento do Intune, Microsoft Defender para Ponto de Extremidade, Microsoft Defender, Windows Defender, redução de superfície de ataque, ASR, linha de base de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840893"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="61b4c-104">Verificar se os dispositivos estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="61b4c-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61b4c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="61b4c-105">**Applies to:**</span></span>
- [<span data-ttu-id="61b4c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="61b4c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61b4c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61b4c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="61b4c-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="61b4c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61b4c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="61b4c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="61b4c-110">Com dispositivos configurados corretamente, você pode aumentar a resiliência geral contra ameaças e aprimorar sua capacidade de detectar e responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="61b4c-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="61b4c-111">O gerenciamento de configuração de segurança ajuda a garantir que seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="61b4c-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="61b4c-112">Integração ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="61b4c-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="61b4c-113">Atender ou exceder a configuração de linha de base de segurança do Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61b4c-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="61b4c-114">Ter mitigações de superfície de ataque estratégicas no local</span><span class="sxs-lookup"><span data-stu-id="61b4c-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="61b4c-115">Clique **em Gerenciamento de configuração** no menu de navegação para abrir a página Gerenciamento de configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="61b4c-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="61b4c-116">![Página de gerenciamento de configuração de segurança](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="61b4c-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="61b4c-117">*Página de gerenciamento de configuração de dispositivo*</span><span class="sxs-lookup"><span data-stu-id="61b4c-117">*Device configuration management page*</span></span>

<span data-ttu-id="61b4c-118">Você pode rastrear o status de configuração em um nível organizacional e tomar medidas rapidamente em resposta à cobertura de integração ruim, problemas de conformidade e mitigações de superfície de ataque mal otimizadas por meio de links diretos e profundos para páginas de gerenciamento de dispositivos no centro de segurança Microsoft Intune e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61b4c-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="61b4c-119">Ao fazer isso, você se beneficia de:</span><span class="sxs-lookup"><span data-stu-id="61b4c-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="61b4c-120">Visibilidade abrangente dos eventos em seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="61b4c-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="61b4c-121">Inteligência de ameaças robusta e tecnologias avançadas de aprendizado de dispositivo para processar eventos brutos e identificar a atividade de violação e os indicadores de ameaça</span><span class="sxs-lookup"><span data-stu-id="61b4c-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="61b4c-122">Uma pilha completa de recursos de segurança configurados para interromper eficientemente a instalação de implantes mal-intencionados, o seqüestro de arquivos e processos do sistema, a exfiltração de dados e outras atividades de ameaças</span><span class="sxs-lookup"><span data-stu-id="61b4c-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="61b4c-123">Mitigações otimizadas da superfície de ataque, maximizando as defesas estratégicas contra a atividade de ameaças, minimizando o impacto na produtividade</span><span class="sxs-lookup"><span data-stu-id="61b4c-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="61b4c-124">Registrar dispositivos no gerenciamento do Intune</span><span class="sxs-lookup"><span data-stu-id="61b4c-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="61b4c-125">O gerenciamento de configuração de dispositivo funciona de perto com o gerenciamento de dispositivos do Intune para estabelecer o inventário dos dispositivos em sua organização e a configuração de segurança da linha de base.</span><span class="sxs-lookup"><span data-stu-id="61b4c-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="61b4c-126">Você poderá rastrear e gerenciar problemas de configuração em dispositivos Windows 10 intune.</span><span class="sxs-lookup"><span data-stu-id="61b4c-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="61b4c-127">Antes de garantir que seus dispositivos estão configurados corretamente, inscreva-os no gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="61b4c-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="61b4c-128">O registro do Intune é robusto e tem várias opções de registro para Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="61b4c-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="61b4c-129">Para obter mais informações sobre as opções de registro do Intune, leia sobre como configurar o registro [para Windows dispositivos](/intune/windows-enroll).</span><span class="sxs-lookup"><span data-stu-id="61b4c-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="61b4c-130">Para registrar Windows dispositivos no Intune, os administradores já devem ter sido atribuídos licenças.</span><span class="sxs-lookup"><span data-stu-id="61b4c-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="61b4c-131">[Leia sobre a atribuição de licenças para registro de dispositivo.](/intune/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="61b4c-131">[Read about assigning licenses for device enrollment](/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="61b4c-132">Para otimizar o gerenciamento de dispositivos por meio do Intune, [conecte o Intune ao Defender para Ponto de Extremidade.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="61b4c-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="61b4c-133">Obter permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="61b4c-133">Obtain required permissions</span></span>
<span data-ttu-id="61b4c-134">Por padrão, somente os usuários que foram atribuídos à função Administrador Global ou Administrador de Serviço do Intune no Azure AD podem gerenciar e atribuir os perfis de configuração de dispositivo necessários para a integração de dispositivos e a implantação da linha de base de segurança.</span><span class="sxs-lookup"><span data-stu-id="61b4c-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="61b4c-135">Se você tiver sido atribuído a outras funções, certifique-se de ter as permissões necessárias:</span><span class="sxs-lookup"><span data-stu-id="61b4c-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="61b4c-136">Permissões completas para configurações de dispositivo</span><span class="sxs-lookup"><span data-stu-id="61b4c-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="61b4c-137">Permissões completas para linhas de base de segurança</span><span class="sxs-lookup"><span data-stu-id="61b4c-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="61b4c-138">Ler permissões para políticas de conformidade de dispositivos</span><span class="sxs-lookup"><span data-stu-id="61b4c-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="61b4c-139">Permissões de leitura para a organização</span><span class="sxs-lookup"><span data-stu-id="61b4c-139">Read permissions to the organization</span></span>

<span data-ttu-id="61b4c-140">![Permissões necessárias no intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="61b4c-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="61b4c-141">*Permissões de configuração de dispositivo no Intune*</span><span class="sxs-lookup"><span data-stu-id="61b4c-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="61b4c-142">Para saber mais sobre a atribuição de permissões no Intune, [leia sobre a criação de funções personalizadas.](/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="61b4c-142">To learn more about assigning permissions on Intune, [read about creating custom roles](/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="61b4c-143">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="61b4c-143">In this section</span></span>
<span data-ttu-id="61b4c-144">Tópico</span><span class="sxs-lookup"><span data-stu-id="61b4c-144">Topic</span></span> | <span data-ttu-id="61b4c-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="61b4c-145">Description</span></span>
:---|:---
[<span data-ttu-id="61b4c-146">Obter dispositivos conectados ao Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="61b4c-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="61b4c-147">Acompanhe o status de integração de dispositivos gerenciados pelo Intune e aborde mais dispositivos por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="61b4c-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="61b4c-148">Aumentar a conformidade com a linha de base de segurança do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="61b4c-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="61b4c-149">Acompanhe a conformidade e o descumprimento da linha de base.</span><span class="sxs-lookup"><span data-stu-id="61b4c-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="61b4c-150">Implante a linha de base de segurança em mais dispositivos gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="61b4c-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="61b4c-151">Otimizar a implantação e as detecções de regras ASR</span><span class="sxs-lookup"><span data-stu-id="61b4c-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="61b4c-152">Revise a implantação de regras e ajuste as detecções usando ferramentas de análise de impacto Microsoft 365 centro de segurança.</span><span class="sxs-lookup"><span data-stu-id="61b4c-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="61b4c-153">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="61b4c-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61b4c-154">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="61b4c-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
