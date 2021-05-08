---
title: Configurar o Microsoft Defender para Ponto de Extremidade em recursos do iOS
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade em recursos do iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245271"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="884e1-104">Configurar o Microsoft Defender para Ponto de Extremidade em recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="884e1-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="884e1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="884e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="884e1-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="884e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="884e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="884e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="884e1-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="884e1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="884e1-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="884e1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="884e1-110">O Defender for Endpoint no iOS usaria uma VPN para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="884e1-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="884e1-111">Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="884e1-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="884e1-112">Acesso condicional com o Defender para Ponto de Extremidade no iOS</span><span class="sxs-lookup"><span data-stu-id="884e1-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="884e1-113">O Microsoft Defender for Endpoint no iOS juntamente com o Microsoft Intune e Azure Active Directory permite aplicar políticas de conformidade de dispositivo e Acesso Condicional com base na pontuação de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="884e1-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="884e1-114">O Defender for Endpoint é uma solução MTD (Mobile Threat Defense) que você pode implantar para aproveitar esse recurso por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="884e1-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="884e1-115">Para obter mais informações sobre como configurar o Acesso Condicional com o Defender para Ponto de Extremidade no iOS, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="884e1-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="884e1-116">**A detecção de jailbreak pelo Microsoft Defender para Ponto de Extremidade no iOS está atualmente em visualização**.</span><span class="sxs-lookup"><span data-stu-id="884e1-116">**Jailbreak detection by Microsoft Defender for Endpoint on iOS is currently in preview**.</span></span> <span data-ttu-id="884e1-117">Se um dispositivo for detectado como jailbroken pelo Microsoft Defender para Ponto de Extremidade, um alerta de alto risco será relatado para a Central de Segurança e se o Acesso Condicional for configurado com base na pontuação de risco do dispositivo, o dispositivo será impedido de acessar dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="884e1-117">If a device is detected to be jailbroken by Microsoft Defender for Endpoint, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="884e1-118">Proteção da Web e VPN</span><span class="sxs-lookup"><span data-stu-id="884e1-118">Web Protection and VPN</span></span>

<span data-ttu-id="884e1-119">Por padrão, o Defender para Ponto de Extremidade no iOS inclui e habilita o recurso de proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="884e1-119">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="884e1-120">[A proteção da Web](web-protection-overview.md) ajuda a proteger dispositivos contra ameaças da Web e proteger os usuários contra ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="884e1-120">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="884e1-121">O Defender for Endpoint no iOS usa uma VPN para fornecer essa proteção.</span><span class="sxs-lookup"><span data-stu-id="884e1-121">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="884e1-122">Observe que esta é uma VPN local e, ao contrário da VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="884e1-122">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="884e1-123">Embora habilitada por padrão, pode haver alguns casos que exigem que você desabilite a VPN.</span><span class="sxs-lookup"><span data-stu-id="884e1-123">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="884e1-124">Por exemplo, você deseja executar alguns aplicativos que não funcionam quando uma VPN está configurada.</span><span class="sxs-lookup"><span data-stu-id="884e1-124">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="884e1-125">Nesses casos, você pode optar por desabilitar a VPN do aplicativo no dispositivo seguindo as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="884e1-125">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="884e1-126">Em seu dispositivo iOS, abra o aplicativo **Configurações,** clique ou toque em **Geral** **e,** em seguida, VPN .</span><span class="sxs-lookup"><span data-stu-id="884e1-126">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="884e1-127">Clique ou toque no botão "i" do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="884e1-127">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="884e1-128">Desative o **Conexão Sob Demanda para** desabilitar a VPN.</span><span class="sxs-lookup"><span data-stu-id="884e1-128">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="884e1-129">![Vpn config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="884e1-129">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="884e1-130">A Proteção da Web não estará disponível quando a VPN estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="884e1-130">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="884e1-131">Para habilitar a Proteção Web de novo, abra o aplicativo Microsoft Defender para Ponto de Extremidade no dispositivo e clique ou toque em **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="884e1-131">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="884e1-132">Co-existência de vários perfis VPN</span><span class="sxs-lookup"><span data-stu-id="884e1-132">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="884e1-133">O iOS da Apple não dá suporte a várias VPNs em todo o dispositivo para serem ativas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="884e1-133">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="884e1-134">Embora vários perfis VPN possam existir no dispositivo, apenas uma VPN pode estar ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="884e1-134">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="884e1-135">Configurar a política de conformidade em dispositivos com cadeia de segurança</span><span class="sxs-lookup"><span data-stu-id="884e1-135">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="884e1-136">Para proteger os dados corporativos de serem acessados em dispositivos iOS de cadeia, recomendamos que você defina a seguinte política de conformidade no Intune.</span><span class="sxs-lookup"><span data-stu-id="884e1-136">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="884e1-137">Neste momento, a detecção de jailbreak pelo Microsoft Defender para Ponto de Extremidade no iOS está em visualização.</span><span class="sxs-lookup"><span data-stu-id="884e1-137">At this time jailbreak detection by Microsoft Defender for Endpoint on iOS is in preview.</span></span> <span data-ttu-id="884e1-138">Recomendamos que você configure essa política como uma camada adicional de defesa contra cenários de jailbreak.</span><span class="sxs-lookup"><span data-stu-id="884e1-138">We recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="884e1-139">Siga as etapas a seguir para criar uma política de conformidade contra dispositivos com cadeia de segurança.</span><span class="sxs-lookup"><span data-stu-id="884e1-139">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="884e1-140">No [Microsoft Endpoint Manager de administração,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Políticas** de Conformidade  ->  **de**  ->  **Dispositivos Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="884e1-140">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="884e1-141">Selecione "iOS/iPadOS" como plataforma e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="884e1-141">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="884e1-142">![Criar Política](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="884e1-142">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="884e1-143">Especifique um nome da política, por exemplo "Política de Conformidade para Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="884e1-143">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="884e1-144">Na página configurações de conformidade, clique para expandir a seção **Saúde do** Dispositivo e clique **em Bloquear** para **dispositivos jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="884e1-144">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="884e1-145">![Política Configurações](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="884e1-145">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="884e1-146">Na seção *Ação para não conformidade,* selecione as ações de acordo com seus requisitos e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="884e1-146">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="884e1-147">![Ações de política](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="884e1-147">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="884e1-148">Na seção *Atribuições,* selecione os grupos de usuários que você deseja incluir para esta política e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="884e1-148">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="884e1-149">Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="884e1-149">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="884e1-150">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="884e1-150">Configure custom indicators</span></span>

<span data-ttu-id="884e1-151">O Defender for Endpoint no iOS permite que os administradores configurem indicadores personalizados em dispositivos iOS também.</span><span class="sxs-lookup"><span data-stu-id="884e1-151">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="884e1-152">Para obter mais informações sobre como configurar indicadores personalizados, consulte [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="884e1-152">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="884e1-153">O Defender para Ponto de Extremidade no iOS dá suporte à criação de indicadores personalizados apenas para endereços IP e URLs/domínios.</span><span class="sxs-lookup"><span data-stu-id="884e1-153">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="884e1-154">Relatar site não seguro</span><span class="sxs-lookup"><span data-stu-id="884e1-154">Report unsafe site</span></span>

<span data-ttu-id="884e1-155">Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras.</span><span class="sxs-lookup"><span data-stu-id="884e1-155">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="884e1-156">Visite a [página Fornecer comentários sobre a](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) proteção de rede se quiser relatar um site que pode ser um site de phishing.</span><span class="sxs-lookup"><span data-stu-id="884e1-156">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="884e1-157">Problemas de consumo de bateria no iOS quando o Microsoft Defender for Endpoint está instalado</span><span class="sxs-lookup"><span data-stu-id="884e1-157">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="884e1-158">O uso da bateria por um aplicativo é calculado pela Apple com base em uma infinidade de fatores, incluindo o uso da CPU e da rede.</span><span class="sxs-lookup"><span data-stu-id="884e1-158">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="884e1-159">O Microsoft Defender para Ponto de Extremidade usa uma VPN local/loop-back em segundo plano para verificar o tráfego da Web em busca de sites ou conexões mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="884e1-159">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="884e1-160">Os pacotes de rede de qualquer aplicativo passam por essa verificação e isso faz com que o uso da bateria do Microsoft Defender para o Ponto de Extremidade seja calculado de forma impreciso.</span><span class="sxs-lookup"><span data-stu-id="884e1-160">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="884e1-161">Isso dá uma falsa impressão ao usuário.</span><span class="sxs-lookup"><span data-stu-id="884e1-161">This gives a false impression to the user.</span></span> <span data-ttu-id="884e1-162">O consumo real de bateria do Microsoft Defender para Ponto de Extremidade é menor do que o mostrado na página Bateria Configurações no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="884e1-162">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="884e1-163">Isso se baseia em testes realizados no aplicativo Microsoft Defender para Ponto de Extremidade para entender o consumo de bateria.</span><span class="sxs-lookup"><span data-stu-id="884e1-163">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="884e1-164">Além disso, a VPN usada é uma VPN local e, ao contrário das VPNs tradicionais, o tráfego de rede não é enviado fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="884e1-164">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
