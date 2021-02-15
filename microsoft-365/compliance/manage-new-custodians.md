---
title: Gerenciar custodiantes em um caso de Descoberta Avançada
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
description: Saiba como exibir detalhes, editar e editar em massa a lista de custodiantes em um caso de Descoberta Avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739864"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="3857d-103">Gerenciar custodiantes em um caso de Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="3857d-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="3857d-104">A página Custodians na guia **Fontes** em um caso de Descoberta Avançada contém uma lista de todos os custodiantes que foram adicionados à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3857d-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="3857d-105">Depois de adicionar custodiantes a uma ocorrência, os detalhes sobre cada custodiante são coletados automaticamente do Azure Active Directory e podem ser visualizados na Descoberta Automática Avançada.</span><span class="sxs-lookup"><span data-stu-id="3857d-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Gerenciar custodiantes](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="3857d-107">Exibir detalhes custodiados</span><span class="sxs-lookup"><span data-stu-id="3857d-107">View custodian details</span></span>

<span data-ttu-id="3857d-108">Para exibir os detalhes sobre um custodiante, clique no custodiante na lista na **guia Custodiantes.** Uma página de flyout é exibida e contém as seguintes informações sobre o custodiatário:</span><span class="sxs-lookup"><span data-stu-id="3857d-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="3857d-109">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="3857d-109">Contact information</span></span>

  - <span data-ttu-id="3857d-110">**Nome para Exibição** - O nome exibido no livro de endereços do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="3857d-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="3857d-111">Geralmente, essa é a combinação do nome, da inicial do meio e do sobrenome do custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="3857d-112">**Email/SMTP** - O endereço SMTP principal do custodiante, por exemplo, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="3857d-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="3857d-113">O upN (nome upn) do usuário custodiante também está listado.</span><span class="sxs-lookup"><span data-stu-id="3857d-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="3857d-114">**Cargo** - O cargo do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="3857d-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="3857d-115">**Departamento** - O nome do departamento no qual o custodiatário trabalha.</span><span class="sxs-lookup"><span data-stu-id="3857d-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="3857d-116">**Gerente** - O gerente do custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="3857d-117">O gerente designado receberá as comunicações de escalonamento desse custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="3857d-118">Informações de localização</span><span class="sxs-lookup"><span data-stu-id="3857d-118">Location information</span></span>

  - <span data-ttu-id="3857d-119">**Cidade** - A cidade em que o custodiatário está localizado.</span><span class="sxs-lookup"><span data-stu-id="3857d-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="3857d-120">**Estado** - O estado ou província no endereço do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="3857d-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="3857d-121">**País/região** - O país/região onde o custodiatário está localizado.</span><span class="sxs-lookup"><span data-stu-id="3857d-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="3857d-122">**Office** - O local do escritório no local de trabalho do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="3857d-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="3857d-123">Informações sobre a ocorrência</span><span class="sxs-lookup"><span data-stu-id="3857d-123">Case information</span></span>

  - <span data-ttu-id="3857d-124">**Status de** espera - Indica se o custodiatário foi colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="3857d-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="3857d-125">**Status de** comunicação: indica se o custodiatário recebeu um aviso de espera.</span><span class="sxs-lookup"><span data-stu-id="3857d-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="3857d-126">Se o custodiante tiver sido emitido um aviso, esse valor dessa propriedade será **Publicado.**</span><span class="sxs-lookup"><span data-stu-id="3857d-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="3857d-127">Se o custodiante não tiver sido emitido um aviso, o status será **Não Publicado.**</span><span class="sxs-lookup"><span data-stu-id="3857d-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="3857d-128">**Status** - O status do custodiante dentro da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3857d-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="3857d-129">Um status **ativo** indica que o custodiante faz parte do caso.</span><span class="sxs-lookup"><span data-stu-id="3857d-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="3857d-130">Se um custodiante for liberado de uma ocorrência, o status será alterado para **Liberado.**</span><span class="sxs-lookup"><span data-stu-id="3857d-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="3857d-131">Fontes de dados e informações de indexação</span><span class="sxs-lookup"><span data-stu-id="3857d-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="3857d-132">**Fontes de** dados – mostra a contagem e o tipo de fontes de dados (caixas de correio, sites e Teams) que estão associadas ao custodiante e fazem parte do caso.</span><span class="sxs-lookup"><span data-stu-id="3857d-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="3857d-133">**Tempo de atualização do** índice - Indica a hora e a data de quando o trabalho de indexação avançada foi disparado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="3857d-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="3857d-134">Essa propriedade também indicará quando o processo avançado de indexação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="3857d-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="3857d-135">Editar um custodiatário</span><span class="sxs-lookup"><span data-stu-id="3857d-135">Edit a custodian</span></span>

<span data-ttu-id="3857d-136">À medida que seu caso progride, você pode descobrir que pode haver fontes de dados adicionais relevantes para um custodiante & seu caso.</span><span class="sxs-lookup"><span data-stu-id="3857d-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="3857d-137">Em outros cenários, talvez você queira remover determinadas fontes de dados que foram revisadas e consideradas não relevantes.</span><span class="sxs-lookup"><span data-stu-id="3857d-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="3857d-138">Para atualizar as fontes de dados associadas a um custodiante:</span><span class="sxs-lookup"><span data-stu-id="3857d-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="3857d-139">Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3857d-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="3857d-140">Clique na **guia** Fontes.</span><span class="sxs-lookup"><span data-stu-id="3857d-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="3857d-141">Na página **Custodiantes,** selecione um custodiante na lista e clique em **Editar** na página do flyout.</span><span class="sxs-lookup"><span data-stu-id="3857d-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Editar Fontes de Dados](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="3857d-143">Clique **na guia Escolher fontes** de dados para alterar as configurações da caixa de correio do Exchange do custodiante e da conta do OneDrive, clique em Escolher fontes de **dados.**</span><span class="sxs-lookup"><span data-stu-id="3857d-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="3857d-144">Clique na **guia Selecionar fontes de dados adicionais** para adicionar ou remover caixas de correio do Teams, SharePoint ou Exchange associadas ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="3857d-145">Para obter mais informações sobre fontes de dados associadas a um custodiante, consulte [Adicionar custodiantes a uma ocorrência.](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="3857d-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="3857d-146">Clique **em Colocar reter custodiante** para habilitar ou desabilitar a espera do custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="3857d-147">Re-indexar dados custodiante</span><span class="sxs-lookup"><span data-stu-id="3857d-147">Re-index custodian data</span></span>

<span data-ttu-id="3857d-148">Na maioria dos fluxos de trabalho de Descoberta Eletrônico para investigações legais, um subconjunto de dados de um custodiante é pesquisado depois que o custodiante é adicionado a um caso jurídico.</span><span class="sxs-lookup"><span data-stu-id="3857d-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="3857d-149">Devido a tamanhos de arquivo muito grandes ou possível corrupção de dados, alguns itens nas fontes de dados associadas a um custodiante podem ser parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="3857d-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="3857d-150">Usando o recurso de [indexação](indexing-custodian-data.md) avançada na Descoberta Automática Avançada, os itens mais parcialmente indexados podem ser automaticamente remediados pela indexação desses itens sob demanda.</span><span class="sxs-lookup"><span data-stu-id="3857d-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="3857d-151">Quando um custodiante é adicionado a uma ocorrência, os dados localizados nas fontes de dados associadas ao custodiante são indexados automaticamente (pelo processo avançado de indexação).</span><span class="sxs-lookup"><span data-stu-id="3857d-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="3857d-152">Isso significa que você pode deixar os dados no local em vez de ter que baixá-los e remedia-los e, em seguida, pesquisá-los offline).</span><span class="sxs-lookup"><span data-stu-id="3857d-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="3857d-153">No entanto, durante o ciclo de vida de um caso jurídico, novas fontes de dados podem ser associadas a um custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="3857d-154">Nesse caso, você pode indexar os dados do custodiante executando o processo de indexação avançado para remediar todos os itens parcialmente indexados e atualizar o índice dos dados do custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="3857d-155">Para disparar o processo de indexação para lidar com itens parcialmente indexados:</span><span class="sxs-lookup"><span data-stu-id="3857d-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="3857d-156">Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3857d-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="3857d-157">Clique na **guia** Fontes.</span><span class="sxs-lookup"><span data-stu-id="3857d-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="3857d-158">Na página **Custodiantes,** selecione um custodiante cujos dados devem ser reindexados.</span><span class="sxs-lookup"><span data-stu-id="3857d-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="3857d-159">Na página do flyout, clique em **Atualizar índice.**</span><span class="sxs-lookup"><span data-stu-id="3857d-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="3857d-160">Uma caixa de diálogo é exibida dizendo que o trabalho de índice foi criado.</span><span class="sxs-lookup"><span data-stu-id="3857d-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="3857d-161">A indexação de dados custodiante é um processo de longa execução; o trabalho correspondente criado é denominado **re-indexação de dados custodiante**.</span><span class="sxs-lookup"><span data-stu-id="3857d-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="3857d-162">Você pode acompanhar o progresso na guia **Trabalhos** ou na guia **Custodiantes** monitorando o status na coluna Status do **trabalho de Indexação.**</span><span class="sxs-lookup"><span data-stu-id="3857d-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="3857d-163">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="3857d-163">For more information, see:</span></span>

- [<span data-ttu-id="3857d-164">Trabalhar com erros de processamento</span><span class="sxs-lookup"><span data-stu-id="3857d-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="3857d-165">Gerenciar tarefas</span><span class="sxs-lookup"><span data-stu-id="3857d-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="3857d-166">Liberar um custodiante de uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="3857d-166">Release a custodian from a case</span></span>

<span data-ttu-id="3857d-167">Um custodiante é liberado em situações em que um caso é fechado, o custodiante não está mais sob a obrigação de preservar o conteúdo de uma ocorrência ou quando o custodiante é considerado não mais relevante para o caso.</span><span class="sxs-lookup"><span data-stu-id="3857d-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="3857d-168">Se você liberar um custodiante após a publicação de um aviso de espera, uma notificação de liberação será enviada ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="3857d-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="3857d-169">Além disso, todas as reteres colocadas em fontes de dados que foram associadas ao custodiante serão removidas.</span><span class="sxs-lookup"><span data-stu-id="3857d-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="3857d-170">Se o custodiante foi colocado em uma espera silenciosa *,* onde não foram emitidas notificações de responsabilidade legal, uma notificação de liberação não será enviada, mas todas as reteres colocadas em fontes de dados que foram associadas a esse custodiante serão removidas.</span><span class="sxs-lookup"><span data-stu-id="3857d-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="3857d-171">Para liberar um custodiatário:</span><span class="sxs-lookup"><span data-stu-id="3857d-171">To release a custodian:</span></span> 

1. <span data-ttu-id="3857d-172">Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3857d-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="3857d-173">Clique na **guia** Fontes.</span><span class="sxs-lookup"><span data-stu-id="3857d-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="3857d-174">Na página **Custodians** e selecione o custodiante que está sendo liberado da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3857d-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="3857d-175">Na página do flyout, clique em **Liberar custodiante.**</span><span class="sxs-lookup"><span data-stu-id="3857d-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="3857d-176">Uma página de aviso é exibida explicando que, se uma isenção for aplicada a uma fonte de dados associada ao custodiante, a isenção será removida e que qualquer outra isenção associada a um caso de Descoberta Avançada diferente ainda será aplicada.</span><span class="sxs-lookup"><span data-stu-id="3857d-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="3857d-177">Isso inclui outros tipos de recursos de preservação e retenção (como uma política de retenção do Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="3857d-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="3857d-178">Clique **em Sim** para confirmar que você deseja liberar o custodiatário.</span><span class="sxs-lookup"><span data-stu-id="3857d-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="3857d-179">O status desse usuário na guia **Custodians** é definido como Liberado e o **status** de Espera na página do flyout é alterado para **False**. </span><span class="sxs-lookup"><span data-stu-id="3857d-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="3857d-180">Um custodiatário pode estar envolvido simultaneamente em vários casos legais.</span><span class="sxs-lookup"><span data-stu-id="3857d-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="3857d-181">Quando um custodiante é liberado de uma ocorrência, as iseções e notificações em outras questões não serão impactadas.</span><span class="sxs-lookup"><span data-stu-id="3857d-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="3857d-182">Custodiantes de edição em massa</span><span class="sxs-lookup"><span data-stu-id="3857d-182">Bulk-edit custodians</span></span>

<span data-ttu-id="3857d-183">Você pode usar o editor em massa para editar vários custodiantes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3857d-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="3857d-184">Para fazer isso, basta selecionar dois ou mais custodiantes na guia **Custodiantes** para exibir o editor em massa e clicar em uma das tarefas.</span><span class="sxs-lookup"><span data-stu-id="3857d-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Página de flyout para editar configurações de vários custodiantes](../media/AeDBulkEditCustodians.png)
