---
title: Marcas de usuário no Office 365 ATP
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
description: Os administradores podem aprender a identificar grupos específicos de usuários com marcas de usuário no Office 365 ATP Plan 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Office 365 ATP para identificar rapidamente os usuários marcados.
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399380"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="93333-104">Marcas de usuário no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="93333-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="93333-105">As marcas de usuário são identificadores de grupos específicos de usuários no [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="93333-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="93333-106">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="93333-106">There are two types of user tags:</span></span>

- <span data-ttu-id="93333-107">**Marcas de sistema**: atualmente, [contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) é o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="93333-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="93333-108">**Marcas personalizadas**: você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="93333-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="93333-109">Se sua organização tiver o plano de ATP 2 do Office 365 (incluído na sua assinatura ou como um complemento), você poderá criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="93333-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="93333-110">Após aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="93333-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="93333-111">Alertas no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="93333-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="93333-112">Gerenciador de ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="93333-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="93333-113">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="93333-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="93333-114">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="93333-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="93333-115">Este artigo explica como configurar marcas de usuário no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="93333-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="93333-116">Não há cmdlets no centro de conformidade & segurança para gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="93333-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="93333-117">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="93333-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="93333-118">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="93333-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="93333-119">Para ir diretamente para a página **marcas do usuário** , abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="93333-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="93333-120">Para criar, modificar ou remover **marcas de usuário personalizadas**, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="93333-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="93333-121">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="93333-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="93333-122">Para configurar contas de prioridade (marcas de sistema), você precisa ser um [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou um [administrador do Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="93333-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="93333-123">Você também pode gerenciar e monitorar contas de prioridade no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93333-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="93333-124">Para obter instruções, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="93333-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="93333-125">Usar a central de segurança para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="93333-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="93333-126">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="93333-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="93333-127">Na página **marcas de usuário** que é aberta, clique em **criar marca**.</span><span class="sxs-lookup"><span data-stu-id="93333-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="93333-128">O assistente **criar marca** é aberto em uma nova saída. Na página **definir marca** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="93333-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="93333-129">**Name**: Insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="93333-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="93333-130">Este é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="93333-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="93333-131">**Descrição**: Insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="93333-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="93333-132">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93333-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="93333-133">Na página **atribuir caixas de correio** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="93333-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="93333-134">Clique em **adicionar caixas de correio**.</span><span class="sxs-lookup"><span data-stu-id="93333-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="93333-135">Na saída exibida, execute uma das seguintes etapas para adicionar usuários individuais ou grupos:</span><span class="sxs-lookup"><span data-stu-id="93333-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="93333-136">Clique na caixa e role pela lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="93333-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="93333-137">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="93333-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="93333-138">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="93333-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="93333-139">Para remover entradas individuais da caixa, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no usuário ou grupo na caixa.</span><span class="sxs-lookup"><span data-stu-id="93333-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="93333-140">Para remover as entradas existentes da lista abaixo da caixa, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção na entrada.</span><span class="sxs-lookup"><span data-stu-id="93333-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="93333-141">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="93333-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="93333-142">Clique em **importar** para selecionar um arquivo de texto que contenha os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="93333-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="93333-143">Certifique-se de que o arquivo de texto contém uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="93333-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="93333-144">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93333-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="93333-145">Na página **rever tag** , revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="93333-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="93333-146">Você pode clicar em **Editar** na seção específica para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="93333-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="93333-147">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="93333-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="93333-148">Usar a central de segurança para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="93333-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="93333-149">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="93333-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="93333-150">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="93333-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="93333-151">Nos detalhes de somente leitura que aparecerem, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="93333-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="93333-152">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="93333-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="93333-153">Usar a central de segurança para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="93333-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="93333-154">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="93333-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="93333-155">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em **Editar marca**.</span><span class="sxs-lookup"><span data-stu-id="93333-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="93333-156">O assistente de política é aberto em uma **marca de edição** de saída. Clique em **Avançar** para revisar e modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="93333-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="93333-157">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="93333-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="93333-158">Usar a central de segurança para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="93333-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="93333-159">**Observação**: não é possível remover a marca de **conta de prioridade** interna.</span><span class="sxs-lookup"><span data-stu-id="93333-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="93333-160">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="93333-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="93333-161">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja remover, clique em **excluir marca**e selecione **Sim, remova** o aviso exibido.</span><span class="sxs-lookup"><span data-stu-id="93333-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
