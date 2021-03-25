---
title: Configurar políticas de Links Seguros no Microsoft Defender para Office 365
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
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de Links Seguros e configurações globais de Links Seguros no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203037"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="55fc7-103">Configurar políticas de Links Seguros no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="55fc7-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="55fc7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="55fc7-104">**Applies to**</span></span>
- [<span data-ttu-id="55fc7-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="55fc7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="55fc7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55fc7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="55fc7-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="55fc7-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="55fc7-108">Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="55fc7-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="55fc7-109">Links Seguros é um recurso do [Microsoft Defender para Office 365](defender-for-office-365.md) que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="55fc7-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="55fc7-110">Para obter mais informações, consulte [Links seguros no Microsoft Defender para Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="55fc7-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="55fc7-111">Não há nenhuma política interna ou padrão de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="55fc7-112">Para obter a verificação de URLs de Links Seguros, você precisa criar uma ou mais políticas de Links Seguros, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="55fc7-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc7-113">Você configura as configurações globais para proteção de Links Seguros **fora das** políticas de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="55fc7-114">Para obter instruções, consulte [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="55fc7-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="55fc7-115">Você pode configurar políticas de Links Seguros no Centro de Conformidade de Segurança & ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; PowerShell autônomo do EOP para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="55fc7-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="55fc7-116">Os elementos básicos de uma política de Links Seguros são:</span><span class="sxs-lookup"><span data-stu-id="55fc7-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="55fc7-117">A política de **links** seguros : ativar a proteção de Links Seguros, ativar a verificação de URL em tempo real, especificar se a verificação em tempo real deve ser concluída antes de entregar a mensagem, ativar a verificação de mensagens internas, especificar se deve rastrear os cliques do usuário em URLs e especificar se os usuários devem clicar na URL original.</span><span class="sxs-lookup"><span data-stu-id="55fc7-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="55fc7-118">**A regra de links seguros**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="55fc7-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="55fc7-119">A diferença entre esses dois elementos não é óbvia quando você gerencia as polícias de Links Seguros no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="55fc7-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="55fc7-120">Ao criar uma política de Links Seguros, você está realmente criando uma regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="55fc7-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="55fc7-121">Quando você modifica uma política de Links Seguros, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="55fc7-122">Todas as outras configurações modificam a política de links seguros associados.</span><span class="sxs-lookup"><span data-stu-id="55fc7-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="55fc7-123">Quando você remove uma política de Links Seguros, a regra de links seguros e a política de links seguros associados são removidas.</span><span class="sxs-lookup"><span data-stu-id="55fc7-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="55fc7-124">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="55fc7-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="55fc7-125">Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online ou [o EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autônomo para configurar políticas de Links Seguros posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="55fc7-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="55fc7-126">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="55fc7-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="55fc7-127">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="55fc7-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="55fc7-128">Para ir diretamente para a página **Links Seguros,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="55fc7-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="55fc7-129">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="55fc7-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="55fc7-130">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="55fc7-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="55fc7-131">Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="55fc7-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="55fc7-132">Para criar, modificar e excluir políticas de Links Seguros  &,  você precisa ser membro dos grupos de  função Gerenciamento  da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de função Gerenciamento da Organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55fc7-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="55fc7-133">Para acesso somente leitura a políticas de Links Seguros, você precisa ser membro dos grupos de função Leitor **Global ou** **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="55fc7-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="55fc7-134">Para obter mais informações, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="55fc7-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="55fc7-135">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55fc7-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="55fc7-136">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="55fc7-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="55fc7-137">.</span><span class="sxs-lookup"><span data-stu-id="55fc7-137">.</span></span> <span data-ttu-id="55fc7-138">- O **grupo de função Gerenciamento** de Organização Somente Exibição no Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="55fc7-138">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="55fc7-139">Para nossas configurações recomendadas para políticas de Links Seguros, consulte Configurações de política [de Links Seguros.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="55fc7-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="55fc7-140">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="55fc7-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="55fc7-141">[Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="55fc7-141">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="55fc7-142">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas existentes de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="55fc7-143">Use o Centro de Conformidade & segurança para criar políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="55fc7-144">A criação de uma política & de Links Seguros personalizada no Centro de Conformidade e Segurança cria a regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="55fc7-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="55fc7-145">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="55fc7-146">Na página **Links Seguros,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="55fc7-147">O **assistente de política Novos Links Seguros** é aberto.</span><span class="sxs-lookup"><span data-stu-id="55fc7-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="55fc7-148">Na página **Nomear sua política,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="55fc7-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="55fc7-149">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="55fc7-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="55fc7-150">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="55fc7-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="55fc7-151">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="55fc7-152">Na página **Configurações** exibida, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="55fc7-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="55fc7-153">**Selecione a ação para URLs** mal-intencionadas desconhecidas em mensagens : Selecione **Ativado** para habilitar a proteção de Links Seguros para links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="55fc7-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="55fc7-154">**Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas no Microsoft Teams : Selecione **Ativado** para habilitar a proteção de Links Seguros para links no Teams.</span><span class="sxs-lookup"><span data-stu-id="55fc7-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="55fc7-155">**Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Selecione essa configuração para habilitar a verificação em tempo real de links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="55fc7-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="55fc7-156">**Aguarde a conclusão da** verificação de URL antes de entregar a mensagem : Selecione essa configuração para aguardar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="55fc7-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="55fc7-157">**Aplicar Links Seguros a mensagens de email** enviadas dentro da organização : Selecione essa configuração para aplicar a política de Links Seguros a mensagens entre os destinatários internos e os destinatários internos.</span><span class="sxs-lookup"><span data-stu-id="55fc7-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="55fc7-158">**Não acompanhar cliques do usuário**: Deixe essa configuração não eleita para habilitar os cliques do usuário de controle em URLs em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="55fc7-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="55fc7-159">**Não permita que os usuários cliquem** na URL original : Selecione essa configuração para impedir que os usuários cliquem na URL original em páginas [de aviso.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="55fc7-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="55fc7-160">**Não reescreva as SEGUINTES URLs**: Permite acessar as URLs especificadas que seriam bloqueadas por Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="55fc7-161">Na caixa, digite a URL ou o valor que você deseja e clique em</span><span class="sxs-lookup"><span data-stu-id="55fc7-161">In the box, type the URL or value that you want, and then click</span></span> ![Adicionar ícone de botão](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="55fc7-163">.</span><span class="sxs-lookup"><span data-stu-id="55fc7-163">.</span></span>

     <span data-ttu-id="55fc7-164">Para remover uma entrada existente, selecione-a e clique em</span><span class="sxs-lookup"><span data-stu-id="55fc7-164">To remove an existing entry, select it and then click</span></span> ![Excluir ícone de botão](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="55fc7-166">.</span><span class="sxs-lookup"><span data-stu-id="55fc7-166">.</span></span>

     <span data-ttu-id="55fc7-167">Para a sintaxe de entrada, consulte [Sintaxe de entrada para a lista "Não reescrever as URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="55fc7-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="55fc7-168">Para obter informações detalhadas sobre essas configurações, consulte [Configurações](safe-links.md#safe-links-settings-for-email-messages) de Links Seguros para mensagens de email e configurações de Links Seguros [para o Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="55fc7-168">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="55fc7-169">Para obter mais valores recomendados para configurações de política Padrão e Estrita, consulte Configurações de política [de Links Seguros.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="55fc7-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="55fc7-170">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="55fc7-171">Na página **Aplicada à** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="55fc7-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="55fc7-172">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="55fc7-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="55fc7-173">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="55fc7-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="55fc7-174">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="55fc7-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="55fc7-175">Clique **em Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-175">Click **Add a condition**.</span></span> <span data-ttu-id="55fc7-176">No menu suspenso exibido, selecione uma condição em **Aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="55fc7-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="55fc7-177">**O destinatário é**: Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="55fc7-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="55fc7-178">**O destinatário é membro de**: Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="55fc7-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="55fc7-179">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="55fc7-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="55fc7-180">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="55fc7-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="55fc7-181">Clique na caixa e role a lista de valores a ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="55fc7-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="55fc7-182">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="55fc7-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="55fc7-183">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="55fc7-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="55fc7-184">Para remover entradas individuais, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="55fc7-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="55fc7-185">Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="55fc7-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="55fc7-186">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **Applied if**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="55fc7-187">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="55fc7-188">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="55fc7-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="55fc7-189">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="55fc7-190">Na página **Revisar suas configurações** que aparece, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="55fc7-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="55fc7-191">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="55fc7-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="55fc7-192">Quando terminar, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="55fc7-193">Use o Centro de Conformidade & segurança para exibir políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="55fc7-194">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="55fc7-195">Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="55fc7-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="55fc7-196">Os detalhes da política aparecem em um fly-out</span><span class="sxs-lookup"><span data-stu-id="55fc7-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="55fc7-197">Use o Centro de Conformidade & segurança para modificar políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="55fc7-198">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="55fc7-199">Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="55fc7-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="55fc7-200">Nos detalhes da política exibidos, clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="55fc7-201">As configurações disponíveis no sobrevoo que aparece são idênticas às descritas na seção Usar o Centro de Conformidade & Segurança para criar políticas [de Links](#use-the-security--compliance-center-to-create-safe-links-policies) Seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="55fc7-202">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="55fc7-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="55fc7-203">Habilitar ou desabilitar políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="55fc7-204">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="55fc7-205">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="55fc7-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="55fc7-206">Mova o botão de alternância para a esquerda para desabilitar a política:</span><span class="sxs-lookup"><span data-stu-id="55fc7-206">Move the toggle to the left to disable the policy:</span></span> ![Desativar a política](../../media/scc-toggle-off.png)<span data-ttu-id="55fc7-208">.</span><span class="sxs-lookup"><span data-stu-id="55fc7-208">.</span></span>

   - <span data-ttu-id="55fc7-209">Mova o botão de alternância para a direita para habilitar a política:</span><span class="sxs-lookup"><span data-stu-id="55fc7-209">Move the toggle to the right to enable the policy:</span></span> ![Ativar a política](../../media/scc-toggle-on.png)<span data-ttu-id="55fc7-211">.</span><span class="sxs-lookup"><span data-stu-id="55fc7-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="55fc7-212">Definir a prioridade das políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="55fc7-213">Por padrão, as políticas de Links Seguros têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="55fc7-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="55fc7-214">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="55fc7-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="55fc7-215">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="55fc7-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="55fc7-216">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="55fc7-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="55fc7-217">As políticas de Links Seguros são exibidas na ordem em que são processadas (a primeira política tem o **valor Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="55fc7-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="55fc7-218">No Centro de Conformidade & segurança, você só pode alterar a prioridade da política links seguros após a criação.</span><span class="sxs-lookup"><span data-stu-id="55fc7-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="55fc7-219">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="55fc7-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="55fc7-220">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="55fc7-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="55fc7-221">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="55fc7-222">Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="55fc7-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="55fc7-223">Nos detalhes da política exibidos, clique no botão de prioridade disponível:</span><span class="sxs-lookup"><span data-stu-id="55fc7-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="55fc7-224">A política links seguros com o **valor Prioridade** **0** tem apenas o **botão Diminuir** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="55fc7-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="55fc7-225">A política Links Seguros com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão Aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="55fc7-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="55fc7-226">Se você tiver três ou mais políticas de Links Seguros, as políticas  entre os valores de prioridade mais altos e mais baixos terão os botões **Aumentar** prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="55fc7-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="55fc7-227">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor Priority.**</span><span class="sxs-lookup"><span data-stu-id="55fc7-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="55fc7-228">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="55fc7-229">Use o Centro de Conformidade & segurança para remover políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="55fc7-230">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="55fc7-231">Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="55fc7-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="55fc7-232">Nos detalhes da política exibidos, clique em **Excluir política** e clique em **Sim** na caixa de diálogo de aviso exibida.</span><span class="sxs-lookup"><span data-stu-id="55fc7-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="55fc7-233">Usar o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="55fc7-234">Conforme descrito anteriormente, uma política de Links Seguros consiste em uma política de links seguros e uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="55fc7-235">No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente.</span><span class="sxs-lookup"><span data-stu-id="55fc7-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="55fc7-236">Você gerencia políticas de links seguros usando os cmdlets **\* -SafeLinksPolicy** e gerencia as regras de links seguros usando os cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="55fc7-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="55fc7-237">No PowerShell, primeiro você cria a política de links seguros e, em seguida, cria a regra de links seguros que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="55fc7-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="55fc7-238">No PowerShell, você modifica as configurações na política de links seguros e a regra de links seguros separadamente.</span><span class="sxs-lookup"><span data-stu-id="55fc7-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="55fc7-239">Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="55fc7-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="55fc7-240">Usar o PowerShell para criar políticas de Links Seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="55fc7-241">Criar uma política de Links Seguros no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="55fc7-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="55fc7-242">Crie a política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="55fc7-243">Crie a regra de links seguros que especifica a política de links seguros à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="55fc7-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="55fc7-244">Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="55fc7-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="55fc7-245">Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="55fc7-246">Você pode configurar as configurações a seguir em novas políticas de links seguros no PowerShell que não estão disponíveis no Centro de Conformidade de Segurança & até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="55fc7-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="55fc7-247">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="55fc7-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="55fc7-248">Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="55fc7-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="55fc7-249">Uma nova política de links seguros que você cria no PowerShell não fica visível no Centro de Conformidade & segurança até que você atribua a política a uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="55fc7-250">Etapa 1: Usar o PowerShell para criar uma política de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="55fc7-251">Para criar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="55fc7-252">Para obter detalhes sobre a sintaxe de entrada a ser usada para o parâmetro _DoNotRewriteUrls,_ consulte Sintaxe de entrada para a lista "Não reescrever as [URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="55fc7-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="55fc7-253">Para obter uma sintaxe adicional que você pode usar para o parâmetro _DoNotRewriteUrls_ ao modificar políticas de links seguros existentes usando o cmdlet **Set-SafeLinksPolicy,** consulte a seção [Usar o PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar políticas de links seguros posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="55fc7-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="55fc7-254">Este exemplo cria uma política de links seguros chamada Contoso All com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="55fc7-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="55fc7-255">Ativar a verificação e a reescrita de URL em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="55fc7-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="55fc7-256">Ativar a verificação de URL no Teams (somente visualização do TAP).</span><span class="sxs-lookup"><span data-stu-id="55fc7-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="55fc7-257">Ativar a verificação em tempo real de URLs clicadas, incluindo links clicados que apontam para arquivos.</span><span class="sxs-lookup"><span data-stu-id="55fc7-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="55fc7-258">Aguarde a conclusão da verificação de URL antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="55fc7-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="55fc7-259">Ativar a verificação de URL e a reescrita de mensagens internas.</span><span class="sxs-lookup"><span data-stu-id="55fc7-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="55fc7-260">Rastrear cliques do usuário relacionados à proteção de Links Seguros (não estamos usando o parâmetro _DoNotTrackUserClicks_ e o valor padrão é $false, o que significa que os cliques do usuário são rastreados).</span><span class="sxs-lookup"><span data-stu-id="55fc7-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="55fc7-261">Não permita que os usuários cliquem na URL original.</span><span class="sxs-lookup"><span data-stu-id="55fc7-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="55fc7-262">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="55fc7-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="55fc7-263">Etapa 2: Usar o PowerShell para criar uma regra de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="55fc7-264">Para criar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="55fc7-265">Este exemplo cria uma regra de links seguros chamada Contoso All com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="55fc7-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="55fc7-266">A regra está associada à política de links seguros chamada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="55fc7-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="55fc7-267">A regra se aplica a todos os destinatários no contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="55fc7-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="55fc7-268">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="55fc7-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="55fc7-269">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="55fc7-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="55fc7-270">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="55fc7-270">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="55fc7-271">Usar o PowerShell para exibir políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="55fc7-272">Para exibir políticas de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="55fc7-273">Este exemplo retorna uma lista resumida de todas as políticas de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="55fc7-274">Este exemplo retorna informações detalhadas para a política de links seguros chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="55fc7-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="55fc7-275">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="55fc7-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="55fc7-276">Usar o PowerShell para exibir regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="55fc7-277">Para exibir as regras de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="55fc7-278">Este exemplo retorna uma lista resumida de todas as regras de links seguros.</span><span class="sxs-lookup"><span data-stu-id="55fc7-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="55fc7-279">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="55fc7-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="55fc7-280">Este exemplo retorna informações detalhadas para a regra de links seguros chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="55fc7-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="55fc7-281">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="55fc7-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="55fc7-282">Usar o PowerShell para modificar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="55fc7-283">Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **Set-SafeLinksPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="55fc7-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="55fc7-284">Ao renomear uma política de Links Seguros no Centro de Conformidade & segurança, você está renomeando apenas a regra de links _seguros._</span><span class="sxs-lookup"><span data-stu-id="55fc7-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="55fc7-285">A única consideração adicional para modificar políticas de links seguros no PowerShell é a sintaxe disponível para o parâmetro _DoNotRewriteUrls_ (a lista "Não reescrever as [URLs a seguir"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="55fc7-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="55fc7-286">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="55fc7-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="55fc7-287">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="55fc7-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="55fc7-288">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de links seguros, conforme descrito na Etapa [1: Usar](#step-1-use-powershell-to-create-a-safe-links-policy) o PowerShell para criar uma seção de política de links seguros anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="55fc7-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="55fc7-289">Para modificar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="55fc7-290">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="55fc7-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="55fc7-291">Usar o PowerShell para modificar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="55fc7-292">A única configuração que não está disponível quando você modifica uma regra de links seguros no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="55fc7-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="55fc7-293">Para habilitar ou desabilitar as regras de links seguros existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="55fc7-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="55fc7-294">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-a-safe-links-rule) o PowerShell para criar uma seção de regra de links seguros anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="55fc7-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="55fc7-295">Para modificar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="55fc7-296">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="55fc7-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="55fc7-297">Usar o PowerShell para habilitar ou desabilitar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="55fc7-298">Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política de Links Seguros (a regra de links seguros e a política de links seguros atribuídos).</span><span class="sxs-lookup"><span data-stu-id="55fc7-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="55fc7-299">Para habilitar ou desabilitar uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="55fc7-300">Este exemplo desabilita a regra de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="55fc7-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="55fc7-301">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="55fc7-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="55fc7-302">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="55fc7-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="55fc7-303">Usar o PowerShell para definir a prioridade das regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="55fc7-304">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="55fc7-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="55fc7-305">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="55fc7-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="55fc7-306">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="55fc7-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="55fc7-307">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="55fc7-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="55fc7-308">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="55fc7-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="55fc7-309">Para definir a prioridade de uma regra de links seguros no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="55fc7-310">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="55fc7-310">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="55fc7-311">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="55fc7-311">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="55fc7-312">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="55fc7-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="55fc7-313">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="55fc7-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="55fc7-314">Usar o PowerShell para remover políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="55fc7-315">Quando você usa o PowerShell para remover uma política de links seguros, a regra de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="55fc7-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="55fc7-316">Para remover uma política de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="55fc7-317">Este exemplo remove a política de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="55fc7-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="55fc7-318">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="55fc7-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="55fc7-319">Usar o PowerShell para remover regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="55fc7-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="55fc7-320">Quando você usa o PowerShell para remover uma regra de links seguros, a política de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="55fc7-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="55fc7-321">Para remover uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="55fc7-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="55fc7-322">Este exemplo remove a regra de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="55fc7-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="55fc7-323">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="55fc7-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="55fc7-324">Para verificar se Os Links Seguros estão verificando mensagens, verifique os relatórios disponíveis do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="55fc7-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="55fc7-325">Para obter mais informações, consulte [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="55fc7-325">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="55fc7-326">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="55fc7-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="55fc7-327">Para verificar se você criou, modificou ou removeu políticas de Links Seguros com êxito, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="55fc7-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="55fc7-328">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.</span><span class="sxs-lookup"><span data-stu-id="55fc7-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="55fc7-329">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="55fc7-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="55fc7-330">Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly-out.</span><span class="sxs-lookup"><span data-stu-id="55fc7-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="55fc7-331">No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="55fc7-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```