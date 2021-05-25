---
title: Introdução à prevenção contra perda de dados do Microsoft 365 Endpoint
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
description: Configure a prevenção contra perda de dados de ponto de extremidade do Microsoft 365 para monitorar atividades de arquivo e implementar ações de proteção para esses arquivos para pontos de extremidade.
ms.openlocfilehash: a6c0ec6f1248fdeecd8616b7eda000b7608d452d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651003"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="e9be4-103">Introdução à Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="e9be4-104">A prevenção contra perda de dados de ponto de extremidade do Microsoft (Endpoint DLP) faz parte do pacote de recursos de prevenção contra perda de dados (DLP) da Microsoft 365, que você pode usar para descobrir e proteger itens confidenciais em todos os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9be4-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="e9be4-105">Para obter mais informações sobre todas as ofertas de DLP da Microsoft, consulte [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="e9be4-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="e9be4-106">Para saber mais sobre a DLP do ponto de extremidade, confira [Saiba mais sobre a prevenção contra perda de dados do Ponto de extremidade](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="e9be4-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="e9be4-107">O Microsoft Endpoint DLP permite monitorar dispositivos Windows 10 e detectar quando itens confidenciais são usados e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="e9be4-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="e9be4-108">Isso dá a você a visibilidade e o controle necessários para garantir que eles sejam usados e protegidos corretamente, e para ajudar a evitar o comportamento arriscado que possa comprometer.</span><span class="sxs-lookup"><span data-stu-id="e9be4-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e9be4-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e9be4-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="e9be4-110">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="e9be4-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="e9be4-111">Antes de começar a usar o Endpoint DLP, confirme seu [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e os complementos.</span><span class="sxs-lookup"><span data-stu-id="e9be4-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="e9be4-112">Para acessar e usar a funcionalidade do Endpoint DLP, você deve ter uma dessas assinaturas ou complementos.</span><span class="sxs-lookup"><span data-stu-id="e9be4-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="e9be4-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e9be4-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="e9be4-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="e9be4-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="e9be4-115">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e9be4-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="e9be4-116">Conformidade do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="e9be4-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="e9be4-117">Governança e Proteção de Informações do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e9be4-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="e9be4-118">Governança e Proteção de Informações do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="e9be4-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="e9be4-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="e9be4-119">Permissions</span></span>

<span data-ttu-id="e9be4-120">Para habilitar o gerenciamento de dispositivos, a conta que você usa deve ser um membro de qualquer uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e9be4-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="e9be4-121">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9be4-121">Global admin</span></span>
- <span data-ttu-id="e9be4-122">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="e9be4-122">Security admin</span></span>
- <span data-ttu-id="e9be4-123">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-123">Compliance admin</span></span>

<span data-ttu-id="e9be4-124">Se você quiser usar uma conta personalizada para exibir as configurações de gerenciamento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e9be4-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="e9be4-125">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9be4-125">Global admin</span></span>
- <span data-ttu-id="e9be4-126">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-126">Compliance admin</span></span>
- <span data-ttu-id="e9be4-127">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-127">Compliance data admin</span></span>
- <span data-ttu-id="e9be4-128">Leitor global</span><span class="sxs-lookup"><span data-stu-id="e9be4-128">Global reader</span></span>

<span data-ttu-id="e9be4-129">Se você quiser usar uma conta personalizada para acessar a página de integração/remoção, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e9be4-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="e9be4-130">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9be4-130">Global admin</span></span>
- <span data-ttu-id="e9be4-131">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-131">Compliance admin</span></span>

<span data-ttu-id="e9be4-132">Se você quiser usar uma conta personalizada para ativar/desativar o monitoramento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="e9be4-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="e9be4-133">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9be4-133">Global admin</span></span>
- <span data-ttu-id="e9be4-134">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-134">Compliance admin</span></span>

<span data-ttu-id="e9be4-135">Os dados do Endpoint DLP podem ser exibidos no [Explorador de atividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="e9be4-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="e9be4-136">Há quatro funções que concedem permissão para o explorador de atividades, a conta que você usa para acessar os dados deve ser um membro de qualquer uma delas.</span><span class="sxs-lookup"><span data-stu-id="e9be4-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="e9be4-137">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9be4-137">Global admin</span></span>
- <span data-ttu-id="e9be4-138">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-138">Compliance admin</span></span>
- <span data-ttu-id="e9be4-139">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="e9be4-139">Security admin</span></span>
- <span data-ttu-id="e9be4-140">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-140">Compliance data admin</span></span>
- <span data-ttu-id="e9be4-141">Leitor global</span><span class="sxs-lookup"><span data-stu-id="e9be4-141">Global reader</span></span>
- <span data-ttu-id="e9be4-142">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="e9be4-142">Security reader</span></span>
- <span data-ttu-id="e9be4-143">Leitor de relatórios</span><span class="sxs-lookup"><span data-stu-id="e9be4-143">Reports reader</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="e9be4-144">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-144">Prepare your endpoints</span></span>

<span data-ttu-id="e9be4-145">Certifique-se de que os dispositivos Windows 10 que você pretende implantar o Endpoint DLP atendam a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="e9be4-145">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="e9be4-146">Deve estar executando o Windows 10 x64 build 1809 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e9be4-146">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="e9be4-147">A Versão do Cliente Antimalware é 4.18.2009.7 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="e9be4-147">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="e9be4-148">Verifique sua versão atual abrindo o aplicativo Segurança do Windows, selecione o ícone Configurações e, em seguida, selecione Sobre.</span><span class="sxs-lookup"><span data-stu-id="e9be4-148">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="e9be4-149">O número da versão está listado na Versão do Cliente Antimalware.</span><span class="sxs-lookup"><span data-stu-id="e9be4-149">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="e9be4-150">Atualize para a Versão do Cliente Antimalware instalando o Windows Update KB4052623.</span><span class="sxs-lookup"><span data-stu-id="e9be4-150">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="e9be4-151">Nenhum dos componentes de Segurança do Windows precisa estar ativo, você pode executar o ponto de extremidade da DLP independente do status de segurança do Windows, mas a [proteção em tempo real e o monitor de comportamento devem estar habilitados](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="e9be4-151">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="e9be4-152">As seguintes atualizações do Windows foram instaladas.</span><span class="sxs-lookup"><span data-stu-id="e9be4-152">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="e9be4-153">Essas atualizações não são um pré-requisito para integrar um dispositivo ao Ponto de extremidade da DLP, mas contêm correções para problemas importantes, portanto, devem ser instaladas antes de usar o produto.</span><span class="sxs-lookup"><span data-stu-id="e9be4-153">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="e9be4-154">Para Windows 10 1809 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="e9be4-154">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="e9be4-155">Para Windows 10 1903 ou 1909 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="e9be4-155">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="e9be4-156">Para Windows 10 2004 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="e9be4-156">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="e9be4-157">Para dispositivos que executam o Office 2016 (e nenhuma outra versão do Office) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="e9be4-157">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="e9be4-158">Todos os dispositivos devem um destes:</span><span class="sxs-lookup"><span data-stu-id="e9be4-158">All devices must be one of these:</span></span>
- [<span data-ttu-id="e9be4-159">Ingressado no Active Directory do Azure (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e9be4-159">Azure Active Directory (Azure AD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="e9be4-160">Ingressado no AD</span><span class="sxs-lookup"><span data-stu-id="e9be4-160">AD joined</span></span>
- [<span data-ttu-id="e9be4-161">Ingressado no Azure AD Híbrido</span><span class="sxs-lookup"><span data-stu-id="e9be4-161">Hybrid Azure AD joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
- [<span data-ttu-id="e9be4-162">Registrado no AAD</span><span class="sxs-lookup"><span data-stu-id="e9be4-162">AAD registered</span></span>](/azure/active-directory/user-help/user-help-register-device-on-network)

5. <span data-ttu-id="e9be4-163">Instalar o navegador Microsoft Chromium Edge no dispositivo do ponto de extremidade para impor ações de política para a atividade carregar na nuvem.</span><span class="sxs-lookup"><span data-stu-id="e9be4-163">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="e9be4-164">Confira, [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="e9be4-164">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="e9be4-165">Se você está no Canal Empresarial Mensal das versões 2004-2008 do Microsoft 365 Apps, há um problema conhecido com o DLP do ponto de extremidade classificando o conteúdo do Office, e você precisa atualizar para a versão 2009 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="e9be4-165">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="e9be4-166">Confira [Histórico de atualização do Microsoft 365 Apps (relacionado por data)](/officeupdates/update-history-microsoft365-apps-by-date) para as versões atuais.</span><span class="sxs-lookup"><span data-stu-id="e9be4-166">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="e9be4-167">Para saber mais sobre esse problema, confira a seção Pacote do Office de [notas de versão do Canal Atual em 2020](/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="e9be4-167">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="e9be4-168">Se você tem pontos de extremidade que usam um proxy de dispositivo para se conectar à Internet, siga os procedimentos em [definir as configurações de conexão com a Internet e o proxy do dispositivo para o Endpoint DLP](endpoint-dlp-configure-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="e9be4-168">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="e9be4-169">Dispositivos de integração no gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e9be4-169">Onboarding devices into device management</span></span>

<span data-ttu-id="e9be4-170">Você deve habilitar o monitoramento de dispositivos e encaminhar os pontos de extremidade antes de poder monitorar e proteger itens confidenciais em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9be4-170">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="e9be4-171">Estas ações estão concluídas no portal de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9be4-171">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="e9be4-172">Se você quiser que os dispositivos integrados ainda não estejam integrados, baixe o script apropriado e distribua-o a esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e9be4-172">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="e9be4-173">Siga o [Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="e9be4-173">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="e9be4-174">Se você já tiver dispositivos integrados na [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/), eles já serão exibidos na lista dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="e9be4-174">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="e9be4-175">Siga [Com dispositivos integrados no procedimento Microsoft Defender para Ponto de Extremidade](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="e9be4-175">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="e9be4-176">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="e9be4-176">Onboarding devices</span></span>

<span data-ttu-id="e9be4-177">Neste cenário de implantação, você integrará dispositivos que ainda não foram integrados e você só deseja monitorar e proteger itens confidenciais contra compartilhamento não intencional em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e9be4-177">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="e9be4-178">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e9be4-178">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="e9be4-179">Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-179">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9be4-180">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="e9be4-180">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="e9be4-181">Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9be4-181">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="e9be4-182">Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-182">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="e9be4-183">A lista estará vazia até você integrar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e9be4-183">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="e9be4-184">Escolha **Integração** para iniciar o processo de integração.</span><span class="sxs-lookup"><span data-stu-id="e9be4-184">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="e9be4-185">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9be4-186">![método de implantação](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="e9be4-186">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="e9be4-187">Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="e9be4-187">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="e9be4-188">Este link leva você a uma página de destino onde você pode acessar os procedimentos da Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="e9be4-188">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="e9be4-189">Integrar computadores com Windows 10 usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="e9be4-189">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="e9be4-190">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e9be4-190">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="e9be4-191">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e9be4-191">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="e9be4-192">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="e9be4-192">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="e9be4-193">Integrar computadores VDI (infraestrutura de área de trabalho virtual) não persistente em cenários de sessão única.</span><span class="sxs-lookup"><span data-stu-id="e9be4-193">Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios</span></span>

<span data-ttu-id="e9be4-194">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na lista dispositivos e começar a relatar logs de atividades de auditoria para o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="e9be4-194">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="e9be4-195">Esta experiência está na imposição da licença.</span><span class="sxs-lookup"><span data-stu-id="e9be4-195">This experience is under license enforcement.</span></span> <span data-ttu-id="e9be4-196">Sem a licença necessária, os dados não estarão visíveis nem acessíveis.</span><span class="sxs-lookup"><span data-stu-id="e9be4-196">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="e9be4-197">Com dispositivos integrados no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9be4-197">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e9be4-198">Neste cenário, o Microsoft Defender para Ponto de Extremidade já está implantado e há relatórios de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9be4-198">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="e9be4-199">Todos esses pontos de extremidade serão exibidos na lista dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="e9be4-199">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="e9be4-200">Você pode continuar a integrar novos dispositivos no ponto de extremidade DLP para expandir a cobertura usando o[Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="e9be4-200">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="e9be4-201">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e9be4-201">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="e9be4-202">Abra a página de configurações do Centro de conformidade e escolha **Habilitar o monitoramento de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-202">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="e9be4-203">Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-203">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="e9be4-204">Você deverá ver a lista de dispositivos que já estão relatando para o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9be4-204">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9be4-205">![gerenciamento de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="e9be4-205">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="e9be4-206">Escolha **Integração**, caso precise integrar dispositivos adicionais.</span><span class="sxs-lookup"><span data-stu-id="e9be4-206">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="e9be4-207">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-207">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="e9be4-208">Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="e9be4-208">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="e9be4-209">Este link leva você a uma página de destino onde você pode acessar os procedimentos da Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="e9be4-209">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="e9be4-210">Integrar computadores com Windows 10 usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="e9be4-210">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="e9be4-211">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e9be4-211">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="e9be4-212">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e9be4-212">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="e9be4-213">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="e9be4-213">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="e9be4-214">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="e9be4-214">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="e9be4-215">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na tabela **Dispositivos** e começar a relatar logs de atividades de auditoria para o **Explorador de atividades**.</span><span class="sxs-lookup"><span data-stu-id="e9be4-215">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="e9be4-216">Esta experiência está na imposição da licença.</span><span class="sxs-lookup"><span data-stu-id="e9be4-216">This experience is under license enforcement.</span></span> <span data-ttu-id="e9be4-217">Sem a licença necessária, os dados não estarão visíveis nem acessíveis.</span><span class="sxs-lookup"><span data-stu-id="e9be4-217">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="e9be4-218">Exibir alertas de prevenção contra perda de dados (DLP) do ponto de extremidade no painel de Gerenciamento de Alertas de DLP</span><span class="sxs-lookup"><span data-stu-id="e9be4-218">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="e9be4-219">Abra a Página de prevenção contra perda de dados no Centro de conformidade do Microsoft 365 e escolha Alertas.</span><span class="sxs-lookup"><span data-stu-id="e9be4-219">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="e9be4-220">Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9be4-220">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="e9be4-221">Exibir dados de Endpoint DLP no explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="e9be4-221">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="e9be4-222">Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) do seu domínio no Centro de conformidade do Microsoft 365 e escolha o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="e9be4-222">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="e9be4-223">Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9be4-223">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9be4-224">![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="e9be4-224">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9be4-225">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e9be4-225">Next steps</span></span>
<span data-ttu-id="e9be4-226">Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e9be4-226">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="e9be4-227">Usando a Prevenção contra perda de dados de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-227">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="e9be4-228">Confira também</span><span class="sxs-lookup"><span data-stu-id="e9be4-228">See also</span></span>

- [<span data-ttu-id="e9be4-229">Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-229">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="e9be4-230">Usando a prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-230">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="e9be4-231">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="e9be4-231">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="e9be4-232">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="e9be4-232">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e9be4-233">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="e9be4-233">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e9be4-234">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e9be4-234">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="e9be4-235">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="e9be4-235">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="e9be4-236">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9be4-236">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="e9be4-237">Dispositivos associados ao Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="e9be4-237">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="e9be4-238">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="e9be4-238">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
