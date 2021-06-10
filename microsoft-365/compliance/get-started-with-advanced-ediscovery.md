---
title: Configurar Advanced eDiscovery no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar o Advanced eDiscovery para que você possa começar a criar e gerenciar casos. Ele também descreve as assinaturas e licenciamento necessários da Microsoft. Depois de concluir algumas etapas rápidas, a Advanced eDiscovery ferramenta estará pronta para uso.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919737"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="743b5-105">Configurar Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="743b5-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="743b5-106">Advanced eDiscovery no Microsoft 365 fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar dados que respondem às investigações internas e externas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="743b5-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="743b5-107">Nada é necessário para implantar o Advanced eDiscovery, mas há algumas tarefas de pré-requisitos que um administrador de IT e o gerente de Descobertas Online precisam concluir antes que sua organização possa começar a criar e usar Advanced eDiscovery casos para gerenciar suas investigações.</span><span class="sxs-lookup"><span data-stu-id="743b5-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="743b5-108">Este artigo discute as etapas a seguir necessárias para configurar Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="743b5-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![Etapas para configurar Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="743b5-110">Isso inclui garantir o licenciamento adequado necessário para acessar Advanced eDiscovery e adicionar custodiantes a casos e atribuir permissões à sua equipe legal e de investigação para que eles possam acessar e gerenciar casos.</span><span class="sxs-lookup"><span data-stu-id="743b5-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="743b5-111">Etapa 1: Verificar e atribuir licenças apropriadas</span><span class="sxs-lookup"><span data-stu-id="743b5-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="743b5-112">O licenciamento para Advanced eDiscovery requer a assinatura da organização apropriada e o licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="743b5-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="743b5-113">Para ver uma lista de requisitos de licenciamento para Advanced eDiscovery, consulte [Assinaturas e licenciamento.](overview-ediscovery-20.md#subscriptions-and-licensing)</span><span class="sxs-lookup"><span data-stu-id="743b5-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="743b5-114">Etapa 2: Atribuir permissões de Descoberta e</span><span class="sxs-lookup"><span data-stu-id="743b5-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="743b5-115">Para acessar Advanced eDiscovery ou adicionado como membro de um caso Advanced eDiscovery, um usuário deve ter as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="743b5-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="743b5-116">Especificamente, um usuário deve ser adicionado como membro do grupo de funções do Gerenciador de Descobertas e no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="743b5-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="743b5-117">Os membros desse grupo de funções podem criar e gerenciar Advanced eDiscovery casos.</span><span class="sxs-lookup"><span data-stu-id="743b5-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="743b5-118">Eles podem adicionar e remover membros, colocar custodiantes e locais de conteúdo em espera, gerenciar notificações de avaliação legal, criar e editar pesquisas associadas em um caso, adicionar resultados de pesquisa a um conjunto de revisão, analisar dados em um conjunto de revisão e exportar e baixar de um caso de Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="743b5-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="743b5-119">Conclua as etapas a seguir para adicionar usuários ao grupo de funções do Gerenciador de Descobertas E:</span><span class="sxs-lookup"><span data-stu-id="743b5-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="743b5-120">Acesse e entre usando as credenciais de uma conta <https://protection.office.com/permissions> de administrador em sua Microsoft 365 organização.</span><span class="sxs-lookup"><span data-stu-id="743b5-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="743b5-121">Na página **Permissões,** selecione o grupo de função **Gerenciador de** Descobertas.</span><span class="sxs-lookup"><span data-stu-id="743b5-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="743b5-122">Na página de sobrevoo do Gerenciador de Descobertas e, em Seguida, clique em **Editar** ao lado da **seção Gerenciador de** Descobertas E.</span><span class="sxs-lookup"><span data-stu-id="743b5-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="743b5-123">Na página **Escolher Gerente de** Descoberta Virtual no assistente editar grupo de funções, clique em Escolher Gerenciador de **Descobertas E.**</span><span class="sxs-lookup"><span data-stu-id="743b5-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="743b5-124">Clique **em Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="743b5-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="743b5-125">Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito**.</span><span class="sxs-lookup"><span data-stu-id="743b5-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="743b5-126">Clique **em Salvar** para adicionar os usuários ao grupo de funções e clique em **Fechar** para concluir a etapa.</span><span class="sxs-lookup"><span data-stu-id="743b5-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="743b5-127">Mais informações sobre o grupo de funções do Gerenciador de Descobertas E</span><span class="sxs-lookup"><span data-stu-id="743b5-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="743b5-128">Há dois subgrupos no grupo de funções do Gerenciador de Descobertas.</span><span class="sxs-lookup"><span data-stu-id="743b5-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="743b5-129">A diferença entre esses subgrupos está no escopo.</span><span class="sxs-lookup"><span data-stu-id="743b5-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="743b5-130">**EDiscovery Manager**: pode exibir e gerenciar os Advanced eDiscovery casos dos quais eles criam ou são membros.</span><span class="sxs-lookup"><span data-stu-id="743b5-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="743b5-131">Se outro Gerenciador de Descobertas De eDiscovery criar uma ocorrência, mas não adicionar um segundo Gerenciador de Descobertas Deeconsutórias como membro desse caso, o segundo Gerente de Descoberta Desdiscovery não poderá exibir ou abrir o caso na página Advanced eDiscovery no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="743b5-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="743b5-132">Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo do Gerenciador de Descobertas.</span><span class="sxs-lookup"><span data-stu-id="743b5-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="743b5-133">**Administrador de Descoberta e**: pode executar todas as tarefas de gerenciamento de caso que um Gerenciador de Descobertas E pode fazer.</span><span class="sxs-lookup"><span data-stu-id="743b5-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="743b5-134">Além disso, um Administrador de Descoberta Eletrônica pode:</span><span class="sxs-lookup"><span data-stu-id="743b5-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="743b5-135">Exibir todos os casos listados na página Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="743b5-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="743b5-136">Gerenciar qualquer caso na organização após adicionarem a si mesmos como membros do caso.</span><span class="sxs-lookup"><span data-stu-id="743b5-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="743b5-137">Acessar e exportar dados de caso de qualquer caso na organização.</span><span class="sxs-lookup"><span data-stu-id="743b5-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="743b5-138">Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores que são membros do subgrupo de Administradores da Descoberta Eletrônica.</span><span class="sxs-lookup"><span data-stu-id="743b5-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="743b5-139">Para obter mais informações sobre permissões de Descoberta E e uma descrição de cada função atribuída ao grupo de funções do Gerenciador de Descobertas E, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="743b5-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="743b5-140">Etapa 3: Configurar configurações globais para Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="743b5-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="743b5-141">A última etapa a ser concluída antes que as pessoas em sua organização comecem a criar e usar casos é configurar as configurações globais que se aplicam a todos os casos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="743b5-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="743b5-142">Neste momento, a única configuração global é a detecção de privilégio *advogado-cliente* (mais configurações globais estarão disponíveis no futuro).</span><span class="sxs-lookup"><span data-stu-id="743b5-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="743b5-143">Essa configuração permite que o modelo de privilégio advogado-cliente seja executado quando você analisa dados em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="743b5-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="743b5-144">O modelo usa o aprendizado de máquina para determinar a probabilidade de que um documento contenha conteúdo que seja legal por natureza.</span><span class="sxs-lookup"><span data-stu-id="743b5-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="743b5-145">Ele também compara os participantes dos documentos com uma lista de advogados (que você envia ao configurar o modelo) para determinar se um documento tem pelo menos um participante que é um advogado.</span><span class="sxs-lookup"><span data-stu-id="743b5-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="743b5-146">Para obter mais informações sobre como configurar e usar o modelo de detecção de privilégio advogado-cliente, consulte Configurar a detecção de privilégio [advogado-cliente em Advanced eDiscovery](attorney-privilege-detection.md).</span><span class="sxs-lookup"><span data-stu-id="743b5-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="743b5-147">Esta é uma etapa opcional que você pode executar a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="743b5-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="743b5-148">Não implementar o modelo de detecção de privilégio advogado-cliente não o impede de criar e usar Advanced eDiscovery casos.</span><span class="sxs-lookup"><span data-stu-id="743b5-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="743b5-149">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="743b5-149">Next steps</span></span>

<span data-ttu-id="743b5-150">Depois de configurar Advanced eDiscovery, você estará pronto para [criar um caso](create-and-manage-advanced-ediscoveryv2-case.md).</span><span class="sxs-lookup"><span data-stu-id="743b5-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>