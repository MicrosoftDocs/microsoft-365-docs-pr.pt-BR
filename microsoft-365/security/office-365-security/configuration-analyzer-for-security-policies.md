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
description: Os administradores podem aprender a usar o analisador de configuração para encontrar e corrigir as políticas de segurança que estão abaixo das políticas de segurança predefinidas de proteção padrão e proteção estrita.
ms.openlocfilehash: 1429bddc5ae5f8409ad4f3593f7ea236b13f854c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846467"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="8cd8c-103">Analisador de configuração para políticas de proteção no EOP e Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8cd8c-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="8cd8c-104">Os recursos descritos neste tópico estão em visualização, não estão disponíveis em todas as organizações e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="8cd8c-105">Para obter informações sobre o cronograma de lançamento, confira o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="8cd8c-106">O analisador de configuração no centro de conformidade & segurança fornece um local central para encontrar e corrigir as políticas de segurança nas quais as configurações estão abaixo das configurações de perfil de proteção padrão e proteção estrita em [políticas de segurança predefinidas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="8cd8c-107">Os seguintes tipos de políticas são analisados pelo analisador de configuração:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="8cd8c-108">**Políticas de proteção do Exchange Online (EOP)** : isso inclui as organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-108">**Exchange Online Protection (EOP) policies** : This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="8cd8c-109">[Políticas antispam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="8cd8c-110">[Diretivas Antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="8cd8c-111">[EOP regras anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="8cd8c-112">**Políticas do Microsoft defender para Office 365** : isso inclui organizações com as assinaturas do complemento Microsoft 365 E5 ou defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-112">**Microsoft Defender for Office 365 policies** : This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="8cd8c-113">Políticas anti-phishing no Microsoft defender para Office 365, que incluem:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="8cd8c-114">As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="8cd8c-115">Configurações de representação</span><span class="sxs-lookup"><span data-stu-id="8cd8c-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="8cd8c-116">Limites avançados de phishing</span><span class="sxs-lookup"><span data-stu-id="8cd8c-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="8cd8c-117">[Políticas de links seguros](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="8cd8c-118">[Políticas de anexos seguros](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="8cd8c-119">Os valores de configuração de política **padrão** e **estrito** usados como linhas de base são descritos em [configurações recomendadas para a segurança do EOP e do Microsoft defender para Office 365](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8cd8c-120">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="8cd8c-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8cd8c-121">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8cd8c-122">Para ir diretamente para a página do **analisador de configuração** , use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="8cd8c-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="8cd8c-123">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="8cd8c-124">Você precisa receber permissões antes de executar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="8cd8c-125">Para usar o analisador de configuração **e** fazer atualizações em políticas de segurança, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8cd8c-126">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8cd8c-127">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8cd8c-128">Para acesso somente leitura ao analisador de configuração, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8cd8c-129">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8cd8c-130">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="8cd8c-131">Usar o analisador de configuração no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="8cd8c-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="8cd8c-132">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **analisador de configuração** de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analisador de configuração na página política de gerenciamento de ameaças \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="8cd8c-134">O analisador de configuração tem duas guias principais:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="8cd8c-135">**Configurações e recomendações** : escolha padrão ou estrito e Compare essas configurações com as políticas de segurança existentes.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-135">**Settings and recommendations** : You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="8cd8c-136">Nos resultados, você pode ajustar os valores de suas configurações para colocá-los no mesmo nível que o padrão ou estrito.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="8cd8c-137">**Histórico e análise de descompasso de configuração** : este modo de exibição permite que você rastreie alterações de política ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-137">**Configuration drift analysis and history** : This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="8cd8c-138">Guia configuração e recomendações no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="8cd8c-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="8cd8c-139">Por padrão, a guia é aberta na comparação com o perfil de proteção padrão.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="8cd8c-140">Você pode mudar para a comparação do perfil de proteção estrito clicando em **Exibir recomendações estritas**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="8cd8c-141">Para retornar, selecione **Exibir recomendações padrão**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-141">To switch back, select **View Standard recommendations**.</span></span>

![Exibição de configurações e recomendações no analisador de configuração](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="8cd8c-143">Por padrão, a coluna **grupo de políticas/nome da configuração** contém uma exibição recolhida dos diferentes tipos de políticas de segurança e o número de configurações que precisam de melhorias (se houver).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="8cd8c-144">Os tipos de políticas são:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-144">The types of policies are:</span></span>

- <span data-ttu-id="8cd8c-145">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-145">**Anti-spam**</span></span>
- <span data-ttu-id="8cd8c-146">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-146">**Anti-phishing**</span></span>
- <span data-ttu-id="8cd8c-147">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-147">**Anti-malware**</span></span>
- <span data-ttu-id="8cd8c-148">**Anexos seguros de ATP** (se sua assinatura incluir o Microsoft defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="8cd8c-148">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="8cd8c-149">**Links seguros de ATP** (se sua assinatura incluir o Microsoft defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="8cd8c-149">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="8cd8c-150">No modo de exibição padrão, tudo é recolhido.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="8cd8c-151">Ao lado de cada política, há um resumo dos resultados da comparação de suas políticas (que você pode modificar) e as configurações nas políticas correspondentes para os perfis de proteção padrão ou estrito (que você não pode modificar).</span><span class="sxs-lookup"><span data-stu-id="8cd8c-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="8cd8c-152">Você verá as seguintes informações para o perfil de proteção para o qual você está comparando:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="8cd8c-153">**Verde** : todas as configurações de todas as políticas existentes são pelo menos tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-153">**Green** : All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="8cd8c-154">**Âmbar** : um pequeno número de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-154">**Amber** : A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="8cd8c-155">**Vermelho** : um número significativo de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-155">**Red** : A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="8cd8c-156">Isso pode ser algumas configurações em muitas políticas ou muitas configurações em uma política.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="8cd8c-157">Para comparações favoráveis, você verá o texto: **todas as configurações seguem** \<**Standard** or **Strict**\> **recomendações**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="8cd8c-158">Caso contrário, você verá o número de configurações recomendadas a serem alteradas.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="8cd8c-159">Se você expandir o **nome de configuração e grupo de políticas** , todas as políticas e as configurações associadas em cada política específica que exigem atenção são reveladas.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-159">If you expand **Policy group/setting name** , all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="8cd8c-160">Ou você pode expandir um tipo específico de política (por exemplo, **antispam** ) para ver apenas essas configurações nesses tipos de políticas que exigem sua atenção.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-160">Or, you can expand a specific type of policy (for example, **Anti-spam** ) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="8cd8c-161">Se a comparação não tiver recomendações de melhoria (verde), a expansão da política não revela nada.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="8cd8c-162">Se houver qualquer número de recomendações de aperfeiçoamento (âmbar ou vermelho), as configurações que exigem atenção são reveladas e as informações correspondentes são reveladas nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="8cd8c-163">O nome da configuração que requer sua atenção.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="8cd8c-164">Por exemplo, na captura de tela anterior, é o **limite de email em massa** em uma política antispam.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="8cd8c-165">**Política** : o nome da política afetada que contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-165">**Policy** : The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="8cd8c-166">**Aplicado a** : o número de usuários aos quais as políticas afetadas são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-166">**Applied to** : The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="8cd8c-167">**Configuração atual** : o valor atual da configuração.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-167">**Current configuration** : The current value of the setting.</span></span>

- <span data-ttu-id="8cd8c-168">**Última modificação** : a data em que a política foi modificada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-168">**Last modified** : The date that the policy was last modified.</span></span>

- <span data-ttu-id="8cd8c-169">**Recomendações** : o valor da configuração no perfil de proteção padrão ou estrita.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-169">**Recommendations** : The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="8cd8c-170">Para alterar o valor da configuração na política para corresponder ao valor recomendado no perfil de proteção, clique em **adotar**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="8cd8c-171">Se a alteração for bem-sucedida, você verá a mensagem: as **recomendações foram adotadas com êxito**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="8cd8c-172">Clique em **Atualizar** para ver o número reduzido de recomendações e a remoção da linha de configuração/política específica dos resultados.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="8cd8c-173">Análise de descompasso de configuração e guia histórico no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="8cd8c-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="8cd8c-174">Esta guia permite que você rastreie as alterações feitas em suas políticas de segurança personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="8cd8c-175">Por padrão, as seguintes informações são exibidas:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="8cd8c-176">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-176">**Last modified**</span></span>
- <span data-ttu-id="8cd8c-177">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-177">**Modified by**</span></span>
- <span data-ttu-id="8cd8c-178">**Nome da configuração**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-178">**Setting Name**</span></span>
- <span data-ttu-id="8cd8c-179">**Política**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-179">**Policy**</span></span>
- <span data-ttu-id="8cd8c-180">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-180">**Type**</span></span>

<span data-ttu-id="8cd8c-181">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="8cd8c-182">No submenu **filtros** que aparece, você pode selecionar um dos seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="8cd8c-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="8cd8c-183">**Hora de início** e **hora de término** (Data)</span><span class="sxs-lookup"><span data-stu-id="8cd8c-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="8cd8c-184">**Proteção padrão** ou **proteção estrita**</span><span class="sxs-lookup"><span data-stu-id="8cd8c-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="8cd8c-185">Para exportar os resultados para um arquivo. csv, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="8cd8c-185">To export the results to a .csv file, click **Export**.</span></span>

![Análise de descompasso de configuração e exibição de histórico no analisador de configuração](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
