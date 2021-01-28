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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar o analisador de configuração para encontrar e corrigir políticas de segurança que estão abaixo das políticas de segurança predefinidas de proteção Padrão e Estrito.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04027e78a2683c6c33954bb548c502497c5e8323
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029473"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="72696-103">Analisador de configuração para políticas de proteção no EOP e no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="72696-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="72696-104">O analisado & r de configuração no Centro de Conformidade e Segurança fornece um local central para localizar e [](preset-security-policies.md)corrigir políticas de segurança onde as configurações estão abaixo das configurações de perfil de proteção Padrão e Estrito em políticas de segurança predefinidas.</span><span class="sxs-lookup"><span data-stu-id="72696-104">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="72696-105">Os seguintes tipos de políticas são analisados pelo analisador de configuração:</span><span class="sxs-lookup"><span data-stu-id="72696-105">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="72696-106">**Políticas do Exchange Online Protection (EOP)**: isso inclui organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações EOP autônomas sem caixas de correio do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="72696-106">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="72696-107">[Políticas anti-spam.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="72696-107">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="72696-108">[Políticas anti-malware.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="72696-108">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="72696-109">[Políticas anti-phishing do EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="72696-109">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="72696-110">**Políticas do Microsoft Defender para Office 365:** isso inclui organizações com o Microsoft 365 E5 ou o Defender para assinaturas de complemento do Office 365:</span><span class="sxs-lookup"><span data-stu-id="72696-110">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="72696-111">Políticas anti-phishing no Microsoft Defender para Office 365, que incluem:</span><span class="sxs-lookup"><span data-stu-id="72696-111">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="72696-112">As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.</span><span class="sxs-lookup"><span data-stu-id="72696-112">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="72696-113">Configurações de representação</span><span class="sxs-lookup"><span data-stu-id="72696-113">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="72696-114">Limites avançados de phishing</span><span class="sxs-lookup"><span data-stu-id="72696-114">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="72696-115">[Políticas de Links Seguros.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="72696-115">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="72696-116">[Políticas de Anexos Seguros.](set-up-atp-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="72696-116">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="72696-117">Os **valores de** configuração de política Padrão e Estrito usados como linhas de base são descritos em Configurações recomendadas para a segurança do EOP e do Microsoft Defender para Office  [365.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="72696-117">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="72696-118">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="72696-118">What do you need to know before you begin?</span></span>

- <span data-ttu-id="72696-119">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="72696-119">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="72696-120">Para ir diretamente para a página **do analisador de** configuração, use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="72696-120">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="72696-121">Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="72696-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="72696-122">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="72696-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="72696-123">Para usar o **analisador** de configuração e fazer atualizações em  políticas de segurança, você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="72696-123">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="72696-124">Para acesso somente leitura ao analisador de configuração, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="72696-124">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="72696-125">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="72696-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="72696-126">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72696-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="72696-127">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="72696-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="72696-128">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="72696-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="72696-129">Usar o analisador de configuração no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="72696-129">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="72696-130">No Centro de Conformidade & segurança, vá para o analisador **de** Configuração de Política de \> **Gerenciamento** \> **de Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="72696-130">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget do analisador de configuração na página Política de \> Gerenciamento de Ameaças](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="72696-132">O analisador de configuração tem duas guias principais:</span><span class="sxs-lookup"><span data-stu-id="72696-132">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="72696-133">**Configurações e recomendações:** você escolhe Padrão ou Estrito e compara essas configurações com suas políticas de segurança existentes.</span><span class="sxs-lookup"><span data-stu-id="72696-133">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="72696-134">Nos resultados, você pode ajustar os valores de suas configurações para ajustá-los ao mesmo nível padrão ou estrito.</span><span class="sxs-lookup"><span data-stu-id="72696-134">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="72696-135">**Análise e histórico de desvios de** configuração: essa exibição permite controlar alterações de política ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="72696-135">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="72696-136">Guia Configuração e recomendações no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="72696-136">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="72696-137">Por padrão, a guia abre na comparação com o perfil de proteção Padrão.</span><span class="sxs-lookup"><span data-stu-id="72696-137">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="72696-138">Você pode alternar para a comparação do perfil de proteção Estrito clicando em **Exibir Recomendações Estritas.**</span><span class="sxs-lookup"><span data-stu-id="72696-138">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="72696-139">Para voltar, selecione **Exibir recomendações padrão.**</span><span class="sxs-lookup"><span data-stu-id="72696-139">To switch back, select **View Standard recommendations**.</span></span>

![Exibição de configurações e recomendações no analisador de configuração](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="72696-141">Por padrão, a coluna de nome de **grupo/configuração** de política contém uma exibição recolhido dos diferentes tipos de políticas de segurança e o número de configurações que precisam de aperfeiçoamento (se necessário).</span><span class="sxs-lookup"><span data-stu-id="72696-141">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="72696-142">Os tipos de políticas são:</span><span class="sxs-lookup"><span data-stu-id="72696-142">The types of policies are:</span></span>

- <span data-ttu-id="72696-143">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="72696-143">**Anti-spam**</span></span>
- <span data-ttu-id="72696-144">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="72696-144">**Anti-phishing**</span></span>
- <span data-ttu-id="72696-145">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="72696-145">**Anti-malware**</span></span>
- <span data-ttu-id="72696-146">**Anexos seguros da ATP** (se sua assinatura incluir o Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="72696-146">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="72696-147">**Links seguros da ATP** (se sua assinatura incluir o Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="72696-147">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="72696-148">No modo de exibição padrão, tudo é recolhido.</span><span class="sxs-lookup"><span data-stu-id="72696-148">In the default view, everything is collapsed.</span></span> <span data-ttu-id="72696-149">Ao lado de cada política, há um resumo dos resultados de comparação de suas políticas (que você pode modificar) e as configurações nas políticas correspondentes para os perfis de proteção Padrão ou Estrito (que você não pode modificar).</span><span class="sxs-lookup"><span data-stu-id="72696-149">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="72696-150">Você verá as seguintes informações para o perfil de proteção que está comparando:</span><span class="sxs-lookup"><span data-stu-id="72696-150">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="72696-151">**Verde**: todas as configurações em todas as políticas existentes são pelo menos tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="72696-151">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="72696-152">**Paulo**: um pequeno número de configurações nas políticas existentes não são tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="72696-152">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="72696-153">**Vermelho**: um número significativo de configurações nas políticas existentes não são tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="72696-153">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="72696-154">Isso pode ser algumas configurações em muitas políticas ou muitas configurações em uma política.</span><span class="sxs-lookup"><span data-stu-id="72696-154">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="72696-155">Para comparações favoráveis, você verá o texto: Todas **as configurações seguem** \<**Standard** or **Strict**\> **as recomendações.**</span><span class="sxs-lookup"><span data-stu-id="72696-155">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="72696-156">Caso contrário, você verá o número de configurações recomendadas a alterar.</span><span class="sxs-lookup"><span data-stu-id="72696-156">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="72696-157">Se você expandir **o nome do grupo/configuração** da política, todas as políticas e as configurações associadas em cada política específica que exigem atenção serão reveladas.</span><span class="sxs-lookup"><span data-stu-id="72696-157">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="72696-158">Ou você pode expandir um tipo específico de política (por exemplo, **Anti-spam)** para ver apenas as configurações nesses tipos de políticas que exigem sua atenção.</span><span class="sxs-lookup"><span data-stu-id="72696-158">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="72696-159">Se a comparação não tiver recomendações para melhoria (verde), a expansão da política não revelará nada.</span><span class="sxs-lookup"><span data-stu-id="72696-159">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="72696-160">Se houver qualquer número de recomendações de melhoria (em vermelho ou vermelho), as configurações que exigem atenção serão reveladas e as informações correspondentes serão reveladas nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="72696-160">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="72696-161">O nome da configuração que requer sua atenção.</span><span class="sxs-lookup"><span data-stu-id="72696-161">The name of the setting that requires your attention.</span></span> <span data-ttu-id="72696-162">Por exemplo, na captura de tela anterior, é o limite de **email** em massa em uma política anti-spam.</span><span class="sxs-lookup"><span data-stu-id="72696-162">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="72696-163">**Política**: o nome da política afetada que contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="72696-163">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="72696-164">**Aplicado a:** o número de usuários aos que as políticas afetadas são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="72696-164">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="72696-165">**Configuração** atual: o valor atual da configuração.</span><span class="sxs-lookup"><span data-stu-id="72696-165">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="72696-166">**Última modificação:** a data em que a política foi modificada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="72696-166">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="72696-167">**Recomendações:** o valor da configuração no perfil de proteção Padrão ou Estrito.</span><span class="sxs-lookup"><span data-stu-id="72696-167">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="72696-168">Para alterar o valor da configuração em sua política para corresponder ao valor recomendado no perfil de proteção, clique em **Adotar**.</span><span class="sxs-lookup"><span data-stu-id="72696-168">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="72696-169">Se a alteração for bem-sucedida, você verá a mensagem: **Recomendações adotadas com êxito.**</span><span class="sxs-lookup"><span data-stu-id="72696-169">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="72696-170">Clique **em** Atualizar para ver o número reduzido de recomendações e a remoção da linha de configuração/política específica dos resultados.</span><span class="sxs-lookup"><span data-stu-id="72696-170">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="72696-171">Análise de desvio de configuração e guia histórico no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="72696-171">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="72696-172">Essa guia permite controlar as alterações feitas em suas políticas de segurança personalizadas.</span><span class="sxs-lookup"><span data-stu-id="72696-172">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="72696-173">Por padrão, as seguintes informações são exibidas:</span><span class="sxs-lookup"><span data-stu-id="72696-173">By default, the following information is displayed:</span></span>

- <span data-ttu-id="72696-174">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="72696-174">**Last modified**</span></span>
- <span data-ttu-id="72696-175">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="72696-175">**Modified by**</span></span>
- <span data-ttu-id="72696-176">**Nome da Configuração**</span><span class="sxs-lookup"><span data-stu-id="72696-176">**Setting Name**</span></span>
- <span data-ttu-id="72696-177">**Política**</span><span class="sxs-lookup"><span data-stu-id="72696-177">**Policy**</span></span>
- <span data-ttu-id="72696-178">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="72696-178">**Type**</span></span>

<span data-ttu-id="72696-179">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="72696-179">To filter the results, click **Filter**.</span></span> <span data-ttu-id="72696-180">No flyout **Filtros** exibido, você pode selecionar entre os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="72696-180">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="72696-181">**Hora de início** **e hora de término** (data)</span><span class="sxs-lookup"><span data-stu-id="72696-181">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="72696-182">**Proteção padrão ou** **proteção estrita**</span><span class="sxs-lookup"><span data-stu-id="72696-182">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="72696-183">Para exportar os resultados para um arquivo .csv, clique em **Exportar.**</span><span class="sxs-lookup"><span data-stu-id="72696-183">To export the results to a .csv file, click **Export**.</span></span>

![Análise de desvio de configuração e exibição de histórico no analisador de configuração](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
