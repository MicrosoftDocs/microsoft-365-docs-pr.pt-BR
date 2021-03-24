---
title: Configurar o Microsoft Defender ATP para recursos do iOS
description: Descreve como implantar o Microsoft Defender ATP para recursos iOS
keywords: microsoft, defender, atp, ios, configurar, recursos, ios
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b9f4372321bfa17ce5c11081ca274a3360e18dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053403"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="0ebfc-104">Configurar o Microsoft Defender para Ponto de Extremidade para recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="0ebfc-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ebfc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0ebfc-105">**Applies to:**</span></span>
- [<span data-ttu-id="0ebfc-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0ebfc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0ebfc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ebfc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0ebfc-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0ebfc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0ebfc-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="0ebfc-110">O Defender for Endpoint para iOS usaria uma VPN para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0ebfc-111">Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="0ebfc-112">Acesso condicional com o Defender para Ponto de Extremidade para iOS</span><span class="sxs-lookup"><span data-stu-id="0ebfc-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="0ebfc-113">O Microsoft Defender for Endpoint para iOS juntamente com o Microsoft Intune e o Azure Active Directory permite a aplicação de políticas de conformidade de dispositivo e acesso condicional com base nos níveis de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="0ebfc-114">O Defender for Endpoint é uma solução MTD (Mobile Threat Defense) que você pode implantar para aproveitar esse recurso por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="0ebfc-115">Para obter mais informações sobre como configurar o Acesso Condicional com o Defender para Ponto de Extremidade para iOS, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="0ebfc-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="0ebfc-116">Proteção da Web e VPN</span><span class="sxs-lookup"><span data-stu-id="0ebfc-116">Web Protection and VPN</span></span>

<span data-ttu-id="0ebfc-117">Por padrão, o Defender para Ponto de Extremidade para iOS inclui e habilita o recurso de proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="0ebfc-118">[A proteção da Web](web-protection-overview.md) ajuda a proteger dispositivos contra ameaças da Web e proteger os usuários contra ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="0ebfc-119">O Defender para Ponto de Extremidade para iOS usa uma VPN para fornecer essa proteção.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="0ebfc-120">Observe que esta é uma VPN local e, ao contrário da VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="0ebfc-121">Embora habilitada por padrão, pode haver alguns casos que exigem que você desabilite a VPN.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="0ebfc-122">Por exemplo, você deseja executar alguns aplicativos que não funcionam quando uma VPN está configurada.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="0ebfc-123">Nesses casos, você pode optar por desabilitar a VPN do aplicativo no dispositivo seguindo as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="0ebfc-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="0ebfc-124">Em seu dispositivo iOS, abra o aplicativo **Configurações,** clique ou toque em **Geral** **e,** em seguida, VPN .</span><span class="sxs-lookup"><span data-stu-id="0ebfc-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="0ebfc-125">Clique ou toque no botão "i" do Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="0ebfc-126">Desative o **Connect On Demand para** desabilitar a VPN.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ebfc-127">![Vpn config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="0ebfc-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0ebfc-128">A Proteção da Web não estará disponível quando a VPN estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="0ebfc-129">Para habilitar a Proteção Web de novo, abra o aplicativo Microsoft Defender para Ponto de Extremidade no dispositivo e clique ou toque em **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="0ebfc-130">Co-existência de vários perfis VPN</span><span class="sxs-lookup"><span data-stu-id="0ebfc-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="0ebfc-131">O iOS da Apple não dá suporte a várias VPNs em todo o dispositivo para serem ativas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="0ebfc-132">Embora vários perfis VPN possam existir no dispositivo, apenas uma VPN pode estar ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="0ebfc-133">Configurar a política de conformidade em dispositivos com cadeia de segurança</span><span class="sxs-lookup"><span data-stu-id="0ebfc-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="0ebfc-134">Para proteger os dados corporativos de serem acessados em dispositivos iOS de cadeia, recomendamos que você defina a seguinte política de conformidade no Intune.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="0ebfc-135">No momento, o Microsoft Defender para Ponto de Extremidade para iOS não oferece proteção contra cenários de jailbreak.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="0ebfc-136">Se usado em um dispositivo jailbroken, em cenários específicos, os dados que são usados pelo aplicativo, como sua id de email corporativa e imagem de perfil corporativo (se disponível) podem ser expostos localmente</span><span class="sxs-lookup"><span data-stu-id="0ebfc-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="0ebfc-137">Siga as etapas a seguir para criar uma política de conformidade contra dispositivos com cadeia de segurança.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="0ebfc-138">No [Centro de administração do Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Políticas** de Conformidade  ->  **de**  ->  **Dispositivos Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="0ebfc-139">Selecione "iOS/iPadOS" como plataforma e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ebfc-140">![Criar Política](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0ebfc-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="0ebfc-141">Especifique um nome da política, por exemplo "Política de Conformidade para Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="0ebfc-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="0ebfc-142">Na página configurações de conformidade, clique para expandir a seção **Saúde do** Dispositivo e clique **em Bloquear** para **dispositivos jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="0ebfc-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ebfc-143">![Configurações de Política](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0ebfc-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="0ebfc-144">Na seção *Ação para não conformidade,* selecione as ações de acordo com seus requisitos e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ebfc-145">![Ações de política](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0ebfc-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="0ebfc-146">Na seção *Atribuições,* selecione os grupos de usuários que você deseja incluir para esta política e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="0ebfc-147">Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="0ebfc-148">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="0ebfc-148">Configure custom indicators</span></span>

<span data-ttu-id="0ebfc-149">O Defender para Ponto de Extremidade para iOS também permite que os administradores configurem indicadores personalizados em dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="0ebfc-150">Para obter mais informações sobre como configurar indicadores personalizados, consulte [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="0ebfc-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="0ebfc-151">O Defender para Ponto de Extremidade para iOS dá suporte à criação de indicadores personalizados apenas para endereços IP e URLs/domínios.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="0ebfc-152">Relatar site não seguro</span><span class="sxs-lookup"><span data-stu-id="0ebfc-152">Report unsafe site</span></span>

<span data-ttu-id="0ebfc-153">Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="0ebfc-154">Visite a [página Fornecer comentários sobre a](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) proteção de rede se quiser relatar um site que pode ser um site de phishing.</span><span class="sxs-lookup"><span data-stu-id="0ebfc-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>
