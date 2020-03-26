---
title: Capacitar funcionários remotos
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Configure a infraestrutura e os recursos de segurança que permitem que seus funcionários trabalhem remotamente em qualquer lugar e a qualquer momento.
ms.openlocfilehash: cfbabfbe0c239ca837356b585171778d40daaa93
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42952049"
---
# <a name="empower-remote-workers"></a><span data-ttu-id="708c6-103">Capacitar funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="708c6-103">Empower remote workers</span></span>

<span data-ttu-id="708c6-104">*Este cenário aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="708c6-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="708c6-105">Permitir aos funcionários trabalhar fora do escritório sem problemas e com segurança é algo muito importante para várias organizações, pois permite economizar espaço, contratar e manter funcionários que não desejem ser realocados e reduzir a deslocação dos funcionários, deixando-os mais produtivos e permitindo que eles realizem atividades de redução de estresse fora do trabalho.</span><span class="sxs-lookup"><span data-stu-id="708c6-105">Allowing employees to work away from the office seamlessly and securely is important for many organizations to save on office space, hire and retain employees who are unwilling to relocate, and reduce employee commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="708c6-106">O trabalho remoto, também conhecido como teletrabalho, pode abranger um espectro que inclui:</span><span class="sxs-lookup"><span data-stu-id="708c6-106">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="708c6-107">Funcionários que estão ocasionalmente fora do escritório para conferências ou reuniões com clientes.</span><span class="sxs-lookup"><span data-stu-id="708c6-107">Employees that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="708c6-108">Alguns funcionários que trabalham remotamente em tempo integral.</span><span class="sxs-lookup"><span data-stu-id="708c6-108">Some employees that work remotely full-time.</span></span>
- <span data-ttu-id="708c6-109">Uma organização totalmente remota na qual não há nenhum escritório e todos os funcionários são remotos.</span><span class="sxs-lookup"><span data-stu-id="708c6-109">A fully remote organization in which there is no office and all employees are remote.</span></span>

<span data-ttu-id="708c6-110">Para dar suporte a funcionários remotos, uma combinação de recursos no Microsoft 365 Enterprise permite aos funcionários remotos colaborar de forma ativa, como por exemplo:</span><span class="sxs-lookup"><span data-stu-id="708c6-110">To support remote workers, a combination of features in Microsoft 365 Enterprise enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="708c6-111">Reuniões online e sessões de chat.</span><span class="sxs-lookup"><span data-stu-id="708c6-111">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="708c6-112">Espaços de trabalho compartilhados para armazenamento de arquivos na nuvem com acessibilidade global e colaboração em tempo real.</span><span class="sxs-lookup"><span data-stu-id="708c6-112">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="708c6-113">Tarefas e fluxos de trabalho compartilhados para dividir o trabalho e realizar as tarefas.</span><span class="sxs-lookup"><span data-stu-id="708c6-113">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="708c6-114">Para segurança forte, o Microsoft 365 Enterprise inclui:</span><span class="sxs-lookup"><span data-stu-id="708c6-114">For strong security, Microsoft 365 Enterprise includes:</span></span>

- <span data-ttu-id="708c6-115">Requisitos de autenticação imposta, detecção e resposta a entradas de alto risco e bloqueio de aplicativos selecionados e dispositivos que não estejam em conformidade.</span><span class="sxs-lookup"><span data-stu-id="708c6-115">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="708c6-116">Conexões criptografadas e ativos digitais na nuvem.</span><span class="sxs-lookup"><span data-stu-id="708c6-116">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="708c6-117">Permissões para definir quem pode fazer o que com os arquivos.</span><span class="sxs-lookup"><span data-stu-id="708c6-117">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="708c6-118">Prevenção contra perda de dados (DLP) para evitar o vazamento de dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="708c6-118">Data loss prevention (DLP) to prevent leakage of highly regulated data.</span></span>

<span data-ttu-id="708c6-119">Para atender a esses critérios para funcionários remotos, use os seguintes recursos do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="708c6-119">To meet these criteria for remote workers, use the following Microsoft 365 Enterprise features:</span></span>

- <span data-ttu-id="708c6-120">Identidade do usuário e segurança de entrada</span><span class="sxs-lookup"><span data-stu-id="708c6-120">User identity and sign-in security</span></span>
  - <span data-ttu-id="708c6-121">Contas de usuário do Azure Active Directory (Azure AD) com autenticação multifator (MFA)</span><span class="sxs-lookup"><span data-stu-id="708c6-121">Azure Active Directory (Azure AD) user accounts with multi-factor authentication (MFA)</span></span>
  - <span data-ttu-id="708c6-122">Políticas de acesso condicional para exigir MFA para entradas potencialmente perigosas</span><span class="sxs-lookup"><span data-stu-id="708c6-122">Conditional Access policies to require MFA for risky sign-ins</span></span>
- <span data-ttu-id="708c6-123">Plataformas de colaboração</span><span class="sxs-lookup"><span data-stu-id="708c6-123">Collaboration platforms</span></span>
  - <span data-ttu-id="708c6-124">Microsoft Teams, SharePoint e OneDrive, com os quais funcionários remotos podem agendar e participar de reuniões online e trabalhar nos mesmos documentos ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="708c6-124">Microsoft Teams, SharePoint, and OneDrive, with which remote workers can schedule and attend online video-based meetings and work on the same documents at the same time</span></span>
- <span data-ttu-id="708c6-125">Acesso protegido aos recursos</span><span class="sxs-lookup"><span data-stu-id="708c6-125">Secure access to resources</span></span>
  - <span data-ttu-id="708c6-126">Grupos e permissões para o Teams, sites do SharePoint e o OneDrive, para que somente usuários autenticados e permitidos tenham acesso</span><span class="sxs-lookup"><span data-stu-id="708c6-126">Groups and permissions for Teams, SharePoint sites, and OneDrive so that only authenticated and permitted users have access</span></span>
- <span data-ttu-id="708c6-127">Proteção contra divulgação não autorizada de arquivos</span><span class="sxs-lookup"><span data-stu-id="708c6-127">Protection for leaked files</span></span>
  - <span data-ttu-id="708c6-128">Políticas DLP do Office 365</span><span class="sxs-lookup"><span data-stu-id="708c6-128">Office 365 DLP policies</span></span>
  - <span data-ttu-id="708c6-129">Rótulos de sensibilidade para criptografia e permissões que viajam com arquivos</span><span class="sxs-lookup"><span data-stu-id="708c6-129">Sensitivity labels for encryption and permissions that travel with files</span></span>
- <span data-ttu-id="708c6-130">Gerenciamento e segurança de dispositivos com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="708c6-130">Device management and security with Microsoft Intune</span></span>
  - <span data-ttu-id="708c6-131">Registro de dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="708c6-131">Enrollment for managed devices</span></span>
  - <span data-ttu-id="708c6-132">Configurações de aplicativo para dispositivos pessoais</span><span class="sxs-lookup"><span data-stu-id="708c6-132">App settings for personal devices</span></span>
  - <span data-ttu-id="708c6-133">Políticas de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="708c6-133">Device and app policies</span></span>
- <span data-ttu-id="708c6-134">Aplicativos de produtividade para dispositivos</span><span class="sxs-lookup"><span data-stu-id="708c6-134">Productivity apps for devices</span></span>
  - <span data-ttu-id="708c6-135">Aplicativos do Office 365 ProPlus para experiências colaborativas com o Teams, o SharePoint e o OneDrive</span><span class="sxs-lookup"><span data-stu-id="708c6-135">Office 365 ProPlus apps for collaborative experiences with Teams, SharePoint, and OneDrive</span></span> 
- <span data-ttu-id="708c6-136">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="708c6-136">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="708c6-137">Recursos de segurança abrangentes para proteção contra ataques cibernéticos e prevenção de vazamento de dados</span><span class="sxs-lookup"><span data-stu-id="708c6-137">Comprehensive security features to protect against cyberattacks and prevent data leakage</span></span>
- <span data-ttu-id="708c6-138">Acesso a aplicativos locais</span><span class="sxs-lookup"><span data-stu-id="708c6-138">Access to on-premises apps</span></span>
  - <span data-ttu-id="708c6-139">Organizações que tenham identidade híbrida podem usar o Proxy de Aplicativo do Azure AD em vez de conexões VPN (rede virtual privada)</span><span class="sxs-lookup"><span data-stu-id="708c6-139">Organizations that have hybrid identity can use Azure AD Application Proxy instead of virtual private network (VPN) connections</span></span>

<span data-ttu-id="708c6-140">As fases a seguir o ajudarão a implantar o recurso do Microsoft 365 Enterprise para permitir o acesso remoto e impulsionar a adoção de funcionários remotos.</span><span class="sxs-lookup"><span data-stu-id="708c6-140">The following phases step you through deploying the feature of Microsoft 365 Enterprise for remote access and driving adoption for remote workers.</span></span> <span data-ttu-id="708c6-141">Se você já tiver implantado os elementos dessas fases, certifique-se de que eles atendam aos requisitos descritos antes de passar para o próximo elemento.</span><span class="sxs-lookup"><span data-stu-id="708c6-141">If you have already deployed elements of these phases, ensure that they meet the stated requirements before moving on to the next element.</span></span>

<a name="poster"></a><span data-ttu-id="708c6-142">Para ver um resumo de uma página desse cenário, consulte o pôster [Capacitar funcionários remotos](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).</span><span class="sxs-lookup"><span data-stu-id="708c6-142">For a 1-page summary of this scenario, see the [Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).</span></span>

<span data-ttu-id="708c6-143">[![Pôster Capacitar funcionários remotos](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span><span class="sxs-lookup"><span data-stu-id="708c6-143">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span></span>

<span data-ttu-id="708c6-144">Você também pode baixar este pôster nos formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) ou [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) e imprimir em papel carta, oficial ou tabloide (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="708c6-144">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a><span data-ttu-id="708c6-145">Fase 1: implantar os recursos e as funcionalidades do Microsoft 365 para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="708c6-145">Phase 1: Deploy Microsoft 365 features and capabilities for remote workers</span></span>

<span data-ttu-id="708c6-146">Devido a amplitude e a quantidade de recursos e capacidades necessárias para esse cenário, vamos guiá-lo pelos elementos necessários das seções de infraestrutura e cargas de trabalho do [Guia de Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="708c6-146">Because of the breadth and number of features and capabilities required for this scenario, we’ll step you through the required elements of the foundation infrastructure and workloads sections of the [Microsoft 365 Enterprise Deployment Guide](deploy-microsoft-365-enterprise.md).</span></span>

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a><span data-ttu-id="708c6-147">Etapa 1: fundamentos da infraestrutura para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="708c6-147">Step 1: Foundation infrastructure requirements for remote workers</span></span>

<span data-ttu-id="708c6-148">Nesta etapa, veremos as fases da [infraestrutura de base](deploy-foundation-infrastructure.md) e listamos os elementos necessários para habilitar funcionários remotos.</span><span class="sxs-lookup"><span data-stu-id="708c6-148">In this step, we’ll visit the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) and list the required elements to enable remote workers.</span></span>

<span data-ttu-id="708c6-149">Para a [Fase 2: identidade](identity-infrastructure.md), implante o seguinte para identidade do usuário e segurança de entrada:</span><span class="sxs-lookup"><span data-stu-id="708c6-149">For [Phase 2: Identity](identity-infrastructure.md), deploy the following for user identity and sign-in security:</span></span>

- <span data-ttu-id="708c6-150">Para identidade híbrida, contas de usuários e grupos sincronizados de Serviços de Domínio do Active Directory (AD DS) locais.</span><span class="sxs-lookup"><span data-stu-id="708c6-150">For hybrid identity, user accounts and groups synchronized from on-premises Active Directory Domain Services (AD DS).</span></span>
- <span data-ttu-id="708c6-151">Para atribuir permissões de grupos sincronizados ou do Azure AD com os membros apropriados.</span><span class="sxs-lookup"><span data-stu-id="708c6-151">For assigning permissions, synchronized or Azure AD groups with the appropriate members.</span></span>
- <span data-ttu-id="708c6-152">Configurações de autenticação, como exigir a MFA.</span><span class="sxs-lookup"><span data-stu-id="708c6-152">Authentication settings, such as requiring MFA.</span></span>
- <span data-ttu-id="708c6-153">As políticas de acesso condicional exigem a MFA para entradas potencialmente perigosas e bloqueiam clientes que não tenham suporte para autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="708c6-153">Conditional Access policies to require MFA for risky sign-ins and block clients that don’t support modern authentication.</span></span>

<span data-ttu-id="708c6-154">Esta é a configuração resultante com os elementos de identidade realçados.</span><span class="sxs-lookup"><span data-stu-id="708c6-154">Here's the resulting configuration with the identity elements highlighted.</span></span>

![Elementos de identidade para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
<span data-ttu-id="708c6-156">Para a [Fase 3: Windows 10 Enterprise](windows10-infrastructure.md), implante:</span><span class="sxs-lookup"><span data-stu-id="708c6-156">For [Phase 3: Windows 10 Enterprise](windows10-infrastructure.md), deploy:</span></span>

- <span data-ttu-id="708c6-157">A infraestrutura para implantar novos dispositivos com Windows 10 Enterprise e atualizar seus dispositivos do Windows 7 ou Windows 8.1 para o Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="708c6-157">The infrastructure to deploy new devices with Windows 10 Enterprise and to upgrade of your Windows 7 or Windows 8.1 devices to Windows 10 Enterprise</span></span>
- <span data-ttu-id="708c6-158">Habilitar recursos de segurança abrangentes de identidade, identificação de ameaças e proteção de informações</span><span class="sxs-lookup"><span data-stu-id="708c6-158">Enabling comprehensive security features for identity, threat, and information protection</span></span>

<span data-ttu-id="708c6-159">Esta é a configuração resultante com dispositivos do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="708c6-159">Here's the resulting configuration with Windows 10 Enterprise devices.</span></span>

![Elementos do Windows 10 Enterprise para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
<span data-ttu-id="708c6-161">Para a [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md), implante a infraestrutura para instalar o Office 365 ProPlus ou atualizar seu pacote do Office instalado no momento, como o Office 2010 ou o Office 2013, para o Office 365 ProPlus nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="708c6-161">For [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md), deploy the infrastructure to install Office 365 ProPlus or upgrade your currently installed Office suite, such as Office 2010 or Office 2013, to Office 365 ProPlus on your organization devices.</span></span> <span data-ttu-id="708c6-162">Isso dará aos seus usuários a melhor segurança e experiências colaborativas.</span><span class="sxs-lookup"><span data-stu-id="708c6-162">This will give your users the best security and collaborative experiences.</span></span>

<span data-ttu-id="708c6-163">Esta é a configuração que resulta da instalação do Office 365 ProPlus nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="708c6-163">Here's the resulting configuration with Office 365 ProPlus installed on devices.</span></span>

![Elementos do Office 365 ProPlus para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
<span data-ttu-id="708c6-165">Para a [Fase 5: gerenciamento de dispositivos móveis](mobility-infrastructure.md), implante o gerenciamento de dispositivos e aplicativos do Intune para:</span><span class="sxs-lookup"><span data-stu-id="708c6-165">For [Phase 5: Mobile device management](mobility-infrastructure.md), deploy Intune device and app management for:</span></span>

- <span data-ttu-id="708c6-166">Registrar os dispositivos do Windows 10 Enterprise, iOS, macOS, Android e Android Enterprise para que eles recebam recursos e configurações de segurança definidos pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="708c6-166">Enrollment of your Windows 10 Enterprise, iOS, macOS, Android, and Android Enterprise devices so they receive features and security settings defined by your organization.</span></span>
- <span data-ttu-id="708c6-167">Configurações de aplicativos para segurança extra e com capacidade de permitir ou bloquear aplicativos, mesmo em dispositivos pessoais de propriedade dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="708c6-167">App settings for extra security and to allow or block apps, even on employee-owned personal devices.</span></span>
- <span data-ttu-id="708c6-168">Políticas de conformidade com Acesso Condicional para impedir que dispositivos que não estejam em conformidade se conectem.</span><span class="sxs-lookup"><span data-stu-id="708c6-168">Compliance policies with Conditional Access to prevent non-compliant devices from connecting.</span></span>

<span data-ttu-id="708c6-169">Esta é a configuração resultante com as políticas e dispositivos registrados do Intune realçados.</span><span class="sxs-lookup"><span data-stu-id="708c6-169">Here's the resulting configuration with Intune enrolled devices and policies highlighted.</span></span>

![Elementos de gerenciamento de dispositivos móveis para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
<span data-ttu-id="708c6-171">Para a [Fase 6: proteção de informações](infoprotect-infrastructure.md), crie e configure a proteção para seus ativos digitais com:</span><span class="sxs-lookup"><span data-stu-id="708c6-171">For [Phase 6: Information protection](infoprotect-infrastructure.md), design and configure protection for your digital assets with:</span></span>

- <span data-ttu-id="708c6-172">Políticas DLP do Office 365.</span><span class="sxs-lookup"><span data-stu-id="708c6-172">Office 365 DLP policies.</span></span>
- <span data-ttu-id="708c6-173">Rótulos de sensibilidade do Office 365 para criptografia e permissões que acompanham os arquivos.</span><span class="sxs-lookup"><span data-stu-id="708c6-173">Office 365 sensitivity labels for encryption and permissions that travel with files.</span></span>

<span data-ttu-id="708c6-174">Esta é a configuração resultante com políticas DLP e rótulos de confidencialidade realçados.</span><span class="sxs-lookup"><span data-stu-id="708c6-174">Here's the resulting configuration with DLP policies and sensitivity labels highlighted.</span></span>

![Elementos de proteção de informações para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
<span data-ttu-id="708c6-176">Para acessar os aplicativos locais, você pode usar o [Proxy de Aplicativo do Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), que requer um ambiente de identidade híbrido.</span><span class="sxs-lookup"><span data-stu-id="708c6-176">For access to on-premises apps, you can use [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), which requires a hybrid identity environment.</span></span>

<span data-ttu-id="708c6-177">Esta é a configuração resultante com os componentes de proxy de aplicativo realçados.</span><span class="sxs-lookup"><span data-stu-id="708c6-177">Here's the resulting configuration with the application proxy components highlighted.</span></span>

![Elementos de proxy de aplicativo para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a><span data-ttu-id="708c6-179">Etapa 2: cargas de trabalho para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="708c6-179">Step 2: Workloads for remote workers</span></span>

<span data-ttu-id="708c6-180">Para [Exchange Online](exchangeonline-workload.md), implante as caixas de correio do Exchange Online para cada um dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="708c6-180">For [Exchange Online](exchangeonline-workload.md), deploy Exchange Online mailboxes to each of your users.</span></span>

<span data-ttu-id="708c6-181">Para o [Teams](teams-workload.md), implante o Teams para seus usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="708c6-181">For [Teams](teams-workload.md), deploy Teams to your users and groups.</span></span>

<span data-ttu-id="708c6-182">Para o [SharePoint e o OneDrive](sharepoint-online-onedrive-workload.md), implante sites de comunicação ou de equipe do SharePoint e pastas do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="708c6-182">For [SharePoint and OneDrive](sharepoint-online-onedrive-workload.md), deploy SharePoint team or communication sites and OneDrive folders.</span></span>

<span data-ttu-id="708c6-183">Esta é a configuração resultante com as cargas de trabalho realçadas.</span><span class="sxs-lookup"><span data-stu-id="708c6-183">Here's the resulting configuration with the workloads highlighted.</span></span>

![Cargas de trabalho do Microsoft 365 para funcionários remotos](../media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a><span data-ttu-id="708c6-185">Resultados da implantação</span><span class="sxs-lookup"><span data-stu-id="708c6-185">Deployment results</span></span>

<span data-ttu-id="708c6-186">Depois de implantar a infraestrutura de fundação e cargas de trabalho e distribuir o Windows 10 Enterprise e o Office 365 ProPlus, os funcionários remotos:</span><span class="sxs-lookup"><span data-stu-id="708c6-186">After deploying the foundation infrastructure and workloads and rolling out Windows 10 Enterprise and Office 365 ProPlus, remote workers:</span></span>

- <span data-ttu-id="708c6-187">Ficam sujeitos a autenticação forte e a proteção de identidade.</span><span class="sxs-lookup"><span data-stu-id="708c6-187">Are subject to strong authentication and identity protection.</span></span>
- <span data-ttu-id="708c6-188">Recebem a versão mais recente e mais segura do Windows em seus dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="708c6-188">Have the latest and most secure version of Windows on their Windows devices.</span></span>
- <span data-ttu-id="708c6-189">Recebem a versão mais recente e mais produtiva do pacote Office em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="708c6-189">Have the latest and most productive version of the Office suite on their devices.</span></span>
- <span data-ttu-id="708c6-190">Ficam sujeitos a políticas de conformidade de dispositivos e gerenciamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="708c6-190">Are subject to app management and device compliance policies.</span></span>
- <span data-ttu-id="708c6-191">Ficam sujeitos a restrições e políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="708c6-191">Are subject to DLP policies and restrictions.</span></span>
- <span data-ttu-id="708c6-192">Podem atribuir rótulos de confidencialidade para criptografia e permissões que viajam com arquivos e email.</span><span class="sxs-lookup"><span data-stu-id="708c6-192">Can assign sensitivity labels for encryption and permissions that travel with files and email.</span></span>
- <span data-ttu-id="708c6-193">Podem acessar aplicativos locais sem uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="708c6-193">Can access on-premises apps without a VPN connection.</span></span>
- <span data-ttu-id="708c6-194">Podem executar seu próprio trabalho e participar de colaboração em tempo real com colegas de trabalho por meio de chats, reuniões e arquivos no Teams, SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="708c6-194">Can perform their own work and participate in real-time collaboration with co-workers with chats, meetings, and files in Teams and files in SharePoint and OneDrive.</span></span>

<span data-ttu-id="708c6-195">Quando estiver offline (não conectado à Internet), seus funcionários remotos podem alterar cópias locais de arquivos.</span><span class="sxs-lookup"><span data-stu-id="708c6-195">When offline (not connected to the Internet), your remote workers can change local copies of files.</span></span> <span data-ttu-id="708c6-196">Ao se reconectar à Internet, o OneDrive sincroniza cópias locais com os arquivos armazenados na sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="708c6-196">When they reconnect to the Internet, OneDrive synchronizes local copies with the files stored in your Microsoft 365 subscription.</span></span> 

<span data-ttu-id="708c6-197">Esta é a configuração resultante para funcionários remotos da sua organização se você usar a identidade híbrida.</span><span class="sxs-lookup"><span data-stu-id="708c6-197">Here's the resulting configuration for remote workers of your organization if you use hybrid identity.</span></span>

![Configuração final de uma organização com identidade híbrida](../media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
<span data-ttu-id="708c6-199">Esta é a configuração resultante para funcionários remotos sua organização, caso você use a identidade somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="708c6-199">Here's the resulting configuration for remote workers your organization if you use cloud-only identity.</span></span>

![Configuração final de uma organização com identidade somente na nuvem](../media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a><span data-ttu-id="708c6-201">Fase 2: orientar a adoção do usuário para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="708c6-201">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="708c6-202">Agora que a infraestrutura de fundação e as cargas de trabalho estão em vigor, é hora de direcionar o uso contínuo desses recursos para seus funcionários remotos, para que eles possam ser produtivos em qualquer lugar e a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="708c6-202">Now that the foundation infrastructure and workloads are in place, it’s time to drive the ongoing usage of these capabilities to your remote workers so they can be productive anywhere and at any time.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="708c6-203">Etapa 1: treinar os usuários</span><span class="sxs-lookup"><span data-stu-id="708c6-203">Step 1: Train your users</span></span>

<span data-ttu-id="708c6-204">Treinar seus funcionários remotos em:</span><span class="sxs-lookup"><span data-stu-id="708c6-204">Train your remote workers on:</span></span>

- <span data-ttu-id="708c6-205">Procedimentos de entrada apropriados, incluindo o registro da MFA, e como as entradas podem ser desafiadas quando o risco é detectado.</span><span class="sxs-lookup"><span data-stu-id="708c6-205">Proper sign-in procedures, including MFA registration, and how sign ins can be challenged when risk is detected.</span></span>
- <span data-ttu-id="708c6-206">O uso dos dispositivos e como as políticas podem ser usadas para bloquear o acesso a dispositivos que não estejam em conformidade.</span><span class="sxs-lookup"><span data-stu-id="708c6-206">The use of devices and how policies can be used to block access for non-compliant devices.</span></span>
- <span data-ttu-id="708c6-207">O uso de aplicativos permitidos e como as políticas do aplicativo Intune podem ser usadas para bloquear aplicativos.</span><span class="sxs-lookup"><span data-stu-id="708c6-207">The use of allowed apps and how Intune app polices can be used to block apps.</span></span>
- <span data-ttu-id="708c6-208">Recursos de segurança do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="708c6-208">Windows 10 Enterprise security features.</span></span>
- <span data-ttu-id="708c6-209">Como usar o Outlook para email e calendário.</span><span class="sxs-lookup"><span data-stu-id="708c6-209">How to use Outlook for email and calendaring.</span></span>
- <span data-ttu-id="708c6-210">Como usar o [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) para chat, conferências baseadas em vídeo, compartilhamento de documentos e conversas encadeadas.</span><span class="sxs-lookup"><span data-stu-id="708c6-210">How to use [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="708c6-211">Como usar sites da equipe ou comunicações do SharePoint e pastas do OneDrive para procurar arquivos na biblioteca de um usuário e os que pertencem a um grupo.</span><span class="sxs-lookup"><span data-stu-id="708c6-211">How to use SharePoint team or communication sites and OneDrive folders to browse files in a user's library and those belonging to a group.</span></span>
- <span data-ttu-id="708c6-212">Como usar e aplicar rótulos de sensibilidade para arquivos que contenham dados confidenciais ou altamente regulados, para versões locais e online dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="708c6-212">How to use and apply sensitivity labels for files containing sensitive or highly regulated data, for both local and online versions of files.</span></span>

<span data-ttu-id="708c6-213">Este treinamento deve incluir exercícios práticos para que os usuários possam experimentar esses recursos e os resultados.</span><span class="sxs-lookup"><span data-stu-id="708c6-213">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a><span data-ttu-id="708c6-214">Etapa 2: realizar revisões periódicas de uso e de agir sobre comentários dos funcionários</span><span class="sxs-lookup"><span data-stu-id="708c6-214">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="708c6-215">Nas semanas após o treinamento:</span><span class="sxs-lookup"><span data-stu-id="708c6-215">In the weeks after training:</span></span>

- <span data-ttu-id="708c6-216">Aja rapidamente sobre os comentários de trabalhadores remotos e ajuste políticas e configurações.</span><span class="sxs-lookup"><span data-stu-id="708c6-216">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="708c6-217">Analise o uso de equipes, sites do SharePoint e pastas do OneDrive e compare-o a expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="708c6-217">Analyze usage for teams, SharePoint sites, and OneDrive folders and compare it with usage expectations.</span></span>
- <span data-ttu-id="708c6-218">Verifique se os arquivos confidenciais ou altamente regulamentados foram corretamente rotulados com o rótulo de sensibilidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="708c6-218">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="708c6-219">Repita o treinamento dos usuários conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="708c6-219">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="708c6-220">Resultados de adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="708c6-220">User adoption results</span></span>

<span data-ttu-id="708c6-221">Seus funcionários remotos podem usar o Windows 10 Enterprise ou outros dispositivos e o Office 365 ProPlus para acessar e trabalhar em serviços compartilhados e recursos de nuvem do Microsoft 365 Enterprise em um ambiente seguro, para participar de reuniões, criar e colaborar em tempo real.</span><span class="sxs-lookup"><span data-stu-id="708c6-221">Your remote workers can use their Windows 10 Enterprise or other devices and Office 365 ProPlus to access and work on shared Microsoft 365 Enterprise cloud services and resources in a secure environment, and they’re meeting, creating, and collaborating in real time.</span></span>

## <a name="see-also"></a><span data-ttu-id="708c6-222">Confira também</span><span class="sxs-lookup"><span data-stu-id="708c6-222">See also</span></span>

[<span data-ttu-id="708c6-223">Cargas de trabalho e cenários</span><span class="sxs-lookup"><span data-stu-id="708c6-223">Workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="708c6-224">[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="708c6-224">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="708c6-225">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="708c6-225">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
