---
title: 'Fase 3: critérios de saída da infraestrutura do Windows 10 Enterprise'
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para o Windows 10 Enterprise.
ms.openlocfilehash: d51392572c78edb1a21f5edc3229057b9af3f514
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801216"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="4e4d4-103">Fase 3: critérios de saída da infraestrutura do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4e4d4-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="4e4d4-105">Verifique se a infraestrutura do Windows 10 Enterprise atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="4e4d4-106">Obrigatório: seus domínios do Microsoft 365 são adicionados e verificados</span><span class="sxs-lookup"><span data-stu-id="4e4d4-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="4e4d4-107">O locatário do Azure AD para o Office 365 e suas assinaturas do Intune são configurados com os nomes de domínio da Internet (como contoso.com), em vez de apenas um nome de domínio que inclui "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="4e4d4-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="4e4d4-p101">Se não fizer isso, você sofrerá limitações nos métodos de autenticação que podem ser configurados. Por exemplo, a senha e a autenticação federada não podem usar o nome de domínio "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="4e4d4-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="4e4d4-110">Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="4e4d4-111">Opcional: os usuários são adicionados e licenciados</span><span class="sxs-lookup"><span data-stu-id="4e4d4-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="4e4d4-112">As contas que correspondem aos usuários são adicionadas, diretamente ao locatário do Azure AD para as assinaturas do Office 365 e do Intune ou na sincronização do diretório dos Serviços de Domínio do Active Directory (AD DS) local.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="4e4d4-113">Depois de adicionar os usuários, atribua licenças do Microsoft 365 Enterprise a eles, diretamente como um administrador de usuários ou global ou automaticamente usando uma associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="4e4d4-114">Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="4e4d4-115">Opcional: os diagnósticos são habilitados</span><span class="sxs-lookup"><span data-stu-id="4e4d4-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="4e4d4-116">Você habilitou as configurações de dados de diagnóstico usando a Política de Grupo, o Microsoft Intune, o Editor do Registro ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="4e4d4-117">Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="4e4d4-118">Obrigatório para atualização in-loco: criou uma sequência de tarefas do Gerenciador de Configurações para a implantação de um sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4e4d4-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="4e4d4-119">Para iniciar uma sequência de tarefas do Gerenciador de Configurações para realizar uma atualização in-loco em um dispositivo que executa o Windows 7 ou o Windows 8.1, você deve:</span><span class="sxs-lookup"><span data-stu-id="4e4d4-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="4e4d4-120">Definir níveis de dados adequados de diagnóstico do Windows</span><span class="sxs-lookup"><span data-stu-id="4e4d4-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="4e4d4-121">Verificar a preparação para atualização do Windows</span><span class="sxs-lookup"><span data-stu-id="4e4d4-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="4e4d4-122">Criar uma sequência de tarefas do Gerenciador de Configurações que inclua uma coleção de dispositivos e a implantação de um sistema operacional com uma imagem do sistema operacional do Windows 10</span><span class="sxs-lookup"><span data-stu-id="4e4d4-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="4e4d4-p102">Após a implantação, realize atualizações in-loco nos dispositivos que estiverem preparados para a atualização para o Windows. Para obter o máximo proveito do Microsoft 365 Enterprise, atualize o maior número possível de dispositivos que executam o Windows 7 e o Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="4e4d4-p103">Todos dispositivos que executam o Windows 10 Enterprise podem aproveitar as vantagens da solução integrada do Microsoft 365 Enterprise. Os demais dispositivos, que executam o Windows 7 ou o Windows 8.1, não podem usar tecnologias conectadas na nuvem e os recursos de segurança avançados do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="4e4d4-127">Se necessário, a [Etapa 2](windows10-deploy-inplaceupgrade.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="4e4d4-128">Obrigatório para novos dispositivos: Windows Autopilot configurado</span><span class="sxs-lookup"><span data-stu-id="4e4d4-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="4e4d4-129">Para usar o Windows Autopilot para implantar e personalizar o Windows 10 Enterprise um novo dispositivo, você deve:</span><span class="sxs-lookup"><span data-stu-id="4e4d4-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="4e4d4-130">Definir os níveis adequados de dados de diagnóstico do Windows</span><span class="sxs-lookup"><span data-stu-id="4e4d4-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="4e4d4-131">Definir os pré-requisitos para o Windows Autopilot, que incluem:</span><span class="sxs-lookup"><span data-stu-id="4e4d4-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="4e4d4-132">Registro do dispositivo e personalização da OOBE</span><span class="sxs-lookup"><span data-stu-id="4e4d4-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="4e4d4-133">Identidade visual da empresa para OOBE</span><span class="sxs-lookup"><span data-stu-id="4e4d4-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="4e4d4-134">Registro automático do MDM do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4e4d4-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="4e4d4-135">Conectividade de rede para os serviços de nuvem usados pelo Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="4e4d4-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="4e4d4-136">Dispositivos que estão pré-instalados no Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="4e4d4-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="4e4d4-137">Selecionado o Windows Autopilot Deployment Program para sua organização</span><span class="sxs-lookup"><span data-stu-id="4e4d4-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="4e4d4-138">Depois de concluir a configuração do Windows Autopilot, você pode usá-lo para configurar e personalizar o Windows 10 Enterprise com a OOBE ( Configuração Inicial pelo Usuário) para:</span><span class="sxs-lookup"><span data-stu-id="4e4d4-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="4e4d4-139">Novos dispositivos</span><span class="sxs-lookup"><span data-stu-id="4e4d4-139">New devices</span></span>
- <span data-ttu-id="4e4d4-140">Dispositivos que já concluíram uma configuração pronta na organização.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="4e4d4-141">O Windows Autopilot configura o dispositivo e o conecta ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="4e4d4-142">Caso não tenha o Windows Autopilot, configure manualmente os novos dispositivos, incluindo a conexão com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="4e4d4-143">Se necessário, a [Etapa 3](windows10-deploy-autopilot.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="4e4d4-144">Opcional: você está usando a Integridade do Dispositivo do Windows Analytics para monitorar seus dispositivos baseados no Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4e4d4-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="4e4d4-p104">Você usou as informações em Monitorar a integridade de dispositivos com a Integridade do Dispositivo para detectar e corrigir problemas que afetam os usuários finais. Ao tratar rapidamente dos problemas do usuário final, é possível reduzir os custos de suporte e demonstrar aos usuários o compromisso da TI com o Windows 10 Enterprise. Isso pode ajudar a promover a adoção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="4e4d4-147">Se necessário, a [Etapa 4](windows10-enable-windows-analytics.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="4e4d4-148">Obrigatório: você está usando o Windows Defender Antivirus ou uma solução antimalware</span><span class="sxs-lookup"><span data-stu-id="4e4d4-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="4e4d4-p105">Você implantou o Windows Defender Antivirus ou sua própria solução antivírus para proteger seus dispositivos que executam o Windows 10 Enterprise contra softwares mal-intencionados. Se tiver implantado o Windows Defender Antivirus, você implementou um método de relatório, como o Microsoft Endpoint Configuration Manager ou o Microsoft Intune, para monitorar eventos e atividades de antivírus.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="4e4d4-151">Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-av) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="4e4d4-152">Obrigatório: você está usando o Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="4e4d4-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="4e4d4-153">Você implantou o Windows Defender Exploit Guard para proteger seus dispositivos que executam o Windows 10 Enterprise contra invasões e implementou um método de relatório, como o Configuration Manager ou o Microsoft Intune, para monitorar eventos e atividades de invasão.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="4e4d4-154">Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-eg) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="4e4d4-155">Obrigatório: você está usando a Proteção Avançada Contra Ameaças do Microsoft Defender (Microsoft 365 Enterprise E5 apenas)</span><span class="sxs-lookup"><span data-stu-id="4e4d4-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="4e4d4-156">Você implantou a Proteção Avançada contra Ameaças do Microsoft Defender (ATP) para detectar, investigar e responder a ameaças avançadas contra sua rede e dispositivos que executam o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="4e4d4-157">Como opção, você integrou o Microsoft Defender ATP com outras ferramentas para expandir seus recursos.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="4e4d4-158">Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-atp) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="4e4d4-159">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4e4d4-159">Results and next steps</span></span>

<span data-ttu-id="4e4d4-160">Sua infraestrutura do Windows 10 Enterprise está pronta para ser instalada em novos dispositivos e atualizações em vigor em dispositivos executando versões anteriores do Windows, e você está usando os principais recursos de segurança do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4e4d4-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="4e4d4-162">Se você está seguindo as fases para a implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase é [Office 365 ProPlus](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="4e4d4-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
