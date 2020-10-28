---
title: Dispositivos Windows 10 integrados por meio da política de grupo
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
description: Use a política de grupo para implantar o pacote de configuração em dispositivos Windows 10 para que eles sejam integrados ao serviço.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769384"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="8c029-103">Dispositivos Windows 10 integrados usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="8c029-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="8c029-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8c029-104">**Applies to:**</span></span>

- [<span data-ttu-id="8c029-105">Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="8c029-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="8c029-106">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="8c029-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-107">Para usar atualizações de política de grupo (GP) para implantar o pacote, você deve estar no Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8c029-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="8c029-108">Para o Windows Server 2019, talvez seja necessário substituir o NT AUTHORITY\Well-Known-System-Account pelo NT AUTHORITY\SYSTEM do arquivo XML que a preferência de política de grupo cria.</span><span class="sxs-lookup"><span data-stu-id="8c029-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="8c029-109">Dispositivos integrados usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="8c029-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="8c029-110">Abra o arquivo. zip do pacote de configuração GP ( *DeviceComplianceOnboardingPackage.zip* ) que você baixou a partir do assistente de integração de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c029-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="8c029-111">Você também pode obter o pacote do [centro de conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="8c029-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="8c029-112">No painel de navegação, selecione **Settings**  >  **integração do dispositivo** de configurações.</span><span class="sxs-lookup"><span data-stu-id="8c029-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="8c029-113">No campo **método de implantação** , selecione **política de grupo** .</span><span class="sxs-lookup"><span data-stu-id="8c029-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="8c029-114">Clique em **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="8c029-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="8c029-115">Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c029-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="8c029-116">Você deve ter uma pasta chamada *OptionalParamsPolicy* e o arquivo *DeviceComplianceLocalOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="8c029-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="8c029-117">Abra o GPMC ( [console de gerenciamento de política de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) ), clique com o botão direito do mouse no objeto de diretiva de grupo (GPO) que você deseja configurar e clique em **Editar** .</span><span class="sxs-lookup"><span data-stu-id="8c029-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="8c029-118">No **Editor de gerenciamento de política de grupo** , vá para configuração do **computador** , **preferências** e, em seguida, configurações do **painel de controle** .</span><span class="sxs-lookup"><span data-stu-id="8c029-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="8c029-119">Clique com o botão direito do mouse em **tarefas agendadas** , aponte para **novo** e clique em **tarefa imediata (pelo menos Windows 7)** .</span><span class="sxs-lookup"><span data-stu-id="8c029-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="8c029-120">Na janela de **tarefas** que é aberta, vá para a guia **geral** . Em **Opções de segurança** , clique em **Alterar usuário ou grupo** e digite System e clique em **verificar nomes** e em **OK** .</span><span class="sxs-lookup"><span data-stu-id="8c029-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="8c029-121">NT AUTHORITY\SYSTEM será exibido como a conta de usuário na qual a tarefa será executada.</span><span class="sxs-lookup"><span data-stu-id="8c029-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="8c029-122">Selecione **executar se o usuário está conectado ou não** e marque a caixa de seleção **executar com privilégios mais altos** .</span><span class="sxs-lookup"><span data-stu-id="8c029-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="8c029-123">Vá até a guia **ações** e clique em **novo..** . Certifique-se de que **Iniciar um programa** está selecionado no campo de **ação** .</span><span class="sxs-lookup"><span data-stu-id="8c029-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="8c029-124">Insira o nome do arquivo e o local do arquivo *WindowsDefenderATPOnboardingScript. cmd* compartilhado.</span><span class="sxs-lookup"><span data-stu-id="8c029-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="8c029-125">Clique em **OK** e feche todas as janelas do GPMC abertas.</span><span class="sxs-lookup"><span data-stu-id="8c029-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="8c029-126">Dispositivos externamente usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="8c029-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="8c029-127">Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="8c029-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="8c029-128">Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="8c029-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="8c029-129">Ao baixar um pacote de remoção, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="8c029-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-130">As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="8c029-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="8c029-131">Obtenha o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="8c029-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="8c029-132">No painel de navegação, selecione **configurações**  >  **//Device** de  >  **remoção de integração** .</span><span class="sxs-lookup"><span data-stu-id="8c029-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="8c029-133">No campo **método de implantação** , selecione **política de grupo** .</span><span class="sxs-lookup"><span data-stu-id="8c029-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="8c029-134">Clique em **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="8c029-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="8c029-135">Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c029-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="8c029-136">Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="8c029-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="8c029-137">Abra o GPMC ( [console de gerenciamento de política de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) ), clique com o botão direito do mouse no objeto de diretiva de grupo (GPO) que você deseja configurar e clique em **Editar** .</span><span class="sxs-lookup"><span data-stu-id="8c029-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="8c029-138">No **Editor de gerenciamento de política de grupo** , vá para configuração do **computador,** **preferências** e, em seguida, configurações do **painel de controle** .</span><span class="sxs-lookup"><span data-stu-id="8c029-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="8c029-139">Clique com o botão direito do mouse em **tarefas agendadas** , aponte para **novo** e clique em **tarefa imediata** .</span><span class="sxs-lookup"><span data-stu-id="8c029-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="8c029-140">Na janela de **tarefas** que é aberta, vá para a guia **geral** . Escolha a conta de usuário do sistema local (BUILTIN\SYSTEM) em **Opções de segurança** .</span><span class="sxs-lookup"><span data-stu-id="8c029-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="8c029-141">Selecione **executar se o usuário está conectado ou não** e marque a caixa de seleção **executar com privilégios mais altos** .</span><span class="sxs-lookup"><span data-stu-id="8c029-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="8c029-142">Vá até a guia **ações** e clique em **novo..** .. Certifique-se de que **Iniciar um programa** está selecionado no campo de **ação** .</span><span class="sxs-lookup"><span data-stu-id="8c029-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="8c029-143">Insira o nome do arquivo e o local do arquivo compartilhado  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="8c029-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="8c029-144">Clique em **OK** e feche todas as janelas do GPMC abertas.</span><span class="sxs-lookup"><span data-stu-id="8c029-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c029-145">A remoção faz com que o dispositivo pare de enviar dados de sensor para o portal, mas dados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c029-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="8c029-146">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c029-146">Monitor device configuration</span></span>
<span data-ttu-id="8c029-147">Com a política de grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8c029-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="8c029-148">O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.</span><span class="sxs-lookup"><span data-stu-id="8c029-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="8c029-149">Monitorar dispositivos usando o portal</span><span class="sxs-lookup"><span data-stu-id="8c029-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="8c029-150">Vá para [o centro de conformidade da Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8c029-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="8c029-151">Clique em lista de **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="8c029-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="8c029-152">Verifique se os dispositivos estão aparecendo.</span><span class="sxs-lookup"><span data-stu-id="8c029-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-153">Pode levar vários dias para os dispositivos começarem a ser exibidos na **lista de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="8c029-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="8c029-154">Isso inclui o tempo que leva para que as políticas sejam distribuídas para o dispositivo, o tempo que leva antes que o usuário faça logon e o tempo que leva para o ponto de extremidade para iniciar o relatório.</span><span class="sxs-lookup"><span data-stu-id="8c029-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8c029-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8c029-155">Related topics</span></span>
- [<span data-ttu-id="8c029-156">Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c029-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="8c029-157">Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="8c029-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="8c029-158">Dispositivos integrados do Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="8c029-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="8c029-159">Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="8c029-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="8c029-160">Executar um teste de detecção em um dispositivo Microsoft defender ATP recentemente integrado</span><span class="sxs-lookup"><span data-stu-id="8c029-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="8c029-161">Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="8c029-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
