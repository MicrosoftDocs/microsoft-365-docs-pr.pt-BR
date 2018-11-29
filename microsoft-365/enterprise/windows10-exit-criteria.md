---
title: 'Fase 3: critérios de saída da infraestrutura do Windows 10 Enterprise'
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 06/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para o Windows 10 Enterprise.
ms.openlocfilehash: 7ac79fec93e4b4aae0b075891917e2f88432b80f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865068"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="128c6-103">Fase 3: critérios de saída da infraestrutura do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="128c6-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="128c6-104">Se a sua infraestrutura do Windows 10 Enterprise atender às condições a seguir, você estará pronto para passar para a Fase 4.</span><span class="sxs-lookup"><span data-stu-id="128c6-104">If your Windows 10 Enterprise infrastructure meets the following conditions, you’re ready to move to Phase 4.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="128c6-105">Obrigatório: seus domínios do Microsoft 365 são adicionados e verificados</span><span class="sxs-lookup"><span data-stu-id="128c6-105">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="128c6-106">O locatário do Azure AD para o Office 365 e suas assinaturas do Intune são configurados com os nomes de domínio da Internet (como contoso.com), em vez de apenas um nome de domínio que inclui "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="128c6-106">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="128c6-p101">Se não fizer isso, você sofrerá limitações nos métodos de autenticação que podem ser configurados. Por exemplo, a senha e a autenticação federada não podem usar o nome de domínio "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="128c6-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="128c6-109">Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="128c6-109">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="128c6-110">Opcional: os usuários são adicionados e licenciados</span><span class="sxs-lookup"><span data-stu-id="128c6-110">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="128c6-111">As contas que correspondem aos usuários são adicionadas, diretamente ao locatário do Azure AD para as assinaturas do Office 365 e do Intune ou na sincronização de diretório do Windows Server AD local.</span><span class="sxs-lookup"><span data-stu-id="128c6-111">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Windows Server AD.</span></span>

<span data-ttu-id="128c6-112">Depois de adicionar os usuários, atribua licenças do Microsoft 365 Enterprise a eles, diretamente como um administrador de usuários ou global ou automaticamente usando uma associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="128c6-112">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="128c6-113">Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="128c6-113">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="128c6-114">Opcional: os diagnósticos são habilitados</span><span class="sxs-lookup"><span data-stu-id="128c6-114">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="128c6-115">Você habilitou as configurações de dados de diagnóstico usando a Política de Grupo, o Microsoft Intune, o Editor do Registro ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="128c6-115">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="128c6-116">Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="128c6-116">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="128c6-117">Obrigatório para atualização in-loco: criou uma sequência de tarefas do Gerenciador de Configurações para a implantação de um sistema operacional</span><span class="sxs-lookup"><span data-stu-id="128c6-117">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="128c6-118">Para iniciar uma sequência de tarefas do Gerenciador de Configurações para realizar uma atualização in-loco em um dispositivo que executa o Windows 7 ou o Windows 8.1, você deve:</span><span class="sxs-lookup"><span data-stu-id="128c6-118">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="128c6-119">Definir níveis de dados adequados de diagnóstico do Windows</span><span class="sxs-lookup"><span data-stu-id="128c6-119">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="128c6-120">Verificar a preparação para atualização do Windows</span><span class="sxs-lookup"><span data-stu-id="128c6-120">Verify the readiness to upgrade Windows</span></span>
- <span data-ttu-id="128c6-121">Criar uma sequência de tarefas do Gerenciador de Configurações que inclua uma coleção de dispositivos e a implantação de um sistema operacional com uma imagem do sistema operacional do Windows 10</span><span class="sxs-lookup"><span data-stu-id="128c6-121">Create a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="128c6-p102">Após a implantação, realize atualizações in-loco nos dispositivos que estiverem preparados para a atualização para o Windows. Para obter o máximo proveito do Microsoft 365 Enterprise, atualize o maior número possível de dispositivos que executam o Windows 7 e o Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="128c6-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="128c6-p103">Todos dispositivos que executam o Windows 10 Enterprise podem aproveitar as vantagens da solução integrada do Microsoft 365 Enterprise. Os demais dispositivos, que executam o Windows 7 ou o Windows 8.1, não podem usar tecnologias conectadas na nuvem e os recursos de segurança avançados do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="128c6-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="128c6-126">Se necessário, a [Etapa 2](windows10-deploy-inplaceupgrade.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="128c6-126">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="128c6-127">Obrigatório para novos dispositivos: Windows Autopilot configurado</span><span class="sxs-lookup"><span data-stu-id="128c6-127">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="128c6-128">Para usar o Windows Autopilot para implantar e personalizar o Windows 10 Enterprise um novo dispositivo, você deve:</span><span class="sxs-lookup"><span data-stu-id="128c6-128">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="128c6-129">Definir níveis de dados adequados de diagnóstico do Windows</span><span class="sxs-lookup"><span data-stu-id="128c6-129">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="128c6-130">Ter concluído os pré-requisitos para o Windows Autopilot, que incluem:</span><span class="sxs-lookup"><span data-stu-id="128c6-130">Completed the prerequisites for Windows Autopilot, which include:</span></span>
- <span data-ttu-id="128c6-131">Registro do dispositivo e personalização da OOBE</span><span class="sxs-lookup"><span data-stu-id="128c6-131">Device registration and OOBE customization</span></span>
- <span data-ttu-id="128c6-132">Identidade visual da empresa para OOBE</span><span class="sxs-lookup"><span data-stu-id="128c6-132">Company branding for OOBE</span></span>
- <span data-ttu-id="128c6-133">Registro automático do MDM do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="128c6-133">MDM auto-enrollment in Microsoft Intune</span></span>
- <span data-ttu-id="128c6-134">Conectividade de rede para os serviços de nuvem usados pelo Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="128c6-134">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="128c6-135">Os dispositivos devem estar pré-instalados no Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="128c6-135">Devices must be pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="128c6-136">Selecionado o Windows Autopilot Deployment Program para sua organização</span><span class="sxs-lookup"><span data-stu-id="128c6-136">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="128c6-137">Depois de concluir a configuração do Windows Autopilot, você pode usá-lo para configurar e personalizar o Windows 10 Enterprise com a OOBE ( Configuração Inicial pelo Usuário) para:</span><span class="sxs-lookup"><span data-stu-id="128c6-137">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="128c6-138">Novos dispositivos</span><span class="sxs-lookup"><span data-stu-id="128c6-138">New devices</span></span>
- <span data-ttu-id="128c6-139">Dispositivos que já concluíram uma configuração pronta na organização.</span><span class="sxs-lookup"><span data-stu-id="128c6-139">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="128c6-140">O Windows Autopilot configura o dispositivo e o conecta ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="128c6-140">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="128c6-141">Caso não tenha o Windows Autopilot, configure manualmente os novos dispositivos, incluindo a conexão com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="128c6-141">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="128c6-142">Se necessário, a [Etapa 3](windows10-deploy-autopilot.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="128c6-142">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="128c6-143">Opcional: você está usando a Integridade do Dispositivo do Windows Analytics para monitorar seus dispositivos baseados no Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="128c6-143">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="128c6-p104">Você usou as informações em Monitorar a integridade de dispositivos com a Integridade do Dispositivo para detectar e corrigir problemas que afetam os usuários finais. Ao tratar rapidamente dos problemas do usuário final, é possível reduzir os custos de suporte e demonstrar aos usuários o compromisso da TI com o Windows 10 Enterprise. Isso pode ajudar a promover a adoção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="128c6-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="128c6-146">Se necessário, a [Etapa 4](windows10-enable-windows-analytics.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="128c6-146">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="128c6-147">Obrigatório: você está usando o Windows Defender Antivirus ou uma solução antimalware</span><span class="sxs-lookup"><span data-stu-id="128c6-147">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="128c6-p105">Você implantou o Windows Defender Antivirus ou sua própria solução antivírus para proteger seus dispositivos que executam o Windows 10 Enterprise contra softwares mal-intencionados. Se tiver implantado o Windows Defender Antivirus, você implementou um método de relatório, como o System Center Configuration Manager ou o Microsoft Intune, para monitorar eventos e atividades de antivírus.</span><span class="sxs-lookup"><span data-stu-id="128c6-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="128c6-150">Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-av) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="128c6-150">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="128c6-151">Obrigatório: você está usando o Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="128c6-151">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="128c6-152">Você implantou o Windows Defender Exploit Guard para proteger seus dispositivos que executam o Windows 10 Enterprise contra invasões e implementou um método de relatório, como o System Center Configuration Manager ou o Microsoft Intune, para monitorar eventos e atividades de invasão.</span><span class="sxs-lookup"><span data-stu-id="128c6-152">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="128c6-153">Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-eg) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="128c6-153">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="128c6-154">Obrigatório: você está usando a Proteção Avançada Contra Ameaças do Windows Defender (Microsoft 365 Enterprise E5 apenas)</span><span class="sxs-lookup"><span data-stu-id="128c6-154">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="128c6-155">Você implantou a Proteção Avançada contra Ameaças do Windows Defender (ATP) para detectar, investigar e responder a ameaças avançadas contra sua rede e dispositivos que executam o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="128c6-155">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="128c6-156">Como opção, você integrou o Windows Defender ATP com outras ferramentas para expandir seus recursos.</span><span class="sxs-lookup"><span data-stu-id="128c6-156">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="128c6-157">Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-atp) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="128c6-157">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>


## <a name="next-phase"></a><span data-ttu-id="128c6-158">Próxima fase</span><span class="sxs-lookup"><span data-stu-id="128c6-158">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="128c6-159">Sua próxima fase do processo de implantação de ponta a ponta para o Microsoft 365 Enterprise é o [Office 365 ProPlus](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="128c6-159">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
