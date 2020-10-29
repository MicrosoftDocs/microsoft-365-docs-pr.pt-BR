---
title: Correção de problemas encontrados pela ferramenta de avaliação de prontidão
description: Ações detalhadas a serem tomadas para cada problema que a ferramenta encontrar
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795112"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="55bd0-104">Correção de problemas encontrados pela ferramenta de avaliação de prontidão</span><span class="sxs-lookup"><span data-stu-id="55bd0-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="55bd0-105">Para cada verificação, a ferramenta relatará um dos quatro resultados possíveis:</span><span class="sxs-lookup"><span data-stu-id="55bd0-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="55bd0-106">Resultado</span><span class="sxs-lookup"><span data-stu-id="55bd0-106">Result</span></span>  |<span data-ttu-id="55bd0-107">Significado</span><span class="sxs-lookup"><span data-stu-id="55bd0-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="55bd0-108">Pronto</span><span class="sxs-lookup"><span data-stu-id="55bd0-108">Ready</span></span>     | <span data-ttu-id="55bd0-109">Nenhuma ação é necessária antes de concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="55bd0-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="55bd0-110">Advisory</span></span>    | <span data-ttu-id="55bd0-111">Siga as etapas na ferramenta ou neste artigo para obter a melhor experiência com o registro e para os usuários.</span><span class="sxs-lookup"><span data-stu-id="55bd0-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="55bd0-112">Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar o primeiro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55bd0-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="55bd0-113">Não está pronto</span><span class="sxs-lookup"><span data-stu-id="55bd0-113">Not ready</span></span> | <span data-ttu-id="55bd0-114">*O registro falhará se você não corrigir esses problemas.*</span><span class="sxs-lookup"><span data-stu-id="55bd0-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="55bd0-115">Siga as etapas na ferramenta ou neste artigo para resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="55bd0-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="55bd0-116">Erro</span><span class="sxs-lookup"><span data-stu-id="55bd0-116">Error</span></span> | <span data-ttu-id="55bd0-117">A função de diretor do Azure Active Directory (AD) que você está usando não tem permissão suficiente para executar essa verificação.</span><span class="sxs-lookup"><span data-stu-id="55bd0-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="55bd0-118">Configurações do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="55bd0-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="55bd0-119">Perfil de implantação do piloto automático</span><span class="sxs-lookup"><span data-stu-id="55bd0-119">Autopilot deployment profile</span></span>

<span data-ttu-id="55bd0-120">Você não deve ter perfis do AutoPilot existentes que se destinam a grupos atribuídos ou dinâmicos usados pela área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="55bd0-121">O Microsoft Managed desktop usa o piloto automático para provisionar novos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="55bd0-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="55bd0-122">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-122">**Not ready**</span></span>

<span data-ttu-id="55bd0-123">Você tem um perfil do AutoPilot atribuído a todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="55bd0-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="55bd0-124">Para obter etapas, consulte [registrar dispositivos Windows no Intune usando o Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="55bd0-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="55bd0-125">Após o registro de área de trabalho gerenciada da Microsoft, defina a política de piloto automático para excluir os **dispositivos de local de trabalho modernos-todos os** grupos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="55bd0-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="55bd0-126">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-126">**Advisory**</span></span>

<span data-ttu-id="55bd0-127">Verifique se os perfis do AutoPilot têm como destino um grupo do Azure Active Directory atribuído ou dinâmico que não inclui os dispositivos de área de trabalho gerenciada da Microsoft que serão criados no registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="55bd0-128">Para obter etapas, consulte [registrar dispositivos Windows no Intune usando o Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="55bd0-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="55bd0-129">Após o registro de área de trabalho gerenciada da Microsoft, defina a política de piloto automático para excluir os **dispositivos de local de trabalho modernos-todos os** grupos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="55bd0-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="55bd0-130">Conectores de certificado</span><span class="sxs-lookup"><span data-stu-id="55bd0-130">Certificate connectors</span></span>

<span data-ttu-id="55bd0-131">Se você tiver conectores de certificado usados pelos dispositivos que deseja registrar na área de trabalho gerenciada da Microsoft, os conectores não poderão ter erros.</span><span class="sxs-lookup"><span data-stu-id="55bd0-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="55bd0-132">Apenas um dos seguintes comunicados será aplicado à sua situação, portanto, verifique-os cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="55bd0-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="55bd0-133">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-133">**Advisory**</span></span>

<span data-ttu-id="55bd0-134">Nenhum conector de certificado está presente.</span><span class="sxs-lookup"><span data-stu-id="55bd0-134">No certificate connectors are present.</span></span> <span data-ttu-id="55bd0-135">É possível que você não precise de nenhum conector, mas deve avaliar se você pode precisar de alguma conectividade de rede para os dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-136">Para obter mais informações, consulte [preparar certificados e perfis de rede para a área de trabalho gerenciada da Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="55bd0-137">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-137">**Advisory**</span></span>

<span data-ttu-id="55bd0-138">Pelo menos um conector de certificado tem um erro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="55bd0-139">Se você precisar desse conector para conectividade com dispositivos de área de trabalho gerenciada da Microsoft, você deve resolver o erro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="55bd0-140">Para obter mais informações, consulte [preparar certificados e perfis de rede para a área de trabalho gerenciada da Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="55bd0-141">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-141">**Advisory**</span></span>

<span data-ttu-id="55bd0-142">Você tem pelo menos um conector de certificado e nenhum erro é relatado.</span><span class="sxs-lookup"><span data-stu-id="55bd0-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="55bd0-143">No entanto, talvez seja necessário criar um perfil para reutilizar o conector para dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-144">Para obter mais informações, consulte [preparar certificados e perfis de rede para a área de trabalho gerenciada da Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="55bd0-145">Políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="55bd0-145">Conditional access policies</span></span>

<span data-ttu-id="55bd0-146">As políticas de acesso condicional em sua organização do Azure AD não devem ser direcionadas a usuários do Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="55bd0-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="55bd0-147">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-147">**Not ready**</span></span>

<span data-ttu-id="55bd0-148">Você tem pelo menos uma política de acesso condicional que se destina a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="55bd0-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="55bd0-149">Redefina a política para direcionar um grupo específico do Azure AD que não inclui o grupo Azure AD de contas de serviço de área de trabalho gerenciada da Microsoft que serão criadas no registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="55bd0-150">Para obter etapas, consulte [acesso condicional: usuários e grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="55bd0-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="55bd0-151">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-151">**Advisory**</span></span>

<span data-ttu-id="55bd0-152">Certifique-se de que as políticas de acesso condicional que você excluiu o grupo de **contas do serviço de área de trabalho moderna** do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55bd0-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="55bd0-153">Para obter etapas, consulte [ajustar o acesso condicional](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="55bd0-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="55bd0-154">O grupo de **serviços de área de trabalho moderna** grupo do Azure AD é um grupo dinâmico que criamos para o serviço ao se inscrever.</span><span class="sxs-lookup"><span data-stu-id="55bd0-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="55bd0-155">Você precisará voltar para excluir esse grupo após o registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="55bd0-156">Para saber mais sobre essas contas de serviço, consulte [Standard Operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="55bd0-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="55bd0-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="55bd0-157">**Error**</span></span>

<span data-ttu-id="55bd0-158">A função de administrador do Intune não tem permissões suficientes para esta verificação.</span><span class="sxs-lookup"><span data-stu-id="55bd0-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="55bd0-159">Você também precisará de qualquer uma destas funções do Azure AD atribuídas para executar esta verificação:</span><span class="sxs-lookup"><span data-stu-id="55bd0-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="55bd0-160">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-160">Security Reader</span></span>
- <span data-ttu-id="55bd0-161">Administrador de Segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-161">Security Administrator</span></span>
- <span data-ttu-id="55bd0-162">Administrador de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="55bd0-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="55bd0-163">Leitor global</span><span class="sxs-lookup"><span data-stu-id="55bd0-163">Global Reader</span></span>
- <span data-ttu-id="55bd0-164">Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="55bd0-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="55bd0-165">Políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="55bd0-165">Device Compliance policies</span></span>

<span data-ttu-id="55bd0-166">As políticas de conformidade do dispositivo do Intune em sua organização do Azure AD não devem ser direcionadas a usuários do Microsoft Managed desktop.</span><span class="sxs-lookup"><span data-stu-id="55bd0-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="55bd0-167">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-167">**Not ready**</span></span>

<span data-ttu-id="55bd0-168">Você tem pelo menos uma política de conformidade voltada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="55bd0-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="55bd0-169">Redefina a política para direcionar um grupo específico do Azure AD que não inclui nenhum usuário da área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="55bd0-170">Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="55bd0-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="55bd0-171">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-171">**Advisory**</span></span>

<span data-ttu-id="55bd0-172">Certifique-se de que as políticas de conformidade que você não incluiu nenhum usuário da área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="55bd0-173">Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="55bd0-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="55bd0-174">Políticas de configuração de dispositivo</span><span class="sxs-lookup"><span data-stu-id="55bd0-174">Device Configuration policies</span></span>

<span data-ttu-id="55bd0-175">As políticas de configuração de dispositivo do Intune em sua organização do Azure AD não devem ser direcionadas a nenhum dispositivo ou usuário do Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="55bd0-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="55bd0-176">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-176">**Not ready**</span></span>

<span data-ttu-id="55bd0-177">Você tem pelo menos uma política de configuração voltada para todos os usuários, todos os dispositivos ou ambos.</span><span class="sxs-lookup"><span data-stu-id="55bd0-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="55bd0-178">Redefina a política para direcionar um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-179">Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="55bd0-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="55bd0-180">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-180">**Advisory**</span></span>

<span data-ttu-id="55bd0-181">Certifique-se de que as políticas de conformidade que você não incluiu nenhum dispositivo ou usuário do Microsoft Managed desktop.</span><span class="sxs-lookup"><span data-stu-id="55bd0-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="55bd0-182">Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="55bd0-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="55bd0-183">Restrições de tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="55bd0-183">Device type restrictions</span></span>

<span data-ttu-id="55bd0-184">Os dispositivos de área de trabalho gerenciada da Microsoft devem ter permissão para se inscrever no Intune.</span><span class="sxs-lookup"><span data-stu-id="55bd0-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="55bd0-185">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-185">**Not ready**</span></span>

<span data-ttu-id="55bd0-186">Siga as etapas em [definir restrições de registro](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) para alterar a configuração para **permitir** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow** .</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="55bd0-187">Página de status do registro</span><span class="sxs-lookup"><span data-stu-id="55bd0-187">Enrollment Status Page</span></span>

<span data-ttu-id="55bd0-188">No momento, você tem a página de status de registro (ESP) habilitada.</span><span class="sxs-lookup"><span data-stu-id="55bd0-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="55bd0-189">Se você estiver participando da visualização pública desse recurso, poderá ignorar esse item.</span><span class="sxs-lookup"><span data-stu-id="55bd0-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="55bd0-190">Para obter mais informações, consulte [experiência de primeira execução com o AutoPilot e a página status do registro](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="55bd0-191">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-191">**Not ready**</span></span>

<span data-ttu-id="55bd0-192">Você tem o perfil padrão ESP definido para **mostrar o progresso da configuração de perfil e aplicativo** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-192">You have the ESP default profile set to **Show app and profile configuration progress** .</span></span> <span data-ttu-id="55bd0-193">Desabilite essa configuração seguindo as etapas descritas em [Configurar a página status do registro](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="55bd0-193">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="55bd0-194">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-194">**Advisory**</span></span>

<span data-ttu-id="55bd0-195">Certifique-se de que todos os perfis que têm a configuração de **andamento da configuração mostrar aplicativo e perfil** não estão atribuídos a nenhum grupo do Azure AD que inclua dispositivos de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-196">Para obter mais informações, consulte [Configurar a página status do registro](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="55bd0-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="55bd0-197">Registro do Intune</span><span class="sxs-lookup"><span data-stu-id="55bd0-197">Intune enrollment</span></span>

<span data-ttu-id="55bd0-198">Os dispositivos Windows 10 em sua organização do Azure AD devem ser registrados automaticamente no Intune.</span><span class="sxs-lookup"><span data-stu-id="55bd0-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="55bd0-199">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-199">**Not ready**</span></span>

<span data-ttu-id="55bd0-200">Os usuários em sua organização do Azure AD não estão inscritos automaticamente no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="55bd0-200">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="55bd0-201">Altere o escopo do usuário MDM para **alguns** ou **todos** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-201">Change the MDM User scope to **Some** or **All** .</span></span> <span data-ttu-id="55bd0-202">Se você escolher **alguns** , volte após o registro e selecione o **local de trabalho moderno – todos os** grupos do Azure ad para **grupos** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** .</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="55bd0-203">Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="55bd0-203">Microsoft Store for Business</span></span>

<span data-ttu-id="55bd0-204">Usamos a Microsoft Store para empresas para que você possa baixar o portal da empresa para implantar alguns aplicativos, como o Microsoft Project e o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="55bd0-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="55bd0-205">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-205">**Not ready**</span></span>

<span data-ttu-id="55bd0-206">A Microsoft Store para empresas não está habilitada ou não está sincronizada com o Intune.</span><span class="sxs-lookup"><span data-stu-id="55bd0-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="55bd0-207">Para obter mais informações, consulte [como gerenciar aplicativos comprados por volume da Microsoft Store para empresas com o Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e [instalar o portal da empresa do Intune em dispositivos](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="55bd0-208">Autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="55bd0-208">Multi-factor authentication</span></span>

<span data-ttu-id="55bd0-209">A autenticação multifator não deve ser aplicada acidentalmente às contas de serviço de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="55bd0-210">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-210">**Not ready**</span></span>

<span data-ttu-id="55bd0-211">Você tem algumas políticas de autenticação multifator (MFA) definidas como "obrigatórias" para políticas de acesso condicional que são atribuídas a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="55bd0-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="55bd0-212">Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-213">Para obter mais informações, consulte [políticas de acesso condicional](#conditional-access-policies) e [acesso condicional: exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="55bd0-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="55bd0-214">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-214">**Advisory**</span></span>

<span data-ttu-id="55bd0-215">Certifique-se de que todas as políticas de acesso condicional que exijam a MFA excluam o grupo do **local de trabalho moderno – todo** o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55bd0-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="55bd0-216">Para obter mais informações, consulte [políticas de acesso condicional](#conditional-access-policies) e [acesso condicional: exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="55bd0-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="55bd0-217">O **ambiente de trabalho moderno – todos os** grupos do Azure AD é um grupo dinâmico criado quando você se inscreve na área de trabalho gerenciada da Microsoft, portanto, você terá que voltar a excluir esse grupo após o registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="55bd0-218">**Error**</span><span class="sxs-lookup"><span data-stu-id="55bd0-218">**Error**</span></span>

<span data-ttu-id="55bd0-219">A função de administrador do Intune não tem permissões suficientes para esta verificação.</span><span class="sxs-lookup"><span data-stu-id="55bd0-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="55bd0-220">Você também precisará de qualquer uma destas funções do Azure AD atribuídas para executar esta verificação:</span><span class="sxs-lookup"><span data-stu-id="55bd0-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="55bd0-221">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-221">Security Reader</span></span>
- <span data-ttu-id="55bd0-222">Administrador de Segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-222">Security Administrator</span></span>
- <span data-ttu-id="55bd0-223">Administrador de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="55bd0-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="55bd0-224">Leitor global</span><span class="sxs-lookup"><span data-stu-id="55bd0-224">Global Reader</span></span>
- <span data-ttu-id="55bd0-225">Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="55bd0-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="55bd0-226">Scripts do PowerShell</span><span class="sxs-lookup"><span data-stu-id="55bd0-226">PowerShell scripts</span></span>

<span data-ttu-id="55bd0-227">Os scripts do Windows PowerShell não podem ser atribuídos de uma maneira que direcione dispositivos da área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="55bd0-228">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-228">**Advisory**</span></span>

<span data-ttu-id="55bd0-229">Certifique-se de que os scripts do Windows PowerShell em sua organização do Azure AD não se destinam a nenhum dispositivo ou usuário do Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="55bd0-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="55bd0-230">Para obter mais informações, consulte [usar scripts do PowerShell em dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="55bd0-230">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="55bd0-231">Região</span><span class="sxs-lookup"><span data-stu-id="55bd0-231">Region</span></span>

<span data-ttu-id="55bd0-232">Sua região deve ser compatível com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-232">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="55bd0-233">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-233">**Not ready**</span></span>

<span data-ttu-id="55bd0-234">Sua região da organização do Azure AD não é suportada atualmente pela Microsoft Managed desktop.</span><span class="sxs-lookup"><span data-stu-id="55bd0-234">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="55bd0-235">Para obter mais informações, consulte [áreas e idiomas compatíveis com o Microsoft Managed desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-235">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="55bd0-236">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-236">**Advisory**</span></span>

<span data-ttu-id="55bd0-237">Um ou mais países onde sua organização do Azure AD está localizada não é suportado pela área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-237">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="55bd0-238">Para obter mais informações, consulte [áreas e idiomas compatíveis com o Microsoft Managed desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="55bd0-239">Linhas de base de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-239">Security baselines</span></span>

<span data-ttu-id="55bd0-240">As políticas de linha de base de segurança não devem ter como destino nenhum dispositivo de área de trabalho gerenciado</span><span class="sxs-lookup"><span data-stu-id="55bd0-240">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="55bd0-241">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-241">**Not ready**</span></span>

<span data-ttu-id="55bd0-242">Você tem um perfil de linha de base de segurança direcionado a todos os usuários, todos os dispositivos ou ambos.</span><span class="sxs-lookup"><span data-stu-id="55bd0-242">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="55bd0-243">Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-243">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-244">Para obter etapas, consulte [usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="55bd0-244">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="55bd0-245">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-245">**Advisory**</span></span>

<span data-ttu-id="55bd0-246">Certifique-se de que as políticas de linha de base de segurança que você tenha excluído dispositivos de desktop gerenciados da Microsoft</span><span class="sxs-lookup"><span data-stu-id="55bd0-246">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-247">Para obter etapas, consulte [usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="55bd0-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="55bd0-248">Os **dispositivos de área de trabalho moderna – todos os** grupos do Azure ad são um grupo dinâmico que criamos quando você se inscreve na área de trabalho gerenciada da Microsoft, portanto, você terá que voltar a excluir esse grupo após o registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-248">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="55bd0-249">Aplicativos do Windows</span><span class="sxs-lookup"><span data-stu-id="55bd0-249">Windows apps</span></span>

<span data-ttu-id="55bd0-250">Revise os aplicativos que você deseja que seus usuários do Microsoft Managed desktop tenham.</span><span class="sxs-lookup"><span data-stu-id="55bd0-250">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="55bd0-251">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-251">**Advisory**</span></span>

<span data-ttu-id="55bd0-252">Você deve preparar um inventário dos aplicativos que você deseja que seus usuários de área de trabalho gerenciada da Microsoft tenham.</span><span class="sxs-lookup"><span data-stu-id="55bd0-252">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="55bd0-253">Verifique se esses aplicativos podem ser implantados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="55bd0-253">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="55bd0-254">Para obter mais informações, consulte [aplicativos na área de trabalho gerenciada da Microsoft](apps.md).</span><span class="sxs-lookup"><span data-stu-id="55bd0-254">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="55bd0-255">Você pode solicitar ao representante da sua conta da Microsoft uma consulta no Microsoft Endpoint Configuration Manager para identificar os aplicativos que estão prontos para migrar para o Intune ou que precisam de ajuste.</span><span class="sxs-lookup"><span data-stu-id="55bd0-255">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="55bd0-256">Windows Hello para Empresas</span><span class="sxs-lookup"><span data-stu-id="55bd0-256">Windows Hello for Business</span></span>

<span data-ttu-id="55bd0-257">A área de trabalho gerenciada da Microsoft exige que o Windows Hello para empresas seja habilitado.</span><span class="sxs-lookup"><span data-stu-id="55bd0-257">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="55bd0-258">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-258">**Not ready**</span></span>

<span data-ttu-id="55bd0-259">O Windows Hello para empresas está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="55bd0-259">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="55bd0-260">Habilite-o seguindo as etapas em [criar uma política do Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="55bd0-260">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="55bd0-261">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-261">**Advisory**</span></span>

<span data-ttu-id="55bd0-262">O Windows Hello para empresas não está configurado.</span><span class="sxs-lookup"><span data-stu-id="55bd0-262">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="55bd0-263">Habilite-o seguindo as etapas em [criar uma política do Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="55bd0-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="55bd0-264">Toques de atualização do Windows 10</span><span class="sxs-lookup"><span data-stu-id="55bd0-264">Windows 10 update rings</span></span>

<span data-ttu-id="55bd0-265">A política do "Windows 10 Update Ring" no Intune não deve ser direcionada a nenhum dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-265">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="55bd0-266">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-266">**Not ready**</span></span>

<span data-ttu-id="55bd0-267">Você tem uma política de "anel de atualização" voltada para todos os dispositivos, todos os usuários ou ambos.</span><span class="sxs-lookup"><span data-stu-id="55bd0-267">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="55bd0-268">Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-268">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55bd0-269">Para obter etapas, consulte [Manage Windows 10 software updates no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="55bd0-269">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="55bd0-270">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-270">**Advisory**</span></span>

<span data-ttu-id="55bd0-271">Certifique-se de que todas as políticas de anel de atualização que você excluiu o grupo de **trabalho** do Azure</span><span class="sxs-lookup"><span data-stu-id="55bd0-271">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="55bd0-272">Para obter etapas, consulte [Manage Windows 10 software updates no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="55bd0-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="55bd0-273">Os **dispositivos de área de trabalho moderna – todos os** grupos do Azure ad são um grupo dinâmico que criamos quando você se inscreve na área de trabalho gerenciada da Microsoft, portanto, você terá que voltar a excluir esse grupo após o registro.</span><span class="sxs-lookup"><span data-stu-id="55bd0-273">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="55bd0-274">Configurações do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="55bd0-274">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="55bd0-275">Assinaturas ad hoc</span><span class="sxs-lookup"><span data-stu-id="55bd0-275">Ad hoc subscriptions</span></span>

<span data-ttu-id="55bd0-276">Aconselha a verificar uma configuração que (se definida como "false") pode impedir que o roaming de estado corporativo funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="55bd0-276">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="55bd0-277">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-277">**Advisory**</span></span>

<span data-ttu-id="55bd0-278">Verifique se **AllowAdHocSubscriptions** está definido como **true** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-278">Ensure that **AllowAdHocSubscriptions** is set to **True** .</span></span> <span data-ttu-id="55bd0-279">Caso contrário, o roaming de estado corporativo pode não funcionar.</span><span class="sxs-lookup"><span data-stu-id="55bd0-279">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="55bd0-280">Para obter mais informações, consulte [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="55bd0-280">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="55bd0-281">Roaming de Estado da Empresa</span><span class="sxs-lookup"><span data-stu-id="55bd0-281">Enterprise State Roaming</span></span>

<span data-ttu-id="55bd0-282">O roaming de estado corporativo deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="55bd0-282">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="55bd0-283">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-283">**Advisory**</span></span>

<span data-ttu-id="55bd0-284">Certifique-se de que o roaming de estado corporativo está habilitado para **todos** ou para grupos **selecionados** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-284">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="55bd0-285">Para obter mais informações, consulte [habilitar o roaming de estado corporativo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="55bd0-285">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="55bd0-286">Licenças</span><span class="sxs-lookup"><span data-stu-id="55bd0-286">Licenses</span></span>

<span data-ttu-id="55bd0-287">É necessário ter várias licenças para usar a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-287">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="55bd0-288">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-288">**Not Ready**</span></span>

<span data-ttu-id="55bd0-289">Você não tem todas as licenças necessárias para usar a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-289">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="55bd0-290">Para obter mais informações, consulte [tecnologias de área de trabalho gerenciada da Microsoft](../intro/technologies.md) e [mais sobre licenças](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="55bd0-290">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="55bd0-291">Nomes de contas de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-291">Security account names</span></span>

<span data-ttu-id="55bd0-292">Determinados nomes de contas de segurança podem entrar em conflito com aqueles criados pela área de trabalho gerenciada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-292">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="55bd0-293">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-293">**Not ready**</span></span>

<span data-ttu-id="55bd0-294">Você tem pelo menos um nome de conta que entrará em conflito com aqueles criados pela área de trabalho gerenciada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-294">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="55bd0-295">Trabalhe com seu representante de conta da Microsoft para excluir esses nomes de conta.</span><span class="sxs-lookup"><span data-stu-id="55bd0-295">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="55bd0-296">Funções de administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-296">Security administrator roles</span></span>

<span data-ttu-id="55bd0-297">Os usuários com determinadas funções de segurança devem ter os atribuídos no Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="55bd0-297">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="55bd0-298">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-298">**Advisory**</span></span>

<span data-ttu-id="55bd0-299">Se você tiver qualquer uma dessas funções atribuídas em sua organização do Azure AD, certifique-se de que elas também tenham essas funções atribuídas no Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="55bd0-299">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="55bd0-300">Caso contrário, os administradores com essas funções não poderão acessar o portal de administração.</span><span class="sxs-lookup"><span data-stu-id="55bd0-300">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="55bd0-301">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-301">Security Reader</span></span>
- <span data-ttu-id="55bd0-302">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-302">Security Operator</span></span>
- <span data-ttu-id="55bd0-303">Leitor global</span><span class="sxs-lookup"><span data-stu-id="55bd0-303">Global Reader</span></span>

<span data-ttu-id="55bd0-304">Para obter mais informações, consulte [Create and Manage Roles for Role-Based Access Control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="55bd0-304">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="55bd0-305">Padrão de segurança</span><span class="sxs-lookup"><span data-stu-id="55bd0-305">Security default</span></span>

<span data-ttu-id="55bd0-306">Os padrões de segurança no Azure Active Directory impedirão que a área de trabalho gerenciada da Microsoft gerencie seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="55bd0-306">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="55bd0-307">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-307">**Not ready**</span></span>

<span data-ttu-id="55bd0-308">Os padrões de segurança estão ativados.</span><span class="sxs-lookup"><span data-stu-id="55bd0-308">You have Security defaults turned on.</span></span> <span data-ttu-id="55bd0-309">Desative os padrões de segurança e configure as políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="55bd0-309">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="55bd0-310">Para obter mais informações, consulte [políticas de acesso condicional comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="55bd0-310">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="55bd0-311">Redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="55bd0-311">Self-service Password Reset</span></span>

<span data-ttu-id="55bd0-312">A redefinição de senha de autoatendimento (SSPR) deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="55bd0-312">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="55bd0-313">**Não está pronto**</span><span class="sxs-lookup"><span data-stu-id="55bd0-313">**Not ready**</span></span>

<span data-ttu-id="55bd0-314">SSPR deve ser habilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="55bd0-314">SSPR must be enabled for all users.</span></span> <span data-ttu-id="55bd0-315">Se não for, as contas do serviço de área de trabalho gerenciada da Microsoft não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="55bd0-315">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="55bd0-316">Para obter mais informações, consulte [tutorial: permitir que os usuários desbloqueiem suas contas ou redefinam senhas usando a redefinição de senha de autoatendimento do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="55bd0-316">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="55bd0-317">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-317">**Advisory**</span></span>

<span data-ttu-id="55bd0-318">Certifique-se de que a configuração **selecionada** SSPR inclui dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-318">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="55bd0-319">**Error**</span><span class="sxs-lookup"><span data-stu-id="55bd0-319">**Error**</span></span>

<span data-ttu-id="55bd0-320">A função de administrador do Intune não tem permissões suficientes para esta verificação.</span><span class="sxs-lookup"><span data-stu-id="55bd0-320">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="55bd0-321">Você também precisará do leitor de relatórios do Azure AD role atribuída para executar esta verificação.</span><span class="sxs-lookup"><span data-stu-id="55bd0-321">You'll also need the Reports Reader Azure AD role assigned to run this check.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="55bd0-322">Função de usuário padrão</span><span class="sxs-lookup"><span data-stu-id="55bd0-322">Standard user role</span></span>

<span data-ttu-id="55bd0-323">Os usuários de área de trabalho gerenciada da Microsoft devem ser usuários padrão sem privilégios de administrador local.</span><span class="sxs-lookup"><span data-stu-id="55bd0-323">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="55bd0-324">Eles receberão uma função de usuário padrão quando iniciarem o dispositivo de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-324">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="55bd0-325">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-325">**Advisory**</span></span>

<span data-ttu-id="55bd0-326">Os usuários de área de trabalho gerenciada da Microsoft não devem ter privilégios de administrador local antes da inscrição.</span><span class="sxs-lookup"><span data-stu-id="55bd0-326">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="55bd0-327">Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="55bd0-327">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="55bd0-328">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="55bd0-328">OneDrive for Business</span></span>

<span data-ttu-id="55bd0-329">A configuração **permitir sincronização somente em computadores associados a domínios específicos** entrará em conflito com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-329">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="55bd0-330">**Recomendações**</span><span class="sxs-lookup"><span data-stu-id="55bd0-330">**Advisory**</span></span>

<span data-ttu-id="55bd0-331">Você está usando a configuração **permitir sincronização somente em computadores associados a domínios específicos** .</span><span class="sxs-lookup"><span data-stu-id="55bd0-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="55bd0-332">Essa configuração não funcionará com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55bd0-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="55bd0-333">Desabilite essa configuração e configure o OneDrive for Business para usar uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="55bd0-333">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="55bd0-334">Consulte [planejar uma implantação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="55bd0-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

