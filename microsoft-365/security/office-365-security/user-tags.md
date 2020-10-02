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
ms.openlocfilehash: 9522499b3861f0f0e44fcbf09896a5c93feed95d
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337248"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="9001d-104">Marcas de usuário no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="9001d-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="9001d-105">As marcas de usuário são identificadores de grupos específicos de usuários no [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="9001d-106">[As contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) são um tipo de marca de usuário.</span><span class="sxs-lookup"><span data-stu-id="9001d-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="9001d-107">Se sua organização tiver o plano de ATP 2 do Office 365 (incluído na sua assinatura ou como um complemento), você poderá criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="9001d-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="9001d-108">Após aplicar marcas a usuários específicos, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="9001d-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="9001d-109">Alertas no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="9001d-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="9001d-110">Gerenciador de ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="9001d-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="9001d-111">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="9001d-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="9001d-112">Modos de exibição de campanha</span><span class="sxs-lookup"><span data-stu-id="9001d-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="9001d-113">Este artigo explica como configurar marcas de usuário no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="9001d-113">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="9001d-114">Não há cmdlets no centro de conformidade & segurança para gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="9001d-114">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9001d-115">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="9001d-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9001d-116">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9001d-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9001d-117">Para ir diretamente para a página **marcas do usuário** , abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="9001d-117">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="9001d-118">Para criar, modificar ou remover marcas de usuário, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="9001d-118">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="9001d-119">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9001d-120">Você também pode gerenciar e monitorar contas de prioridade no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9001d-120">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9001d-121">Para obter instruções, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="9001d-121">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="9001d-122">Usar a central de segurança para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="9001d-122">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="9001d-123">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="9001d-123">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="9001d-124">Na página **marcas de usuário** que é aberta, clique em **criar marca**.</span><span class="sxs-lookup"><span data-stu-id="9001d-124">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="9001d-125">O assistente **criar marca** é aberto em uma nova saída. Na página **definir marca** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="9001d-125">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="9001d-126">**Name**: Insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="9001d-126">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="9001d-127">Este é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="9001d-127">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="9001d-128">**Descrição**: Insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="9001d-128">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="9001d-129">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9001d-129">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9001d-130">Na página **atribuir caixas de correio** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9001d-130">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="9001d-131">Clique em **adicionar caixas de correio**.</span><span class="sxs-lookup"><span data-stu-id="9001d-131">Click **Add mailboxes**.</span></span> <span data-ttu-id="9001d-132">Na saída exibida, execute uma das seguintes etapas para adicionar usuários individuais ou grupos:</span><span class="sxs-lookup"><span data-stu-id="9001d-132">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="9001d-133">Clique na caixa e role pela lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="9001d-133">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="9001d-134">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="9001d-134">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="9001d-135">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="9001d-135">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="9001d-136">Para remover entradas individuais da caixa, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no usuário ou grupo na caixa.</span><span class="sxs-lookup"><span data-stu-id="9001d-136">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="9001d-137">Para remover as entradas existentes da lista abaixo da caixa, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção na entrada.</span><span class="sxs-lookup"><span data-stu-id="9001d-137">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="9001d-138">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9001d-138">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="9001d-139">Clique em **importar** para selecionar um arquivo de texto que contenha os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="9001d-139">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="9001d-140">Certifique-se de que o arquivo de texto contém uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="9001d-140">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="9001d-141">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9001d-141">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9001d-142">Na página **rever tag** , revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="9001d-142">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="9001d-143">Você pode clicar em **Editar** na seção específica para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="9001d-143">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="9001d-144">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9001d-144">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="9001d-145">Usar a central de segurança para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="9001d-145">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="9001d-146">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="9001d-146">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="9001d-147">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="9001d-147">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="9001d-148">Nos detalhes de somente leitura que aparecerem, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="9001d-148">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="9001d-149">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9001d-149">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="9001d-150">Usar a central de segurança para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="9001d-150">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="9001d-151">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="9001d-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="9001d-152">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em **Editar marca**.</span><span class="sxs-lookup"><span data-stu-id="9001d-152">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="9001d-153">O assistente de política é aberto em uma **marca de edição** de saída. Clique em **Avançar** para revisar e modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="9001d-153">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="9001d-154">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9001d-154">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="9001d-155">Usar a central de segurança para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="9001d-155">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="9001d-156">**Observação**: não é possível remover a marca de **conta de prioridade** interna.</span><span class="sxs-lookup"><span data-stu-id="9001d-156">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="9001d-157">Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="9001d-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="9001d-158">Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja remover, clique em **excluir marca**e selecione **Sim, remova** o aviso exibido.</span><span class="sxs-lookup"><span data-stu-id="9001d-158">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
