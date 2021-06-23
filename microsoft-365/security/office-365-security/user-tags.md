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
description: Os administradores podem aprender a identificar grupos específicos de usuários com marcas de usuário no Microsoft Defender para Office 365 Plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Microsoft Defender para Office 365 identificar rapidamente os usuários marcados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083111"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="44a2f-104">Marcas de usuário no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="44a2f-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="44a2f-105">O recurso de marcas de usuário está em Visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="44a2f-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="44a2f-106">Para obter informações sobre o cronograma de lançamento, confira [o roteiro Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="44a2f-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="44a2f-107">As marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="44a2f-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="44a2f-108">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="44a2f-108">There are two types of user tags:</span></span>

- <span data-ttu-id="44a2f-109">**Marcas do** sistema : Atualmente, [contas de prioridade](../../admin/setup/priority-accounts.md) é o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="44a2f-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="44a2f-110">**Marcas personalizadas**: você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="44a2f-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="44a2f-111">Se sua organização tiver o Defender para Office 365 Plano 2 (incluído na sua assinatura ou como complemento), você poderá criar marcas de usuário personalizadas, além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="44a2f-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="44a2f-112">Atualmente, você só pode aplicar marcas de usuário a usuários de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="44a2f-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="44a2f-113">Depois de aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="44a2f-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="44a2f-114">Alertas</span><span class="sxs-lookup"><span data-stu-id="44a2f-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="44a2f-115">Políticas de alerta personalizadas</span><span class="sxs-lookup"><span data-stu-id="44a2f-115">Custom alert policies</span></span>](../../compliance/alert-policies.md#viewing-alerts)
- [<span data-ttu-id="44a2f-116">Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="44a2f-116">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="44a2f-117">Página de entidade de email</span><span class="sxs-lookup"><span data-stu-id="44a2f-117">Email entity page</span></span>](mdo-email-entity-page.md#other-innovations)
- [<span data-ttu-id="44a2f-118">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="44a2f-118">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="44a2f-119">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="44a2f-119">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="44a2f-120">Para contas prioritárias, você pode usar o [relatório Problemas de email](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) para contas prioritárias no centro de administração Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="44a2f-120">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="44a2f-121">Este artigo explica como configurar marcas de usuário no Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="44a2f-121">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="44a2f-122">Não há cmdlets no portal Microsoft 365 Defender gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="44a2f-122">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="44a2f-123">Para ver como as marcas de usuário fazem parte da estratégia para ajudar a proteger contas de usuário de alto impacto, consulte [Recomendações](security-recommendations-for-priority-accounts.md)de segurança para contas de prioridade em Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="44a2f-123">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44a2f-124">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="44a2f-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="44a2f-125">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="44a2f-125">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="44a2f-126">Para ir diretamente para a **página Marcas de** usuário, abra <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="44a2f-126">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="44a2f-127">Você precisa ter permissões atribuídas no portal Microsoft 365 Defender antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="44a2f-127">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="44a2f-128">Para criar, modificar e excluir marcas de usuário, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="44a2f-128">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="44a2f-129">Para adicionar e remover membros de marcas de usuário existentes, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Operador **de** Segurança</span><span class="sxs-lookup"><span data-stu-id="44a2f-129">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="44a2f-130">Para acesso somente leitura a marcas de usuário, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="44a2f-130">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="44a2f-131">Para obter mais informações, veja [Permissões no portal do Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="44a2f-131">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="44a2f-132">Adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44a2f-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="44a2f-133">Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="44a2f-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="44a2f-134">O gerenciamento de marca de usuário é controlado pelas funções **Leitor de Marca e** Gerenciador de **Marca.**</span><span class="sxs-lookup"><span data-stu-id="44a2f-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="44a2f-135">Você também pode gerenciar e monitorar contas de prioridade no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44a2f-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="44a2f-136">Para obter instruções, consulte [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="44a2f-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="44a2f-137">Para obter informações sobre como proteger contas _privilegiadas_ (contas de administrador), consulte [este tópico](/azure/architecture/framework/security/critical-impact-accounts).</span><span class="sxs-lookup"><span data-stu-id="44a2f-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="44a2f-138">Usar o portal Microsoft 365 Defender para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="44a2f-138">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="44a2f-139">No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-139">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="44a2f-140">Na página **Marcas de usuário,** clique em ![ Criar ícone de marca Criar ](../../media/m365-cc-sc-create-icon.png) **marca**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-140">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="44a2f-141">O **assistente Criar marca** é aberto em um novo sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="44a2f-141">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="44a2f-142">Na página **Definir marca,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="44a2f-142">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="44a2f-143">**Nome**: insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="44a2f-143">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="44a2f-144">Esse é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="44a2f-144">This is the value that you'll see and use.</span></span> <span data-ttu-id="44a2f-145">Observe que você não pode renomear uma marca depois de criar.</span><span class="sxs-lookup"><span data-stu-id="44a2f-145">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="44a2f-146">**Descrição**: insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="44a2f-146">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="44a2f-147">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="44a2f-148">Na página **Atribuir membros,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="44a2f-148">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="44a2f-149">Clique ![ em Adicionar ícone de membros Adicionar ](../../media/m365-cc-sc-create-icon.png) **membros**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-149">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="44a2f-150">No fly out que aparece, faça qualquer uma das etapas a seguir para adicionar usuários ou grupos individuais:</span><span class="sxs-lookup"><span data-stu-id="44a2f-150">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="44a2f-151">Clique na caixa e role a lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="44a2f-151">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="44a2f-152">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="44a2f-152">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="44a2f-153">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="44a2f-153">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="44a2f-154">Para remover entradas individuais, clique em</span><span class="sxs-lookup"><span data-stu-id="44a2f-154">To remove individual entries, click</span></span> ![Remover ícone de entrada](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="44a2f-156">ao lado da entrada na caixa.</span><span class="sxs-lookup"><span data-stu-id="44a2f-156">next to the entry in the box.</span></span>
     - <span data-ttu-id="44a2f-157">Para remover todas as entradas, clique em Remover ícone de entrada no item Usuários de nn selecionados e grupos ![ ](../../media/m365-cc-sc-remove-selection-icon.png) de **nn** abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="44a2f-157">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="44a2f-158">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-158">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="44a2f-159">De volta à **página Atribuir membros,** você também pode remover entradas clicando em ![ Excluir ícone ao lado da ](../../media/m365-cc-sc-delete-icon.png) entrada.</span><span class="sxs-lookup"><span data-stu-id="44a2f-159">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="44a2f-160">Clique **em Importar** para selecionar um arquivo de texto que contém os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="44a2f-160">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="44a2f-161">Certifique-se de que o arquivo de texto contenha uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="44a2f-161">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="44a2f-162">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="44a2f-163">Na página **Revisar marca** que aparece, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="44a2f-163">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="44a2f-164">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="44a2f-164">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="44a2f-165">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="44a2f-165">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="44a2f-166">Quando terminar, clique em **Enviar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-166">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="44a2f-167">Usar o portal Microsoft 365 Defender para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="44a2f-167">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="44a2f-168">No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-168">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="44a2f-169">Na página **Marcas de usuário,** as seguintes propriedades são exibidas na lista de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="44a2f-169">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="44a2f-170">**Tag**: O nome da marca do usuário.</span><span class="sxs-lookup"><span data-stu-id="44a2f-170">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="44a2f-171">Observe que isso inclui a marca do sistema de conta **de prioridade** integrado.</span><span class="sxs-lookup"><span data-stu-id="44a2f-171">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="44a2f-172">**Aplicado a**: O número de membros</span><span class="sxs-lookup"><span data-stu-id="44a2f-172">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="44a2f-173">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="44a2f-173">**Last modified**</span></span>
   - <span data-ttu-id="44a2f-174">**Criado em**</span><span class="sxs-lookup"><span data-stu-id="44a2f-174">**Created on**</span></span>

3. <span data-ttu-id="44a2f-175">Quando você seleciona uma marca de usuário clicando no nome, os detalhes são exibidos em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="44a2f-175">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="44a2f-176">Usar o portal Microsoft 365 Defender para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="44a2f-176">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="44a2f-177">No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-177">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="44a2f-178">Na página **Marcas de usuário,** selecione a marca do usuário na lista e clique em Editar ícone ![ de marca Editar ](../../media/m365-cc-sc-edit-icon.png) **marca**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-178">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="44a2f-179">No sobremenu de detalhes exibido, o mesmo assistente e configurações estão disponíveis conforme descrito na seção Usar o portal Microsoft 365 Defender [para](#use-the-microsoft-365-defender-portal-to-create-user-tags) criar marcas de usuário anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="44a2f-179">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="44a2f-180">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="44a2f-180">**Notes**:</span></span>

   - <span data-ttu-id="44a2f-181">A **página Definir marca** não está disponível para a marca do sistema de conta **De** prioridade, portanto, você não pode renomear essa marca ou alterar a descrição.</span><span class="sxs-lookup"><span data-stu-id="44a2f-181">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="44a2f-182">Você não pode renomear uma marca personalizada, mas pode alterar a descrição.</span><span class="sxs-lookup"><span data-stu-id="44a2f-182">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="44a2f-183">Usar o portal Microsoft 365 Defender para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="44a2f-183">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="44a2f-184">Não é possível remover a marca do sistema de conta **De prioridade** integrado.</span><span class="sxs-lookup"><span data-stu-id="44a2f-184">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="44a2f-185">No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-185">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="44a2f-186">Na página **Marcas de usuário,** selecione a marca do usuário na lista e clique em Excluir ícone ![ de marca Excluir ](../../media/m365-cc-sc-delete-icon.png) **marca**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-186">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="44a2f-187">Leia o aviso na caixa de diálogo de confirmação exibida e clique em **Sim, remova**.</span><span class="sxs-lookup"><span data-stu-id="44a2f-187">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
