---
title: Configurar políticas Cofre links no Microsoft Defender para Office 365
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
description: Os administradores podem aprender a exibir, criar, modificar e excluir Cofre políticas de links e configurações globais Cofre Links no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1e0257fd124a53b2191ad8025ce42dc13a2e23e
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096763"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa64b-103">Configurar políticas Cofre links no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fa64b-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fa64b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="fa64b-104">**Applies to**</span></span>
- [<span data-ttu-id="fa64b-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fa64b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fa64b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa64b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="fa64b-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fa64b-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="fa64b-108">Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="fa64b-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fa64b-109">Cofre Links no [Microsoft Defender para Office 365](defender-for-office-365.md) fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique de URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="fa64b-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="fa64b-110">Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fa64b-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="fa64b-111">Não há política de links interna ou padrão Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="fa64b-112">Para obter Cofre verificação de links de URLs, você precisa criar uma ou mais políticas Cofre Links conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="fa64b-113">Você configura as configurações globais para a proteção Cofre Links **fora** das políticas Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="fa64b-114">Para obter instruções, consulte [Configure global settings for Cofre Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fa64b-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="fa64b-115">Os administradores devem considerar as diferentes configurações para Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="fa64b-116">Uma das opções disponíveis é incluir informações de identificação do usuário em Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="fa64b-117">Esse recurso permite que as *equipes de Operações* de Segurança investiguem possíveis comprometimentos do usuário, tome medidas corretivas e limitem violações custosas.</span><span class="sxs-lookup"><span data-stu-id="fa64b-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="fa64b-118">Você pode configurar políticas de Links do Cofre no portal do Microsoft 365 Defender ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; PowerShell autônomo do EOP para organizações sem caixas de correio Exchange Online, mas com o Microsoft Defender para assinaturas de complementos do Office 365).</span><span class="sxs-lookup"><span data-stu-id="fa64b-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="fa64b-119">Os elementos básicos de uma política Cofre Links são:</span><span class="sxs-lookup"><span data-stu-id="fa64b-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="fa64b-120">A política de **links** seguros : ativar a proteção de links do Cofre, ativar a verificação de URL em tempo real, especificar se a verificação em tempo real deve ser concluída antes de entregar a mensagem, ativar a verificação de mensagens internas, especificar se deve rastrear os cliques do usuário em URLs e especificar se os usuários devem clicar na URL original.</span><span class="sxs-lookup"><span data-stu-id="fa64b-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="fa64b-121">**A regra de links seguros**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="fa64b-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="fa64b-122">A diferença entre esses dois elementos não é óbvia quando você gerencia Cofre políticas de Links no portal Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="fa64b-122">The difference between these two elements isn't obvious when you manage Safe Links policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="fa64b-123">Ao criar uma política Cofre Links, você está realmente criando uma regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="fa64b-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fa64b-124">Quando você modifica uma política Cofre Links, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="fa64b-125">Todas as outras configurações modificam a política de links seguros associados.</span><span class="sxs-lookup"><span data-stu-id="fa64b-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="fa64b-126">Quando você remove uma política Cofre Links, a regra de links seguros e a política de links seguros associados são removidas.</span><span class="sxs-lookup"><span data-stu-id="fa64b-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="fa64b-127">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="fa64b-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fa64b-128">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autônomo para configurar Cofre políticas de Links posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fa64b-129">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="fa64b-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fa64b-130">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="fa64b-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="fa64b-131">Para ir diretamente para a página **Cofre Links,** use <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="fa64b-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="fa64b-132">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fa64b-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fa64b-133">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fa64b-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fa64b-134">Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="fa64b-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fa64b-135">Para criar, modificar e excluir Cofre políticas de Links, você  precisa ser  membro dos grupos de função Gerenciamento da Organização  ou Administrador de Segurança no **portal** Microsoft 365 Defender e membro do grupo de função Gerenciamento da Organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fa64b-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="fa64b-136">Para acesso somente leitura às políticas Cofre Links, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="fa64b-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fa64b-137">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="fa64b-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="fa64b-138">Adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa64b-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fa64b-139">Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fa64b-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="fa64b-140">.</span><span class="sxs-lookup"><span data-stu-id="fa64b-140">.</span></span> <span data-ttu-id="fa64b-141">- O **grupo de função gerenciamento** de organização somente exibição no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="fa64b-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="fa64b-142">Para nossas configurações recomendadas para políticas Cofre Links, [consulte Cofre configurações da](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="fa64b-143">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="fa64b-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="fa64b-144">[Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="fa64b-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="fa64b-145">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de links Cofre existentes.</span><span class="sxs-lookup"><span data-stu-id="fa64b-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="fa64b-146">Usar o portal Microsoft 365 Defender para criar políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="fa64b-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="fa64b-147">A criação de uma política Cofre links personalizada no portal Microsoft 365 Defender cria a regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="fa64b-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fa64b-148">No portal Microsoft 365 Defender, vá até Políticas & **políticas políticas** de ameaças seção Cofre \>  \>  \> **Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fa64b-149">Na página **Cofre Links,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="fa64b-150">O **assistente de política Cofre Novos Links** é aberto.</span><span class="sxs-lookup"><span data-stu-id="fa64b-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="fa64b-151">Na página **Nomear sua política,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fa64b-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="fa64b-152">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="fa64b-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="fa64b-153">**Descrição**: insira uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="fa64b-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fa64b-154">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fa64b-155">Na página **Usuários e domínios** que aparece, identifique os destinatários internos aos quais a política se aplica (condições de destinatário):</span><span class="sxs-lookup"><span data-stu-id="fa64b-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="fa64b-156">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="fa64b-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fa64b-157">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="fa64b-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="fa64b-158">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="fa64b-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="fa64b-159">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="fa64b-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="fa64b-160">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="fa64b-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="fa64b-161">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="fa64b-161">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="fa64b-163">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="fa64b-163">next to the value.</span></span>

   <span data-ttu-id="fa64b-164">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="fa64b-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="fa64b-165">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fa64b-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="fa64b-166">Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="fa64b-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="fa64b-167">Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="fa64b-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="fa64b-168">**Excluir esses usuários, grupos** e domínios : Para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatário), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="fa64b-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="fa64b-169">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="fa64b-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fa64b-170">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fa64b-171">Na página **Configurações de Proteção** exibida, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fa64b-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="fa64b-172">**Selecione a ação para URLs** mal-intencionadas desconhecidas em mensagens : **Selecione** Ativar para habilitar Cofre de links para links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="fa64b-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="fa64b-173">Se você ativar essa configuração, as seguintes configurações estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fa64b-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="fa64b-174">**Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Selecione essa opção para habilitar a verificação em tempo real de links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="fa64b-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="fa64b-175">Se você ativar essa configuração na configuração a seguir está disponível:</span><span class="sxs-lookup"><span data-stu-id="fa64b-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="fa64b-176">**Aguarde a conclusão da** verificação de URL antes de entregar a mensagem : Selecione essa opção para aguardar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="fa64b-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="fa64b-177">**Aplicar Cofre Links** para mensagens de email enviadas dentro da organização : Selecione essa opção para aplicar a política Cofre Links para mensagens entre destinatários internos e destinatários internos.</span><span class="sxs-lookup"><span data-stu-id="fa64b-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="fa64b-178">**Selecione a ação para URLs desconhecidas** ou potencialmente  mal-intencionadas em Microsoft Teams : Selecione Ativado para habilitar Cofre Proteção de links para links Teams.</span><span class="sxs-lookup"><span data-stu-id="fa64b-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="fa64b-179">**Não acompanhar cliques do usuário**: Deixe essa configuração não eleita para habilitar os cliques do usuário de controle em URLs em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="fa64b-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="fa64b-180">**Não permita que os usuários cliquem** na URL original : Selecione essa opção para impedir que os usuários cliquem na URL original em páginas [de aviso.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="fa64b-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="fa64b-181">**Não reescreva as SEGUINTES URLs**: Permite acessar as URLs especificadas que, de outra forma, seriam bloqueadas por Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="fa64b-182">Na caixa, digite a URL ou o valor que você deseja e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="fa64b-183">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="fa64b-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="fa64b-184">Para remover uma entrada existente, clique em</span><span class="sxs-lookup"><span data-stu-id="fa64b-184">To remove an existing entry, click</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="fa64b-186">ao lado da entrada.</span><span class="sxs-lookup"><span data-stu-id="fa64b-186">next to the entry.</span></span>

     <span data-ttu-id="fa64b-187">Para a sintaxe de entrada, consulte [Sintaxe de entrada para a lista "Não reescrever as URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="fa64b-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="fa64b-188">Para obter informações detalhadas sobre essas configurações, consulte [Cofre Configurações](safe-links.md#safe-links-settings-for-email-messages) de Links para mensagens de email e Cofre [Configurações](safe-links.md#safe-links-settings-for-microsoft-teams)de links para Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="fa64b-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="fa64b-189">Para obter mais valores recomendados para configurações de política padrão e estritas, [consulte Cofre Configurações de](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.</span><span class="sxs-lookup"><span data-stu-id="fa64b-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="fa64b-190">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="fa64b-191">Na página **Notificação** exibida, selecione um dos seguintes valores para **Como você gostaria de notificar seus usuários?**:</span><span class="sxs-lookup"><span data-stu-id="fa64b-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="fa64b-192">**Usar o texto de notificação padrão**</span><span class="sxs-lookup"><span data-stu-id="fa64b-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="fa64b-193">**Use texto de notificação personalizado**: Se você selecionar esse valor (o comprimento não pode exceder 200 caracteres), as seguintes configurações aparecerão:</span><span class="sxs-lookup"><span data-stu-id="fa64b-193">**Use custom notification text**: If you select this value (the length cannot exceed 200 characters), the following settings appear:</span></span>
     - <span data-ttu-id="fa64b-194">**Usar Microsoft Translator para localização automática**</span><span class="sxs-lookup"><span data-stu-id="fa64b-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="fa64b-195">**Texto de notificação personalizado**: Insira o texto de notificação personalizado nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="fa64b-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="fa64b-196">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="fa64b-197">Na página **Revisão** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="fa64b-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="fa64b-198">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="fa64b-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fa64b-199">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="fa64b-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="fa64b-200">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="fa64b-201">Na mensagem de confirmação exibida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="fa64b-202">Use o portal Microsoft 365 Defender para exibir Cofre Links</span><span class="sxs-lookup"><span data-stu-id="fa64b-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="fa64b-203">No portal Microsoft 365 Defender, vá até Políticas & **políticas políticas** de ameaças seção Cofre \>  \>  \> **Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fa64b-204">Na página **Cofre Links,** as seguintes propriedades são exibidas na lista de políticas Cofre Links:</span><span class="sxs-lookup"><span data-stu-id="fa64b-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="fa64b-205">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fa64b-205">**Name**</span></span>
   - <span data-ttu-id="fa64b-206">**Status**</span><span class="sxs-lookup"><span data-stu-id="fa64b-206">**Status**</span></span>
   - <span data-ttu-id="fa64b-207">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="fa64b-207">**Priority**</span></span>

3. <span data-ttu-id="fa64b-208">Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="fa64b-209">Usar o portal Microsoft 365 Defender para modificar as políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="fa64b-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="fa64b-210">No portal Microsoft 365 Defender, vá até Políticas & **políticas políticas** de ameaças seção Cofre \>  \>  \> **Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fa64b-211">Na página **Cofre Links,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="fa64b-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fa64b-212">No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="fa64b-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fa64b-213">Para obter mais informações sobre as configurações, consulte a seção [anterior Usar](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) o portal Microsoft 365 Defender para criar políticas Cofre Links neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="fa64b-214">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa64b-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="fa64b-215">Habilitar ou desabilitar Cofre de links</span><span class="sxs-lookup"><span data-stu-id="fa64b-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="fa64b-216">No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fa64b-217">Na página **Cofre Links,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="fa64b-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fa64b-218">Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fa64b-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="fa64b-219">**Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .</span><span class="sxs-lookup"><span data-stu-id="fa64b-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="fa64b-220">**Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="fa64b-221">Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="fa64b-222">Clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="fa64b-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="fa64b-223">De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="fa64b-224">Definir a prioridade das políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="fa64b-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="fa64b-225">Por padrão, Cofre links recebe uma prioridade baseada na ordem em que foram criados (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="fa64b-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="fa64b-226">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="fa64b-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fa64b-227">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="fa64b-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fa64b-228">Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="fa64b-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="fa64b-229">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="fa64b-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="fa64b-230">**Observação**:</span><span class="sxs-lookup"><span data-stu-id="fa64b-230">**Note**:</span></span>

- <span data-ttu-id="fa64b-231">No portal Microsoft 365 Defender, você só pode alterar a prioridade da política Cofre Links após a criação.</span><span class="sxs-lookup"><span data-stu-id="fa64b-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="fa64b-232">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="fa64b-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="fa64b-233">Cofre As políticas de links são processadas na ordem em que são exibidas (a primeira política tem **o valor Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="fa64b-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="fa64b-234">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="fa64b-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="fa64b-235">No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fa64b-236">Na página **Cofre Links,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="fa64b-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fa64b-237">Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="fa64b-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="fa64b-238">A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="fa64b-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="fa64b-239">A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="fa64b-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="fa64b-240">Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fa64b-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="fa64b-241">Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="fa64b-242">Quando terminar, clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="fa64b-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="fa64b-243">Usar o portal Microsoft 365 Defender para remover as políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="fa64b-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="fa64b-244">No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fa64b-245">Na página **Cofre Links,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="fa64b-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="fa64b-246">Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="fa64b-247">Na caixa de diálogo de confirmação exibida, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="fa64b-248">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar Cofre links</span><span class="sxs-lookup"><span data-stu-id="fa64b-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="fa64b-249">Conforme descrito anteriormente, uma política Cofre Links consiste em uma política de links seguros e uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="fa64b-250">No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente.</span><span class="sxs-lookup"><span data-stu-id="fa64b-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="fa64b-251">Você gerencia políticas de links seguros usando os cmdlets **\* -SafeLinksPolicy** e gerencia as regras de links seguros usando os cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="fa64b-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="fa64b-252">No PowerShell, primeiro você cria a política de links seguros e, em seguida, cria a regra de links seguros que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="fa64b-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fa64b-253">No PowerShell, você modifica as configurações na política de links seguros e a regra de links seguros separadamente.</span><span class="sxs-lookup"><span data-stu-id="fa64b-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="fa64b-254">Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="fa64b-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="fa64b-255">Usar o PowerShell para criar políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="fa64b-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="fa64b-256">Criar uma Cofre de links no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="fa64b-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fa64b-257">Crie a política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="fa64b-258">Crie a regra de links seguros que especifica a política de links seguros à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="fa64b-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fa64b-259">Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="fa64b-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="fa64b-260">Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="fa64b-261">Você pode configurar as seguintes configurações em novas políticas de links seguros no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="fa64b-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="fa64b-262">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="fa64b-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="fa64b-263">Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="fa64b-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="fa64b-264">Uma nova política de links seguros que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até atribuir a política a uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="fa64b-265">Etapa 1: Usar o PowerShell para criar uma política de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="fa64b-266">Para criar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="fa64b-267">Para obter detalhes sobre a sintaxe de entrada a ser usada para o parâmetro _DoNotRewriteUrls,_ consulte Sintaxe de entrada para a lista "Não reescrever as [URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="fa64b-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="fa64b-268">Para obter uma sintaxe adicional que você pode usar para o parâmetro _DoNotRewriteUrls_ ao modificar políticas de links seguros existentes usando o cmdlet **Set-SafeLinksPolicy,** consulte a seção [Usar o PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar políticas de links seguros posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="fa64b-269">Este exemplo cria uma política de links seguros chamada Contoso All com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fa64b-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="fa64b-270">Ativar a verificação e a reescrita de URL em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="fa64b-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="fa64b-271">Ativar a verificação de URL no Teams (somente visualização do TAP).</span><span class="sxs-lookup"><span data-stu-id="fa64b-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="fa64b-272">Ativar a verificação em tempo real de URLs clicadas, incluindo links clicados que apontam para arquivos.</span><span class="sxs-lookup"><span data-stu-id="fa64b-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="fa64b-273">Aguarde a conclusão da verificação de URL antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="fa64b-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="fa64b-274">Ativar a verificação de URL e a reescrita de mensagens internas.</span><span class="sxs-lookup"><span data-stu-id="fa64b-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="fa64b-275">Rastrear cliques do usuário relacionados à proteção de links do Cofre (não estamos usando o parâmetro _DoNotTrackUserClicks_ e o valor padrão é $false, o que significa que os cliques do usuário são rastreados).</span><span class="sxs-lookup"><span data-stu-id="fa64b-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="fa64b-276">Não permita que os usuários cliquem na URL original.</span><span class="sxs-lookup"><span data-stu-id="fa64b-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="fa64b-277">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="fa64b-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="fa64b-278">Etapa 2: Usar o PowerShell para criar uma regra de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="fa64b-279">Para criar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="fa64b-280">Este exemplo cria uma regra de links seguros chamada Contoso All com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="fa64b-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="fa64b-281">A regra está associada à política de links seguros chamada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="fa64b-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="fa64b-282">A regra se aplica a todos os destinatários no contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="fa64b-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="fa64b-283">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="fa64b-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="fa64b-284">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="fa64b-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="fa64b-285">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fa64b-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="fa64b-286">Usar o PowerShell para exibir políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="fa64b-287">Para exibir políticas de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fa64b-288">Este exemplo retorna uma lista resumida de todas as políticas de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="fa64b-289">Este exemplo retorna informações detalhadas para a política de links seguros chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="fa64b-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="fa64b-290">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="fa64b-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="fa64b-291">Usar o PowerShell para exibir regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="fa64b-292">Para exibir as regras de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fa64b-293">Este exemplo retorna uma lista resumida de todas as regras de links seguros.</span><span class="sxs-lookup"><span data-stu-id="fa64b-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="fa64b-294">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fa64b-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="fa64b-295">Este exemplo retorna informações detalhadas para a regra de links seguros chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="fa64b-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="fa64b-296">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fa64b-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="fa64b-297">Usar o PowerShell para modificar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="fa64b-298">Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **Set-SafeLinksPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="fa64b-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fa64b-299">Quando você renomea uma política Cofre Links no portal Microsoft 365 Defender, você está renomeando apenas a regra de links _seguros._</span><span class="sxs-lookup"><span data-stu-id="fa64b-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="fa64b-300">A única consideração adicional para modificar políticas de links seguros no PowerShell é a sintaxe disponível para o parâmetro _DoNotRewriteUrls_ (a lista "Não reescrever as [URLs a seguir"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="fa64b-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="fa64b-301">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="fa64b-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="fa64b-302">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="fa64b-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="fa64b-303">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de links seguros, conforme descrito na Etapa [1: Usar](#step-1-use-powershell-to-create-a-safe-links-policy) o PowerShell para criar uma seção de política de links seguros anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="fa64b-304">Para modificar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fa64b-305">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="fa64b-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="fa64b-306">Usar o PowerShell para modificar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="fa64b-307">A única configuração que não está disponível quando você modifica uma regra de links seguros no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="fa64b-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fa64b-308">Para habilitar ou desabilitar as regras de links seguros existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="fa64b-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="fa64b-309">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-a-safe-links-rule) o PowerShell para criar uma seção de regra de links seguros anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fa64b-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="fa64b-310">Para modificar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fa64b-311">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fa64b-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="fa64b-312">Usar o PowerShell para habilitar ou desabilitar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="fa64b-313">Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política Cofre Links (a regra de links seguros e a política de links seguros atribuídos).</span><span class="sxs-lookup"><span data-stu-id="fa64b-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="fa64b-314">Para habilitar ou desabilitar uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="fa64b-315">Este exemplo desabilita a regra de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fa64b-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fa64b-316">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="fa64b-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fa64b-317">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fa64b-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="fa64b-318">Usar o PowerShell para definir a prioridade das regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="fa64b-319">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="fa64b-319">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fa64b-320">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="fa64b-320">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fa64b-321">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="fa64b-321">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fa64b-322">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="fa64b-322">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fa64b-323">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="fa64b-323">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fa64b-324">Para definir a prioridade de uma regra de links seguros no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fa64b-325">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="fa64b-325">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="fa64b-326">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="fa64b-326">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="fa64b-327">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="fa64b-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="fa64b-328">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fa64b-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="fa64b-329">Usar o PowerShell para remover políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="fa64b-330">Quando você usa o PowerShell para remover uma política de links seguros, a regra de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="fa64b-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="fa64b-331">Para remover uma política de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fa64b-332">Este exemplo remove a política de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fa64b-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fa64b-333">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="fa64b-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="fa64b-334">Usar o PowerShell para remover regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="fa64b-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="fa64b-335">Quando você usa o PowerShell para remover uma regra de links seguros, a política de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="fa64b-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="fa64b-336">Para remover uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fa64b-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="fa64b-337">Este exemplo remove a regra de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fa64b-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fa64b-338">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fa64b-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="fa64b-339">Para verificar se Cofre links está verificando mensagens, verifique os relatórios disponíveis do Microsoft Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa64b-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="fa64b-340">Para obter mais informações, [consulte View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="fa64b-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fa64b-341">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="fa64b-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="fa64b-342">Para verificar se você criou, modificou ou removeu com êxito Cofre políticas de Links, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="fa64b-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="fa64b-343">No portal Microsoft 365 Defender, acesse Políticas & **regras** \> **Políticas de** ameaça Cofre \> **Links**.</span><span class="sxs-lookup"><span data-stu-id="fa64b-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="fa64b-344">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="fa64b-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fa64b-345">Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly-out.</span><span class="sxs-lookup"><span data-stu-id="fa64b-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="fa64b-346">Em Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e verifique \<Name\> as configurações:</span><span class="sxs-lookup"><span data-stu-id="fa64b-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
