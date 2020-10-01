---
title: Configurar políticas de links seguros no Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de links seguros e configurações globais de links seguros na proteção avançada contra ameaças do Office 365 (ATP).
ms.openlocfilehash: 58088955a6909238c1fe5202688e0b8d1ab8e6c6
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327220"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a><span data-ttu-id="c7610-103">Configurar políticas de links seguros no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c7610-103">Set up Safe Links policies in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="c7610-104">Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c7610-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="c7610-105">Se você for um usuário doméstico que procura informações sobre o Safelinks no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="c7610-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c7610-106">Links seguros é um recurso da [proteção avançada contra ameaças do Office 365 (ATP)](office-365-atp.md) que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e a hora de clicar em verificação de URLs e links em mensagens de email e em outros locais.</span><span class="sxs-lookup"><span data-stu-id="c7610-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="c7610-107">Para obter mais informações, consulte [links seguros no Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c7610-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="c7610-108">Não há nenhuma política interna ou de links seguros padrão.</span><span class="sxs-lookup"><span data-stu-id="c7610-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="c7610-109">Para obter a verificação de URLs de links seguros, você precisa criar uma ou mais políticas de links seguros, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c7610-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="c7610-110">Você pode configurar políticas de links seguros no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações qualificadas da Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online, mas com assinaturas do Office 365 ATP Add-on).</span><span class="sxs-lookup"><span data-stu-id="c7610-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

<span data-ttu-id="c7610-111">Os elementos básicos de uma política de links seguros são:</span><span class="sxs-lookup"><span data-stu-id="c7610-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="c7610-112">**A política de links seguros**: Ative a proteção de links seguros, ative a verificação de URL em tempo real, especifique se deve aguardar a conclusão da verificação em tempo real antes de entregar a mensagem, ative a verificação de mensagens internas, especifique se deseja rastrear cliques do usuário em URLs e especifique se deseja permitir que os usuários cliquem em Trough para a URL original.</span><span class="sxs-lookup"><span data-stu-id="c7610-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="c7610-113">**A regra de links seguros**: especifica a prioridade e os filtros de destinatários (a qual a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="c7610-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="c7610-114">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de links seguros no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="c7610-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c7610-115">Ao criar uma política de links seguros, você realmente está criando uma regra de links seguros e a política de links seguros associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="c7610-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c7610-116">Quando você modifica uma política de links seguros, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="c7610-117">Todas as outras configurações modificam a política de links seguros associada.</span><span class="sxs-lookup"><span data-stu-id="c7610-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="c7610-118">Quando você remove uma política de links seguros, a regra de links seguros e a política de links seguros associada são removidos.</span><span class="sxs-lookup"><span data-stu-id="c7610-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="c7610-119">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="c7610-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c7610-120">Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de links seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) , posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c7610-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c7610-121">Você define as configurações globais para proteção de links seguros **fora** de políticas de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="c7610-122">Para obter instruções, consulte [Configure Global Settings for Safe links in Office 365 ATP](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c7610-122">For instructions, see [Configure global settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c7610-123">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="c7610-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c7610-124">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c7610-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c7610-125">Para ir diretamente para a página de **links seguros de ATP** , use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="c7610-125">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="c7610-126">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c7610-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c7610-127">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c7610-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c7610-128">Para exibir, criar, modificar e excluir as políticas de links seguros, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="c7610-128">To view, create, modify, and delete Safe Links policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="c7610-129">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c7610-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="c7610-130">**Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c7610-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="c7610-131">Para obter as configurações recomendadas para políticas de links seguros, consulte [configurações de política de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="c7610-131">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="c7610-132">Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="c7610-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c7610-133">[Novos recursos estão sempre sendo adicionados à ATP](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="c7610-133">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="c7610-134">À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes em suas políticas de links seguros existentes.</span><span class="sxs-lookup"><span data-stu-id="c7610-134">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="c7610-135">Usar o centro de conformidade de & de segurança para criar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-135">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="c7610-136">A criação de uma política de links seguros personalizada no centro de conformidade de & de segurança cria a regra de links seguros e a política de links seguros associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="c7610-136">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="c7610-137">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c7610-138">Na página **links seguros** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="c7610-138">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="c7610-139">O assistente de **nova política de links seguros** é aberto.</span><span class="sxs-lookup"><span data-stu-id="c7610-139">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="c7610-140">Na página **nomear sua política** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c7610-140">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="c7610-141">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="c7610-141">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="c7610-142">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="c7610-142">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="c7610-143">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c7610-143">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c7610-144">Na página **configurações** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c7610-144">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7610-145">**Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens**: selecione **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c7610-145">**Select the action for unknown potentially malicious URLs in messages**: Select **On**.</span></span>

   - <span data-ttu-id="c7610-146">**Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens**: selecione **ativado** ou deixe o valor padrão **desativado** .</span><span class="sxs-lookup"><span data-stu-id="c7610-146">**Select the action for unknown potentially malicious URLs in messages**: Select **On** or leave the default value **Off** selected.</span></span>

   - <span data-ttu-id="c7610-147">**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**: Selecione essa configuração para habilitar a verificação em tempo real de links em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="c7610-147">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="c7610-148">**Aguarde a conclusão da verificação de URL antes de entregar a mensagem**: Selecione essa configuração para esperar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c7610-148">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="c7610-149">**Aplicar links seguros a mensagens de email enviadas dentro da organização**: Selecione essa configuração para aplicar a política de links seguros a mensagens entre remetentes internos e destinatários internos.</span><span class="sxs-lookup"><span data-stu-id="c7610-149">**Apply safe links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="c7610-150">**Não rastrear cliques do usuário**: Deixe essa configuração desmarcada para permitir que o usuário de acompanhamento clique em URLs nas mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="c7610-150">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="c7610-151">**Não permitir que os usuários cliquem na URL original**: Selecione essa configuração para impedir que os usuários cliquem na URL original nas [páginas de aviso](atp-safe-links.md#warning-pages-from-safe-links).</span><span class="sxs-lookup"><span data-stu-id="c7610-151">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="c7610-152">**Não Reescreva as seguintes URLs**: permite acessar as URLs especificadas que, caso contrário, serão bloqueadas por links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-152">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="c7610-153">Na caixa, digite a URL ou o valor desejado e clique em</span><span class="sxs-lookup"><span data-stu-id="c7610-153">In the box, type the URL or value that you want, and then click</span></span> ![Ícone Adicionar botão](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="c7610-155">.</span><span class="sxs-lookup"><span data-stu-id="c7610-155">.</span></span>

     <span data-ttu-id="c7610-156">Para remover uma entrada existente, selecione-a e clique em</span><span class="sxs-lookup"><span data-stu-id="c7610-156">To remove an existing entry, select it and then click</span></span> ![Ícone Excluir botão](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="c7610-158">.</span><span class="sxs-lookup"><span data-stu-id="c7610-158">.</span></span>

     <span data-ttu-id="c7610-159">Para obter a sintaxe de entrada, consulte a [sintaxe de entrada da lista "não reescrever as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="c7610-159">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="c7610-160">Para obter informações detalhadas sobre essas configurações, consulte [configurações de links seguros para mensagens de email](atp-safe-links.md#safe-links-settings-for-email-messages) e [configurações de links seguros para o Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="c7610-160">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="c7610-161">Para obter mais valores recomendados para configurações de política padrão e estrita, consulte [configurações de política de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="c7610-161">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="c7610-162">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c7610-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c7610-163">Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="c7610-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="c7610-164">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="c7610-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c7610-165">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="c7610-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="c7610-166">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="c7610-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="c7610-167">Clique em **Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="c7610-167">Click **Add a condition**.</span></span> <span data-ttu-id="c7610-168">Na lista suspensa exibida, selecione uma condição em **aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="c7610-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="c7610-169">**O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c7610-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="c7610-170">**O destinatário é um membro de**: especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c7610-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="c7610-171">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="c7610-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="c7610-172">Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.</span><span class="sxs-lookup"><span data-stu-id="c7610-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="c7610-173">Clique na caixa e role pela lista de valores para selecionar.</span><span class="sxs-lookup"><span data-stu-id="c7610-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="c7610-174">Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c7610-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="c7610-175">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="c7610-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="c7610-176">Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="c7610-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="c7610-177">Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="c7610-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="c7610-178">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.</span><span class="sxs-lookup"><span data-stu-id="c7610-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="c7610-179">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**.</span><span class="sxs-lookup"><span data-stu-id="c7610-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="c7610-180">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="c7610-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="c7610-181">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c7610-181">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c7610-182">Na página **revise suas configurações** exibidas, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="c7610-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="c7610-183">Você pode clicar em **Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="c7610-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="c7610-184">Quando tiver concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c7610-184">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="c7610-185">Usar o centro de conformidade de & de segurança para exibir políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-185">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="c7610-186">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c7610-187">Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="c7610-187">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="c7610-188">Os detalhes da política aparecem em saída</span><span class="sxs-lookup"><span data-stu-id="c7610-188">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="c7610-189">Usar o centro de conformidade de & de segurança para modificar as políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-189">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="c7610-190">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c7610-191">Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="c7610-191">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c7610-192">Nos detalhes da política que aparecem, clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="c7610-192">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="c7610-193">As configurações disponíveis no menu suspenso que aparecem são idênticas às descritas na seção [usar o centro de conformidade de segurança & para criar políticas de links seguros](#use-the-security--compliance-center-to-create-safe-links-policies) .</span><span class="sxs-lookup"><span data-stu-id="c7610-193">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="c7610-194">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c7610-194">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="c7610-195">Habilitar ou desabilitar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-195">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="c7610-196">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c7610-197">Observe o valor na coluna **status** :</span><span class="sxs-lookup"><span data-stu-id="c7610-197">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="c7610-198">Mova o botão de alternância para a esquerda para desabilitar a política:</span><span class="sxs-lookup"><span data-stu-id="c7610-198">Move the toggle to the left to disable the policy:</span></span> ![Desativar política](../../media/scc-toggle-off.png)<span data-ttu-id="c7610-200">.</span><span class="sxs-lookup"><span data-stu-id="c7610-200">.</span></span>

   - <span data-ttu-id="c7610-201">Mova o botão de alternância para a direita para habilitar a política:</span><span class="sxs-lookup"><span data-stu-id="c7610-201">Move the toggle to the right to enable the policy:</span></span> ![Ativar política](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c7610-203">.</span><span class="sxs-lookup"><span data-stu-id="c7610-203">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="c7610-204">Definir a prioridade das políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-204">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="c7610-205">Por padrão, as políticas de links seguros recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="c7610-205">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="c7610-206">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="c7610-206">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c7610-207">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="c7610-207">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c7610-208">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="c7610-208">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="c7610-209">As políticas de links seguros são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="c7610-209">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="c7610-210">**Observação**: no centro de conformidade & segurança, você só pode alterar a prioridade da política de links seguros após criá-la.</span><span class="sxs-lookup"><span data-stu-id="c7610-210">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="c7610-211">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="c7610-211">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="c7610-212">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="c7610-212">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="c7610-213">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-213">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c7610-214">Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="c7610-214">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c7610-215">Na saída detalhes da política exibida, clique no botão prioridade disponível:</span><span class="sxs-lookup"><span data-stu-id="c7610-215">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="c7610-216">A política de links seguros com o valor de **prioridade** **0** tem apenas o botão **diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="c7610-216">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="c7610-217">A política de links seguros com o menor valor de **prioridade** (por exemplo, **3**) tem apenas o botão **aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="c7610-217">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="c7610-218">Se você tiver três ou mais políticas de links seguros, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c7610-218">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="c7610-219">Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="c7610-219">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="c7610-220">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c7610-220">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="c7610-221">Usar o centro de conformidade de & de segurança para remover políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-221">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="c7610-222">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c7610-223">Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="c7610-223">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c7610-224">Nos detalhes da política de saída, clique em **excluir política**e clique em **Sim** na caixa de diálogo de aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="c7610-224">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="c7610-225">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-225">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="c7610-226">Como descrito anteriormente, uma política de links seguros consiste em uma política de links seguros e uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-226">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="c7610-227">No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente.</span><span class="sxs-lookup"><span data-stu-id="c7610-227">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="c7610-228">Você gerencia as políticas de links seguros usando os cmdlets \*\* \* -SafeLinksPolicy\*\* e gerencia as regras de links seguros usando os cmdlets \*\* \* -SafeLinksRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="c7610-228">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="c7610-229">No PowerShell, você cria a política de links seguros primeiro e, em seguida, cria a regra de links seguros que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="c7610-229">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c7610-230">No PowerShell, você modifica as configurações da política de links seguros e da regra de links seguros separadamente.</span><span class="sxs-lookup"><span data-stu-id="c7610-230">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="c7610-231">Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="c7610-231">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="c7610-232">Usar o PowerShell para criar políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-232">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="c7610-233">A criação de uma política de links seguros no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="c7610-233">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c7610-234">Criar a política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-234">Create the safe links policy.</span></span>
2. <span data-ttu-id="c7610-235">Crie a regra de links seguros que especifica a política de links seguros à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="c7610-235">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="c7610-236">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c7610-236">**Notes**:</span></span>

- <span data-ttu-id="c7610-237">Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros sem associação existente a ela.</span><span class="sxs-lookup"><span data-stu-id="c7610-237">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="c7610-238">Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-238">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="c7610-239">Você pode definir as seguintes configurações em novas políticas de links seguros no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="c7610-239">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="c7610-240">Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="c7610-240">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="c7610-241">Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="c7610-241">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="c7610-242">Uma nova política de links seguros que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-242">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="c7610-243">Etapa 1: usar o PowerShell para criar uma política de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-243">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="c7610-244">Para criar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-244">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="c7610-245">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c7610-245">**Notes**:</span></span>

- <span data-ttu-id="c7610-246">Para obter detalhes sobre a sintaxe de entrada a ser usada para o parâmetro _DoNotRewriteUrls_ , consulte [a sintaxe de entrada da lista "não reescrever as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="c7610-246">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="c7610-247">Para obter sintaxe adicional que você pode usar para o parâmetro _DoNotRewriteUrls_ ao modificar as políticas de links seguros existentes usando o cmdlet **set-SafeLinksPolicy** , consulte a seção [usar o PowerShell para modificar as políticas de links seguros](#use-powershell-to-modify-safe-links-policies) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c7610-247">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="c7610-248">Este exemplo cria uma política de links seguros chamada contoso todos com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c7610-248">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="c7610-249">Ative a verificação de URL e reescreva em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="c7610-249">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="c7610-250">Ative a verificação de URL no Microsoft Teams (toque apenas em visualização).</span><span class="sxs-lookup"><span data-stu-id="c7610-250">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="c7610-251">Ative a verificação em tempo real de URLs clicadas, incluindo links clicados apontando para arquivos.</span><span class="sxs-lookup"><span data-stu-id="c7610-251">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="c7610-252">Aguarde a conclusão da verificação de URL antes de entregar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c7610-252">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="c7610-253">Ative a verificação de URL e a reconfiguração de mensagens internas.</span><span class="sxs-lookup"><span data-stu-id="c7610-253">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="c7610-254">Rastrear cliques do usuário relacionados à proteção de links seguros (não estamos usando o parâmetro _DoNotTrackUserClicks_ , e o valor padrão é $false, o que significa que os cliques do usuário são controlados).</span><span class="sxs-lookup"><span data-stu-id="c7610-254">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="c7610-255">Não permita que os usuários cliquem até a URL original.</span><span class="sxs-lookup"><span data-stu-id="c7610-255">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="c7610-256">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c7610-256">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="c7610-257">Etapa 2: usar o PowerShell para criar uma regra de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-257">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="c7610-258">Para criar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-258">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="c7610-259">Este exemplo cria uma regra de links seguros chamada contoso com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="c7610-259">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="c7610-260">A regra é associada à política de links seguros chamada contoso ALL.</span><span class="sxs-lookup"><span data-stu-id="c7610-260">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="c7610-261">A regra se aplica a todos os destinatários no domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c7610-261">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="c7610-262">Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="c7610-262">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="c7610-263">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="c7610-263">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="c7610-264">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c7610-264">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="c7610-265">Usar o PowerShell para exibir políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-265">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="c7610-266">Para exibir as políticas de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-266">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c7610-267">Este exemplo retorna uma lista resumida de todas as políticas de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-267">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="c7610-268">Este exemplo retorna informações detalhadas sobre a política de links seguros chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="c7610-268">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="c7610-269">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c7610-269">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="c7610-270">Usar o PowerShell para exibir regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-270">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="c7610-271">Para exibir regras de links seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-271">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c7610-272">Este exemplo retorna uma lista resumida de todas as regras de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-272">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="c7610-273">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="c7610-273">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="c7610-274">Este exemplo retorna informações detalhadas sobre a regra de links seguros chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="c7610-274">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="c7610-275">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c7610-275">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="c7610-276">Usar o PowerShell para modificar as políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-276">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="c7610-277">Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **set-SafeLinksPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="c7610-277">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c7610-278">Ao renomear uma política de links seguros no centro de conformidade e segurança &, você estará apenas renomeando a _regra_de links seguros.</span><span class="sxs-lookup"><span data-stu-id="c7610-278">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="c7610-279">A única consideração adicional para modificar as políticas de links seguros no PowerShell é a sintaxe disponível para o parâmetro _DoNotRewriteUrls_ (a [lista "não reescrever as seguintes URLs"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="c7610-279">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="c7610-280">Para adicionar valores que substituirão as entradas existentes, use a seguinte sintaxe: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="c7610-280">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="c7610-281">Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="c7610-281">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="c7610-282">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de links seguros, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de links seguros](#step-1-use-powershell-to-create-a-safe-links-policy) , anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c7610-282">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="c7610-283">Para modificar uma política de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-283">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c7610-284">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c7610-284">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="c7610-285">Usar o PowerShell para modificar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-285">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="c7610-286">A única configuração que não está disponível quando você modifica uma regra de links seguros no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c7610-286">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c7610-287">Para habilitar ou desabilitar regras de links seguros existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="c7610-287">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="c7610-288">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de links seguros](#step-2-use-powershell-to-create-a-safe-links-rule) , anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c7610-288">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="c7610-289">Para modificar uma regra de links seguros, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-289">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c7610-290">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c7610-290">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="c7610-291">Usar o PowerShell para habilitar ou desabilitar regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-291">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="c7610-292">Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política de links seguros (a regra de links seguros e a política de links seguros atribuídas).</span><span class="sxs-lookup"><span data-stu-id="c7610-292">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="c7610-293">Para habilitar ou desabilitar uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-293">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="c7610-294">Este exemplo desabilita a regra de links seguros chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="c7610-294">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c7610-295">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="c7610-295">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c7610-296">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c7610-296">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="c7610-297">Usar o PowerShell para definir a prioridade de regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-297">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="c7610-298">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="c7610-298">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c7610-299">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="c7610-299">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c7610-300">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="c7610-300">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c7610-301">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="c7610-301">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c7610-302">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="c7610-302">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c7610-303">Para definir a prioridade de uma regra de links seguros no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-303">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c7610-304">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="c7610-304">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="c7610-305">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="c7610-305">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="c7610-306">**Observação**: para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="c7610-306">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="c7610-307">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c7610-307">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="c7610-308">Usar o PowerShell para remover políticas de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-308">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="c7610-309">Quando você usa o PowerShell para remover uma política de links seguros, a regra de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="c7610-309">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="c7610-310">Para remover uma política de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-310">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c7610-311">Este exemplo remove a política de links seguros chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="c7610-311">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c7610-312">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c7610-312">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="c7610-313">Usar o PowerShell para remover regras de links seguros</span><span class="sxs-lookup"><span data-stu-id="c7610-313">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="c7610-314">Quando você usa o PowerShell para remover uma regra de links seguros, a política de links seguros correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="c7610-314">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="c7610-315">Para remover uma regra de links seguros no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7610-315">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="c7610-316">Este exemplo remove a regra de links seguros chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="c7610-316">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c7610-317">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c7610-317">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="c7610-318">Para verificar se os links seguros estão verificando mensagens, verifique os relatórios de proteção avançada contra ameaças disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c7610-318">To verify that Safe Links is scanning messages, check the available Advanced Threat Protection reports.</span></span> <span data-ttu-id="c7610-319">Para obter mais informações, consulte [exibir relatórios do Office 365 ATP](view-reports-for-atp.md) e [usar o Explorer no centro de conformidade do & de segurança](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="c7610-319">For more information, see [View reports for Office 365 ATP](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c7610-320">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="c7610-320">How do you know these procedures worked?</span></span>

<span data-ttu-id="c7610-321">Para verificar se as políticas de links seguros foram criadas, modificadas ou removidas com êxito, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c7610-321">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="c7610-322">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="c7610-322">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="c7610-323">Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="c7610-323">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="c7610-324">Para exibir mais detalhes, selecione a política na lista e exiba os detalhes na saída.</span><span class="sxs-lookup"><span data-stu-id="c7610-324">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="c7610-325">No PowerShell do Exchange Online ou do Exchange Online Protection, substitua o \<Name\> nome da política ou regra, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="c7610-325">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
