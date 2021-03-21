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
ms.openlocfilehash: 8024894cdb4a4718422c250eff87fa6da5443a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922407"
---
# <a name="quarantine-tags"></a><span data-ttu-id="b3904-103">Marcas de quarentena</span><span class="sxs-lookup"><span data-stu-id="b3904-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="b3904-104">Os recursos descritos neste artigo estão atualmente em Visualização, não estão disponíveis para todos e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="b3904-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="b3904-105">As marcas de quarentena no Exchange Online Protection (EOP) permitem que os administradores controlem o que os usuários são capazes de fazer com suas mensagens em quarentena com base em como a mensagem chegou em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="b3904-106">O EOP tradicionalmente permitiu ou impediu determinados [](find-and-release-quarantined-messages-as-a-user.md) níveis de interatividade para mensagens em quarentena e em notificações de [spam do usuário final.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b3904-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="b3904-107">Por exemplo, os usuários finais podem exibir e liberar mensagens que foram colocadas em quarentena pela filtragem anti-spam como spam ou em massa, mas não podem exibir ou liberar mensagens que estavam em quarentena como phishing de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="b3904-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="b3904-108">Para [recursos de proteção](#step-2-assign-a-quarantine-tag-to-supported-features)com suporte, as marcas de quarentena especificam o que os usuários têm permissão para fazer em mensagens de notificação de spam do usuário final e em suas mensagens em quarentena (mensagens em que o usuário é um destinatário).</span><span class="sxs-lookup"><span data-stu-id="b3904-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="b3904-109">As marcas de quarentena padrão são atribuídas automaticamente para impor os recursos históricos para usuários finais em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="b3904-110">Ou você pode criar e atribuir marcas de quarentena personalizadas para permitir ou impedir que os usuários finais executam ações específicas em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="b3904-111">As permissões individuais são combinadas nos seguintes grupos de permissões predefinidos:</span><span class="sxs-lookup"><span data-stu-id="b3904-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="b3904-112">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="b3904-112">No access</span></span>
- <span data-ttu-id="b3904-113">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="b3904-113">Limited access</span></span>
- <span data-ttu-id="b3904-114">Acesso total</span><span class="sxs-lookup"><span data-stu-id="b3904-114">Full access</span></span>

<span data-ttu-id="b3904-115">As permissões individuais disponíveis e o que está incluído ou não nos grupos de permissão predefinidos são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3904-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="b3904-116">Permissão</span><span class="sxs-lookup"><span data-stu-id="b3904-116">Permission</span></span>|<span data-ttu-id="b3904-117">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="b3904-117">No access</span></span>|<span data-ttu-id="b3904-118">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="b3904-118">Limited access</span></span>|<span data-ttu-id="b3904-119">Acesso total</span><span class="sxs-lookup"><span data-stu-id="b3904-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="b3904-120">**Permitir remetente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="b3904-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="b3904-122">**Bloquear remetente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="b3904-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="b3904-125">**Excluir** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="b3904-125">**Delete** (_PermissionToDelete_)</span></span>||![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="b3904-128">**Visualização** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="b3904-128">**Preview** (_PermissionToPreview_)</span></span>||![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="b3904-131">**Permitir que os destinatários liberem uma mensagem de quarentena** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="b3904-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Marca de seleção](../../media/checkmark.png)|
|<span data-ttu-id="b3904-133">**Permitir que os destinatários solicitem que uma mensagem seja liberada da quarentena** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="b3904-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Marca de seleção](../../media/checkmark.png)||
|

<span data-ttu-id="b3904-135">Se você não gostar das permissões padrão nos grupos de permissões predefinidos, poderá usar permissões personalizadas ao criar ou modificar marcas de quarentena personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b3904-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="b3904-136">Para obter mais informações sobre o que cada permissão faz, consulte a seção Detalhes da permissão [de marca](#quarantine-tag-permission-details) de quarentena posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b3904-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="b3904-137">Você cria e atribui marcas de quarentena no Centro de Conformidade & Segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com Caixas de Correio do Exchange Online; PowerShell autônomo do EOP em organizações do EOP sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="b3904-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b3904-138">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="b3904-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b3904-139">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b3904-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b3904-140">Para ir diretamente para a página **Marcas de quarentena,** abra <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="b3904-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="b3904-141">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b3904-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b3904-142">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b3904-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b3904-143">Para exibir, criar, modificar ou remover marcas de quarentena,  você  precisa ser membro das funções Gerenciamento da Organização ou Administrador de Segurança no Centro de Conformidade & [Segurança.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="b3904-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="b3904-144">Etapa 1: Criar marcas de quarentena no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b3904-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b3904-145">No Centro de Conformidade & segurança, vá para **Política** de gerenciamento de ameaças e \>  selecione Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="b3904-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="b3904-146">Na página **Marcas de quarentena,** selecione **Adicionar marca personalizada**.</span><span class="sxs-lookup"><span data-stu-id="b3904-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="b3904-147">O **assistente nova marca** é aberto.</span><span class="sxs-lookup"><span data-stu-id="b3904-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="b3904-148">Na página **Nome da** marca, insira um nome breve, mas exclusivo no campo **Nome da** marca.</span><span class="sxs-lookup"><span data-stu-id="b3904-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="b3904-149">Você precisará identificar e selecionar a marca pelo nome nas próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="b3904-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="b3904-150">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3904-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b3904-151">Na página **Acesso à** mensagem de destinatário, selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b3904-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="b3904-152">**Sem acesso**</span><span class="sxs-lookup"><span data-stu-id="b3904-152">**No access**</span></span>
   - <span data-ttu-id="b3904-153">**Acesso limitado**</span><span class="sxs-lookup"><span data-stu-id="b3904-153">**Limited access**</span></span>
   - <span data-ttu-id="b3904-154">**Acesso total**</span><span class="sxs-lookup"><span data-stu-id="b3904-154">**Full access**</span></span>

   <span data-ttu-id="b3904-155">As permissões individuais incluídas nesses grupos de permissão são descritas anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b3904-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="b3904-156">Para especificar permissões personalizadas, selecione **Definir acesso específico (Avançado)** e configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b3904-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="b3904-157">**Selecione preferência de ação de versão**: Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b3904-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="b3904-158">**Nenhuma ação de versão**: esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b3904-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="b3904-159">**Permitir que os destinatários liberem uma mensagem da quarentena**</span><span class="sxs-lookup"><span data-stu-id="b3904-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="b3904-160">**Permitir que os destinatários solicitem que uma mensagem seja liberada da quarentena**</span><span class="sxs-lookup"><span data-stu-id="b3904-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="b3904-161">**Selecione ações adicionais que os destinatários podem tomar** em mensagens em quarentena : Selecione alguns, todos ou nenhum dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b3904-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="b3904-162">**Delete**</span><span class="sxs-lookup"><span data-stu-id="b3904-162">**Delete**</span></span>
       - <span data-ttu-id="b3904-163">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="b3904-163">**Preview**</span></span>
       - <span data-ttu-id="b3904-164">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-164">**Allow sender**</span></span>
       - <span data-ttu-id="b3904-165">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-165">**Block sender**</span></span>

   <span data-ttu-id="b3904-166">Essas permissões e seus efeitos nas mensagens em quarentena e nas notificações de spam do usuário final são descritos na seção Detalhes da permissão de [marca](#quarantine-tag-permission-details) de quarentena posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b3904-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="b3904-167">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3904-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b3904-168">Na página **Resumo** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="b3904-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="b3904-169">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="b3904-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b3904-170">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b3904-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="b3904-171">Clique **em Feito** na página de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="b3904-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="b3904-172">Agora você está pronto para atribuir a marca de quarentena a um recurso de quarentena conforme descrito na [seção Etapa 2.](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="b3904-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="b3904-173">Criar marcas de quarentena no PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3904-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="b3904-174">Se preferir usar o PowerShell para criar marcas de quarentena, conecte-se ao PowerShell do Exchange Online ou ao PowerShell de Proteção do Exchange Online e use o cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="b3904-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="b3904-175">Você tem dois métodos diferentes para escolher:</span><span class="sxs-lookup"><span data-stu-id="b3904-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="b3904-176">Use o _parâmetro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="b3904-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="b3904-177">Use o _parâmetro EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="b3904-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="b3904-178">Esses métodos são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="b3904-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="b3904-179">Usar o parâmetro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="b3904-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="b3904-180">Para criar uma marca de quarentena usando o _parâmetro EndUserQuarantinePermissionsValue,_ use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b3904-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="b3904-181">O _parâmetro EndUserQuarantinePermissionsValue_ usa um valor decimal convertido de um valor binário.</span><span class="sxs-lookup"><span data-stu-id="b3904-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="b3904-182">O valor binário corresponde às permissões de quarentena do usuário final disponíveis em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="b3904-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="b3904-183">Para cada permissão, o valor 1 é igual a True e o valor 0 é igual a False.</span><span class="sxs-lookup"><span data-stu-id="b3904-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="b3904-184">A ordem e os valores necessários para cada permissão individual em grupos de permissão predefinidos são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3904-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="b3904-185">Permissão</span><span class="sxs-lookup"><span data-stu-id="b3904-185">Permission</span></span>|<span data-ttu-id="b3904-186">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="b3904-186">No access</span></span>|<span data-ttu-id="b3904-187">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="b3904-187">Limited access</span></span>|<span data-ttu-id="b3904-188">Acesso total</span><span class="sxs-lookup"><span data-stu-id="b3904-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="b3904-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="b3904-189">PermissionToAllowSender</span></span>|<span data-ttu-id="b3904-190">0</span><span class="sxs-lookup"><span data-stu-id="b3904-190">0</span></span>|<span data-ttu-id="b3904-191">0</span><span class="sxs-lookup"><span data-stu-id="b3904-191">0</span></span>|<span data-ttu-id="b3904-192">1</span><span class="sxs-lookup"><span data-stu-id="b3904-192">1</span></span>|
|<span data-ttu-id="b3904-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="b3904-193">PermissionToBlockSender</span></span>|<span data-ttu-id="b3904-194">0</span><span class="sxs-lookup"><span data-stu-id="b3904-194">0</span></span>|<span data-ttu-id="b3904-195">1</span><span class="sxs-lookup"><span data-stu-id="b3904-195">1</span></span>|<span data-ttu-id="b3904-196">1</span><span class="sxs-lookup"><span data-stu-id="b3904-196">1</span></span>|
|<span data-ttu-id="b3904-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="b3904-197">PermissionToDelete</span></span>|<span data-ttu-id="b3904-198">0</span><span class="sxs-lookup"><span data-stu-id="b3904-198">0</span></span>|<span data-ttu-id="b3904-199">1</span><span class="sxs-lookup"><span data-stu-id="b3904-199">1</span></span>|<span data-ttu-id="b3904-200">1</span><span class="sxs-lookup"><span data-stu-id="b3904-200">1</span></span>|
|<span data-ttu-id="b3904-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3904-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="b3904-202">0</span><span class="sxs-lookup"><span data-stu-id="b3904-202">0</span></span>|<span data-ttu-id="b3904-203">0</span><span class="sxs-lookup"><span data-stu-id="b3904-203">0</span></span>|<span data-ttu-id="b3904-204">0</span><span class="sxs-lookup"><span data-stu-id="b3904-204">0</span></span>|
|<span data-ttu-id="b3904-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="b3904-205">PermissionToPreview</span></span>|<span data-ttu-id="b3904-206">0</span><span class="sxs-lookup"><span data-stu-id="b3904-206">0</span></span>|<span data-ttu-id="b3904-207">1</span><span class="sxs-lookup"><span data-stu-id="b3904-207">1</span></span>|<span data-ttu-id="b3904-208">1</span><span class="sxs-lookup"><span data-stu-id="b3904-208">1</span></span>|
|<span data-ttu-id="b3904-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3904-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="b3904-210">0</span><span class="sxs-lookup"><span data-stu-id="b3904-210">0</span></span>|<span data-ttu-id="b3904-211">0</span><span class="sxs-lookup"><span data-stu-id="b3904-211">0</span></span>|<span data-ttu-id="b3904-212">1</span><span class="sxs-lookup"><span data-stu-id="b3904-212">1</span></span>|
|<span data-ttu-id="b3904-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3904-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="b3904-214">0</span><span class="sxs-lookup"><span data-stu-id="b3904-214">0</span></span>|<span data-ttu-id="b3904-215">1</span><span class="sxs-lookup"><span data-stu-id="b3904-215">1</span></span>|<span data-ttu-id="b3904-216">0</span><span class="sxs-lookup"><span data-stu-id="b3904-216">0</span></span>|
|<span data-ttu-id="b3904-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3904-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="b3904-218">0</span><span class="sxs-lookup"><span data-stu-id="b3904-218">0</span></span>|<span data-ttu-id="b3904-219">0</span><span class="sxs-lookup"><span data-stu-id="b3904-219">0</span></span>|<span data-ttu-id="b3904-220">0</span><span class="sxs-lookup"><span data-stu-id="b3904-220">0</span></span>|
|<span data-ttu-id="b3904-221">Valor binário</span><span class="sxs-lookup"><span data-stu-id="b3904-221">Binary value</span></span>|<span data-ttu-id="b3904-222">00000000</span><span class="sxs-lookup"><span data-stu-id="b3904-222">00000000</span></span>|<span data-ttu-id="b3904-223">01101010</span><span class="sxs-lookup"><span data-stu-id="b3904-223">01101010</span></span>|<span data-ttu-id="b3904-224">11101100</span><span class="sxs-lookup"><span data-stu-id="b3904-224">11101100</span></span>|
|<span data-ttu-id="b3904-225">Valor decimal a ser usado</span><span class="sxs-lookup"><span data-stu-id="b3904-225">Decimal value to use</span></span>|<span data-ttu-id="b3904-226">0</span><span class="sxs-lookup"><span data-stu-id="b3904-226">0</span></span>|<span data-ttu-id="b3904-227">106</span><span class="sxs-lookup"><span data-stu-id="b3904-227">106</span></span>|<span data-ttu-id="b3904-228">236</span><span class="sxs-lookup"><span data-stu-id="b3904-228">236</span></span>|

<span data-ttu-id="b3904-229"><sup>\*</sup> Atualmente, esse valor é sempre 0.</span><span class="sxs-lookup"><span data-stu-id="b3904-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="b3904-230">Para PermissionToViewHeader, o valor 0 não oculta o botão Exibir o **header** da mensagem nos detalhes da mensagem em quarentena (o botão está sempre disponível).</span><span class="sxs-lookup"><span data-stu-id="b3904-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="b3904-231"><sup>\*\*</sup> Não de definir ambos os valores como 1.</span><span class="sxs-lookup"><span data-stu-id="b3904-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="b3904-232">De definir um como 1 e o outro como 0 ou definir ambos como 0.</span><span class="sxs-lookup"><span data-stu-id="b3904-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="b3904-233">Este exemplo cria um novo nome de marca de quarentena NoAccess que atribui as permissões Sem acesso conforme descrito na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="b3904-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="b3904-234">Para permissões de acesso limitado, use o valor 106.</span><span class="sxs-lookup"><span data-stu-id="b3904-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="b3904-235">Para permissões de acesso total, use o valor 236.</span><span class="sxs-lookup"><span data-stu-id="b3904-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="b3904-236">Para permissões personalizadas, use a tabela anterior para obter o valor binário que corresponde às permissões que você deseja.</span><span class="sxs-lookup"><span data-stu-id="b3904-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="b3904-237">Converta o valor binário em um valor decimal e use o valor decimal para o _parâmetro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="b3904-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="b3904-238">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="b3904-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="b3904-239">Usar o parâmetro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="b3904-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="b3904-240">Para criar uma marca de quarentena usando o _parâmetro EndUserQuarantinePermissionsValue,_ faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b3904-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="b3904-241">R.</span><span class="sxs-lookup"><span data-stu-id="b3904-241">A.</span></span> <span data-ttu-id="b3904-242">Armazene um objeto de permissões de quarentena em uma variável usando o cmdlet **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="b3904-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="b3904-243">B.</span><span class="sxs-lookup"><span data-stu-id="b3904-243">B.</span></span> <span data-ttu-id="b3904-244">Use a variável _como o valor EndUserQuarantinePermissions_ no **comando New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="b3904-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="b3904-245">Etapa A: Armazenar um objeto de permissões de quarentena em uma variável</span><span class="sxs-lookup"><span data-stu-id="b3904-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="b3904-246">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b3904-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="b3904-247">O valor padrão para todos os parâmetros não usado é , portanto, você só precisa usar os parâmetros onde deseja `$false` definir o valor como `$true` .</span><span class="sxs-lookup"><span data-stu-id="b3904-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="b3904-248">Os exemplos a seguir mostram como criar objetos de permissão que correspondem aos grupos de permissões predefinidos:</span><span class="sxs-lookup"><span data-stu-id="b3904-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="b3904-249">**Sem acesso**:</span><span class="sxs-lookup"><span data-stu-id="b3904-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="b3904-250">**Acesso limitado**:</span><span class="sxs-lookup"><span data-stu-id="b3904-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="b3904-251">**Acesso completo**:</span><span class="sxs-lookup"><span data-stu-id="b3904-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="b3904-252">Para ver os valores que você definiu, execute o nome da variável como um comando (por exemplo, execute o comando `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="b3904-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="b3904-253">Para permissões personalizadas, não de definir os parâmetros _PermissionToRelease_ e _PermissionToRequestRelease_ como `$true` .</span><span class="sxs-lookup"><span data-stu-id="b3904-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="b3904-254">De definir um para `$true` e deixar o outro como , ou deixar ambos como `$false` `$false` .</span><span class="sxs-lookup"><span data-stu-id="b3904-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="b3904-255">Você também pode modificar uma variável de objeto de permissões existente após criar, mas antes de usá-la usando o cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="b3904-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="b3904-256">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) e [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="b3904-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="b3904-257">Etapa B: Use a variável no comando New-QuarantineTag comando</span><span class="sxs-lookup"><span data-stu-id="b3904-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="b3904-258">Depois de criar e armazenar o objeto permissions em uma variável, use a variável para o valor do parâmetro _EndUserQuarantinePermission_ no seguinte comando **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="b3904-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="b3904-259">Este exemplo cria uma nova marca de quarentena chamada LimitedAccess usando o objeto permissions que foi descrito e `$LimitedAccess` criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="b3904-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="b3904-260">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="b3904-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="b3904-261">Etapa 2: Atribuir uma marca de quarentena aos recursos com suporte</span><span class="sxs-lookup"><span data-stu-id="b3904-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="b3904-262">Nos _recursos de proteção_ com suporte que as mensagens ou arquivos de quarentena (automaticamente ou como uma ação configurável), você pode atribuir uma marca de quarentena às ações de quarentena disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b3904-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="b3904-263">Recursos que as mensagens de quarentena e a disponibilidade de marcas de quarentena são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3904-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="b3904-264">Recurso</span><span class="sxs-lookup"><span data-stu-id="b3904-264">Feature</span></span>|<span data-ttu-id="b3904-265">Marcas de quarentena suportadas?</span><span class="sxs-lookup"><span data-stu-id="b3904-265">Quarantine tags supported?</span></span>|<span data-ttu-id="b3904-266">Marcas de quarentena padrão usadas</span><span class="sxs-lookup"><span data-stu-id="b3904-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="b3904-267">[Políticas anti-spam](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="b3904-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="b3904-268">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="b3904-269">**Spam de alta confiança** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="b3904-270">**Email de phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="b3904-271">**Email de phishing de** alta confiança (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="b3904-272">**Email em massa** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="b3904-273">Sim</span><span class="sxs-lookup"><span data-stu-id="b3904-273">Yes</span></span>|<ul><li><span data-ttu-id="b3904-274">DefaultSpamTag (Acesso completo)</span><span class="sxs-lookup"><span data-stu-id="b3904-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="b3904-275">DefaultHighConfSpamTag (acesso completo)</span><span class="sxs-lookup"><span data-stu-id="b3904-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="b3904-276">DefaultPhishTag (acesso completo)</span><span class="sxs-lookup"><span data-stu-id="b3904-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="b3904-277">DefaultHighConfPhishTag (Sem acesso)</span><span class="sxs-lookup"><span data-stu-id="b3904-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="b3904-278">DefaultBulkTag (acesso completo)</span><span class="sxs-lookup"><span data-stu-id="b3904-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="b3904-279">Políticas anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="b3904-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="b3904-280">[Proteção de inteligência de spoof](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="b3904-281">[Proteção contra representação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3904-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="b3904-282">**Se o email for enviado por um usuário personificado** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="b3904-283">**Se o email for enviado por um domínio personificado** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="b3904-284">**Inteligência de caixa de correio** \> **Se o email for enviado por um usuário personificado** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="b3904-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="b3904-285">Não</span><span class="sxs-lookup"><span data-stu-id="b3904-285">No</span></span>|<span data-ttu-id="b3904-286">n/d</span><span class="sxs-lookup"><span data-stu-id="b3904-286">n/a</span></span>|
|<span data-ttu-id="b3904-287">[Políticas anti-malware](configure-anti-malware-policies.md): Todas as mensagens detectadas estão sempre em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="b3904-288">Não</span><span class="sxs-lookup"><span data-stu-id="b3904-288">No</span></span>|<span data-ttu-id="b3904-289">n/d</span><span class="sxs-lookup"><span data-stu-id="b3904-289">n/a</span></span>|
|[<span data-ttu-id="b3904-290">Anexos seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3904-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="b3904-291">Não</span><span class="sxs-lookup"><span data-stu-id="b3904-291">No</span></span>|<span data-ttu-id="b3904-292">n/d</span><span class="sxs-lookup"><span data-stu-id="b3904-292">n/a</span></span>|
|<span data-ttu-id="b3904-293">[Regras de fluxo de emails](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (também conhecidas como regras de transporte) com a ação: Entregar a mensagem à **quarentena** hospedada (_Quarentena_).</span><span class="sxs-lookup"><span data-stu-id="b3904-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="b3904-294">Não</span><span class="sxs-lookup"><span data-stu-id="b3904-294">No</span></span>|<span data-ttu-id="b3904-295">n/d</span><span class="sxs-lookup"><span data-stu-id="b3904-295">n/a</span></span>|
|

<span data-ttu-id="b3904-296"><sup>\*</sup> As configurações de proteção de representação estão disponíveis somente em políticas anti-phishing no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3904-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="b3904-297">Se você estiver satisfeito com as permissões do usuário final fornecidas pelas marcas de quarentena padrão, você não precisa fazer nada.</span><span class="sxs-lookup"><span data-stu-id="b3904-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="b3904-298">Se você quiser personalizar os recursos do usuário final (botões disponíveis) em notificações de spam do usuário final ou em detalhes de mensagem em quarentena, você pode atribuir uma marca de quarentena personalizada.</span><span class="sxs-lookup"><span data-stu-id="b3904-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="b3904-299">Atribuir marcas de quarentena em políticas anti-spam no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b3904-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="b3904-300">Instruções completas para criar e modificar políticas anti-spam são descritas em [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b3904-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="b3904-301">No Centro de Conformidade & segurança, vá para **Política** de gerenciamento de ameaças e \>  \> selecione **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="b3904-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="b3904-302">Ou, abra <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="b3904-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="b3904-303">Encontre e selecione uma política anti-spam existente para editar ou criar uma nova política anti-spam.</span><span class="sxs-lookup"><span data-stu-id="b3904-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="b3904-304">No sobremenu de detalhes da política, expanda a seção **Spam e ações em massa.**</span><span class="sxs-lookup"><span data-stu-id="b3904-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="b3904-305">Se você tiver  selecionado a mensagem de quarentena para a  ação de um veredito de filtragem de spam disponível, a caixa aplicar a marca de política de quarentena estará disponível para você selecionar a marca de quarentena para esse veredito.</span><span class="sxs-lookup"><span data-stu-id="b3904-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="b3904-306">**Observação**: quando você cria uma nova política, um valor de marca de quarentena em branco para um veredito de filtragem de spam indica que a marca de quarentena padrão para esse veredito é usada.</span><span class="sxs-lookup"><span data-stu-id="b3904-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="b3904-307">Quando você edita mais tarde a política, os valores em branco são substituídos pelos nomes de marca de quarentena padrão reais, conforme descrito na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="b3904-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Seleções de marca de quarentena em uma política anti-spam](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="b3904-309">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b3904-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="b3904-310">Atribuir marcas de quarentena em políticas anti-spam no PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3904-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="b3904-311">Se você preferir usar o PowerShell para atribuir marcas de quarentena em políticas anti-spam, conecte-se ao PowerShell do Exchange Online ou ao PowerShell de Proteção do Exchange Online e use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b3904-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="b3904-312">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="b3904-312">**Notes**:</span></span>

- <span data-ttu-id="b3904-313">O valor padrão para o parâmetro _HighConfidencePhishAction_ é Quarantine, portanto, você não precisa definir a ação quarentena para detecções de phishing de alta confiança em novas políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="b3904-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="b3904-314">Para todos os outros vereditos de filtragem de spam em políticas anti-spam novas ou existentes, a marca de quarentena só será efetiva se o valor da ação for Quarantine.</span><span class="sxs-lookup"><span data-stu-id="b3904-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="b3904-315">Para ver os valores de ação em políticas anti-spam existentes, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b3904-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="b3904-316">Para obter informações sobre os valores de ação padrão e os valores de ação recomendados para Standard e Strict, consulte [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b3904-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="b3904-317">Um veredito de filtragem de spam sem um parâmetro de marca de quarentena correspondente significa que a marca de [quarentena padrão](#step-2-assign-a-quarantine-tag-to-supported-features) para esse veredito é usada.</span><span class="sxs-lookup"><span data-stu-id="b3904-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="b3904-318">Você só precisa substituir uma marca de quarentena padrão por uma marca de quarentena personalizada se quiser alterar os recursos padrão do usuário final em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="b3904-319">Uma nova política anti-spam no PowerShell exige uma política de filtro de spam (configurações) usando o cmdlet **New-HostedContentFilterPolicy** e uma nova regra de filtro de spam (filtros de destinatário) usando o cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="b3904-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="b3904-320">Para obter instruções, [consulte Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="b3904-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="b3904-321">Este exemplo cria uma nova política de filtro de spam chamada Departamento de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b3904-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="b3904-322">A ação para todos os vereditos de filtragem de spam está definida como Quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="b3904-323">A marca de quarentena personalizada chamada NoAccess que atribui Nenhuma permissão de acesso substitui qualquer marca de quarentena padrão que ainda não atribua **nenhuma** permissão de acesso por padrão. </span><span class="sxs-lookup"><span data-stu-id="b3904-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="b3904-324">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b3904-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="b3904-325">Este exemplo modifica a política de filtro de spam existente chamada Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="b3904-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="b3904-326">A ação para o veredito de quarentena de spam é definida como Quarentena e a marca de quarentena personalizada chamada NoAccess é atribuída.</span><span class="sxs-lookup"><span data-stu-id="b3904-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="b3904-327">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b3904-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="b3904-328">Configurar configurações de notificação de quarentena global no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b3904-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="b3904-329">As configurações globais para marcas de quarentena permitem personalizar as notificações de spam do usuário final enviadas aos destinatários das mensagens que foram colocadas em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="b3904-330">Para obter mais informações sobre essas notificações, consulte [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="b3904-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="b3904-331">No Centro de Conformidade & segurança, vá para **Política** de gerenciamento de ameaças e \>  selecione Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="b3904-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="b3904-332">Na página **Marcas de quarentena,** selecione **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="b3904-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="b3904-333">No **sobrevoo de configurações** de notificação de quarentena que é aberto, configure algumas ou todas as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b3904-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="b3904-334">**Use o logotipo da minha empresa**: selecione essa opção para substituir o logotipo padrão da Microsoft que é usado na parte superior das notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="b3904-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="b3904-335">Antes de fazer isso, você precisa seguir as instruções em Personalizar o tema do [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) para sua organização carregar seu logotipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3904-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="b3904-336">A captura de tela a seguir mostra um logotipo personalizado em uma notificação de spam do usuário final:</span><span class="sxs-lookup"><span data-stu-id="b3904-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Um logotipo personalizado em uma notificação de spam do usuário final](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="b3904-338">**Escolha idioma**: As notificações de spam do usuário final já estão localizadas com base nas configurações de idioma do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b3904-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="b3904-339">Você pode especificar texto personalizado em idiomas diferentes para os valores **Nome de** exibição e Aviso de **Isenção** de Responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="b3904-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="b3904-340">Selecione pelo menos um idioma na primeira caixa de idioma e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b3904-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="b3904-341">Você pode selecionar vários idiomas clicando em **Adicionar** após cada um deles.</span><span class="sxs-lookup"><span data-stu-id="b3904-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="b3904-342">Uma caixa de idioma de seção mostra todos os idiomas selecionados:</span><span class="sxs-lookup"><span data-stu-id="b3904-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Idiomas selecionados na caixa segundo idioma nas configurações de notificação de quarentena global de marcas de quarentena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="b3904-344">**Nome para** exibição : Personalize o nome de exibição do remetente usado em notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="b3904-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="b3904-345">Para cada idioma adicionado, selecione o idioma na segunda caixa de idioma (não clique no X) e insira o valor de texto que você deseja na caixa **Nome de** exibição.</span><span class="sxs-lookup"><span data-stu-id="b3904-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="b3904-346">A captura de tela a seguir mostra o nome de exibição personalizado em uma notificação de spam do usuário final:</span><span class="sxs-lookup"><span data-stu-id="b3904-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Um nome de exibição de remetente personalizado em uma notificação de spam do usuário final](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="b3904-348">**Aviso de isenção** de responsabilidade : adicione um aviso de isenção de responsabilidade personalizado à parte inferior das notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="b3904-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="b3904-349">O texto localizado, Um aviso de **isenção de responsabilidade da** sua organização: é sempre incluído primeiro, seguido pelo texto especificado.</span><span class="sxs-lookup"><span data-stu-id="b3904-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="b3904-350">Para cada idioma adicionado, selecione o idioma na segunda caixa de idioma (não clique no X) e insira o valor de texto que você deseja na caixa **Aviso** de isenção de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="b3904-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="b3904-351">A captura de tela a seguir mostra o aviso de isenção de responsabilidade personalizado em uma notificação de spam do usuário final:</span><span class="sxs-lookup"><span data-stu-id="b3904-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Um aviso de isenção de responsabilidade personalizado na parte inferior de uma notificação de spam do usuário final](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="b3904-353">Exibir marcas de quarentena no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b3904-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b3904-354">No Centro de Conformidade & segurança, vá para **Política** de gerenciamento de ameaças e \>  selecione Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="b3904-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="b3904-355">Para exibir as configurações de marcas de quarentena personalizadas ou criadas, selecione a marca de quarentena na lista (não selecione a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="b3904-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="b3904-356">Para exibir as configurações globais, selecione **Configurações globais**</span><span class="sxs-lookup"><span data-stu-id="b3904-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="b3904-357">Exibir marcas de quarentena no PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3904-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="b3904-358">Se você preferir usar o PowerShell para exibir marcas de quarentena, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b3904-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="b3904-359">Para exibir uma lista resumida de todas as marcas personalizadas ou criadas, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b3904-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="b3904-360">Para exibir as configurações de marcas de quarentena personalizadas ou criadas, substitua pelo nome da marca de quarentena e \<TagName\> execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b3904-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="b3904-361">Para exibir as configurações globais, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b3904-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="b3904-362">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b3904-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="b3904-363">Remover marcas de quarentena no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b3904-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="b3904-364">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="b3904-364">**Notes**:</span></span>

- <span data-ttu-id="b3904-365">Não é possível remover marcas de quarentena integrados.</span><span class="sxs-lookup"><span data-stu-id="b3904-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="b3904-366">Antes de remover uma marca de quarentena personalizada, verifique se ela não está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="b3904-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="b3904-367">Por exemplo, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3904-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="b3904-368">Se a marca de quarentena estiver sendo usada, [substitua a marca de quarentena atribuída](#step-2-assign-a-quarantine-tag-to-supported-features) antes de removê-la.</span><span class="sxs-lookup"><span data-stu-id="b3904-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="b3904-369">No Centro de Conformidade & segurança, vá para **Política** de gerenciamento de ameaças e \>  selecione Marcas **de quarentena.**</span><span class="sxs-lookup"><span data-stu-id="b3904-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="b3904-370">Na página **Marcas de quarentena,** selecione a marca de quarentena personalizada que você deseja remover e clique em **Excluir marca**.</span><span class="sxs-lookup"><span data-stu-id="b3904-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="b3904-371">Clique **em Remover marca** na caixa de diálogo de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="b3904-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="b3904-372">Remover marcas de quarentena no PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3904-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="b3904-373">Se você preferir usar o PowerShell para remover uma marca de quarentena personalizada, substitua pelo nome da marca de quarentena e \<TagName\> execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b3904-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="b3904-374">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="b3904-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="b3904-375">Detalhes da permissão de marca de quarentena</span><span class="sxs-lookup"><span data-stu-id="b3904-375">Quarantine tag permission details</span></span>

<span data-ttu-id="b3904-376">As seções a seguir descrevem os efeitos de grupos de permissões predefinidos e permissões individuais nos detalhes das mensagens em quarentena e nas notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="b3904-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="b3904-377">Grupos de permissões predefinidas</span><span class="sxs-lookup"><span data-stu-id="b3904-377">Preset permissions groups</span></span>

<span data-ttu-id="b3904-378">As permissões individuais incluídas em grupos de permissão predefinidos estão listadas na tabela no início deste artigo.</span><span class="sxs-lookup"><span data-stu-id="b3904-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="b3904-379">Sem acesso</span><span class="sxs-lookup"><span data-stu-id="b3904-379">No access</span></span>

<span data-ttu-id="b3904-380">Se a marca de quarentena atribuir as permissões **Sem** acesso (sem permissões), os usuários ainda obterão alguns recursos de linha de base:</span><span class="sxs-lookup"><span data-stu-id="b3904-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="b3904-381">**Detalhes da mensagem em quarentena**: o botão Exibir o **header** da mensagem está sempre disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Botões disponíveis nos detalhes da mensagem em quarentena se a marca de quarentena der ao usuário nenhuma permissão de acesso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="b3904-383">**Notificações de spam do usuário final**: O botão **Revisão** que leva o usuário para a mensagem em quarentena está sempre disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Botões disponíveis na notificação de spam do usuário final se a marca de quarentena der ao usuário nenhuma permissão de acesso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="b3904-385">Acesso limitado</span><span class="sxs-lookup"><span data-stu-id="b3904-385">Limited access</span></span>

<span data-ttu-id="b3904-386">Se a marca de quarentena atribuir as **permissões** de acesso limitado, os usuários obterão os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="b3904-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="b3904-387">**Detalhes da mensagem em quarentena:** Os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b3904-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="b3904-388">**Versão de solicitação**</span><span class="sxs-lookup"><span data-stu-id="b3904-388">**Request release**</span></span>
  - <span data-ttu-id="b3904-389">**Exibir cabeçalho de mensagem**</span><span class="sxs-lookup"><span data-stu-id="b3904-389">**View message header**</span></span>
  - <span data-ttu-id="b3904-390">**Mensagem de visualização**</span><span class="sxs-lookup"><span data-stu-id="b3904-390">**Preview message**</span></span>
  - <span data-ttu-id="b3904-391">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-391">**Block sender**</span></span>
  - <span data-ttu-id="b3904-392">**Remover da quarentena**</span><span class="sxs-lookup"><span data-stu-id="b3904-392">**Remove from quarantine**</span></span>

  ![Botões disponíveis nos detalhes da mensagem em quarentena se a marca de quarentena der ao usuário permissões de acesso limitado](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="b3904-394">**Notificações de spam do usuário final:** Os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b3904-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="b3904-395">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-395">**Block sender**</span></span>
  - <span data-ttu-id="b3904-396">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="b3904-396">**Review**</span></span>

  ![Botões disponíveis na notificação de spam do usuário final se a marca de quarentena der ao usuário permissões de acesso limitado](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="b3904-398">Acesso total</span><span class="sxs-lookup"><span data-stu-id="b3904-398">Full access</span></span>

<span data-ttu-id="b3904-399">Se a marca de quarentena atribuir as **permissões** de acesso total (todas as permissões disponíveis), os usuários obterão os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="b3904-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="b3904-400">**Detalhes da mensagem em quarentena:** Os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b3904-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="b3904-401">**Mensagem de versão**</span><span class="sxs-lookup"><span data-stu-id="b3904-401">**Release message**</span></span>
  - <span data-ttu-id="b3904-402">**Exibir cabeçalho de mensagem**</span><span class="sxs-lookup"><span data-stu-id="b3904-402">**View message header**</span></span>
  - <span data-ttu-id="b3904-403">**Mensagem de visualização**</span><span class="sxs-lookup"><span data-stu-id="b3904-403">**Preview message**</span></span>
  - <span data-ttu-id="b3904-404">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-404">**Block sender**</span></span>
  - <span data-ttu-id="b3904-405">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-405">**Allow sender**</span></span>
  - <span data-ttu-id="b3904-406">**Remover da quarentena**</span><span class="sxs-lookup"><span data-stu-id="b3904-406">**Remove from quarantine**</span></span>

  ![Botões disponíveis nos detalhes da mensagem em quarentena se a marca de quarentena der ao usuário permissões de acesso total](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="b3904-408">**Notificações de spam do usuário final:** Os seguintes botões estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b3904-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="b3904-409">**Bloquear remetente**</span><span class="sxs-lookup"><span data-stu-id="b3904-409">**Block sender**</span></span>
  - <span data-ttu-id="b3904-410">**Liberar**</span><span class="sxs-lookup"><span data-stu-id="b3904-410">**Release**</span></span>
  - <span data-ttu-id="b3904-411">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="b3904-411">**Review**</span></span>

  ![Botões disponíveis na notificação de spam do usuário final se a marca de quarentena der ao usuário permissões de acesso total](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="b3904-413">Permissões individuais</span><span class="sxs-lookup"><span data-stu-id="b3904-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="b3904-414">Lembre-se de que os usuários sempre têm os botões descritos na [seção Sem](#no-access) acesso.</span><span class="sxs-lookup"><span data-stu-id="b3904-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="b3904-415">Esses botões não estão incluídos nas descrições de permissão individuais.</span><span class="sxs-lookup"><span data-stu-id="b3904-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="b3904-416">Permitir permissão de remetente</span><span class="sxs-lookup"><span data-stu-id="b3904-416">Allow sender permission</span></span>

<span data-ttu-id="b3904-417">A **permissão Permitir remetente** (_PermissionToAllowSender_) controla o acesso ao botão que permite que os usuários adicionem convenientemente o remetente de mensagem em quarentena à lista de Remetentes Seguros.</span><span class="sxs-lookup"><span data-stu-id="b3904-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="b3904-418">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="b3904-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b3904-419">**Permitir permissão de remetente** habilitada: o **botão Permitir remetente** está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="b3904-420">**Permitir permissão de remetente** desabilitada: o **botão Permitir remetente** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="b3904-421">**Notificações de spam do usuário final**: Sem efeito.</span><span class="sxs-lookup"><span data-stu-id="b3904-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="b3904-422">Para obter mais informações sobre a lista De envios confiáveis, consulte [Prevent trusted senders](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) from being blocked and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="b3904-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="b3904-423">Bloquear permissão de remetente</span><span class="sxs-lookup"><span data-stu-id="b3904-423">Block sender permission</span></span>

<span data-ttu-id="b3904-424">A **permissão bloquear remetente** (_PermissionToBlockSender_) controla o acesso ao botão que permite que os usuários adicionem convenientemente o remetente de mensagem em quarentena à lista de Remetentes Bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b3904-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="b3904-425">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="b3904-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b3904-426">**Bloquear a permissão de** remetente habilitada: o **botão Bloquear remetente** está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="b3904-427">**Bloquear a permissão de** remetente desabilitada: o **botão Bloquear remetente** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="b3904-428">**Notificações de spam do usuário final:**</span><span class="sxs-lookup"><span data-stu-id="b3904-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="b3904-429">**Bloquear a permissão de** remetente desabilitada: o **botão Bloquear remetente** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="b3904-430">**Bloquear a permissão de** remetente habilitada: o **botão Bloquear remetente** está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="b3904-431">Para obter mais informações sobre a lista De envios bloqueados, consulte [Bloquear](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) mensagens de alguém e Usar o PowerShell do Exchange Online para configurar o conjunto de listas [seguras em uma caixa de correio](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="b3904-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="b3904-432">Permissão de exclusão</span><span class="sxs-lookup"><span data-stu-id="b3904-432">Delete permission</span></span>

<span data-ttu-id="b3904-433">A **permissão Delete** (_PermissionToDelete_) controla a capacidade dos usuários de excluir suas mensagens (mensagens em que o usuário é um destinatário) da quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="b3904-434">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="b3904-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b3904-435">**Excluir** permissão habilitada: o **botão Remover da** quarentena está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="b3904-436">**Excluir** permissão desabilitada: o **botão Remover da** quarentena não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="b3904-437">**Notificações de spam do usuário final**: Sem efeito.</span><span class="sxs-lookup"><span data-stu-id="b3904-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="b3904-438">Permissão de visualização</span><span class="sxs-lookup"><span data-stu-id="b3904-438">Preview permission</span></span>

<span data-ttu-id="b3904-439">A **permissão Preview** (_PermissionToPreview_) controla a capacidade dos usuários de visualizar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="b3904-440">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="b3904-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b3904-441">**Permissão** de visualização habilitada: o **botão Mensagem de** visualização está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="b3904-442">**Permissão** de visualização desabilitada: o **botão Visualizar** mensagem não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="b3904-443">**Notificações de spam do usuário final**: Sem efeito.</span><span class="sxs-lookup"><span data-stu-id="b3904-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="b3904-444">Permitir que os destinatários liberem uma mensagem da permissão de quarentena</span><span class="sxs-lookup"><span data-stu-id="b3904-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="b3904-445">A **permissão Permitir que os destinatários** liberem uma mensagem da permissão de quarentena (_PermissionToRelease_) controla a capacidade dos usuários de liberar suas mensagens em quarentena diretamente e sem a aprovação de um administrador.</span><span class="sxs-lookup"><span data-stu-id="b3904-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="b3904-446">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="b3904-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b3904-447">Permissão habilitada: o **botão Liberar** mensagem está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="b3904-448">Permissão desabilitada: o **botão Liberar** mensagem não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="b3904-449">**Notificações de spam do usuário final:**</span><span class="sxs-lookup"><span data-stu-id="b3904-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="b3904-450">Permissão habilitada: o **botão Liberar** está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="b3904-451">Permissão desabilitada: o **botão Liberar** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="b3904-452">Permitir que os destinatários solicitem que uma mensagem seja liberada da permissão de quarentena</span><span class="sxs-lookup"><span data-stu-id="b3904-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="b3904-453">A **permissão Permitir que os destinatários** solicitem que uma mensagem seja liberada da permissão  de quarentena (_PermissionToRequestRelease_) controla a capacidade dos usuários de solicitar a liberação de suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b3904-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="b3904-454">A mensagem só é liberada depois que um administrador aprova a solicitação.</span><span class="sxs-lookup"><span data-stu-id="b3904-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="b3904-455">**Detalhes da mensagem em quarentena:**</span><span class="sxs-lookup"><span data-stu-id="b3904-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b3904-456">Permissão habilitada: o **botão Liberar** solicitação está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="b3904-457">Permissão desabilitada: o **botão Liberar** solicitação não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="b3904-458">**Notificações de spam do usuário final**: o botão **Liberar** não está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3904-458">**End-user spam notifications**: The **Release** button is not available.</span></span>