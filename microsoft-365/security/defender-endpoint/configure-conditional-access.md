---
title: Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade
description: Saiba mais sobre as etapas que você precisa fazer no Intune, Microsoft 365 Defender e no Azure para implementar o acesso condicional
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
ms.openlocfilehash: 2c9462fa0d4be4d6ff78ba3e5db2cd4fa71fef0b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339509"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="49dad-104">Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="49dad-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49dad-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="49dad-105">**Applies to:**</span></span>
- [<span data-ttu-id="49dad-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="49dad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="49dad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49dad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="49dad-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="49dad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="49dad-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="49dad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="49dad-110">Esta seção orienta você por todas as etapas necessárias para implementar corretamente o Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="49dad-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="49dad-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="49dad-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="49dad-112">É importante observar que não há suporte para dispositivos registrados no Azure AD neste cenário.</span><span class="sxs-lookup"><span data-stu-id="49dad-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="49dad-113">Somente dispositivos inscritos do Intune têm suporte.</span><span class="sxs-lookup"><span data-stu-id="49dad-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="49dad-114">Você precisa se certificar de que todos os seus dispositivos estão inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="49dad-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="49dad-115">Você pode usar qualquer uma das seguintes opções para registrar dispositivos no Intune:</span><span class="sxs-lookup"><span data-stu-id="49dad-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="49dad-116">Administrador de IT: Para obter mais informações sobre como habilcar o registro automático, [consulte Windows Registro](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="49dad-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="49dad-117">Usuário final: para obter mais informações sobre como registrar seu dispositivo Windows 10 no Intune, consulte Registrar seu dispositivo [Windows 10 no Intune](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="49dad-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="49dad-118">Alternativa para o usuário final: para obter mais informações sobre como ingressar em um domínio do Azure AD, consulte Como: Planejar a implementação de junção do [Azure AD](/azure/active-directory/devices/azureadjoin-plan).</span><span class="sxs-lookup"><span data-stu-id="49dad-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="49dad-119">Há etapas que você precisará seguir no Microsoft 365 Defender, no portal do Intune e no portal do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49dad-119">There are steps you'll need to take in Microsoft 365 Defender, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="49dad-120">É importante observar as funções necessárias para acessar esses portais e implementar o acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="49dad-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="49dad-121">**Microsoft 365 Defender** - Você precisará entrar no portal com uma função de administrador global para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="49dad-121">**Microsoft 365 Defender** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="49dad-122">**Intune** - Você precisará entrar no portal com direitos de administrador de segurança com permissões de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49dad-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="49dad-123">**Portal do Azure AD** - Você precisará entrar como administrador global, administrador de segurança ou administrador de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="49dad-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="49dad-124">Você precisará de um ambiente Microsoft Intune, com o Intune gerenciado e o Azure AD ingressado Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="49dad-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="49dad-125">Tome as seguintes etapas para habilitar o Acesso Condicional:</span><span class="sxs-lookup"><span data-stu-id="49dad-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="49dad-126">Etapa 1: Ativar a conexão Microsoft Intune de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49dad-126">Step 1: Turn on the Microsoft Intune connection from Microsoft 365 Defender</span></span>
- <span data-ttu-id="49dad-127">Etapa 2: Ativar a integração do Defender para Ponto de Extremidade no Intune</span><span class="sxs-lookup"><span data-stu-id="49dad-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="49dad-128">Etapa 3: Criar a política de conformidade no Intune</span><span class="sxs-lookup"><span data-stu-id="49dad-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="49dad-129">Etapa 4: Atribuir a política</span><span class="sxs-lookup"><span data-stu-id="49dad-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="49dad-130">Etapa 5: Criar uma política de Acesso Condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="49dad-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="49dad-131">Etapa 1: ativar a Microsoft Intune conexão</span><span class="sxs-lookup"><span data-stu-id="49dad-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="49dad-132">No painel de navegação, **selecione** Configurações Recursos Avançados Gerais dos Pontos de Extremidade  >    >    >  **Microsoft Intune**  >  **conexão**.</span><span class="sxs-lookup"><span data-stu-id="49dad-132">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="49dad-133">Alterne a configuração Microsoft Intune para **On**.</span><span class="sxs-lookup"><span data-stu-id="49dad-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="49dad-134">Clique **em Salvar preferências**.</span><span class="sxs-lookup"><span data-stu-id="49dad-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="49dad-135">Etapa 2: Ativar a integração do Defender para Ponto de Extremidade no Intune</span><span class="sxs-lookup"><span data-stu-id="49dad-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="49dad-136">Entre no [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="49dad-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="49dad-137">Selecione **Conformidade de dispositivo** Microsoft Defender  >  **ATP**.</span><span class="sxs-lookup"><span data-stu-id="49dad-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="49dad-138">De **Conexão Windows 10.0.15063+ dispositivos** para Proteção Avançada contra Ameaças do Microsoft Defender como **On**.</span><span class="sxs-lookup"><span data-stu-id="49dad-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="49dad-139">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49dad-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="49dad-140">Etapa 3: Criar a política de conformidade no Intune</span><span class="sxs-lookup"><span data-stu-id="49dad-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="49dad-141">No portal [do Azure,](https://portal.azure.com)selecione **Todos os serviços,** filtre no **Intune** e selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="49dad-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="49dad-142">Selecione **Políticas de conformidade de**  >  **dispositivo** Criar  >  **política**.</span><span class="sxs-lookup"><span data-stu-id="49dad-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="49dad-143">Insira um **Nome e** **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="49dad-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="49dad-144">Em **Plataforma,** selecione **Windows 10 e posterior.**</span><span class="sxs-lookup"><span data-stu-id="49dad-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="49dad-145">Nas **configurações de Saúde** do Dispositivo, desempate Exigir que o dispositivo seja **ou sob** o Nível de Ameaça de Dispositivo para o nível preferencial:</span><span class="sxs-lookup"><span data-stu-id="49dad-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="49dad-146">**Protegido**: esse nível é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="49dad-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="49dad-147">O dispositivo não pode ter ameaças existentes e ainda acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="49dad-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="49dad-148">Se alguma ameaça for encontrada, o dispositivo será avaliado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="49dad-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="49dad-149">**Baixo**: o dispositivo é compatível se existirem apenas ameaças de baixo nível.</span><span class="sxs-lookup"><span data-stu-id="49dad-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="49dad-150">Dispositivos com níveis médios ou altos de ameaça não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="49dad-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="49dad-151">**Médio**: o dispositivo é compatível se as ameaças encontradas no dispositivo são baixas ou médias.</span><span class="sxs-lookup"><span data-stu-id="49dad-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="49dad-152">Se ameaças de alto nível são detectadas, o dispositivo é determinado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="49dad-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="49dad-153">**Alto**: esse nível é o menos seguro e permite todos os níveis de ameaça.</span><span class="sxs-lookup"><span data-stu-id="49dad-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="49dad-154">Portanto, dispositivos que com níveis de ameaça altos, médios ou baixos são considerados compatíveis.</span><span class="sxs-lookup"><span data-stu-id="49dad-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="49dad-155">Selecione **OK** e **Criar para** salvar suas alterações (e criar a política).</span><span class="sxs-lookup"><span data-stu-id="49dad-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="49dad-156">Etapa 4: Atribuir a política</span><span class="sxs-lookup"><span data-stu-id="49dad-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="49dad-157">No portal [do Azure,](https://portal.azure.com)selecione **Todos os serviços,** filtre no **Intune** e selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="49dad-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="49dad-158">Selecione **Políticas de conformidade**  >  **de** dispositivo> sua política de conformidade do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="49dad-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="49dad-159">Selecione **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="49dad-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="49dad-160">Inclua ou exclua seus grupos do Azure AD para atribuir a política a eles.</span><span class="sxs-lookup"><span data-stu-id="49dad-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="49dad-161">Para implantar a política nos grupos, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49dad-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="49dad-162">Os dispositivos de usuário direcionados pela política são avaliados para conformidade.</span><span class="sxs-lookup"><span data-stu-id="49dad-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="49dad-163">Etapa 5: Criar uma política de Acesso Condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="49dad-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="49dad-164">No portal [do Azure,](https://portal.azure.com)abra **Azure Active Directory** nova política  >  **de Acesso**  >  **Condicional.**</span><span class="sxs-lookup"><span data-stu-id="49dad-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="49dad-165">Insira um nome **de política** e selecione Usuários **e grupos.**</span><span class="sxs-lookup"><span data-stu-id="49dad-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="49dad-166">Use as opções Incluir ou Excluir para adicionar seus grupos para a política e selecione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="49dad-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="49dad-167">Selecione **Aplicativos de nuvem** e escolha quais aplicativos proteger.</span><span class="sxs-lookup"><span data-stu-id="49dad-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="49dad-168">Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e **Office 365 Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="49dad-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="49dad-169">Selecione **Concluído** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="49dad-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="49dad-170">Selecione **Condições**  >  **Aplicativos de cliente** para aplicar a política a aplicativos e navegadores.</span><span class="sxs-lookup"><span data-stu-id="49dad-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="49dad-171">Por exemplo, selecione **Sim** e, em seguida, habilitar **aplicativos** de navegador e **móveis e clientes de área de trabalho.**</span><span class="sxs-lookup"><span data-stu-id="49dad-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="49dad-172">Selecione **Concluído** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="49dad-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="49dad-173">Selecione **Conceder para** aplicar o Acesso Condicional com base na conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49dad-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="49dad-174">Por exemplo, selecione **Conceder acesso** Exigir que o dispositivo seja marcado  >  **como compatível**.</span><span class="sxs-lookup"><span data-stu-id="49dad-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="49dad-175">Escolha **Selecionar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="49dad-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="49dad-176">Selecione **Habilitar política** e, em **seguida, Criar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="49dad-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="49dad-177">Para obter mais informações, [consulte Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="49dad-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="49dad-178">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="49dad-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="49dad-179">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="49dad-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
