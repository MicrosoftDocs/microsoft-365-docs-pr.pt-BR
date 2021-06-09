---
title: Dispositivos integrados com várias sessões do Windows 10 na Área de Trabalho Virtual do Windows
description: Leia mais neste artigo sobre a integração de Windows 10 de várias sessões em Windows Área de Trabalho Virtual
keywords: Windows Área de trabalho virtual, WVD, microsoft defender, ponto de extremidade, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7ade1ae1e045cb52f48d231acbc1712e753b6bc3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841841"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="2a012-104">Dispositivos integrados com várias sessões do Windows 10 na Área de Trabalho Virtual do Windows</span><span class="sxs-lookup"><span data-stu-id="2a012-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="2a012-105">6 minutos para leitura</span><span class="sxs-lookup"><span data-stu-id="2a012-105">6 minutes to read</span></span> 

<span data-ttu-id="2a012-106">Aplicável a:</span><span class="sxs-lookup"><span data-stu-id="2a012-106">Applies to:</span></span> 
- <span data-ttu-id="2a012-107">Windows 10 várias sessões em execução Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="2a012-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="2a012-108">O Microsoft Defender para Ponto de Extremidade oferece suporte ao monitoramento de VDI e Windows da Área de Trabalho Virtual.</span><span class="sxs-lookup"><span data-stu-id="2a012-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="2a012-109">Dependendo das necessidades da sua organização, talvez seja necessário implementar sessões de VDI ou de área de trabalho virtual Windows para ajudar seus funcionários a acessar dados corporativos e aplicativos de um dispositivo sem gestão, localização remota ou cenário semelhante.</span><span class="sxs-lookup"><span data-stu-id="2a012-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="2a012-110">Com o Microsoft Defender para Ponto de Extremidade, você pode monitorar essas máquinas virtuais para atividades anômalas.</span><span class="sxs-lookup"><span data-stu-id="2a012-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="2a012-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2a012-111">Before you begin</span></span>
<span data-ttu-id="2a012-112">Familiarize-se com as [considerações para VDI não persistente.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="2a012-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="2a012-113">Embora [Windows Área](/azure/virtual-desktop/overview) de Trabalho Virtual não forneça opções de não persistência, ela fornece maneiras de usar uma imagem de Windows dourada que pode ser usada para provisionar novos hosts e reimplantar computadores.</span><span class="sxs-lookup"><span data-stu-id="2a012-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="2a012-114">Isso aumenta a volatilidade no ambiente e, portanto, afeta quais entradas são criadas e mantidas no portal do Microsoft Defender para Ponto de Extremidade, reduzindo a visibilidade para seus analistas de segurança.</span><span class="sxs-lookup"><span data-stu-id="2a012-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="2a012-115">Dependendo da escolha do método de integração, os dispositivos podem aparecer no portal do Microsoft Defender para Ponto de Extremidade como:</span><span class="sxs-lookup"><span data-stu-id="2a012-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="2a012-116">Entrada única para cada área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="2a012-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="2a012-117">Várias entradas para cada área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="2a012-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="2a012-118">A Microsoft recomenda a integração Windows Área de Trabalho Virtual como uma única entrada por área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="2a012-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="2a012-119">Isso garante que a experiência de investigação no portal do Ponto de Extremidade do Microsoft Defender está no contexto de um dispositivo com base no nome do computador.</span><span class="sxs-lookup"><span data-stu-id="2a012-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="2a012-120">As organizações que frequentemente excluem e reimplantam hosts WVD devem considerar fortemente o uso desse método, pois impede que vários objetos para o mesmo computador seja criado no portal do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2a012-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="2a012-121">Isso pode levar a confusão ao investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="2a012-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="2a012-122">Para ambientes de teste ou não voláteis, você pode optar por escolher de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="2a012-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="2a012-123">A Microsoft recomenda adicionar o script de integração do Microsoft Defender for Endpoint à imagem dourada do WVD.</span><span class="sxs-lookup"><span data-stu-id="2a012-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="2a012-124">Dessa forma, você pode ter certeza de que esse script de integração é executado imediatamente na primeira inicialização.</span><span class="sxs-lookup"><span data-stu-id="2a012-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="2a012-125">Ele é executado como um script de inicialização na primeira inicialização em todos os dispositivos WVD provisionados da imagem dourada do WVD.</span><span class="sxs-lookup"><span data-stu-id="2a012-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="2a012-126">No entanto, se você estiver usando uma das imagens da galeria sem modificação, coloque o script em um local compartilhado e chame-o de política de grupo local ou de domínio.</span><span class="sxs-lookup"><span data-stu-id="2a012-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a012-127">O posicionamento e a configuração do script de inicialização de integração da VDI na imagem dourada do WVD o configura como um script de inicialização que é executado quando o WVD é iniciado.</span><span class="sxs-lookup"><span data-stu-id="2a012-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="2a012-128">Não é recomendável a integração da imagem real de ouro WVD.</span><span class="sxs-lookup"><span data-stu-id="2a012-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="2a012-129">Outra consideração é o método usado para executar o script.</span><span class="sxs-lookup"><span data-stu-id="2a012-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="2a012-130">Ele deve ser executado o mais cedo possível no processo de inicialização/provisionamento para reduzir o tempo entre o computador que está disponível para receber sessões e a integração do dispositivo ao serviço.</span><span class="sxs-lookup"><span data-stu-id="2a012-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="2a012-131">Abaixo, os cenários 1 & 2 levam isso em consideração.</span><span class="sxs-lookup"><span data-stu-id="2a012-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="2a012-132">Cenários</span><span class="sxs-lookup"><span data-stu-id="2a012-132">Scenarios</span></span>
<span data-ttu-id="2a012-133">Há várias maneiras de fazer a integração de um computador host WVD:</span><span class="sxs-lookup"><span data-stu-id="2a012-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="2a012-134">Execute o script na imagem dourada (ou em um local compartilhado) durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="2a012-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="2a012-135">Use uma ferramenta de gerenciamento para executar o script.</span><span class="sxs-lookup"><span data-stu-id="2a012-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="2a012-136">*Cenário 1: usando a política de grupo local*</span><span class="sxs-lookup"><span data-stu-id="2a012-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="2a012-137">Esse cenário exige colocar o script em uma imagem dourada e usa a política de grupo local para ser executado no início do processo de inicialização.</span><span class="sxs-lookup"><span data-stu-id="2a012-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="2a012-138">Use as instruções em [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span><span class="sxs-lookup"><span data-stu-id="2a012-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="2a012-139">Siga as instruções para uma única entrada para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2a012-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="2a012-140">*Cenário 2: usando a política de grupo de domínio*</span><span class="sxs-lookup"><span data-stu-id="2a012-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="2a012-141">Esse cenário usa um script localizado centralmente e o executa usando uma política de grupo baseada em domínio.</span><span class="sxs-lookup"><span data-stu-id="2a012-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="2a012-142">Você também pode colocar o script na imagem dourada e execute-o da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="2a012-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="2a012-143">**Baixe o WindowsDefenderATPOnboardingPackage.zip do centro de segurança Windows Defender de segurança**</span><span class="sxs-lookup"><span data-stu-id="2a012-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="2a012-144">Abra o arquivo de pacote de configuração .zip VDI (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="2a012-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="2a012-145">No painel Central de Segurança do Microsoft Defender de navegação, selecione **Configurações**  >  **Integração**.</span><span class="sxs-lookup"><span data-stu-id="2a012-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="2a012-146">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2a012-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="2a012-147">No campo **Método de implantação,** selecione scripts de integração VDI para pontos de extremidade não persistentes.</span><span class="sxs-lookup"><span data-stu-id="2a012-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="2a012-148">Clique **em Baixar pacote** e salve o .zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="2a012-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="2a012-149">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2a012-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="2a012-150">Você deve ter uma pasta chamada **OptionalParamsPolicy** e os arquivos **WindowsDefenderATPOnboardingScript.cmd** e **Onboard-NonPersistentMachine.ps1**.</span><span class="sxs-lookup"><span data-stu-id="2a012-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="2a012-151">**Usar o console de gerenciamento de Política de Grupo para executar o script quando a máquina virtual for iniciada**</span><span class="sxs-lookup"><span data-stu-id="2a012-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="2a012-152">Abra o Console de Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2a012-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2a012-153">No Editor de Gerenciamento de Política de Grupo, vá até **Configuração** do computador \> **Configurações Configurações** Do painel \> **Controle de configurações**.</span><span class="sxs-lookup"><span data-stu-id="2a012-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="2a012-154">Clique com o botão direito do mouse em **Tarefas Agendadas,** clique em **Novo** e em **Tarefa** Imediata (Pelo menos Windows 7).</span><span class="sxs-lookup"><span data-stu-id="2a012-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="2a012-155">Na janela Tarefa aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA.</span><span class="sxs-lookup"><span data-stu-id="2a012-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="2a012-156">Clique **em Verificar Nomes** e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2a012-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="2a012-157">NT AUTHORITY\SYSTEM aparece como a conta de usuário que a tarefa executará como.</span><span class="sxs-lookup"><span data-stu-id="2a012-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="2a012-158">Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.</span><span class="sxs-lookup"><span data-stu-id="2a012-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="2a012-159">Vá até a guia **Ações** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a012-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="2a012-160">Verifique se **Iniciar um programa** está selecionado no campo Ação.</span><span class="sxs-lookup"><span data-stu-id="2a012-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="2a012-161">Insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2a012-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="2a012-162">Em seguida, **selecione OK** e feche qualquer janela GPMC aberta.</span><span class="sxs-lookup"><span data-stu-id="2a012-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="2a012-163">*Cenário 3: Integração usando ferramentas de gerenciamento*</span><span class="sxs-lookup"><span data-stu-id="2a012-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="2a012-164">Se você planeja gerenciar seus dispositivos usando uma ferramenta de gerenciamento, poderá integrar dispositivos com Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2a012-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="2a012-165">Para obter mais informações, consulte [Onboard Windows 10 using Configuration Manager](configure-endpoints-sccm.md).</span><span class="sxs-lookup"><span data-stu-id="2a012-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="2a012-166">Se você planeja usar As Regras de Redução de Superfície de Ataque [,](attack-surface-reduction.md)observe que a regra " Bloquear criações de processo originadas de[comandos PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)e WMI " não deve ser usada, pois essa regra é incompatível com o gerenciamento por meio de Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2a012-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="2a012-167">A regra bloqueia comandos WMI que o cliente configuration Manager usa para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="2a012-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="2a012-168">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se o dispositivo está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="2a012-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="2a012-169">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="2a012-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="2a012-170">Marcando seus máquinas ao criar sua imagem dourada</span><span class="sxs-lookup"><span data-stu-id="2a012-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="2a012-171">Como parte de sua integração, talvez você queira considerar a configuração de uma marca de máquina para diferenciar máquinas WVD com mais facilidade no Centro de Segurança da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a012-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="2a012-172">Para obter mais informações, [consulte Add device tags by setting a Registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span><span class="sxs-lookup"><span data-stu-id="2a012-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="2a012-173">Outras configurações recomendadas</span><span class="sxs-lookup"><span data-stu-id="2a012-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="2a012-174">Ao criar sua imagem dourada, você também pode querer definir as configurações de proteção inicial.</span><span class="sxs-lookup"><span data-stu-id="2a012-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="2a012-175">Para obter mais informações, consulte [Outras configurações recomendadas.](configure-endpoints-gp.md#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="2a012-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="2a012-176">Além disso, se você estiver usando perfis de usuário FSlogix, recomendamos excluir os seguintes arquivos da proteção always-on:</span><span class="sxs-lookup"><span data-stu-id="2a012-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="2a012-177">**Excluir Arquivos:**</span><span class="sxs-lookup"><span data-stu-id="2a012-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="2a012-178">**Excluir processos:**</span><span class="sxs-lookup"><span data-stu-id="2a012-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="2a012-179">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="2a012-179">Licensing requirements</span></span> 

<span data-ttu-id="2a012-180">Observação sobre licenciamento: ao usar o Windows 10 Enterprise em várias sessões, dependendo de seus requisitos, você pode optar por ter todos os usuários licenciados por meio do Microsoft Defender para Ponto de Extremidade (por usuário), Windows Enterprise E5, Microsoft 365 Security ou Microsoft 365 E5, ou ter a VM licenciada por meio do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="2a012-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="2a012-181">Os requisitos de licenciamento do Microsoft Defender para ponto de extremidade podem ser encontrados em: [Requisitos de licenciamento.](minimum-requirements.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="2a012-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>
