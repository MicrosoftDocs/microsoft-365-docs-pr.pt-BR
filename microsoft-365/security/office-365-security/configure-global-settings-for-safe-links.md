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
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821976"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d96a2-103">Configurar configurações globais para Cofre links no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d96a2-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d96a2-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="d96a2-104">**Applies to**</span></span>
- [<span data-ttu-id="d96a2-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d96a2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d96a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d96a2-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="d96a2-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d96a2-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="d96a2-108">Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="d96a2-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="d96a2-109">Cofre Links é um recurso no [Microsoft Defender para](defender-for-office-365.md) Office 365 que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="d96a2-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="d96a2-110">Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="d96a2-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="d96a2-111">Você configura a maioria Cofre configurações de Links em Cofre Políticas de Links.</span><span class="sxs-lookup"><span data-stu-id="d96a2-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="d96a2-112">Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d96a2-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="d96a2-113">No entanto, Cofre Links também usa as seguintes configurações globais que você configura fora das políticas Cofre Links por conta própria:</span><span class="sxs-lookup"><span data-stu-id="d96a2-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="d96a2-114">A **lista Bloquear as URLs a** seguir.</span><span class="sxs-lookup"><span data-stu-id="d96a2-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="d96a2-115">Essa configuração se aplica a todos os usuários incluídos em qualquer política Cofre Links ativas.</span><span class="sxs-lookup"><span data-stu-id="d96a2-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="d96a2-116">Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Cofre Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="d96a2-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="d96a2-117">Cofre Proteção de links para Office 365 aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d96a2-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="d96a2-118">Essas configurações se aplicam a todos os usuários da organização licenciados para o Defender para Office 365, independentemente de os usuários estar incluídos em políticas Cofre Links ativos ou não.</span><span class="sxs-lookup"><span data-stu-id="d96a2-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="d96a2-119">Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="d96a2-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="d96a2-120">Você pode configurar as configurações globais de Links do Cofre no centro de segurança do Microsoft 365 ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio Exchange Online, mas com o Microsoft Defender para assinaturas de complemento do Office 365).</span><span class="sxs-lookup"><span data-stu-id="d96a2-120">You can configure the global Safe Links settings in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d96a2-121">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="d96a2-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d96a2-122">Não há política de links interna ou padrão Cofre, portanto, você precisa criar pelo menos uma política Cofre Links para que a lista bloquear as **URLs a** seguir seja ativa.</span><span class="sxs-lookup"><span data-stu-id="d96a2-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="d96a2-123">Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d96a2-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="d96a2-124">Abra o centro de segurança em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="d96a2-124">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="d96a2-125">Para ir diretamente para a página **Cofre Links,** use <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="d96a2-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="d96a2-126">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d96a2-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d96a2-127">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d96a2-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d96a2-128">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="d96a2-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d96a2-129">Para definir as configurações globais para Cofre Links, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="d96a2-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d96a2-130">Para acesso somente leitura às configurações globais para links Cofre, você precisa ser membro dos grupos de função Leitor **Global** ou Leitor **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="d96a2-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d96a2-131">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="d96a2-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="d96a2-132">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="d96a2-132">**Notes**:</span></span>

  - <span data-ttu-id="d96a2-133">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d96a2-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d96a2-134">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d96a2-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d96a2-135">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="d96a2-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="d96a2-136">Para nossos valores recomendados para as configurações globais para links Cofre, [consulte Cofre Configurações de Links.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="d96a2-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="d96a2-137">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="d96a2-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="d96a2-138">[Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="d96a2-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="d96a2-139">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de links Cofre existentes.</span><span class="sxs-lookup"><span data-stu-id="d96a2-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a><span data-ttu-id="d96a2-140">Configurar a lista "Bloquear as URLs a seguir" no centro de segurança</span><span class="sxs-lookup"><span data-stu-id="d96a2-140">Configure the "Block the following URLs" list in the security center</span></span>

<span data-ttu-id="d96a2-141">A **lista Bloquear as URLs** a seguir identifica os links que sempre devem ser bloqueados Cofre verificação de links em aplicativos com suporte.</span><span class="sxs-lookup"><span data-stu-id="d96a2-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="d96a2-142">Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Cofre Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="d96a2-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="d96a2-143">No centro de segurança, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.</span><span class="sxs-lookup"><span data-stu-id="d96a2-143">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="d96a2-144">Na página **Cofre Links,** clique em **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="d96a2-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="d96a2-145">Na política **Cofre Links para** sua organização que aparece, vá para a caixa Bloquear as **URLs a** seguir.</span><span class="sxs-lookup"><span data-stu-id="d96a2-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="d96a2-146">Configure uma ou mais entradas conforme descrito em Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="d96a2-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="d96a2-147">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d96a2-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="d96a2-148">Configurar a lista "Bloquear as URLs a seguir" no PowerShell</span><span class="sxs-lookup"><span data-stu-id="d96a2-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="d96a2-149">Para obter detalhes sobre a sintaxe de entrada, consulte Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="d96a2-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="d96a2-150">Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir entradas existentes na _propriedade BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="d96a2-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="d96a2-151">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no Exchange Online PowerShell ou Proteção do Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d96a2-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="d96a2-152">Este exemplo adiciona as seguintes entradas à lista:</span><span class="sxs-lookup"><span data-stu-id="d96a2-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="d96a2-153">Bloqueie o domínio, subdomas e caminhos para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="d96a2-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="d96a2-154">Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios em tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="d96a2-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="d96a2-155">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d96a2-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="d96a2-156">Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="d96a2-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a><span data-ttu-id="d96a2-157">Configurar Cofre proteção de links para Office 365 aplicativos no centro de segurança</span><span class="sxs-lookup"><span data-stu-id="d96a2-157">Configure Safe Links protection for Office 365 apps in the security center</span></span>

<span data-ttu-id="d96a2-158">Cofre A proteção de links Office 365 aplicativos se aplica a documentos em aplicativos Office desktop, mobile e Web suportados.</span><span class="sxs-lookup"><span data-stu-id="d96a2-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="d96a2-159">Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="d96a2-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="d96a2-160">No centro de segurança, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.</span><span class="sxs-lookup"><span data-stu-id="d96a2-160">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="d96a2-161">Na página **Cofre Links,** clique em **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="d96a2-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="d96a2-162">Na política **Cofre Links** para sua organização que aparece, configure as seguintes configurações no Configurações que se aplicam **ao** conteúdo na seção aplicativos Office 365 com suporte:</span><span class="sxs-lookup"><span data-stu-id="d96a2-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="d96a2-163">**Usar Cofre Links** em aplicativos Office 365 : Verifique se a alternância está à direita para habilitar Cofre Links para aplicativos Office 365 com suporte: ![ Alternar em ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="d96a2-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="d96a2-164">**Não rastreia quando** os usuários clicam em links protegidos em aplicativos Office 365 : Mova a alternância para a esquerda para controlar os cliques do usuário relacionados a URLs bloqueadas em aplicativos Office 365 suportados: ![ Alternar ](../../media/scc-toggle-off.png) para fora .</span><span class="sxs-lookup"><span data-stu-id="d96a2-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="d96a2-165">**Não permitir** que os usuários cliquem na URL original em aplicativos Office 365 : Verifique se a alternância está à direita para impedir que os usuários cliquem na URL bloqueada original em aplicativos Office 365 suportados: ![ Alternar ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="d96a2-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="d96a2-166">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d96a2-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="d96a2-167">Configurar Cofre de links para Office 365 aplicativos no PowerShell</span><span class="sxs-lookup"><span data-stu-id="d96a2-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="d96a2-168">Se você preferir usar o PowerShell para configurar a proteção de links Cofre para aplicativos Office 365, use a seguinte sintaxe no Exchange Online PowerShell ou no Proteção do Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d96a2-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="d96a2-169">Este exemplo configura as seguintes configurações para a proteção Cofre Links em Office 365 aplicativos:</span><span class="sxs-lookup"><span data-stu-id="d96a2-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="d96a2-170">Cofre Links para Office 365 aplicativos estão ativados (não estamos usando o _parâmetro EnableSafeLinksForO365Clients_ e o valor padrão é $true).</span><span class="sxs-lookup"><span data-stu-id="d96a2-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="d96a2-171">Cliques do usuário relacionados a URLs bloqueadas em Office 365 aplicativos são rastreados.</span><span class="sxs-lookup"><span data-stu-id="d96a2-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="d96a2-172">Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos Office 365 com suporte (não estamos usando o parâmetro _AllowClickThrough_ e o valor padrão é $false).</span><span class="sxs-lookup"><span data-stu-id="d96a2-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="d96a2-173">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d96a2-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d96a2-174">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="d96a2-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="d96a2-175">Para verificar se você configurou com êxito as configurações globais para links Cofre (a lista Bloquear as **SEGUINTES URLs** e as configurações de proteção de aplicativos Office 365), faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d96a2-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="d96a2-176">No centro de segurança, vá até **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras Cofre Links clique em Configurações globais e verifique as configurações no sobrevoo que \>  \>  \>  \>  \> aparece. </span><span class="sxs-lookup"><span data-stu-id="d96a2-176">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="d96a2-177">No Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="d96a2-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="d96a2-178">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d96a2-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
