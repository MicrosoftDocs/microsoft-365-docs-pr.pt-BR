---
title: Integrar dispositivo Windows 10 usando o Configuration Manager
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
description: Use o Configuration Manager para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
ms.openlocfilehash: d2db35e50d31a0a19076965da6dcecf9cfeef826
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226892"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="80e46-103">Integrar dispositivo Windows 10 usando o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="80e46-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="80e46-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="80e46-104">**Applies to:**</span></span>

- [<span data-ttu-id="80e46-105">Microsoft 365 Prevenção contra perda de dados do ponto de extremidade (DLP)</span><span class="sxs-lookup"><span data-stu-id="80e46-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="80e46-106">Gerenciador de Configurações do System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="80e46-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="80e46-107">Dispositivos de integração usando System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="80e46-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="80e46-108">Abra o arquivo de pacote de configuração do Configuration Manager .zip (*DeviceComplianceOnboardingPackage.zip*) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="80e46-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="80e46-109">Você também pode obter o pacote do [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="80e46-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="80e46-110">No painel de navegação, **selecione** Configurações  >  **integração de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="80e46-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="80e46-111">No campo **método Deployment,** selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="80e46-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>

4. <span data-ttu-id="80e46-112">Selecione **Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="80e46-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="80e46-113">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="80e46-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="80e46-114">Você deve ter um arquivo chamado *DeviceComplianceOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="80e46-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="80e46-115">Implante o pacote seguindo as etapas no artigo [Pacotes e Programas no System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="80e46-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="80e46-116">Escolha uma coleção de dispositivos predefinida para a qual implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="80e46-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="80e46-117">Microsoft 365 A prevenção contra perda de dados do ponto de extremidade não dá suporte à integração durante a fase [OOBE (Experiência](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Inicial).</span><span class="sxs-lookup"><span data-stu-id="80e46-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="80e46-118">Certifique-se de que os usuários concluam o OOBE após Windows instalação ou atualização.</span><span class="sxs-lookup"><span data-stu-id="80e46-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

> [!TIP]
> <span data-ttu-id="80e46-119">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="80e46-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="80e46-120">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span><span class="sxs-lookup"><span data-stu-id="80e46-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="80e46-121">Observe que é possível criar uma regra de detecção em um aplicativo do Configuration Manager para verificar continuamente se um dispositivo foi internado.</span><span class="sxs-lookup"><span data-stu-id="80e46-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="80e46-122">Um aplicativo é um tipo diferente de objeto do que um pacote e um programa.</span><span class="sxs-lookup"><span data-stu-id="80e46-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="80e46-123">Se um dispositivo ainda não estiver conectado (devido à conclusão pendente do OOBE ou qualquer outro motivo), o Configuration Manager repetirá a integração do dispositivo até que a regra detecte a alteração de status.</span><span class="sxs-lookup"><span data-stu-id="80e46-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
>
> <span data-ttu-id="80e46-124">Esse comportamento pode ser realizado criando uma verificação de regra de detecção se o valor do Registro "OnboardingState" (do tipo REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="80e46-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="80e46-125">Esse valor do Registro está localizado em "HKLM\SOFTWARE\Microsoft\Windows Proteção Avançada contra Ameaças\Status".</span><span class="sxs-lookup"><span data-stu-id="80e46-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="80e46-126">Para obter mais informações, [consulte Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="80e46-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="80e46-127">Configurar configurações de coleção de exemplos</span><span class="sxs-lookup"><span data-stu-id="80e46-127">Configure sample collection settings</span></span>

<span data-ttu-id="80e46-128">Para cada dispositivo, você pode definir um valor de configuração para determinar se amostras podem ser coletadas do dispositivo quando uma solicitação é feita por meio do Central de Segurança do Microsoft Defender enviar um arquivo para análise profunda.</span><span class="sxs-lookup"><span data-stu-id="80e46-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="80e46-129">Essas configurações geralmente são feitas por meio do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="80e46-129">These configuration settings are typically done through Configuration Manager.</span></span>

<span data-ttu-id="80e46-130">Você pode definir uma regra de conformidade para o item de configuração no Configuration Manager para alterar a configuração de compartilhamento de exemplo em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="80e46-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="80e46-131">Essa regra deve ser um *item de* configuração de regra de conformidade de correção que define o valor de uma chave do Registro em dispositivos direcionados para garantir que eles sejam reclamações.</span><span class="sxs-lookup"><span data-stu-id="80e46-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="80e46-132">A configuração é definida por meio da seguinte entrada de chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="80e46-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="80e46-133">Onde:</span><span class="sxs-lookup"><span data-stu-id="80e46-133">Where:</span></span><br>
<span data-ttu-id="80e46-134">Tipo de chave é um D-WORD.</span><span class="sxs-lookup"><span data-stu-id="80e46-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="80e46-135">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="80e46-135">Possible values are:</span></span>
- <span data-ttu-id="80e46-136">0 - não permite o compartilhamento de exemplo deste dispositivo</span><span class="sxs-lookup"><span data-stu-id="80e46-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="80e46-137">1 - permite o compartilhamento de todos os tipos de arquivo deste dispositivo</span><span class="sxs-lookup"><span data-stu-id="80e46-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="80e46-138">O valor padrão caso a chave do Registro não exista é 1.</span><span class="sxs-lookup"><span data-stu-id="80e46-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="80e46-139">Para obter mais informações sobre System Center Configuration Manager Conformidade, consulte Introdução às configurações de conformidade [no System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="80e46-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="80e46-140">Outras configurações recomendadas</span><span class="sxs-lookup"><span data-stu-id="80e46-140">Other recommended configuration settings</span></span>
<span data-ttu-id="80e46-141">Após a integração de dispositivos ao serviço, é importante aproveitar os recursos de proteção contra ameaças incluídos, habilitando-os com as seguintes configurações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="80e46-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="80e46-142">Configuração do conjunto de dispositivos</span><span class="sxs-lookup"><span data-stu-id="80e46-142">Device collection configuration</span></span>
<span data-ttu-id="80e46-143">Se você estiver usando o Endpoint Configuration Manager, versão 2002 ou posterior, poderá optar por ampliar a implantação para incluir servidores ou clientes de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="80e46-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="80e46-144">Configuração de proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="80e46-144">Next generation protection configuration</span></span>

<span data-ttu-id="80e46-145">As seguintes configurações são recomendadas:</span><span class="sxs-lookup"><span data-stu-id="80e46-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="80e46-146">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="80e46-146">**Scan**</span></span>

- <span data-ttu-id="80e46-147">Examinar dispositivos de armazenamento removíveis, como unidades USB: Sim</span><span class="sxs-lookup"><span data-stu-id="80e46-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="80e46-148">**Proteção em tempo real**</span><span class="sxs-lookup"><span data-stu-id="80e46-148">**Real-time Protection**</span></span>

- <span data-ttu-id="80e46-149">Habilitar o Monitoramento Comportamental: Sim</span><span class="sxs-lookup"><span data-stu-id="80e46-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="80e46-150">Habilitar a proteção contra aplicativos potencialmente indesejados no download e antes da instalação: Sim</span><span class="sxs-lookup"><span data-stu-id="80e46-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="80e46-151">**Serviço de Proteção na Nuvem**</span><span class="sxs-lookup"><span data-stu-id="80e46-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="80e46-152">Tipo de associação do Serviço de Proteção na Nuvem: Associação avançada</span><span class="sxs-lookup"><span data-stu-id="80e46-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="80e46-153">**Redução de superfície de ataque** Configure todas as regras disponíveis para Auditoria.</span><span class="sxs-lookup"><span data-stu-id="80e46-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

> [!NOTE]
> <span data-ttu-id="80e46-154">O bloqueio dessas atividades pode interromper processos comerciais legítimos.</span><span class="sxs-lookup"><span data-stu-id="80e46-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="80e46-155">A melhor abordagem é definir tudo para auditoria, identificar quais são seguros para ativar e, em seguida, ativar essas configurações em pontos de extremidade que não têm detecções de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="80e46-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="80e46-156">**Proteção de rede**</span><span class="sxs-lookup"><span data-stu-id="80e46-156">**Network protection**</span></span>

<span data-ttu-id="80e46-157">Antes de ativar a proteção de rede no modo de auditoria ou bloqueio, verifique se você instalou a atualização da plataforma antimalware, que pode ser obtida na página [de suporte](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span><span class="sxs-lookup"><span data-stu-id="80e46-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="80e46-158">**Acesso controlado a pastas**</span><span class="sxs-lookup"><span data-stu-id="80e46-158">**Controlled folder access**</span></span>

<span data-ttu-id="80e46-159">Habilita o recurso no modo de auditoria por pelo menos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="80e46-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="80e46-160">Após esse período, revise as detecções e crie uma lista de aplicativos que têm permissão para gravar em diretórios protegidos.</span><span class="sxs-lookup"><span data-stu-id="80e46-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="80e46-161">Para obter mais informações, consulte [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="80e46-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="80e46-162">Dispositivos offboard usando o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="80e46-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="80e46-163">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="80e46-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="80e46-164">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="80e46-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="80e46-165">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="80e46-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="80e46-166">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="80e46-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="80e46-167">Dispositivos de offboard usando Microsoft Endpoint Configuration Manager ramificação atual</span><span class="sxs-lookup"><span data-stu-id="80e46-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="80e46-168">Se você usar Microsoft Endpoint Configuration Manager branch atual, consulte [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span><span class="sxs-lookup"><span data-stu-id="80e46-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="80e46-169">Dispositivos de offboard usando System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="80e46-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="80e46-170">Obter o pacote de offboard do [Centro de Conformidade da Microsoft](https://compliance.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="80e46-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="80e46-171">No painel de navegação, selecione **Configurações**  >   **Offboarding** de integração do >  **dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="80e46-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="80e46-172">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="80e46-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="80e46-173">No campo **método Deployment,** selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="80e46-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>

5. <span data-ttu-id="80e46-174">Selecione **Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="80e46-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="80e46-175">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="80e46-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="80e46-176">Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="80e46-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="80e46-177">Implante o pacote seguindo as etapas no artigo [Pacotes e Programas no System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="80e46-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="80e46-178">Escolha uma coleção de dispositivos predefinida para a qual implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="80e46-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80e46-179">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.</span><span class="sxs-lookup"><span data-stu-id="80e46-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="80e46-180">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="80e46-180">Monitor device configuration</span></span>

<span data-ttu-id="80e46-181">Se você estiver usando Microsoft Endpoint Configuration Manager branch atual, use o painel integrado do Microsoft Defender para Ponto de Extremidade no console do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="80e46-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="80e46-182">Para obter mais informações, consulte [Proteção Avançada contra Ameaças do Microsoft Defender - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="80e46-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="80e46-183">Se você estiver usando o System Center 2012 R2 Configuration Manager, o monitoramento consiste em duas partes:</span><span class="sxs-lookup"><span data-stu-id="80e46-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="80e46-184">Confirmar se o pacote de configuração foi implantado corretamente e está sendo executado (ou executado com êxito) nos dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="80e46-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="80e46-185">Verificar se os dispositivos estão em conformidade com o serviço de prevenção contra perda de dados do ponto de extremidade do Microsoft 365 (isso garante que o dispositivo possa concluir o processo de integração e pode continuar a relatar dados ao serviço).</span><span class="sxs-lookup"><span data-stu-id="80e46-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="80e46-186">Confirme se o pacote de configuração foi implantado corretamente</span><span class="sxs-lookup"><span data-stu-id="80e46-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="80e46-187">No console do Configuration Manager, clique **em Monitoramento** na parte inferior do painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="80e46-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="80e46-188">Selecione **Visão geral** e **implantações.**</span><span class="sxs-lookup"><span data-stu-id="80e46-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="80e46-189">Selecione na implantação com o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="80e46-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="80e46-190">Revise os indicadores de status **em Estatísticas de Conclusão** e Status de **Conteúdo.**</span><span class="sxs-lookup"><span data-stu-id="80e46-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="80e46-191">Se houver implantações com falha (dispositivos com **status Error**, **Requirements Not Met**, ou **Failed**), talvez seja necessário solucionar problemas dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="80e46-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="80e46-192">Para obter mais informações, consulte Solução de problemas de integração da [Proteção Avançada contra Ameaças do Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="80e46-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Gerenciador de Configurações mostrando implantação bem-sucedida sem erros](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="80e46-194">Verifique se os dispositivos estão em conformidade com o serviço Microsoft 365 de prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80e46-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="80e46-195">Você pode definir uma regra de conformidade para o item de configuração no System Center 2012 R2 Configuration Manager para monitorar sua implantação.</span><span class="sxs-lookup"><span data-stu-id="80e46-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="80e46-196">Este procedimento e a entrada do Registro se aplica à DLP do ponto de extremidade, bem como à Proteção Avançada contra Ameaças.</span><span class="sxs-lookup"><span data-stu-id="80e46-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="80e46-197">Essa regra deve ser um *item* de configuração de regra de conformidade não corretivo que monitora o valor de uma chave do Registro em dispositivos direcionados.</span><span class="sxs-lookup"><span data-stu-id="80e46-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="80e46-198">Monitore a seguinte entrada da chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="80e46-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="80e46-199">Para obter mais informações, consulte [Introdução às configurações de conformidade no System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="80e46-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="80e46-200">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="80e46-200">Related topics</span></span>
- [<span data-ttu-id="80e46-201">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="80e46-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="80e46-202">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="80e46-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="80e46-203">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="80e46-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="80e46-204">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="80e46-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="80e46-205">Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="80e46-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="80e46-206">Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="80e46-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)