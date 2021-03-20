---
title: Definir configurações globais para configurações de Links Seguros no Defender para Office 365
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
description: Os administradores podem aprender a exibir e configurar configurações globais (a lista "Bloquear as URLs a seguir" e a proteção para aplicativos do Office 365) para Links Seguros no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3466f515458b05a5c00053a30fad8f5a84802fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906559"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f4039-103">Configurar configurações globais para Links Seguros no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4039-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4039-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f4039-104">**Applies to**</span></span>
- [<span data-ttu-id="f4039-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4039-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f4039-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4039-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="f4039-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f4039-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="f4039-108">Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="f4039-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f4039-109">Links Seguros é um recurso do [Microsoft Defender para Office 365](office-365-atp.md) que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="f4039-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="f4039-110">Para obter mais informações, consulte [Links seguros no Microsoft Defender para Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="f4039-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="f4039-111">Você configura a maioria das configurações de Links Seguros em políticas de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="f4039-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="f4039-112">Para obter instruções, consulte [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f4039-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="f4039-113">No entanto, Os Links Seguros também usam configurações globais que se aplicam a todos os usuários incluídos em quaisquer políticas de Links Seguros ativos.</span><span class="sxs-lookup"><span data-stu-id="f4039-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="f4039-114">Estas áreas de configurações globais:</span><span class="sxs-lookup"><span data-stu-id="f4039-114">These global settings area:</span></span>

- <span data-ttu-id="f4039-115">A **lista Bloquear as URLs a** seguir.</span><span class="sxs-lookup"><span data-stu-id="f4039-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="f4039-116">Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Links Seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="f4039-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="f4039-117">Proteção de Links Seguros para aplicativos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4039-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="f4039-118">Para obter mais informações, consulte [Configurações de Links Seguros para aplicativos do Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="f4039-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="f4039-119">Você pode configurar as configurações globais de Links Seguros no Centro de Conformidade de Segurança & ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="f4039-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4039-120">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f4039-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4039-121">Os recursos fornecidos pelas configurações globais para Links Seguros só são aplicados aos usuários incluídos em políticas ativas de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="f4039-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="f4039-122">Não há política interna ou padrão de Links Seguros, portanto, você precisa criar pelo menos uma política de Links Seguros para que essas configurações globais sejam ativas.</span><span class="sxs-lookup"><span data-stu-id="f4039-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="f4039-123">Para obter instruções, consulte [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f4039-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="f4039-124">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f4039-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f4039-125">Para ir diretamente para a página **Links Seguros,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="f4039-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="f4039-126">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4039-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f4039-127">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4039-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f4039-128">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="f4039-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f4039-129">Para definir as configurações globais para Links Seguros, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="f4039-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f4039-130">Para acesso somente leitura às configurações globais para Links Seguros, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="f4039-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f4039-131">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="f4039-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="f4039-132">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="f4039-132">**Notes**:</span></span>

  - <span data-ttu-id="f4039-133">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4039-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f4039-134">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f4039-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="f4039-135">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="f4039-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f4039-136">Para nossos valores recomendados para as configurações globais para Links Seguros, consulte [Configurações de Links Seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="f4039-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="f4039-137">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="f4039-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f4039-138">[Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="f4039-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f4039-139">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas existentes de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="f4039-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="f4039-140">Configure a lista "Bloquear as URLs a seguir" no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="f4039-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="f4039-141">A **lista Bloquear as URLs** a seguir identifica os links que sempre devem ser bloqueados pela verificação de Links Seguros em aplicativos com suporte.</span><span class="sxs-lookup"><span data-stu-id="f4039-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="f4039-142">Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Links Seguros.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="f4039-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="f4039-143">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças Atp Links Seguros e clique \>  \> em **Configurações Globais**.</span><span class="sxs-lookup"><span data-stu-id="f4039-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="f4039-144">Na política **Links Seguros para sua organização** que aparece, vá para a caixa Bloquear as **URLs a** seguir.</span><span class="sxs-lookup"><span data-stu-id="f4039-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="f4039-145">Configure uma ou mais entradas conforme descrito em Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f4039-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="f4039-146">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4039-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="f4039-147">Configurar a lista "Bloquear as URLs a seguir" no PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4039-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="f4039-148">Para obter detalhes sobre a sintaxe de entrada, consulte Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f4039-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="f4039-149">Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir entradas existentes na _propriedade BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="f4039-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="f4039-150">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no PowerShell do Exchange Online ou no PowerShell de Proteção do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f4039-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="f4039-151">Este exemplo adiciona as seguintes entradas à lista:</span><span class="sxs-lookup"><span data-stu-id="f4039-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="f4039-152">Bloqueie o domínio, subdomas e caminhos para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f4039-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="f4039-153">Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios em tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="f4039-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="f4039-154">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f4039-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="f4039-155">Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f4039-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="f4039-156">Configurar a proteção de Links Seguros para aplicativos do Office 365 no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="f4039-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="f4039-157">A proteção de Links Seguros para aplicativos do Office 365 se aplica a documentos em aplicativos da área de trabalho, dispositivos móveis e web do Office com suporte.</span><span class="sxs-lookup"><span data-stu-id="f4039-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="f4039-158">Para obter mais informações, consulte [Configurações de Links Seguros para aplicativos do Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="f4039-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="f4039-159">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças Atp Links Seguros e clique \>  \> em **Configurações Globais**.</span><span class="sxs-lookup"><span data-stu-id="f4039-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="f4039-160">Na política **Links Seguros para sua** organização que aparece, configure as seguintes configurações na seção Configurações que se aplicam ao conteúdo, exceto **email:**</span><span class="sxs-lookup"><span data-stu-id="f4039-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="f4039-161">**Aplicativos do Office 365**: Verifique se a alternância está à direita para habilitar Links Seguros para aplicativos do Office 365 com ![ suporte: Alternar ](../../media/scc-toggle-on.png) em .</span><span class="sxs-lookup"><span data-stu-id="f4039-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="f4039-162">**Não rastreia quando** os usuários clicam em Links Seguros : Mova a alternância para a esquerda para controlar os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 com suporte: ![ Alternar ](../../media/scc-toggle-off.png) para fora .</span><span class="sxs-lookup"><span data-stu-id="f4039-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="f4039-163">**Não permitir que** os usuários cliquem em Links Seguros para a URL original : Verifique se a alternância está à direita para impedir que os usuários cliquem na URL bloqueada original em aplicativos do Office 365 com suporte: ![ Alternar em ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="f4039-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="f4039-164">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4039-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="f4039-165">Configurar a proteção de links seguros para aplicativos do Office 365 no PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4039-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="f4039-166">Se você preferir usar o PowerShell para configurar a proteção de Links Seguros para aplicativos do Office 365, use a seguinte sintaxe no PowerShell do Exchange Online ou no PowerShell de Proteção do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f4039-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="f4039-167">Este exemplo configura as seguintes configurações para a proteção de Links Seguros em aplicativos do Office 365:</span><span class="sxs-lookup"><span data-stu-id="f4039-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="f4039-168">Links seguros para aplicativos do Office 365 está ativado (não estamos usando o parâmetro _EnableSafeLinksForO365Clients_ e o valor padrão é $true).</span><span class="sxs-lookup"><span data-stu-id="f4039-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="f4039-169">Os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 suportados são rastreados.</span><span class="sxs-lookup"><span data-stu-id="f4039-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="f4039-170">Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos do Office 365 com suporte (não estamos usando o parâmetro _AllowClickThrough_ e o valor padrão é $false).</span><span class="sxs-lookup"><span data-stu-id="f4039-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="f4039-171">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="f4039-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f4039-172">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="f4039-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="f4039-173">Para verificar se você configurou com êxito as configurações globais para Links Seguros (a lista Bloquear as **URLs** a seguir e as configurações de proteção de aplicativos do Office 365), faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f4039-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="f4039-174">No Centro de Conformidade & segurança,  vá até Política de Gerenciamento de Ameaças Links Seguros atp , clique em Configurações globais e verifique as configurações no \>  \> fly out que aparece.</span><span class="sxs-lookup"><span data-stu-id="f4039-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="f4039-175">No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="f4039-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="f4039-176">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="f4039-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>