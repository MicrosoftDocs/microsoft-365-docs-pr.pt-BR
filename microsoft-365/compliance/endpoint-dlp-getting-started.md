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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Configure a prevenção contra perda de dados de ponto de extremidade do Microsoft 365 para monitorar as atividades de arquivo e implementar ações de proteção para os pontos de extremidade desse arquivo.
ms.openlocfilehash: e0b9ba6afcad0c683aaa7386998a621f279aa9eb
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379240"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="e98e9-103">Introdução à prevenção contra perda de dados do ponto de extremidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="e98e9-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="e98e9-104">A prevenção contra perda de dados de ponto de extremidade do Microsoft (Endpoint DLP) faz parte do pacote de recursos de prevenção contra perda de dados (DLP) da Microsoft 365, que você pode usar para descobrir e proteger itens confidenciais em todos os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e98e9-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="e98e9-105">Para obter mais informações sobre todas as ofertas de DLP da Microsoft, confira [Visão geral de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e98e9-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="e98e9-106">Para saber mais sobre o Endpoint DLP, confira [Saber mais sobre a prevenção contra perda de dados do ponto de extremidade (visualização)](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="e98e9-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="e98e9-107">O Microsoft Endpoint DLP permite monitorar dispositivos Windows 10 e detectar quando itens confidenciais são usados e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="e98e9-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="e98e9-108">Isso dá a você a visibilidade e o controle necessários para garantir que eles sejam usados e protegidos corretamente, e para ajudar a evitar o comportamento arriscado que possa comprometer.</span><span class="sxs-lookup"><span data-stu-id="e98e9-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e98e9-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e98e9-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="e98e9-110">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="e98e9-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="e98e9-111">Antes de começar a usar o Endpoint DLP, confirme seu [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e os complementos.</span><span class="sxs-lookup"><span data-stu-id="e98e9-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="e98e9-112">Para acessar e usar a funcionalidade do Endpoint DLP, você deve ter uma dessas assinaturas ou complementos.</span><span class="sxs-lookup"><span data-stu-id="e98e9-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="e98e9-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e98e9-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="e98e9-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="e98e9-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="e98e9-115">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e98e9-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="e98e9-116">Conformidade do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="e98e9-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="e98e9-117">Governança e Proteção de Informações do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e98e9-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="e98e9-118">Governança e Proteção de Informações do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="e98e9-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="e98e9-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="e98e9-119">Permissions</span></span>

<span data-ttu-id="e98e9-120">Para habilitar o gerenciamento de dispositivos, a conta que você usa deve ser um membro de qualquer uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e98e9-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="e98e9-121">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e98e9-121">Global admin</span></span>
- <span data-ttu-id="e98e9-122">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="e98e9-122">Security admin</span></span>
- <span data-ttu-id="e98e9-123">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-123">Compliance admin</span></span>

<span data-ttu-id="e98e9-124">Se você quiser usar uma conta personalizada para exibir as configurações de gerenciamento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e98e9-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="e98e9-125">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e98e9-125">Global admin</span></span>
- <span data-ttu-id="e98e9-126">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-126">Compliance admin</span></span>
- <span data-ttu-id="e98e9-127">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-127">Compliance data admin</span></span>
- <span data-ttu-id="e98e9-128">Leitor global</span><span class="sxs-lookup"><span data-stu-id="e98e9-128">Global reader</span></span>

<span data-ttu-id="e98e9-129">Se você quiser usar uma conta personalizada para acessar a página de integração/remoção, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e98e9-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="e98e9-130">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e98e9-130">Global admin</span></span>
- <span data-ttu-id="e98e9-131">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-131">Compliance admin</span></span>

<span data-ttu-id="e98e9-132">Se você quiser usar uma conta personalizada para ativar/desativar o monitoramento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e98e9-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="e98e9-133">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e98e9-133">Global admin</span></span>
- <span data-ttu-id="e98e9-134">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-134">Compliance admin</span></span>

<span data-ttu-id="e98e9-135">Os dados do Endpoint DLP podem ser exibidos no [Explorador de atividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="e98e9-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="e98e9-136">Há quatro funções que concedem permissão para o explorador de atividades, a conta que você usa para acessar os dados deve ser um membro de qualquer uma delas.</span><span class="sxs-lookup"><span data-stu-id="e98e9-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="e98e9-137">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e98e9-137">Global admin</span></span>
- <span data-ttu-id="e98e9-138">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-138">Compliance admin</span></span>
- <span data-ttu-id="e98e9-139">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="e98e9-139">Security admin</span></span>
- <span data-ttu-id="e98e9-140">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="e98e9-141">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="e98e9-141">Prepare your endpoints</span></span>

<span data-ttu-id="e98e9-142">Certifique-se de que os dispositivos Windows 10 que você pretende implantar o Endpoint DLP atendam a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="e98e9-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="e98e9-143">Deve estar executando o Windows 10 Build 1809 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e98e9-143">Must be running Windows 10 build 1809 or up.</span></span>
2. <span data-ttu-id="e98e9-144">Todos os dispositivos devem estar [ingressados no Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) ou no Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="e98e9-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="e98e9-145">Instalar o navegador Microsoft Chromium Edge no dispositivo do ponto de extremidade para impor ações de política para a atividade carregar na nuvem.</span><span class="sxs-lookup"><span data-stu-id="e98e9-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="e98e9-146">Confira, [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="e98e9-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="e98e9-147">Dispositivos de integração no gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e98e9-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="e98e9-148">Você deve habilitar o monitoramento de dispositivos e encaminhar os pontos de extremidade antes de poder monitorar e proteger itens confidenciais em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e98e9-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="e98e9-149">Estas ações estão concluídas no portal de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e98e9-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="e98e9-150">Se você quiser que os dispositivos integrados ainda não estejam integrados, baixe o script apropriado e distribua-o a esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e98e9-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="e98e9-151">Siga o [Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="e98e9-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="e98e9-152">Se você já tiver dispositivos integrados na [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), eles já serão exibidos na lista dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="e98e9-152">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="e98e9-153">Siga [Com dispositivos integrados no procedimento Microsoft Defender para Ponto de Extremidade](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span><span class="sxs-lookup"><span data-stu-id="e98e9-153">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="e98e9-154">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="e98e9-154">Onboarding devices</span></span>

<span data-ttu-id="e98e9-155">Neste cenário de implantação, você integrará dispositivos que ainda não foram integrados e você só deseja monitorar e proteger itens confidenciais contra compartilhamento não intencional em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e98e9-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="e98e9-156">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e98e9-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="e98e9-157">Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   ![habilitar o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > <span data-ttu-id="e98e9-159">Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e98e9-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="e98e9-160">Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="e98e9-161">A lista estará vazia até você integrar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e98e9-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="e98e9-162">Escolha **Integração** para iniciar o processo de integração.</span><span class="sxs-lookup"><span data-stu-id="e98e9-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="e98e9-163">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   ![método de implementação](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. <span data-ttu-id="e98e9-165">Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="e98e9-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="e98e9-166">Esse link levará você a uma página inicial onde você pode acessar os procedimentos do Microsoft Defender para Ponto de Extremidade que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="e98e9-166">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="e98e9-167">Integrar computadores com Windows 10 usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="e98e9-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="e98e9-168">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e98e9-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="e98e9-169">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e98e9-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="e98e9-170">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="e98e9-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="e98e9-171">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="e98e9-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="e98e9-172">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na lista dispositivos e começar a relatar logs de atividades de auditoria para o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="e98e9-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="e98e9-173">Esta experiência está na imposição da licença.</span><span class="sxs-lookup"><span data-stu-id="e98e9-173">This experience is under license enforcement.</span></span> <span data-ttu-id="e98e9-174">Sem a licença necessária, os dados não estarão visíveis nem acessíveis.</span><span class="sxs-lookup"><span data-stu-id="e98e9-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="e98e9-175">Com dispositivos integrados no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e98e9-175">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e98e9-176">Neste cenário, o Microsoft Defender para Ponto de Extremidade já está implantado e há relatórios de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e98e9-176">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="e98e9-177">Todos esses pontos de extremidade serão exibidos na lista dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="e98e9-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="e98e9-178">Você pode continuar a integrar novos dispositivos no ponto de extremidade DLP para expandir a cobertura usando o[Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="e98e9-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="e98e9-179">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e98e9-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="e98e9-180">Abra a página de configurações do Centro de conformidade e escolha **Habilitar o monitoramento de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="e98e9-181">Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="e98e9-182">Você deverá ver a lista de dispositivos que já estão relatando para o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e98e9-182">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e98e9-183">![gerenciamento de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="e98e9-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="e98e9-184">Escolha **Integração**, caso precise integrar dispositivos adicionais.</span><span class="sxs-lookup"><span data-stu-id="e98e9-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="e98e9-185">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="e98e9-186">Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="e98e9-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="e98e9-187">Esse link levará você a uma página inicial onde você pode acessar os procedimentos do Microsoft Defender para Ponto de Extremidade que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="e98e9-187">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="e98e9-188">Integrar computadores com Windows 10 usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="e98e9-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="e98e9-189">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e98e9-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="e98e9-190">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e98e9-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="e98e9-191">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="e98e9-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="e98e9-192">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="e98e9-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="e98e9-193">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na tabela **Dispositivos** e começar a relatar logs de atividades de auditoria para o **Explorador de atividades**.</span><span class="sxs-lookup"><span data-stu-id="e98e9-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="e98e9-194">Esta experiência está na imposição da licença.</span><span class="sxs-lookup"><span data-stu-id="e98e9-194">This experience is under license enforcement.</span></span> <span data-ttu-id="e98e9-195">Sem a licença necessária, os dados não estarão visíveis nem acessíveis.</span><span class="sxs-lookup"><span data-stu-id="e98e9-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="e98e9-196">Exibir dados de Endpoint DLP no explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="e98e9-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="e98e9-197">Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) do seu domínio no Centro de conformidade do Microsoft 365 e escolha o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="e98e9-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="e98e9-198">Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e98e9-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="e98e9-200">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e98e9-200">Next steps</span></span>
<span data-ttu-id="e98e9-201">Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e98e9-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="e98e9-202">Usando a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="e98e9-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="e98e9-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="e98e9-203">See also</span></span>

- [<span data-ttu-id="e98e9-204">Saiba mais sobre a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="e98e9-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="e98e9-205">Usando a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="e98e9-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="e98e9-206">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="e98e9-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e98e9-207">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="e98e9-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e98e9-208">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="e98e9-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e98e9-209">Proteção Avançada contra Ameaças do Microsoft Defender (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="e98e9-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="e98e9-210">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="e98e9-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="e98e9-211">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e98e9-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="e98e9-212">Associados a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="e98e9-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="e98e9-213">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="e98e9-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
