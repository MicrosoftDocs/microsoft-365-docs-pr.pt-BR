---
title: Configurar políticas Cofre anexos no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Saiba como definir as Cofre de anexos para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108218"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9b69f-103">Configurar políticas Cofre anexos no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9b69f-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b69f-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9b69f-104">**Applies to**</span></span>
- [<span data-ttu-id="9b69f-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9b69f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9b69f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b69f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="9b69f-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9b69f-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="9b69f-108">Se você for um usuário de residência procurando informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="9b69f-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9b69f-109">Cofre Os anexos são um recurso do [Microsoft Defender](whats-new-in-defender-for-office-365.md) para Office 365 que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois que eles foram verificados pela proteção anti-malware no [Proteção do Exchange Online (EOP),](anti-malware-protection.md)mas antes da entrega aos destinatários.</span><span class="sxs-lookup"><span data-stu-id="9b69f-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="9b69f-110">Para obter mais informações, [consulte Cofre Anexos no Microsoft Defender para Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="9b69f-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="9b69f-111">Não há política de anexos interna ou Cofre padrão.</span><span class="sxs-lookup"><span data-stu-id="9b69f-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="9b69f-112">Para obter Cofre de Anexos de anexos de mensagem de email, você precisa criar uma ou mais Cofre políticas de anexos, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69f-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="9b69f-113">Você pode configurar políticas de anexos do Cofre no portal do Microsoft 365 Defender ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio Exchange Online, mas com o Defender para assinaturas de complemento de Office 365).</span><span class="sxs-lookup"><span data-stu-id="9b69f-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="9b69f-114">Os elementos básicos de uma política Cofre Attachments são:</span><span class="sxs-lookup"><span data-stu-id="9b69f-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="9b69f-115">A **política** de anexo seguro : especifica as ações para detecções de malware desconhecidas, se o envio de mensagens com anexos de malware para um endereço de email especificado e se a entrega de mensagens se Cofre verificação de anexos não puder ser concluída.</span><span class="sxs-lookup"><span data-stu-id="9b69f-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="9b69f-116">**A regra de anexo seguro**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="9b69f-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="9b69f-117">A diferença entre esses dois elementos não é óbvia quando você gerencia Cofre políticas de anexos no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="9b69f-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="9b69f-118">Quando você cria uma política de Cofre de anexos, você está realmente criando uma regra de anexo seguro e a política de anexo segura associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="9b69f-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="9b69f-119">Quando você modifica uma Cofre de anexos, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="9b69f-120">Todas as outras configurações modificam a política de anexo seguro associada.</span><span class="sxs-lookup"><span data-stu-id="9b69f-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="9b69f-121">Quando você remove uma Cofre de anexos, a regra de anexo seguro e a política de anexo seguro associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="9b69f-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="9b69f-122">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="9b69f-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="9b69f-123">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autônomo para configurar Cofre políticas de anexos posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69f-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="9b69f-124">Na área de configurações globais de Cofre De anexos, você configura recursos que não dependem de políticas Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="9b69f-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="9b69f-125">Para obter instruções, consulte Ativar Cofre anexos para [SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) e Cofre documentos [Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="9b69f-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9b69f-126">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="9b69f-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9b69f-127">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="9b69f-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="9b69f-128">Para ir diretamente para a página **Cofre Anexos,** use <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="9b69f-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="9b69f-129">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b69f-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9b69f-130">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b69f-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9b69f-131">Você precisa de permissões antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="9b69f-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9b69f-132">Para criar, modificar e excluir Cofre de anexos, você precisa  ser membro  dos grupos de função Gerenciamento da Organização ou  Administrador de Segurança no **portal** Microsoft 365 Defender e membro do grupo de função Gerenciamento da Organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9b69f-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="9b69f-133">Para acessar somente leitura Cofre políticas de Anexos, você precisa ser  membro dos grupos de função Leitor **Global** ou Leitor de Segurança no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9b69f-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="9b69f-134">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="9b69f-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9b69f-135">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="9b69f-135">**Notes**:</span></span>

  - <span data-ttu-id="9b69f-136">Adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b69f-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9b69f-137">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9b69f-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="9b69f-138">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="9b69f-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="9b69f-139">Para nossas configurações recomendadas para Cofre de anexos, [consulte Cofre Configurações de anexos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="9b69f-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="9b69f-140">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="9b69f-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="9b69f-141">Usar o portal Microsoft 365 Defender para criar Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="9b69f-142">A criação de uma política Cofre anexos personalizados no portal Microsoft 365 Defender cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="9b69f-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="9b69f-143">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="9b69f-144">Na página **Cofre Anexos,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="9b69f-145">O assistente de política é aberto.</span><span class="sxs-lookup"><span data-stu-id="9b69f-145">The policy wizard opens.</span></span> <span data-ttu-id="9b69f-146">Na página **Nomear sua política,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="9b69f-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="9b69f-147">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="9b69f-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="9b69f-148">**Descrição**: insira uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="9b69f-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9b69f-149">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9b69f-150">Na página **Usuários e domínios** que aparece, identifique os destinatários internos aos quais a política se aplica (condições de destinatário):</span><span class="sxs-lookup"><span data-stu-id="9b69f-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="9b69f-151">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="9b69f-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9b69f-152">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="9b69f-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="9b69f-153">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="9b69f-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="9b69f-154">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="9b69f-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="9b69f-155">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="9b69f-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="9b69f-156">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="9b69f-156">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="9b69f-158">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="9b69f-158">next to the value.</span></span>

   <span data-ttu-id="9b69f-159">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="9b69f-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="9b69f-160">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9b69f-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="9b69f-161">Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="9b69f-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9b69f-162">Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9b69f-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="9b69f-163">**Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="9b69f-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="9b69f-164">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="9b69f-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9b69f-165">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9b69f-166">Na página **Configurações,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="9b69f-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="9b69f-167">Cofre resposta de **malware desconhecido anexos**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9b69f-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="9b69f-168">**Off**: Normalmente, não recomendamos esse valor.</span><span class="sxs-lookup"><span data-stu-id="9b69f-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="9b69f-169">**Monitorar**</span><span class="sxs-lookup"><span data-stu-id="9b69f-169">**Monitor**</span></span>
     - <span data-ttu-id="9b69f-170">**Bloquear**: esse é o valor padrão e o valor recomendado em Políticas de segurança predefinidas padrão [e estritas.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9b69f-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="9b69f-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="9b69f-171">**Replace**</span></span>
     - <span data-ttu-id="9b69f-172">**Entrega Dinâmica (Recurso de Visualização)**</span><span class="sxs-lookup"><span data-stu-id="9b69f-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="9b69f-173">Esses valores são explicados [Cofre configurações de política de anexos.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="9b69f-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="9b69f-174">Redirecionar mensagens com **anexos detectados**: se você selecionar Habilitar redirecionamento, poderá especificar um endereço de email na caixa Enviar mensagens que contenham **anexos bloqueados, monitorados** ou substituídos na caixa de endereços de email especificado para enviar mensagens que contenham anexos de malware para análise e investigação.</span><span class="sxs-lookup"><span data-stu-id="9b69f-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="9b69f-175">A recomendação para configurações de política padrão e estrita é habilitar o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="9b69f-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="9b69f-176">Para obter mais informações, [consulte Cofre Configurações de anexos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="9b69f-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="9b69f-177">Aplique a resposta de detecção de **anexos** do Cofre se a verificação não puder ser concluída (tempo de conclusão ou erros) : a ação especificada pelo **Cofre Anexos** resposta de malware desconhecido é tomada em mensagens mesmo quando Cofre verificação de Anexos não pode ser concluída.</span><span class="sxs-lookup"><span data-stu-id="9b69f-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="9b69f-178">Se você selecionou essa opção, selecione Sempre **Habilitar redirecionamento** e especificar um endereço de email para enviar mensagens que contenham anexos de malware.</span><span class="sxs-lookup"><span data-stu-id="9b69f-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="9b69f-179">Caso contrário, as mensagens podem ser perdidas.</span><span class="sxs-lookup"><span data-stu-id="9b69f-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="9b69f-180">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9b69f-181">Na página **Revisão** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="9b69f-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="9b69f-182">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="9b69f-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="9b69f-183">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="9b69f-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="9b69f-184">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="9b69f-185">Na mensagem de confirmação exibida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="9b69f-186">Use o portal Microsoft 365 Defender para exibir Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="9b69f-187">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-187">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="9b69f-188">Na página **Cofre Anexos,** as seguintes propriedades são exibidas na lista de políticas:</span><span class="sxs-lookup"><span data-stu-id="9b69f-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="9b69f-189">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9b69f-189">**Name**</span></span>
   - <span data-ttu-id="9b69f-190">**Status**</span><span class="sxs-lookup"><span data-stu-id="9b69f-190">**Status**</span></span>
   - <span data-ttu-id="9b69f-191">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="9b69f-191">**Priority**</span></span>

3. <span data-ttu-id="9b69f-192">Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="9b69f-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="9b69f-193">Usar o portal Microsoft 365 Defender para modificar Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="9b69f-194">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-194">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="9b69f-195">Na página **Cofre Anexos,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="9b69f-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="9b69f-196">No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="9b69f-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="9b69f-197">Para obter mais informações sobre as configurações, consulte a seção Usar o portal Microsoft 365 Defender para criar Cofre [de anexos](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69f-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="9b69f-198">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="9b69f-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="9b69f-199">Habilitar ou desabilitar Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="9b69f-200">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-200">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="9b69f-201">Na página **Cofre Anexos,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="9b69f-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="9b69f-202">Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9b69f-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="9b69f-203">**Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .</span><span class="sxs-lookup"><span data-stu-id="9b69f-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="9b69f-204">**Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="9b69f-205">Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="9b69f-206">Clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="9b69f-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="9b69f-207">De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="9b69f-208">Definir a prioridade das políticas de Cofre Anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="9b69f-209">Por padrão, Cofre de anexos recebe uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="9b69f-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="9b69f-210">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="9b69f-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9b69f-211">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="9b69f-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="9b69f-212">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="9b69f-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="9b69f-213">Cofre As políticas de anexos são exibidas na ordem em que são processadas (a primeira política tem o **valor Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="9b69f-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="9b69f-214">**Observação**: no portal Microsoft 365 Defender, você só pode alterar a prioridade da política Cofre Anexos após a criação.</span><span class="sxs-lookup"><span data-stu-id="9b69f-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="9b69f-215">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="9b69f-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9b69f-216">Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="9b69f-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="9b69f-217">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="9b69f-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="9b69f-218">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-218">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="9b69f-219">Na página **Cofre Anexos,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="9b69f-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="9b69f-220">Na parte superior do sobremenu de detalhes  da política  exibido, você verá Aumentar prioridade ou Diminuir prioridade com base no valor de prioridade atual e no número de políticas:</span><span class="sxs-lookup"><span data-stu-id="9b69f-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="9b69f-221">A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="9b69f-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="9b69f-222">A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="9b69f-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="9b69f-223">Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9b69f-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="9b69f-224">Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="9b69f-225">Quando terminar, clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="9b69f-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="9b69f-226">Use o portal Microsoft 365 Defender para remover Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="9b69f-227">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-227">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="9b69f-228">Na página **Cofre Anexos,** selecione uma política personalizada na lista clicando no nome da política.</span><span class="sxs-lookup"><span data-stu-id="9b69f-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="9b69f-229">Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="9b69f-230">Na caixa de diálogo de confirmação exibida, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="9b69f-231">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="9b69f-232">Conforme descrito anteriormente, uma política Cofre Attachments consiste em uma política de anexo seguro e uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="9b69f-233">No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente.</span><span class="sxs-lookup"><span data-stu-id="9b69f-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="9b69f-234">Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo segura usando os cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9b69f-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="9b69f-235">No PowerShell, primeiro você cria a política de anexo seguro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="9b69f-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="9b69f-236">No PowerShell, você modifica as configurações na política de anexo seguro e a regra de anexo seguro separadamente.</span><span class="sxs-lookup"><span data-stu-id="9b69f-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="9b69f-237">Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="9b69f-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="9b69f-238">Usar o PowerShell para criar Cofre de anexos</span><span class="sxs-lookup"><span data-stu-id="9b69f-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="9b69f-239">Criar uma Cofre de anexos no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="9b69f-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9b69f-240">Crie a política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="9b69f-241">Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="9b69f-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="9b69f-242">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="9b69f-242">**Notes**:</span></span>

- <span data-ttu-id="9b69f-243">Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo seguro existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="9b69f-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="9b69f-244">Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="9b69f-245">Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="9b69f-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="9b69f-246">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="9b69f-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="9b69f-247">Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="9b69f-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="9b69f-248">Uma nova política de anexo seguro que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="9b69f-249">Etapa 1: Usar o PowerShell para criar uma política de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="9b69f-250">Para criar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="9b69f-251">Este exemplo cria uma política de anexo seguro chamada Contoso All com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9b69f-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="9b69f-252">Bloquear mensagens que são encontradas para conter malware Cofre verificação de documentos (não estamos usando o parâmetro _Action_ e o valor padrão é `Block` ).</span><span class="sxs-lookup"><span data-stu-id="9b69f-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="9b69f-253">O redirecionamento está habilitado e as mensagens que são encontradas com malware são enviadas sec-ops@contoso.com análise e investigação.</span><span class="sxs-lookup"><span data-stu-id="9b69f-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="9b69f-254">Se Cofre verificação de anexos não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="9b69f-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="9b69f-255">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9b69f-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="9b69f-256">Etapa 2: Usar o PowerShell para criar uma regra de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="9b69f-257">Para criar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="9b69f-258">Este exemplo cria uma regra de anexo segura chamada Contoso All com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="9b69f-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="9b69f-259">A regra é associada à política de anexo seguro chamada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="9b69f-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="9b69f-260">A regra se aplica a todos os destinatários no contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="9b69f-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="9b69f-261">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="9b69f-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="9b69f-262">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="9b69f-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="9b69f-263">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9b69f-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="9b69f-264">Usar o PowerShell para exibir políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="9b69f-265">Para exibir políticas de anexo seguras existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9b69f-266">Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="9b69f-267">Este exemplo retorna informações detalhadas para a política de anexo seguro chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="9b69f-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9b69f-268">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9b69f-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="9b69f-269">Usar o PowerShell para exibir regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="9b69f-270">Para exibir as regras de anexo seguro existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9b69f-271">Este exemplo retorna uma lista resumida de todas as regras de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="9b69f-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="9b69f-272">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="9b69f-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="9b69f-273">Este exemplo retorna informações detalhadas para a regra de anexo seguro chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="9b69f-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9b69f-274">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9b69f-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="9b69f-275">Usar o PowerShell para modificar políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="9b69f-276">Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **Set-SafeAttachmentPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="9b69f-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9b69f-277">Ao renomear uma política Cofre Anexos no portal Microsoft 365 Defender, você só está renomeando a regra de anexo _seguro._</span><span class="sxs-lookup"><span data-stu-id="9b69f-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="9b69f-278">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro, conforme descrito na Etapa [1: Usar](#step-1-use-powershell-to-create-a-safe-attachment-policy) o PowerShell para criar uma seção de política de anexo seguro anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69f-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="9b69f-279">Para modificar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9b69f-280">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9b69f-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="9b69f-281">Usar o PowerShell para modificar regras de anexo seguras</span><span class="sxs-lookup"><span data-stu-id="9b69f-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="9b69f-282">A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="9b69f-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9b69f-283">Para habilitar ou desabilitar as regras de anexo segura existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="9b69f-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="9b69f-284">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-a-safe-attachment-rule) o PowerShell para criar uma seção de regra de anexo seguro anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69f-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="9b69f-285">Para modificar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9b69f-286">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9b69f-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="9b69f-287">Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="9b69f-288">Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política Cofre Anexos do Cofre (a regra de anexo seguro e a política de anexo seguro atribuída).</span><span class="sxs-lookup"><span data-stu-id="9b69f-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="9b69f-289">Para habilitar ou desabilitar uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="9b69f-290">Este exemplo desabilita a regra de anexo seguro chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="9b69f-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9b69f-291">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="9b69f-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9b69f-292">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9b69f-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="9b69f-293">Usar o PowerShell para definir a prioridade das regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="9b69f-294">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="9b69f-294">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9b69f-295">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="9b69f-295">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9b69f-296">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="9b69f-296">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9b69f-297">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="9b69f-297">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9b69f-298">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="9b69f-298">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9b69f-299">Para definir a prioridade de uma regra de anexo seguro no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9b69f-300">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="9b69f-300">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="9b69f-301">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="9b69f-301">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9b69f-302">**Observação**: para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9b69f-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="9b69f-303">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9b69f-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="9b69f-304">Usar o PowerShell para remover políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="9b69f-305">Quando você usa o PowerShell para remover uma política de anexo seguro, a regra de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="9b69f-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="9b69f-306">Para remover uma política de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9b69f-307">Este exemplo remove a política de anexo seguro chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="9b69f-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9b69f-308">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9b69f-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="9b69f-309">Usar o PowerShell para remover regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="9b69f-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="9b69f-310">Quando você usa o PowerShell para remover uma regra de anexo seguro, a política de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="9b69f-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="9b69f-311">Para remover uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b69f-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="9b69f-312">Este exemplo remove a regra de anexo seguro chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="9b69f-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9b69f-313">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9b69f-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9b69f-314">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="9b69f-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="9b69f-315">Para verificar se você criou, modificou ou removeu com êxito Cofre políticas de Anexos, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9b69f-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="9b69f-316">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="9b69f-316">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="9b69f-317">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="9b69f-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9b69f-318">Para exibir mais detalhes, selecione a política na lista clicando no nome e exibindo os detalhes no fly-out.</span><span class="sxs-lookup"><span data-stu-id="9b69f-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="9b69f-319">Em Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e verifique \<Name\> as configurações:</span><span class="sxs-lookup"><span data-stu-id="9b69f-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="9b69f-320">Para verificar se Cofre anexos está verificando mensagens, verifique o Defender disponível para Office 365 relatórios.</span><span class="sxs-lookup"><span data-stu-id="9b69f-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="9b69f-321">Para obter mais informações, [consulte View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="9b69f-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
