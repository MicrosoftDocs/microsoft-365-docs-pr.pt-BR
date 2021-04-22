---
title: Marcas de usuário no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 2c1dc426bae77cd35b567bf166032855327a8ffe
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943006"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8dd21-104">Marcas de usuário no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8dd21-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="8dd21-105">O recurso de marcas de usuário está em Visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="8dd21-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="8dd21-106">Para obter informações sobre o cronograma de lançamento, confira o [roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="8dd21-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="8dd21-107">As marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8dd21-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="8dd21-108">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="8dd21-108">There are two types of user tags:</span></span>

- <span data-ttu-id="8dd21-109">**Marcas do** sistema : Atualmente, [contas de prioridade](../../admin/setup/priority-accounts.md) é o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="8dd21-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="8dd21-110">**Marcas personalizadas**: você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="8dd21-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="8dd21-111">Se sua organização tiver o Defender for Office 365 Plan 2 (incluído na sua assinatura ou como complemento), você poderá criar marcas de usuário personalizadas, além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="8dd21-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="8dd21-112">Atualmente, você só pode aplicar marcas de usuário a usuários de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="8dd21-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="8dd21-113">Depois de aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="8dd21-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="8dd21-114">Alertas no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="8dd21-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="8dd21-115">Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="8dd21-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="8dd21-116">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="8dd21-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="8dd21-117">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="8dd21-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="8dd21-118">Para contas prioritárias, você pode usar o [relatório Problemas de email](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) para contas de prioridade no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="8dd21-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="8dd21-119">Este artigo explica como configurar marcas de usuário no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="8dd21-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="8dd21-120">Não há cmdlets no Centro de Conformidade & segurança para gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="8dd21-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="8dd21-121">Para ver como as marcas de usuário fazem parte da estratégia para ajudar a proteger contas de usuário de alto impacto, consulte Recomendações de segurança para contas de prioridade [no Microsoft 365](security-recommendations-for-priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="8dd21-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8dd21-122">Se você usar o centro de segurança unificado do Microsoft 365, poderá definir marcas aqui: https://security.microsoft.com/userTags .</span><span class="sxs-lookup"><span data-stu-id="8dd21-122">If you use the unified Microsoft 365 security center, you can set tags here: https://security.microsoft.com/userTags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8dd21-123">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="8dd21-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8dd21-124">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8dd21-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8dd21-125">Para ir diretamente para a **página Marcas de** usuário, abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="8dd21-125">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="8dd21-126">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="8dd21-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8dd21-127">Para criar, modificar e excluir marcas de usuário, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="8dd21-127">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8dd21-128">Para adicionar e remover membros de marcas de usuário existentes, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Operador **de** Segurança</span><span class="sxs-lookup"><span data-stu-id="8dd21-128">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="8dd21-129">Para acesso somente leitura a marcas de usuário, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="8dd21-129">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8dd21-130">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8dd21-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="8dd21-131">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="8dd21-131">**Notes**:</span></span>

  - <span data-ttu-id="8dd21-132">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dd21-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8dd21-133">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8dd21-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8dd21-134">O gerenciamento de marca de usuário é controlado pelas funções **Leitor de Marca e** Gerenciador de **Marca.**</span><span class="sxs-lookup"><span data-stu-id="8dd21-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="8dd21-135">Você também pode gerenciar e monitorar contas de prioridade no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dd21-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8dd21-136">Para obter instruções, consulte [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="8dd21-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="8dd21-137">Para obter informações sobre como proteger contas _privilegiadas_ (contas de administrador), consulte [este tópico](/azure/architecture/framework/security/critical-impact-accounts).</span><span class="sxs-lookup"><span data-stu-id="8dd21-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="8dd21-138">Use o Centro de Conformidade & segurança para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="8dd21-138">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="8dd21-139">No Centro de Conformidade & segurança, acesse Marcas **de** usuário de gerenciamento \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="8dd21-139">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8dd21-140">Na página **Marcas de usuário** abertas, clique em Criar **marca**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-140">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="8dd21-141">O **assistente Criar marca** é aberto em um novo fly out. Na página **Definir marca,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8dd21-141">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="8dd21-142">**Nome**: insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="8dd21-142">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="8dd21-143">Esse é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="8dd21-143">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="8dd21-144">**Descrição**: insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="8dd21-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="8dd21-145">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8dd21-146">Na página **Atribuir usuários,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8dd21-146">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="8dd21-147">Clique **em Adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-147">Click **Add users**.</span></span> <span data-ttu-id="8dd21-148">No fly out que aparece, faça qualquer uma das etapas a seguir para adicionar usuários ou grupos individuais:</span><span class="sxs-lookup"><span data-stu-id="8dd21-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="8dd21-149">Clique na caixa e role a lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="8dd21-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="8dd21-150">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="8dd21-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="8dd21-151">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="8dd21-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="8dd21-152">Para remover entradas individuais da caixa, clique em **Remover** ícone Remover no ![ usuário ou grupo na ](../../media/scc-remove-icon.png) caixa.</span><span class="sxs-lookup"><span data-stu-id="8dd21-152">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="8dd21-153">Para remover entradas existentes da lista abaixo da caixa, clique em **Remover** ![ ícone Remover da ](../../media/scc-remove-icon.png) entrada.</span><span class="sxs-lookup"><span data-stu-id="8dd21-153">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="8dd21-154">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-154">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="8dd21-155">Clique **em Importar** para selecionar um arquivo de texto que contém os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="8dd21-155">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="8dd21-156">Certifique-se de que o arquivo de texto contenha uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="8dd21-156">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="8dd21-157">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-157">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8dd21-158">Na página **Revisar marca,** revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="8dd21-158">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="8dd21-159">Você pode clicar **em Editar** na seção específica para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="8dd21-159">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="8dd21-160">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="8dd21-161">Use o Centro de Conformidade & segurança para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="8dd21-161">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="8dd21-162">No Centro de Conformidade & segurança, acesse Marcas **de** usuário de gerenciamento \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="8dd21-162">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8dd21-163">Na página **Marcas de** usuário abertas, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="8dd21-163">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="8dd21-164">Nos detalhes somente leitura exibidos, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="8dd21-164">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="8dd21-165">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-165">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="8dd21-166">Use o Centro de Conformidade & segurança para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="8dd21-166">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="8dd21-167">No Centro de Conformidade & segurança, acesse Marcas **de** usuário de gerenciamento \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="8dd21-167">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8dd21-168">Na página **Marcas de usuário** abertas, selecione a marca de usuário que você deseja exibir e clique em Editar **marca**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-168">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="8dd21-169">O assistente de política é aberto em uma **marca Editar.** Clique **em Próximo** para revisar e modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="8dd21-169">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="8dd21-170">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8dd21-170">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="8dd21-171">Use o Centro de Conformidade & segurança para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="8dd21-171">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="8dd21-172">**Observação**: não é possível remover a marca de conta **De prioridade.**</span><span class="sxs-lookup"><span data-stu-id="8dd21-172">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="8dd21-173">No Centro de Conformidade & segurança, acesse Marcas **de** usuário de gerenciamento \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="8dd21-173">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8dd21-174">Na página **Marcas de** usuário abertas, selecione a marca de usuário que você deseja remover, clique em Excluir **marca** e selecione **Sim, remova** no aviso exibido.</span><span class="sxs-lookup"><span data-stu-id="8dd21-174">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>