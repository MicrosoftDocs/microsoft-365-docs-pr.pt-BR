---
title: Habilitar o bloqueio à primeira vista para detectar malware em segundos
description: A turn on the block at first sight feature to detect and block malware within seconds.
keywords: scan, BAFS, malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765750"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="42954-104">Ativar o bloqueio à primeira vista</span><span class="sxs-lookup"><span data-stu-id="42954-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="42954-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="42954-105">**Applies to:**</span></span>

- [<span data-ttu-id="42954-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="42954-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="42954-107">Bloquear à primeira vista fornece uma maneira de detectar e bloquear um novo malware em segundos.</span><span class="sxs-lookup"><span data-stu-id="42954-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="42954-108">Essa proteção é habilitada por padrão quando determinadas configurações de pré-requisito estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="42954-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="42954-109">Essas configurações incluem proteção entregue na nuvem, um tempo máximo de envio de amostra especificado (como 50 segundos) e um nível alto de bloqueio de arquivos.</span><span class="sxs-lookup"><span data-stu-id="42954-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="42954-110">Na maioria das organizações corporativas, essas configurações são habilitadas por padrão com implantações do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="42954-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="42954-111">Você pode [especificar por quanto tempo um arquivo deve ser](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) impedido de ser executado enquanto o serviço de proteção baseado em nuvem analisa o arquivo.</span><span class="sxs-lookup"><span data-stu-id="42954-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="42954-112">E, você pode [personalizar a mensagem exibida nos desktops dos](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) usuários quando um arquivo é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="42954-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="42954-113">Você pode alterar o nome da empresa, as informações de contato e a URL da mensagem.</span><span class="sxs-lookup"><span data-stu-id="42954-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="42954-114">Visite o site de demonstração do Microsoft Defender para Ponto de Extremidade [no](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com para confirmar se os recursos estão funcionando e ver como eles funcionam.</span><span class="sxs-lookup"><span data-stu-id="42954-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="42954-115">Como funciona</span><span class="sxs-lookup"><span data-stu-id="42954-115">How it works</span></span>

<span data-ttu-id="42954-116">Quando o Microsoft Defender Antivírus encontra um arquivo suspeito, mas não detectado, ele consulta nosso back-end de proteção de nuvem.</span><span class="sxs-lookup"><span data-stu-id="42954-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="42954-117">O back-back da nuvem aplica heurística, aprendizado de máquina e análise automatizada do arquivo para determinar se os arquivos são mal-intencionados ou não uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="42954-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="42954-118">O Microsoft Defender Antivírus usa várias tecnologias de detecção e prevenção para oferecer proteção precisa, inteligente e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="42954-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="42954-119">Para saber mais, confira este blog: Conheça as tecnologias avançadas no núcleo do [Microsoft Defender para Endpoint de proteção de próxima geração.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="42954-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="42954-120">![Lista de mecanismos do Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="42954-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="42954-121">No Windows 10, versão 1803 ou posterior, o bloqueio à primeira vista pode bloquear arquivos executáveis não portáteis (como JS, VBS ou macros), bem como arquivos executáveis.</span><span class="sxs-lookup"><span data-stu-id="42954-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="42954-122">O bloqueio à primeira vista usa apenas o back-end de proteção de nuvem para arquivos executáveis e arquivos executáveis não portáteis baixados da Internet ou que se originam da zona da Internet.</span><span class="sxs-lookup"><span data-stu-id="42954-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="42954-123">Um valor de hash do arquivo .exe é verificado por meio do back-end da nuvem para determinar se o arquivo é um arquivo não detectado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="42954-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="42954-124">Se o back-back da nuvem não puder fazer uma determinação, o Microsoft Defender Antivírus bloqueia o arquivo e carrega uma cópia na nuvem.</span><span class="sxs-lookup"><span data-stu-id="42954-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="42954-125">A nuvem executa análises adicionais para chegar a uma determinação antes de permitir que o arquivo seja executado ou o bloqueia em todos os futuros encontros, dependendo de determinar se o arquivo é mal-intencionado ou seguro.</span><span class="sxs-lookup"><span data-stu-id="42954-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="42954-126">Em muitos casos, esse processo pode reduzir o tempo de resposta para o novo malware de horas para segundos.</span><span class="sxs-lookup"><span data-stu-id="42954-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="42954-127">Ativar bloqueio à primeira vista com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="42954-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="42954-128">O Microsoft Intune agora faz parte do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="42954-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="42954-129">No Centro de administração do Microsoft Endpoint Manager ( ), navegue até [https://endpoint.microsoft.com](https://endpoint.microsoft.com) **Perfis**  >  **de Configuração de Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="42954-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="42954-130">Selecione ou crie um perfil usando o tipo **de perfil restrições** de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42954-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="42954-131">Nas **configurações do** perfil restrições de dispositivo, de definir ou confirmar as seguintes configurações em **Microsoft Defender Antivírus**:</span><span class="sxs-lookup"><span data-stu-id="42954-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="42954-132">**Proteção entregue na nuvem**: Habilitada</span><span class="sxs-lookup"><span data-stu-id="42954-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="42954-133">**Nível de bloqueio de arquivos**: alto</span><span class="sxs-lookup"><span data-stu-id="42954-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="42954-134">**Extensão de tempo para verificação de arquivos pela nuvem**: 50</span><span class="sxs-lookup"><span data-stu-id="42954-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="42954-135">**Solicitar aos usuários antes do envio de exemplo**: Enviar todos os dados sem solicitar</span><span class="sxs-lookup"><span data-stu-id="42954-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Config do Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="42954-137">Salve suas configurações.</span><span class="sxs-lookup"><span data-stu-id="42954-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="42954-138">Definir o nível de bloqueio de arquivo **como Alto** aplica um nível forte de detecção.</span><span class="sxs-lookup"><span data-stu-id="42954-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="42954-139">No caso improvável de que o bloqueio de arquivos cause uma detecção de falsos positivos de arquivos legítimos, você pode [restaurar arquivos em quarentena.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="42954-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="42954-140">Para obter mais informações sobre como configurar restrições de dispositivo do Microsoft Defender Antivírus no Intune, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="42954-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="42954-141">Para ver uma lista de restrições de dispositivo do Microsoft Defender Antivírus no Intune, consulte Restrição de dispositivo para configurações do [Windows 10 (e mais novas) no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="42954-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="42954-142">Ativar o bloqueio à primeira vista com o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="42954-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="42954-143">Se você estiver procurando o Microsoft Endpoint Configuration Manager, ele agora faz parte do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="42954-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="42954-144">No Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), acesse **Endpoint security**  >  **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="42954-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="42954-145">Selecione uma política existente ou crie uma nova política usando o tipo de **perfil do Microsoft Defender Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="42954-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="42954-146">De definir ou confirmar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="42954-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="42954-147">**Ativar a proteção entregue na nuvem**: Sim</span><span class="sxs-lookup"><span data-stu-id="42954-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="42954-148">**Nível de proteção entregue na nuvem**: Alto</span><span class="sxs-lookup"><span data-stu-id="42954-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="42954-149">**Tempo de tempo estendido da** nuvem do Defender em segundos : 50</span><span class="sxs-lookup"><span data-stu-id="42954-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloquear as configurações à primeira vista no Endpoint Manager":::

4. <span data-ttu-id="42954-151">Aplique o perfil do Microsoft Defender Antivírus a um grupo, como **Todos** os usuários , **Todos** os dispositivos ou **Todos os usuários e dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="42954-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="42954-152">Ativar o bloqueio à primeira vista com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="42954-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="42954-153">Recomendamos usar o Intune ou o Microsoft Endpoint Manager para ativar o bloqueio à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="42954-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="42954-154">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="42954-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="42954-155">Usando o **Editor de Gerenciamento de Política de Grupo,** acesse **Configuração** do computador  >  **Modelos administrativos**  >  **Componentes do Windows** Microsoft Defender  >    >  **Antivírus MAPS**.</span><span class="sxs-lookup"><span data-stu-id="42954-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="42954-156">Na seção MAPAs, clique duas vezes em Configurar o recurso **"Bloquear** à Primeira Vista", des configurá-lo como Habilitado **e** selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="42954-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="42954-157">A **configuração como Sempre prompt (0)** diminuirá o estado de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42954-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="42954-158">Definir como **Nunca enviar (2)** significa que o bloqueio à primeira vista não funcionará.</span><span class="sxs-lookup"><span data-stu-id="42954-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="42954-159">Na seção MAPAs, clique duas vezes em **Enviar amostras** de arquivo quando outra análise for necessária e desdeixá-la **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="42954-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="42954-160">Em **Enviar amostras de arquivo quando uma análise** posterior for necessária, selecione Enviar todos os **exemplos** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42954-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="42954-161">Se você tiver alterado qualquer configuração, reimplante o Objeto de Política de Grupo em toda a rede para garantir que todos os pontos de extremidade sejam cobertos.</span><span class="sxs-lookup"><span data-stu-id="42954-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="42954-162">Confirmar que o bloqueio à primeira vista está habilitado em clientes individuais</span><span class="sxs-lookup"><span data-stu-id="42954-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="42954-163">Você pode confirmar que o bloqueio à primeira vista está habilitado em clientes individuais usando configurações de segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="42954-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="42954-164">O bloqueio à primeira vista é  habilitado automaticamente, desde que a proteção entregue na nuvem e o envio **automático** de exemplo sejam ativados.</span><span class="sxs-lookup"><span data-stu-id="42954-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="42954-165">Abra o aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="42954-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="42954-166">Selecione **Proteção contra &** contra vírus e, em Configurações de proteção contra & vírus, selecione Gerenciar **Configurações**. </span><span class="sxs-lookup"><span data-stu-id="42954-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="42954-168">Confirme se **a proteção entregue na nuvem** e o envio **automático** de exemplo estão ambos a ligado.</span><span class="sxs-lookup"><span data-stu-id="42954-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="42954-169">Se as configurações de pré-requisitos são configuradas e implantadas usando a Política de Grupo, as configurações descritas nesta seção serão acinzenadas e indisponíveis para uso em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="42954-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="42954-170">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas Configurações do Windows.</span><span class="sxs-lookup"><span data-stu-id="42954-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="42954-171">Validar bloco à primeira vista está funcionando</span><span class="sxs-lookup"><span data-stu-id="42954-171">Validate block at first sight is working</span></span>

<span data-ttu-id="42954-172">Para validar se o recurso está funcionando, siga as orientações em Validar conexões [entre sua rede e a nuvem](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="42954-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="42954-173">Desativar o bloco à primeira vista</span><span class="sxs-lookup"><span data-stu-id="42954-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="42954-174">Desligar o bloco à primeira vista diminuirá o estado de proteção de seus dispositivos e de sua rede.</span><span class="sxs-lookup"><span data-stu-id="42954-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="42954-175">Você pode optar por desabilitar o bloqueio à primeira vista se quiser manter as configurações de pré-requisito sem realmente usar a proteção de bloqueio à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="42954-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="42954-176">Você pode desativar temporariamente o bloqueio à primeira vista se estiver enfrentando problemas de latência ou quiser testar o impacto do recurso em sua rede.</span><span class="sxs-lookup"><span data-stu-id="42954-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="42954-177">No entanto, não recomendamos desabilitar o bloco à primeira vista permanentemente.</span><span class="sxs-lookup"><span data-stu-id="42954-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="42954-178">Desativar o bloco à primeira vista com o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="42954-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="42954-179">Vá para o Centro de administração do Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="42954-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="42954-180">Vá para **o Antivírus de segurança** do ponto de extremidade e selecione sua política do Microsoft Defender  >  Antivírus.</span><span class="sxs-lookup"><span data-stu-id="42954-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="42954-181">Em **Gerenciar**, escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="42954-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="42954-182">Ao lado **das configurações,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="42954-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="42954-183">Altere uma ou mais das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="42954-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="42954-184">Definir **Ativar a proteção entregue na nuvem** como **Não** ou **Não configurado.**</span><span class="sxs-lookup"><span data-stu-id="42954-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="42954-185">Definir **o nível de proteção entregue na nuvem** como Não **configurado**.</span><span class="sxs-lookup"><span data-stu-id="42954-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="42954-186">Limpe a **caixa Tempo Decoro Estendido da** Nuvem do Defender em Segundos.</span><span class="sxs-lookup"><span data-stu-id="42954-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="42954-187">Revise e salve suas configurações.</span><span class="sxs-lookup"><span data-stu-id="42954-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="42954-188">Desativar o bloco à primeira vista com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="42954-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="42954-189">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="42954-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="42954-190">Usando o **Editor de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="42954-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="42954-191">Expanda a árvore por meio **de componentes do Windows** Microsoft Defender  >    >  **Antivírus MAPS**.</span><span class="sxs-lookup"><span data-stu-id="42954-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="42954-192">Clique duas vezes **em Configurar o recurso "Bloquear à Primeira Vista"** e de definir a opção como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="42954-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42954-193">Desabilitar o bloco à primeira vista não desabilita ou altera as políticas de grupo de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="42954-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="42954-194">Confira também</span><span class="sxs-lookup"><span data-stu-id="42954-194">See also</span></span>

- [<span data-ttu-id="42954-195">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="42954-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="42954-196">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="42954-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)