---
title: Ativar proteção fornecida pela nuvem em Microsoft Defender Antivírus
description: Acotoda a proteção fornecida pela nuvem para se beneficiar de recursos de proteção rápidos e avançados.
keywords: Microsoft Defender Antivírus, antimalware, segurança, nuvem, bloco à primeira vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572052"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="dc66c-104">Ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc66c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="dc66c-105">**Applies to:**</span></span>

- [<span data-ttu-id="dc66c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="dc66c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="dc66c-107">O serviço de nuvem Microsoft Defender Antivírus é um mecanismo para fornecer proteção atualizada à sua rede e pontos finais.</span><span class="sxs-lookup"><span data-stu-id="dc66c-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="dc66c-108">Embora seja chamado de serviço de nuvem, não é simplesmente proteção para arquivos armazenados na nuvem; em vez disso, ele usa recursos distribuídos e aprendizado de máquina para fornecer proteção aos seus pontos finais a uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="dc66c-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="dc66c-109">Microsoft Defender Antivírus usa múltiplas tecnologias de detecção e prevenção para fornecer proteção precisa, em tempo real e inteligente.</span><span class="sxs-lookup"><span data-stu-id="dc66c-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="dc66c-110">[Conheça as tecnologias avançadas no núcleo do Microsoft Defender para proteção de próxima geração do Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="dc66c-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="dc66c-111">Você pode ativar ou desativar Microsoft Defender Antivírus proteção fornecida pela nuvem de várias maneiras:</span><span class="sxs-lookup"><span data-stu-id="dc66c-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="dc66c-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc66c-112">Microsoft Intune</span></span>
- <span data-ttu-id="dc66c-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dc66c-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="dc66c-114">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="dc66c-114">Group Policy</span></span>
- <span data-ttu-id="dc66c-115">Cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc66c-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="dc66c-116">Você também pode ligá-lo ou desligá-lo em clientes individuais com o aplicativo Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="dc66c-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="dc66c-117">Consulte [Use a proteção fornecida pela Nuvem da Microsoft](cloud-protection-microsoft-defender-antivirus.md) para uma visão geral da proteção fornecida pela nuvem Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="dc66c-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="dc66c-118">Para obter mais informações sobre os requisitos específicos de conectividade de rede para garantir que seus pontos finais possam se conectar ao serviço de proteção entregue à nuvem, consulte [Configurar e validar conexões de rede](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="dc66c-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dc66c-119">Em Windows 10, não há diferença entre as opções **de relatórios Básicos** e **Avançados** descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="dc66c-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="dc66c-120">Esta é uma distinção legado e escolher qualquer configuração resultará no mesmo nível de proteção fornecida pela nuvem.</span><span class="sxs-lookup"><span data-stu-id="dc66c-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="dc66c-121">Não há diferença no tipo ou quantidade de informações que são compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="dc66c-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="dc66c-122">Para obter mais informações sobre o que coletamos, consulte a [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).</span><span class="sxs-lookup"><span data-stu-id="dc66c-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dc66c-123">Use o Intune para ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="dc66c-124">Vá para o centro administrativo Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () e faça login.</span><span class="sxs-lookup"><span data-stu-id="dc66c-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="dc66c-125">No **painel Home,** selecione **Configuração do dispositivo > Perfis**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="dc66c-126">Selecione o tipo de perfil **de restrições do dispositivo** que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="dc66c-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="dc66c-127">Se você precisar criar um novo tipo de perfil **de restrições do dispositivo,** consulte [Configurar as configurações de restrição do dispositivo em Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="dc66c-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="dc66c-128">Selecione   >  **configurações de configuração de propriedades: Editar**  >  **Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="dc66c-129">No switch **de proteção entregue à Nuvem,** selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="dc66c-130">No **Prompt users antes** da submissão da amostra, selecione **Enviar todos os dados automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="dc66c-131">Para obter mais informações sobre os perfis dos dispositivos Intune, incluindo como criar e configurar suas configurações, consulte [Quais são Microsoft Intune perfis de dispositivos?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="dc66c-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dc66c-132">Use Microsoft Endpoint Manager para ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="dc66c-133">Vá para o centro administrativo Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () e faça login.</span><span class="sxs-lookup"><span data-stu-id="dc66c-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="dc66c-134">Escolha **o Antivírus de segurança endpoint**  >  .</span><span class="sxs-lookup"><span data-stu-id="dc66c-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="dc66c-135">Selecione um perfil antivírus.</span><span class="sxs-lookup"><span data-stu-id="dc66c-135">Select an antivirus profile.</span></span> <span data-ttu-id="dc66c-136">(Se você ainda não tiver um ou se quiser criar um novo perfil, consulte [Configurar as configurações de restrição do dispositivo em Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="dc66c-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="dc66c-137">Selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-137">Select **Properties**.</span></span> <span data-ttu-id="dc66c-138">Em seguida, ao lado **das configurações de configuração,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="dc66c-139">Expanda a **proteção da nuvem** e, em seguida, na lista **de nível de proteção fornecida pela Nuvem,** selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="dc66c-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="dc66c-140">**Alto:** Aplica um forte nível de detecção.</span><span class="sxs-lookup"><span data-stu-id="dc66c-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="dc66c-141">**Alto plus**: Usa o **alto** nível e aplica medidas adicionais de proteção (pode afetar o desempenho do cliente).</span><span class="sxs-lookup"><span data-stu-id="dc66c-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="dc66c-142">**Tolerância zero**: Bloqueia todos os executáveis desconhecidos.</span><span class="sxs-lookup"><span data-stu-id="dc66c-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="dc66c-143">Selecione **Review + salvar**, e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="dc66c-144">Para obter mais informações sobre a configuração Microsoft Endpoint Configuration Manager, consulte [Como criar e implantar políticas antimalware: serviço de proteção de nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="dc66c-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dc66c-145">Use a Política do Grupo para ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="dc66c-146">Em seu dispositivo de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="dc66c-147">No **Editor de Gerenciamento de Políticas de Grupo**, vá para **configuração de computador**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="dc66c-148">Selecione **modelos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="dc66c-149">Expandir a árvore para **Windows componentes > Microsoft Defender Antivírus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="dc66c-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="dc66c-150">Clique duas vezes **em "Junte-se ao Microsoft MAPS"**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="dc66c-151">Certifique-se de que a opção está ligada e definida para **MAPAS Básicos** ou **MAPAS Avançados**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="dc66c-152">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-152">Select **OK**.</span></span>

6. <span data-ttu-id="dc66c-153">Clique duas vezes **Enviar amostras de arquivos quando for necessária uma análise adicional**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="dc66c-154">Certifique-se de que a primeira opção está definida como **Habilitada** e que as outras opções estão definidas para qualquer um:</span><span class="sxs-lookup"><span data-stu-id="dc66c-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="dc66c-155">**Enviar amostras seguras** (1)</span><span class="sxs-lookup"><span data-stu-id="dc66c-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="dc66c-156">**Envie todas as amostras** (3)</span><span class="sxs-lookup"><span data-stu-id="dc66c-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="dc66c-157">A opção **Enviar amostras seguras** (1) significa que a maioria das amostras será enviada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dc66c-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="dc66c-158">Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.</span><span class="sxs-lookup"><span data-stu-id="dc66c-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="dc66c-159">Definir a opção para **Always Prompt** (0) reduzirá o estado de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc66c-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="dc66c-160">Defini-lo para **Nunca enviar** (2) significa que o recurso Block at [First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) do Microsoft Defender for Endpoint não funcionará.</span><span class="sxs-lookup"><span data-stu-id="dc66c-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="dc66c-161">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dc66c-162">Use cmdlets do PowerShell para ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="dc66c-163">Os seguintes cmdlets podem ativar a proteção fornecida pela nuvem:</span><span class="sxs-lookup"><span data-stu-id="dc66c-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="dc66c-164">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [usar cmdlets do PowerShell para configurar e executar Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e os [cmdlets Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="dc66c-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="dc66c-165">[Política CSP - Defender](/windows/client-management/mdm/policy-csp-defender) também tem mais informações especificamente sobre [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="dc66c-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="dc66c-166">Você também pode definir **-EnviarSamplesConsent** para `SendSafeSamples` (a configuração padrão) `NeverSend` ou `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="dc66c-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="dc66c-167">A `SendSafeSamples` configuração significa que a maioria das amostras será enviada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dc66c-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="dc66c-168">Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.</span><span class="sxs-lookup"><span data-stu-id="dc66c-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="dc66c-169">Configuração **-EnviarSamplesConsent** para `NeverSend` ou `AlwaysPrompt` reduzirá o nível de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc66c-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="dc66c-170">Além disso, defini-lo `NeverSend` significa que o recurso Block at First [Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) do Microsoft Defender for Endpoint não funcionará.</span><span class="sxs-lookup"><span data-stu-id="dc66c-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dc66c-171">Use o WMI (Windows Management Instruction, instrução de gerenciamento de Windows para ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="dc66c-172">Use o método [ **Definir** da](/previous-versions/windows/desktop/defender/set-msft-mppreference) classe MSFT_MpPreference para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="dc66c-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="dc66c-173">Para obter mais informações sobre parâmetros permitidos, consulte [Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="dc66c-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="dc66c-174">Acodou a proteção fornecida pela nuvem em clientes individuais com o aplicativo Segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="dc66c-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="dc66c-175">Se a **configuração local configurar para relatar** a configuração de política de grupo do Microsoft MAPS for definida como **Desativada,** então a **configuração de proteção baseada** em nuvem em Windows Configurações estará acinzentada e indisponível.</span><span class="sxs-lookup"><span data-stu-id="dc66c-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="dc66c-176">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas configurações do Windows.</span><span class="sxs-lookup"><span data-stu-id="dc66c-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="dc66c-177">Abra o aplicativo Segurança do Windows selecionando o ícone do escudo na barra de tarefas ou pesquisando no menu iniciar para **o Defender**.</span><span class="sxs-lookup"><span data-stu-id="dc66c-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="dc66c-178">Selecione o **ladrilho de proteção contra ameaças virus &** (ou o ícone do escudo na barra de menu esquerda) e, em seguida, o rótulo de **configurações de proteção contra ameaças do Vírus &:**</span><span class="sxs-lookup"><span data-stu-id="dc66c-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Captura de tela do rótulo de configurações da Proteção contra vírus e ameaças no aplicativo de segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="dc66c-180">Confirme se **a proteção baseada em nuvem** e o envio automático de **amostras** estão ligados **.**</span><span class="sxs-lookup"><span data-stu-id="dc66c-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="dc66c-181">Se o envio automático da amostra tiver sido configurado com a Política de Grupo, a configuração estará acinzentada e indisponível.</span><span class="sxs-lookup"><span data-stu-id="dc66c-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dc66c-182">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="dc66c-182">Related articles</span></span>

- [<span data-ttu-id="dc66c-183">Configurar o período de tempo limite de bloqueio da nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dc66c-184">Configurar bloco à primeira vista</span><span class="sxs-lookup"><span data-stu-id="dc66c-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dc66c-185">Usar cmdlets do PowerShell para gerenciar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="dc66c-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="dc66c-186">[Ajude a proteger Windows PCs com Endpoint Protection para Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="dc66c-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="dc66c-187">Cmdlets defensores</span><span class="sxs-lookup"><span data-stu-id="dc66c-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="dc66c-188">Use a proteção fornecida pela Microsoft em Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="dc66c-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dc66c-189">Como criar e implantar políticas antimalware: serviço de proteção à nuvem</span><span class="sxs-lookup"><span data-stu-id="dc66c-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="dc66c-190">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="dc66c-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
