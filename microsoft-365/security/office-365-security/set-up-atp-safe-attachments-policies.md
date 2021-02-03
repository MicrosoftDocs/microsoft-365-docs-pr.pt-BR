---
title: Configurar políticas de Anexos Seguros no Microsoft Defender para Office 365
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
description: Saiba mais sobre como definir políticas de Anexos seguros para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9343ce222f1deb84e900f0d6f18e7d55daa73372
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084608"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="353f1-103">Configurar políticas de Anexos Seguros no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="353f1-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="353f1-104">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="353f1-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="353f1-105">Se você for um usuário de residência procurando informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="353f1-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="353f1-106">Anexos Seguros é um recurso do [Microsoft Defender para Office 365](office-365-atp.md) que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois que eles são verificados pela proteção anti-malware no Proteção do Exchange Online [(EOP),](anti-malware-protection.md)mas antes da entrega aos destinatários.</span><span class="sxs-lookup"><span data-stu-id="353f1-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="353f1-107">Para obter mais informações, consulte [Anexos seguros no Microsoft Defender para Office 365.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="353f1-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="353f1-108">Não há nenhuma política de Anexos seguros interna ou padrão.</span><span class="sxs-lookup"><span data-stu-id="353f1-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="353f1-109">Para obter a verificação de Anexos Seguros de anexos de mensagens de email, você precisa criar uma ou mais políticas de Anexos Seguros, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="353f1-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="353f1-110">Você pode configurar políticas de Anexos Seguros no Centro de Conformidade e Segurança ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Defender para Office 365). &</span><span class="sxs-lookup"><span data-stu-id="353f1-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="353f1-111">Os elementos básicos de uma política de Anexos seguros são:</span><span class="sxs-lookup"><span data-stu-id="353f1-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="353f1-112">A política de anexo **seguro:** especifica as ações para detecções de malware desconhecidas, se é para enviar mensagens com anexos de malware para um endereço de email especificado e se a verificação de Anexos Seguros não pode ser concluída.</span><span class="sxs-lookup"><span data-stu-id="353f1-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="353f1-113">**A regra de anexo seguro:** especifica os filtros de prioridade e destinatário (a quem a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="353f1-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="353f1-114">A diferença entre esses dois elementos não é óbvia quando você gerencia as política de Anexos seguros no Centro de Conformidade & e Segurança:</span><span class="sxs-lookup"><span data-stu-id="353f1-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="353f1-115">Ao criar uma política de Anexos Seguros, você está criando uma regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="353f1-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="353f1-116">Quando você modifica uma política de Anexos Seguros, as configurações relacionadas ao nome, prioridade, habilitada ou desabilitada e filtros de destinatário modificam a regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="353f1-117">Todas as outras configurações modificam a política de anexo seguro associada.</span><span class="sxs-lookup"><span data-stu-id="353f1-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="353f1-118">Quando você remove uma política de Anexos Seguros, a regra de anexo seguro e a política de anexo seguro associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="353f1-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="353f1-119">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="353f1-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="353f1-120">Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online ou [do EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autônomo para configurar políticas de Anexos seguros posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="353f1-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="353f1-121">Na área de configurações globais das configurações de Anexos Seguros, você configura recursos que não dependem de políticas de Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="353f1-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="353f1-122">Para obter instruções, confira Ativar Anexos Seguros para [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md) e Microsoft Teams e Documentos Seguros no [Microsoft 365 E5.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="353f1-122">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="353f1-123">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="353f1-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="353f1-124">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="353f1-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="353f1-125">Para ir diretamente para a **página Anexos Seguros,** use <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="353f1-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="353f1-126">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="353f1-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="353f1-127">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="353f1-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="353f1-128">Para fazer os procedimentos deste artigo, você precisa ter permissões:</span><span class="sxs-lookup"><span data-stu-id="353f1-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="353f1-129">Para criar, modificar e excluir políticas de Anexos Seguros  &, você precisa ser membro dos grupos de função Gerenciamento  da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de funções Gerenciamento da Organização no Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="353f1-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="353f1-130">Para acesso somente leitura às políticas de Anexos Seguros, você  precisa ser membro dos grupos de função Leitor & **Global** ou Leitor de Segurança no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="353f1-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="353f1-131">Para obter mais informações, [consulte Permissões no Centro de conformidade e & segurança](permissions-in-the-security-and-compliance-center.md) no Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="353f1-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="353f1-132">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="353f1-132">**Notes**:</span></span>

  - <span data-ttu-id="353f1-133">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="353f1-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="353f1-134">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="353f1-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="353f1-135">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="353f1-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="353f1-136">Para nossas configurações recomendadas para políticas de Anexos Seguros, consulte [configurações de Anexos Seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="353f1-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="353f1-137">Permita até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="353f1-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="353f1-138">Usar o Centro de Conformidade & segurança para criar políticas de Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="353f1-139">Criar uma política de Anexo & s Seguros personalizada no Centro de Conformidade e Segurança cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="353f1-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="353f1-140">No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="353f1-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="353f1-141">Na página **Anexos Seguros,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="353f1-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="353f1-142">O **assistente nova política de Anexos seguros** é aberto.</span><span class="sxs-lookup"><span data-stu-id="353f1-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="353f1-143">Na página **Nomear sua política,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="353f1-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="353f1-144">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="353f1-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="353f1-145">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="353f1-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="353f1-146">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="353f1-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="353f1-147">Na página **Configurações** exibida, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="353f1-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="353f1-148">**Resposta de malware desconhecido anexos seguros:** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="353f1-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="353f1-149">**Off**: Normalmente, não recomendamos esse valor.</span><span class="sxs-lookup"><span data-stu-id="353f1-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="353f1-150">**Monitorar**</span><span class="sxs-lookup"><span data-stu-id="353f1-150">**Monitor**</span></span>
     - <span data-ttu-id="353f1-151">**Block:** este é o valor padrão e o valor recomendado nas políticas de segurança predefinidas Padrão [e Estrito.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="353f1-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="353f1-152">**Replace**</span><span class="sxs-lookup"><span data-stu-id="353f1-152">**Replace**</span></span>
     - <span data-ttu-id="353f1-153">**Entrega Dinâmica (Recurso de Visualização)**</span><span class="sxs-lookup"><span data-stu-id="353f1-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="353f1-154">Esses valores são explicados nas [configurações de política de Anexos seguros.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="353f1-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="353f1-155">Envie o anexo para o seguinte endereço de  **email:** para os valores de ação **Bloquear**, **Monitorar** ou Substituir , você pode selecionar Habilitar redirecionamento para enviar mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação. </span><span class="sxs-lookup"><span data-stu-id="353f1-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="353f1-156">A recomendação para as configurações de política Padrão e Estrito é habilitar o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="353f1-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="353f1-157">Para obter mais informações, consulte [configurações de Anexos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="353f1-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="353f1-158">Aplique a seleção acima se a verificação de anexos de **malware esgoter** ou ocorrer um erro: a ação especificada pela resposta de malware desconhecido **anexos** seguros é tomada em mensagens mesmo quando a verificação de Anexos Seguros não puder ser concluída.</span><span class="sxs-lookup"><span data-stu-id="353f1-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="353f1-159">Se você selecionou essa opção, sempre selecione **Redirecionamento habilitado.**</span><span class="sxs-lookup"><span data-stu-id="353f1-159">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="353f1-160">Caso contrário, as mensagens podem ser perdidas.</span><span class="sxs-lookup"><span data-stu-id="353f1-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="353f1-161">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="353f1-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="353f1-162">Na página **Aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="353f1-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="353f1-163">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="353f1-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="353f1-164">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="353f1-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="353f1-165">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="353f1-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="353f1-166">Clique **em Adicionar uma condição.**</span><span class="sxs-lookup"><span data-stu-id="353f1-166">Click **Add a condition**.</span></span> <span data-ttu-id="353f1-167">No menu suspenso exibido, selecione uma condição em **Aplicado se:**</span><span class="sxs-lookup"><span data-stu-id="353f1-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="353f1-168">**O destinatário é:** Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="353f1-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="353f1-169">**O destinatário é membro de:** Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="353f1-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="353f1-170">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="353f1-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="353f1-171">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="353f1-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="353f1-172">Clique na caixa e role pela lista de valores a selecionar.</span><span class="sxs-lookup"><span data-stu-id="353f1-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="353f1-173">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="353f1-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="353f1-174">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="353f1-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="353f1-175">Para remover entradas individuais, clique **no** ícone ![ Remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="353f1-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="353f1-176">Para remover toda a condição, clique **no** ícone ![ Remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="353f1-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="353f1-177">Para adicionar uma condição adicional, clique **em Adicionar uma condição** e selecione um valor restante em Aplicado **se**.</span><span class="sxs-lookup"><span data-stu-id="353f1-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="353f1-178">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Exceto **se**.</span><span class="sxs-lookup"><span data-stu-id="353f1-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="353f1-179">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="353f1-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="353f1-180">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="353f1-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="353f1-181">Na página **Revisar as configurações** exibida, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="353f1-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="353f1-182">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="353f1-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="353f1-183">Quando terminar, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="353f1-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="353f1-184">Usar o Centro de Conformidade & segurança para exibir políticas de Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="353f1-185">No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="353f1-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="353f1-186">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="353f1-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="353f1-187">Os detalhes da política aparecem em um fly out</span><span class="sxs-lookup"><span data-stu-id="353f1-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="353f1-188">Usar o Centro de Conformidade & Segurança para modificar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="353f1-189">No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="353f1-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="353f1-190">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="353f1-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="353f1-191">Nos detalhes da política exibidos, clique em **Editar política.**</span><span class="sxs-lookup"><span data-stu-id="353f1-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="353f1-192">As configurações disponíveis no menu explicativo exibido são idênticas às descritas na seção & Usar o Centro de Conformidade e Segurança para criar políticas de [Anexos seguros.](#use-the-security--compliance-center-to-create-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="353f1-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="353f1-193">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="353f1-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="353f1-194">Habilitar ou desabilitar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="353f1-195">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="353f1-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="353f1-196">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="353f1-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="353f1-197">Mover o alternância para a esquerda</span><span class="sxs-lookup"><span data-stu-id="353f1-197">Move the toggle to the left</span></span> ![Desativar política](../../media/scc-toggle-off.png) <span data-ttu-id="353f1-199">para desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="353f1-199">to disable the policy.</span></span>

   - <span data-ttu-id="353f1-200">Mover o alternância para a direita</span><span class="sxs-lookup"><span data-stu-id="353f1-200">Move the toggle to the right</span></span> ![Ativar a política](../../media/scc-toggle-on.png) <span data-ttu-id="353f1-202">para habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="353f1-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="353f1-203">Definir a prioridade das políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="353f1-204">Por padrão, as políticas de Anexos Seguros têm uma prioridade baseada na ordem em que foram criadas (políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="353f1-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="353f1-205">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="353f1-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="353f1-206">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="353f1-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="353f1-207">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="353f1-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="353f1-208">As políticas de Anexos Seguros são exibidas na ordem em que são processadas (a primeira política tem **o valor** prioridade 0).</span><span class="sxs-lookup"><span data-stu-id="353f1-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="353f1-209">**Observação:** no Centro de Conformidade & segurança, você só pode alterar a prioridade da política de Anexos seguros depois de criar a política.</span><span class="sxs-lookup"><span data-stu-id="353f1-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="353f1-210">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="353f1-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="353f1-211">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="353f1-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="353f1-212">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="353f1-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="353f1-213">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="353f1-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="353f1-214">Nos detalhes da política exibidos, clique no botão de prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="353f1-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="353f1-215">A política de Anexos Seguros com o **valor** **prioridade 0** tem apenas o **botão** Diminuir prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="353f1-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="353f1-216">A política anexos seguros com o menor valor **de** prioridade (por exemplo, **3**) tem apenas o **botão** Aumentar prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="353f1-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="353f1-217">Se você tiver três ou mais políticas de Anexos Seguros,  as políticas  entre os valores de prioridade mais alta e mais baixa terão os botões Aumentar prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="353f1-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="353f1-218">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor prioridade.**</span><span class="sxs-lookup"><span data-stu-id="353f1-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="353f1-219">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="353f1-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="353f1-220">Usar o Centro de Conformidade & segurança para remover políticas de Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="353f1-221">No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="353f1-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="353f1-222">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="353f1-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="353f1-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span><span class="sxs-lookup"><span data-stu-id="353f1-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="353f1-224">Usar o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="353f1-225">Conforme descrito anteriormente, uma política de Anexos Seguros consiste em uma política de anexo seguro e uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="353f1-226">No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente.</span><span class="sxs-lookup"><span data-stu-id="353f1-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="353f1-227">Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo seguro usando os cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="353f1-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="353f1-228">No PowerShell, primeiro você cria a política de anexo seguro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="353f1-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="353f1-229">No PowerShell, você modifica as configurações da política de anexo seguro e da regra de anexo seguro separadamente.</span><span class="sxs-lookup"><span data-stu-id="353f1-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="353f1-230">Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="353f1-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="353f1-231">Usar o PowerShell para criar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="353f1-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="353f1-232">Criar uma política de Anexos Seguros no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="353f1-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="353f1-233">Crie a política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="353f1-234">Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="353f1-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="353f1-235">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="353f1-235">**Notes**:</span></span>

- <span data-ttu-id="353f1-236">Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo seguro não associada existente a ela.</span><span class="sxs-lookup"><span data-stu-id="353f1-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="353f1-237">Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="353f1-238">Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estarão disponíveis no Centro de Conformidade e Segurança até que você crie & a política:</span><span class="sxs-lookup"><span data-stu-id="353f1-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="353f1-239">Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="353f1-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="353f1-240">Definir a prioridade da política durante a criação (_Prioridade_ ) no _\<Number\>_ cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="353f1-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="353f1-241">Uma nova política de anexo seguro que você criar no PowerShell não será visível no Centro de Conformidade e Segurança & até que você atribua a política a uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="353f1-242">Etapa 1: Usar o PowerShell para criar uma política de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="353f1-243">Para criar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="353f1-244">Este exemplo cria uma política de anexo seguro chamada Contoso All com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="353f1-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="353f1-245">Bloquear mensagens que contêm malware pela verificação de Documentos Seguros (não estamos usando o parâmetro _Action_ e o valor padrão é `Block` ).</span><span class="sxs-lookup"><span data-stu-id="353f1-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="353f1-246">O redirecionamento está habilitado, e as mensagens que contêm malware são enviadas sec-ops@contoso.com análise e investigação.</span><span class="sxs-lookup"><span data-stu-id="353f1-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="353f1-247">Se a verificação de Anexos Seguros não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="353f1-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="353f1-248">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="353f1-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="353f1-249">Etapa 2: Usar o PowerShell para criar uma regra de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="353f1-250">Para criar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="353f1-251">Este exemplo cria uma regra de anexo seguro chamada Contoso All com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="353f1-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="353f1-252">A regra é associada à política de anexo seguro chamada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="353f1-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="353f1-253">A regra se aplica a todos os destinatários no contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="353f1-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="353f1-254">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="353f1-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="353f1-255">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="353f1-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="353f1-256">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="353f1-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="353f1-257">Usar o PowerShell para exibir políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="353f1-258">Para exibir políticas de anexos seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="353f1-259">Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="353f1-260">Este exemplo retorna informações detalhadas sobre a política de anexo seguro chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="353f1-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="353f1-261">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="353f1-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="353f1-262">Usar o PowerShell para exibir regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="353f1-263">Para exibir as regras existentes de anexo seguro, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="353f1-264">Este exemplo retorna uma lista resumida de todas as regras de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="353f1-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="353f1-265">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="353f1-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="353f1-266">Este exemplo retorna informações detalhadas sobre a regra de anexo seguro chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="353f1-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="353f1-267">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="353f1-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="353f1-268">Usar o PowerShell para modificar políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="353f1-269">Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **Set-SafeAttachmentPolicy** não tem parâmetro _Name)._</span><span class="sxs-lookup"><span data-stu-id="353f1-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="353f1-270">Ao renomear uma política de Anexos Seguros no Centro de & Conformidade e Segurança, você está apenas renomeando a regra de anexo _seguro._</span><span class="sxs-lookup"><span data-stu-id="353f1-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="353f1-271">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro conforme descrito na Etapa [1: use](#step-1-use-powershell-to-create-a-safe-attachment-policy) o PowerShell para criar uma seção de política de anexo seguro anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="353f1-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="353f1-272">Para modificar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="353f1-273">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="353f1-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="353f1-274">Usar o PowerShell para modificar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="353f1-275">A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="353f1-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="353f1-276">Para habilitar ou desabilitar regras de anexo seguro existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="353f1-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="353f1-277">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Usar](#step-2-use-powershell-to-create-a-safe-attachment-rule) o PowerShell para criar uma seção de regra de anexo seguro anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="353f1-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="353f1-278">Para modificar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="353f1-279">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="353f1-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="353f1-280">Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="353f1-281">Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política de Anexos Seguros (a regra de anexo seguro e a política de anexo seguro atribuída).</span><span class="sxs-lookup"><span data-stu-id="353f1-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="353f1-282">Para habilitar ou desabilitar uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="353f1-283">Este exemplo desabilita a regra de anexo seguro chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="353f1-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="353f1-284">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="353f1-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="353f1-285">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="353f1-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="353f1-286">Usar o PowerShell para definir a prioridade de regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="353f1-287">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="353f1-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="353f1-288">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="353f1-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="353f1-289">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="353f1-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="353f1-290">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="353f1-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="353f1-291">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="353f1-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="353f1-292">Para definir a prioridade de uma regra de anexo seguro no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="353f1-293">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="353f1-293">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="353f1-294">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="353f1-294">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="353f1-295">**Observação:** para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="353f1-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="353f1-296">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="353f1-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="353f1-297">Usar o PowerShell para remover políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="353f1-298">Quando você usa o PowerShell para remover uma política de anexo seguro, a regra de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="353f1-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="353f1-299">Para remover uma política de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="353f1-300">Este exemplo remove a política de anexo seguro chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="353f1-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="353f1-301">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="353f1-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="353f1-302">Usar o PowerShell para remover regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="353f1-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="353f1-303">Quando você usa o PowerShell para remover uma regra de anexo seguro, a política de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="353f1-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="353f1-304">Para remover uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="353f1-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="353f1-305">Este exemplo remove a regra de anexo seguro chamada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="353f1-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="353f1-306">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="353f1-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="353f1-307">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="353f1-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="353f1-308">Para verificar se você criou, modificou ou removeu com êxito as políticas de Anexos Seguros, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="353f1-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="353f1-309">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="353f1-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="353f1-310">Verifique a lista de políticas, seus valores **de Status** e seus **valores de** Prioridade.</span><span class="sxs-lookup"><span data-stu-id="353f1-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="353f1-311">Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly out.</span><span class="sxs-lookup"><span data-stu-id="353f1-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="353f1-312">No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, substitua o nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="353f1-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="353f1-313">Para verificar se os Anexos Seguros estão verificando mensagens, verifique os relatórios disponíveis do Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="353f1-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="353f1-314">Para obter mais informações, consulte Exibir relatórios do [Defender para Office 365](view-reports-for-atp.md) e usar o Explorer no Centro de [Conformidade & Segurança.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="353f1-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
