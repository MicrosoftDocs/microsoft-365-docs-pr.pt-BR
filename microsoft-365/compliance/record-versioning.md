---
title: Use o controle de versão de registro para atualizar os registros armazenados no SharePoint ou no OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre os registros para ajudá-lo na implementação de uma solução de gerenciamento de registros no Microsoft 365.
ms.openlocfilehash: 943bf3949ab57eb4603695495d7a8ca0c4b90db7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695225"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="878fd-103">Use o controle de versão de registro para atualizar os registros armazenados no SharePoint ou no OneDrive</span><span class="sxs-lookup"><span data-stu-id="878fd-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="878fd-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="878fd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="878fd-105">A capacidade de marcar um documento como [registro](records.md) e restringir as ações que podem ser executadas no registro é uma meta essencial para qualquer solução de gerenciamento de registros.</span><span class="sxs-lookup"><span data-stu-id="878fd-105">The ability to mark a document as a [record](records.md) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="878fd-106">No entanto, a colaboração também pode ser necessária para as pessoas criarem versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="878fd-106">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="878fd-107">Por exemplo, você pode marcar um contrato de vendas como registro, mas precisa atualizar o contrato com novos termos e marcar a versão mais recente como novo registro enquanto ainda mantém a versão do registro anterior.</span><span class="sxs-lookup"><span data-stu-id="878fd-107">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="878fd-108">Para esses tipos de cenários, o SharePoint e o OneDrive oferecem suporte ao *controle de versão do registro*.</span><span class="sxs-lookup"><span data-stu-id="878fd-108">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="878fd-109">As pastas do bloco de anotações do OneNote não oferecem suporte ao controle de versão do registro.</span><span class="sxs-lookup"><span data-stu-id="878fd-109">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="878fd-110">Para usar o controle de versão de registro, primeiro [rotule o documento e marque-o como registro](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="878fd-110">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="878fd-111">Nesse momento, uma propriedade do documento, chamada *Status do registro* será exibida ao lado do rótulo de retenção e o status inicial do registro será **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="878fd-111">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="878fd-112">Agora, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="878fd-112">You can now do the following things:</span></span>

  - <span data-ttu-id="878fd-113">**Editar e reter continuamente versões individuais do documento como registros, desbloqueando e bloqueando a propriedade de Status do registro.**</span><span class="sxs-lookup"><span data-stu-id="878fd-113">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="878fd-114">Somente quando a propriedade **Status do registro** é definida como **Bloqueado** será mantida uma nova versão do registro.</span><span class="sxs-lookup"><span data-stu-id="878fd-114">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="878fd-115">Essa alternância entre bloqueado e desbloqueado reduz o risco de manter versões e cópias desnecessárias do documento.</span><span class="sxs-lookup"><span data-stu-id="878fd-115">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="878fd-116">**Ter os registros armazenados automaticamente em um repositório de registros in-loco, localizado no conjunto de sites.**</span><span class="sxs-lookup"><span data-stu-id="878fd-116">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="878fd-117">Cada conjunto de sites no SharePoint e no OneDrive preserva o conteúdo em sua biblioteca de Retenção para Preservação.</span><span class="sxs-lookup"><span data-stu-id="878fd-117">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="878fd-118">As versões de registro são armazenadas na pasta Registros nesta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="878fd-118">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="878fd-119">**Manter um documento perene que contenha todas as versões.**</span><span class="sxs-lookup"><span data-stu-id="878fd-119">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="878fd-120">Por padrão, cada documento do SharePoint e do OneDrive têm um histórico de versão disponível no menu do item.</span><span class="sxs-lookup"><span data-stu-id="878fd-120">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="878fd-121">Nesse histórico de versão, você pode ver facilmente quais versões são registros e exibir esses documentos.</span><span class="sxs-lookup"><span data-stu-id="878fd-121">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="878fd-122">O controle de versão do registro está disponível automaticamente para qualquer documento que tenha um rótulo de retenção que marque o item como registro.</span><span class="sxs-lookup"><span data-stu-id="878fd-122">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="878fd-123">Quando um usuário exibe as propriedades do documento usando o painel de detalhes, eles podem alternar o **Status do registro** de **Bloqueado** para **Desbloqueado**.</span><span class="sxs-lookup"><span data-stu-id="878fd-123">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="878fd-124">Essa ação cria um registro na pasta Registros na Biblioteca de Retenção para Preservação, onde reside pelo restante do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="878fd-124">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="878fd-125">Enquanto o documento está desbloqueado, qualquer usuário com permissões de edição padrão pode editar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="878fd-125">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="878fd-126">No entanto, os usuários não podem excluir o arquivo, porque ele continua sendo um registro.</span><span class="sxs-lookup"><span data-stu-id="878fd-126">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="878fd-127">Quando a edição estiver concluída, o usuário poderá alternar o **Status do registro** de **Desbloqueado** para **Bloqueado**, o que impede novas edições enquanto estiver nesse status.</span><span class="sxs-lookup"><span data-stu-id="878fd-127">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Propriedade do status do registro no documento marcado como um registro](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="878fd-129">Bloqueando e desbloqueando um registro</span><span class="sxs-lookup"><span data-stu-id="878fd-129">Locking and unlocking a record</span></span>

<span data-ttu-id="878fd-130">Depois que um rótulo de retenção que marca o conteúdo como registro é aplicado a um documento, qualquer usuário com permissões de Contribuição ou com um nível de permissão mais restrito pode desbloquear um registro ou bloquear um registro desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="878fd-130">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![O status do registro mostra que o documento de registro está desbloqueado](../media/recordversioning9.png)

<span data-ttu-id="878fd-132">Quando um usuário desbloqueia um registro, as seguintes ações ocorrem:</span><span class="sxs-lookup"><span data-stu-id="878fd-132">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="878fd-133">Se o conjunto de sites atual não tiver uma biblioteca de Retenção para Preservação, ela será criada.</span><span class="sxs-lookup"><span data-stu-id="878fd-133">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="878fd-134">Se a biblioteca de Retenção para Preservação não tiver uma pasta Registros, ela será criada.</span><span class="sxs-lookup"><span data-stu-id="878fd-134">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="878fd-135">Uma ação de **Copiar para** copia a versão mais recente do documento para a pasta Registros.</span><span class="sxs-lookup"><span data-stu-id="878fd-135">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="878fd-136">A ação **Copiar para** inclui apenas a versão mais recente e nenhuma das versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="878fd-136">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="878fd-137">Este documento copiado agora é considerado uma versão de registro do documento e o nome do arquivo tem o formato: \[Versão GUID Título\#\]</span><span class="sxs-lookup"><span data-stu-id="878fd-137">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="878fd-138">A cópia criada na pasta Registros é adicionada ao histórico da versão do documento original, e esta versão mostra a palavra **Registro** no campo de comentários.</span><span class="sxs-lookup"><span data-stu-id="878fd-138">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="878fd-139">O documento original é uma nova versão que pode ser editada, mas não excluída.</span><span class="sxs-lookup"><span data-stu-id="878fd-139">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="878fd-140">A coluna da biblioteca de documentos **Item é um Registro** ainda mostra o valor **Sim** porque o documento continua sendo um registro, mesmo que agora possa ser editado.</span><span class="sxs-lookup"><span data-stu-id="878fd-140">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="878fd-141">Quando um usuário bloqueia um registro, o documento original não poderá ser editado novamente.</span><span class="sxs-lookup"><span data-stu-id="878fd-141">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="878fd-142">Mas é a ação de desbloquear um registro que copia uma versão para a pasta Registros na biblioteca de Retenção para Preservação.</span><span class="sxs-lookup"><span data-stu-id="878fd-142">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="878fd-143">Versões de registro</span><span class="sxs-lookup"><span data-stu-id="878fd-143">Record versions</span></span>

<span data-ttu-id="878fd-144">Sempre que um usuário desbloqueia um registro, a versão mais recente é copiada para a pasta Registros na biblioteca de Retenção para Preservação, e essa versão contém o valor de **Registro** no campo **Comentários** do histórico da versão.</span><span class="sxs-lookup"><span data-stu-id="878fd-144">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Registro mostrado na biblioteca de Retenção para Preservação](../media/recordversioning10.png)

<span data-ttu-id="878fd-146">Para exibir o histórico da versão, escolha um documento na biblioteca de documentos e clique em **Histórico da Versão** no menu do item.</span><span class="sxs-lookup"><span data-stu-id="878fd-146">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="878fd-147">Onde os registros são armazenados</span><span class="sxs-lookup"><span data-stu-id="878fd-147">Where records are stored</span></span>

<span data-ttu-id="878fd-148">Os registros são armazenados na pasta Registros na biblioteca de Retenção para Preservação no site de nível superior do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="878fd-148">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="878fd-149">Na barra de navegação à esquerda no site de nível superior, escolha **Conteúdos do site** \> **Biblioteca de Retenção para Preservação**.</span><span class="sxs-lookup"><span data-stu-id="878fd-149">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Biblioteca de Retenção para Preservação](../media/recordversioning11.png)

<br/><br/>

![A pasta Registros na biblioteca de Retenção para Preservação](../media/recordversioning12.png)

<span data-ttu-id="878fd-152">A biblioteca de Retenção para Preservação está visível somente para administradores de conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="878fd-152">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="878fd-153">Além disso, a biblioteca de Retenção para Preservação não existe por padrão.</span><span class="sxs-lookup"><span data-stu-id="878fd-153">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="878fd-154">Ela é criada apenas quando o conteúdo sujeito a um rótulo ou política de retenção é excluído pela primeira vez do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="878fd-154">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="878fd-155">Pesquisando o log de auditoria para eventos de controle de versão do registro</span><span class="sxs-lookup"><span data-stu-id="878fd-155">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="878fd-156">As ações de bloqueio e desbloqueio de registros são registradas no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="878fd-156">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="878fd-157">Você pode pesquisar pelas atividades específicas **Status do registro alterado para bloqueado** e **Status do registro alterado para desbloqueado**, que estão localizadas na seção **Atividades de arquivo e página** na lista suspensa de **Atividades** na página de **Pesquisa de log de auditoria** no centro de conformidade e segurança.</span><span class="sxs-lookup"><span data-stu-id="878fd-157">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Pesquisar o log de auditoria para eventos de controle de versão do registro](../media/recordversioning13.png)

<span data-ttu-id="878fd-159">Para obter mais informações sobre a pesquisa desses eventos, confira a seção "Atividades de arquivo e página" em [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="878fd-159">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="878fd-160">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="878fd-160">Next steps</span></span>

<span data-ttu-id="878fd-161">Para marcar o conteúdo como registro, confira [Declarar registros usando rótulos de retenção](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="878fd-161">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>

<span data-ttu-id="878fd-162">Para saber mais sobre a disposição de registros, confira [Disposição de conteúdo](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="878fd-162">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>