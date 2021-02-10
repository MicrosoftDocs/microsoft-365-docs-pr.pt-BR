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
ms.openlocfilehash: 314f7fd882986c22adddd0c4570b4aa9f49a40f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166328"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b6a98-103">Configurar políticas de Anexos Seguros no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b6a98-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b6a98-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="b6a98-104">**Applies to**</span></span>
- [<span data-ttu-id="b6a98-105">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="b6a98-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b6a98-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6a98-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="b6a98-107">Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b6a98-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b6a98-108">Se você for um usuário de residência procurando informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="b6a98-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b6a98-109">Anexos Seguros é um recurso do [Microsoft Defender para Office 365](office-365-atp.md) que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois que eles são verificados pela proteção anti-malware no Proteção do Exchange Online [(EOP),](anti-malware-protection.md)mas antes da entrega aos destinatários.</span><span class="sxs-lookup"><span data-stu-id="b6a98-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="b6a98-110">Para obter mais informações, consulte [Anexos seguros no Microsoft Defender para Office 365.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="b6a98-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="b6a98-111">Não há nenhuma política de Anexos Seguros interna ou padrão.</span><span class="sxs-lookup"><span data-stu-id="b6a98-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="b6a98-112">Para obter a verificação de Anexos Seguros de anexos de mensagens de email, você precisa criar uma ou mais políticas de Anexos Seguros, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b6a98-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="b6a98-113">Você pode configurar políticas de Anexos Seguros no Centro de Conformidade e Segurança ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Defender para Office 365). &</span><span class="sxs-lookup"><span data-stu-id="b6a98-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="b6a98-114">Os elementos básicos de uma política de Anexos seguros são:</span><span class="sxs-lookup"><span data-stu-id="b6a98-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="b6a98-115">A política de anexo **seguro:** especifica as ações para detecções de malware desconhecidas, se é para enviar mensagens com anexos de malware para um endereço de email especificado e se a verificação de Anexos Seguros não pode ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b6a98-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="b6a98-116">**A regra de anexo seguro:** especifica os filtros de prioridade e destinatário (a quem a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="b6a98-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="b6a98-117">A diferença entre esses dois elementos não é óbvia quando você gerencia as política de Anexos seguros no Centro de Conformidade & e Segurança:</span><span class="sxs-lookup"><span data-stu-id="b6a98-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b6a98-118">Ao criar uma política de Anexos Seguros, você está criando uma regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="b6a98-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b6a98-119">Quando você modifica uma política de Anexos Seguros, as configurações relacionadas ao nome, prioridade, habilitada ou desabilitada e filtros de destinatário modificam a regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="b6a98-120">Todas as outras configurações modificam a política de anexo seguro associada.</span><span class="sxs-lookup"><span data-stu-id="b6a98-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="b6a98-121">Quando você remove uma política de Anexos Seguros, a regra de anexo seguro e a política de anexo seguro associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="b6a98-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="b6a98-122">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="b6a98-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b6a98-123">Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online ou [do EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autônomo para configurar políticas de Anexos seguros posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b6a98-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b6a98-124">Na área de configurações globais das configurações de Anexos Seguros, você configura recursos que não dependem de políticas de Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="b6a98-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="b6a98-125">Para obter instruções, confira Ativar Anexos Seguros para [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md) e Microsoft Teams e Documentos Seguros no [Microsoft 365 E5.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="b6a98-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b6a98-126">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="b6a98-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b6a98-127">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b6a98-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b6a98-128">Para ir diretamente para a **página Anexos Seguros,** use <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="b6a98-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="b6a98-129">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b6a98-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b6a98-130">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b6a98-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b6a98-131">Para fazer os procedimentos deste artigo, você precisa ter permissões:</span><span class="sxs-lookup"><span data-stu-id="b6a98-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b6a98-132">Para criar, modificar e excluir políticas de Anexos Seguros  &, você precisa ser membro dos grupos de função Gerenciamento  da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de funções Gerenciamento da Organização no Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="b6a98-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="b6a98-133">Para acesso somente leitura às políticas de Anexos Seguros, você  precisa ser membro dos grupos de função Leitor & **Global** ou Leitor de Segurança no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="b6a98-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="b6a98-134">Para obter mais informações, [consulte Permissões no Centro de conformidade e & segurança](permissions-in-the-security-and-compliance-center.md) no Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="b6a98-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="b6a98-135">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="b6a98-135">**Notes**:</span></span>

  - <span data-ttu-id="b6a98-136">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6a98-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b6a98-137">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b6a98-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="b6a98-138">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="b6a98-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b6a98-139">Para nossas configurações recomendadas para políticas de Anexos Seguros, consulte [configurações de Anexos Seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="b6a98-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="b6a98-140">Permita até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="b6a98-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="b6a98-141">Usar o Centro de Conformidade & segurança para criar políticas de Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="b6a98-142">Criar uma política de Anexo & s Seguros personalizada no Centro de Conformidade e Segurança cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="b6a98-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b6a98-143">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b6a98-144">Na página **Anexos Seguros,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="b6a98-145">O **assistente nova política de Anexos seguros** é aberto.</span><span class="sxs-lookup"><span data-stu-id="b6a98-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="b6a98-146">Na página **Nomear sua política,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b6a98-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b6a98-147">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="b6a98-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b6a98-148">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="b6a98-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b6a98-149">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b6a98-150">Na página **Configurações** exibida, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b6a98-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b6a98-151">**Resposta de malware desconhecido anexos seguros:** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b6a98-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="b6a98-152">**Off**: Normalmente, não recomendamos esse valor.</span><span class="sxs-lookup"><span data-stu-id="b6a98-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="b6a98-153">**Monitorar**</span><span class="sxs-lookup"><span data-stu-id="b6a98-153">**Monitor**</span></span>
     - <span data-ttu-id="b6a98-154">**Block:** este é o valor padrão e o valor recomendado nas políticas de segurança predefinidas Padrão [e Estrito.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b6a98-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="b6a98-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="b6a98-155">**Replace**</span></span>
     - <span data-ttu-id="b6a98-156">**Entrega Dinâmica (Recurso de Visualização)**</span><span class="sxs-lookup"><span data-stu-id="b6a98-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="b6a98-157">Esses valores são explicados nas [configurações de política de Anexos seguros.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b6a98-157">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="b6a98-158">Envie o anexo para o seguinte endereço de  **email:** para os valores de ação **Bloquear**, **Monitorar** ou Substituir , você pode selecionar Habilitar redirecionamento para enviar mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação. </span><span class="sxs-lookup"><span data-stu-id="b6a98-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="b6a98-159">A recomendação para as configurações de política Padrão e Estrito é habilitar o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="b6a98-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="b6a98-160">Para obter mais informações, consulte [configurações de Anexos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="b6a98-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="b6a98-161">Aplique a seleção acima se a verificação de anexos de **malware esgoter** ou ocorrer um erro: a ação especificada pela resposta de malware desconhecido **anexos** seguros é tomada em mensagens mesmo quando a verificação de Anexos Seguros não puder ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b6a98-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="b6a98-162">Se você selecionou essa opção, sempre selecione **Redirecionamento habilitado.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="b6a98-163">Caso contrário, as mensagens podem ser perdidas.</span><span class="sxs-lookup"><span data-stu-id="b6a98-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="b6a98-164">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b6a98-165">Na página **Aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="b6a98-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b6a98-166">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="b6a98-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b6a98-167">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b6a98-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b6a98-168">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b6a98-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="b6a98-169">Clique **em Adicionar uma condição.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-169">Click **Add a condition**.</span></span> <span data-ttu-id="b6a98-170">No menu suspenso exibido, selecione uma condição em **Aplicado se:**</span><span class="sxs-lookup"><span data-stu-id="b6a98-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="b6a98-171">**O destinatário é:** Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b6a98-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b6a98-172">**O destinatário é membro de:** Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b6a98-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b6a98-173">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="b6a98-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="b6a98-174">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b6a98-175">Clique na caixa e role pela lista de valores a selecionar.</span><span class="sxs-lookup"><span data-stu-id="b6a98-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b6a98-176">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="b6a98-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b6a98-177">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="b6a98-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b6a98-178">Para remover entradas individuais, clique **no** ícone ![ Remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="b6a98-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b6a98-179">Para remover toda a condição, clique **no** ícone ![ Remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="b6a98-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b6a98-180">Para adicionar uma condição adicional, clique **em Adicionar uma condição** e selecione um valor restante em Aplicado **se**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b6a98-181">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Exceto **se**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b6a98-182">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="b6a98-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b6a98-183">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b6a98-184">Na página **Revisar as configurações** exibida, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="b6a98-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b6a98-185">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="b6a98-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b6a98-186">Quando terminar, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="b6a98-187">Usar o Centro de Conformidade & segurança para exibir políticas de Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="b6a98-188">No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b6a98-189">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="b6a98-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="b6a98-190">Os detalhes da política aparecem em um fly out</span><span class="sxs-lookup"><span data-stu-id="b6a98-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="b6a98-191">Usar o Centro de Conformidade & Segurança para modificar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="b6a98-192">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b6a98-193">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="b6a98-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b6a98-194">Nos detalhes da política exibidos, clique em **Editar política.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="b6a98-195">As configurações disponíveis no & menu explicativo exibido são idênticas às descritas na seção Usar o Centro de Conformidade e Segurança para criar políticas de [Anexos seguros.](#use-the-security--compliance-center-to-create-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="b6a98-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="b6a98-196">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="b6a98-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="b6a98-197">Habilitar ou desabilitar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="b6a98-198">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b6a98-199">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="b6a98-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b6a98-200">Mover o alternância para a esquerda</span><span class="sxs-lookup"><span data-stu-id="b6a98-200">Move the toggle to the left</span></span> ![Desativar política](../../media/scc-toggle-off.png) <span data-ttu-id="b6a98-202">para desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="b6a98-202">to disable the policy.</span></span>

   - <span data-ttu-id="b6a98-203">Mover o alternância para a direita</span><span class="sxs-lookup"><span data-stu-id="b6a98-203">Move the toggle to the right</span></span> ![Ativar a política](../../media/scc-toggle-on.png) <span data-ttu-id="b6a98-205">para habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="b6a98-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="b6a98-206">Definir a prioridade das políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="b6a98-207">Por padrão, as políticas de Anexos Seguros têm uma prioridade baseada na ordem em que foram criadas (políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="b6a98-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="b6a98-208">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="b6a98-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b6a98-209">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="b6a98-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b6a98-210">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b6a98-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b6a98-211">As políticas de Anexos Seguros são exibidas na ordem em que são processadas (a primeira política tem **o valor** prioridade 0).</span><span class="sxs-lookup"><span data-stu-id="b6a98-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="b6a98-212">**Observação:** no Centro de Conformidade & segurança, você só pode alterar a prioridade da política de Anexos seguros depois de criar a política.</span><span class="sxs-lookup"><span data-stu-id="b6a98-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="b6a98-213">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="b6a98-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b6a98-214">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="b6a98-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="b6a98-215">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b6a98-216">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="b6a98-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b6a98-217">Nos detalhes da política exibidos, clique no botão de prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="b6a98-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="b6a98-218">A política de Anexos Seguros com o **valor** **prioridade 0** tem apenas o **botão** Diminuir prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="b6a98-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b6a98-219">A política anexos seguros com o menor valor **de** prioridade (por exemplo, **3**) tem apenas o **botão** Aumentar prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="b6a98-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b6a98-220">Se você tiver três ou mais políticas de Anexos Seguros,  as políticas  entre os valores de prioridade mais alta e mais baixa terão os botões Aumentar prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b6a98-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b6a98-221">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor prioridade.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b6a98-222">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b6a98-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="b6a98-223">Usar o Centro de Conformidade & segurança para remover políticas de Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="b6a98-224">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b6a98-225">Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="b6a98-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b6a98-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span><span class="sxs-lookup"><span data-stu-id="b6a98-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="b6a98-227">Usar o PowerShell do Exchange Online ou o PowerShell do EOP autônomo para configurar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="b6a98-228">Conforme descrito anteriormente, uma política de Anexos Seguros consiste em uma política de anexo seguro e uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="b6a98-229">No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente.</span><span class="sxs-lookup"><span data-stu-id="b6a98-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="b6a98-230">Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo seguro usando os cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="b6a98-231">No PowerShell, primeiro você cria a política de anexo seguro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="b6a98-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b6a98-232">No PowerShell, você modifica as configurações da política de anexo seguro e da regra de anexo seguro separadamente.</span><span class="sxs-lookup"><span data-stu-id="b6a98-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="b6a98-233">Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="b6a98-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="b6a98-234">Usar o PowerShell para criar políticas de Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="b6a98-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="b6a98-235">Criar uma política de Anexos Seguros no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="b6a98-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b6a98-236">Crie a política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="b6a98-237">Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="b6a98-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="b6a98-238">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="b6a98-238">**Notes**:</span></span>

- <span data-ttu-id="b6a98-239">Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo seguro existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="b6a98-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="b6a98-240">Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="b6a98-241">Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estarão disponíveis no Centro de Conformidade e Segurança até que você crie & a política:</span><span class="sxs-lookup"><span data-stu-id="b6a98-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="b6a98-242">Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="b6a98-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="b6a98-243">Definir a prioridade da política durante a criação (_Prioridade_ ) no _\<Number\>_ cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="b6a98-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="b6a98-244">Uma nova política de anexo seguro que você criar no PowerShell não será visível no Centro de Conformidade e Segurança & até que você atribua a política a uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="b6a98-245">Etapa 1: Usar o PowerShell para criar uma política de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="b6a98-246">Para criar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="b6a98-247">Este exemplo cria uma política de anexo seguro chamada Contoso All com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b6a98-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="b6a98-248">Bloquear mensagens que contêm malware pela verificação de Documentos Seguros (não estamos usando o parâmetro _Action_ e o valor padrão é `Block` ).</span><span class="sxs-lookup"><span data-stu-id="b6a98-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="b6a98-249">O redirecionamento está habilitado, e as mensagens que contêm malware são enviadas sec-ops@contoso.com análise e investigação.</span><span class="sxs-lookup"><span data-stu-id="b6a98-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="b6a98-250">Se a verificação de Anexos seguros não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="b6a98-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="b6a98-251">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="b6a98-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="b6a98-252">Etapa 2: Usar o PowerShell para criar uma regra de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="b6a98-253">Para criar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="b6a98-254">Este exemplo cria uma regra de anexo seguro chamada Contoso All com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="b6a98-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="b6a98-255">A regra é associada à política de anexo seguro chamada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="b6a98-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="b6a98-256">A regra se aplica a todos os destinatários no contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="b6a98-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="b6a98-257">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="b6a98-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="b6a98-258">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="b6a98-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="b6a98-259">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="b6a98-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="b6a98-260">Usar o PowerShell para exibir políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="b6a98-261">Para exibir as políticas de anexos seguros existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b6a98-262">Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="b6a98-263">Este exemplo retorna informações detalhadas sobre a política de anexo seguro chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b6a98-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b6a98-264">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="b6a98-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="b6a98-265">Usar o PowerShell para exibir regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="b6a98-266">Para exibir as regras existentes de anexo seguro, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b6a98-267">Este exemplo retorna uma lista resumida de todas as regras de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="b6a98-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="b6a98-268">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="b6a98-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="b6a98-269">Este exemplo retorna informações detalhadas sobre a regra de anexo seguro chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b6a98-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b6a98-270">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="b6a98-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="b6a98-271">Usar o PowerShell para modificar políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="b6a98-272">Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **Set-SafeAttachmentPolicy** não tem parâmetro _Name)._</span><span class="sxs-lookup"><span data-stu-id="b6a98-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b6a98-273">Ao renomear uma política de Anexos Seguros no Centro de & Conformidade e Segurança, você está apenas renomeando a regra de anexo _seguro._</span><span class="sxs-lookup"><span data-stu-id="b6a98-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="b6a98-274">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro conforme descrito na Etapa [1: use](#step-1-use-powershell-to-create-a-safe-attachment-policy) o PowerShell para criar uma seção de política de anexo seguro anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b6a98-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="b6a98-275">Para modificar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b6a98-276">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="b6a98-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="b6a98-277">Usar o PowerShell para modificar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="b6a98-278">A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="b6a98-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b6a98-279">Para habilitar ou desabilitar regras de anexo seguro existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="b6a98-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="b6a98-280">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Usar](#step-2-use-powershell-to-create-a-safe-attachment-rule) o PowerShell para criar uma seção de regra de anexo seguro anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b6a98-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="b6a98-281">Para modificar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b6a98-282">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="b6a98-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="b6a98-283">Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="b6a98-284">Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política de Anexos Seguros (a regra de anexo seguro e a política de anexo seguro atribuída).</span><span class="sxs-lookup"><span data-stu-id="b6a98-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="b6a98-285">Para habilitar ou desabilitar uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="b6a98-286">Este exemplo desabilita a regra de anexo seguro chamada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b6a98-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="b6a98-287">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="b6a98-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="b6a98-288">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="b6a98-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="b6a98-289">Usar o PowerShell para definir a prioridade de regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="b6a98-290">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="b6a98-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b6a98-291">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="b6a98-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b6a98-292">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="b6a98-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b6a98-293">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="b6a98-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b6a98-294">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="b6a98-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b6a98-295">Para definir a prioridade de uma regra de anexo seguro no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b6a98-296">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="b6a98-296">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="b6a98-297">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="b6a98-297">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b6a98-298">**Observação:** para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="b6a98-299">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="b6a98-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="b6a98-300">Usar o PowerShell para remover políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="b6a98-301">Quando você usa o PowerShell para remover uma política de anexo seguro, a regra de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="b6a98-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="b6a98-302">Para remover uma política de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b6a98-303">Este exemplo remove a política de anexo seguro chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="b6a98-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b6a98-304">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="b6a98-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="b6a98-305">Usar o PowerShell para remover regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="b6a98-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="b6a98-306">Quando você usa o PowerShell para remover uma regra de anexo seguro, a política de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="b6a98-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="b6a98-307">Para remover uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b6a98-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="b6a98-308">Este exemplo remove a regra de anexo seguro chamada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b6a98-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="b6a98-309">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="b6a98-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b6a98-310">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="b6a98-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="b6a98-311">Para verificar se você criou, modificou ou removeu com êxito as políticas de Anexos Seguros, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b6a98-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="b6a98-312">No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de Ameaças anexos seguros \>  \> **da ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6a98-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="b6a98-313">Verifique a lista de políticas, seus **valores de Status** e seus valores **de** Prioridade.</span><span class="sxs-lookup"><span data-stu-id="b6a98-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b6a98-314">Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly out.</span><span class="sxs-lookup"><span data-stu-id="b6a98-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="b6a98-315">No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, substitua o nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="b6a98-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="b6a98-316">Para verificar se os Anexos Seguros estão verificando mensagens, verifique os relatórios disponíveis do Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6a98-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="b6a98-317">Para obter mais informações, consulte Exibir relatórios do [Defender para Office 365](view-reports-for-atp.md) e usar o Explorer no Centro de [Conformidade & Segurança.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="b6a98-317">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
