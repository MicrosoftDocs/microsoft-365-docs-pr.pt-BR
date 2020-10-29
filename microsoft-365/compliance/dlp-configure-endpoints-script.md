---
title: Dispositivos integrados do Windows 10 usando um script local
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use um script local para implantar o pacote de configuração nos dispositivos de modo que eles sejam incluídos no serviço.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769390"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="b681d-103">Dispositivos integrados do Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="b681d-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="b681d-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b681d-104">**Applies to:**</span></span>

- [<span data-ttu-id="b681d-105">Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="b681d-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="b681d-106">Você também pode manualmente embutir dispositivos individuais na prevenção de perda de dados de ponto de extremidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b681d-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="b681d-107">Você pode querer fazer isso primeiro ao testar o serviço antes de confirmar a integração de todos os dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="b681d-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b681d-108">Este script foi otimizado para uso em até 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b681d-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="b681d-109">Para implantar em escala, use [outras opções de implantação](dlp-configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="b681d-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="b681d-110">Por exemplo, você pode implantar um script de integração em mais de 10 dispositivos em produção com o script disponível em [dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md).</span><span class="sxs-lookup"><span data-stu-id="b681d-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="b681d-111">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="b681d-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="b681d-112">Abra o arquivo. zip do pacote de configuração GP ( *DeviceComplianceOnboardingPackage.zip* ) que você baixou a partir do assistente de integração de serviço.</span><span class="sxs-lookup"><span data-stu-id="b681d-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="b681d-113">Você também pode obter o pacote do [centro de conformidade da Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b681d-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="b681d-114">No painel de navegação, selecione **Settings**  >  **integração do dispositivo** de configurações.</span><span class="sxs-lookup"><span data-stu-id="b681d-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="b681d-115">No campo **método de implantação** , selecione **script local** .</span><span class="sxs-lookup"><span data-stu-id="b681d-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="b681d-116">Clique em **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="b681d-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="b681d-117">Extraia o conteúdo do pacote de configuração para um local no dispositivo que você deseja integrar (por exemplo, a área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="b681d-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="b681d-118">Você deve ter um arquivo chamado *DeviceOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="b681d-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="b681d-119">Abra um prompt de linha de comando com privilégios elevados no dispositivo e execute o script:</span><span class="sxs-lookup"><span data-stu-id="b681d-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="b681d-120">Vá para **Iniciar** e digite **cmd** .</span><span class="sxs-lookup"><span data-stu-id="b681d-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="b681d-121">Clique com o botão direito do mouse em **prompt de comando** e selecione **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="b681d-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Menu iniciar janela apontando para executar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="b681d-123">Digite o local do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="b681d-123">Type the location of the script file.</span></span> <span data-ttu-id="b681d-124">Se você copiou o arquivo para a área de trabalho, digite: *%USERPROFILE%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="b681d-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="b681d-125">Pressione a tecla **Enter** ou clique em **OK** .</span><span class="sxs-lookup"><span data-stu-id="b681d-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="b681d-126">Para obter informações sobre como você pode validar manualmente se o dispositivo está em conformidade e relata corretamente os dados do sensor, confira [solucionar problemas de integração da proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="b681d-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="b681d-127">Dispositivos externamente usando um script local</span><span class="sxs-lookup"><span data-stu-id="b681d-127">Offboard devices using a local script</span></span>
<span data-ttu-id="b681d-128">Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="b681d-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="b681d-129">Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="b681d-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="b681d-130">Ao baixar um pacote de remoção, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="b681d-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="b681d-131">As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="b681d-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="b681d-132">Obter o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b681d-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="b681d-133">No painel de navegação, selecione **configurações** de  >  **remoção de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="b681d-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="b681d-134">No campo **método de implantação** , selecione **script local** .</span><span class="sxs-lookup"><span data-stu-id="b681d-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="b681d-135">Clique em **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="b681d-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="b681d-136">Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b681d-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="b681d-137">Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="b681d-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="b681d-138">Abra um prompt de linha de comando com privilégios elevados no dispositivo e execute o script:</span><span class="sxs-lookup"><span data-stu-id="b681d-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="b681d-139">Vá para **Iniciar** e digite **cmd** .</span><span class="sxs-lookup"><span data-stu-id="b681d-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="b681d-140">Clique com o botão direito do mouse em **prompt de comando** e selecione **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="b681d-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Menu iniciar janela apontando para executar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="b681d-142">Digite o local do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="b681d-142">Type the location of the script file.</span></span> <span data-ttu-id="b681d-143">Se você copiou o arquivo para a área de trabalho, digite: *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*</span><span class="sxs-lookup"><span data-stu-id="b681d-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="b681d-144">Pressione a tecla **Enter** ou clique em **OK** .</span><span class="sxs-lookup"><span data-stu-id="b681d-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b681d-145">A remoção faz com que o dispositivo pare de enviar dados de sensor para o Portal.</span><span class="sxs-lookup"><span data-stu-id="b681d-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="b681d-146">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b681d-146">Monitor device configuration</span></span>
<span data-ttu-id="b681d-147">Você pode seguir as diferentes etapas de verificação no [solucionar problemas de integração] (( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) para verificar se o script foi concluído com êxito e se o agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="b681d-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="b681d-148">O monitoramento também pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.</span><span class="sxs-lookup"><span data-stu-id="b681d-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="b681d-149">Monitorar dispositivos usando o portal</span><span class="sxs-lookup"><span data-stu-id="b681d-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="b681d-150">Vá para [o centro de conformidade da Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b681d-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="b681d-151">Escolha **configurações**  >  dispositivos de **integração de dispositivos**  >  **Devices** .</span><span class="sxs-lookup"><span data-stu-id="b681d-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="b681d-152">Verifique se os dispositivos estão aparecendo.</span><span class="sxs-lookup"><span data-stu-id="b681d-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b681d-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b681d-153">Related topics</span></span>
- [<span data-ttu-id="b681d-154">Dispositivos Windows 10 integrados usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="b681d-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="b681d-155">Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b681d-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b681d-156">Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="b681d-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b681d-157">Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="b681d-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="b681d-158">Executar um teste de detecção em um dispositivo Microsoft defender ATP recentemente integrado</span><span class="sxs-lookup"><span data-stu-id="b681d-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="b681d-159">Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="b681d-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
