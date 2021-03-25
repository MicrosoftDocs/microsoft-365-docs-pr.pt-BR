---
title: Requisitos mínimos para o Microsoft Defender para Ponto de Extremidade
description: Entenda os requisitos e requisitos de licenciamento para integração de dispositivos ao serviço
keywords: requisitos mínimos, licenciamento, tabela de comparação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c6afa48fcee80c0b8fb7ed0563264932566b6321
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185786"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="002ec-104">Requisitos mínimos para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="002ec-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="002ec-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="002ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="002ec-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="002ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="002ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="002ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="002ec-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="002ec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="002ec-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="002ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="002ec-110">Há alguns requisitos mínimos para a integração de dispositivos ao serviço.</span><span class="sxs-lookup"><span data-stu-id="002ec-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="002ec-111">Saiba mais sobre os requisitos de licenciamento, hardware e software e outras configurações para os dispositivos de integração ao serviço.</span><span class="sxs-lookup"><span data-stu-id="002ec-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="002ec-112">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="002ec-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="002ec-113">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="002ec-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="002ec-114">Saiba mais sobre os aprimoramentos mais recentes no Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="002ec-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="002ec-115">O Defender for Endpoint demonstrou recursos de detecção e ótica líderes do setor na avaliação recente do MITRE.</span><span class="sxs-lookup"><span data-stu-id="002ec-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="002ec-116">Leitura: [Insights do MITRE ATT&avaliação baseada em CK.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="002ec-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="002ec-117">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="002ec-117">Licensing requirements</span></span>
<span data-ttu-id="002ec-118">O Microsoft Defender para Ponto de Extremidade requer uma das seguintes ofertas de licenciamento por volume da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="002ec-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="002ec-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="002ec-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="002ec-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="002ec-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="002ec-121">Microsoft 365 E5 (M365 E5) que inclui o Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="002ec-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="002ec-122">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="002ec-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="002ec-123">Segurança do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="002ec-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="002ec-124">Segurança 365 A5 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="002ec-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="002ec-125">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="002ec-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-126">Os usuários licenciados qualificados podem usar o Microsoft Defender para Ponto de Extremidade em até cinco dispositivos simultâneos.</span><span class="sxs-lookup"><span data-stu-id="002ec-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="002ec-127">O Microsoft Defender para Ponto de Extremidade também está disponível para compra de um Provedor de Soluções na Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="002ec-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="002ec-128">O Microsoft Defender para Ponto de Extremidade para servidores requer uma das seguintes opções de licenciamento:</span><span class="sxs-lookup"><span data-stu-id="002ec-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="002ec-129">Centro de Segurança do Azure com o Azure Defender habilitado</span><span class="sxs-lookup"><span data-stu-id="002ec-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="002ec-130">Microsoft Defender para Ponto de Extremidade para Servidor (um por servidor coberto)</span><span class="sxs-lookup"><span data-stu-id="002ec-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-131">Os clientes podem adquirir licenças de servidor (uma por servidor coberto Ambiente do Sistema Operacional (OSE)) para o Microsoft Defender para Ponto de Extremidade para Servidores se eles têm um mínimo combinado de 50 licenças para uma ou mais das seguintes licenças de usuário:</span><span class="sxs-lookup"><span data-stu-id="002ec-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="002ec-132">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="002ec-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="002ec-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="002ec-133">Windows E5/A5</span></span>
> * <span data-ttu-id="002ec-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="002ec-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="002ec-135">Segurança do Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="002ec-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="002ec-136">Para obter informações detalhadas sobre licenciamento, consulte o [site Termos](https://www.microsoft.com/licensing/terms/) do Produto e trabalhe com sua equipe de conta para saber mais sobre os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="002ec-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="002ec-137">Para obter mais informações sobre a matriz de recursos em edições do Windows 10, consulte [Comparar edições do Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="002ec-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="002ec-138">Para uma tabela de comparação detalhada da comparação de edição comercial do Windows 10, consulte a [comparação PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span><span class="sxs-lookup"><span data-stu-id="002ec-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="002ec-139">Requisitos de navegador</span><span class="sxs-lookup"><span data-stu-id="002ec-139">Browser requirements</span></span>
<span data-ttu-id="002ec-140">O acesso ao Defender para Ponto de Extremidade é feito por meio de um navegador, suportando os seguintes navegadores:</span><span class="sxs-lookup"><span data-stu-id="002ec-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="002ec-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="002ec-141">Microsoft Edge</span></span>
- <span data-ttu-id="002ec-142">Internet Explorer versão 11</span><span class="sxs-lookup"><span data-stu-id="002ec-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="002ec-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="002ec-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-144">Embora outros navegadores possam funcionar, os navegadores mencionados são aqueles com suporte.</span><span class="sxs-lookup"><span data-stu-id="002ec-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="002ec-145">Requisitos de hardware e software</span><span class="sxs-lookup"><span data-stu-id="002ec-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="002ec-146">Versões com suporte do Windows</span><span class="sxs-lookup"><span data-stu-id="002ec-146">Supported Windows versions</span></span>
- <span data-ttu-id="002ec-147">Windows 7 SP1 Enterprise ([Requer ESU para suporte](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="002ec-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="002ec-148">Windows 7 SP1 Pro ([Requer ESU para suporte](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="002ec-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="002ec-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="002ec-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="002ec-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="002ec-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="002ec-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="002ec-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="002ec-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="002ec-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="002ec-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="002ec-153">Windows 10 Education</span></span>
- <span data-ttu-id="002ec-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="002ec-154">Windows 10 Pro</span></span>
- <span data-ttu-id="002ec-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="002ec-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="002ec-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="002ec-156">Windows server</span></span>
  - <span data-ttu-id="002ec-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="002ec-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="002ec-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="002ec-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="002ec-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="002ec-159">Windows Server 2016</span></span>
  - <span data-ttu-id="002ec-160">Windows Server, versão 1803 ou posterior</span><span class="sxs-lookup"><span data-stu-id="002ec-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="002ec-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="002ec-161">Windows Server 2019</span></span>
- <span data-ttu-id="002ec-162">Área de Trabalho Virtual do Windows</span><span class="sxs-lookup"><span data-stu-id="002ec-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="002ec-163">Os dispositivos em sua rede devem estar executando uma dessas edições.</span><span class="sxs-lookup"><span data-stu-id="002ec-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="002ec-164">Os requisitos de hardware para o Defender para Ponto de Extremidade em dispositivos são os mesmos para as edições com suporte.</span><span class="sxs-lookup"><span data-stu-id="002ec-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-165">Computadores que executam versões móveis do Windows (como Windows CE e Windows 10 Mobile) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="002ec-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="002ec-166">Máquinas virtuais que executam o Windows 10 Enterprise 2016 LTSB podem encontrar problemas de desempenho se executados em plataformas de virtualização que não são da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="002ec-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="002ec-167">Para ambientes virtuais, recomendamos usar o Windows 10 Enterprise LTSC 2019 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="002ec-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="002ec-168">Outros sistemas operacionais com suporte</span><span class="sxs-lookup"><span data-stu-id="002ec-168">Other supported operating systems</span></span>
- <span data-ttu-id="002ec-169">Android</span><span class="sxs-lookup"><span data-stu-id="002ec-169">Android</span></span>
- <span data-ttu-id="002ec-170">Linux</span><span class="sxs-lookup"><span data-stu-id="002ec-170">Linux</span></span>
- <span data-ttu-id="002ec-171">macOS</span><span class="sxs-lookup"><span data-stu-id="002ec-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-172">Você precisará saber as distribuições e versões exatas do Linux do Android e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione.</span><span class="sxs-lookup"><span data-stu-id="002ec-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="002ec-173">Requisitos de configuração e armazenamento de rede e dados</span><span class="sxs-lookup"><span data-stu-id="002ec-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="002ec-174">Ao executar o assistente de integração pela primeira vez, você deve escolher onde suas informações relacionadas ao Microsoft Defender for Endpoint estão armazenadas: na União Europeia, no Reino Unido ou no datacenter dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="002ec-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="002ec-175">Não é possível alterar o local de armazenamento de dados após a configuração pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="002ec-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="002ec-176">Revise o [Microsoft Defender para armazenamento e](data-storage-privacy.md) privacidade de dados do Ponto de Extremidade para obter mais informações sobre onde e como a Microsoft armazena seus dados.</span><span class="sxs-lookup"><span data-stu-id="002ec-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="002ec-177">Configurações de dados de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="002ec-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-178">O Microsoft Defender para Ponto de Extremidade não exige nenhum nível de diagnóstico específico, desde que ele seja habilitado.</span><span class="sxs-lookup"><span data-stu-id="002ec-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="002ec-179">Certifique-se de que o serviço de dados de diagnóstico está habilitado em todos os dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="002ec-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="002ec-180">Por padrão, esse serviço está habilitado.</span><span class="sxs-lookup"><span data-stu-id="002ec-180">By default, this service is enabled.</span></span> <span data-ttu-id="002ec-181">É uma boa prática verificar para garantir que você obterá dados do sensor deles.</span><span class="sxs-lookup"><span data-stu-id="002ec-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="002ec-182">Use a linha de comando para verificar o tipo de inicialização do serviço de dados de diagnóstico **do Windows 10:**</span><span class="sxs-lookup"><span data-stu-id="002ec-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="002ec-183">Abra um prompt de linha de comando elevada no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="002ec-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="002ec-184">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="002ec-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="002ec-185">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="002ec-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="002ec-186">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="002ec-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="002ec-187">Se o serviço estiver habilitado, o resultado deverá ter a seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="002ec-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Resultado do comando de consulta sc para diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="002ec-189">Você precisará definir o serviço para iniciar automaticamente se **o** START_TYPE não estiver definido como **AUTO_START**.</span><span class="sxs-lookup"><span data-stu-id="002ec-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="002ec-190">**Use a linha de comando para definir o serviço de dados de diagnóstico do Windows 10 para iniciar automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="002ec-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="002ec-191">Abra um prompt de linha de comando elevada no ponto de extremidade:</span><span class="sxs-lookup"><span data-stu-id="002ec-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="002ec-192">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="002ec-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="002ec-193">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="002ec-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="002ec-194">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="002ec-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="002ec-195">Uma mensagem de sucesso é exibida.</span><span class="sxs-lookup"><span data-stu-id="002ec-195">A success message is displayed.</span></span> <span data-ttu-id="002ec-196">Verifique a alteração inserindo o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="002ec-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="002ec-197">Conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="002ec-197">Internet connectivity</span></span>
<span data-ttu-id="002ec-198">A conectividade com a Internet em dispositivos é necessária diretamente ou por proxy.</span><span class="sxs-lookup"><span data-stu-id="002ec-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="002ec-199">O sensor Defender para Ponto de Extremidade pode utilizar uma largura de banda média diária de 5 MB para se comunicar com o serviço de nuvem do Defender para Ponto de Extremidade e relatar dados cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="002ec-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="002ec-200">Atividades exclusivas, como carregamentos de arquivos e conjunto de pacotes de investigação, não estão incluídas nesta largura de banda média diária.</span><span class="sxs-lookup"><span data-stu-id="002ec-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="002ec-201">Para obter mais informações sobre configurações de proxy adicionais, consulte [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="002ec-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="002ec-202">Antes de você entrar em dispositivos, o serviço de dados de diagnóstico deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="002ec-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="002ec-203">O serviço é habilitado por padrão no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="002ec-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="002ec-204">Requisito de configuração do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="002ec-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="002ec-205">O agente Defender para Ponto de Extremidade depende da capacidade do Microsoft Defender Antivírus de examinar arquivos e fornecer informações sobre eles.</span><span class="sxs-lookup"><span data-stu-id="002ec-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="002ec-206">Configure atualizações de inteligência de segurança no Defender para dispositivos de ponto de extremidade, independentemente de o Microsoft Defender Antivírus ser o antimalware ativo ou não.</span><span class="sxs-lookup"><span data-stu-id="002ec-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="002ec-207">Para obter mais informações, consulte [Manage Microsoft Defender Antivírus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="002ec-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="002ec-208">Quando o Microsoft Defender Antivírus não é o antimalware ativo em sua organização e você usa o serviço Defender para Ponto de Extremidade, o Microsoft Defender Antivírus entra no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="002ec-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="002ec-209">Se sua organização tiver desligado o Microsoft Defender Antivírus por meio de política de grupo ou outros métodos, os dispositivos que estão integrados devem ser excluídos dessa política de grupo.</span><span class="sxs-lookup"><span data-stu-id="002ec-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="002ec-210">Se você estiver integrando servidores e o Microsoft Defender Antivírus não for o antimalware ativo em seus servidores, o Microsoft Defender Antivírus precisará ser configurado para entrar no modo passivo ou desinstalado.</span><span class="sxs-lookup"><span data-stu-id="002ec-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="002ec-211">A configuração depende da versão do servidor.</span><span class="sxs-lookup"><span data-stu-id="002ec-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="002ec-212">Para obter mais informações, consulte [compatibilidade do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="002ec-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="002ec-213">Sua política de grupo regular não se aplica à Proteção contra Adulteração, e as alterações nas configurações do Microsoft Defender Antivírus serão ignoradas quando a Proteção contra Adulteração estiver em uso.</span><span class="sxs-lookup"><span data-stu-id="002ec-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="002ec-214">O driver antimalware de início antecipado do Microsoft Defender Antivírus (ELAM) está habilitado</span><span class="sxs-lookup"><span data-stu-id="002ec-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="002ec-215">Se você estiver executando o Microsoft Defender Antivírus como o produto antimalware principal em seus dispositivos, o agente Defender for Endpoint será aderido com êxito.</span><span class="sxs-lookup"><span data-stu-id="002ec-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="002ec-216">Se você estiver executando um cliente antimalware de terceiros e usar soluções de Gerenciamento de Dispositivo Móvel ou Microsoft Endpoint Manager (filial atual), você precisará garantir que o driver ELAM do Microsoft Defender Antivírus esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="002ec-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="002ec-217">Para obter mais informações, consulte [Ensure that Microsoft Defender Antivírus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="002ec-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="002ec-218">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="002ec-218">Related topics</span></span>
- [<span data-ttu-id="002ec-219">Configurar o Microsoft Defender para implantação do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="002ec-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="002ec-220">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="002ec-220">Onboard devices</span></span>](onboard-configure.md)
