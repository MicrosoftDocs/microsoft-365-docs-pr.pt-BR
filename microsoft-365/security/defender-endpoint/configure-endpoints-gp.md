---
title: Integração Windows 10 dispositivos para o Microsoft Defender para Ponto de Extremidade por meio da Política de Grupo
description: Use a Política de Grupo para implantar o pacote de configuração em Windows 10 dispositivos para que eles sejam integrados ao serviço.
keywords: configurar dispositivos usando a política de grupo, o gerenciamento de dispositivos, configurar o Microsoft Defender para dispositivos de ponto de extremidade, a integração do Microsoft Defender para dispositivos de ponto de extremidade, a política de grupo
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 80794a9d5e4da0d2da74fc714ffd1e0ceab34c8f
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105681"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="aa4a6-104">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="aa4a6-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa4a6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-105">**Applies to:**</span></span>

- <span data-ttu-id="aa4a6-106">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="aa4a6-106">Group Policy</span></span>
- [<span data-ttu-id="aa4a6-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="aa4a6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa4a6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa4a6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aa4a6-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="aa4a6-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa4a6-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="aa4a6-111">Para usar atualizações de Política de Grupo (GP) para implantar o pacote, você deve estar Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="aa4a6-112">Para o Windows Server 2019, talvez seja necessário substituir o NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM do arquivo XML que a preferência de Política de Grupo cria.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="aa4a6-113">Dispositivos integrados usando Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="aa4a6-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="aa4a6-114">[![Imagem do PDF mostrando os vários caminhos de implantação](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aa4a6-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="aa4a6-115">Confira o [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) ou [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="aa4a6-116">Abra o arquivo de pacote de configuração da GP .zip (*WindowsDefenderATPOnboardingPackage.zip*) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="aa4a6-117">Você também pode obter o pacote de [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/):</span><span class="sxs-lookup"><span data-stu-id="aa4a6-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="aa4a6-118">No painel de navegação, selecione **Configurações**  >  **Integração**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="aa4a6-119">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="aa4a6-120">No campo **Método de implantação,** selecione **Política de grupo**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="aa4a6-121">Clique **em Baixar pacote** e salve o .zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="aa4a6-122">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="aa4a6-123">Você deve ter uma pasta chamada *OptionalParamsPolicy* e o *arquivo WindowsDefenderATPOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="aa4a6-124">Abra o [Console de Gerenciamento de Política](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-124">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="aa4a6-125">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador, **Preferências** e configurações **do painel de controle.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="aa4a6-126">Clique com o botão direito do mouse em **Tarefas Agendadas,** aponte para **Novo** e clique em Tarefa Imediata (Pelo menos **Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="aa4a6-127">Na janela **Tarefa** aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA e clique em Verificar **Nomes,** em **seguida, OK**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="aa4a6-128">NT AUTHORITY\SYSTEM aparece como a conta de usuário que a tarefa executará como.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="aa4a6-129">Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="aa4a6-130">Vá até a guia **Ações** e clique em **Novo...** Verifique se **Iniciar um programa** está selecionado no **campo** Ação.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="aa4a6-131">Insira o nome do arquivo e o local do *arquivo WindowsDefenderATPOnboardingScript.cmd* compartilhado.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="aa4a6-132">Clique **em OK** e feche as janelas do GPMC abertas.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="aa4a6-133">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se o dispositivo está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="aa4a6-134">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="aa4a6-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="aa4a6-135">Configurações adicionais do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="aa4a6-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="aa4a6-136">Para cada dispositivo, você pode determinar se amostras podem ser coletadas do dispositivo quando uma solicitação é feita por meio Central de Segurança do Microsoft Defender enviar um arquivo para análise profunda.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="aa4a6-137">Você pode usar a Política de Grupo (GP) para definir configurações, como configurações para o compartilhamento de exemplo usado no recurso de análise profunda.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="aa4a6-138">Configurar configurações de coleção de exemplos</span><span class="sxs-lookup"><span data-stu-id="aa4a6-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="aa4a6-139">Em seu dispositivo de gerenciamento de GP, copie os seguintes arquivos do pacote de configuração:</span><span class="sxs-lookup"><span data-stu-id="aa4a6-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="aa4a6-140">Copie _AtpConfiguration.admx_ em _C: \\ Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="aa4a6-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="aa4a6-141">Copiar _AtpConfiguration.adml_ em _C: \\ Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="aa4a6-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="aa4a6-142">Se você estiver usando um Armazenamento Central para Modelos [Administrativos](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)de Política de Grupo, copie os seguintes arquivos do pacote de configuração:</span><span class="sxs-lookup"><span data-stu-id="aa4a6-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="aa4a6-143">Copiar _AtpConfiguration.admx_ em _\\ \\ \<forest.root\> \\ Políticas SysVol \\ \<forest.root\> \\ \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="aa4a6-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="aa4a6-144">Copiar _AtpConfiguration.adml_ em _\\ \\ \<forest.root\> \\ Políticas SysVol \\ \<forest.root\> \\ \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="aa4a6-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="aa4a6-145">Abra o [Console de Gerenciamento de Política de Grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), clique com o botão direito do mouse no GPO que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-145">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="aa4a6-146">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do computador**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="aa4a6-147">Clique **em Políticas** e, em **seguida, modelos administrativos.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="aa4a6-148">Clique **Windows componentes e,** **em seguida, Windows Defender SmartScreen**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-148">Click **Windows components** and then **Windows Defender SmartScreen**.</span></span>

6.  <span data-ttu-id="aa4a6-149">Escolha habilitar ou desabilitar o compartilhamento de exemplo de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="aa4a6-150">Se você não definir um valor, o valor padrão será habilitar a coleção de exemplos.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="aa4a6-151">Outras configurações recomendadas</span><span class="sxs-lookup"><span data-stu-id="aa4a6-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="aa4a6-152">Atualizar a configuração de proteção do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="aa4a6-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="aa4a6-153">Depois de configurar o script de integração, continue editando a mesma política de grupo para adicionar configurações de proteção de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="aa4a6-154">Execute as edições de política de grupo de um sistema que Windows 10 ou o Server 2019 para garantir que você tenha todos os recursos de Microsoft Defender Antivírus necessários.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="aa4a6-155">Talvez seja necessário fechar e reabrir o objeto de política de grupo para registrar as configurações do Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="aa4a6-156">Todas as políticas estão localizadas em `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="aa4a6-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="aa4a6-157">**Local da política:** \Windows Components\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="aa4a6-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="aa4a6-158">Política</span><span class="sxs-lookup"><span data-stu-id="aa4a6-158">Policy</span></span> | <span data-ttu-id="aa4a6-159">Setting</span><span class="sxs-lookup"><span data-stu-id="aa4a6-159">Setting</span></span> 
:---|:---
<span data-ttu-id="aa4a6-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="aa4a6-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="aa4a6-161">Habilitado - verificado "Habilitar coleta de exemplo em máquinas"</span><span class="sxs-lookup"><span data-stu-id="aa4a6-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="aa4a6-162">**Local da política:** \Windows Components\Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="aa4a6-162">**Policy location:**  \Windows Components\Microsoft Defender Antivirus</span></span>

<span data-ttu-id="aa4a6-163">Política</span><span class="sxs-lookup"><span data-stu-id="aa4a6-163">Policy</span></span> | <span data-ttu-id="aa4a6-164">Setting</span><span class="sxs-lookup"><span data-stu-id="aa4a6-164">Setting</span></span> 
:---|:---
<span data-ttu-id="aa4a6-165">Configurar a detecção para aplicativos potencialmente indesejados</span><span class="sxs-lookup"><span data-stu-id="aa4a6-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="aa4a6-166">Habilitado, Bloqueado</span><span class="sxs-lookup"><span data-stu-id="aa4a6-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="aa4a6-167">**Local da política:** \Windows Components\Microsoft Defender Antivírus\MAPS</span><span class="sxs-lookup"><span data-stu-id="aa4a6-167">**Policy location:** \Windows Components\Microsoft Defender Antivirus\MAPS</span></span>

<span data-ttu-id="aa4a6-168">Política</span><span class="sxs-lookup"><span data-stu-id="aa4a6-168">Policy</span></span> | <span data-ttu-id="aa4a6-169">Setting</span><span class="sxs-lookup"><span data-stu-id="aa4a6-169">Setting</span></span> 
:---|:---
<span data-ttu-id="aa4a6-170">Ingressar no Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="aa4a6-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="aa4a6-171">MAPAs avançados e habilitados</span><span class="sxs-lookup"><span data-stu-id="aa4a6-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="aa4a6-172">Enviar amostras de arquivo quando uma análise posterior for necessária</span><span class="sxs-lookup"><span data-stu-id="aa4a6-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="aa4a6-173">Habilitado, Enviar amostras seguras</span><span class="sxs-lookup"><span data-stu-id="aa4a6-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="aa4a6-174">**Local da política:** \Windows Components\Microsoft Defender Antivírus\Proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="aa4a6-174">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="aa4a6-175">Política</span><span class="sxs-lookup"><span data-stu-id="aa4a6-175">Policy</span></span> | <span data-ttu-id="aa4a6-176">Setting</span><span class="sxs-lookup"><span data-stu-id="aa4a6-176">Setting</span></span> 
:---|:---
<span data-ttu-id="aa4a6-177">Desativar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="aa4a6-177">Turn off real-time protection</span></span>|<span data-ttu-id="aa4a6-178">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="aa4a6-178">Disabled</span></span>
<span data-ttu-id="aa4a6-179">Ativar o monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="aa4a6-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="aa4a6-180">Habilitado</span><span class="sxs-lookup"><span data-stu-id="aa4a6-180">Enabled</span></span>
<span data-ttu-id="aa4a6-181">Examinar todos os arquivos e anexos baixados</span><span class="sxs-lookup"><span data-stu-id="aa4a6-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="aa4a6-182">Habilitado</span><span class="sxs-lookup"><span data-stu-id="aa4a6-182">Enabled</span></span>
<span data-ttu-id="aa4a6-183">Monitorar atividades de arquivo e programa em seu computador</span><span class="sxs-lookup"><span data-stu-id="aa4a6-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="aa4a6-184">Habilitado</span><span class="sxs-lookup"><span data-stu-id="aa4a6-184">Enabled</span></span>

<br/>

<span data-ttu-id="aa4a6-185">**Local da política:** \Windows Components\Microsoft Defender Antivírus\Scan</span><span class="sxs-lookup"><span data-stu-id="aa4a6-185">**Policy location:**  \Windows Components\Microsoft Defender Antivirus\Scan</span></span>

<span data-ttu-id="aa4a6-186">Essas configurações configuram verificações periódicas do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="aa4a6-187">Recomendamos a realização de uma verificação rápida semanal, permitindo desempenho.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="aa4a6-188">Política</span><span class="sxs-lookup"><span data-stu-id="aa4a6-188">Policy</span></span> | <span data-ttu-id="aa4a6-189">Setting</span><span class="sxs-lookup"><span data-stu-id="aa4a6-189">Setting</span></span> 
:---|:---
<span data-ttu-id="aa4a6-190">Verifique a inteligência de segurança de vírus e spyware mais recente antes de executar uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="aa4a6-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="aa4a6-191">Habilitado</span><span class="sxs-lookup"><span data-stu-id="aa4a6-191">Enabled</span></span>


<br/>

<span data-ttu-id="aa4a6-192">**Local da política:** \Windows Components\Microsoft Defender Antivírus\Microsoft Defender Exploit Guard\Redução de Superfície de Ataque</span><span class="sxs-lookup"><span data-stu-id="aa4a6-192">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="aa4a6-193">Obter a lista atual de GUIDs de redução de superfície de ataque de Personalizar regras de redução [de superfície de ataque](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="aa4a6-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="aa4a6-194">Abra a **política Configurar Redução de Superfície de** Ataque.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="aa4a6-195">Selecione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="aa4a6-196">Selecione o **botão Mostrar.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="aa4a6-197">Adicione cada GUID no campo **Nome do** Valor com um Valor de 2.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="aa4a6-198">Isso configurará cada um deles apenas para auditoria.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-198">This will set each up for audit only.</span></span>

   ![Imagem da configuração de redução de superfície de ataque](images/asr-guid.png)



<span data-ttu-id="aa4a6-200">Política</span><span class="sxs-lookup"><span data-stu-id="aa4a6-200">Policy</span></span> | <span data-ttu-id="aa4a6-201">Setting</span><span class="sxs-lookup"><span data-stu-id="aa4a6-201">Setting</span></span> 
:---|:---
<span data-ttu-id="aa4a6-202">Configurar acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="aa4a6-202">Configure Controlled folder access</span></span>| <span data-ttu-id="aa4a6-203">Habilitado, Modo de Auditoria</span><span class="sxs-lookup"><span data-stu-id="aa4a6-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="aa4a6-204">Dispositivos offboard usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="aa4a6-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="aa4a6-205">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="aa4a6-206">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="aa4a6-207">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="aa4a6-208">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="aa4a6-209">Obter o pacote de offboard de [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/):</span><span class="sxs-lookup"><span data-stu-id="aa4a6-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="aa4a6-210">No painel de navegação, selecione **Configurações**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="aa4a6-211">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="aa4a6-212">No campo **Método de implantação,** selecione **Política de grupo**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="aa4a6-213">Clique **em Baixar pacote** e salve o .zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="aa4a6-214">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="aa4a6-215">Você deve ter um arquivo chamado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="aa4a6-216">Abra o [Console de Gerenciamento de Política](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-216">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="aa4a6-217">No Editor **de Gerenciamento de Política de Grupo,** vá para Configuração do **computador,** **Preferências** e configurações **do painel de controle.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="aa4a6-218">Clique com o botão direito do mouse **em Tarefas agendadas,** aponte para **Novo** e clique em **Tarefa Imediata.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="aa4a6-219">Na janela **Tarefa** aberta, vá para a **guia** Geral. Escolha a conta de usuário do SISTEMA local (BUILTIN\SYSTEM) em **Opções de segurança.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="aa4a6-220">Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="aa4a6-221">Vá até a guia **Ações** e clique em **Novo...**. Verifique se **Iniciar um programa** está selecionado no **campo** Ação.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="aa4a6-222">Insira o nome do arquivo e o local do arquivo  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartilhado.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="aa4a6-223">Clique **em OK** e feche as janelas do GPMC abertas.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa4a6-224">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="aa4a6-225">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="aa4a6-225">Monitor device configuration</span></span>
<span data-ttu-id="aa4a6-226">Com a Política de Grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="aa4a6-227">O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="aa4a6-228">Monitorar dispositivos usando o portal</span><span class="sxs-lookup"><span data-stu-id="aa4a6-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="aa4a6-229">Vá para [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="aa4a6-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="aa4a6-230">Clique **em Lista de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="aa4a6-231">Verifique se os dispositivos estão aparecendo.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="aa4a6-232">Pode levar vários dias para que os dispositivos comecem a ser exibidos na lista **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="aa4a6-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="aa4a6-233">Isso inclui o tempo necessário para que as políticas sejam distribuídas para o dispositivo, o tempo necessário para o usuário fazer o login e o tempo necessário para que o ponto de extremidade comece a relatar.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa4a6-234">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="aa4a6-234">Related topics</span></span>
- [<span data-ttu-id="aa4a6-235">Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aa4a6-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="aa4a6-236">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="aa4a6-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="aa4a6-237">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="aa4a6-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="aa4a6-238">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="aa4a6-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="aa4a6-239">Executar um teste de detecção em um Microsoft Defender recém-integrado para dispositivos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="aa4a6-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="aa4a6-240">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="aa4a6-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
