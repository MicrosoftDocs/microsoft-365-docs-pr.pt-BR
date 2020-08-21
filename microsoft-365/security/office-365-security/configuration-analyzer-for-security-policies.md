---
title: Analisador de configuração para políticas de segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar o analisador de configuração para localizar e corrigir políticas de segurança que contêm configurações que estão abaixo das políticas de segurança predefinidas proteção padrão e proteção estrita.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825768"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="01fd4-103">Analisador de configuração para políticas de proteção no EOP e no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="01fd4-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="01fd4-104">Os recursos descritos neste tópico estão em visualização, não estão disponíveis em todas as organizações e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="01fd4-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="01fd4-105">O analisador de configuração no centro de conformidade & segurança fornece um local central para encontrar e corrigir qualquer uma das políticas de segurança que contêm configurações que estão abaixo das configurações de perfil de proteção padrão e proteção estrita em [políticas de segurança predefinidas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="01fd4-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="01fd4-106">Os seguintes tipos de políticas são analisados pelo analisador de configuração:</span><span class="sxs-lookup"><span data-stu-id="01fd4-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="01fd4-107">**Políticas de proteção do Exchange Online (EOP)**: isso inclui as organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="01fd4-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="01fd4-108">[Políticas antispam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="01fd4-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="01fd4-109">[Diretivas Antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="01fd4-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="01fd4-110">[EOP regras anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="01fd4-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="01fd4-111">**Políticas de proteção avançada contra ameaças (ATP) do office 365**: inclui organizações com as assinaturas do Microsoft 365 E5 ou do Office 365 ATP Add-on:</span><span class="sxs-lookup"><span data-stu-id="01fd4-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="01fd4-112">Políticas anti-phishing da ATP, que incluem:</span><span class="sxs-lookup"><span data-stu-id="01fd4-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="01fd4-113">As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.</span><span class="sxs-lookup"><span data-stu-id="01fd4-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="01fd4-114">Configurações de representação</span><span class="sxs-lookup"><span data-stu-id="01fd4-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="01fd4-115">Limites avançados de phishing</span><span class="sxs-lookup"><span data-stu-id="01fd4-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="01fd4-116">[Políticas de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="01fd4-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="01fd4-117">[Políticas de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="01fd4-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="01fd4-118">Os valores de configuração de política **padrão** e **estrito** usados como linhas de base são descritos em [configurações recomendadas para a segurança do EOP e do Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="01fd4-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="01fd4-119">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="01fd4-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="01fd4-120">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="01fd4-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="01fd4-121">Para ir diretamente para a página do **analisador de configuração** , use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="01fd4-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="01fd4-122">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="01fd4-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="01fd4-123">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="01fd4-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="01fd4-124">Para usar o analisador de configuração **e** fazer atualizações em políticas de segurança, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="01fd4-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="01fd4-125">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="01fd4-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="01fd4-126">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="01fd4-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="01fd4-127">Para acesso somente leitura ao analisador de configuração, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="01fd4-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="01fd4-128">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="01fd4-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="01fd4-129">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="01fd4-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="01fd4-130">Usar o analisador de configuração no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="01fd4-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="01fd4-131">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **analisador de configuração**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="01fd4-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analisador de configuração na página política de gerenciamento de ameaças \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="01fd4-133">O analisador de configuração tem duas guias principais:</span><span class="sxs-lookup"><span data-stu-id="01fd4-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="01fd4-134">**Configurações e recomendações**: escolha padrão ou estrito e Compare essas configurações com as políticas de segurança existentes.</span><span class="sxs-lookup"><span data-stu-id="01fd4-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="01fd4-135">Nos resultados, você pode ajustar os valores de suas configurações para colocá-los no mesmo nível que o padrão ou estrito.</span><span class="sxs-lookup"><span data-stu-id="01fd4-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="01fd4-136">**Histórico e análise de descompasso de configuração**: este modo de exibição permite controlar as alterações feitas em suas políticas com base nos resultados do analisador de configuração ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="01fd4-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="01fd4-137">Guia configuração e recomendações no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="01fd4-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="01fd4-138">Por padrão, a guia é aberta na comparação com o perfil de proteção padrão.</span><span class="sxs-lookup"><span data-stu-id="01fd4-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="01fd4-139">Você pode mudar para a comparação do perfil de proteção estrito clicando em **Exibir recomendações estritas**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="01fd4-140">Para retornar, selecione **Exibir recomendações padrão**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-140">To switch back, select **View Standard recommendations**.</span></span>

![Exibição de configurações e recomendações no analisador de configuração](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="01fd4-142">Por padrão, a coluna **grupo de políticas/nome da configuração** contém uma exibição recolhida dos diferentes tipos de políticas de segurança e o número de configurações nessas políticas que precisam de melhorias (se houver).</span><span class="sxs-lookup"><span data-stu-id="01fd4-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="01fd4-143">Os tipos de políticas são:</span><span class="sxs-lookup"><span data-stu-id="01fd4-143">The types of policies are:</span></span>

- <span data-ttu-id="01fd4-144">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="01fd4-144">**Anti-spam**</span></span>
- <span data-ttu-id="01fd4-145">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="01fd4-145">**Anti-phishing**</span></span>
- <span data-ttu-id="01fd4-146">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="01fd4-146">**Anti-malware**</span></span>
- <span data-ttu-id="01fd4-147">**Anexos seguros de ATP** (se sua assinatura incluir ATP)</span><span class="sxs-lookup"><span data-stu-id="01fd4-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="01fd4-148">**Links seguros de ATP** (se sua assinatura incluir ATP)</span><span class="sxs-lookup"><span data-stu-id="01fd4-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="01fd4-149">No modo de exibição padrão, tudo é recolhido.</span><span class="sxs-lookup"><span data-stu-id="01fd4-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="01fd4-150">Ao lado de cada política, um resumo dos resultados da comparação de suas políticas (que você pode modificar) e as configurações nas políticas correspondentes para os perfis de proteção padrão ou estrito (que você não pode modificar) são exibidos.</span><span class="sxs-lookup"><span data-stu-id="01fd4-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="01fd4-151">Você verá as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="01fd4-151">You'll see the following information:</span></span>

- <span data-ttu-id="01fd4-152">**Verde**: todas as configurações de todas as políticas existentes são pelo menos tão seguras quanto o perfil de proteção para o qual você está comparando.</span><span class="sxs-lookup"><span data-stu-id="01fd4-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="01fd4-153">**Âmbar**: um pequeno número de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção para o qual você está comparando.</span><span class="sxs-lookup"><span data-stu-id="01fd4-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="01fd4-154">**Vermelho**: um número significativo de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção para o qual você está comparando.</span><span class="sxs-lookup"><span data-stu-id="01fd4-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="01fd4-155">Isso pode ser algumas configurações em muitas políticas ou muitas configurações em uma política.</span><span class="sxs-lookup"><span data-stu-id="01fd4-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="01fd4-156">Para comparações favoráveis, você verá o texto: **todas as configurações seguem** \<**Standard** or **Strict**\> **recomendações**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="01fd4-157">Caso contrário, você verá o número de configurações recomendadas a serem alteradas.</span><span class="sxs-lookup"><span data-stu-id="01fd4-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="01fd4-158">Se você expandir o **nome de configuração e grupo de políticas**, todas as políticas e as configurações associadas em cada política específica que exigem atenção são reveladas.</span><span class="sxs-lookup"><span data-stu-id="01fd4-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="01fd4-159">Ou você pode expandir um tipo específico de política (por exemplo, **antispam**) para ver apenas essas configurações nesses tipos de políticas que exigem sua atenção.</span><span class="sxs-lookup"><span data-stu-id="01fd4-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="01fd4-160">Se a comparação não tiver recomendações de melhoria (verde), a expansão da política não revela nada.</span><span class="sxs-lookup"><span data-stu-id="01fd4-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="01fd4-161">Se houver qualquer número de recomendações de aperfeiçoamento (âmbar ou vermelho), as configurações que exigem atenção são reveladas e as informações correspondentes são reveladas nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="01fd4-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="01fd4-162">O nome da configuração que requer sua atenção.</span><span class="sxs-lookup"><span data-stu-id="01fd4-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="01fd4-163">Por exemplo, na captura de tela anterior, é o **limite de email em massa** em uma política antispam.</span><span class="sxs-lookup"><span data-stu-id="01fd4-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="01fd4-164">**Política**: o nome da política afetada que contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="01fd4-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="01fd4-165">**Aplicado a**: o número de usuários aos quais as políticas afetadas são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="01fd4-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="01fd4-166">**Configuração atual**: o valor atual da configuração.</span><span class="sxs-lookup"><span data-stu-id="01fd4-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="01fd4-167">**Última modificação**: a data em que a política foi modificada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="01fd4-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="01fd4-168">**Recomendações**: o valor da configuração no perfil de proteção padrão ou estrita.</span><span class="sxs-lookup"><span data-stu-id="01fd4-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="01fd4-169">Para alterar o valor da configuração na política para corresponder ao valor recomendado no perfil de proteção, clique em **adotar**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="01fd4-170">Se a alteração for bem-sucedida, você verá a mensagem: as **recomendações foram adotadas com êxito**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="01fd4-171">Clique em **Atualizar** para ver o número reduzido de recomendações e a remoção da linha de configuração/política específica dos resultados.</span><span class="sxs-lookup"><span data-stu-id="01fd4-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="01fd4-172">Análise de descompasso de configuração e guia histórico no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="01fd4-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="01fd4-173">Esta guia permite que você rastreie as alterações feitas em suas políticas de segurança personalizadas com base nas informações do analisador de segurança.</span><span class="sxs-lookup"><span data-stu-id="01fd4-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="01fd4-174">Por padrão, as seguintes informações são exibidas:</span><span class="sxs-lookup"><span data-stu-id="01fd4-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="01fd4-175">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="01fd4-175">**Last modified**</span></span>
- <span data-ttu-id="01fd4-176">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="01fd4-176">**Modified by**</span></span>
- <span data-ttu-id="01fd4-177">**Nome da configuração**</span><span class="sxs-lookup"><span data-stu-id="01fd4-177">**Setting Name**</span></span>
- <span data-ttu-id="01fd4-178">**Política**</span><span class="sxs-lookup"><span data-stu-id="01fd4-178">**Policy**</span></span>
- <span data-ttu-id="01fd4-179">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="01fd4-179">**Type**</span></span>

<span data-ttu-id="01fd4-180">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="01fd4-181">No submenu **filtros** que aparece, você pode selecionar um dos seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="01fd4-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="01fd4-182">**Hora de início** e **hora de término** (Data)</span><span class="sxs-lookup"><span data-stu-id="01fd4-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="01fd4-183">**Proteção padrão** ou **proteção estrita**</span><span class="sxs-lookup"><span data-stu-id="01fd4-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="01fd4-184">Para exportar os resultados para um arquivo. csv, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="01fd4-184">To export the results to a .csv file, click **Export**.</span></span>

![Análise de descompasso de configuração e exibição de histórico no analisador de configuração](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
