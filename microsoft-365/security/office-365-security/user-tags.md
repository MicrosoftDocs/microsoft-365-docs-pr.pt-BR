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
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879163"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="344e7-104">Marcas de usuário no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="344e7-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="344e7-105">O recurso de marcas de usuário está em Visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="344e7-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="344e7-106">Para obter informações sobre o cronograma de lançamento, confira [o roteiro Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="344e7-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="344e7-107">As marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="344e7-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="344e7-108">Há dois tipos de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="344e7-108">There are two types of user tags:</span></span>

- <span data-ttu-id="344e7-109">**Marcas do** sistema : Atualmente, [contas de prioridade](../../admin/setup/priority-accounts.md) é o único tipo de marca do sistema.</span><span class="sxs-lookup"><span data-stu-id="344e7-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="344e7-110">**Marcas personalizadas**: você mesmo cria essas marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="344e7-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="344e7-111">Se sua organização tiver o Defender para Office 365 Plano 2 (incluído na sua assinatura ou como complemento), você poderá criar marcas de usuário personalizadas, além de usar a marca de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="344e7-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="344e7-112">Atualmente, você só pode aplicar marcas de usuário a usuários de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="344e7-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="344e7-113">Depois de aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:</span><span class="sxs-lookup"><span data-stu-id="344e7-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="344e7-114">Alertas</span><span class="sxs-lookup"><span data-stu-id="344e7-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="344e7-115">Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="344e7-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="344e7-116">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="344e7-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="344e7-117">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="344e7-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="344e7-118">Para contas prioritárias, você pode usar o [relatório Problemas de email](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) para contas prioritárias no centro de administração Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="344e7-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="344e7-119">Este artigo explica como configurar marcas de usuário no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="344e7-119">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="344e7-120">Não há cmdlets no portal Microsoft 365 Defender para gerenciar marcas de usuário.</span><span class="sxs-lookup"><span data-stu-id="344e7-120">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="344e7-121">Para ver como as marcas de usuário fazem parte da estratégia para ajudar a proteger contas de usuário de alto impacto, consulte [Recomendações](security-recommendations-for-priority-accounts.md)de segurança para contas de prioridade em Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="344e7-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="344e7-122">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="344e7-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="344e7-123">Você abre o portal Microsoft 365 Defender em <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="344e7-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="344e7-124">Para ir diretamente para a **página Marcas de** usuário, abra <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="344e7-124">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="344e7-125">Você precisa ter permissões atribuídas no portal Microsoft 365 Defender antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="344e7-125">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="344e7-126">Para criar, modificar e excluir marcas de usuário, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="344e7-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="344e7-127">Para adicionar e remover membros de marcas de usuário existentes, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Operador **de** Segurança</span><span class="sxs-lookup"><span data-stu-id="344e7-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="344e7-128">Para acesso somente leitura a marcas de usuário, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="344e7-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="344e7-129">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="344e7-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="344e7-130">Adicionar usuários à função de Azure Active Directory correspondente no centro de administração Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ do Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="344e7-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="344e7-131">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="344e7-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="344e7-132">O gerenciamento de marca de usuário é controlado pelas funções **Leitor de Marca e** Gerenciador de **Marca.**</span><span class="sxs-lookup"><span data-stu-id="344e7-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="344e7-133">Você também pode gerenciar e monitorar contas de prioridade no Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="344e7-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="344e7-134">Para obter instruções, consulte [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="344e7-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="344e7-135">Para obter informações sobre como proteger contas _privilegiadas_ (contas de administrador), consulte [este tópico](/azure/architecture/framework/security/critical-impact-accounts).</span><span class="sxs-lookup"><span data-stu-id="344e7-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="344e7-136">Usar o portal Microsoft 365 Defender para criar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="344e7-136">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="344e7-137">No portal Microsoft 365 Defender, acesse **Configurações** \> **Email & de** usuário de \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="344e7-137">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="344e7-138">Na página **Marcas de usuário,** clique em ![ Criar ícone de marca Criar ](../../media/m365-cc-sc-create-icon.png) **marca**.</span><span class="sxs-lookup"><span data-stu-id="344e7-138">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="344e7-139">O **assistente Criar marca** é aberto em um novo sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="344e7-139">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="344e7-140">Na página **Definir marca,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="344e7-140">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="344e7-141">**Nome**: insira um nome exclusivo e descritivo para a marca.</span><span class="sxs-lookup"><span data-stu-id="344e7-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="344e7-142">Esse é o valor que você verá e usará.</span><span class="sxs-lookup"><span data-stu-id="344e7-142">This is the value that you'll see and use.</span></span> <span data-ttu-id="344e7-143">Observe que você não pode renomear uma marca depois de criar.</span><span class="sxs-lookup"><span data-stu-id="344e7-143">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="344e7-144">**Descrição**: insira uma descrição opcional para a marca.</span><span class="sxs-lookup"><span data-stu-id="344e7-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="344e7-145">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="344e7-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="344e7-146">Na página **Atribuir membros,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="344e7-146">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="344e7-147">Clique ![ em Adicionar ícone de membros Adicionar ](../../media/m365-cc-sc-create-icon.png) **membros**.</span><span class="sxs-lookup"><span data-stu-id="344e7-147">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="344e7-148">No fly out que aparece, faça qualquer uma das etapas a seguir para adicionar usuários ou grupos individuais:</span><span class="sxs-lookup"><span data-stu-id="344e7-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="344e7-149">Clique na caixa e role a lista para selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="344e7-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="344e7-150">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="344e7-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="344e7-151">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="344e7-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="344e7-152">Para remover entradas individuais, clique em</span><span class="sxs-lookup"><span data-stu-id="344e7-152">To remove individual entries, click</span></span> ![Remover ícone de entrada](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="344e7-154">ao lado da entrada na caixa.</span><span class="sxs-lookup"><span data-stu-id="344e7-154">next to the entry in the box.</span></span>
     - <span data-ttu-id="344e7-155">Para remover todas as entradas, clique em Remover ícone de entrada no item Usuários de nn selecionados e grupos ![ ](../../media/m365-cc-sc-remove-selection-icon.png) de **nn** abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="344e7-155">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="344e7-156">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="344e7-156">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="344e7-157">De volta à **página Atribuir membros,** você também pode remover entradas clicando em ![ Excluir ícone ao lado da ](../../media/m365-cc-sc-delete-icon.png) entrada.</span><span class="sxs-lookup"><span data-stu-id="344e7-157">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="344e7-158">Clique **em Importar** para selecionar um arquivo de texto que contém os endereços de email dos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="344e7-158">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="344e7-159">Certifique-se de que o arquivo de texto contenha uma entrada por linha.</span><span class="sxs-lookup"><span data-stu-id="344e7-159">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="344e7-160">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="344e7-160">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="344e7-161">Na página **Revisar marca** que aparece, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="344e7-161">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="344e7-162">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="344e7-162">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="344e7-163">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="344e7-163">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="344e7-164">Quando terminar, clique em **Enviar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="344e7-164">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="344e7-165">Usar o portal Microsoft 365 Defender para exibir marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="344e7-165">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="344e7-166">No portal Microsoft 365 Defender, acesse **Configurações** \> **Email & de** usuário de \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="344e7-166">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="344e7-167">Na página **Marcas de usuário,** as seguintes propriedades são exibidas na lista de marcas de usuário:</span><span class="sxs-lookup"><span data-stu-id="344e7-167">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="344e7-168">**Tag**: O nome da marca do usuário.</span><span class="sxs-lookup"><span data-stu-id="344e7-168">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="344e7-169">Observe que isso inclui a marca do sistema de conta **de prioridade** integrado.</span><span class="sxs-lookup"><span data-stu-id="344e7-169">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="344e7-170">**Aplicado a**: O número de membros</span><span class="sxs-lookup"><span data-stu-id="344e7-170">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="344e7-171">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="344e7-171">**Last modified**</span></span>
   - <span data-ttu-id="344e7-172">**Criado em**</span><span class="sxs-lookup"><span data-stu-id="344e7-172">**Created on**</span></span>

3. <span data-ttu-id="344e7-173">Quando você seleciona uma marca de usuário clicando no nome, os detalhes são exibidos em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="344e7-173">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="344e7-174">Usar o portal Microsoft 365 Defender para modificar marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="344e7-174">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="344e7-175">No portal Microsoft 365 Defender, acesse **Configurações** \> **Email & de** usuário de \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="344e7-175">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="344e7-176">Na página **Marcas de usuário,** selecione a marca do usuário na lista e clique em Editar ícone ![ de marca Editar ](../../media/m365-cc-sc-edit-icon.png) **marca**.</span><span class="sxs-lookup"><span data-stu-id="344e7-176">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="344e7-177">No sobremenu de detalhes que aparece, o mesmo assistente e configurações estão disponíveis conforme descrito no portal Usar o [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) para criar a seção de marcas de usuário anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="344e7-177">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="344e7-178">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="344e7-178">**Notes**:</span></span>

   - <span data-ttu-id="344e7-179">A **página Definir marca** não está disponível para a marca do sistema de conta **De** prioridade, portanto, você não pode renomear essa marca ou alterar a descrição.</span><span class="sxs-lookup"><span data-stu-id="344e7-179">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="344e7-180">Você não pode renomear uma marca personalizada, mas pode alterar a descrição.</span><span class="sxs-lookup"><span data-stu-id="344e7-180">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="344e7-181">Usar o portal Microsoft 365 Defender para remover marcas de usuário</span><span class="sxs-lookup"><span data-stu-id="344e7-181">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="344e7-182">Não é possível remover a marca do sistema de conta **De prioridade** integrado.</span><span class="sxs-lookup"><span data-stu-id="344e7-182">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="344e7-183">No portal Microsoft 365 Defender, acesse **Configurações** \> **Email & de** usuário de \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="344e7-183">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="344e7-184">Na página **Marcas de usuário,** selecione a marca do usuário na lista e clique em Excluir ícone ![ de marca Excluir ](../../media/m365-cc-sc-delete-icon.png) **marca**.</span><span class="sxs-lookup"><span data-stu-id="344e7-184">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="344e7-185">Leia o aviso na caixa de diálogo de confirmação exibida e clique em **Sim, remova**.</span><span class="sxs-lookup"><span data-stu-id="344e7-185">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
