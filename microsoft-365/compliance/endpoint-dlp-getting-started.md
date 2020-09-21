---
title: Introdução à prevenção contra perda de dados de ponto de extremidade do Microsoft 365 (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Configure a prevenção contra perda de dados de ponto de extremidade do Microsoft 365 para monitorar as atividades de arquivo e implementar ações de proteção para os pontos de extremidade desse arquivo.
ms.openlocfilehash: 43ab2a30570f153f16819ede2eeed1f0e091da74
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949841"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="b7995-103">Introdução à prevenção contra perda de dados do ponto de extremidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="b7995-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="b7995-104">A prevenção contra perda de dados de ponto de extremidade do Microsoft (Endpoint DLP) faz parte do pacote de recursos de prevenção contra perda de dados (DLP) da Microsoft 365, que você pode usar para descobrir e proteger itens confidenciais em todos os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7995-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="b7995-105">Para obter mais informações sobre todas as ofertas de DLP da Microsoft, confira [Visão geral de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b7995-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="b7995-106">Para saber mais sobre o Endpoint DLP, confira [Saber mais sobre a prevenção contra perda de dados do ponto de extremidade (visualização)](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="b7995-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="b7995-107">O Microsoft Endpoint DLP permite monitorar dispositivos Windows 10 e detectar quando itens confidenciais são usados e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="b7995-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="b7995-108">Isso dá a você a visibilidade e o controle necessários para garantir que eles sejam usados e protegidos corretamente, e para ajudar a evitar o comportamento arriscado que possa comprometer.</span><span class="sxs-lookup"><span data-stu-id="b7995-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b7995-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b7995-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="b7995-110">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="b7995-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="b7995-111">Antes de começar a usar o Endpoint DLP, confirme seu [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e os complementos.</span><span class="sxs-lookup"><span data-stu-id="b7995-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="b7995-112">Para acessar e usar a funcionalidade do Endpoint DLP, você deve ter uma dessas assinaturas ou complementos.</span><span class="sxs-lookup"><span data-stu-id="b7995-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="b7995-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7995-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="b7995-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="b7995-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="b7995-115">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7995-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="b7995-116">Conformidade do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="b7995-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="b7995-117">Governança e Proteção de Informações do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7995-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="b7995-118">Governança e Proteção de Informações do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="b7995-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="b7995-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="b7995-119">Permissions</span></span>

<span data-ttu-id="b7995-120">Para habilitar o gerenciamento de dispositivos, a conta que você usa deve ser um membro de qualquer uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="b7995-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="b7995-121">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b7995-121">Global admin</span></span>
- <span data-ttu-id="b7995-122">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="b7995-122">Security admin</span></span>
- <span data-ttu-id="b7995-123">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-123">Compliance admin</span></span>

<span data-ttu-id="b7995-124">Se você quiser usar uma conta personalizada para exibir as configurações de gerenciamento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="b7995-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="b7995-125">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b7995-125">Global admin</span></span>
- <span data-ttu-id="b7995-126">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-126">Compliance admin</span></span>
- <span data-ttu-id="b7995-127">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-127">Compliance data admin</span></span>
- <span data-ttu-id="b7995-128">Leitor global</span><span class="sxs-lookup"><span data-stu-id="b7995-128">Global reader</span></span>

<span data-ttu-id="b7995-129">Se você quiser usar uma conta personalizada para acessar a página de integração/remoção, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="b7995-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="b7995-130">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b7995-130">Global admin</span></span>
- <span data-ttu-id="b7995-131">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-131">Compliance admin</span></span>

<span data-ttu-id="b7995-132">Se você quiser usar uma conta personalizada para ativar/desativar o monitoramento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="b7995-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="b7995-133">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b7995-133">Global admin</span></span>
- <span data-ttu-id="b7995-134">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-134">Compliance admin</span></span>

<span data-ttu-id="b7995-135">Os dados do Endpoint DLP podem ser exibidos no [Explorador de atividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="b7995-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="b7995-136">Há quatro funções que concedem permissão para o explorador de atividades, a conta que você usa para acessar os dados deve ser um membro de qualquer uma delas.</span><span class="sxs-lookup"><span data-stu-id="b7995-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="b7995-137">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b7995-137">Global admin</span></span>
- <span data-ttu-id="b7995-138">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-138">Compliance admin</span></span>
- <span data-ttu-id="b7995-139">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="b7995-139">Security admin</span></span>
- <span data-ttu-id="b7995-140">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="b7995-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="b7995-141">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b7995-141">Prepare your endpoints</span></span>

<span data-ttu-id="b7995-142">Certifique-se de que os dispositivos Windows 10 que você pretende implantar o Endpoint DLP atendam a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="b7995-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="b7995-143">Deve estar executando o Windows 10 Build 1809 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7995-143">Must be running Windows 10 build 1809 or up.</span></span>
2. <span data-ttu-id="b7995-144">Todos os dispositivos devem estar [ingressados no Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) ou no Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="b7995-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="b7995-145">Instalar o navegador Microsoft Chromium Edge no dispositivo do ponto de extremidade para impor ações de política para a atividade carregar na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b7995-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="b7995-146">Confira, [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="b7995-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="b7995-147">Dispositivos de integração no gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b7995-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="b7995-148">Você deve habilitar o monitoramento de dispositivos e encaminhar os pontos de extremidade antes de poder monitorar e proteger itens confidenciais em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7995-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="b7995-149">Estas ações estão concluídas no portal de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7995-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="b7995-150">Se você quiser que os dispositivos integrados ainda não estejam integrados, baixe o script apropriado e distribua-o a esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7995-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="b7995-151">Siga o [Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="b7995-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="b7995-152">Se você já tiver dispositivos integrados na [Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/), eles já serão exibidos na lista dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="b7995-152">If you already have devices onboarded into [Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="b7995-153">Siga o [Procedimento com dispositivos integrados no MDATP](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).</span><span class="sxs-lookup"><span data-stu-id="b7995-153">Follow the [With devices onboarded into MDATP procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="b7995-154">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="b7995-154">Onboarding devices</span></span>

<span data-ttu-id="b7995-155">Neste cenário de implantação, você integrará dispositivos que ainda não foram integrados e você só deseja monitorar e proteger itens confidenciais contra compartilhamento não intencional em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b7995-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="b7995-156">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b7995-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="b7995-157">Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7995-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   ![habilitar o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > <span data-ttu-id="b7995-159">Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7995-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="b7995-160">Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7995-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="b7995-161">A lista estará vazia até você integrar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7995-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="b7995-162">Escolha **Integração** para iniciar o processo de integração.</span><span class="sxs-lookup"><span data-stu-id="b7995-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="b7995-163">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="b7995-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   ![método de implementação](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. <span data-ttu-id="b7995-165">Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="b7995-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="b7995-166">Esse link levará você a uma página inicial onde você pode acessar os procedimentos MDATP que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="b7995-166">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="b7995-167">Integrar computadores com Windows 10 usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="b7995-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="b7995-168">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b7995-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="b7995-169">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="b7995-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="b7995-170">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="b7995-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="b7995-171">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="b7995-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="b7995-172">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na lista dispositivos e começar a relatar logs de atividades de auditoria para o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="b7995-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="b7995-173">Esta experiência está na imposição da licença.</span><span class="sxs-lookup"><span data-stu-id="b7995-173">This experience is under license enforcement.</span></span> <span data-ttu-id="b7995-174">Sem a licença necessária, os dados não estarão visíveis nem acessíveis.</span><span class="sxs-lookup"><span data-stu-id="b7995-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-mdatp"></a><span data-ttu-id="b7995-175">Com dispositivos integrados no MDATP</span><span class="sxs-lookup"><span data-stu-id="b7995-175">With devices onboarded into MDATP</span></span>

<span data-ttu-id="b7995-176">Neste cenário, MDATP já está implantado e há relatórios de pontos de extremidade no.</span><span class="sxs-lookup"><span data-stu-id="b7995-176">In this scenario, MDATP is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="b7995-177">Todos esses pontos de extremidade serão exibidos na lista dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="b7995-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="b7995-178">Você pode continuar a integrar novos dispositivos no ponto de extremidade DLP para expandir a cobertura usando o[Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="b7995-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="b7995-179">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b7995-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="b7995-180">Abra a página de configurações do Centro de conformidade e escolha **Habilitar o monitoramento de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7995-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="b7995-181">Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7995-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="b7995-182">Você deverá ver a lista de dispositivos que já estão relatando para o MDATP.</span><span class="sxs-lookup"><span data-stu-id="b7995-182">You should see the list of devices that are already reporting in to MDATP.</span></span> <span data-ttu-id="b7995-183">![gerenciamento de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="b7995-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="b7995-184">Escolha **Integração**, caso precise integrar dispositivos adicionais.</span><span class="sxs-lookup"><span data-stu-id="b7995-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="b7995-185">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="b7995-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="b7995-186">Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="b7995-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="b7995-187">Esse link levará você a uma página inicial onde você pode acessar os procedimentos MDATP que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="b7995-187">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="b7995-188">Integrar computadores com Windows 10 usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="b7995-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="b7995-189">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b7995-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="b7995-190">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="b7995-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="b7995-191">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="b7995-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="b7995-192">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="b7995-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="b7995-193">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na tabela **Dispositivos** e começar a relatar logs de atividades de auditoria para o **Explorador de atividades**.</span><span class="sxs-lookup"><span data-stu-id="b7995-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="b7995-194">Esta experiência está na imposição da licença.</span><span class="sxs-lookup"><span data-stu-id="b7995-194">This experience is under license enforcement.</span></span> <span data-ttu-id="b7995-195">Sem a licença necessária, os dados não estarão visíveis nem acessíveis.</span><span class="sxs-lookup"><span data-stu-id="b7995-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="b7995-196">Exibir dados de Endpoint DLP no explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="b7995-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="b7995-197">Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) do seu domínio no Centro de conformidade do Microsoft 365 e escolha o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="b7995-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="b7995-198">Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7995-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="b7995-200">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b7995-200">Next steps</span></span>
<span data-ttu-id="b7995-201">Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b7995-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="b7995-202">Usando a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="b7995-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="b7995-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="b7995-203">See also</span></span>

- [<span data-ttu-id="b7995-204">Saiba mais sobre a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="b7995-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="b7995-205">Usando a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="b7995-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="b7995-206">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="b7995-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="b7995-207">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="b7995-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="b7995-208">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="b7995-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="b7995-209">Proteção Avançada contra Ameaças do Microsoft Defender (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="b7995-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="b7995-210">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7995-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="b7995-211">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7995-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="b7995-212">Associados a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="b7995-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="b7995-213">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="b7995-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
