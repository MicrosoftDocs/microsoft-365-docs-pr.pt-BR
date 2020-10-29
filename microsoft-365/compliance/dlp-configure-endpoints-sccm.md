---
title: Dispositivos integrados do Windows 10 usando o Configuration Manager
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
description: Use o Gerenciador de configurações para implantar o pacote de configuração nos dispositivos para que eles sejam incluídos no serviço.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769391"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="20402-103">Dispositivos integrados do Windows 10 usando o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="20402-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="20402-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="20402-104">**Applies to:**</span></span>

- [<span data-ttu-id="20402-105">Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="20402-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="20402-106">Gerenciador de Configurações do System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="20402-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="20402-107">Dispositivos integrados usando o System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="20402-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="20402-108">Abra o arquivo. zip do pacote de configuração do Gerenciador de configurações ( *DeviceComplianceOnboardingPackage.zip* ) que você baixou do assistente de integração de serviço.</span><span class="sxs-lookup"><span data-stu-id="20402-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="20402-109">Você também pode obter o pacote do [centro de conformidade da Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="20402-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="20402-110">No painel de navegação, selecione integração de integração do dispositivo de **configuração**  >  **Device Onboarding**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="20402-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="20402-111">No campo **método de implantação** , selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span><span class="sxs-lookup"><span data-stu-id="20402-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="20402-112">Selecione **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="20402-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="20402-113">Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="20402-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="20402-114">Você deve ter um arquivo chamado *DeviceComplianceOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="20402-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="20402-115">Implante o pacote seguindo as etapas descritas no artigo [pacotes e programas no System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .</span><span class="sxs-lookup"><span data-stu-id="20402-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="20402-116">Escolha uma coleção de dispositivos predefinida para implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="20402-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="20402-117">O Microsoft 365 Endpoint Data Loss Prevention não dá suporte à integração durante a fase de [experiência inicial (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) .</span><span class="sxs-lookup"><span data-stu-id="20402-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="20402-118">Certifique-se de que os usuários concluem o OOBE após executar a instalação ou atualização do Windows.</span><span class="sxs-lookup"><span data-stu-id="20402-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="20402-119">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente integrado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="20402-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="20402-120">Para obter mais informações, consulte [executar um teste de detecção em um dispositivo ATP do Microsoft defender recentemente integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span><span class="sxs-lookup"><span data-stu-id="20402-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="20402-121">Observe que é possível criar uma regra de detecção em um aplicativo do Gerenciador de configurações para verificar continuamente se um dispositivo foi integrado.</span><span class="sxs-lookup"><span data-stu-id="20402-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="20402-122">Um aplicativo é um tipo diferente de objeto do que um pacote e programa.</span><span class="sxs-lookup"><span data-stu-id="20402-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="20402-123">Se um dispositivo ainda não estiver integrado (devido à conclusão do OOBE pendente ou a qualquer outro motivo), o Gerenciador de configurações tentará integrar novamente o dispositivo até que a regra detecte a alteração do status.</span><span class="sxs-lookup"><span data-stu-id="20402-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="20402-124">Esse comportamento pode ser feito criando uma regra de detecção verificando se o valor do registro "OnboardingState" (do tipo REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="20402-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="20402-125">Esse valor do registro está localizado em "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="20402-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="20402-126">Para obter mais informações, consulte [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="20402-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="20402-127">Definir configurações de coleção de amostra</span><span class="sxs-lookup"><span data-stu-id="20402-127">Configure sample collection settings</span></span>

<span data-ttu-id="20402-128">Para cada dispositivo, você pode definir um valor de configuração para indicar se os exemplos podem ser coletados do dispositivo quando uma solicitação é feita por meio da central de segurança do Microsoft defender para enviar um arquivo para análise profunda.</span><span class="sxs-lookup"><span data-stu-id="20402-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="20402-129">Essas definições de configuração geralmente são realizadas pelo Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="20402-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="20402-130">Você pode definir uma regra de conformidade para o item de configuração no Gerenciador de configurações para alterar a configuração de compartilhamento de amostra em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20402-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="20402-131">Esta regra deve ser um item de configuração de regra de conformidade de *correção* que define o valor de uma chave de registro em dispositivos de destino para garantir que eles sejam queixas.</span><span class="sxs-lookup"><span data-stu-id="20402-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="20402-132">A configuração é definida por meio da seguinte entrada de chave do registro:</span><span class="sxs-lookup"><span data-stu-id="20402-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="20402-133">Onde:</span><span class="sxs-lookup"><span data-stu-id="20402-133">Where:</span></span><br>
<span data-ttu-id="20402-134">O tipo de chave é uma palavra D.</span><span class="sxs-lookup"><span data-stu-id="20402-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="20402-135">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="20402-135">Possible values are:</span></span>
- <span data-ttu-id="20402-136">0-não permitir o compartilhamento de exemplo deste dispositivo</span><span class="sxs-lookup"><span data-stu-id="20402-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="20402-137">1-permite o compartilhamento de todos os tipos de arquivo deste dispositivo</span><span class="sxs-lookup"><span data-stu-id="20402-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="20402-138">O valor padrão no caso de a chave do registro não existir é 1.</span><span class="sxs-lookup"><span data-stu-id="20402-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="20402-139">Para obter mais informações sobre a conformidade do System Center Configuration Manager, consulte [Introduction to Compliance Settings in System center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="20402-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="20402-140">Outras definições de configuração recomendadas</span><span class="sxs-lookup"><span data-stu-id="20402-140">Other recommended configuration settings</span></span>
<span data-ttu-id="20402-141">Após a integração de dispositivos ao serviço, é importante aproveitar os recursos de proteção contra ameaças incluídos habilitando-os com as seguintes definições de configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="20402-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="20402-142">Configuração do conjunto de dispositivos</span><span class="sxs-lookup"><span data-stu-id="20402-142">Device collection configuration</span></span>
<span data-ttu-id="20402-143">Se você estiver usando o Endpoint Configuration Manager, versão 2002 ou posterior, você pode optar por ampliar a implantação para incluir servidores ou clientes de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="20402-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="20402-144">Configuração de proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="20402-144">Next generation protection configuration</span></span>

<span data-ttu-id="20402-145">As definições de configuração a seguir são recomendadas:</span><span class="sxs-lookup"><span data-stu-id="20402-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="20402-146">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="20402-146">**Scan**</span></span>

- <span data-ttu-id="20402-147">Examinar dispositivos de armazenamento removíveis, como unidades USB: Sim</span><span class="sxs-lookup"><span data-stu-id="20402-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="20402-148">**Proteção em tempo real**</span><span class="sxs-lookup"><span data-stu-id="20402-148">**Real-time Protection**</span></span>

- <span data-ttu-id="20402-149">Habilitar monitoramento comportamental: Sim</span><span class="sxs-lookup"><span data-stu-id="20402-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="20402-150">Habilitar a proteção contra aplicativos potencialmente indesejados no download e antes da instalação: Sim</span><span class="sxs-lookup"><span data-stu-id="20402-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="20402-151">**Serviço de proteção de nuvem**</span><span class="sxs-lookup"><span data-stu-id="20402-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="20402-152">Tipo de associação do serviço de proteção de nuvem: Associação avançada</span><span class="sxs-lookup"><span data-stu-id="20402-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="20402-153">**Redução da superfície de ataque** Configure todas as regras disponíveis para auditoria.</span><span class="sxs-lookup"><span data-stu-id="20402-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="20402-154">Bloquear essas atividades pode interromper processos de negócios legítimos.</span><span class="sxs-lookup"><span data-stu-id="20402-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="20402-155">A melhor abordagem é definir tudo como auditoria, identificar quais são os que são seguros e, em seguida, habilitar essas configurações em pontos de extremidade que não têm detecções falsas positivas.</span><span class="sxs-lookup"><span data-stu-id="20402-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="20402-156">**Proteção de rede**</span><span class="sxs-lookup"><span data-stu-id="20402-156">**Network protection**</span></span>

<span data-ttu-id="20402-157">Antes de habilitar a proteção de rede no modo de auditoria ou de bloqueio, verifique se você instalou a atualização da plataforma Antimalware, que pode ser obtida na [página de suporte](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span><span class="sxs-lookup"><span data-stu-id="20402-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="20402-158">**Acesso a pastas controladas**</span><span class="sxs-lookup"><span data-stu-id="20402-158">**Controlled folder access**</span></span>

<span data-ttu-id="20402-159">Habilite o recurso no modo de auditoria por pelo menos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="20402-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="20402-160">Após esse período, revise as detecções e crie uma lista de aplicativos que têm permissão para gravar em diretórios protegidos.</span><span class="sxs-lookup"><span data-stu-id="20402-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="20402-161">Para obter mais informações, consulte [avaliar acesso a pastas controladas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="20402-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="20402-162">Dispositivos externamente usando o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="20402-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="20402-163">Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="20402-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="20402-164">Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="20402-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="20402-165">Ao baixar um pacote de remoção, você será notificado da data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="20402-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="20402-166">As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="20402-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="20402-167">Dispositivos externamente usando a ramificação atual do Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="20402-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="20402-168">Se você usar a ramificação atual do Microsoft Endpoint Configuration Manager, confira [criar um arquivo de configuração de remoção](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span><span class="sxs-lookup"><span data-stu-id="20402-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="20402-169">Dispositivos externamente usando o Gerenciador de configuração do System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="20402-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="20402-170">Obtenha o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="20402-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="20402-171">No painel de navegação, selecione remoção de configuração de dispositivo de **configurações**  >   **Device onboarding** >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="20402-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="20402-172">Selecione Windows 10 como sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="20402-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="20402-173">No campo **método de implantação** , selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span><span class="sxs-lookup"><span data-stu-id="20402-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="20402-174">Selecione **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="20402-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="20402-175">Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="20402-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="20402-176">Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="20402-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="20402-177">Implante o pacote seguindo as etapas descritas no artigo [pacotes e programas no System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .</span><span class="sxs-lookup"><span data-stu-id="20402-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="20402-178">Escolha uma coleção de dispositivos predefinida para implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="20402-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20402-179">A remoção faz com que o dispositivo pare de enviar dados de sensor para o portal, mas os dados do dispositivo, incluindo referência a qualquer alerta que tenha tido, serão mantidos por até seis meses.</span><span class="sxs-lookup"><span data-stu-id="20402-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="20402-180">Monitorar a configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="20402-180">Monitor device configuration</span></span>

<span data-ttu-id="20402-181">Se você estiver usando a ramificação atual do Microsoft Endpoint Configuration Manager, use o painel interno do Microsoft defender ATP no console do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="20402-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="20402-182">Para obter mais informações, consulte [Microsoft defender Advanced Threat Protection-monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="20402-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="20402-183">Se você estiver usando o System Center 2012 R2 Configuration Manager, o monitoramento consiste em duas partes:</span><span class="sxs-lookup"><span data-stu-id="20402-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="20402-184">A confirmação do pacote de configuração foi implantada corretamente e está em execução (ou foi executada com êxito) nos dispositivos da sua rede.</span><span class="sxs-lookup"><span data-stu-id="20402-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="20402-185">Verificar se os dispositivos estão em conformidade com o serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365 (isso garante que o dispositivo possa concluir o processo de integração e que possa continuar a relatar dados para o serviço).</span><span class="sxs-lookup"><span data-stu-id="20402-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="20402-186">Confirmar se o pacote de configuração foi implantado corretamente</span><span class="sxs-lookup"><span data-stu-id="20402-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="20402-187">No console do Gerenciador de configurações, clique em **monitoramento** na parte inferior do painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="20402-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="20402-188">Selecione **visão geral** e **implantações** .</span><span class="sxs-lookup"><span data-stu-id="20402-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="20402-189">Selecione na implantação com o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="20402-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="20402-190">Revise os indicadores de status sob **Estatísticas de conclusão** e **status do conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="20402-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="20402-191">Se houver falha nas implantações (dispositivos com **erro** , **requisitos não atendidos** ou **status de falha** ), talvez seja necessário solucionar problemas dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="20402-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="20402-192">Para saber mais, confira [solucionar problemas de integração da proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="20402-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Gerenciador de configurações mostrando uma implantação bem-sucedida sem erros](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="20402-194">Verifique se os dispositivos são compatíveis com o serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20402-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="20402-195">Você pode definir uma regra de conformidade para o item de configuração no System Center 2012 R2 Configuration Manager para monitorar sua implantação.</span><span class="sxs-lookup"><span data-stu-id="20402-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="20402-196">Este procedimento e a entrada do registro se aplicam ao Endpoint DLP, bem como à proteção avançada contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="20402-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="20402-197">Esta regra deve ser um item de configuração de regra de conformidade de *não correção* que monitora o valor de uma chave do registro em dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="20402-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="20402-198">Monitore a seguinte entrada de chave do registro:</span><span class="sxs-lookup"><span data-stu-id="20402-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="20402-199">Para obter mais informações, consulte [introdução às configurações de conformidade no System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="20402-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="20402-200">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="20402-200">Related topics</span></span>
- [<span data-ttu-id="20402-201">Dispositivos Windows 10 integrados usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="20402-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="20402-202">Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="20402-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="20402-203">Dispositivos integrados do Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="20402-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="20402-204">Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="20402-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="20402-205">Executar um teste de detecção em um dispositivo Microsoft defender ATP recentemente integrado</span><span class="sxs-lookup"><span data-stu-id="20402-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="20402-206">Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="20402-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
