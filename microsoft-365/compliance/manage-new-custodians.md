---
title: Gerenciar custodiantes em um Advanced eDiscovery caso
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como exibir detalhes, editar e editar em massa a lista de custodiantes em Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739864"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="2f476-103">Gerenciar custodiantes em um Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="2f476-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="2f476-104">A página Custodians na guia **Fontes em** uma Advanced eDiscovery contém uma lista de todos os custodiantes que foram adicionados ao caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="2f476-105">Depois de adicionar os custodiantes a um caso, os detalhes sobre cada custodiante são coletados automaticamente do Azure Active Directory e podem ser visualizados Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2f476-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Gerenciar custodiantes](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="2f476-107">Exibir detalhes do custodiado</span><span class="sxs-lookup"><span data-stu-id="2f476-107">View custodian details</span></span>

<span data-ttu-id="2f476-108">Para exibir os detalhes sobre um custodiante, clique no custodiante da lista na **guia Custodiantes.** Uma página de sobrevoo é exibida e contém as seguintes informações sobre o custodiado:</span><span class="sxs-lookup"><span data-stu-id="2f476-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="2f476-109">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="2f476-109">Contact information</span></span>

  - <span data-ttu-id="2f476-110">**Nome de** exibição - O nome exibido no livro de endereços do custodiado.</span><span class="sxs-lookup"><span data-stu-id="2f476-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="2f476-111">Geralmente, essa é a combinação do nome do custodiante, inicial do meio e sobrenome.</span><span class="sxs-lookup"><span data-stu-id="2f476-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="2f476-112">**Email/SMTP** - O endereço SMTP principal do custodiante, por exemplo, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2f476-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="2f476-113">O nome principal do usuário (UPN) do custodiante também está listado.</span><span class="sxs-lookup"><span data-stu-id="2f476-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="2f476-114">**Título** - O cargo do custodiado.</span><span class="sxs-lookup"><span data-stu-id="2f476-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="2f476-115">**Departamento** - O nome do departamento no qual o custodiado trabalha.</span><span class="sxs-lookup"><span data-stu-id="2f476-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="2f476-116">**Gerente** - O gerente do custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="2f476-117">O gerente designado receberá comunicações de escalonamento desse custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="2f476-118">Informações de local</span><span class="sxs-lookup"><span data-stu-id="2f476-118">Location information</span></span>

  - <span data-ttu-id="2f476-119">**Cidade** - A cidade na qual o custodiado está localizado.</span><span class="sxs-lookup"><span data-stu-id="2f476-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="2f476-120">**Estado** - O estado ou a província no endereço do custodiado.</span><span class="sxs-lookup"><span data-stu-id="2f476-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="2f476-121">**País/Região** - O país/região onde o custodiatário está localizado.</span><span class="sxs-lookup"><span data-stu-id="2f476-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="2f476-122">**Office** - O local do escritório no local de trabalho do custodiado.</span><span class="sxs-lookup"><span data-stu-id="2f476-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="2f476-123">Informações de caso</span><span class="sxs-lookup"><span data-stu-id="2f476-123">Case information</span></span>

  - <span data-ttu-id="2f476-124">**Status de espera** - Indica se o custodiado foi colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="2f476-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="2f476-125">**Status da** comunicação : indica se o custodiado foi emitido um aviso de missão.</span><span class="sxs-lookup"><span data-stu-id="2f476-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="2f476-126">Se o custodiante tiver sido emitido um aviso, esse valor dessa propriedade será **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="2f476-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="2f476-127">Se o custodiante não tiver sido emitido um aviso, o status será **Não publicado**.</span><span class="sxs-lookup"><span data-stu-id="2f476-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="2f476-128">**Status** - O status do custodiante dentro do caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="2f476-129">Um status **ativo** indica que o custodiante faz parte do caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="2f476-130">Se um custodiante for liberado de um caso, o status será alterado para **Released**.</span><span class="sxs-lookup"><span data-stu-id="2f476-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="2f476-131">Fontes de dados e informações de indexação</span><span class="sxs-lookup"><span data-stu-id="2f476-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="2f476-132">**Fontes de** dados - mostra a contagem e o tipo de fontes de dados (caixas de correio, sites e Teams) que estão associadas ao custodiante e fazem parte do caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="2f476-133">**Hora atualizada do** índice - Indica a hora e a data para quando o trabalho de indexação avançada foi disparado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="2f476-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="2f476-134">Essa propriedade também indicará quando o processo avançado de indexação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="2f476-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="2f476-135">Editar um custodiado</span><span class="sxs-lookup"><span data-stu-id="2f476-135">Edit a custodian</span></span>

<span data-ttu-id="2f476-136">À medida que seu caso avança, você pode descobrir que pode haver fontes de dados adicionais relevantes para um custodiante específico & seu caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="2f476-137">Em outros cenários, talvez você queira remover determinadas fontes de dados que foram revisadas e consideradas não relevantes.</span><span class="sxs-lookup"><span data-stu-id="2f476-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="2f476-138">Para atualizar as fontes de dados associadas a um custodiante:</span><span class="sxs-lookup"><span data-stu-id="2f476-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="2f476-139">Vá para **a > Advanced eDiscovery** e abra o caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="2f476-140">Clique na **guia Fontes.**</span><span class="sxs-lookup"><span data-stu-id="2f476-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="2f476-141">Na página **Custodiantes,** selecione um custodiante na lista e clique em **Editar** na página de sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="2f476-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Editar Fontes de Dados](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="2f476-143">Clique **em Escolher fontes de** dados guia para alterar as configurações da caixa de correio Exchange do custodiante e OneDrive conta, clique em Escolher fontes de **dados**.</span><span class="sxs-lookup"><span data-stu-id="2f476-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="2f476-144">Clique na **guia Selecionar fontes de dados** adicionais para adicionar ou remover Teams, SharePoint ou Exchange caixas de correio associadas ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="2f476-145">Para obter mais informações sobre fontes de dados associadas a um custodiante, consulte [Add custodians to a case](add-custodians-to-case.md).</span><span class="sxs-lookup"><span data-stu-id="2f476-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="2f476-146">Clique **em Colocar reter a custodia** para habilitar ou desabilitar a responsabilidade do custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="2f476-147">Re indexar dados custodiados</span><span class="sxs-lookup"><span data-stu-id="2f476-147">Re-index custodian data</span></span>

<span data-ttu-id="2f476-148">Na maioria dos fluxos de trabalho de Descoberta Eletrônico para investigações legais, um subconjunto de dados de um custodiante é pesquisado depois que o custodiante é adicionado a um caso legal.</span><span class="sxs-lookup"><span data-stu-id="2f476-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="2f476-149">Devido a tamanhos de arquivo muito grandes ou possível corrupção de dados, alguns itens nas fontes de dados associadas a um custodiante podem ser parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="2f476-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="2f476-150">Usando o [recurso de indexação](indexing-custodian-data.md) avançada no Advanced eDiscovery, a maioria dos itens indexados parcialmente pode ser corrigida automaticamente re indexando esses itens sob demanda.</span><span class="sxs-lookup"><span data-stu-id="2f476-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="2f476-151">Quando um custodiante é adicionado a uma ocorrência, os dados localizados nas fontes de dados associadas ao custodiante são automaticamente indexados (pelo processo avançado de indexação).</span><span class="sxs-lookup"><span data-stu-id="2f476-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="2f476-152">Isso significa que você pode deixar os dados in-locar em vez de ter que baixá-los e remediar e, em seguida, pesquisá-los offline).</span><span class="sxs-lookup"><span data-stu-id="2f476-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="2f476-153">No entanto, durante o ciclo de vida de um caso legal, novas fontes de dados podem ser associadas a um custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="2f476-154">Nesse caso, você pode re indexar os dados do custodiante executando o processo avançado de indexação para correção de itens parcialmente indexados e atualizar o índice para os dados do custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="2f476-155">Para disparar o processo de re indexação para resolver itens parcialmente indexados:</span><span class="sxs-lookup"><span data-stu-id="2f476-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="2f476-156">Vá para **a > Advanced eDiscovery** e abra o caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="2f476-157">Clique na **guia Fontes.**</span><span class="sxs-lookup"><span data-stu-id="2f476-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="2f476-158">Na página **Custodiantes,** selecione um custodiante cujos dados devem ser reindexados.</span><span class="sxs-lookup"><span data-stu-id="2f476-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="2f476-159">Na página sobrevoo, clique em **Atualizar índice**.</span><span class="sxs-lookup"><span data-stu-id="2f476-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="2f476-160">Uma caixa de diálogo é exibida dizendo que o trabalho de índice foi criado.</span><span class="sxs-lookup"><span data-stu-id="2f476-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="2f476-161">A re indexação de dados de custodiante é um processo de longa duração; o trabalho correspondente criado é chamado **de Re-indexação de dados custodiados**.</span><span class="sxs-lookup"><span data-stu-id="2f476-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="2f476-162">Você pode acompanhar o progresso na guia **Trabalhos** ou na guia **Custodiantes** monitorando o status na coluna Status do trabalho **de indexação.**</span><span class="sxs-lookup"><span data-stu-id="2f476-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="2f476-163">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="2f476-163">For more information, see:</span></span>

- [<span data-ttu-id="2f476-164">Trabalhar com erros de processamento</span><span class="sxs-lookup"><span data-stu-id="2f476-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="2f476-165">Gerenciar tarefas</span><span class="sxs-lookup"><span data-stu-id="2f476-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="2f476-166">Liberar um custodiante de um caso</span><span class="sxs-lookup"><span data-stu-id="2f476-166">Release a custodian from a case</span></span>

<span data-ttu-id="2f476-167">Um custodiante é liberado em situações em que um caso é fechado, o custodiante não tem mais a obrigação de preservar o conteúdo de um caso ou quando o custodiante é considerado como não mais relevante para o caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="2f476-168">Se você liberar um custodiante depois que um aviso de hold foi publicado, um aviso de versão será enviado para o custodiante.</span><span class="sxs-lookup"><span data-stu-id="2f476-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="2f476-169">Além disso, todas as reteres colocadas em fontes de dados associadas ao custodiante são removidas.</span><span class="sxs-lookup"><span data-stu-id="2f476-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="2f476-170">Se o custodiante foi colocado em uma espera silenciosa *,* onde não foram emitidas notificações de responsabilidade legal, um aviso de liberação não será enviado, mas quaisquer reteres colocados em fontes de dados associadas a esse custodiante serão removidas.</span><span class="sxs-lookup"><span data-stu-id="2f476-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="2f476-171">Para liberar um custodiado:</span><span class="sxs-lookup"><span data-stu-id="2f476-171">To release a custodian:</span></span> 

1. <span data-ttu-id="2f476-172">Vá para **a > Advanced eDiscovery** e abra o caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="2f476-173">Clique na **guia Fontes.**</span><span class="sxs-lookup"><span data-stu-id="2f476-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="2f476-174">Na página **Custodiantes** e selecione o custodiante que está sendo liberado do caso.</span><span class="sxs-lookup"><span data-stu-id="2f476-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="2f476-175">Na página de sobrevoo, clique em **Liberar custodiante**.</span><span class="sxs-lookup"><span data-stu-id="2f476-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="2f476-176">Uma página de aviso é exibida explicando que, se uma responsabilidade for colocada em uma fonte de dados associada ao custodiante, a responsabilidade será removida e que qualquer outra reter associada a um caso de Advanced eDiscovery diferente ainda será aplicada.</span><span class="sxs-lookup"><span data-stu-id="2f476-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="2f476-177">Isso inclui outros tipos de recursos de preservação e retenção (como uma Microsoft 365 de retenção).</span><span class="sxs-lookup"><span data-stu-id="2f476-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="2f476-178">Clique **em Sim** para confirmar se deseja liberar o custodiado.</span><span class="sxs-lookup"><span data-stu-id="2f476-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="2f476-179">O status desse usuário na guia **Custodiantes** é definido como Liberado e o  **status** de Bloqueio na página de sobrevoo é alterado para **False**.</span><span class="sxs-lookup"><span data-stu-id="2f476-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="2f476-180">Um custodiado pode estar simultaneamente envolvido em vários casos legais.</span><span class="sxs-lookup"><span data-stu-id="2f476-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="2f476-181">Quando um custodiante é liberado de um caso, as resitências e notificações em outras questões não serão impactadas.</span><span class="sxs-lookup"><span data-stu-id="2f476-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="2f476-182">Custodiantes de edição em massa</span><span class="sxs-lookup"><span data-stu-id="2f476-182">Bulk-edit custodians</span></span>

<span data-ttu-id="2f476-183">Você pode usar o editor em massa para editar vários custodiantes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="2f476-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="2f476-184">Para fazer isso, selecione dois ou mais custodiantes na guia **Custodiantes** para exibir o editor em massa e clique em uma das tarefas.</span><span class="sxs-lookup"><span data-stu-id="2f476-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Página de sobrevoo para editar configurações de vários custodiantes](../media/AeDBulkEditCustodians.png)
