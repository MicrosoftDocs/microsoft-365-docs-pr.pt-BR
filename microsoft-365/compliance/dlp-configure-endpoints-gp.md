---
title: Integrar dispositivos Windows 10 por meio da Política de Grupo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use a Política de Grupo para implantar o pacote de configuração em dispositivos Windows 10 para que eles sejam integrados ao serviço.
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918017"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="38428-103">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="38428-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="38428-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="38428-104">**Applies to:**</span></span>

- [<span data-ttu-id="38428-105">Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="38428-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="38428-106">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="38428-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="38428-107">Para usar atualizações de Política de Grupo (GP) para implantar o pacote, você deve estar no Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="38428-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="38428-108">Para o Windows Server 2019, talvez seja necessário substituir o NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM do arquivo XML que a preferência de Política de Grupo cria.</span><span class="sxs-lookup"><span data-stu-id="38428-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="38428-109">Dispositivos de integração usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="38428-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="38428-110">Abra o arquivo .zip do pacote de configuração da GP (*DeviceComplianceOnboardingPackage.zip*) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="38428-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="38428-111">Você também pode obter o pacote do [Centro de Conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="38428-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="38428-112">No painel de navegação, selecione **Configurações**  >  **integração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="38428-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="38428-113">No campo **Método de implantação,** selecione **Política de grupo**.</span><span class="sxs-lookup"><span data-stu-id="38428-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="38428-114">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="38428-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="38428-115">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38428-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="38428-116">Você deve ter uma pasta chamada *OptionalParamsPolicy* e o *arquivo DeviceComplianceLocalOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="38428-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="38428-117">Abra o [Console de Gerenciamento de Política](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="38428-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="38428-118">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador, **Preferências** e configurações **do painel de controle.**</span><span class="sxs-lookup"><span data-stu-id="38428-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="38428-119">Clique com o botão direito do mouse em **Tarefas Agendadas**, aponte para **Novo** e clique em **Tarefa Imediata (Pelo menos Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="38428-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="38428-120">Na janela **Tarefa** aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA e clique em Verificar **Nomes,** em **seguida, OK**.</span><span class="sxs-lookup"><span data-stu-id="38428-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="38428-121">NT AUTHORITY\SYSTEM aparece como a conta de usuário que a tarefa executará como.</span><span class="sxs-lookup"><span data-stu-id="38428-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="38428-122">Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.</span><span class="sxs-lookup"><span data-stu-id="38428-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="38428-123">Vá até a guia **Ações** e clique em **Novo...** Verifique se **Iniciar um programa** está selecionado no **campo** Ação.</span><span class="sxs-lookup"><span data-stu-id="38428-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="38428-124">Insira o nome do arquivo e o local do *arquivo WindowsDefenderATPOnboardingScript.cmd* compartilhado.</span><span class="sxs-lookup"><span data-stu-id="38428-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="38428-125">Clique **em OK** e feche as janelas do GPMC abertas.</span><span class="sxs-lookup"><span data-stu-id="38428-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="38428-126">Dispositivos offboard usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="38428-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="38428-127">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="38428-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="38428-128">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="38428-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="38428-129">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="38428-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="38428-130">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="38428-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="38428-131">Obter o pacote de offboard do [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="38428-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="38428-132">No painel de navegação, selecione **Configurações**  >  **//Dispositivo integrando**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="38428-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="38428-133">No campo **Método de implantação,** selecione **Política de grupo**.</span><span class="sxs-lookup"><span data-stu-id="38428-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="38428-134">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="38428-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="38428-135">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38428-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="38428-136">Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="38428-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="38428-137">Abra o [Console de Gerenciamento de Política](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="38428-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="38428-138">No Editor **de Gerenciamento de Política de Grupo,** vá para Configuração do **computador,** **Preferências** e configurações **do painel de controle.**</span><span class="sxs-lookup"><span data-stu-id="38428-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="38428-139">Clique com o botão direito do mouse **em Tarefas agendadas,** aponte para **Novo** e clique em **Tarefa Imediata.**</span><span class="sxs-lookup"><span data-stu-id="38428-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="38428-140">Na janela **Tarefa** aberta, vá para a **guia** Geral. Escolha a conta de usuário do SISTEMA local (BUILTIN\SYSTEM) em **Opções de segurança.**</span><span class="sxs-lookup"><span data-stu-id="38428-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="38428-141">Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.</span><span class="sxs-lookup"><span data-stu-id="38428-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="38428-142">Vá até a guia **Ações** e clique em **Novo...**. Verifique se **Iniciar um programa** está selecionado no **campo** Ação.</span><span class="sxs-lookup"><span data-stu-id="38428-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="38428-143">Insira o nome do arquivo e o local do arquivo  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartilhado.</span><span class="sxs-lookup"><span data-stu-id="38428-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="38428-144">Clique **em OK** e feche as janelas do GPMC abertas.</span><span class="sxs-lookup"><span data-stu-id="38428-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38428-145">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38428-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="38428-146">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="38428-146">Monitor device configuration</span></span>
<span data-ttu-id="38428-147">Com a Política de Grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="38428-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="38428-148">O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.</span><span class="sxs-lookup"><span data-stu-id="38428-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="38428-149">Monitorar dispositivos usando o portal</span><span class="sxs-lookup"><span data-stu-id="38428-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="38428-150">Vá para o [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="38428-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="38428-151">Clique **em Lista de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="38428-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="38428-152">Verifique se os dispositivos estão aparecendo.</span><span class="sxs-lookup"><span data-stu-id="38428-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="38428-153">Pode levar vários dias para que os dispositivos comecem a ser exibidos na lista **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="38428-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="38428-154">Isso inclui o tempo necessário para que as políticas sejam distribuídas para o dispositivo, o tempo necessário para o usuário fazer o login e o tempo necessário para que o ponto de extremidade comece a relatar.</span><span class="sxs-lookup"><span data-stu-id="38428-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="38428-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="38428-155">Related topics</span></span>
- [<span data-ttu-id="38428-156">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="38428-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="38428-157">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="38428-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="38428-158">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="38428-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="38428-159">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="38428-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="38428-160">Executar um teste de detecção em dispositivos MICROSOFT Defender ATP recém-instados</span><span class="sxs-lookup"><span data-stu-id="38428-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="38428-161">Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38428-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)