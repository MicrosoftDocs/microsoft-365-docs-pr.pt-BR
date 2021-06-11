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
description: Os administradores podem aprender a usar o analisador de configuração para encontrar e corrigir políticas de segurança que estão abaixo das políticas de segurança predefinidas de proteção padrão e de proteção estrita.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f98ab9b251894a5821d308d95fd786b496e396e4
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878659"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="d23c5-103">Analisador de configuração para políticas de proteção no EOP e no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d23c5-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d23c5-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="d23c5-104">**Applies to**</span></span>
- [<span data-ttu-id="d23c5-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d23c5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d23c5-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d23c5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d23c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d23c5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d23c5-108">O analisador de configuração no portal do defender Microsoft 365 fornece um local central para localizar e corrigir políticas de segurança em que as configurações estão abaixo das configurações de perfil de proteção padrão e estrita em políticas de segurança [predefinidas.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d23c5-108">Configuration analyzer in the Microsoft 365 Defender portal provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="d23c5-109">Os seguintes tipos de políticas são analisados pelo analisador de configuração:</span><span class="sxs-lookup"><span data-stu-id="d23c5-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="d23c5-110">**Proteção do Exchange Online (EOP)**: isso inclui organizações Microsoft 365 com caixas de correio Exchange Online e organizações EOP autônomas sem Exchange Online caixas de correio:</span><span class="sxs-lookup"><span data-stu-id="d23c5-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="d23c5-111">[Políticas anti-spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d23c5-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="d23c5-112">[Políticas anti-malware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d23c5-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="d23c5-113">[Políticas anti-phishing do EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d23c5-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="d23c5-114">**Políticas do Microsoft Defender para Office 365**: isso inclui organizações com o Microsoft 365 E5 ou o Defender para Office 365 assinaturas de complemento:</span><span class="sxs-lookup"><span data-stu-id="d23c5-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="d23c5-115">Políticas anti-phishing no Microsoft Defender para Office 365, que incluem:</span><span class="sxs-lookup"><span data-stu-id="d23c5-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>
    - <span data-ttu-id="d23c5-116">As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.</span><span class="sxs-lookup"><span data-stu-id="d23c5-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="d23c5-117">Configurações de representação</span><span class="sxs-lookup"><span data-stu-id="d23c5-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="d23c5-118">Limites avançados de phishing</span><span class="sxs-lookup"><span data-stu-id="d23c5-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - <span data-ttu-id="d23c5-119">[Cofre Políticas de links.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d23c5-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>
  - <span data-ttu-id="d23c5-120">[Cofre de anexos.](set-up-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d23c5-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="d23c5-121">Os valores  **de configuração** de política Padrão e Estrita usados como linhas de base são descritos em [Configurações recomendadas](recommended-settings-for-eop-and-office365.md)para EOP e Microsoft Defender para Office 365 segurança .</span><span class="sxs-lookup"><span data-stu-id="d23c5-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d23c5-122">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="d23c5-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d23c5-123">Você abre o portal Microsoft 365 Defender em <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="d23c5-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="d23c5-124">Para ir diretamente para a página **analisador de** configuração, use <https://security.microsoft.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="d23c5-124">To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="d23c5-125">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d23c5-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d23c5-126">Você precisa ter permissões atribuídas no portal Microsoft 365 Defender antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="d23c5-126">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d23c5-127">Para usar o **analisador** de configuração e fazer atualizações para  políticas de segurança, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="d23c5-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d23c5-128">Para acesso somente leitura ao analisador de configuração, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="d23c5-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d23c5-129">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="d23c5-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="d23c5-130">Adicionar usuários à função Azure Active Directory correspondente fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d23c5-130">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d23c5-131">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d23c5-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="d23c5-132">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="d23c5-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="d23c5-133">Use o analisador de configuração no portal Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d23c5-133">Use the configuration analyzer in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="d23c5-134">No portal Microsoft 365 Defender, vá para **Email** & políticas de colaboração & políticas de ameaça Seção Políticas \>  \>  \>  \> **modelo. Analisador de configuração.**</span><span class="sxs-lookup"><span data-stu-id="d23c5-134">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Templated policies** section \> **Configuration analyzer**.</span></span>

<span data-ttu-id="d23c5-135">A **página analisador de** configuração tem duas guias principais:</span><span class="sxs-lookup"><span data-stu-id="d23c5-135">The **Configuration analyzer** page has two main tabs:</span></span>

- <span data-ttu-id="d23c5-136">**Configurações e recomendações**: você escolhe **Standard** ou **Strict** e compara essas configurações às políticas de segurança existentes.</span><span class="sxs-lookup"><span data-stu-id="d23c5-136">**Settings and recommendations**: You pick **Standard** or **Strict** and compare those settings to your existing security policies.</span></span> <span data-ttu-id="d23c5-137">Nos resultados, você pode ajustar os valores de suas configurações para trazê-los para o mesmo nível que Standard ou Strict.</span><span class="sxs-lookup"><span data-stu-id="d23c5-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>
- <span data-ttu-id="d23c5-138">**Análise e histórico de desvios de** configuração : essa exibição permite controlar as alterações de política ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="d23c5-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="d23c5-139">Guia Configuração e recomendações no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="d23c5-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="d23c5-140">Por padrão, a guia é aberta na comparação com o perfil de proteção padrão.</span><span class="sxs-lookup"><span data-stu-id="d23c5-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="d23c5-141">Você pode alternar para a comparação do perfil de proteção estrito **selecionando Exibir recomendações estritas.**</span><span class="sxs-lookup"><span data-stu-id="d23c5-141">You can switch to the comparison of the Strict protection profile by selecting **View Strict recommendations**.</span></span> <span data-ttu-id="d23c5-142">Para alternar de volta, selecione **Exibir recomendações padrão**.</span><span class="sxs-lookup"><span data-stu-id="d23c5-142">To switch back, select **View Standard recommendations**.</span></span>

![Configurações e recomendações no analisador de configuração](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="d23c5-144">Por padrão, a coluna **Grupo de política/nome** de configuração contém um modo de exibição recolhido dos diferentes tipos de políticas de segurança e o número de configurações que precisam ser melhoradas (se alguma).</span><span class="sxs-lookup"><span data-stu-id="d23c5-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="d23c5-145">Os tipos de políticas são:</span><span class="sxs-lookup"><span data-stu-id="d23c5-145">The types of policies are:</span></span>

- <span data-ttu-id="d23c5-146">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="d23c5-146">**Anti-spam**</span></span>
- <span data-ttu-id="d23c5-147">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="d23c5-147">**Anti-phishing**</span></span>
- <span data-ttu-id="d23c5-148">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="d23c5-148">**Anti-malware**</span></span>
- <span data-ttu-id="d23c5-149">**Cofre Anexos** (se sua assinatura incluir o Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="d23c5-149">**Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="d23c5-150">**Cofre Links** (se sua assinatura incluir o Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="d23c5-150">**Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="d23c5-151">No modo de exibição padrão, tudo é recolhido.</span><span class="sxs-lookup"><span data-stu-id="d23c5-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="d23c5-152">Ao lado de cada política, há um resumo dos resultados de comparação de suas políticas (que você pode modificar) e as configurações nas políticas correspondentes para os perfis de proteção Standard ou Strict (que você não pode modificar).</span><span class="sxs-lookup"><span data-stu-id="d23c5-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="d23c5-153">Você verá as seguintes informações para o perfil de proteção ao que está comparando:</span><span class="sxs-lookup"><span data-stu-id="d23c5-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="d23c5-154">**Verde**: Todas as configurações em todas as políticas existentes são pelo menos tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="d23c5-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="d23c5-155">**Âmbar**: um pequeno número de configurações nas políticas existentes não são tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="d23c5-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="d23c5-156">**Vermelho**: um número significativo de configurações nas políticas existentes não são tão seguras quanto o perfil de proteção.</span><span class="sxs-lookup"><span data-stu-id="d23c5-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="d23c5-157">Isso pode ser algumas configurações em muitas políticas ou em muitas configurações em uma política.</span><span class="sxs-lookup"><span data-stu-id="d23c5-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="d23c5-158">Para comparações favoráveis, você verá o texto: **Todas as configurações seguem** as \<**Standard** or **Strict**\> **recomendações**.</span><span class="sxs-lookup"><span data-stu-id="d23c5-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="d23c5-159">Caso contrário, você verá o número de configurações recomendadas a ser mudada.</span><span class="sxs-lookup"><span data-stu-id="d23c5-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="d23c5-160">Se você expandir o nome do grupo **de política/configuração**, todas as políticas e as configurações associadas em cada política específica que exigem atenção serão reveladas.</span><span class="sxs-lookup"><span data-stu-id="d23c5-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="d23c5-161">Ou, você pode expandir um tipo específico de política (por exemplo, **Anti-spam**) para ver apenas essas configurações nesses tipos de políticas que exigem sua atenção.</span><span class="sxs-lookup"><span data-stu-id="d23c5-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="d23c5-162">Se a comparação não tiver recomendações de melhoria (verde), a expansão da política não revelará nada.</span><span class="sxs-lookup"><span data-stu-id="d23c5-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="d23c5-163">Se houver qualquer número de recomendações de melhoria (vermelho ou vermelho), as configurações que exigem atenção serão reveladas e as informações correspondentes serão reveladas nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="d23c5-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="d23c5-164">**Nome do grupo de política/configuração:** o nome da configuração que requer sua atenção.</span><span class="sxs-lookup"><span data-stu-id="d23c5-164">**Policy group/setting name**: The name of the setting that requires your attention.</span></span> <span data-ttu-id="d23c5-165">Por exemplo, na captura de tela anterior, são as configurações na política anti-spam padrão.</span><span class="sxs-lookup"><span data-stu-id="d23c5-165">For example, in the previous screenshot, it's the settings in the default anti-spam policy.</span></span>
- <span data-ttu-id="d23c5-166">**Política**: o nome da política afetada que contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="d23c5-166">**Policy**: The name of the affected policy that contains the setting.</span></span>
- <span data-ttu-id="d23c5-167">**Aplicado a**: o número de usuários aos que as políticas afetadas são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d23c5-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>
- <span data-ttu-id="d23c5-168">**Configuração atual**: O valor atual da configuração.</span><span class="sxs-lookup"><span data-stu-id="d23c5-168">**Current configuration**: The current value of the setting.</span></span> <span data-ttu-id="d23c5-169">Para a política padrão desse tipo que se aplica a todos os destinatários, esse valor está em branco.</span><span class="sxs-lookup"><span data-stu-id="d23c5-169">For the default policy of that type that applies to all recipients, this value is blank.</span></span>
- <span data-ttu-id="d23c5-170">**Última modificação:** a data em que a política foi modificada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="d23c5-170">**Last modified**: The date that the policy was last modified.</span></span>
- <span data-ttu-id="d23c5-171">**Recomendações:** o valor da configuração no perfil de proteção Padrão ou Estrito.</span><span class="sxs-lookup"><span data-stu-id="d23c5-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="d23c5-172">Para alterar o valor da configuração em sua política para corresponder ao valor recomendado no perfil de proteção, clique em **Adotar**.</span><span class="sxs-lookup"><span data-stu-id="d23c5-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="d23c5-173">Se a alteração for bem-sucedida, você verá a mensagem: Recomendações **adotada com êxito.**</span><span class="sxs-lookup"><span data-stu-id="d23c5-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="d23c5-174">Clique **em** Atualizar para ver o número reduzido de recomendações e a remoção da linha de configuração/política específica dos resultados.</span><span class="sxs-lookup"><span data-stu-id="d23c5-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="d23c5-175">Análise de deriva de configuração e guia histórico no analisador de configuração</span><span class="sxs-lookup"><span data-stu-id="d23c5-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="d23c5-176">Essa guia permite rastrear as alterações feitas em suas políticas de segurança personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d23c5-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="d23c5-177">Por padrão, as seguintes informações são exibidas:</span><span class="sxs-lookup"><span data-stu-id="d23c5-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="d23c5-178">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="d23c5-178">**Last modified**</span></span>
- <span data-ttu-id="d23c5-179">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="d23c5-179">**Modified by**</span></span>
- <span data-ttu-id="d23c5-180">**Nome da configuração**</span><span class="sxs-lookup"><span data-stu-id="d23c5-180">**Setting Name**</span></span>
- <span data-ttu-id="d23c5-181">**Política**</span><span class="sxs-lookup"><span data-stu-id="d23c5-181">**Policy**</span></span>
- <span data-ttu-id="d23c5-182">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d23c5-182">**Type**</span></span>
- <span data-ttu-id="d23c5-183">**Alteração de configuração**</span><span class="sxs-lookup"><span data-stu-id="d23c5-183">**Configuration change**</span></span>
- <span data-ttu-id="d23c5-184">**Deriva de configuração**: o valor **Aumentar** ou **Diminuir**.</span><span class="sxs-lookup"><span data-stu-id="d23c5-184">**Configuration drift**: The value **Increase** or **Decrease**.</span></span>

<span data-ttu-id="d23c5-185">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="d23c5-185">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d23c5-186">No flyout **Filters** exibido, você pode selecionar entre os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="d23c5-186">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="d23c5-187">**Hora de início** **e hora de término** (data)</span><span class="sxs-lookup"><span data-stu-id="d23c5-187">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="d23c5-188">**Proteção padrão** ou **proteção estrita**</span><span class="sxs-lookup"><span data-stu-id="d23c5-188">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="d23c5-189">Para exportar os resultados para um arquivo .csv, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="d23c5-189">To export the results to a .csv file, click **Export**.</span></span>

![Análise de deriva de configuração e exibição de histórico no analisador de configuração](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
