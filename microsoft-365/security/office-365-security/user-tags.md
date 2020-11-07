---
title: Marcas de usuário no Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem saber como identificar grupos específicos de usuários com marcas de usuário no Microsoft defender para Office 365 plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Microsoft defender para Office 365 para identificar rapidamente os usuários marcados.
ms.openlocfilehash: 9c83a323a3116b3da61a133c7fb449978ca13841
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945313"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="32a99-104">Marcas de usuário no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="32a99-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="32a99-105">O recurso de marcas de usuário está em visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="32a99-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="32a99-106">Para obter informações sobre o cronograma de lançamento, confira o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="32a99-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="32a99-107">Marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="32a99-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="32a99-108">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="32a99-108">There are two types of user tags:</span></span>

- <span data-ttu-id="32a99-109">**Marcas de sistema** : atualmente, [contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) é o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="32a99-109">**System tags** : Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="32a99-110">**Marcas personalizadas** : você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="32a99-110">**Custom tags** : You create these user tags yourself.</span></span>

<span data-ttu-id="32a99-111">Se sua organização tiver o defender para Office 365 plano 2 (incluído na sua assinatura ou como um complemento), você poderá criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="32a99-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="32a99-112">Após aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="32a99-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="32a99-113">Alertas no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="32a99-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="32a99-114">Gerenciador de ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="32a99-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="32a99-115">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="32a99-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="32a99-116">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="32a99-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="32a99-117">Este artigo explica como configurar marcas de usuário no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="32a99-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="32a99-118">Não há cmdlets no centro de conformidade & segurança para gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="32a99-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="32a99-119">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="32a99-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="32a99-120">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="32a99-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="32a99-121">Para ir diretamente para a página **marcas do usuário** , abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="32a99-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="32a99-122">Para criar, modificar ou remover **marcas de usuário personalizadas** , você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="32a99-122">To create, modify, or remove **custom user tags** , you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="32a99-123">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="32a99-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="32a99-124">Para configurar contas de prioridade (marcas de sistema), você precisa ser um [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou um [administrador do Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="32a99-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="32a99-125">Você também pode gerenciar e monitorar contas de prioridade no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32a99-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="32a99-126">Para obter instruções, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="32a99-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="32a99-127">Usar a central de segurança para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="32a99-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="32a99-128">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="32a99-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="32a99-129">Na página **marcas de usuário** que é aberta, clique em **criar marca**.</span><span class="sxs-lookup"><span data-stu-id="32a99-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="32a99-130">O assistente **criar marca** é aberto em uma nova saída. Na página **definir marca** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="32a99-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="32a99-131">**Name** : Insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="32a99-131">**Name** : Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="32a99-132">Este é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="32a99-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="32a99-133">**Descrição** : Insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="32a99-133">**Description** : Enter an optional description for the tag.</span></span>

   <span data-ttu-id="32a99-134">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32a99-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="32a99-135">Na página **atribuir caixas de correio** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="32a99-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="32a99-136">Clique em **adicionar caixas de correio**.</span><span class="sxs-lookup"><span data-stu-id="32a99-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="32a99-137">Na saída exibida, execute uma das seguintes etapas para adicionar usuários individuais ou grupos:</span><span class="sxs-lookup"><span data-stu-id="32a99-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="32a99-138">Clique na caixa e role pela lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="32a99-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="32a99-139">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="32a99-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="32a99-140">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="32a99-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="32a99-141">Para remover entradas individuais da caixa, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no usuário ou grupo na caixa.</span><span class="sxs-lookup"><span data-stu-id="32a99-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="32a99-142">Para remover as entradas existentes da lista abaixo da caixa, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção na entrada.</span><span class="sxs-lookup"><span data-stu-id="32a99-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="32a99-143">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="32a99-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="32a99-144">Clique em **importar** para selecionar um arquivo de texto que contenha os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="32a99-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="32a99-145">Certifique-se de que o arquivo de texto contém uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="32a99-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="32a99-146">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32a99-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="32a99-147">Na página **rever tag** , revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="32a99-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="32a99-148">Você pode clicar em **Editar** na seção específica para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="32a99-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="32a99-149">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="32a99-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="32a99-150">Usar a central de segurança para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="32a99-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="32a99-151">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="32a99-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="32a99-152">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="32a99-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="32a99-153">Nos detalhes de somente leitura que aparecerem, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="32a99-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="32a99-154">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32a99-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="32a99-155">Usar a central de segurança para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="32a99-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="32a99-156">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="32a99-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="32a99-157">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em **Editar marca**.</span><span class="sxs-lookup"><span data-stu-id="32a99-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="32a99-158">O assistente de política é aberto em uma **marca de edição** de saída. Clique em **Avançar** para revisar e modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="32a99-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="32a99-159">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="32a99-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="32a99-160">Usar a central de segurança para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="32a99-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="32a99-161">**Observação** : não é possível remover a marca de **conta de prioridade** interna.</span><span class="sxs-lookup"><span data-stu-id="32a99-161">**Note** : You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="32a99-162">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="32a99-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="32a99-163">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja remover, clique em **excluir marca** e selecione **Sim, remova** o aviso exibido.</span><span class="sxs-lookup"><span data-stu-id="32a99-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag** , and then select **Yes, remove** in the warning that appears.</span></span>
