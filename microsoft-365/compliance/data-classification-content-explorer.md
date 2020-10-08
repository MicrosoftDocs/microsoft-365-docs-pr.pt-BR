---
title: Introdução ao gerenciador de conteúdo
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O explorador de conteúdo permite que se veja nativamente os itens rotulados.
ms.openlocfilehash: 7977d30881a4229f99f4c5976d4c41377573a6ca
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379213"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="b4b45-103">Introdução ao gerenciador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b4b45-103">Get started with content explorer</span></span>

<span data-ttu-id="b4b45-104">O explorador de conteúdo de classificação de dados permite que os itens que foram resumidos na página visão geral sejam exibidos nativamente.</span><span class="sxs-lookup"><span data-stu-id="b4b45-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![captura de tela do explorador de conteúdo recolhido](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="b4b45-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b4b45-106">Prerequisites</span></span>

<span data-ttu-id="b4b45-107">Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="b4b45-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="b4b45-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="b4b45-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="b4b45-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="b4b45-109">Office 365 (E5)</span></span>
- <span data-ttu-id="b4b45-110">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="b4b45-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="b4b45-111">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="b4b45-111">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="b4b45-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="b4b45-112">Permissions</span></span>

<span data-ttu-id="b4b45-113">Para obter acesso à guia do Gerenciador de conteúdo, uma conta deve ter associação em qualquer uma dessas funções ou grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="b4b45-113">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="b4b45-114">Uma **política DLP** ajuda a proteger informações confidenciais, que são definidas como um [tipo de informações confidenciais](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b4b45-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="b4b45-115">O Microsoft 365 inclui [definições para vários tipos de informações confidenciais comuns](sensitive-information-type-entity-definitions.md) em diferentes regiões, prontas para você usar.</span><span class="sxs-lookup"><span data-stu-id="b4b45-115">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="b4b45-116">Por exemplo, um número de cartão de crédito, números de contas bancárias, números de ID nacionais e números de serviço Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="b4b45-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

<span data-ttu-id="b4b45-117">**Grupos de funções do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="b4b45-117">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="b4b45-118">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b4b45-118">Global administrator</span></span>
- <span data-ttu-id="b4b45-119">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="b4b45-119">Compliance administrator</span></span>
- <span data-ttu-id="b4b45-120">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="b4b45-120">Security administrator</span></span>
- <span data-ttu-id="b4b45-121">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="b4b45-121">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4b45-122">A associação nesses grupos de função não permite que você veja a lista de itens ou exiba o conteúdo dos itens no Gerenciador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-122">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="b4b45-123">Permissões necessárias para acessar itens no Gerenciador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b4b45-123">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="b4b45-124">O acesso ao Gerenciador de conteúdo é altamente restrito porque permite ler o conteúdo dos arquivos digitalizados.</span><span class="sxs-lookup"><span data-stu-id="b4b45-124">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4b45-125">Essas permissões substituem as permissões que são atribuídas localmente aos itens, permitindo a visualização do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-125">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="b4b45-126">Há duas funções que concedem acesso ao Explorador de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="b4b45-126">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="b4b45-127">**Visualizador de Listas do Explorador de Conteúdo**: a associação neste grupo de função permite que você veja cada item e seu local na exibição da lista.</span><span class="sxs-lookup"><span data-stu-id="b4b45-127">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="b4b45-128">A função `data classification list viewer` foi predefinida para esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="b4b45-128">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="b4b45-129">**Visualizador de Conteúdos do Explorador de Conteúdo**: a associação neste grupo de função permite exibir o conteúdo de cada item na lista.</span><span class="sxs-lookup"><span data-stu-id="b4b45-129">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="b4b45-130">A função `data classification content viewer` foi predefinida para esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="b4b45-130">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="b4b45-131">A conta que você usa para acessar o Explorador de conteúdo deve estar em uma ou em ambas os grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="b4b45-131">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="b4b45-132">Esses são grupos de funções independentes e não são cumulativos.</span><span class="sxs-lookup"><span data-stu-id="b4b45-132">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="b4b45-133">Por exemplo, se você deseja conceder a uma conta a capacidade de exibir apenas os itens e seus locais, conceda direitos ao visualizador de Listas do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-133">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="b4b45-134">Se você deseja que a mesma conta também possa exibir o conteúdo dos itens da lista, conceda também direitos ao visualizador de Conteúdos do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-134">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="b4b45-135">Você também pode atribuir uma ou ambas as funções a um grupo de funções personalizada para ajustar o acesso ao Gerenciador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-135">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="b4b45-136">Um administrador global, um administrador de conformidade ou um administrador de dados pode atribuir o Visualizador de lista do Gerenciador de conteúdo  necessário e Visualizador de conteúdo do Gerenciador de conteúdo a associação do grupo de função.</span><span class="sxs-lookup"><span data-stu-id="b4b45-136">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="b4b45-137">Explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b4b45-137">Content explorer</span></span>

<span data-ttu-id="b4b45-138">O Explorador de conteúdo mostra uma imagem instantânea atual dos itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4b45-138">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="b4b45-139">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="b4b45-139">Sensitive information types</span></span>

<span data-ttu-id="b4b45-140">Uma **política DLP** ajuda a proteger informações confidenciais, que são definidas como um [tipo de informações confidenciais](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b4b45-140">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="b4b45-141">O Microsoft 365 inclui [definições para vários tipos de informações confidenciais comuns](sensitive-information-type-entity-definitions.md) de diferentes regiões, prontas para você usar.</span><span class="sxs-lookup"><span data-stu-id="b4b45-141">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="b4b45-142">Por exemplo, um número de cartão de crédito, números de contas bancárias, números de identificação nacional e números de serviço do Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="b4b45-142">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="b4b45-143">O Gerenciador de conteúdo atualmente não examina os tipos de informações confidenciais no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b4b45-143">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="b4b45-144">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="b4b45-144">Sensitivity labels</span></span>

<span data-ttu-id="b4b45-145">Um [rótulo de confidencialidade](sensitivity-labels.md) é simplesmente uma marca que indica o valor do item para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4b45-145">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="b4b45-146">Ele pode ser aplicado manualmente ou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4b45-146">It can be applied manually, or automatically.</span></span> <span data-ttu-id="b4b45-147">Uma vez aplicado, ele é incorporado ao documento e o acompanhará em todos os lugares.</span><span class="sxs-lookup"><span data-stu-id="b4b45-147">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="b4b45-148">Um rótulo de confidencialidade habilita vários comportamentos de proteção, como uma marca d' água obrigatória ou a criptografia.</span><span class="sxs-lookup"><span data-stu-id="b4b45-148">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="b4b45-149">Os rótulos de confidencialidade devem ser habilitados para arquivos que estão no SharePoint e no OneDrive para que os dados correspondentes apareçam na página de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="b4b45-149">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="b4b45-150">Para obter mais informações, confira [Habilitar rótulos de confidencialidade para arquivos do Office no Microsoft Office SharePoint Online e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="b4b45-150">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="b4b45-151">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="b4b45-151">Retention labels</span></span>

<span data-ttu-id="b4b45-152">Um [rótulo de retenção](retention.md) permite definir por quanto tempo um item rotulado será mantido e as etapas a serem seguidas antes de excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-152">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="b4b45-153">Ele pode ser aplicado manualmente ou automaticamente através de políticas.</span><span class="sxs-lookup"><span data-stu-id="b4b45-153">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="b4b45-154">Eles podem ajudar a sua organização a se manter em conformidade com as determinações regulamentares e legais.</span><span class="sxs-lookup"><span data-stu-id="b4b45-154">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="b4b45-155">Como usar o explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b4b45-155">How to use content explorer</span></span>

1. <span data-ttu-id="b4b45-156">Abra o **centro de conformidade do Microsoft 365**  > **Classificação de dados** > \*\* Explorador de conteúdo\*\*.</span><span class="sxs-lookup"><span data-stu-id="b4b45-156">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="b4b45-157">Se souber o nome do rótulo ou o tipo de informação confidencial, digite-o na caixa de filtro.</span><span class="sxs-lookup"><span data-stu-id="b4b45-157">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="b4b45-158">Como alternativa, você pode procurar o item expandindo o tipo de rótulo e selecionando o rótulo da lista.</span><span class="sxs-lookup"><span data-stu-id="b4b45-158">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="b4b45-159">Selecione um local em **Todas as localizações** e faça uma busca detalhada na estrutura de pastas para o item.</span><span class="sxs-lookup"><span data-stu-id="b4b45-159">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="b4b45-160">Clique duas vezes para abrir o item nativamente no explorador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4b45-160">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="b4b45-161">Exportar</span><span class="sxs-lookup"><span data-stu-id="b4b45-161">Export</span></span>
<span data-ttu-id="b4b45-162">O controle **exportar** criará um arquivo .csv que contém uma lista do que está sendo exibido no painel **Todos os locais**.</span><span class="sxs-lookup"><span data-stu-id="b4b45-162">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![controle de exportação de classificação de dados](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="b4b45-164">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="b4b45-164">Search</span></span>

<span data-ttu-id="b4b45-165">Quando você faz uma busca detalhada em um local, como uma pasta do Exchange ou um site do SharePoint ou do OneDrive, a ferramenta **Pesquisar** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b4b45-165">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![ferramenta de pesquisa do explorador de conteúdo](../media/data_classification_search_tool.png)


<span data-ttu-id="b4b45-167">O escopo da ferramenta de pesquisa é o que é exibido no painel **Todos os locais** e o que você pode pesquisar varia dependendo do local selecionado.</span><span class="sxs-lookup"><span data-stu-id="b4b45-167">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="b4b45-168">Quando **Exchange** é o local selecionado, você pode pesquisar o endereço de email completo da caixa de correio, por exemplo `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="b4b45-168">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="b4b45-169">Quando **SharePoint** ou **OneDrive** são selecionados, a ferramenta de pesquisa será exibida ao fazer a busca detalhada para nomes de site, pastas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="b4b45-169">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4b45-170">**OneDrive** Ouvimos seus comentários sobre a integração do OneDrive durante nosso programa de versão prévia.</span><span class="sxs-lookup"><span data-stu-id="b4b45-170">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="b4b45-171">Com base nesses comentários, a funcionalidade do OneDrive permanecerá em versão prévia até que todas as correções estejam instaladas.</span><span class="sxs-lookup"><span data-stu-id="b4b45-171">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="b4b45-172">Dependendo do locatário, alguns clientes podem não ver o OneDrive como um local.</span><span class="sxs-lookup"><span data-stu-id="b4b45-172">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="b4b45-173">Agradecemos o seu apoio contínuo neste tema.</span><span class="sxs-lookup"><span data-stu-id="b4b45-173">We appreciate your continued support on this.</span></span>

<span data-ttu-id="b4b45-174">Você pode pesquisar em:</span><span class="sxs-lookup"><span data-stu-id="b4b45-174">You can search on:</span></span>


|<span data-ttu-id="b4b45-175">valor</span><span class="sxs-lookup"><span data-stu-id="b4b45-175">value</span></span>|<span data-ttu-id="b4b45-176">exemplo</span><span class="sxs-lookup"><span data-stu-id="b4b45-176">example</span></span>  |
|---------|---------|
|<span data-ttu-id="b4b45-177">nome completo do site</span><span class="sxs-lookup"><span data-stu-id="b4b45-177">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="b4b45-178">nome da pasta raiz: obtém todas as subpastas</span><span class="sxs-lookup"><span data-stu-id="b4b45-178">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="b4b45-179">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="b4b45-179">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="b4b45-180">texto no início do nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="b4b45-180">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="b4b45-181">texto após um caractere de sublinhado (_) no nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="b4b45-181">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="b4b45-182">`Resume` ou `1234`</span><span class="sxs-lookup"><span data-stu-id="b4b45-182">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="b4b45-183">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="b4b45-183">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="b4b45-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4b45-184">See also</span></span>

- [<span data-ttu-id="b4b45-185">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="b4b45-185">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="b4b45-186">Saiba mais sobre as políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="b4b45-186">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="b4b45-187">Tipo de entidade de informações confidenciais definitions.md</span><span class="sxs-lookup"><span data-stu-id="b4b45-187">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="b4b45-188">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="b4b45-188">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
