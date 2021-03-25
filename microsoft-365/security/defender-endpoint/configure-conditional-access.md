---
title: Configurar o Acesso Condicional no Microsoft Defender ATP
description: Saiba mais sobre as etapas que você precisa fazer no Intune, no Centro de Segurança do Microsoft Defender e no Azure para implementar o acesso condicional
keywords: acesso condicional, condicional, acesso, risco de dispositivo, nível de risco, integração, integração do intune
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165856"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a6544-104">Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a6544-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6544-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a6544-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6544-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a6544-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6544-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6544-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a6544-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a6544-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6544-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a6544-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="a6544-110">Esta seção orienta você por todas as etapas necessárias para implementar corretamente o Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="a6544-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="a6544-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a6544-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="a6544-112">É importante observar que não há suporte para dispositivos registrados no Azure AD neste cenário.</span><span class="sxs-lookup"><span data-stu-id="a6544-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="a6544-113">Somente dispositivos inscritos do Intune têm suporte.</span><span class="sxs-lookup"><span data-stu-id="a6544-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="a6544-114">Você precisa se certificar de que todos os seus dispositivos estão inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="a6544-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="a6544-115">Você pode usar qualquer uma das seguintes opções para registrar dispositivos no Intune:</span><span class="sxs-lookup"><span data-stu-id="a6544-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="a6544-116">Administrador de IT: Para obter mais informações sobre como habilenciar o registro automático, consulte [Registro do Windows](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="a6544-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="a6544-117">Usuário final: para obter mais informações sobre como registrar seu dispositivo Windows 10 no Intune, consulte Registrar seu dispositivo [Windows 10 no Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="a6544-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="a6544-118">Alternativa para o usuário final: para obter mais informações sobre como ingressar em um domínio do Azure AD, consulte Como: Planejar a implementação de junção do [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span><span class="sxs-lookup"><span data-stu-id="a6544-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="a6544-119">Há etapas que você precisará seguir no Centro de Segurança do Microsoft Defender, no portal do Intune e no portal do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a6544-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="a6544-120">É importante observar as funções necessárias para acessar esses portais e implementar o acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="a6544-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="a6544-121">**Centro de Segurança** do Microsoft Defender - Você precisará entrar no portal com uma função de administrador global para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="a6544-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="a6544-122">**Intune** - Você precisará entrar no portal com direitos de administrador de segurança com permissões de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a6544-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="a6544-123">**Portal do Azure AD** - Você precisará entrar como administrador global, administrador de segurança ou administrador de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="a6544-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="a6544-124">Você precisará de um ambiente do Microsoft Intune, com o Intune gerenciado e o Azure AD ingressado em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a6544-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="a6544-125">Tome as seguintes etapas para habilitar o Acesso Condicional:</span><span class="sxs-lookup"><span data-stu-id="a6544-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="a6544-126">Etapa 1: Ativar a conexão do Microsoft Intune do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a6544-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="a6544-127">Etapa 2: Ativar a integração do Defender para Ponto de Extremidade no Intune</span><span class="sxs-lookup"><span data-stu-id="a6544-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="a6544-128">Etapa 3: Criar a política de conformidade no Intune</span><span class="sxs-lookup"><span data-stu-id="a6544-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="a6544-129">Etapa 4: Atribuir a política</span><span class="sxs-lookup"><span data-stu-id="a6544-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="a6544-130">Etapa 5: Criar uma política de Acesso Condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="a6544-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="a6544-131">Etapa 1: Ativar a conexão do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a6544-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="a6544-132">No painel de navegação, selecione **Configurações**  >  **Recursos avançados da** conexão do Microsoft  >  **Intune.**</span><span class="sxs-lookup"><span data-stu-id="a6544-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="a6544-133">Alterne a configuração do Microsoft Intune para **On**.</span><span class="sxs-lookup"><span data-stu-id="a6544-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="a6544-134">Clique **em Salvar preferências**.</span><span class="sxs-lookup"><span data-stu-id="a6544-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="a6544-135">Etapa 2: Ativar a integração do Defender para Ponto de Extremidade no Intune</span><span class="sxs-lookup"><span data-stu-id="a6544-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="a6544-136">Entre no [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a6544-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a6544-137">Selecione **Conformidade de dispositivo** Microsoft Defender  >  **ATP**.</span><span class="sxs-lookup"><span data-stu-id="a6544-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="a6544-138">De **definir conectar dispositivos Windows 10.0.15063+** a Proteção Avançada contra Ameaças do Microsoft Defender como **Ligado.**</span><span class="sxs-lookup"><span data-stu-id="a6544-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="a6544-139">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a6544-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="a6544-140">Etapa 3: Criar a política de conformidade no Intune</span><span class="sxs-lookup"><span data-stu-id="a6544-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="a6544-141">No portal [do Azure,](https://portal.azure.com)selecione **Todos os serviços,** filtre **no Intune** e selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6544-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="a6544-142">Selecione **Políticas de conformidade de**  >  **dispositivo** Criar  >  **política**.</span><span class="sxs-lookup"><span data-stu-id="a6544-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="a6544-143">Insira um **Nome e** **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="a6544-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="a6544-144">Em **Plataforma,** selecione **Windows 10 e posterior**.</span><span class="sxs-lookup"><span data-stu-id="a6544-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="a6544-145">Nas **configurações de Saúde** do Dispositivo, desempate Exigir que o dispositivo seja **ou sob** o Nível de Ameaça de Dispositivo para o nível preferencial:</span><span class="sxs-lookup"><span data-stu-id="a6544-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="a6544-146">**Protegido**: esse nível é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="a6544-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="a6544-147">O dispositivo não pode ter ameaças existentes e ainda acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="a6544-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="a6544-148">Se alguma ameaça for encontrada, o dispositivo será avaliado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="a6544-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="a6544-149">**Baixo**: o dispositivo é compatível se existirem apenas ameaças de baixo nível.</span><span class="sxs-lookup"><span data-stu-id="a6544-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="a6544-150">Dispositivos com níveis médios ou altos de ameaça não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="a6544-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="a6544-151">**Médio**: o dispositivo é compatível se as ameaças encontradas no dispositivo são baixas ou médias.</span><span class="sxs-lookup"><span data-stu-id="a6544-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="a6544-152">Se ameaças de alto nível são detectadas, o dispositivo é determinado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="a6544-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="a6544-153">**Alto**: esse nível é o menos seguro e permite todos os níveis de ameaça.</span><span class="sxs-lookup"><span data-stu-id="a6544-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="a6544-154">Portanto, dispositivos que com níveis de ameaça altos, médios ou baixos são considerados compatíveis.</span><span class="sxs-lookup"><span data-stu-id="a6544-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="a6544-155">Selecione **OK** e **Criar para** salvar suas alterações (e criar a política).</span><span class="sxs-lookup"><span data-stu-id="a6544-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="a6544-156">Etapa 4: Atribuir a política</span><span class="sxs-lookup"><span data-stu-id="a6544-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="a6544-157">No portal [do Azure,](https://portal.azure.com)selecione **Todos os serviços,** filtre **no Intune** e selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6544-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="a6544-158">Selecione **Políticas de conformidade** de dispositivo> sua política de conformidade do Microsoft Defender  >   ATP.</span><span class="sxs-lookup"><span data-stu-id="a6544-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="a6544-159">Selecione **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="a6544-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="a6544-160">Inclua ou exclua seus grupos do Azure AD para atribuir a política a eles.</span><span class="sxs-lookup"><span data-stu-id="a6544-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="a6544-161">Para implantar a política nos grupos, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a6544-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="a6544-162">Os dispositivos de usuário direcionados pela política são avaliados para conformidade.</span><span class="sxs-lookup"><span data-stu-id="a6544-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="a6544-163">Etapa 5: Criar uma política de Acesso Condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="a6544-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="a6544-164">No portal [do Azure,](https://portal.azure.com)abra a nova política de Acesso Condicional do **Azure Active Directory**  >    >  .</span><span class="sxs-lookup"><span data-stu-id="a6544-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="a6544-165">Insira um nome **de política** e selecione Usuários **e grupos.**</span><span class="sxs-lookup"><span data-stu-id="a6544-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="a6544-166">Use as opções Incluir ou Excluir para adicionar seus grupos para a política e selecione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="a6544-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="a6544-167">Selecione **Aplicativos de nuvem** e escolha quais aplicativos proteger.</span><span class="sxs-lookup"><span data-stu-id="a6544-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="a6544-168">Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e Office **365 Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="a6544-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="a6544-169">Selecione **Concluído** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a6544-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="a6544-170">Selecione **Condições**  >  **Aplicativos de cliente** para aplicar a política a aplicativos e navegadores.</span><span class="sxs-lookup"><span data-stu-id="a6544-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="a6544-171">Por exemplo, selecione **Sim** e, em seguida, habilitar **aplicativos** de navegador e **móveis e clientes de área de trabalho.**</span><span class="sxs-lookup"><span data-stu-id="a6544-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="a6544-172">Selecione **Concluído** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a6544-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="a6544-173">Selecione **Conceder para** aplicar o Acesso Condicional com base na conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6544-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="a6544-174">Por exemplo, selecione **Conceder acesso** Exigir que o dispositivo seja marcado  >  **como compatível**.</span><span class="sxs-lookup"><span data-stu-id="a6544-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="a6544-175">Escolha **Selecionar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a6544-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="a6544-176">Selecione **Habilitar política** e, em **seguida, Criar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a6544-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="a6544-177">Para obter mais informações, [consulte Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="a6544-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="a6544-178">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a6544-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6544-179">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a6544-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)