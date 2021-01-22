---
title: Marcas de usuário no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a identificar grupos específicos de usuários com marcas de usuário no Microsoft Defender para Office 365 Plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Microsoft Defender para Office 365 para identificar rapidamente os usuários marcados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931429"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7f701-104">Marcas de usuário no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f701-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="7f701-105">O recurso de marcas de usuário está na Visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="7f701-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="7f701-106">Para obter informações sobre o cronograma de lançamento, confira o [mapa do Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="7f701-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="7f701-107">As marcas de usuário são identificadores para grupos específicos de usuários [no Microsoft Defender para Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="7f701-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="7f701-108">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="7f701-108">There are two types of user tags:</span></span>

- <span data-ttu-id="7f701-109">**Marcas do** sistema: Atualmente, as contas [de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) são o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="7f701-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="7f701-110">**Marcas personalizadas:** você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="7f701-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="7f701-111">Se sua organização tiver o Defender para Office 365 Plano 2 (incluído na sua assinatura ou como um complemento), você pode criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="7f701-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="7f701-112">Depois de aplicar marcas do sistema ou marcas personalizadas aos usuários, você pode usá-la como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="7f701-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="7f701-113">Alertas no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="7f701-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="7f701-114">Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="7f701-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="7f701-115">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="7f701-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="7f701-116">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="7f701-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="7f701-117">Para contas de prioridade, você pode usar os problemas de email para o relatório [de contas prioritárias](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="7f701-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="7f701-118">Este artigo explica como configurar marcas de usuário no Centro de Conformidade e & Segurança.</span><span class="sxs-lookup"><span data-stu-id="7f701-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="7f701-119">Não há cmdlets no Centro de Conformidade e Segurança & gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="7f701-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7f701-120">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="7f701-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7f701-121">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7f701-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7f701-122">Para ir diretamente para a **página De marcas de** usuário, abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="7f701-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="7f701-123">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="7f701-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7f701-124">Para criar, modificar e excluir marcas de usuário,  você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="7f701-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7f701-125">Para adicionar e remover membros de marcas de usuário existentes, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou **Operador** de Segurança</span><span class="sxs-lookup"><span data-stu-id="7f701-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="7f701-126">Para acesso somente leitura às marcas de usuário, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="7f701-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7f701-127">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7f701-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="7f701-128">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="7f701-128">**Notes**:</span></span>

  - <span data-ttu-id="7f701-129">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f701-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7f701-130">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="7f701-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="7f701-131">O gerenciamento de marca de usuário é controlado pelas funções Leitor **de Marca,** **Colaborador de Marca** e Gerenciador de **Marca.**</span><span class="sxs-lookup"><span data-stu-id="7f701-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="7f701-132">Você também pode gerenciar e monitorar contas prioritárias no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f701-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7f701-133">Para obter instruções, consulte [Gerenciar e monitorar contas de prioridade.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="7f701-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="7f701-134">Usar a Central de Segurança para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="7f701-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="7f701-135">Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**</span><span class="sxs-lookup"><span data-stu-id="7f701-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7f701-136">Na página **Marcas de usuário** que é aberta, clique em Criar **marca.**</span><span class="sxs-lookup"><span data-stu-id="7f701-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="7f701-137">O **assistente criar marca** é aberto em um novo fly out. Na página **Definir marca,** defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7f701-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="7f701-138">**Nome:** insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="7f701-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="7f701-139">Esse é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="7f701-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="7f701-140">**Descrição:** insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="7f701-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="7f701-141">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f701-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7f701-142">Na página **Atribuir usuários,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7f701-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="7f701-143">Clique **em Adicionar usuários.**</span><span class="sxs-lookup"><span data-stu-id="7f701-143">Click **Add users**.</span></span> <span data-ttu-id="7f701-144">No fly out exibido, faça uma das seguintes etapas para adicionar usuários ou grupos individuais:</span><span class="sxs-lookup"><span data-stu-id="7f701-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="7f701-145">Clique na caixa e role a lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="7f701-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="7f701-146">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="7f701-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="7f701-147">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="7f701-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="7f701-148">Para remover entradas individuais da  caixa, clique no ícone Remover do ![ usuário ou grupo na ](../../media/scc-remove-icon.png) caixa.</span><span class="sxs-lookup"><span data-stu-id="7f701-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="7f701-149">Para remover as entradas existentes da lista abaixo da caixa, clique no ícone **Remover** ![ da ](../../media/scc-remove-icon.png) entrada.</span><span class="sxs-lookup"><span data-stu-id="7f701-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="7f701-150">Quando terminar, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="7f701-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="7f701-151">Clique **em Importar** para selecionar um arquivo de texto que contém os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="7f701-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="7f701-152">Certifique-se de que o arquivo de texto contenha uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="7f701-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="7f701-153">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f701-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7f701-154">Na página **Revisar marca,** revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="7f701-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="7f701-155">Você pode clicar **em Editar** na seção específica para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="7f701-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="7f701-156">Quando terminar, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="7f701-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="7f701-157">Usar a Central de Segurança para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="7f701-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="7f701-158">Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**</span><span class="sxs-lookup"><span data-stu-id="7f701-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7f701-159">Na página **Marcas de** usuário que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="7f701-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="7f701-160">No submenu somente leitura exibido, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="7f701-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="7f701-161">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7f701-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="7f701-162">Usar a Central de Segurança para modificar as marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="7f701-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="7f701-163">Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**</span><span class="sxs-lookup"><span data-stu-id="7f701-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7f701-164">Na página **Marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em Editar **marca**.</span><span class="sxs-lookup"><span data-stu-id="7f701-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="7f701-165">O assistente de política é aberto em um **fly out de marca** de edição. Clique **em Próximo** para revisar e modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="7f701-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="7f701-166">Quando terminar, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="7f701-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="7f701-167">Usar a Central de Segurança para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="7f701-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="7f701-168">**Observação:** não é possível remover a marca da conta **Priority.**</span><span class="sxs-lookup"><span data-stu-id="7f701-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="7f701-169">Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**</span><span class="sxs-lookup"><span data-stu-id="7f701-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7f701-170">Na página **Marcas de** usuário que é aberta, selecione a marca de usuário que você deseja remover, clique em Excluir **marca** e **selecione Sim,** remova no aviso exibido.</span><span class="sxs-lookup"><span data-stu-id="7f701-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
