---
title: Ativar a proteção entregue na nuvem em Microsoft Defender Antivírus
description: Adoe a proteção entregue na nuvem para se beneficiar dos recursos de proteção rápidos e avançados.
keywords: Microsoft Defender Antivírus, antimalware, segurança, nuvem, bloquear à primeira vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 04/30/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 5fcbd30eca3a6d0965fe65e13d2623ff54d1ff5f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114243"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="02605-104">Ativar a proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02605-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="02605-105">**Applies to:**</span></span>

- [<span data-ttu-id="02605-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="02605-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="02605-107">O Microsoft Defender Antivírus de nuvem é um mecanismo para fornecer proteção atualizada para sua rede e pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="02605-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="02605-108">Embora seja chamado de serviço de nuvem, ele não é simplesmente proteção para arquivos armazenados na nuvem; em vez disso, ele usa recursos distribuídos e aprendizado de máquina para oferecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de Inteligência de Segurança.</span><span class="sxs-lookup"><span data-stu-id="02605-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="02605-109">Microsoft Defender Antivírus usa várias tecnologias de detecção e prevenção para oferecer proteção precisa, em tempo real e inteligente.</span><span class="sxs-lookup"><span data-stu-id="02605-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="02605-110">[Conheça as tecnologias avançadas no núcleo do Microsoft Defender para Proteção](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)de próxima geração do Endpoint.</span><span class="sxs-lookup"><span data-stu-id="02605-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="02605-111">![Lista de mecanismos do Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="02605-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="02605-112">Você pode ativar ou desativar Microsoft Defender Antivírus proteção entregue na nuvem de várias maneiras:</span><span class="sxs-lookup"><span data-stu-id="02605-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="02605-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="02605-113">Microsoft Intune</span></span>
- <span data-ttu-id="02605-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="02605-114">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="02605-115">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="02605-115">Group Policy</span></span>
- <span data-ttu-id="02605-116">Cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02605-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="02605-117">Você também pode ativos ou desligados em clientes individuais com o Segurança do Windows app.</span><span class="sxs-lookup"><span data-stu-id="02605-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="02605-118">Consulte [Usar a proteção entregue na](cloud-protection-microsoft-defender-antivirus.md) nuvem da Microsoft para uma visão geral Microsoft Defender Antivírus proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="02605-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="02605-119">Para obter mais informações sobre os requisitos específicos de conectividade de rede para garantir que seus pontos de extremidade possam se conectar ao serviço de proteção entregue na nuvem, consulte [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="02605-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="02605-120">No Windows 10, não há diferença entre as  opções de relatório **Básico** e Avançado descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="02605-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="02605-121">Essa é uma distinção herdada e escolher qualquer configuração resultará no mesmo nível de proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="02605-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="02605-122">Não há diferença no tipo ou na quantidade de informações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="02605-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="02605-123">Para obter mais informações sobre o que coletamos, consulte a [Declaração de Privacidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="02605-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="02605-124">Usar o Intune para ativar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="02605-125">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.</span><span class="sxs-lookup"><span data-stu-id="02605-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="02605-126">No painel **Home,** selecione Configuração do dispositivo **> Perfis**.</span><span class="sxs-lookup"><span data-stu-id="02605-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="02605-127">Selecione o **tipo de perfil** de restrições de dispositivo que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="02605-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="02605-128">Se você precisar criar um novo tipo de perfil **de** restrições de dispositivo, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="02605-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="02605-129">Selecionar   >  **Configurações de Propriedades: Editar**  >  **Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="02605-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="02605-130">Na opção **Proteção entregue na** nuvem, selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="02605-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="02605-131">No **Prompt users before sample submission** dropdown, select Send all data **automatically**.</span><span class="sxs-lookup"><span data-stu-id="02605-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="02605-132">Para obter mais informações sobre perfis de dispositivo do Intune, incluindo como criar e configurar suas configurações, consulte O que são Microsoft Intune [de dispositivo?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="02605-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="02605-133">Usar Microsoft Endpoint Manager para ativar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="02605-134">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.</span><span class="sxs-lookup"><span data-stu-id="02605-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="02605-135">Escolha **Endpoint security**  >  **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="02605-135">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="02605-136">Selecione um perfil antivírus.</span><span class="sxs-lookup"><span data-stu-id="02605-136">Select an antivirus profile.</span></span> <span data-ttu-id="02605-137">(Se você ainda não tiver um ou se quiser criar um novo perfil, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="02605-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="02605-138">Selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="02605-138">Select **Properties**.</span></span> <span data-ttu-id="02605-139">Em seguida, ao lado **das configurações,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="02605-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="02605-140">Expanda **a proteção na** nuvem e, em seguida, na lista de níveis de proteção entregues na nuvem, selecione um dos seguintes: </span><span class="sxs-lookup"><span data-stu-id="02605-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="02605-141">**Alto**: aplica um nível forte de detecção.</span><span class="sxs-lookup"><span data-stu-id="02605-141">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="02605-142">**Alta a** mais : usa **o nível** Alto e aplica medidas de proteção adicionais (pode afetar o desempenho do cliente).</span><span class="sxs-lookup"><span data-stu-id="02605-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="02605-143">**Tolerância zero**: bloqueia todos os executáveis desconhecidos.</span><span class="sxs-lookup"><span data-stu-id="02605-143">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="02605-144">Selecione **Revisar + salvar** e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02605-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="02605-145">Para obter mais informações sobre a configuração Microsoft Endpoint Configuration Manager, consulte Como criar e implantar políticas [antimalware: serviço de proteção na nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="02605-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="02605-146">Usar a Política de Grupo para ativar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="02605-147">Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="02605-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="02605-148">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do computador**.</span><span class="sxs-lookup"><span data-stu-id="02605-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="02605-149">Selecione **Modelos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="02605-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="02605-150">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="02605-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="02605-151">Clique duas vezes em **Ingressar no Microsoft MAPS.**</span><span class="sxs-lookup"><span data-stu-id="02605-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="02605-152">Certifique-se de que a opção está configurada como **MAPAs Básicos** ou **MAPAS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="02605-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="02605-153">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="02605-153">Select **OK**.</span></span>

6. <span data-ttu-id="02605-154">Clique duas vezes em **Enviar amostras de arquivo quando uma análise posterior for necessária**.</span><span class="sxs-lookup"><span data-stu-id="02605-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="02605-155">Verifique se a primeira opção está definida como **Habilitado** e se as outras opções estão definidas como:</span><span class="sxs-lookup"><span data-stu-id="02605-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="02605-156">**Enviar amostras seguras** (1)</span><span class="sxs-lookup"><span data-stu-id="02605-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="02605-157">**Enviar todos os exemplos** (3)</span><span class="sxs-lookup"><span data-stu-id="02605-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="02605-158">A **opção Enviar amostras seguras** (1) significa que a maioria das amostras será enviada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="02605-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="02605-159">Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.</span><span class="sxs-lookup"><span data-stu-id="02605-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="02605-160">Definir a opção como **Always Prompt** (0) diminuirá o estado de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="02605-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="02605-161">Defini-lo **como Nunca enviar** (2) significa que o recurso [Bloquear](configure-block-at-first-sight-microsoft-defender-antivirus.md) à Primeira Vista do Microsoft Defender para Ponto de Extremidade não funcionará.</span><span class="sxs-lookup"><span data-stu-id="02605-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="02605-162">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="02605-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="02605-163">Usar cmdlets do PowerShell para ativar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="02605-164">Os cmdlets a seguir podem ativar a proteção entregue na nuvem:</span><span class="sxs-lookup"><span data-stu-id="02605-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="02605-165">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.</span><span class="sxs-lookup"><span data-stu-id="02605-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="02605-166">[CSP de](/windows/client-management/mdm/policy-csp-defender) política - O Defender também tem mais informações especificamente [sobre -SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="02605-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="02605-167">Você também pode definir **-SubmitSamplesConsent** como (a configuração `SendSafeSamples` padrão) `NeverSend` ou `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="02605-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="02605-168">A `SendSafeSamples` configuração significa que a maioria das amostras será enviada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="02605-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="02605-169">Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.</span><span class="sxs-lookup"><span data-stu-id="02605-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="02605-170">Configuração **-SubmitSamplesConsent para** `NeverSend` ou `AlwaysPrompt` diminuirá o nível de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="02605-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="02605-171">Além disso, defini-lo como significa que o recurso Bloquear à Primeira Vista do Microsoft Defender para Ponto de `NeverSend` Extremidade não [](configure-block-at-first-sight-microsoft-defender-antivirus.md) funcionará.</span><span class="sxs-lookup"><span data-stu-id="02605-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="02605-172">Use Windows Instrução de Gerenciamento (WMI) para ativar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="02605-173">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="02605-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="02605-174">Para obter mais informações sobre parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="02605-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="02605-175">Ativar a proteção entregue na nuvem em clientes individuais com o Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="02605-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="02605-176">Se a **configuração Configurar** substituição de configuração local para  relatar a Política de Grupo do Microsoft MAPS estiver definida como **Desabilitada,** a configuração de proteção baseada em nuvem no Windows Configurações ficará esbabada e indisponível.</span><span class="sxs-lookup"><span data-stu-id="02605-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="02605-177">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada Windows Configurações.</span><span class="sxs-lookup"><span data-stu-id="02605-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="02605-178">Abra o Segurança do Windows aplicativo selecionando o ícone de escudo na barra de tarefas ou pesquisando o menu iniciar do **Defender**.</span><span class="sxs-lookup"><span data-stu-id="02605-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="02605-179">Selecione o **&** de proteção contra ameaças (ou o ícone de escudo na barra de **menus** esquerda) e, em seguida, o rótulo de configurações de proteção contra ameaças & vírus:</span><span class="sxs-lookup"><span data-stu-id="02605-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Captura de tela do rótulo de configurações de proteção contra & vírus no Segurança do Windows app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="02605-181">Confirme se **a Proteção baseada em nuvem** e o envio automático **de** exemplo estão comutado para **On**.</span><span class="sxs-lookup"><span data-stu-id="02605-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="02605-182">Se o envio automático de exemplo tiver sido configurado com a Política de Grupo, a configuração ficará acinzenada e indisponível.</span><span class="sxs-lookup"><span data-stu-id="02605-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="02605-183">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="02605-183">Related articles</span></span>

- [<span data-ttu-id="02605-184">Configurar o período de tempo limite de bloqueio da nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02605-185">Configurar o bloco à primeira vista</span><span class="sxs-lookup"><span data-stu-id="02605-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02605-186">Usar cmdlets do PowerShell para gerenciar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="02605-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="02605-187">[Ajudar a proteger Windows PCs com Endpoint Protection para Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="02605-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="02605-188">Cmdlets defender</span><span class="sxs-lookup"><span data-stu-id="02605-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="02605-189">Use a proteção entregue na nuvem da Microsoft Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="02605-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02605-190">Como criar e implantar políticas antimalware: serviço de proteção na nuvem</span><span class="sxs-lookup"><span data-stu-id="02605-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="02605-191">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="02605-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
