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
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230002"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="f2f31-104">Configurar o Microsoft Defender para Ponto de Extremidade em recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="f2f31-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2f31-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f2f31-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2f31-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f2f31-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2f31-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2f31-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2f31-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f2f31-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2f31-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f2f31-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="f2f31-110">O Defender for Endpoint no iOS usaria uma VPN para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="f2f31-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="f2f31-111">Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f2f31-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="f2f31-112">Acesso condicional com o Defender para Ponto de Extremidade no iOS</span><span class="sxs-lookup"><span data-stu-id="f2f31-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="f2f31-113">O Microsoft Defender for Endpoint no iOS juntamente com o Microsoft Intune e Azure Active Directory permite aplicar políticas de conformidade de dispositivo e Acesso Condicional com base na pontuação de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f2f31-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="f2f31-114">O Defender for Endpoint é uma solução MTD (Mobile Threat Defense) que você pode implantar para aproveitar esse recurso por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="f2f31-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="f2f31-115">Para obter mais informações sobre como configurar o Acesso Condicional com o Defender para Ponto de Extremidade no iOS, consulte [Defender for Endpoint e Intune](/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="f2f31-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="f2f31-116">Detecção de jailbreak pelo Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f2f31-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="f2f31-117">O Microsoft Defender para Ponto de Extremidade tem a capacidade de detectar dispositivos gerenciados e não gerenciados que são jailbroken.</span><span class="sxs-lookup"><span data-stu-id="f2f31-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="f2f31-118">Se um dispositivo for detectado como jailbroken, um alerta de alto risco será relatado ao Centro de Segurança e se o Acesso Condicional for configurado com base na pontuação de risco do dispositivo, o dispositivo será impedido de acessar dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="f2f31-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="f2f31-119">Proteção da Web e VPN</span><span class="sxs-lookup"><span data-stu-id="f2f31-119">Web Protection and VPN</span></span>

<span data-ttu-id="f2f31-120">Por padrão, o Defender para Ponto de Extremidade no iOS inclui e habilita o recurso de proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="f2f31-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="f2f31-121">[A proteção da Web](web-protection-overview.md) ajuda a proteger dispositivos contra ameaças da Web e proteger os usuários contra ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="f2f31-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="f2f31-122">O Defender for Endpoint no iOS usa uma VPN para fornecer essa proteção.</span><span class="sxs-lookup"><span data-stu-id="f2f31-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="f2f31-123">Observe que esta é uma VPN local e, ao contrário da VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f2f31-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="f2f31-124">Embora habilitada por padrão, pode haver alguns casos que exigem que você desabilite a VPN.</span><span class="sxs-lookup"><span data-stu-id="f2f31-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="f2f31-125">Por exemplo, você deseja executar alguns aplicativos que não funcionam quando uma VPN está configurada.</span><span class="sxs-lookup"><span data-stu-id="f2f31-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="f2f31-126">Nesses casos, você pode optar por desabilitar a VPN do aplicativo no dispositivo seguindo as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="f2f31-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="f2f31-127">Em seu dispositivo iOS, abra o aplicativo **Configurações,** clique ou toque em **Geral** **e,** em seguida, VPN .</span><span class="sxs-lookup"><span data-stu-id="f2f31-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="f2f31-128">Clique ou toque no botão "i" do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f2f31-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="f2f31-129">Desative o **Conexão Sob Demanda para** desabilitar a VPN.</span><span class="sxs-lookup"><span data-stu-id="f2f31-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f2f31-130">![Vpn config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="f2f31-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="f2f31-131">A Proteção da Web não estará disponível quando a VPN estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f2f31-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="f2f31-132">Para habilitar a Proteção Web de novo, abra o aplicativo Microsoft Defender para Ponto de Extremidade no dispositivo e clique ou toque em **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="f2f31-133">Co-existência de vários perfis VPN</span><span class="sxs-lookup"><span data-stu-id="f2f31-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="f2f31-134">O iOS da Apple não dá suporte a várias VPNs em todo o dispositivo para serem ativas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f2f31-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="f2f31-135">Embora vários perfis VPN possam existir no dispositivo, apenas uma VPN pode estar ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="f2f31-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="f2f31-136">Configurar o sinal de risco do Microsoft Defender para Ponto de Extremidade na política de proteção de aplicativos (MAM)</span><span class="sxs-lookup"><span data-stu-id="f2f31-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="f2f31-137">O Microsoft Defender for Endpoint pode ser configurado para enviar sinais de ameaça a serem usados em Políticas de Proteção de Aplicativos (APP, também conhecido como MAM) no iOS/iPadOS.</span><span class="sxs-lookup"><span data-stu-id="f2f31-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="f2f31-138">Com esse recurso, você também pode usar o Microsoft Defender para o Ponto de Extremidade para proteger o acesso aos dados corporativos de dispositivos não reemrollados.</span><span class="sxs-lookup"><span data-stu-id="f2f31-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="f2f31-139">As etapas para configurar políticas de proteção de aplicativos com o Microsoft Defender para Ponto de Extremidade estão abaixo:</span><span class="sxs-lookup"><span data-stu-id="f2f31-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="f2f31-140">Configurar a conexão do seu locatário Microsoft Endpoint Manager o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f2f31-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f2f31-141">No Centro de administração do Gerenciador de Ponto de Extremidade da [Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), vá para Conectores de Administração de Locatários e tokens do Microsoft Defender para Ponto de Extremidade (em Plataforma Cruzada) ou Segurança de Ponto de Extremidade do Microsoft Defender para Ponto de Extremidade (em Instalação) e a ata as alternâncias em Política de Proteção de  >    >   Aplicativo Configurações   >   **para iOS**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="f2f31-142">Selecione Salvar.</span><span class="sxs-lookup"><span data-stu-id="f2f31-142">Select Save.</span></span> <span data-ttu-id="f2f31-143">Você deve ver **que o status da conexão** agora está definido como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="f2f31-144">Criar política de proteção de aplicativo: depois que a configuração do conector do Microsoft Defender for Endpoint for concluída, navegue até **Políticas** de proteção de aplicativos (em Política) para criar uma nova política ou atualizar  >   uma existente.</span><span class="sxs-lookup"><span data-stu-id="f2f31-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="f2f31-145">Selecione a plataforma, **aplicativos, proteção de dados, configurações** de requisitos do Access que sua organização exige para sua política.</span><span class="sxs-lookup"><span data-stu-id="f2f31-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="f2f31-146">Em **Condições de lançamento condicional** Do dispositivo, você encontrará a configuração Nível máximo de ameaça de dispositivo  >   **permitido.**</span><span class="sxs-lookup"><span data-stu-id="f2f31-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="f2f31-147">Isso precisará ser configurado para Baixo, Médio, Alto ou Protegido.</span><span class="sxs-lookup"><span data-stu-id="f2f31-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="f2f31-148">As ações disponíveis para você serão Bloquear o **acesso ou** **apagar dados**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="f2f31-149">Você pode ver uma caixa de diálogo informacional para garantir que seu conector seja definido antes que essa configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="f2f31-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="f2f31-150">Se o conector já estiver definido, você poderá ignorar essa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f2f31-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="f2f31-151">Termine com atribuições e salve sua política.</span><span class="sxs-lookup"><span data-stu-id="f2f31-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="f2f31-152">Para obter mais detalhes sobre a política de proteção de aplicativos ou MAM, consulte configurações da política de proteção de [aplicativos do iOS.](/mem/intune/apps/app-protection-policy-settings-ios)</span><span class="sxs-lookup"><span data-stu-id="f2f31-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="f2f31-153">Implantando o Microsoft Defender para Ponto de Extremidade para MAM ou em dispositivos não reemrollados</span><span class="sxs-lookup"><span data-stu-id="f2f31-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="f2f31-154">O Microsoft Defender para Ponto de Extremidade no iOS habilita o cenário de Política de Proteção de Aplicativos e está disponível na Loja de Aplicativos da Apple.</span><span class="sxs-lookup"><span data-stu-id="f2f31-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="f2f31-155">Os usuários finais devem instalar a versão mais recente do aplicativo diretamente na Loja de Aplicativos da Apple.</span><span class="sxs-lookup"><span data-stu-id="f2f31-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="f2f31-156">Configurar a política de conformidade em dispositivos com cadeia de segurança</span><span class="sxs-lookup"><span data-stu-id="f2f31-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="f2f31-157">Para proteger os dados corporativos de serem acessados em dispositivos iOS de cadeia, recomendamos que você defina a seguinte política de conformidade no Intune.</span><span class="sxs-lookup"><span data-stu-id="f2f31-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="f2f31-158">A detecção de jailbreak é um recurso fornecido pelo Microsoft Defender para Endpoint no iOS.</span><span class="sxs-lookup"><span data-stu-id="f2f31-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="f2f31-159">No entanto, recomendamos que você configure essa política como uma camada adicional de defesa contra cenários de jailbreak.</span><span class="sxs-lookup"><span data-stu-id="f2f31-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="f2f31-160">Siga as etapas a seguir para criar uma política de conformidade contra dispositivos com cadeia de segurança.</span><span class="sxs-lookup"><span data-stu-id="f2f31-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="f2f31-161">No [Microsoft Endpoint Manager de administração,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Políticas** de Conformidade  ->  **de**  ->  **Dispositivos Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="f2f31-162">Selecione "iOS/iPadOS" como plataforma e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f2f31-163">![Criar Política](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="f2f31-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="f2f31-164">Especifique um nome da política, por exemplo "Política de Conformidade para Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="f2f31-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="f2f31-165">Na página configurações de conformidade, clique para expandir a seção **Saúde do** Dispositivo e clique **em Bloquear** para **dispositivos jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="f2f31-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f2f31-166">![Política Configurações](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="f2f31-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="f2f31-167">Na seção **Ação para não conformidade,** selecione as ações de acordo com seus requisitos e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f2f31-168">![Ações de política](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="f2f31-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="f2f31-169">Na seção **Atribuições,** selecione os grupos de usuários que você deseja incluir para esta política e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="f2f31-170">Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f2f31-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="f2f31-171">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="f2f31-171">Configure custom indicators</span></span>

<span data-ttu-id="f2f31-172">O Defender for Endpoint no iOS permite que os administradores configurem indicadores personalizados em dispositivos iOS também.</span><span class="sxs-lookup"><span data-stu-id="f2f31-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="f2f31-173">Para obter mais informações sobre como configurar indicadores personalizados, consulte [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="f2f31-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="f2f31-174">O Defender para Ponto de Extremidade no iOS dá suporte à criação de indicadores personalizados apenas para endereços IP e URLs/domínios.</span><span class="sxs-lookup"><span data-stu-id="f2f31-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="f2f31-175">Relatar site não seguro</span><span class="sxs-lookup"><span data-stu-id="f2f31-175">Report unsafe site</span></span>

<span data-ttu-id="f2f31-176">Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras.</span><span class="sxs-lookup"><span data-stu-id="f2f31-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="f2f31-177">Visite a [página Fornecer comentários sobre a](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) proteção de rede se quiser relatar um site que pode ser um site de phishing.</span><span class="sxs-lookup"><span data-stu-id="f2f31-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

