---
title: Habilitar o bloqueio à primeira vista para detectar malware em segundos
description: A turn on the block at first sight feature to detect and block malware within seconds.
keywords: examinar, bloquear à primeira vista, malware, primeira vista, nuvem, defender, antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079198"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="95467-104">Ativar o bloqueio à primeira vista</span><span class="sxs-lookup"><span data-stu-id="95467-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95467-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="95467-105">**Applies to:**</span></span>

- [<span data-ttu-id="95467-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="95467-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="95467-107">Este artigo descreve um recurso antivírus/antimalware conhecido como "bloquear à primeira vista" e descreve como habilitar o bloqueio à primeira vista para sua organização.</span><span class="sxs-lookup"><span data-stu-id="95467-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="95467-108">Este artigo destina-se a administradores corporativos e profissionais de IT que gerenciam configurações de segurança para organizações.</span><span class="sxs-lookup"><span data-stu-id="95467-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="95467-109">Se você não for um administrador enteprise ou profissional de TI, mas tiver dúvidas sobre bloquear à primeira vista, consulte [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="95467-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="95467-110">O que é "bloquear à primeira vista"?</span><span class="sxs-lookup"><span data-stu-id="95467-110">What is "block at first sight"?</span></span>

<span data-ttu-id="95467-111">Bloquear à primeira vista é um recurso de proteção contra ameaças da proteção de próxima geração que detecta o novo malware e o bloqueia em segundos.</span><span class="sxs-lookup"><span data-stu-id="95467-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="95467-112">O bloqueio à primeira vista é habilitado quando determinadas configurações de segurança estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="95467-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="95467-113">Essas configurações incluem:</span><span class="sxs-lookup"><span data-stu-id="95467-113">These settings include:</span></span>

- <span data-ttu-id="95467-114">Proteção entregue na nuvem;</span><span class="sxs-lookup"><span data-stu-id="95467-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="95467-115">Um tempo de tempo de envio de amostra especificado (como 50 segundos); e</span><span class="sxs-lookup"><span data-stu-id="95467-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="95467-116">Um nível de bloqueio de arquivo alto.</span><span class="sxs-lookup"><span data-stu-id="95467-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="95467-117">Na maioria das organizações corporativas, as configurações necessárias para habilitar o bloqueio à primeira vista são configuradas com implantações do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="95467-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="95467-118">Como funciona</span><span class="sxs-lookup"><span data-stu-id="95467-118">How it works</span></span>

<span data-ttu-id="95467-119">Quando o Microsoft Defender Antivírus encontra um arquivo suspeito, mas não detectado, ele consulta nosso back-end de proteção de nuvem.</span><span class="sxs-lookup"><span data-stu-id="95467-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="95467-120">O back-back da nuvem aplica heurística, aprendizado de máquina e análise automatizada do arquivo para determinar se os arquivos são mal-intencionados ou não uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="95467-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="95467-121">O Microsoft Defender Antivírus usa várias tecnologias de detecção e prevenção para oferecer proteção precisa, inteligente e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="95467-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lista de mecanismos do Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="95467-123">Para saber mais, confira este blog: Conheça as tecnologias avançadas no núcleo do [Microsoft Defender para Endpoint de proteção de próxima geração.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="95467-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="95467-124">Algumas coisas a saber sobre bloqueio à primeira vista</span><span class="sxs-lookup"><span data-stu-id="95467-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="95467-125">No Windows 10, versão 1803 ou posterior, o bloqueio à primeira vista pode bloquear arquivos executáveis não portáteis (como JS, VBS ou macros) e arquivos executáveis.</span><span class="sxs-lookup"><span data-stu-id="95467-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="95467-126">O bloqueio à primeira vista usa apenas o back-end de proteção de nuvem para arquivos executáveis e arquivos executáveis não portáteis baixados da Internet ou que se originam da zona da Internet.</span><span class="sxs-lookup"><span data-stu-id="95467-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="95467-127">Um valor de hash do arquivo .exe é verificado por meio do back-end da nuvem para determinar se o arquivo é um arquivo não detectado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="95467-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="95467-128">Se o back-back da nuvem não puder fazer uma determinação, o Microsoft Defender Antivírus bloqueia o arquivo e carrega uma cópia na nuvem.</span><span class="sxs-lookup"><span data-stu-id="95467-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="95467-129">A nuvem executa mais análises para alcançar uma determinação antes de permitir que o arquivo seja executado ou o bloqueia em todos os futuros encontros, dependendo de determinar se o arquivo é mal-intencionado ou não uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="95467-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="95467-130">Em muitos casos, esse processo pode reduzir o tempo de resposta para o novo malware de horas para segundos.</span><span class="sxs-lookup"><span data-stu-id="95467-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="95467-131">Você pode [especificar por quanto tempo um arquivo deve ser](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) impedido de ser executado enquanto o serviço de proteção baseado em nuvem analisa o arquivo.</span><span class="sxs-lookup"><span data-stu-id="95467-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="95467-132">E, você pode [personalizar a mensagem exibida nos desktops dos](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) usuários quando um arquivo é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="95467-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="95467-133">Você pode alterar o nome da empresa, as informações de contato e a URL da mensagem.</span><span class="sxs-lookup"><span data-stu-id="95467-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="95467-134">Ativar bloqueio à primeira vista com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="95467-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="95467-135">O Microsoft Intune agora faz parte do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="95467-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="95467-136">No Centro de administração do Microsoft Endpoint Manager ( ), navegue até [https://endpoint.microsoft.com](https://endpoint.microsoft.com) **Perfis**  >  **de Configuração de Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="95467-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="95467-137">Selecione ou crie um perfil usando o tipo **de perfil restrições** de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95467-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="95467-138">Nas **configurações do** perfil restrições de dispositivo, de definir ou confirmar as seguintes configurações em **Microsoft Defender Antivírus**:</span><span class="sxs-lookup"><span data-stu-id="95467-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="95467-139">**Proteção entregue na nuvem**: Habilitada</span><span class="sxs-lookup"><span data-stu-id="95467-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="95467-140">**Nível de bloqueio de arquivos**: alto</span><span class="sxs-lookup"><span data-stu-id="95467-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="95467-141">**Extensão de tempo para verificação de arquivos pela nuvem**: 50</span><span class="sxs-lookup"><span data-stu-id="95467-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="95467-142">**Solicitar aos usuários antes do envio de exemplo**: Enviar todos os dados sem solicitar</span><span class="sxs-lookup"><span data-stu-id="95467-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Config do Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="95467-144">Salve suas configurações.</span><span class="sxs-lookup"><span data-stu-id="95467-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="95467-145">Definir o nível de bloqueio de arquivo **como Alto** aplica um nível forte de detecção.</span><span class="sxs-lookup"><span data-stu-id="95467-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="95467-146">No caso improvável de que o bloqueio de arquivos cause uma detecção de falsos positivos de arquivos legítimos, sua equipe de operações de segurança [poderá restaurar arquivos em quarentena.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="95467-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="95467-147">Para obter mais informações sobre como configurar restrições de dispositivo do Microsoft Defender Antivírus no Intune, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="95467-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="95467-148">Para ver uma lista de restrições de dispositivo do Microsoft Defender Antivírus no Intune, consulte Restrição de dispositivo para configurações do [Windows 10 (e mais novas) no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="95467-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="95467-149">Ativar o bloqueio à primeira vista com o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="95467-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="95467-150">Se você estiver procurando o Microsoft Endpoint Configuration Manager, ele agora faz parte do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="95467-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="95467-151">No Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), acesse **Endpoint security**  >  **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="95467-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="95467-152">Selecione uma política existente ou crie uma nova política usando o tipo de **perfil do Microsoft Defender Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="95467-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="95467-153">De definir ou confirmar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95467-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="95467-154">**Ativar a proteção entregue na nuvem**: Sim</span><span class="sxs-lookup"><span data-stu-id="95467-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="95467-155">**Nível de proteção entregue na nuvem**: Alto</span><span class="sxs-lookup"><span data-stu-id="95467-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="95467-156">**Tempo de tempo estendido da** nuvem do Defender em segundos : 50</span><span class="sxs-lookup"><span data-stu-id="95467-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloquear as configurações à primeira vista no Endpoint Manager":::

4. <span data-ttu-id="95467-158">Aplique o perfil do Microsoft Defender Antivírus a um grupo, como **Todos** os usuários , **Todos** os dispositivos ou **Todos os usuários e dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="95467-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="95467-159">Ativar o bloqueio à primeira vista com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="95467-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="95467-160">Recomendamos usar o Intune ou o Microsoft Endpoint Manager para ativar o bloqueio à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="95467-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="95467-161">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="95467-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="95467-162">Usando o **Editor de Gerenciamento de Política de Grupo,** acesse **Configuração** do computador  >  **Modelos administrativos**  >  **Componentes do Windows** Microsoft Defender  >    >  **Antivírus MAPS**.</span><span class="sxs-lookup"><span data-stu-id="95467-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="95467-163">Na seção MAPAs, clique duas vezes em Configurar o recurso **"Bloquear** à Primeira Vista", des configurá-lo como Habilitado **e** selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="95467-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="95467-164">A **configuração como Sempre prompt (0)** diminuirá o estado de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95467-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="95467-165">Definir como **Nunca enviar (2)** significa que o bloqueio à primeira vista não funcionará.</span><span class="sxs-lookup"><span data-stu-id="95467-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="95467-166">Na seção MAPAs, clique duas vezes em **Enviar amostras** de arquivo quando outra análise for necessária e desdeixá-la **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="95467-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="95467-167">Em **Enviar amostras de arquivo quando uma análise** posterior for necessária, selecione Enviar todos os **exemplos** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="95467-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="95467-168">Reimplante seu Objeto de Política de Grupo em sua rede como normalmente faz.</span><span class="sxs-lookup"><span data-stu-id="95467-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="95467-169">Confirmar que o bloqueio à primeira vista está habilitado em dispositivos cliente individuais</span><span class="sxs-lookup"><span data-stu-id="95467-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="95467-170">Você pode confirmar que o bloqueio à primeira vista está habilitado em dispositivos cliente individuais usando o aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="95467-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="95467-171">O bloqueio à primeira vista é  habilitado automaticamente, desde que a proteção entregue na nuvem e o envio **automático** de exemplo sejam ativados.</span><span class="sxs-lookup"><span data-stu-id="95467-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="95467-172">Abra o aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="95467-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="95467-173">Selecione **Proteção contra &** contra vírus e, em Configurações de proteção contra & vírus, selecione Gerenciar **Configurações**. </span><span class="sxs-lookup"><span data-stu-id="95467-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="95467-175">Confirme se **a proteção entregue na nuvem** e o envio **automático** de exemplo estão ambos a ligado.</span><span class="sxs-lookup"><span data-stu-id="95467-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="95467-176">Se as configurações de pré-requisitos são configuradas e implantadas usando a Política de Grupo, as configurações descritas nesta seção serão acinzenadas e indisponíveis para uso em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="95467-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="95467-177">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas Configurações do Windows.</span><span class="sxs-lookup"><span data-stu-id="95467-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="95467-178">Validar bloco à primeira vista está funcionando</span><span class="sxs-lookup"><span data-stu-id="95467-178">Validate block at first sight is working</span></span>

<span data-ttu-id="95467-179">Para validar se o recurso está funcionando, siga as orientações em Validar conexões [entre sua rede e a nuvem](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="95467-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="95467-180">Desativar o bloco à primeira vista</span><span class="sxs-lookup"><span data-stu-id="95467-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="95467-181">Desligar o bloco à primeira vista diminuirá o estado de proteção de seus dispositivos e de sua rede.</span><span class="sxs-lookup"><span data-stu-id="95467-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="95467-182">Você pode optar por desabilitar o bloqueio à primeira vista se quiser manter as configurações de pré-requisito sem realmente usar a proteção de bloqueio à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="95467-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="95467-183">Você pode desativar temporariamente o bloqueio à primeira vista para ver como esse recurso afeta sua rede.</span><span class="sxs-lookup"><span data-stu-id="95467-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="95467-184">No entanto, não recomendamos desabilitar o bloco à primeira vista permanentemente.</span><span class="sxs-lookup"><span data-stu-id="95467-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="95467-185">Desativar o bloco à primeira vista com o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="95467-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="95467-186">Vá para o Centro de administração do Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="95467-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="95467-187">Vá para **o Antivírus de segurança** do ponto de extremidade e selecione sua política do Microsoft Defender  >  Antivírus.</span><span class="sxs-lookup"><span data-stu-id="95467-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="95467-188">Em **Gerenciar**, escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="95467-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="95467-189">Ao lado **das configurações,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="95467-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="95467-190">Altere uma ou mais das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95467-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="95467-191">Definir **Ativar a proteção entregue na nuvem** como **Não** ou **Não configurado.**</span><span class="sxs-lookup"><span data-stu-id="95467-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="95467-192">Definir **o nível de proteção entregue na nuvem** como Não **configurado**.</span><span class="sxs-lookup"><span data-stu-id="95467-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="95467-193">Desacordo a caixa de seleção **para o Tempo Decoro** Estendido da Nuvem do Defender em Segundos.</span><span class="sxs-lookup"><span data-stu-id="95467-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="95467-194">Revise e salve suas configurações.</span><span class="sxs-lookup"><span data-stu-id="95467-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="95467-195">Desativar o bloco à primeira vista com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="95467-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="95467-196">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="95467-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="95467-197">Usando o **Editor de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos**.</span><span class="sxs-lookup"><span data-stu-id="95467-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="95467-198">Expanda a árvore por meio **de componentes do Windows** Microsoft Defender  >    >  **Antivírus MAPS**.</span><span class="sxs-lookup"><span data-stu-id="95467-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="95467-199">Clique duas vezes **em Configurar o recurso "Bloquear à Primeira Vista"** e de definir a opção como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="95467-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95467-200">Desabilitar o bloco à primeira vista não desabilita ou altera as políticas de grupo de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="95467-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="95467-201">Não é um administrador empresarial ou um profissional de IT?</span><span class="sxs-lookup"><span data-stu-id="95467-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="95467-202">Se você não for um administrador corporativo ou profissional de TI, mas tiver dúvidas sobre bloquear à primeira vista, esta seção será para você.</span><span class="sxs-lookup"><span data-stu-id="95467-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="95467-203">Bloquear à primeira vista é um recurso de proteção contra ameaças que detecta e bloqueia malware em segundos.</span><span class="sxs-lookup"><span data-stu-id="95467-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="95467-204">Embora não haja uma configuração específica chamada "Bloquear à primeira vista", o recurso é habilitado quando determinadas configurações são configuradas em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95467-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="95467-205">Como gerenciar o bloqueio à primeira vista em seu próprio dispositivo</span><span class="sxs-lookup"><span data-stu-id="95467-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="95467-206">Se você tiver um dispositivo pessoal que não seja gerenciado por uma organização, você pode estar se perguntando como ativar ou desativar o bloqueio à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="95467-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="95467-207">Você pode usar o aplicativo segurança do Windows para gerenciar o bloqueio à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="95467-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="95467-208">No computador com Windows 10, abra o aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="95467-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="95467-209">Selecione **Proteção contra & contra ameaças.**</span><span class="sxs-lookup"><span data-stu-id="95467-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="95467-210">Em **Configurações & proteção contra vírus,** selecione **Gerenciar configurações**.</span><span class="sxs-lookup"><span data-stu-id="95467-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="95467-211">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="95467-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="95467-212">Para habilitar o bloqueio à primeira vista, **certifique-se** de que a proteção entregue na nuvem e o envio **automático** de exemplo estão ativados.</span><span class="sxs-lookup"><span data-stu-id="95467-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="95467-213">Para desabilitar o bloqueio à primeira vista, desative a **proteção entregue na nuvem** ou **o envio automático de amostra.**</span><span class="sxs-lookup"><span data-stu-id="95467-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="95467-214">Desligar o bloco à primeira vista reduz o nível de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95467-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="95467-215">Não é recomendável desabilitar permanentemente o bloco à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="95467-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="95467-216">Confira também</span><span class="sxs-lookup"><span data-stu-id="95467-216">See also</span></span>

- [<span data-ttu-id="95467-217">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="95467-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="95467-218">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="95467-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95467-219">Mantenha-se protegido com o Windows Security</span><span class="sxs-lookup"><span data-stu-id="95467-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)