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
description: Use a Política de Grupo para implantar o pacote de configuração em dispositivos Windows 10 para que eles sejam onboarded ao serviço.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769384"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="635fd-103">Integração de dispositivos Windows 10 usando Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="635fd-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="635fd-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="635fd-104">**Applies to:**</span></span>

- [<span data-ttu-id="635fd-105">Prevenção contra perda de dados de ponto de extremidade (DLP) do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="635fd-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="635fd-106">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="635fd-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="635fd-107">Para usar atualizações de Política de Grupo (GP) para implantar o pacote, você deve estar no Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="635fd-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="635fd-108">Para o Windows Server 2019, talvez seja necessário substituir NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM do arquivo XML que a preferência de Política de Grupo cria.</span><span class="sxs-lookup"><span data-stu-id="635fd-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="635fd-109">Dispositivos de integração usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="635fd-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="635fd-110">Abra o arquivo .zip do pacote de configuração da GP *(DeviceComplianceOnboardingPackage.zip)* que você baixou do assistente de integração de serviço.</span><span class="sxs-lookup"><span data-stu-id="635fd-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="635fd-111">Você também pode obter o pacote no Centro [de Conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="635fd-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="635fd-112">No painel de navegação, selecione **Configurações de**  >  **Integração de Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="635fd-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="635fd-113">No campo **Método de implantação,** selecione **Política de grupo.**</span><span class="sxs-lookup"><span data-stu-id="635fd-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="635fd-114">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="635fd-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="635fd-115">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="635fd-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="635fd-116">Você deve ter uma pasta chamada *OptionalParamsPolicy* e o arquivo *DeviceComplianceLocalOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="635fd-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="635fd-117">Abra o [Console de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="635fd-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="635fd-118">No **Editor de Gerenciamento de Política de** Grupo, vá para **Configuração do** computador, **preferências** e, em seguida, configurações do painel **de controle.**</span><span class="sxs-lookup"><span data-stu-id="635fd-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="635fd-119">Clique com o botão direito **do** mouse em Tarefas Agendadas, aponte para **Novo** e clique em Tarefa Imediata (pelo menos **Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="635fd-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="635fd-120">Na janela **Tarefa** que é aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA e clique em Verificar **Nomes** e **OK.**</span><span class="sxs-lookup"><span data-stu-id="635fd-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="635fd-121">NT AUTHORITY\SYSTEM aparece como a conta de usuário como a tarefa será executado.</span><span class="sxs-lookup"><span data-stu-id="635fd-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="635fd-122">Marque **Executar se o usuário está conectado ou não e** marque a caixa de seleção Executar com privilégios mais **altos.**</span><span class="sxs-lookup"><span data-stu-id="635fd-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="635fd-123">Vá para a **guia Ações** e clique em **Novo...** **Certifique-se de que Iniciar um** programa está selecionado no **campo** Ação.</span><span class="sxs-lookup"><span data-stu-id="635fd-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="635fd-124">Insira o nome e o local do arquivo *compartilhado WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="635fd-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="635fd-125">Clique **em OK** e feche as janelas abertas do GPMC.</span><span class="sxs-lookup"><span data-stu-id="635fd-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="635fd-126">Desligar dispositivos usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="635fd-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="635fd-127">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="635fd-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="635fd-128">Os pacotes de reexenciamento expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="635fd-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="635fd-129">Ao baixar um pacote de descarregamento, você será notificado sobre a data de vencimento dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="635fd-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="635fd-130">As políticas de integração e de transferência não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="635fd-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="635fd-131">Obter o pacote de redação do Centro [de Conformidade da Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="635fd-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="635fd-132">No painel de navegação, selecione **Configurações**  >  **//Integração de**  >  **dispositivos à rebordagem.**</span><span class="sxs-lookup"><span data-stu-id="635fd-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="635fd-133">No campo **Método de implantação,** selecione **Política de grupo.**</span><span class="sxs-lookup"><span data-stu-id="635fd-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="635fd-134">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="635fd-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="635fd-135">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="635fd-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="635fd-136">Você deve ter um arquivo *chamado DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="635fd-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="635fd-137">Abra o [Console de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="635fd-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="635fd-138">No **Editor de Gerenciamento de Política de** Grupo, vá para a configuração do **computador,** **preferências** e, em seguida, configurações do painel **de controle.**</span><span class="sxs-lookup"><span data-stu-id="635fd-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="635fd-139">Clique com o botão direito **do mouse em Tarefas** Agendadas, aponte para **Novo** e clique em **Tarefa Imediata.**</span><span class="sxs-lookup"><span data-stu-id="635fd-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="635fd-140">Na janela **Tarefa** que é aberta, vá para a **guia** Geral. Escolha a conta de usuário do SISTEMA local (BUILTIN\SYSTEM) em **Opções de segurança.**</span><span class="sxs-lookup"><span data-stu-id="635fd-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="635fd-141">Marque **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.</span><span class="sxs-lookup"><span data-stu-id="635fd-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="635fd-142">Vá para a **guia Ações** e clique em **Novo...**. **Certifique-se de que Iniciar um** programa está selecionado no **campo** Ação.</span><span class="sxs-lookup"><span data-stu-id="635fd-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="635fd-143">Insira o nome e o local do arquivo  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartilhado.</span><span class="sxs-lookup"><span data-stu-id="635fd-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="635fd-144">Clique **em OK** e feche as janelas abertas do GPMC.</span><span class="sxs-lookup"><span data-stu-id="635fd-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="635fd-145">A reação faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="635fd-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="635fd-146">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="635fd-146">Monitor device configuration</span></span>
<span data-ttu-id="635fd-147">Com a Política de Grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="635fd-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="635fd-148">O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.</span><span class="sxs-lookup"><span data-stu-id="635fd-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="635fd-149">Monitorar dispositivos usando o portal</span><span class="sxs-lookup"><span data-stu-id="635fd-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="635fd-150">Vá para o [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="635fd-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="635fd-151">Clique **na lista Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="635fd-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="635fd-152">Verifique se os dispositivos estão aparecendo.</span><span class="sxs-lookup"><span data-stu-id="635fd-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="635fd-153">Pode levar vários dias para que os dispositivos comecem a ser mostrados na lista **de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="635fd-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="635fd-154">Isso inclui o tempo necessário para que as políticas sejam distribuídas para o dispositivo, o tempo necessário para o usuário fazer o login e o tempo necessário para o ponto de extremidade começar a relatar.</span><span class="sxs-lookup"><span data-stu-id="635fd-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="635fd-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="635fd-155">Related topics</span></span>
- [<span data-ttu-id="635fd-156">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="635fd-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="635fd-157">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="635fd-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="635fd-158">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="635fd-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="635fd-159">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="635fd-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="635fd-160">Executar um teste de detecção em dispositivos Microsoft Defender ATP recém-integrados</span><span class="sxs-lookup"><span data-stu-id="635fd-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="635fd-161">Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="635fd-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
