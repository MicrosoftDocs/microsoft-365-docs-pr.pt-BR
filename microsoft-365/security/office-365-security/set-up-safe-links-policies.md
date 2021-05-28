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
ms.openlocfilehash: 61cb4746289a8acbdd9af7f668010604de511902
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694492"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5f52a-103">Configurar políticas Cofre links no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5f52a-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f52a-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="5f52a-104">**Applies to**</span></span>
- [<span data-ttu-id="5f52a-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5f52a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5f52a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f52a-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="5f52a-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="5f52a-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="5f52a-108">Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="5f52a-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="5f52a-109">Cofre Links é um recurso no [Microsoft Defender para](defender-for-office-365.md) Office 365 que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="5f52a-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="5f52a-110">Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="5f52a-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="5f52a-111">Não há política de links interna ou padrão Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="5f52a-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="5f52a-112">Para obter Cofre verificação de links de URLs, você precisa criar uma ou mais políticas Cofre Links conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5f52a-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="5f52a-113">Você configura as configurações globais para a proteção Cofre Links **fora** das políticas Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="5f52a-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="5f52a-114">Para obter instruções, consulte [Configure global settings for Cofre Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="5f52a-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="5f52a-115">Você pode configurar políticas de Links do Cofre no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio Exchange Online, mas com o Microsoft Defender para assinaturas de complemento do Office 365).</span><span class="sxs-lookup"><span data-stu-id="5f52a-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="5f52a-116">Os elementos básicos de uma política Cofre Links são:</span><span class="sxs-lookup"><span data-stu-id="5f52a-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="5f52a-117">A política de **links** seguros : ativar a proteção de links do Cofre, ativar a verificação de URL em tempo real, especificar se a verificação em tempo real deve ser concluída antes de entregar a mensagem, ativar a verificação de mensagens internas, especificar se deve rastrear os cliques do usuário em URLs e especificar se os usuários devem clicar na URL original.</span><span class="sxs-lookup"><span data-stu-id="5f52a-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="5f52a-118">**A regra de links seguros**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="5f52a-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f52a-119">Os administradores devem considerar as configurações diferentes para SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="5f52a-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="5f52a-120">Uma das opções disponíveis é incluir informações de identificação do usuário em SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="5f52a-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="5f52a-121">Esse recurso permite que as *equipes de Operações* de Segurança investiguem possíveis comprometimentos do usuário, tome medidas corretivas e limitem violações custosas.</span><span class="sxs-lookup"><span data-stu-id="5f52a-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="5f52a-122">A diferença entre esses dois elementos não é óbvia quando você gerencia as Cofre links no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="5f52a-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="5f52a-123">Ao criar uma política Cofre Links, você está realmente criando uma regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="5f52a-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="5f52a-124">Quando você modifica uma política Cofre Links, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="5f52a-125">Todas as outras configurações modificam a política de links seguros associados.</span><span class="sxs-lookup"><span data-stu-id="5f52a-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="5f52a-126">Quando você remove uma política Cofre Links, a regra de links seguros e a política de links seguros associados são removidas.</span><span class="sxs-lookup"><span data-stu-id="5f52a-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="5f52a-127">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="5f52a-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="5f52a-128">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autônomo para configurar Cofre políticas de Links posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5f52a-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5f52a-129">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="5f52a-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5f52a-130">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5f52a-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5f52a-131">Para ir diretamente para a página **Cofre Links,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="5f52a-131">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="5f52a-132">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f52a-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5f52a-133">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f52a-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5f52a-134">Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="5f52a-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5f52a-135">Para criar, modificar e excluir políticas Cofre Links &, você  precisa ser  membro dos grupos de função Gerenciamento  da Organização ou  Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de função Gerenciamento da Organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5f52a-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="5f52a-136">Para acesso somente leitura às políticas Cofre Links, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="5f52a-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5f52a-137">Para obter mais informações, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="5f52a-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="5f52a-138">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f52a-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5f52a-139">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5f52a-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="5f52a-140">.</span><span class="sxs-lookup"><span data-stu-id="5f52a-140">.</span></span> <span data-ttu-id="5f52a-141">- O **grupo de função gerenciamento** de organização somente exibição no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="5f52a-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="5f52a-142">Para nossas configurações recomendadas para políticas Cofre Links, [consulte Cofre configurações da](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.</span><span class="sxs-lookup"><span data-stu-id="5f52a-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="5f52a-143">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="5f52a-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="5f52a-144">[Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="5f52a-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="5f52a-145">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de links Cofre existentes.</span><span class="sxs-lookup"><span data-stu-id="5f52a-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="5f52a-146">Use o Centro de Conformidade & segurança para criar políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="5f52a-146">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="5f52a-147">A criação de uma política Cofre & Links personalizada no Centro de Conformidade e Segurança cria a regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="5f52a-147">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="5f52a-148">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="5f52a-149">Na página **Cofre Links,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="5f52a-150">O **assistente de política Cofre Novos Links** é aberto.</span><span class="sxs-lookup"><span data-stu-id="5f52a-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="5f52a-151">Na página **Nomear sua política,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5f52a-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="5f52a-152">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="5f52a-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="5f52a-153">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="5f52a-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="5f52a-154">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5f52a-155">Na página **Configurações** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5f52a-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5f52a-156">**Selecione a ação para URLs** mal-intencionadas desconhecidas em mensagens : **Selecione** Ativar para habilitar Cofre de links para links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="5f52a-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="5f52a-157">**Selecione a ação para URLs desconhecidas** ou potencialmente  mal-intencionadas em Microsoft Teams : Selecione Ativado para habilitar Cofre Proteção de links para links Teams.</span><span class="sxs-lookup"><span data-stu-id="5f52a-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="5f52a-158">**Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Selecione essa configuração para habilitar a verificação em tempo real de links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="5f52a-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="5f52a-159">**Aguarde a conclusão da** verificação de URL antes de entregar a mensagem : Selecione essa configuração para aguardar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="5f52a-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="5f52a-160">**Aplicar Cofre Links** para mensagens de email enviadas dentro da organização : Selecione essa configuração para aplicar a política Cofre Links a mensagens entre destinatários internos e destinatários internos.</span><span class="sxs-lookup"><span data-stu-id="5f52a-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="5f52a-161">**Não acompanhar cliques do usuário**: Deixe essa configuração não eleita para habilitar os cliques do usuário de controle em URLs em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="5f52a-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="5f52a-162">**Não permita que os usuários cliquem** na URL original : Selecione essa configuração para impedir que os usuários cliquem na URL original em páginas [de aviso.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="5f52a-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="5f52a-163">**Não reescreva as SEGUINTES URLs**: Permite acessar as URLs especificadas que, de outra forma, seriam bloqueadas por Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="5f52a-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="5f52a-164">Na caixa, digite a URL ou o valor que você deseja e clique em</span><span class="sxs-lookup"><span data-stu-id="5f52a-164">In the box, type the URL or value that you want, and then click</span></span> ![Adicionar ícone de botão](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="5f52a-166">.</span><span class="sxs-lookup"><span data-stu-id="5f52a-166">.</span></span>

     <span data-ttu-id="5f52a-167">Para remover uma entrada existente, selecione-a e clique em</span><span class="sxs-lookup"><span data-stu-id="5f52a-167">To remove an existing entry, select it and then click</span></span> ![Excluir ícone de botão](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="5f52a-169">.</span><span class="sxs-lookup"><span data-stu-id="5f52a-169">.</span></span>

     <span data-ttu-id="5f52a-170">Para a sintaxe de entrada, consulte [Sintaxe de entrada para a lista "Não reescrever as URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="5f52a-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="5f52a-171">Para obter informações detalhadas sobre essas configurações, consulte [Cofre Configurações](safe-links.md#safe-links-settings-for-email-messages) de Links para mensagens de email e Cofre [Configurações](safe-links.md#safe-links-settings-for-microsoft-teams)de links para Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="5f52a-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="5f52a-172">Para obter mais valores recomendados para configurações de política padrão e estritas, [consulte Cofre Configurações de](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.</span><span class="sxs-lookup"><span data-stu-id="5f52a-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="5f52a-173">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5f52a-174">Na página **Aplicada à** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="5f52a-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="5f52a-175">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="5f52a-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="5f52a-176">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="5f52a-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="5f52a-177">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="5f52a-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="5f52a-178">Clique **em Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-178">Click **Add a condition**.</span></span> <span data-ttu-id="5f52a-179">No menu suspenso exibido, selecione uma condição em **Aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="5f52a-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="5f52a-180">**O destinatário é**: Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f52a-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="5f52a-181">**O destinatário é membro de**: Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f52a-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="5f52a-182">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="5f52a-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="5f52a-183">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="5f52a-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="5f52a-184">Clique na caixa e role a lista de valores a ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="5f52a-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="5f52a-185">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="5f52a-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="5f52a-186">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="5f52a-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="5f52a-187">Para remover entradas individuais, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="5f52a-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="5f52a-188">Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="5f52a-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="5f52a-189">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **Applied if**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="5f52a-190">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="5f52a-191">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="5f52a-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="5f52a-192">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="5f52a-193">Na página **Revisar suas configurações** que aparece, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="5f52a-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="5f52a-194">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="5f52a-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="5f52a-195">Quando terminar, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="5f52a-196">Use o Centro de Conformidade & segurança para exibir Cofre links</span><span class="sxs-lookup"><span data-stu-id="5f52a-196">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="5f52a-197">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="5f52a-198">Na página **Cofre Links,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="5f52a-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="5f52a-199">Os detalhes da política aparecem em um fly-out</span><span class="sxs-lookup"><span data-stu-id="5f52a-199">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="5f52a-200">Use o Centro de Conformidade & segurança para modificar as políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="5f52a-200">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="5f52a-201">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="5f52a-202">Na página **Cofre Links,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="5f52a-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="5f52a-203">Nos detalhes da política exibidos, clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="5f52a-204">As configurações disponíveis no sobrevoo que aparece são idênticas às descritas na seção Usar o Centro de Conformidade & Segurança para criar políticas Cofre [Links.](#use-the-security--compliance-center-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="5f52a-204">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="5f52a-205">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f52a-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="5f52a-206">Habilitar ou desabilitar Cofre de links</span><span class="sxs-lookup"><span data-stu-id="5f52a-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="5f52a-207">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="5f52a-208">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="5f52a-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="5f52a-209">Mova o botão de alternância para a esquerda para desabilitar a política:</span><span class="sxs-lookup"><span data-stu-id="5f52a-209">Move the toggle to the left to disable the policy:</span></span> ![Desativar a política](../../media/scc-toggle-off.png)<span data-ttu-id="5f52a-211">.</span><span class="sxs-lookup"><span data-stu-id="5f52a-211">.</span></span>

   - <span data-ttu-id="5f52a-212">Mova o botão de alternância para a direita para habilitar a política:</span><span class="sxs-lookup"><span data-stu-id="5f52a-212">Move the toggle to the right to enable the policy:</span></span> ![Ativar a política](../../media/scc-toggle-on.png)<span data-ttu-id="5f52a-214">.</span><span class="sxs-lookup"><span data-stu-id="5f52a-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="5f52a-215">Definir a prioridade das políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="5f52a-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="5f52a-216">Por padrão, Cofre de links recebe uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="5f52a-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="5f52a-217">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="5f52a-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="5f52a-218">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="5f52a-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="5f52a-219">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="5f52a-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="5f52a-220">Cofre As políticas de links são exibidas na ordem em que são processadas (a primeira política tem o **valor Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="5f52a-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="5f52a-221">No Centro de Conformidade & segurança, você só pode alterar a prioridade da política Cofre Links após a criação.</span><span class="sxs-lookup"><span data-stu-id="5f52a-221">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="5f52a-222">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="5f52a-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="5f52a-223">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="5f52a-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="5f52a-224">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="5f52a-225">Na página **Cofre Links,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="5f52a-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="5f52a-226">Nos detalhes da política exibidos, clique no botão de prioridade disponível:</span><span class="sxs-lookup"><span data-stu-id="5f52a-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="5f52a-227">A Cofre links com o valor **Prioridade** **0** tem apenas o **botão Diminuir** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="5f52a-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="5f52a-228">A Cofre links com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="5f52a-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="5f52a-229">Se você tiver três ou mais políticas Cofre links, as políticas entre os  valores de prioridade mais alta e mais baixa terão os botões **Aumentar** prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5f52a-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="5f52a-230">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor Priority.**</span><span class="sxs-lookup"><span data-stu-id="5f52a-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="5f52a-231">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5f52a-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="5f52a-232">Use o Centro de Conformidade & segurança para remover Cofre links</span><span class="sxs-lookup"><span data-stu-id="5f52a-232">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="5f52a-233">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="5f52a-234">Na página **Cofre Links,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="5f52a-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="5f52a-235">Nos detalhes da política exibidos, clique em **Excluir política** e clique em **Sim** na caixa de diálogo de aviso exibida.</span><span class="sxs-lookup"><span data-stu-id="5f52a-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="5f52a-236">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar Cofre links</span><span class="sxs-lookup"><span data-stu-id="5f52a-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="5f52a-237">Conforme descrito anteriormente, uma política Cofre Links consiste em uma política de links seguros e uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="5f52a-238">No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente.</span><span class="sxs-lookup"><span data-stu-id="5f52a-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="5f52a-239">Você gerencia políticas de links seguros usando os cmdlets **\* -SafeLinksPolicy** e gerencia as regras de links seguros usando os cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="5f52a-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="5f52a-240">No PowerShell, primeiro você cria a política de links seguros e, em seguida, cria a regra de links seguros que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="5f52a-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="5f52a-241">No PowerShell, você modifica as configurações na política de links seguros e a regra de links seguros separadamente.</span><span class="sxs-lookup"><span data-stu-id="5f52a-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="5f52a-242">Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="5f52a-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="5f52a-243">Usar o PowerShell para criar políticas Cofre Links</span><span class="sxs-lookup"><span data-stu-id="5f52a-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="5f52a-244">Criar uma Cofre de links no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="5f52a-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="5f52a-245">Crie a política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="5f52a-246">Crie a regra de links seguros que especifica a política de links seguros à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="5f52a-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="5f52a-247">Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="5f52a-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="5f52a-248">Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="5f52a-249">Você pode configurar as configurações a seguir em novas políticas de links seguros no PowerShell que não estão disponíveis no Centro de Conformidade de Segurança & até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="5f52a-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="5f52a-250">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="5f52a-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="5f52a-251">Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="5f52a-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="5f52a-252">Uma nova política de links seguros que você cria no PowerShell não fica visível no Centro de Conformidade & segurança até que você atribua a política a uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-252">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="5f52a-253">Etapa 1: Usar o PowerShell para criar uma política de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="5f52a-254">Para criar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="5f52a-255">Para obter detalhes sobre a sintaxe de entrada a ser usada para o parâmetro _DoNotRewriteUrls,_ consulte Sintaxe de entrada para a lista "Não reescrever as [URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="5f52a-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="5f52a-256">Para obter uma sintaxe adicional que você pode usar para o parâmetro _DoNotRewriteUrls_ ao modificar políticas de links seguros existentes usando o cmdlet **Set-SafeLinksPolicy,** consulte a seção [Usar o PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar políticas de links seguros posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5f52a-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="5f52a-257">Este exemplo cria uma política de links seguros chamada Contoso All com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5f52a-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="5f52a-258">Ativar a verificação e a reescrita de URL em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="5f52a-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="5f52a-259">Ativar a verificação de URL no Teams (somente visualização do TAP).</span><span class="sxs-lookup"><span data-stu-id="5f52a-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="5f52a-260">Ativar a verificação em tempo real de URLs clicadas, incluindo links clicados que apontam para arquivos.</span><span class="sxs-lookup"><span data-stu-id="5f52a-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="5f52a-261">Aguarde a conclusão da verificação de URL antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="5f52a-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="5f52a-262">Ativar a verificação de URL e a reescrita de mensagens internas.</span><span class="sxs-lookup"><span data-stu-id="5f52a-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="5f52a-263">Rastrear cliques do usuário relacionados à proteção de links do Cofre (não estamos usando o parâmetro _DoNotTrackUserClicks_ e o valor padrão é $false, o que significa que os cliques do usuário são rastreados).</span><span class="sxs-lookup"><span data-stu-id="5f52a-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="5f52a-264">Não permita que os usuários cliquem na URL original.</span><span class="sxs-lookup"><span data-stu-id="5f52a-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="5f52a-265">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="5f52a-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="5f52a-266">Etapa 2: Usar o PowerShell para criar uma regra de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="5f52a-267">Para criar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="5f52a-268">Este exemplo cria uma regra de links seguros chamada Contoso All com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="5f52a-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="5f52a-269">A regra está associada à política de links seguros chamada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="5f52a-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="5f52a-270">A regra se aplica a todos os destinatários no contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="5f52a-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="5f52a-271">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="5f52a-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="5f52a-272">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="5f52a-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="5f52a-273">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5f52a-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="5f52a-274">Usar o PowerShell para exibir políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="5f52a-275">Para exibir políticas de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="5f52a-276">Este exemplo retorna uma lista resumida de todas as políticas de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="5f52a-277">Este exemplo retorna informações detalhadas para a política de links seguros chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="5f52a-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="5f52a-278">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="5f52a-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="5f52a-279">Usar o PowerShell para exibir regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="5f52a-280">Para exibir as regras de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="5f52a-281">Este exemplo retorna uma lista resumida de todas as regras de links seguros.</span><span class="sxs-lookup"><span data-stu-id="5f52a-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="5f52a-282">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="5f52a-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="5f52a-283">Este exemplo retorna informações detalhadas para a regra de links seguros chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="5f52a-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="5f52a-284">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5f52a-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="5f52a-285">Usar o PowerShell para modificar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="5f52a-286">Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **Set-SafeLinksPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="5f52a-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="5f52a-287">Ao renomear uma política Cofre & Links no Centro de Conformidade e Segurança, você só está renomeando a regra de links _seguros._</span><span class="sxs-lookup"><span data-stu-id="5f52a-287">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="5f52a-288">A única consideração adicional para modificar políticas de links seguros no PowerShell é a sintaxe disponível para o parâmetro _DoNotRewriteUrls_ (a lista "Não reescrever as [URLs a seguir"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="5f52a-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="5f52a-289">Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="5f52a-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="5f52a-290">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="5f52a-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="5f52a-291">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de links seguros, conforme descrito na Etapa [1: Usar](#step-1-use-powershell-to-create-a-safe-links-policy) o PowerShell para criar uma seção de política de links seguros anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5f52a-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="5f52a-292">Para modificar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="5f52a-293">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="5f52a-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="5f52a-294">Usar o PowerShell para modificar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="5f52a-295">A única configuração que não está disponível quando você modifica uma regra de links seguros no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="5f52a-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="5f52a-296">Para habilitar ou desabilitar as regras de links seguros existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="5f52a-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="5f52a-297">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-a-safe-links-rule) o PowerShell para criar uma seção de regra de links seguros anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5f52a-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="5f52a-298">Para modificar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="5f52a-299">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5f52a-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="5f52a-300">Usar o PowerShell para habilitar ou desabilitar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="5f52a-301">Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política Cofre Links (a regra de links seguros e a política de links seguros atribuídos).</span><span class="sxs-lookup"><span data-stu-id="5f52a-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="5f52a-302">Para habilitar ou desabilitar uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="5f52a-303">Este exemplo desabilita a regra de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="5f52a-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="5f52a-304">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="5f52a-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="5f52a-305">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5f52a-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="5f52a-306">Usar o PowerShell para definir a prioridade das regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="5f52a-307">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="5f52a-307">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="5f52a-308">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="5f52a-308">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="5f52a-309">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="5f52a-309">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="5f52a-310">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="5f52a-310">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="5f52a-311">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="5f52a-311">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="5f52a-312">Para definir a prioridade de uma regra de links seguros no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="5f52a-313">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="5f52a-313">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="5f52a-314">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="5f52a-314">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="5f52a-315">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="5f52a-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="5f52a-316">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5f52a-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="5f52a-317">Usar o PowerShell para remover políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="5f52a-318">Quando você usa o PowerShell para remover uma política de links seguros, a regra de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="5f52a-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="5f52a-319">Para remover uma política de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="5f52a-320">Este exemplo remove a política de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="5f52a-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="5f52a-321">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="5f52a-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="5f52a-322">Usar o PowerShell para remover regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="5f52a-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="5f52a-323">Quando você usa o PowerShell para remover uma regra de links seguros, a política de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="5f52a-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="5f52a-324">Para remover uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5f52a-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="5f52a-325">Este exemplo remove a regra de links seguros chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="5f52a-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="5f52a-326">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5f52a-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="5f52a-327">Para verificar se Cofre links está verificando mensagens, verifique os relatórios disponíveis do Microsoft Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f52a-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="5f52a-328">Para obter mais informações, [consulte View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="5f52a-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5f52a-329">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="5f52a-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="5f52a-330">Para verificar se você criou, modificou ou removeu com êxito Cofre políticas de Links, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5f52a-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="5f52a-331">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP** Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="5f52a-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="5f52a-332">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="5f52a-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="5f52a-333">Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly-out.</span><span class="sxs-lookup"><span data-stu-id="5f52a-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="5f52a-334">Em Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e verifique \<Name\> as configurações:</span><span class="sxs-lookup"><span data-stu-id="5f52a-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```