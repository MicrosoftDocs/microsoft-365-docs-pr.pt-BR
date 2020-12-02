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
ms.openlocfilehash: 136de95addae7dcd48de2c6ac1f30ce67714817c
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552014"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a5136-104">Marcas de usuário no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a5136-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="a5136-105">O recurso de marcas de usuário está em visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="a5136-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="a5136-106">Para obter informações sobre o cronograma de lançamento, confira o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="a5136-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="a5136-107">Marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="a5136-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="a5136-108">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="a5136-108">There are two types of user tags:</span></span>

- <span data-ttu-id="a5136-109">**Marcas de sistema**: atualmente, [contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) é o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="a5136-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="a5136-110">**Marcas personalizadas**: você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="a5136-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="a5136-111">Se sua organização tiver o defender para Office 365 plano 2 (incluído na sua assinatura ou como um complemento), você poderá criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="a5136-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="a5136-112">Após aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="a5136-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="a5136-113">Alertas no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="a5136-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="a5136-114">Gerenciador de ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="a5136-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="a5136-115">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="a5136-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="a5136-116">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="a5136-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="a5136-117">Para contas de prioridade, você pode usar o [relatório de problemas de email para contas de prioridade](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) no centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="a5136-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="a5136-118">Este artigo explica como configurar marcas de usuário no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5136-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="a5136-119">Não há cmdlets no centro de conformidade & segurança para gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="a5136-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a5136-120">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a5136-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a5136-121">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a5136-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a5136-122">Para ir diretamente para a página **marcas do usuário** , abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="a5136-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="a5136-123">Para criar, modificar ou remover **marcas de usuário personalizadas**, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5136-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a5136-124">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a5136-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a5136-125">Para configurar contas de prioridade (marcas de sistema), você precisa ser um [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou um [administrador do Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="a5136-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="a5136-126">Você também pode gerenciar e monitorar contas de prioridade no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5136-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a5136-127">Para obter instruções, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="a5136-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="a5136-128">Usar a central de segurança para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="a5136-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="a5136-129">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a5136-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a5136-130">Na página **marcas de usuário** que é aberta, clique em **criar marca**.</span><span class="sxs-lookup"><span data-stu-id="a5136-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="a5136-131">O assistente **criar marca** é aberto em uma nova saída. Na página **definir marca** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a5136-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="a5136-132">**Name**: Insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="a5136-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="a5136-133">Este é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="a5136-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="a5136-134">**Descrição**: Insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="a5136-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="a5136-135">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5136-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a5136-136">Na página **atribuir usuários** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a5136-136">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="a5136-137">Clique em **Adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="a5136-137">Click **Add users**.</span></span> <span data-ttu-id="a5136-138">Na saída exibida, execute uma das seguintes etapas para adicionar usuários individuais ou grupos:</span><span class="sxs-lookup"><span data-stu-id="a5136-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="a5136-139">Clique na caixa e role pela lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="a5136-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="a5136-140">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="a5136-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="a5136-141">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="a5136-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="a5136-142">Para remover entradas individuais da caixa, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no usuário ou grupo na caixa.</span><span class="sxs-lookup"><span data-stu-id="a5136-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="a5136-143">Para remover as entradas existentes da lista abaixo da caixa, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção na entrada.</span><span class="sxs-lookup"><span data-stu-id="a5136-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="a5136-144">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a5136-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="a5136-145">Clique em **importar** para selecionar um arquivo de texto que contenha os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="a5136-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="a5136-146">Certifique-se de que o arquivo de texto contém uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="a5136-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="a5136-147">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5136-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a5136-148">Na página **rever tag** , revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="a5136-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="a5136-149">Você pode clicar em **Editar** na seção específica para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="a5136-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="a5136-150">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a5136-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="a5136-151">Usar a central de segurança para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="a5136-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="a5136-152">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a5136-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a5136-153">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="a5136-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="a5136-154">Nos detalhes de somente leitura que aparecerem, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="a5136-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="a5136-155">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a5136-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="a5136-156">Usar a central de segurança para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="a5136-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="a5136-157">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a5136-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a5136-158">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em **Editar marca**.</span><span class="sxs-lookup"><span data-stu-id="a5136-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="a5136-159">O assistente de política é aberto em uma **marca de edição** de saída. Clique em **Avançar** para revisar e modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="a5136-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="a5136-160">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a5136-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="a5136-161">Usar a central de segurança para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="a5136-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="a5136-162">**Observação**: não é possível remover a marca de **conta de prioridade** interna.</span><span class="sxs-lookup"><span data-stu-id="a5136-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="a5136-163">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a5136-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a5136-164">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja remover, clique em **excluir marca** e selecione **Sim, remova** o aviso exibido.</span><span class="sxs-lookup"><span data-stu-id="a5136-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
