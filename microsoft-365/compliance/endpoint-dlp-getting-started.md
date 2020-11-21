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
description: Configure a prevenção contra perda de dados do Microsoft 365 Endpoint para monitorar as atividades de arquivo e implementar ações de proteção para os pontos de extremidade desse arquivo.
ms.openlocfilehash: 8211ffbe3a84c0ee9fb4cb4c22d4dcea7f906a78
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371597"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="4418c-103">Introdução à Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="4418c-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="4418c-104">A prevenção contra perda de dados do Microsoft Endpoint (DLP do ponto de extremidade) faz parte do pacote de recursos de prevenção contra perda de dados (DLP) da Microsoft 365, que você pode usar para descobrir e proteger itens confidenciais em todos os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4418c-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="4418c-105">Para obter mais informações sobre todas as ofertas de DLP da Microsoft, confira [Visão geral de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4418c-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="4418c-106">Para saber mais sobre a prevenção contra perda de dados do ponto de extremidade, confira [Saiba mais sobre a prevenção contra perda de dados do Ponto de extremidade](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="4418c-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="4418c-p102">A Prevenção contra perda de dados do Ponto de extremidade da Microsoft permite monitorar dispositivos Windows 10 e detectar quando itens confidenciais são usados ​​e compartilhados. Isso lhe dá a visibilidade e o controle de que você precisa para garantir que eles sejam usados ​​e protegidos adequadamente e para ajudar a prevenir comportamentos de risco que podem comprometê-los.</span><span class="sxs-lookup"><span data-stu-id="4418c-p102">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared. This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4418c-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4418c-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="4418c-110">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="4418c-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="4418c-p103">Antes de começar a usar a Prevenção contra perda de dados do Ponto de extremidade, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e todos os complementos. Para acessar e usar a funcionalidade da DLP do ponto de extremidade, você deve ter uma dessas assinaturas ou complementos.</span><span class="sxs-lookup"><span data-stu-id="4418c-p103">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons. To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="4418c-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4418c-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="4418c-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="4418c-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="4418c-115">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4418c-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="4418c-116">Conformidade do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="4418c-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="4418c-117">Governança e Proteção de Informações do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4418c-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="4418c-118">Governança e Proteção de Informações do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="4418c-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="4418c-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="4418c-119">Permissions</span></span>

<span data-ttu-id="4418c-120">Para habilitar o gerenciamento de dispositivos, a conta que você usa deve ser um membro de qualquer uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="4418c-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="4418c-121">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4418c-121">Global admin</span></span>
- <span data-ttu-id="4418c-122">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="4418c-122">Security admin</span></span>
- <span data-ttu-id="4418c-123">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-123">Compliance admin</span></span>

<span data-ttu-id="4418c-124">Se você quiser usar uma conta personalizada para exibir as configurações de gerenciamento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="4418c-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="4418c-125">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4418c-125">Global admin</span></span>
- <span data-ttu-id="4418c-126">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-126">Compliance admin</span></span>
- <span data-ttu-id="4418c-127">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-127">Compliance data admin</span></span>
- <span data-ttu-id="4418c-128">Leitor global</span><span class="sxs-lookup"><span data-stu-id="4418c-128">Global reader</span></span>

<span data-ttu-id="4418c-129">Se você quiser usar uma conta personalizada para acessar a página de integração/remoção, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="4418c-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="4418c-130">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4418c-130">Global admin</span></span>
- <span data-ttu-id="4418c-131">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-131">Compliance admin</span></span>

<span data-ttu-id="4418c-132">Se você quiser usar uma conta personalizada para ativar/desativar o monitoramento de dispositivo, deverá estar em uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="4418c-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="4418c-133">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4418c-133">Global admin</span></span>
- <span data-ttu-id="4418c-134">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-134">Compliance admin</span></span>

<span data-ttu-id="4418c-p104">Os dados da Prevenção contra perda de dados do Ponto de extremidade podem ser visualizados no [Explorador de atividades](data-classification-activity-explorer.md). Existem quatro funções que concedem permissão ao explorador de atividades, a conta que você usa para acessar os dados deve ser membro de qualquer uma delas.</span><span class="sxs-lookup"><span data-stu-id="4418c-p104">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="4418c-137">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4418c-137">Global admin</span></span>
- <span data-ttu-id="4418c-138">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-138">Compliance admin</span></span>
- <span data-ttu-id="4418c-139">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="4418c-139">Security admin</span></span>
- <span data-ttu-id="4418c-140">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="4418c-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="4418c-141">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="4418c-141">Prepare your endpoints</span></span>

<span data-ttu-id="4418c-142">Certifique-se de que os dispositivos Windows 10 que você pretende implantar o Endpoint DLP atendam a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="4418c-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="4418c-143">Deve estar executando o Windows 10 x64 build 1809 ou superior.</span><span class="sxs-lookup"><span data-stu-id="4418c-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="4418c-p105">A versão do cliente Antimalware é 4.18.2009.7 ou mais recente. Verifique a versão atual abrindo o aplicativo Segurança do Windows, selecione o ícone Configurações e, em seguida, selecione Sobre. O número da versão está listado em Versão Cliente Antimalware. Atualize para a Versão mais recente do Cliente Antimalware instalando o Windows Update KB4052623. Observação: Nenhum dos componentes de Segurança do Windows precisa estar ativo, você pode executar a Prevenção contra perda de dados do Ponto de extremidade independentemente do status de segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="4418c-p105">Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623. Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="4418c-p106">As seguintes Atualizações do Windows são instaladas. Observação: Essas atualizações não são um pré-requisito para integrar um dispositivo a Prevenção contra perda de dados do Ponto de extremidade, mas contêm correções para problemas importantes, portanto, devem ser instaladas antes de usar o produto.</span><span class="sxs-lookup"><span data-stu-id="4418c-p106">The following Windows Updates are installed. Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="4418c-151">Para Windows 10 1809 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="4418c-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="4418c-152">Para Windows 10 1903 ou 1909 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="4418c-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="4418c-153">Para Windows 10 2004 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="4418c-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="4418c-154">Para dispositivos que executam o Office 2016 (e nenhuma outra versão do Office) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="4418c-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="4418c-155">Todos os dispositivos devem ser associados ao [Azure Active Directory (Microsoft Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) ou ingressado no Azure AD Híbrido.</span><span class="sxs-lookup"><span data-stu-id="4418c-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="4418c-p107">Instale o navegador Microsoft Chromium Edge no dispositivo do ponto de extremidade para impor ações de política para o upload para a atividade na nuvem. Confira, [Baixe o novo Microsoft Edge baseado no Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="4418c-p107">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="4418c-p108">Se você estiver no Canal Empresarial Mensal do Microsoft 365 Apps versões 2004-2008, há um problema conhecido com a Prevenção contra perda de dados do Ponto de extremidade classificando o conteúdo do Office e você precisa atualizar para a versão 2009 ou posterior. Confira [Histórico de atualizações para aplicativos do Microsoft 365 (listados por data)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) para as versões atuais. Para saber mais sobre esse problema, confira a seção do pacote do Office de [Notas de versão para lançamentos do Canal Atual em 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="4418c-p108">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="4418c-161">Dispositivos de integração no gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="4418c-161">Onboarding devices into device management</span></span>

<span data-ttu-id="4418c-p109">Você deve habilitar o monitoramento de dispositivo e integrar os seus pontos de extremidade antes de monitorar e proteger itens confidenciais em um dispositivo. Ambas as ações são realizadas no portal de Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4418c-p109">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="4418c-p110">Quando quiser integrar dispositivos que ainda não foram integrados, você fará o download do script apropriado e o implantará nesses dispositivos. Siga o [Procedimento de dispositivos integrados](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="4418c-p110">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="4418c-p111">Se você já tiver dispositivos integrados ao [Microsoft Defender para Ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/), eles já aparecerão na lista de dispositivos gerenciados. Siga o [Procedimento Com dispositivos integrados ao Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="4418c-p111">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="4418c-168">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="4418c-168">Onboarding devices</span></span>

<span data-ttu-id="4418c-169">Neste cenário de implantação, você integrará dispositivos que ainda não foram integrados e você só deseja monitorar e proteger itens confidenciais contra compartilhamento não intencional em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4418c-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="4418c-170">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4418c-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="4418c-171">Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="4418c-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4418c-172">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="4418c-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="4418c-173">Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4418c-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="4418c-p112">Escolha **Gerenciamento de dispositivos** para abrir a lista de **Dispositivos**. A lista ficará vazia até você integrar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4418c-p112">Choose **Device management** to open the **Devices** list. The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="4418c-176">Escolha **Integração** para iniciar o processo de integração.</span><span class="sxs-lookup"><span data-stu-id="4418c-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="4418c-177">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="4418c-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4418c-178">![método de implantação](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="4418c-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="4418c-p113">Siga os procedimentos apropriados em [Ferramentas e métodos de integração para máquinas com Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link o leva a uma página de aterrissagem onde você pode acessar os procedimentos do Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="4418c-p113">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="4418c-181">Integrar computadores com Windows 10 usando uma Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="4418c-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="4418c-182">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4418c-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="4418c-183">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="4418c-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="4418c-184">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="4418c-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="4418c-185">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="4418c-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="4418c-186">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na lista dispositivos e começar a relatar logs de atividades de auditoria para o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="4418c-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="4418c-p114">Esta experiência está sob a aplicação de licença. Sem a licença necessária, os dados não estarão visíveis ou acessíveis.</span><span class="sxs-lookup"><span data-stu-id="4418c-p114">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="4418c-189">Com dispositivos integrados do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4418c-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="4418c-p115">Nesse cenário, o Proteção Avançada contra Ameaças do Microsoft Defender já está implantado e há relatórios de pontos de extremidade. Todos esses pontos de extremidade aparecerão na lista de dispositivos gerenciados. Você pode continuar a integrar novos dispositivos na Prevenção contra perda de dados do Ponto de extremidade para expandir a cobertura usando o [Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="4418c-p115">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="4418c-193">Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4418c-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="4418c-194">Abra a página de configurações do Centro de Conformidade e escolha **Habilitar o monitoramento de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="4418c-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="4418c-p116">Escolha **Gerenciamento de dispositivos** para abrir a lista de **Dispositivos**. Você deve ver a lista de dispositivos que já estão se relatando ao Proteção Avançada contra Ameaças do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4418c-p116">Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4418c-197">![gerenciamento de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="4418c-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="4418c-198">Escolha **Integração**, caso precise integrar dispositivos adicionais.</span><span class="sxs-lookup"><span data-stu-id="4418c-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="4418c-199">Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.</span><span class="sxs-lookup"><span data-stu-id="4418c-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="4418c-p117">Siga os procedimentos apropriados em [Ferramentas e métodos de integração para máquinas com Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link o leva a uma página de aterrissagem onde você pode acessar os procedimentos do Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:</span><span class="sxs-lookup"><span data-stu-id="4418c-p117">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="4418c-202">Integrar computadores com Windows 10 usando uma Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="4418c-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="4418c-203">Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4418c-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="4418c-204">Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="4418c-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="4418c-205">Integrar computadores com Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="4418c-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="4418c-206">Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).</span><span class="sxs-lookup"><span data-stu-id="4418c-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="4418c-207">Uma vez que o ponto de extremidade está integrado, ele deve estar visível na tabela **Dispositivos** e começar a relatar logs de atividades de auditoria para o **Explorador de atividades**.</span><span class="sxs-lookup"><span data-stu-id="4418c-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="4418c-p118">Esta experiência está sob a aplicação de licença. Sem a licença necessária, os dados não estarão visíveis ou acessíveis.</span><span class="sxs-lookup"><span data-stu-id="4418c-p118">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="4418c-210">Exibir alertas de Prevenção contra perda de dados (DLP) do Ponto de extremidade no painel de Gerenciamento de Alertas da Prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="4418c-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="4418c-211">Abra a Página de prevenção contra perda de dados no Centro de conformidade do Microsoft 365 e escolha Alertas.</span><span class="sxs-lookup"><span data-stu-id="4418c-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="4418c-212">Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4418c-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="4418c-213">Exibir dados de DLP do ponto de extremidade no explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="4418c-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="4418c-214">Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) do seu domínio no Centro de conformidade do Microsoft 365 e escolha o Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="4418c-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="4418c-215">Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4418c-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4418c-216">![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="4418c-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="4418c-217">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="4418c-217">Next steps</span></span>
<span data-ttu-id="4418c-218">Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="4418c-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="4418c-219">Usando a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="4418c-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="4418c-220">Confira também</span><span class="sxs-lookup"><span data-stu-id="4418c-220">See also</span></span>

- [<span data-ttu-id="4418c-221">Saiba mais sobre a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="4418c-221">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="4418c-222">Usando a prevenção contra perda de dados do EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="4418c-222">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="4418c-223">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="4418c-223">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4418c-224">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="4418c-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4418c-225">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="4418c-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4418c-226">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4418c-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="4418c-227">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="4418c-227">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="4418c-228">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4418c-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="4418c-229">Dispositivos associados ao Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="4418c-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="4418c-230">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="4418c-230">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
