---
title: Configurar a Descoberta Avançada no Microsoft 365
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
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar a Descoberta Avançada para que você possa começar a criar e gerenciar casos. Ele também descreve as assinaturas e o licenciamento necessários da Microsoft. Depois de concluir algumas etapas rápidas, a ferramenta Descoberta Avançada estará pronta para uso.
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841172"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="2e5f2-105">Configurar a Descoberta Avançada do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e5f2-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="2e5f2-106">A Descoberta Avançada no Microsoft 365 fornece um fluxo de trabalho de ponta [a](overview-ediscovery-20.md#advanced-ediscovery-workflow) ponta para preservar, coletar, analisar, analisar e exportar dados que respondem às investigações internas e externas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="2e5f2-107">Nada é necessário para implantar a Descoberta Avançada, mas há algumas tarefas de pré-requisito que um administrador de IT e gerente de Descobertas Ele precisa concluir antes que sua organização possa começar a criar e usar ocorrências de Descoberta e Avançada para gerenciar suas investigações.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="2e5f2-108">Este artigo discute as etapas necessárias para configurar a Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="2e5f2-109">Isso inclui garantir o licenciamento adequado necessário para acessar a Descoberta Avançada e adicionar responsáveis aos casos e atribuir permissões à sua equipe jurídica e de investigação para que eles possam acessar e gerenciar casos.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="2e5f2-110">Etapa 1: Verificar e atribuir licenças apropriadas</span><span class="sxs-lookup"><span data-stu-id="2e5f2-110">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="2e5f2-111">O licenciamento para a Descoberta Avançada requer a assinatura da organização apropriada e o licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-111">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="2e5f2-112">**Assinatura da organização:** Para acessar a Descoberta Avançada no centro de conformidade do Microsoft 365 ou no Centro de Conformidade e Segurança &, sua organização deve ter um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2e5f2-112">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="2e5f2-113">Assinatura do Microsoft 365 E5 ou do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="2e5f2-113">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="2e5f2-114">Assinatura do Microsoft 365 E3 com complemento de Conformidade E5</span><span class="sxs-lookup"><span data-stu-id="2e5f2-114">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="2e5f2-115">Assinatura do Microsoft 365 E3 com Descoberta e Auditoria do E5</span><span class="sxs-lookup"><span data-stu-id="2e5f2-115">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="2e5f2-116">Se você não tiver um plano existente do Microsoft 365 E5 e quiser experimentar [a](https://www.microsoft.com/microsoft-365/enterprise) Descoberta Avançada, adicione o [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-116">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="2e5f2-117">**Licenciamento por usuário:** Para adicionar um usuário como um custodiante em um caso de Descoberta Antecipada, esse usuário deve ter uma das seguintes licenças, dependendo da sua assinatura de organização:</span><span class="sxs-lookup"><span data-stu-id="2e5f2-117">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="2e5f2-118">Microsoft 365: os usuários devem ter uma licença do Microsoft 365 E5, uma licença de complemento de Conformidade do E5 ou uma licença de complemento de Descoberta e Auditoria E5.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-118">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="2e5f2-119">Office 365: os usuários devem ter uma licença do Office 365 E5 atribuída.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-119">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="2e5f2-120">Para obter informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="2e5f2-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="2e5f2-121">Os usuários só precisam de uma licença E5 (ou a licença de complemento apropriada) para serem adicionados como custodiantes a um caso de Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-121">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="2e5f2-122">Administradores de IT, gerentes de eDiscovery, advogados, assistentes jurídicos ou investigadores que usam a Descoberta Avançada para gerenciar casos e analisar dados de caso não precisam de uma licença E5 ou complemento.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-122">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="2e5f2-123">Etapa 2: Atribuir permissões de Descoberta eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2e5f2-123">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="2e5f2-124">Para acessar a Descoberta Avançada ou adicionado como membro de um caso de Descoberta Avançada, um usuário deve ter as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-124">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="2e5f2-125">Especificamente, um usuário deve ser adicionado como membro do grupo de função Gerente de Descobertas & Segurança.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-125">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="2e5f2-126">Os membros desse grupo de função podem criar e gerenciar ocorrências de Descobertas Avançadas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-126">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="2e5f2-127">Eles podem adicionar e remover membros, colocar responsáveis e locais de conteúdo em espera, gerenciar notificações de responsabilidade legal, criar e editar pesquisas associadas em um caso, adicionar resultados de pesquisa a um conjunto de revisão, analisar dados em um conjunto de revisão e exportar e baixar de um caso de Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-127">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="2e5f2-128">Conclua as seguintes etapas para adicionar usuários ao grupo de funções do Gerente de Descobertas e Descobertas:</span><span class="sxs-lookup"><span data-stu-id="2e5f2-128">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="2e5f2-129">Acesse e [https://protection.office.com/permissions](https://protection.office.com/permissions) entre usando as credenciais de uma conta de administrador em sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="2e5f2-130">Na página **Permissões,** selecione o grupo **de funções do Gerente** de Descobertas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-130">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="2e5f2-131">Na página do flyout do Gerenciador de Descobertas Do eDiscovery, clique em **Editar** ao lado da **seção Gerenciador de Descobertas.**</span><span class="sxs-lookup"><span data-stu-id="2e5f2-131">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="2e5f2-132">Na página **Escolher Gerenciador de Descobertas Do** Assistente de Grupo de Função de Edição, clique em Escolher Gerente de Descoberta **e.**</span><span class="sxs-lookup"><span data-stu-id="2e5f2-132">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="2e5f2-133">Clique **em Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-133">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="2e5f2-134">Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito.**</span><span class="sxs-lookup"><span data-stu-id="2e5f2-134">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="2e5f2-135">Clique **em** Salvar para adicionar os usuários ao grupo de funções e clique **em Fechar** para concluir a etapa.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-135">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="2e5f2-136">Mais informações sobre o grupo de funções do Gerente de Descobertas</span><span class="sxs-lookup"><span data-stu-id="2e5f2-136">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="2e5f2-137">Há dois subgrupos no grupo de funções do Gerente de Descobertas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-137">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="2e5f2-138">A diferença entre esses subgrupos está no escopo.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-138">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="2e5f2-139">**Gerente de Descobertas EDiscovery:** Pode exibir e gerenciar os casos de Descoberta eDiscovery Avançada que eles criam ou dos quais são membros.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-139">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="2e5f2-140">Se outro Gerente de Descoberta eDiscovery criar uma ocorrência, mas não adicionar um segundo Gerente de Descobertas Como membro desse caso, o segundo Gerente de Descobertas eDiscovery não poderá exibir ou abrir a ocorrência na página DescobertaScoberta Avançada no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-140">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="2e5f2-141">Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo Gerente de Descobertas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-141">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="2e5f2-142">**Administrador de Descobertas EDiscovery:** Pode executar todas as tarefas de gerenciamento de ocorrências que um Gerente de Descobertas Descoberta Pode fazer.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-142">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="2e5f2-143">Além disso, um Administrador de Descoberta Eletrônica pode:</span><span class="sxs-lookup"><span data-stu-id="2e5f2-143">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="2e5f2-144">Exibir todos os casos listados na página Descobertas Avançadas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-144">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="2e5f2-145">Gerencie qualquer caso na organização depois de adicionar a si mesmo como um membro da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-145">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="2e5f2-146">Acessar e exportar dados de ocorrência para qualquer caso na organização.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-146">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="2e5f2-147">Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores que sejam membros do subgrupo Administradores de Descobertas e Descobertas.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-147">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="2e5f2-148">Para obter mais informações sobre permissões de Descobertas e uma descrição de cada função atribuída ao grupo de função gerente de Descobertas eDiscovery, consulte Atribuir permissões de [Descoberta eDiscovery](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2e5f2-148">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="2e5f2-149">Etapa 3: Definir as configurações globais para a Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="2e5f2-149">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="2e5f2-150">A última etapa a ser concluída antes que as pessoas em sua organização comecem a criar e usar casos é definir configurações globais que se apliquem a todos os casos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-150">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="2e5f2-151">No momento, a única configuração global é a detecção de privilégio *advogado-cliente* (mais configurações globais estarão disponíveis no futuro).</span><span class="sxs-lookup"><span data-stu-id="2e5f2-151">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="2e5f2-152">Essa configuração permite que o modelo de privilégio advogado-cliente seja executado quando você analisar dados em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-152">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="2e5f2-153">O modelo usa o aprendizado de máquina para determinar a probabilidade de que um documento contenha conteúdo legal por natureza.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-153">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="2e5f2-154">Ele também compara os participantes dos documentos com uma lista de advogados (que você envia ao configurar o modelo) para determinar se um documento tem pelo menos um participante que seja advogado.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-154">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="2e5f2-155">Para obter mais informações sobre como configurar e usar o modelo de detecção de privilégio advogado-cliente, consulte Configurar detecção de privilégio [advogado-cliente](attorney-privilege-detection.md)na Descoberta Automática Avançada.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-155">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2e5f2-156">Esta é uma etapa opcional que você pode executar a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-156">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="2e5f2-157">Não implementar o modelo de detecção de privilégio advogado-cliente não impede que você criar e usar casos de Descoberta Automática Avançada.</span><span class="sxs-lookup"><span data-stu-id="2e5f2-157">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2e5f2-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2e5f2-158">Next steps</span></span>

<span data-ttu-id="2e5f2-159">Depois de configurar a Descoberta Avançada, você estará pronto para [criar uma ocorrência.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="2e5f2-159">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>
