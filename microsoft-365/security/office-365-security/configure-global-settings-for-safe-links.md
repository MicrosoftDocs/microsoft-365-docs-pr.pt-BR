---
title: Configurar configurações globais para Cofre de links no Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir e configurar configurações globais (a lista "Bloquear as URLs a seguir" e a proteção para aplicativos Office 365) para links do Cofre no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11544953bf348c47e697b3210da709cccdb31a7e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245835"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e0ddd-103">Configurar configurações globais para Cofre links no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0ddd-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0ddd-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e0ddd-104">**Applies to**</span></span>
- [<span data-ttu-id="e0ddd-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0ddd-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e0ddd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0ddd-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="e0ddd-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="e0ddd-108">Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e0ddd-109">Cofre Links é um recurso no [Microsoft Defender para](defender-for-office-365.md) Office 365 que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="e0ddd-110">Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="e0ddd-111">Você configura a maioria Cofre configurações de Links em Cofre Políticas de Links.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="e0ddd-112">Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="e0ddd-113">No entanto, Cofre Links também usa as seguintes configurações globais que você configura fora das políticas Cofre Links por conta própria:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="e0ddd-114">A **lista Bloquear as URLs a** seguir.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="e0ddd-115">Essa configuração se aplica a todos os usuários incluídos em qualquer política Cofre Links ativas.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="e0ddd-116">Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Cofre Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="e0ddd-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="e0ddd-117">Cofre Proteção de links para Office 365 aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="e0ddd-118">Essas configurações se aplicam a todos os usuários da organização licenciados para o Defender para Office 365, independentemente de os usuários estar incluídos em políticas Cofre Links ativos ou não.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="e0ddd-119">Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="e0ddd-120">Você pode configurar as configurações globais de Links do Cofre no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio Exchange Online, mas com o Microsoft Defender para assinaturas de complemento do Office 365).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-120">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e0ddd-121">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="e0ddd-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e0ddd-122">Não há política de links interna ou padrão Cofre, portanto, você precisa criar pelo menos uma política Cofre Links para que a lista bloquear as **URLs a** seguir seja ativa.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="e0ddd-123">Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="e0ddd-124">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e0ddd-125">Para ir diretamente para a página **Cofre Links,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="e0ddd-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="e0ddd-126">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e0ddd-127">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e0ddd-128">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e0ddd-129">Para definir as configurações globais para Cofre Links, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e0ddd-130">Para acesso somente leitura às configurações globais para links Cofre, você precisa ser membro dos grupos de função Leitor **Global** ou Leitor **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e0ddd-131">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e0ddd-132">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-132">**Notes**:</span></span>

  - <span data-ttu-id="e0ddd-133">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e0ddd-134">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e0ddd-135">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e0ddd-136">Para nossos valores recomendados para as configurações globais para links Cofre, [consulte Cofre Configurações de Links.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="e0ddd-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="e0ddd-137">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="e0ddd-138">[Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="e0ddd-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="e0ddd-139">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de links Cofre existentes.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="e0ddd-140">Configure a lista "Bloquear as URLs a seguir" no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="e0ddd-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="e0ddd-141">A **lista Bloquear as URLs** a seguir identifica os links que sempre devem ser bloqueados Cofre verificação de links em aplicativos com suporte.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="e0ddd-142">Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Cofre Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="e0ddd-143">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças ATP Cofre Links e clique \>  \> em **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="e0ddd-144">Na política **Cofre Links para** sua organização que aparece, vá para a caixa Bloquear as **URLs a** seguir.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="e0ddd-145">Configure uma ou mais entradas conforme descrito em Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e0ddd-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="e0ddd-146">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="e0ddd-147">Configurar a lista "Bloquear as URLs a seguir" no PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0ddd-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="e0ddd-148">Para obter detalhes sobre a sintaxe de entrada, consulte Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e0ddd-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="e0ddd-149">Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir entradas existentes na _propriedade BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="e0ddd-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="e0ddd-150">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no Exchange Online PowerShell ou Proteção do Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="e0ddd-151">Este exemplo adiciona as seguintes entradas à lista:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="e0ddd-152">Bloqueie o domínio, subdomas e caminhos para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="e0ddd-153">Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios em tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="e0ddd-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="e0ddd-154">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="e0ddd-155">Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="e0ddd-156">Configurar Cofre de links para Office 365 aplicativos no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="e0ddd-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="e0ddd-157">Cofre A proteção de links Office 365 aplicativos se aplica a documentos em aplicativos Office desktop, mobile e Web suportados.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="e0ddd-158">Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="e0ddd-159">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças ATP Cofre Links e clique \>  \> em **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="e0ddd-160">Na política **Cofre Links** para sua organização que aparece, configure as seguintes configurações no Configurações que se aplicam ao conteúdo, exceto à seção **email:**</span><span class="sxs-lookup"><span data-stu-id="e0ddd-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="e0ddd-161">**Office 365**: Verifique se a alternância está à direita para habilitar Cofre Links para aplicativos Office 365 com ![ suporte: Alternar ](../../media/scc-toggle-on.png) em .</span><span class="sxs-lookup"><span data-stu-id="e0ddd-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="e0ddd-162">**Não rastreia quando** os usuários clicam em Cofre Links: mova a alternância para a esquerda para controlar os cliques do usuário relacionados a URLs bloqueadas em aplicativos Office 365 com suporte: ![ Alternar ](../../media/scc-toggle-off.png) para fora .</span><span class="sxs-lookup"><span data-stu-id="e0ddd-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="e0ddd-163">**Não permitir que** os usuários cliquem em Cofre Links para a URL original : Verifique se a alternância está à direita para impedir que os usuários cliquem na URL bloqueada original em aplicativos Office 365 com suporte: ![ Alternar em ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="e0ddd-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="e0ddd-164">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="e0ddd-165">Configurar Cofre de links para Office 365 aplicativos no PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0ddd-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="e0ddd-166">Se você preferir usar o PowerShell para configurar a proteção de links Cofre para aplicativos Office 365, use a seguinte sintaxe no Exchange Online PowerShell ou no Proteção do Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="e0ddd-167">Este exemplo configura as seguintes configurações para a proteção Cofre Links em Office 365 aplicativos:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="e0ddd-168">Cofre Links para Office 365 aplicativos estão ativados (não estamos usando o _parâmetro EnableSafeLinksForO365Clients_ e o valor padrão é $true).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="e0ddd-169">Cliques do usuário relacionados a URLs bloqueadas em Office 365 aplicativos são rastreados.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="e0ddd-170">Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos Office 365 com suporte (não estamos usando o parâmetro _AllowClickThrough_ e o valor padrão é $false).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="e0ddd-171">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e0ddd-172">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="e0ddd-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="e0ddd-173">Para verificar se você configurou com êxito as configurações globais para links Cofre (a lista Bloquear as **SEGUINTES URLs** e as configurações de proteção de aplicativos Office 365), faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="e0ddd-174">No Centro de Conformidade & segurança,  vá para Política de Gerenciamento de Ameaças atp Cofre \>  \> **Links,** clique em **Configurações** globais e verifique as configurações no fly out que aparece.</span><span class="sxs-lookup"><span data-stu-id="e0ddd-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="e0ddd-175">No Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="e0ddd-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="e0ddd-176">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="e0ddd-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
