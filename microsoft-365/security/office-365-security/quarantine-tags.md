---
title: Marcas de quarentena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Os administradores podem aprender a usar marcas de quarentena para controlar o que os usuários podem fazer com suas mensagens em quarentena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f18ad6ce1c8b12d38aef377ab663ca679a703e5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928897"
---
# <a name="quarantine-tags"></a><span data-ttu-id="7948e-103">Marcas de quarentena</span><span class="sxs-lookup"><span data-stu-id="7948e-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="7948e-104">Os recursos descritos neste artigo estão atualmente na visualização, não estão disponíveis para todos e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="7948e-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="7948e-105">As marcas de quarentena no Proteção do Exchange Online (EOP) permitem que os administradores controlem o que os usuários podem fazer com suas mensagens em quarentena com base em como a mensagem chegou em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="7948e-106">O EOP tem permitido ou impedido tradicionalmente determinados níveis de interatividade para mensagens em quarentena e em notificações de [spam para o usuário final.](use-spam-notifications-to-release-and-report-quarantined-messages.md) [](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="7948e-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="7948e-107">Por exemplo, os usuários finais podem exibir e liberar mensagens que foram colocadas em quarentena pela filtragem anti-spam como spam ou em massa, mas não podem exibir ou liberar mensagens que foram colocadas em quarentena como phishing de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="7948e-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="7948e-108">Para [recursos](#step-2-assign-a-quarantine-tag-to-supported-features)de proteção com suporte, as marcas de quarentena especificam o que os usuários têm permissão para fazer em mensagens de notificação de spam do usuário final e em suas mensagens em quarentena (mensagens em que o usuário é um destinatário).</span><span class="sxs-lookup"><span data-stu-id="7948e-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="7948e-109">As marcas de quarentena padrão são atribuídas automaticamente para impor os recursos históricos para usuários finais em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="7948e-110">Ou você pode criar e atribuir marcas de quarentena personalizadas para permitir ou impedir que os usuários finais executam ações específicas em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="7948e-111">As permissões individuais são combinadas nos seguintes grupos de permissões predefinidos:</span><span class="sxs-lookup"><span data-stu-id="7948e-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="7948e-112">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="7948e-112">No access</span></span>
- <span data-ttu-id="7948e-113">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="7948e-113">Limited access</span></span>
- <span data-ttu-id="7948e-114">Acesso total</span><span class="sxs-lookup"><span data-stu-id="7948e-114">Full access</span></span>

<span data-ttu-id="7948e-115">As permissões individuais disponíveis e o que está incluído ou não nos grupos de permissões predefinidos são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="7948e-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="7948e-116">Permissão</span><span class="sxs-lookup"><span data-stu-id="7948e-116">Permission</span></span>|<span data-ttu-id="7948e-117">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="7948e-117">No access</span></span>|<span data-ttu-id="7948e-118">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="7948e-118">Limited access</span></span>|<span data-ttu-id="7948e-119">Acesso total</span><span class="sxs-lookup"><span data-stu-id="7948e-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="7948e-120">**Permitir remetente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="7948e-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="7948e-122">**Bloquear remetente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="7948e-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="7948e-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="7948e-125">**Delete** (_PermissionToDelete_)</span></span>||![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="7948e-128">**Visualização** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="7948e-128">**Preview** (_PermissionToPreview_)</span></span>||![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="7948e-131">**Permitir que os destinatários liberem uma mensagem da** quarentena (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="7948e-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="7948e-133">**Permitir que os destinatários solicitem que uma mensagem seja liberada da** quarentena (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="7948e-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Marca de seleção](../../media/checkmark.png)||
|

<span data-ttu-id="7948e-135">Se você não gosta das permissões padrão nos grupos de permissões predefinidos, poderá usar permissões personalizadas ao criar ou modificar marcas de quarentena personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7948e-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="7948e-136">Para obter mais informações sobre o que cada permissão faz, consulte a seção Detalhes da permissão [de marca](#quarantine-tag-permission-details) de quarentena mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7948e-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="7948e-137">Você cria e atribui marcas de quarentena no Centro de Conformidade e Segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com Caixas de Correio do Exchange Online; PowerShell do EOP autônomo em organizações do EOP sem caixas de correio do Exchange Online). &</span><span class="sxs-lookup"><span data-stu-id="7948e-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7948e-138">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="7948e-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7948e-139">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7948e-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7948e-140">Para ir diretamente para a página **de marcas de** quarentena, abra <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="7948e-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="7948e-141">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7948e-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7948e-142">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7948e-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7948e-143">Para exibir, criar, modificar ou remover marcas de quarentena  [&,](permissions-in-the-security-and-compliance-center.md)  você precisa ser membro das funções de Administrador de Segurança ou Gerenciamento da Organização no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="7948e-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="7948e-144">Etapa 1: Criar marcas de quarentena no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="7948e-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="7948e-145">No Centro de Conformidade & segurança,  vá para Política de gerenciamento de ameaças e selecione \>  Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="7948e-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="7948e-146">Na página **Marcas de quarentena,** selecione **Adicionar marca personalizada.**</span><span class="sxs-lookup"><span data-stu-id="7948e-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="7948e-147">O **assistente de nova** marca é aberto.</span><span class="sxs-lookup"><span data-stu-id="7948e-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="7948e-148">Na página **Nome da** Marca, insira um nome breve, mas exclusivo, no campo **Nome da** Marca.</span><span class="sxs-lookup"><span data-stu-id="7948e-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="7948e-149">Você precisará identificar e selecionar a marca pelo nome nas próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="7948e-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="7948e-150">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7948e-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7948e-151">Na página **Acesso à mensagem do** Destinatário, selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7948e-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="7948e-152">**Sem acesso**</span><span class="sxs-lookup"><span data-stu-id="7948e-152">**No access**</span></span>
   - <span data-ttu-id="7948e-153">**Acesso limitado**</span><span class="sxs-lookup"><span data-stu-id="7948e-153">**Limited access**</span></span>
   - <span data-ttu-id="7948e-154">**Acesso total**</span><span class="sxs-lookup"><span data-stu-id="7948e-154">**Full access**</span></span>

   <span data-ttu-id="7948e-155">As permissões individuais incluídas nesses grupos de permissões são descritas anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7948e-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="7948e-156">Para especificar permissões personalizadas, selecione **Definir acesso específico (Avançado)** e de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7948e-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="7948e-157">**Selecione a preferência de ação de** lançamento: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7948e-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="7948e-158">**Nenhuma ação de** lançamento: este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7948e-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="7948e-159">**Permitir que os destinatários liberem uma mensagem da quarentena**</span><span class="sxs-lookup"><span data-stu-id="7948e-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="7948e-160">**Permitir que os destinatários solicitem que uma mensagem seja liberada da quarentena**</span><span class="sxs-lookup"><span data-stu-id="7948e-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="7948e-161">**Selecione ações adicionais que os destinatários podem tomar** em mensagens em quarentena: selecione alguns, todos ou nenhum dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7948e-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="7948e-162">**Delete**</span><span class="sxs-lookup"><span data-stu-id="7948e-162">**Delete**</span></span>
       - <span data-ttu-id="7948e-163">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="7948e-163">**Preview**</span></span>
       - <span data-ttu-id="7948e-164">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-164">**Allow sender**</span></span>
       - <span data-ttu-id="7948e-165">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-165">**Block sender**</span></span>

   <span data-ttu-id="7948e-166">Essas permissões e seus efeitos nas mensagens em quarentena e nas [](#quarantine-tag-permission-details) notificações de spam do usuário final são descritos na seção Detalhes da permissão de marca de quarentena mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7948e-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="7948e-167">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7948e-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7948e-168">Na página **Resumo** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="7948e-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="7948e-169">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="7948e-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="7948e-170">Quando terminar, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="7948e-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="7948e-171">Clique **em Feito** na página de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="7948e-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="7948e-172">Agora você está pronto para atribuir a marca de quarentena a um recurso de quarentena, conforme descrito na [seção Etapa 2.](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="7948e-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="7948e-173">Criar marcas de quarentena no PowerShell</span><span class="sxs-lookup"><span data-stu-id="7948e-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="7948e-174">Se você preferir usar o PowerShell para criar marcas de quarentena, conecte-se ao PowerShell do Exchange Online ou ao PowerShell da Proteção do Exchange Online e use o cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="7948e-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="7948e-175">Você tem dois métodos diferentes para escolher:</span><span class="sxs-lookup"><span data-stu-id="7948e-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="7948e-176">Use o _parâmetro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="7948e-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="7948e-177">Use o _parâmetro EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="7948e-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="7948e-178">Esses métodos são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="7948e-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="7948e-179">Usar o parâmetro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="7948e-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="7948e-180">Para criar uma marca de quarentena usando o _parâmetro EndUserQuarantinePermissionsValue,_ use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7948e-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="7948e-181">O _parâmetro EndUserQuarantinePermissionsValue_ usa um valor decimal convertido de um valor binário.</span><span class="sxs-lookup"><span data-stu-id="7948e-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="7948e-182">O valor binário corresponde às permissões de quarentena de usuário final disponíveis em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="7948e-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="7948e-183">Para cada permissão, o valor 1 é igual a True e o valor 0 é igual a False.</span><span class="sxs-lookup"><span data-stu-id="7948e-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="7948e-184">A ordem e os valores necessários para cada permissão individual em grupos de permissões predefinidos são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="7948e-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="7948e-185">Permissão</span><span class="sxs-lookup"><span data-stu-id="7948e-185">Permission</span></span>|<span data-ttu-id="7948e-186">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="7948e-186">No access</span></span>|<span data-ttu-id="7948e-187">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="7948e-187">Limited access</span></span>|<span data-ttu-id="7948e-188">Acesso total</span><span class="sxs-lookup"><span data-stu-id="7948e-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="7948e-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="7948e-189">PermissionToAllowSender</span></span>|<span data-ttu-id="7948e-190">0</span><span class="sxs-lookup"><span data-stu-id="7948e-190">0</span></span>|<span data-ttu-id="7948e-191">0</span><span class="sxs-lookup"><span data-stu-id="7948e-191">0</span></span>|<span data-ttu-id="7948e-192">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-192">1</span></span>|
|<span data-ttu-id="7948e-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="7948e-193">PermissionToBlockSender</span></span>|<span data-ttu-id="7948e-194">0</span><span class="sxs-lookup"><span data-stu-id="7948e-194">0</span></span>|<span data-ttu-id="7948e-195">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-195">1</span></span>|<span data-ttu-id="7948e-196">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-196">1</span></span>|
|<span data-ttu-id="7948e-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="7948e-197">PermissionToDelete</span></span>|<span data-ttu-id="7948e-198">0</span><span class="sxs-lookup"><span data-stu-id="7948e-198">0</span></span>|<span data-ttu-id="7948e-199">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-199">1</span></span>|<span data-ttu-id="7948e-200">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-200">1</span></span>|
|<span data-ttu-id="7948e-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7948e-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="7948e-202">0</span><span class="sxs-lookup"><span data-stu-id="7948e-202">0</span></span>|<span data-ttu-id="7948e-203">0</span><span class="sxs-lookup"><span data-stu-id="7948e-203">0</span></span>|<span data-ttu-id="7948e-204">0</span><span class="sxs-lookup"><span data-stu-id="7948e-204">0</span></span>|
|<span data-ttu-id="7948e-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="7948e-205">PermissionToPreview</span></span>|<span data-ttu-id="7948e-206">0</span><span class="sxs-lookup"><span data-stu-id="7948e-206">0</span></span>|<span data-ttu-id="7948e-207">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-207">1</span></span>|<span data-ttu-id="7948e-208">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-208">1</span></span>|
|<span data-ttu-id="7948e-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7948e-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="7948e-210">0</span><span class="sxs-lookup"><span data-stu-id="7948e-210">0</span></span>|<span data-ttu-id="7948e-211">0</span><span class="sxs-lookup"><span data-stu-id="7948e-211">0</span></span>|<span data-ttu-id="7948e-212">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-212">1</span></span>|
|<span data-ttu-id="7948e-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7948e-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="7948e-214">0</span><span class="sxs-lookup"><span data-stu-id="7948e-214">0</span></span>|<span data-ttu-id="7948e-215">1 </span><span class="sxs-lookup"><span data-stu-id="7948e-215">1</span></span>|<span data-ttu-id="7948e-216">0</span><span class="sxs-lookup"><span data-stu-id="7948e-216">0</span></span>|
|<span data-ttu-id="7948e-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7948e-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="7948e-218">0</span><span class="sxs-lookup"><span data-stu-id="7948e-218">0</span></span>|<span data-ttu-id="7948e-219">0</span><span class="sxs-lookup"><span data-stu-id="7948e-219">0</span></span>|<span data-ttu-id="7948e-220">0</span><span class="sxs-lookup"><span data-stu-id="7948e-220">0</span></span>|
|<span data-ttu-id="7948e-221">Valor binário</span><span class="sxs-lookup"><span data-stu-id="7948e-221">Binary value</span></span>|<span data-ttu-id="7948e-222">00000000</span><span class="sxs-lookup"><span data-stu-id="7948e-222">00000000</span></span>|<span data-ttu-id="7948e-223">01101010</span><span class="sxs-lookup"><span data-stu-id="7948e-223">01101010</span></span>|<span data-ttu-id="7948e-224">11101100</span><span class="sxs-lookup"><span data-stu-id="7948e-224">11101100</span></span>|
|<span data-ttu-id="7948e-225">Valor decimal a ser usado</span><span class="sxs-lookup"><span data-stu-id="7948e-225">Decimal value to use</span></span>|<span data-ttu-id="7948e-226">0</span><span class="sxs-lookup"><span data-stu-id="7948e-226">0</span></span>|<span data-ttu-id="7948e-227">106</span><span class="sxs-lookup"><span data-stu-id="7948e-227">106</span></span>|<span data-ttu-id="7948e-228">236</span><span class="sxs-lookup"><span data-stu-id="7948e-228">236</span></span>|

<span data-ttu-id="7948e-229"><sup>\*</sup> Atualmente, esse valor é sempre 0.</span><span class="sxs-lookup"><span data-stu-id="7948e-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="7948e-230">Para PermissionToViewHeader, o valor 0 não oculta o botão Exibir o **header** da mensagem nos detalhes da mensagem em quarentena (o botão está sempre disponível).</span><span class="sxs-lookup"><span data-stu-id="7948e-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="7948e-231"><sup>\*\*</sup> Não de definir esses dois valores como 1.</span><span class="sxs-lookup"><span data-stu-id="7948e-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="7948e-232">De definir um como 1 e o outro como 0 ou definir ambos como 0.</span><span class="sxs-lookup"><span data-stu-id="7948e-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="7948e-233">Este exemplo cria um novo nome de marca de quarentena NoAccess que atribui as permissões Sem acesso conforme descrito na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="7948e-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="7948e-234">Para permissões de acesso limitado, use o valor 106.</span><span class="sxs-lookup"><span data-stu-id="7948e-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="7948e-235">Para permissões de acesso total, use o valor 236.</span><span class="sxs-lookup"><span data-stu-id="7948e-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="7948e-236">Para permissões personalizadas, use a tabela anterior para obter o valor binário que corresponde às permissões que você deseja.</span><span class="sxs-lookup"><span data-stu-id="7948e-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="7948e-237">Converta o valor binário em um valor decimal e use o valor decimal para o parâmetro _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="7948e-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="7948e-238">Para informações detalhadas de sintaxes e de parâmetros, [consulte New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="7948e-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="7948e-239">Usar o parâmetro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="7948e-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="7948e-240">Para criar uma marca de quarentena usando o _parâmetro EndUserQuarantinePermissionsValue,_ faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7948e-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="7948e-241">R.</span><span class="sxs-lookup"><span data-stu-id="7948e-241">A.</span></span> <span data-ttu-id="7948e-242">Armazene um objeto de permissões de quarentena em uma variável usando o cmdlet **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="7948e-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="7948e-243">B.</span><span class="sxs-lookup"><span data-stu-id="7948e-243">B.</span></span> <span data-ttu-id="7948e-244">Use a variável _como o valor EndUserQuarantinePermissions_ no **comando New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="7948e-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="7948e-245">Etapa A: Armazenar um objeto de permissões de quarentena em uma variável</span><span class="sxs-lookup"><span data-stu-id="7948e-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="7948e-246">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7948e-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="7948e-247">O valor padrão para qualquer parâmetro não usado é, portanto, você só precisa usar os parâmetros onde deseja `$false` definir o valor como `$true` .</span><span class="sxs-lookup"><span data-stu-id="7948e-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="7948e-248">Os exemplos a seguir mostram como criar objetos de permissão que correspondem aos grupos de permissões predefinidos:</span><span class="sxs-lookup"><span data-stu-id="7948e-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="7948e-249">**Sem acesso:**</span><span class="sxs-lookup"><span data-stu-id="7948e-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="7948e-250">**Acesso limitado:**</span><span class="sxs-lookup"><span data-stu-id="7948e-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="7948e-251">**Acesso completo**:</span><span class="sxs-lookup"><span data-stu-id="7948e-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="7948e-252">Para ver os valores que você definiu, execute o nome da variável como um comando (por exemplo, execute o comando `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="7948e-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="7948e-253">Para permissões personalizadas, não de definir os parâmetros _PermissionToRelease_ e _PermissionToRequestRelease_ como `$true` .</span><span class="sxs-lookup"><span data-stu-id="7948e-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="7948e-254">De definir um `$true` para e deixar o outro como , ou deixe ambos como `$false` `$false` .</span><span class="sxs-lookup"><span data-stu-id="7948e-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="7948e-255">Você também pode modificar uma variável de objeto de permissões existente depois de criar, mas antes de usá-la usando o cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="7948e-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="7948e-256">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) e [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="7948e-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="7948e-257">Etapa B: Usar a variável no comando New-QuarantineTag comando</span><span class="sxs-lookup"><span data-stu-id="7948e-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="7948e-258">Depois de criar e armazenar o objeto permissions em uma variável, use a variável para o valor do parâmetro _EndUserQuarantinePermission_ no seguinte comando **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="7948e-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="7948e-259">Este exemplo cria uma nova marca de quarentena chamada LimitedAccess usando o objeto permissions que foi descrito e `$LimitedAccess` criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="7948e-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="7948e-260">Para informações detalhadas de sintaxes e de parâmetros, [consulte New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="7948e-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="7948e-261">Etapa 2: Atribuir uma marca de quarentena aos recursos com suporte</span><span class="sxs-lookup"><span data-stu-id="7948e-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="7948e-262">Nos _recursos de proteção_ com suporte que coloca em quarentena mensagens ou arquivos (automaticamente ou como uma ação configurável), você pode atribuir uma marca de quarentena às ações de quarentena disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7948e-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="7948e-263">Os recursos que coloca as mensagens em quarentena e a disponibilidade de marcas de quarentena são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="7948e-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="7948e-264">Recurso</span><span class="sxs-lookup"><span data-stu-id="7948e-264">Feature</span></span>|<span data-ttu-id="7948e-265">Marcas de quarentena suportadas?</span><span class="sxs-lookup"><span data-stu-id="7948e-265">Quarantine tags supported?</span></span>|<span data-ttu-id="7948e-266">Marcas de quarentena padrão usadas</span><span class="sxs-lookup"><span data-stu-id="7948e-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="7948e-267">[Políticas anti-spam:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7948e-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="7948e-268">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="7948e-269">**Spam de alta confiança** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="7948e-270">**Email de phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="7948e-271">**Email de phishing de** alta confiança (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="7948e-272">**Email em** massa (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="7948e-273">Sim</span><span class="sxs-lookup"><span data-stu-id="7948e-273">Yes</span></span>|<ul><li><span data-ttu-id="7948e-274">DefaultSpamTag (Acesso completo)</span><span class="sxs-lookup"><span data-stu-id="7948e-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="7948e-275">DefaultHighConfSpamTag (Acesso completo)</span><span class="sxs-lookup"><span data-stu-id="7948e-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="7948e-276">DefaultPhishTag (Acesso completo)</span><span class="sxs-lookup"><span data-stu-id="7948e-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="7948e-277">DefaultHighConfPhishTag (Sem acesso)</span><span class="sxs-lookup"><span data-stu-id="7948e-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="7948e-278">DefaultBulkTag (Acesso completo)</span><span class="sxs-lookup"><span data-stu-id="7948e-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="7948e-279">Políticas anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="7948e-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="7948e-280">[Proteção de inteligência contra spoof](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="7948e-281">[Proteção contra representação:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7948e-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="7948e-282">**Se o email for enviado por um usuário personificado** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="7948e-283">**Se o email for enviado por um domínio personificado** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="7948e-284">**Inteligência de caixa de correio** \> **Se o email for enviado por um usuário personificado** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="7948e-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="7948e-285">Não</span><span class="sxs-lookup"><span data-stu-id="7948e-285">No</span></span>|<span data-ttu-id="7948e-286">n/d</span><span class="sxs-lookup"><span data-stu-id="7948e-286">n/a</span></span>|
|<span data-ttu-id="7948e-287">[Políticas anti-malware:](configure-anti-malware-policies.md)todas as mensagens detectadas ficam sempre em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="7948e-288">Não</span><span class="sxs-lookup"><span data-stu-id="7948e-288">No</span></span>|<span data-ttu-id="7948e-289">n/d</span><span class="sxs-lookup"><span data-stu-id="7948e-289">n/a</span></span>|
|[<span data-ttu-id="7948e-290">Anexos seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7948e-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="7948e-291">Não</span><span class="sxs-lookup"><span data-stu-id="7948e-291">No</span></span>|<span data-ttu-id="7948e-292">n/d</span><span class="sxs-lookup"><span data-stu-id="7948e-292">n/a</span></span>|
|<span data-ttu-id="7948e-293">[Regras de fluxo de](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) emails (também conhecidas como regras de transporte) com a ação: Entregar a mensagem para a **quarentena** hospedada (_Quarentena_).</span><span class="sxs-lookup"><span data-stu-id="7948e-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="7948e-294">Não</span><span class="sxs-lookup"><span data-stu-id="7948e-294">No</span></span>|<span data-ttu-id="7948e-295">n/d</span><span class="sxs-lookup"><span data-stu-id="7948e-295">n/a</span></span>|
|

<span data-ttu-id="7948e-296"><sup>\*</sup> As configurações de proteção contra representação estão disponíveis apenas em políticas anti-phishing no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="7948e-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="7948e-297">Se você estiver satisfeito com as permissões de usuário final fornecidas pelas marcas de quarentena padrão, você não precisa fazer nada.</span><span class="sxs-lookup"><span data-stu-id="7948e-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="7948e-298">Se você quiser personalizar os recursos do usuário final (botões disponíveis) nas notificações de spam do usuário final ou em detalhes da mensagem em quarentena, poderá atribuir uma marca de quarentena personalizada.</span><span class="sxs-lookup"><span data-stu-id="7948e-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="7948e-299">Atribuir marcas de quarentena em políticas anti-spam no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="7948e-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="7948e-300">Instruções completas para criar e modificar políticas anti-spam são descritas em [Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7948e-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="7948e-301">No Centro de Conformidade & segurança, vá para **Política** de gerenciamento de ameaças e \>  \> selecione **Anti-spam.**</span><span class="sxs-lookup"><span data-stu-id="7948e-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="7948e-302">Ou <https://protection.office.com/antispam> abra.</span><span class="sxs-lookup"><span data-stu-id="7948e-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="7948e-303">Encontre e selecione uma política anti-spam existente para editar ou crie uma nova política anti-spam.</span><span class="sxs-lookup"><span data-stu-id="7948e-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="7948e-304">No flyout de detalhes da política, expanda a seção **Spam e ações em massa.**</span><span class="sxs-lookup"><span data-stu-id="7948e-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="7948e-305">Se você tiver  selecionado a mensagem de quarentena para a  ação de um veredito de filtragem de spam disponível, a caixa aplicar a marca de política de quarentena estará disponível para você selecionar a marca de quarentena para esse veredito.</span><span class="sxs-lookup"><span data-stu-id="7948e-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="7948e-306">**Observação:** quando você cria uma nova política, um valor de marca de quarentena em branco para um veredito de filtragem de spam indica que a marca de quarentena padrão para esse veredito é usada.</span><span class="sxs-lookup"><span data-stu-id="7948e-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="7948e-307">Quando você edita a política posteriormente, os valores em branco são substituídos pelos nomes de marcas de quarentena padrão reais, conforme descrito na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="7948e-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Colocar as seleções de marca em quarentena em uma política anti-spam](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="7948e-309">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7948e-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="7948e-310">Atribuir marcas de quarentena em políticas anti-spam no PowerShell</span><span class="sxs-lookup"><span data-stu-id="7948e-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="7948e-311">Se você preferir usar o PowerShell para atribuir marcas de quarentena em políticas anti-spam, conecte-se ao PowerShell do Exchange Online ou ao PowerShell da Proteção do Exchange Online e use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7948e-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="7948e-312">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="7948e-312">**Notes**:</span></span>

- <span data-ttu-id="7948e-313">O valor padrão para o parâmetro _HighConfidencePhishAction_ é Quarantine, portanto, você não precisa definir a ação Quarentena para detecções de phishing de alta confiança em novas políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="7948e-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="7948e-314">Para todos os outros vereditos de filtragem de spam em políticas anti-spam novas ou existentes, a marca de quarentena só será efetiva se o valor da ação for Quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="7948e-315">Para ver os valores de ação em políticas anti-spam existentes, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7948e-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="7948e-316">Para obter informações sobre os valores de ação padrão e os valores de ação recomendados para Padrão e Estrito, consulte as configurações de política [anti-spam do EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="7948e-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="7948e-317">Um veredito de filtragem de spam sem um parâmetro de marca de quarentena correspondente significa que a marca de [quarentena](#step-2-assign-a-quarantine-tag-to-supported-features) padrão para esse veredito é usada.</span><span class="sxs-lookup"><span data-stu-id="7948e-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="7948e-318">Você só precisa substituir uma marca de quarentena padrão por uma marca de quarentena personalizada se quiser alterar os recursos padrão do usuário final em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="7948e-319">Uma nova política anti-spam no PowerShell exige uma política de filtro de spam (configurações) usando o cmdlet **New-HostedContentFilterPolicy** e uma nova regra de filtro de spam (filtros de destinatário) usando o cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="7948e-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="7948e-320">Para obter instruções, [confira Usar o PowerShell para criar políticas anti-spam.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="7948e-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="7948e-321">Este exemplo cria uma nova política de filtro de spam chamada Departamento de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7948e-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="7948e-322">A ação para todos os vereditos de filtragem de spam está definida como Quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="7948e-323">A marca de quarentena personalizada chamada NoAccess que atribui Nenhuma permissão de acesso  substitui qualquer marca de quarentena padrão que ainda não atribua Nenhuma permissão de acesso por padrão. </span><span class="sxs-lookup"><span data-stu-id="7948e-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="7948e-324">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="7948e-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="7948e-325">Este exemplo modifica a política de filtro de spam existente chamada Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="7948e-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="7948e-326">A ação para o veredito de quarentena de spam é definida como Quarentena, e a marca de quarentena personalizada chamada NoAccess é atribuída.</span><span class="sxs-lookup"><span data-stu-id="7948e-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="7948e-327">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="7948e-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="7948e-328">Definir configurações globais de notificação de quarentena no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="7948e-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="7948e-329">As configurações globais para marcas de quarentena permitem que você personalize as notificações de spam do usuário final enviadas aos destinatários das mensagens que foram colocadas em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="7948e-330">Para obter mais informações sobre essas notificações, consulte [Notificações de spam para o usuário final.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="7948e-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="7948e-331">No Centro de Conformidade & segurança,  vá para Política de gerenciamento de ameaças e selecione \>  Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="7948e-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="7948e-332">Na página **Marcas de quarentena,** selecione **Configurações globais.**</span><span class="sxs-lookup"><span data-stu-id="7948e-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="7948e-333">No menu **desdopo de** configurações de notificação de quarentena que é aberto, de configure algumas ou todas as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7948e-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="7948e-334">**Use o logotipo da minha** empresa: selecione essa opção para substituir o logotipo padrão da Microsoft que está sendo usado na parte superior das notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="7948e-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="7948e-335">Antes de fazer isso, você precisa seguir as instruções em Personalizar o tema do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) da sua organização para carregar seu logotipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="7948e-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="7948e-336">A captura de tela a seguir mostra um logotipo personalizado em uma notificação de spam do usuário final:</span><span class="sxs-lookup"><span data-stu-id="7948e-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Um logotipo personalizado em uma notificação de spam do usuário final](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="7948e-338">**Escolher idioma:** as notificações de spam do usuário final já estão localizadas com base nas configurações de idioma do destinatário.</span><span class="sxs-lookup"><span data-stu-id="7948e-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="7948e-339">Você pode especificar texto personalizado em idiomas diferentes para os valores **nome de** exibição e aviso de isenção **de** responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="7948e-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="7948e-340">Selecione pelo menos um idioma na primeira caixa de idioma e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7948e-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="7948e-341">Você pode selecionar vários idiomas clicando em **Adicionar** após cada um deles.</span><span class="sxs-lookup"><span data-stu-id="7948e-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="7948e-342">Uma caixa de idioma de seção mostra todos os idiomas que você selecionou:</span><span class="sxs-lookup"><span data-stu-id="7948e-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Idiomas selecionados na caixa de segundo idioma nas configurações globais de notificação de quarentena de marcas de quarentena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="7948e-344">**Nome para** exibição: personalize o nome de exibição do remetente usado nas notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="7948e-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="7948e-345">Para cada idioma que você adicionou, selecione o idioma na segunda caixa de idioma (não clique  no X) e insira o valor de texto que deseja na caixa Nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="7948e-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="7948e-346">A captura de tela a seguir mostra o nome de exibição personalizado em uma notificação de spam do usuário final:</span><span class="sxs-lookup"><span data-stu-id="7948e-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Um nome de exibição de remetente personalizado em uma notificação de spam para o usuário final](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="7948e-348">**Aviso de isenção** de responsabilidade: adicione um aviso de isenção de responsabilidade personalizado na parte inferior das notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="7948e-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="7948e-349">O texto localizado, **um aviso de isenção de responsabilidade** da sua organização: é sempre incluído primeiro, seguido pelo texto especificado.</span><span class="sxs-lookup"><span data-stu-id="7948e-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="7948e-350">Para cada idioma que você adicionou, selecione o idioma na segunda caixa de idioma (não clique no X) e insira o valor de texto que você deseja na caixa de aviso **de** isenção de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="7948e-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="7948e-351">A captura de tela a seguir mostra o aviso de isenção de responsabilidade personalizado em uma notificação de spam para o usuário final:</span><span class="sxs-lookup"><span data-stu-id="7948e-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Um aviso de isenção de responsabilidade personalizado na parte inferior de uma notificação de spam para o usuário final](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="7948e-353">Exibir marcas de quarentena no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="7948e-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="7948e-354">No Centro de Conformidade & segurança,  vá para Política de gerenciamento de ameaças e selecione \>  Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="7948e-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="7948e-355">Para exibir as configurações de marcas de quarentena personalizadas ou integrados, selecione a marca de quarentena na lista (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="7948e-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="7948e-356">Para exibir as configurações globais, selecione **Configurações globais**</span><span class="sxs-lookup"><span data-stu-id="7948e-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="7948e-357">Exibir marcas de quarentena no PowerShell</span><span class="sxs-lookup"><span data-stu-id="7948e-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="7948e-358">Se você preferir usar o PowerShell para exibir marcas de quarentena, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7948e-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="7948e-359">Para exibir uma lista resumida de todas as marcas personalizadas ou criadas, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7948e-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="7948e-360">Para exibir as configurações de marcas de quarentena personalizadas ou integrados, substitua pelo nome da marca de quarentena e \<TagName\> execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7948e-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="7948e-361">Para exibir as configurações globais, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7948e-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="7948e-362">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="7948e-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="7948e-363">Remover marcas de quarentena no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="7948e-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="7948e-364">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="7948e-364">**Notes**:</span></span>

- <span data-ttu-id="7948e-365">Não é possível remover marcas de quarentena integrados.</span><span class="sxs-lookup"><span data-stu-id="7948e-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="7948e-366">Antes de remover uma marca de quarentena personalizada, verifique se ela não está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="7948e-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="7948e-367">Por exemplo, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7948e-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="7948e-368">Se a marca de quarentena estiver sendo usada, [substitua a marca de](#step-2-assign-a-quarantine-tag-to-supported-features) quarentena atribuída antes de removê-la.</span><span class="sxs-lookup"><span data-stu-id="7948e-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="7948e-369">No Centro de Conformidade & segurança,  vá para Política de gerenciamento de ameaças e selecione \>  Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="7948e-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="7948e-370">Na página **Marcas de quarentena,** selecione a marca de quarentena personalizada que você deseja remover e clique em **Excluir marca.**</span><span class="sxs-lookup"><span data-stu-id="7948e-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="7948e-371">Clique **em Remover marca** na caixa de diálogo de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="7948e-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="7948e-372">Remover marcas de quarentena no PowerShell</span><span class="sxs-lookup"><span data-stu-id="7948e-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="7948e-373">Se você preferir usar o PowerShell para remover uma marca de quarentena personalizada, substitua pelo nome da marca de quarentena e \<TagName\> execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7948e-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="7948e-374">Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="7948e-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="7948e-375">Detalhes de permissão da marca de quarentena</span><span class="sxs-lookup"><span data-stu-id="7948e-375">Quarantine tag permission details</span></span>

<span data-ttu-id="7948e-376">As seções a seguir descrevem os efeitos de grupos de permissão predefinidos e permissões individuais nos detalhes das mensagens em quarentena e nas notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="7948e-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="7948e-377">Grupos de permissões predefinidas</span><span class="sxs-lookup"><span data-stu-id="7948e-377">Preset permissions groups</span></span>

<span data-ttu-id="7948e-378">As permissões individuais incluídas em grupos de permissões predefinidos estão listadas na tabela no início deste artigo.</span><span class="sxs-lookup"><span data-stu-id="7948e-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="7948e-379">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="7948e-379">No access</span></span>

<span data-ttu-id="7948e-380">Se a marca de quarentena atribuir as **permissões Sem** acesso (sem permissões), os usuários ainda obterão alguns recursos de linha de base:</span><span class="sxs-lookup"><span data-stu-id="7948e-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="7948e-381">**Detalhes da mensagem em quarentena:** o **botão Exibir o header** da mensagem está sempre disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Botões disponíveis nos detalhes da mensagem em quarentena se a marca de quarentena der ao usuário nenhuma permissão de acesso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="7948e-383">**Notificações de spam para**  o usuário final: o botão Revisão que leva o usuário para a mensagem em quarentena está sempre disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Botões disponíveis na notificação de spam do usuário final se a marca de quarentena der ao usuário nenhuma permissão de acesso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="7948e-385">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="7948e-385">Limited access</span></span>

<span data-ttu-id="7948e-386">Se a marca de quarentena atribuir as **permissões de** acesso limitado, os usuários obterão os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="7948e-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="7948e-387">**Detalhes da mensagem em quarentena:** os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7948e-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="7948e-388">**Versão da solicitação**</span><span class="sxs-lookup"><span data-stu-id="7948e-388">**Request release**</span></span>
  - <span data-ttu-id="7948e-389">**Exibir cabeçalho de mensagem**</span><span class="sxs-lookup"><span data-stu-id="7948e-389">**View message header**</span></span>
  - <span data-ttu-id="7948e-390">**Mensagem de visualização**</span><span class="sxs-lookup"><span data-stu-id="7948e-390">**Preview message**</span></span>
  - <span data-ttu-id="7948e-391">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-391">**Block sender**</span></span>
  - <span data-ttu-id="7948e-392">**Remover da quarentena**</span><span class="sxs-lookup"><span data-stu-id="7948e-392">**Remove from quarantine**</span></span>

  ![Botões disponíveis nos detalhes da mensagem em quarentena se a marca de quarentena der ao usuário permissões de acesso limitado](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="7948e-394">**Notificações de spam para o usuário final:** os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7948e-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="7948e-395">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-395">**Block sender**</span></span>
  - <span data-ttu-id="7948e-396">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="7948e-396">**Review**</span></span>

  ![Botões disponíveis na notificação de spam do usuário final se a marca de quarentena der ao usuário permissões de acesso limitado](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="7948e-398">Acesso total</span><span class="sxs-lookup"><span data-stu-id="7948e-398">Full access</span></span>

<span data-ttu-id="7948e-399">Se a marca de quarentena atribuir as **permissões** de acesso completo (todas as permissões disponíveis), os usuários obterão os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="7948e-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="7948e-400">**Detalhes da mensagem em quarentena:** os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7948e-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="7948e-401">**Liberar mensagem**</span><span class="sxs-lookup"><span data-stu-id="7948e-401">**Release message**</span></span>
  - <span data-ttu-id="7948e-402">**Exibir cabeçalho de mensagem**</span><span class="sxs-lookup"><span data-stu-id="7948e-402">**View message header**</span></span>
  - <span data-ttu-id="7948e-403">**Mensagem de visualização**</span><span class="sxs-lookup"><span data-stu-id="7948e-403">**Preview message**</span></span>
  - <span data-ttu-id="7948e-404">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-404">**Block sender**</span></span>
  - <span data-ttu-id="7948e-405">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-405">**Allow sender**</span></span>
  - <span data-ttu-id="7948e-406">**Remover da quarentena**</span><span class="sxs-lookup"><span data-stu-id="7948e-406">**Remove from quarantine**</span></span>

  ![Botões disponíveis nos detalhes da mensagem em quarentena se a marca de quarentena der ao usuário permissões de acesso total](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="7948e-408">**Notificações de spam para o usuário final:** os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7948e-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="7948e-409">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="7948e-409">**Block sender**</span></span>
  - <span data-ttu-id="7948e-410">**Liberar**</span><span class="sxs-lookup"><span data-stu-id="7948e-410">**Release**</span></span>
  - <span data-ttu-id="7948e-411">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="7948e-411">**Review**</span></span>

  ![Botões disponíveis na notificação de spam do usuário final se a marca de quarentena der ao usuário permissões de acesso total](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="7948e-413">Permissões individuais</span><span class="sxs-lookup"><span data-stu-id="7948e-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="7948e-414">Lembre-se de que os usuários sempre têm os botões descritos na [seção Sem](#no-access) acesso.</span><span class="sxs-lookup"><span data-stu-id="7948e-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="7948e-415">Esses botões não estão incluídos nas descrições de permissão individuais.</span><span class="sxs-lookup"><span data-stu-id="7948e-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="7948e-416">Permitir permissão de remetente</span><span class="sxs-lookup"><span data-stu-id="7948e-416">Allow sender permission</span></span>

<span data-ttu-id="7948e-417">A **permissão Permitir** remetente (_PermissionToAllowSender_) controla o acesso ao botão que permite aos usuários adicionar convenientemente o remetente da mensagem em quarentena à sua lista de Remetentes Seguros.</span><span class="sxs-lookup"><span data-stu-id="7948e-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="7948e-418">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="7948e-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7948e-419">**Permitir permissão de** remetente habilitada: o **botão** Permitir remetente está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="7948e-420">**Permitir permissão de** remetente desabilitada: o **botão** Permitir remetente não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="7948e-421">**Notificações de spam para o usuário final:** sem efeito.</span><span class="sxs-lookup"><span data-stu-id="7948e-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="7948e-422">Para obter mais informações sobre a [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) lista de Destinatários Confiáveis, consulte Impedir que os destinatários confiáveis são bloqueados e usar o PowerShell do Exchange Online para configurar o conjunto de listas seguras em [uma caixa de correio.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="7948e-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="7948e-423">Bloquear permissão de remetente</span><span class="sxs-lookup"><span data-stu-id="7948e-423">Block sender permission</span></span>

<span data-ttu-id="7948e-424">A **permissão** Bloquear remetente (_PermissionToBlockSender_) controla o acesso ao botão que permite aos usuários adicionar convenientemente o remetente da mensagem em quarentena à sua lista de Remetentes Bloqueados.</span><span class="sxs-lookup"><span data-stu-id="7948e-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="7948e-425">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="7948e-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7948e-426">**Permissão de bloqueio de** remetente habilitada: o **botão** Bloquear remetente está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="7948e-427">**Permissões de bloqueio de** remetente desabilitadas: o botão Bloquear **remetente** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="7948e-428">**Notificações de spam para o usuário final:**</span><span class="sxs-lookup"><span data-stu-id="7948e-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="7948e-429">**Permissões de bloqueio de** remetente desabilitadas: o botão Bloquear **remetente** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="7948e-430">**Permissão de bloqueio de** remetente habilitada: o **botão** Bloquear remetente está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="7948e-431">Para obter mais informações sobre a [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) lista de Destinatários Bloqueados, consulte Bloquear mensagens de alguém e usar o PowerShell do Exchange Online para configurar o conjunto de listas seguras [em uma caixa de correio.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="7948e-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="7948e-432">Permissão de exclusão</span><span class="sxs-lookup"><span data-stu-id="7948e-432">Delete permission</span></span>

<span data-ttu-id="7948e-433">A **permissão Delete** (_PermissionToDelete_) controla a capacidade dos usuários de excluir suas mensagens (mensagens em que o usuário é um destinatário) da quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="7948e-434">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="7948e-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7948e-435">**Permissão** de exclusão habilitada: o **botão Remover** da quarentena está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="7948e-436">**Excluir** permissão desabilitada: **o botão Remover da** quarentena não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="7948e-437">**Notificações de spam para o usuário final:** Sem efeito.</span><span class="sxs-lookup"><span data-stu-id="7948e-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="7948e-438">Permissão de visualização</span><span class="sxs-lookup"><span data-stu-id="7948e-438">Preview permission</span></span>

<span data-ttu-id="7948e-439">A **permissão de** visualização (_PermissionToPreview_) controla a capacidade dos usuários de visualizar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="7948e-440">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="7948e-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7948e-441">**Permissão de** visualização habilitada: o **botão Visualizar** mensagem está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="7948e-442">**Permissão de** visualização desabilitada: o **botão Visualizar** mensagem não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="7948e-443">**Notificações de spam para o usuário final:** sem efeito.</span><span class="sxs-lookup"><span data-stu-id="7948e-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="7948e-444">Permitir que os destinatários liberem uma mensagem da permissão de quarentena</span><span class="sxs-lookup"><span data-stu-id="7948e-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="7948e-445">Permitir **que os destinatários** liberem uma mensagem da permissão de quarentena (_PermissionToRelease_) controla a capacidade dos usuários liberarem suas mensagens em quarentena diretamente e sem a aprovação de um administrador.</span><span class="sxs-lookup"><span data-stu-id="7948e-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="7948e-446">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="7948e-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7948e-447">Permissão habilitada: o **botão** Liberar mensagem está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="7948e-448">Permissão desabilitada: o **botão Liberar** mensagem não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="7948e-449">**Notificações de spam para o usuário final:**</span><span class="sxs-lookup"><span data-stu-id="7948e-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="7948e-450">Permissão habilitada: o **botão** Liberar está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="7948e-451">Permissão desabilitada: o **botão** Liberar não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="7948e-452">Permitir que os destinatários solicitem que uma mensagem seja liberada da permissão de quarentena</span><span class="sxs-lookup"><span data-stu-id="7948e-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="7948e-453">Permitir que os **destinatários** solicitem que uma mensagem seja liberada da permissão de quarentena  (_PermissionToRequestRelease_) controla a capacidade dos usuários de solicitar a liberação de suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7948e-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="7948e-454">A mensagem só será liberada depois que um administrador aprovar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="7948e-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="7948e-455">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="7948e-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7948e-456">Permissão habilitada: **o botão Solicitar** liberação está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="7948e-457">Permissão desabilitada: o **botão Liberar** Solicitação não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="7948e-458">**Notificações de spam para o usuário final:** o **botão** Liberar não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7948e-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
