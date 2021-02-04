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
ms.openlocfilehash: 19ad68d3c32046754e366919e8c4e66336945624
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080720"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="c23a0-103">Introdução ao gerenciador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="c23a0-103">Get started with content explorer</span></span>

<span data-ttu-id="c23a0-104">O explorador de conteúdo de classificação de dados permite que os itens que foram resumidos na página visão geral sejam exibidos nativamente.</span><span class="sxs-lookup"><span data-stu-id="c23a0-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![captura de tela do explorador de conteúdo recolhido](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="c23a0-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c23a0-106">Prerequisites</span></span>

<span data-ttu-id="c23a0-107">Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="c23a0-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="c23a0-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="c23a0-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="c23a0-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="c23a0-109">Office 365 (E5)</span></span>
- <span data-ttu-id="c23a0-110">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="c23a0-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="c23a0-111">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="c23a0-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="c23a0-112">Microsoft 365 E5/A5 Proteção e Governança da Informação</span><span class="sxs-lookup"><span data-stu-id="c23a0-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="c23a0-113">Conformidade Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="c23a0-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="c23a0-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="c23a0-114">Permissions</span></span>

<span data-ttu-id="c23a0-115">Para obter acesso à guia do Gerenciador de conteúdo, uma conta deve ter associação em qualquer uma dessas funções ou grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="c23a0-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="c23a0-116">**Grupos de funções do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="c23a0-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="c23a0-117">Administrador global</span><span class="sxs-lookup"><span data-stu-id="c23a0-117">Global administrator</span></span>
- <span data-ttu-id="c23a0-118">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="c23a0-118">Compliance administrator</span></span>
- <span data-ttu-id="c23a0-119">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="c23a0-119">Security administrator</span></span>
- <span data-ttu-id="c23a0-120">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="c23a0-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c23a0-121">A associação nesses grupos de função não permite que você veja a lista de itens ou exiba o conteúdo dos itens no Gerenciador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="c23a0-122">Permissões necessárias para acessar itens no Gerenciador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="c23a0-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="c23a0-123">O acesso ao Gerenciador de conteúdo é altamente restrito porque permite ler o conteúdo dos arquivos digitalizados.</span><span class="sxs-lookup"><span data-stu-id="c23a0-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c23a0-124">Essas permissões substituem as permissões que são atribuídas localmente aos itens, permitindo a visualização do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="c23a0-125">Existem duas funções que concedem acesso ao explorador de conteúdo e é concedido usando o [Centro da Segurança e Conformidade da Microsoft](https://protection.office.com/permissions):</span><span class="sxs-lookup"><span data-stu-id="c23a0-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="c23a0-126">**Visualizador de Listas do Explorador de Conteúdo**: a associação neste grupo de função permite que você veja cada item e seu local na exibição da lista.</span><span class="sxs-lookup"><span data-stu-id="c23a0-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="c23a0-127">A função `data classification list viewer` foi predefinida para esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="c23a0-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="c23a0-128">**Visualizador de Conteúdos do Explorador de Conteúdo**: a associação neste grupo de função permite exibir o conteúdo de cada item na lista.</span><span class="sxs-lookup"><span data-stu-id="c23a0-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="c23a0-129">A função `data classification content viewer` foi predefinida para esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="c23a0-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="c23a0-130">A conta que você usa para acessar o Explorador de conteúdo deve estar em uma ou em ambas os grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="c23a0-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="c23a0-131">Esses são grupos de funções independentes e não são cumulativos.</span><span class="sxs-lookup"><span data-stu-id="c23a0-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="c23a0-132">Por exemplo, se você deseja conceder a uma conta a capacidade de exibir apenas os itens e seus locais, conceda direitos ao visualizador de Listas do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="c23a0-133">Se você deseja que a mesma conta também possa exibir o conteúdo dos itens da lista, conceda também direitos ao visualizador de Conteúdos do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="c23a0-134">Você também pode atribuir uma ou ambas as funções a um grupo de funções personalizada para ajustar o acesso ao Gerenciador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="c23a0-135">Um administrador global, um administrador de conformidade ou um administrador de dados pode atribuir o Visualizador de lista do Gerenciador de conteúdo  necessário e Visualizador de conteúdo do Gerenciador de conteúdo a associação do grupo de função.</span><span class="sxs-lookup"><span data-stu-id="c23a0-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="c23a0-136">Explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="c23a0-136">Content explorer</span></span>

<span data-ttu-id="c23a0-137">O Explorador de conteúdo mostra uma imagem instantânea atual dos itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c23a0-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="c23a0-138">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="c23a0-138">Sensitive information types</span></span>

<span data-ttu-id="c23a0-139">Uma **política DLP** ajuda a proteger informações confidenciais, que são definidas como um [tipo de informações confidenciais](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c23a0-139">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="c23a0-140">O Microsoft 365 inclui [definições para vários tipos de informações confidenciais comuns](sensitive-information-type-entity-definitions.md) de diferentes regiões, prontas para você usar.</span><span class="sxs-lookup"><span data-stu-id="c23a0-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="c23a0-141">Por exemplo, um número de cartão de crédito, números de contas bancárias, números de identificação nacional e números de serviço do Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="c23a0-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="c23a0-142">O Gerenciador de conteúdo atualmente não examina os tipos de informações confidenciais no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c23a0-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="c23a0-143">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="c23a0-143">Sensitivity labels</span></span>

<span data-ttu-id="c23a0-144">Um [rótulo de confidencialidade](sensitivity-labels.md) é simplesmente uma marca que indica o valor do item para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="c23a0-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="c23a0-145">Ele pode ser aplicado manualmente ou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c23a0-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="c23a0-146">Uma vez aplicado, ele é incorporado ao documento e o acompanhará em todos os lugares.</span><span class="sxs-lookup"><span data-stu-id="c23a0-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="c23a0-147">Um rótulo de confidencialidade habilita vários comportamentos de proteção, como uma marca d' água obrigatória ou a criptografia.</span><span class="sxs-lookup"><span data-stu-id="c23a0-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="c23a0-148">Os rótulos de confidencialidade devem ser habilitados para arquivos que estão no SharePoint e no OneDrive para que os dados correspondentes apareçam na página de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="c23a0-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="c23a0-149">Para obter mais informações, confira [Habilitar rótulos de confidencialidade para arquivos do Office no Microsoft Office SharePoint Online e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="c23a0-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="c23a0-150">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="c23a0-150">Retention labels</span></span>

<span data-ttu-id="c23a0-151">Um [rótulo de retenção](retention.md) permite definir por quanto tempo um item rotulado será mantido e as etapas a serem seguidas antes de excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="c23a0-152">Ele pode ser aplicado manualmente ou automaticamente através de políticas.</span><span class="sxs-lookup"><span data-stu-id="c23a0-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="c23a0-153">Eles podem ajudar a sua organização a se manter em conformidade com as determinações regulamentares e legais.</span><span class="sxs-lookup"><span data-stu-id="c23a0-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="c23a0-154">Como usar o explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="c23a0-154">How to use content explorer</span></span>

1. <span data-ttu-id="c23a0-155">Abra o **centro de conformidade do Microsoft 365**  > **Classificação de dados** > **Explorador de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="c23a0-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="c23a0-156">Se souber o nome do rótulo ou o tipo de informação confidencial, digite-o na caixa de filtro.</span><span class="sxs-lookup"><span data-stu-id="c23a0-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="c23a0-157">Como alternativa, você pode procurar o item expandindo o tipo de rótulo e selecionando o rótulo da lista.</span><span class="sxs-lookup"><span data-stu-id="c23a0-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="c23a0-158">Selecione um local em **Todas as localizações** e faça uma busca detalhada na estrutura de pastas para o item.</span><span class="sxs-lookup"><span data-stu-id="c23a0-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="c23a0-159">Clique duas vezes para abrir o item nativamente no explorador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c23a0-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="c23a0-160">Exportar</span><span class="sxs-lookup"><span data-stu-id="c23a0-160">Export</span></span>
<span data-ttu-id="c23a0-161">O controle **exportar** criará um arquivo .csv que contém uma lista do que está sendo exibido no painel **Todos os locais**.</span><span class="sxs-lookup"><span data-stu-id="c23a0-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![controle de exportação de classificação de dados](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="c23a0-163">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="c23a0-163">Search</span></span>

<span data-ttu-id="c23a0-164">Quando você faz uma busca detalhada em um local, como uma pasta do Exchange ou um site do SharePoint ou do OneDrive, a ferramenta **Pesquisar** é exibida.</span><span class="sxs-lookup"><span data-stu-id="c23a0-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![ferramenta de pesquisa do explorador de conteúdo](../media/data_classification_search_tool.png)


<span data-ttu-id="c23a0-166">O escopo da ferramenta de pesquisa é o que é exibido no painel **Todos os locais** e o que você pode pesquisar varia dependendo do local selecionado.</span><span class="sxs-lookup"><span data-stu-id="c23a0-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="c23a0-167">Quando **Exchange** é o local selecionado, você pode pesquisar o endereço de email completo da caixa de correio, por exemplo `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="c23a0-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="c23a0-168">Quando **SharePoint** ou **OneDrive** são selecionados, a ferramenta de pesquisa será exibida ao fazer a busca detalhada para nomes de site, pastas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="c23a0-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="c23a0-169">**OneDrive** Ouvimos seus comentários sobre a integração do OneDrive durante nosso programa de versão prévia.</span><span class="sxs-lookup"><span data-stu-id="c23a0-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="c23a0-170">Com base nesses comentários, a funcionalidade do OneDrive permanecerá em versão prévia até que todas as correções estejam instaladas.</span><span class="sxs-lookup"><span data-stu-id="c23a0-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="c23a0-171">Dependendo do locatário, alguns clientes podem não ver o OneDrive como um local.</span><span class="sxs-lookup"><span data-stu-id="c23a0-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="c23a0-172">Agradecemos o seu apoio contínuo neste tema.</span><span class="sxs-lookup"><span data-stu-id="c23a0-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="c23a0-173">Você pode pesquisar em:</span><span class="sxs-lookup"><span data-stu-id="c23a0-173">You can search on:</span></span>


|<span data-ttu-id="c23a0-174">valor</span><span class="sxs-lookup"><span data-stu-id="c23a0-174">value</span></span>|<span data-ttu-id="c23a0-175">exemplo</span><span class="sxs-lookup"><span data-stu-id="c23a0-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="c23a0-176">nome completo do site</span><span class="sxs-lookup"><span data-stu-id="c23a0-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="c23a0-177">nome da pasta raiz: obtém todas as subpastas</span><span class="sxs-lookup"><span data-stu-id="c23a0-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="c23a0-178">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="c23a0-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="c23a0-179">texto no início do nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="c23a0-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="c23a0-180">texto após um caractere de sublinhado (_) no nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="c23a0-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="c23a0-181">`Resume` ou `1234`</span><span class="sxs-lookup"><span data-stu-id="c23a0-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="c23a0-182">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="c23a0-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="c23a0-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="c23a0-183">See also</span></span>

- [<span data-ttu-id="c23a0-184">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="c23a0-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="c23a0-185">Saiba mais sobre as políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="c23a0-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="c23a0-186">Tipo de entidade de informações confidenciais definitions.md</span><span class="sxs-lookup"><span data-stu-id="c23a0-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="c23a0-187">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="c23a0-187">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
