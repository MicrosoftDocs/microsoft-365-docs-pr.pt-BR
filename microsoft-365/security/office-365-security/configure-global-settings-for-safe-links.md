---
title: Definir configurações globais para configurações de links seguros no defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir e definir as configurações globais (a lista e proteção dos seguintes URLs para aplicativos do Office 365) para links seguros no Microsoft defender para Office 365.
ms.openlocfilehash: 2793985e6289b26baad268925cbf9c5e9a89dce9
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572424"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3b8e-103">Definir configurações globais para links seguros no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3b8e-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="c3b8e-104">Este artigo destina-se a clientes comerciais que têm [o Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="c3b8e-105">Se você for um usuário doméstico que procura informações sobre o Safelinks no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c3b8e-106">Links seguros é um recurso do [Microsoft defender para Office 365](office-365-atp.md) que oferece verificação de URL de mensagens de email de entrada no fluxo de emails e a hora de clicar em verificação de URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="c3b8e-107">Para obter mais informações, consulte [links seguros no Microsoft defender para Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="c3b8e-108">Você define as configurações de links mais seguros em políticas de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="c3b8e-109">Para obter instruções, consulte [set up Safe links Policies in Microsoft defender for Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-109">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="c3b8e-110">No entanto, os links seguros também usam configurações globais que se aplicam a todos os usuários que estão incluídos em qualquer política ativa de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="c3b8e-111">Área de configurações globais:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-111">These global settings area:</span></span>

- <span data-ttu-id="c3b8e-112">O **bloqueia a lista de URLs a seguir** .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="c3b8e-113">Para obter mais informações, consulte [a lista "bloquear as seguintes URLs" para links seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="c3b8e-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="c3b8e-114">Proteção de links seguros para aplicativos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="c3b8e-115">Para obter mais informações, consulte [configurações de links seguros para aplicativos do Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="c3b8e-116">Você pode definir as configurações de links seguros globais no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações qualificadas da Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online, mas com o Microsoft defender para Office 365 assinaturas complementares).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3b8e-117">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c3b8e-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3b8e-118">Os recursos fornecidos por configurações globais para links seguros só são aplicados aos usuários incluídos em políticas de links seguros ativos.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="c3b8e-119">Não há nenhuma política interna ou de links seguros padrão, portanto, você precisa criar pelo menos uma política de links seguros para que essas configurações globais estejam ativas.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="c3b8e-120">Para obter instruções, consulte [set up Safe links Policies in Microsoft defender for Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-120">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="c3b8e-121">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c3b8e-122">Para ir diretamente para a página de **links seguros** , use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-122">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="c3b8e-123">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c3b8e-124">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c3b8e-125">Você precisa receber permissões no centro de conformidade & de segurança antes de realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c3b8e-126">Para definir as configurações globais de links seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-126">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c3b8e-127">Para acesso somente leitura às configurações globais de links seguros, você precisa ser membro dos grupos de função **leitor global** ou leitor de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-127">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c3b8e-128">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="c3b8e-129">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-129">**Notes**:</span></span>

  - <span data-ttu-id="c3b8e-130">A adição de usuários à função do Azure Active Directory correspondente no centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no centro de conformidade _e_ segurança & para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c3b8e-131">Para obter mais informações, confira [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="c3b8e-132">O grupo de função de **Gerenciamento de organização somente exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="c3b8e-133">Para obter os valores recomendados para as configurações globais de links seguros, consulte [configurações de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-133">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="c3b8e-134">Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-134">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c3b8e-135">[Novos recursos estão sempre sendo adicionados ao Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-135">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="c3b8e-136">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes em suas políticas de links seguros existentes.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-136">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="c3b8e-137">Configurar a lista "bloquear as seguintes URLs" no centro de conformidade de & de segurança</span><span class="sxs-lookup"><span data-stu-id="c3b8e-137">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="c3b8e-138">A lista de **URLs a seguir** identifica os links que devem ser sempre bloqueados pela verificação de links seguros em aplicativos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-138">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="c3b8e-139">Para obter mais informações, consulte [a lista "bloquear as seguintes URLs" para obter links seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-139">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="c3b8e-140">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **links seguros de ATP** e clique em **configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="c3b8e-141">Na **política de links seguros de sua organização** que aparece, vá para a caixa **bloquear as seguintes URLs** .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-141">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="c3b8e-142">Configure uma ou mais entradas, conforme descrito na [sintaxe de entrada da lista "bloquear as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-142">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="c3b8e-143">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-143">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="c3b8e-144">Configurar a lista "bloquear as seguintes URLs" no PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3b8e-144">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="c3b8e-145">Para obter detalhes sobre a sintaxe de entrada, consulte a [sintaxe de entrada para a lista "bloquear as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-145">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="c3b8e-146">Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir as entradas existentes na propriedade _BlockURLs_ .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-146">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="c3b8e-147">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no PowerShell do Exchange Online ou do Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-147">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="c3b8e-148">Este exemplo adiciona as seguintes entradas à lista:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-148">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="c3b8e-149">Bloquear o domínio, subdomínios e caminhos para o fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-149">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="c3b8e-150">Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios no tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="c3b8e-150">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="c3b8e-151">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-151">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="c3b8e-152">Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada de fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-152">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="c3b8e-153">Configurar a proteção de links seguros para aplicativos do Office 365 no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="c3b8e-153">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="c3b8e-154">Proteção de links seguros para aplicativos do Office 365 aplica-se a documentos em aplicativos da Web, móveis e da área de trabalho do Office compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-154">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="c3b8e-155">Para obter mais informações, consulte [configurações de links seguros para aplicativos do Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-155">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="c3b8e-156">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **links seguros de ATP** e clique em **configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="c3b8e-157">Na **política de links seguros de sua organização** que aparece, defina as seguintes configurações na seção **configurações que se aplicam ao conteúdo exceto o email** :</span><span class="sxs-lookup"><span data-stu-id="c3b8e-157">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="c3b8e-158">**Aplicativos do office 365**: Verifique se a opção Alternar está à direita para habilitar links seguros para aplicativos do Office 365 suportados: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-158">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="c3b8e-159">**Não rastrear quando os usuários clicarem em links seguros**: mover a opção para a esquerda para rastrear os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 com suporte: ![ desativar ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-159">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="c3b8e-160">**Não permita que os usuários cliquem através de links seguros para a URL original**: Verifique se o botão de alternância está à direita para impedir que os usuários cliquem no URL bloqueado original em aplicativos do Office 365 com suporte: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="c3b8e-160">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="c3b8e-161">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-161">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="c3b8e-162">Configurar a proteção de links seguros para aplicativos do Office 365 no PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3b8e-162">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="c3b8e-163">Se você preferir usar o PowerShell para configurar a proteção de links seguros para aplicativos do Office 365, use a seguinte sintaxe no PowerShell do Exchange Online ou do Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-163">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="c3b8e-164">Este exemplo define as seguintes configurações para proteção de links seguros em aplicativos do Office 365:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-164">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="c3b8e-165">Os links seguros para aplicativos do Office 365 estão ativados (não estamos usando o parâmetro _EnableSafeLinksForO365Clients_ , e o valor padrão é $true).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-165">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="c3b8e-166">Os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 com suporte são rastreados.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-166">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="c3b8e-167">Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos compatíveis com o Office 365 (não estamos usando o parâmetro _AllowClickThrough_ , e o valor padrão é $false).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-167">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="c3b8e-168">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-168">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c3b8e-169">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="c3b8e-169">How do you know these procedures worked?</span></span>

<span data-ttu-id="c3b8e-170">Para verificar se você configurou com êxito as configurações globais para links seguros (a lista de **seguintes URLs** e as configurações de proteção de aplicativos do Office 365), execute qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-170">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="c3b8e-171">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> , **links seguros de ATP**, clique em **configurações globais** e verifique as configurações na saída que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-171">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="c3b8e-172">No PowerShell do Exchange Online ou do Exchange Online Protection, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="c3b8e-172">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="c3b8e-173">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
