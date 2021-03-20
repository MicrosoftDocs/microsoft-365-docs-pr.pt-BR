---
title: Integrar dispositivos Windows 10 usando um script local
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
description: Use um script local para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917967"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="5326e-103">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="5326e-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="5326e-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5326e-104">**Applies to:**</span></span>

- [<span data-ttu-id="5326e-105">Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="5326e-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="5326e-106">Você também pode fazer a integração manual de dispositivos individuais à prevenção contra perda de dados do Microsoft 365 Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5326e-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="5326e-107">Você pode querer fazer isso primeiro ao testar o serviço antes de se comprometer a integração de todos os dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="5326e-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5326e-108">Esse script foi otimizado para uso em até 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5326e-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="5326e-109">Para implantar em escala, use [outras opções de implantação.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="5326e-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="5326e-110">Por exemplo, você pode implantar um script de integração em mais de 10 dispositivos em produção com o script disponível em dispositivos [Do Windows 10](dlp-configure-endpoints-gp.md)de integração usando a Política de Grupo .</span><span class="sxs-lookup"><span data-stu-id="5326e-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="5326e-111">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="5326e-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="5326e-112">Abra o arquivo .zip do pacote de configuração da GP (*DeviceComplianceOnboardingPackage.zip*) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="5326e-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="5326e-113">Você também pode obter o pacote do [Centro de Conformidade da Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5326e-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="5326e-114">No painel de navegação, selecione **Configurações**  >  **Integração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="5326e-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="5326e-115">No campo **Método de Implantação,** selecione **Script Local**.</span><span class="sxs-lookup"><span data-stu-id="5326e-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="5326e-116">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="5326e-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="5326e-117">Extraia o conteúdo do pacote de configuração para um local no dispositivo que você deseja integrar (por exemplo, a Área de Trabalho).</span><span class="sxs-lookup"><span data-stu-id="5326e-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="5326e-118">Você deve ter um arquivo chamado *DeviceOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="5326e-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="5326e-119">Abra um prompt de linha de comando elevada no dispositivo e execute o script:</span><span class="sxs-lookup"><span data-stu-id="5326e-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="5326e-120">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5326e-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="5326e-121">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="5326e-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![Menu Iniciar janela apontando para Executar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="5326e-123">Digite o local do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="5326e-123">Type the location of the script file.</span></span> <span data-ttu-id="5326e-124">Se você copiou o arquivo para a área de trabalho, *digite: %userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="5326e-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="5326e-125">Pressione a **tecla Enter** ou clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5326e-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="5326e-126">Para obter informações sobre como você pode validar manualmente se o dispositivo é compatível e relata corretamente os dados do sensor, consulte Solução de problemas de integração da Proteção Avançada contra Ameaças do [Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="5326e-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="5326e-127">Dispositivos offboard usando um script local</span><span class="sxs-lookup"><span data-stu-id="5326e-127">Offboard devices using a local script</span></span>
<span data-ttu-id="5326e-128">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="5326e-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="5326e-129">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="5326e-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="5326e-130">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="5326e-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="5326e-131">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="5326e-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="5326e-132">Obter o pacote de offboard do [Centro de Conformidade da Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5326e-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="5326e-133">No painel de navegação, selecione **Configurações**  >  **Offboarding do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="5326e-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="5326e-134">No campo **Método de Implantação,** selecione **Script Local**.</span><span class="sxs-lookup"><span data-stu-id="5326e-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="5326e-135">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="5326e-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="5326e-136">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5326e-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="5326e-137">Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="5326e-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="5326e-138">Abra um prompt de linha de comando elevada no dispositivo e execute o script:</span><span class="sxs-lookup"><span data-stu-id="5326e-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="5326e-139">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5326e-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="5326e-140">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="5326e-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![Menu Iniciar janela apontando para Executar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="5326e-142">Digite o local do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="5326e-142">Type the location of the script file.</span></span> <span data-ttu-id="5326e-143">Se você copiou o arquivo para a área de trabalho, *digite: %userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="5326e-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="5326e-144">Pressione a **tecla Enter** ou clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5326e-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5326e-145">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal.</span><span class="sxs-lookup"><span data-stu-id="5326e-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="5326e-146">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5326e-146">Monitor device configuration</span></span>
<span data-ttu-id="5326e-147">Você pode seguir as diferentes etapas de verificação no [Solucionar problemas de integração](( para verificar se o script foi concluído com êxito e https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) se o agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="5326e-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="5326e-148">O monitoramento também pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.</span><span class="sxs-lookup"><span data-stu-id="5326e-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="5326e-149">Monitorar dispositivos usando o portal</span><span class="sxs-lookup"><span data-stu-id="5326e-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="5326e-150">Vá para o Centro de [Conformidade do Microsoft 365.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5326e-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="5326e-151">Escolha **Configurações**  >  **Dispositivos de**  >  **integração de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5326e-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="5326e-152">Verifique se os dispositivos estão aparecendo.</span><span class="sxs-lookup"><span data-stu-id="5326e-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5326e-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5326e-153">Related topics</span></span>
- [<span data-ttu-id="5326e-154">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="5326e-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="5326e-155">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5326e-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="5326e-156">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="5326e-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="5326e-157">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="5326e-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="5326e-158">Executar um teste de detecção em um dispositivo Microsoft Defender ATP recém-conectado</span><span class="sxs-lookup"><span data-stu-id="5326e-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="5326e-159">Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5326e-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)