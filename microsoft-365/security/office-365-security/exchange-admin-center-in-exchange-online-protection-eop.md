---
title: Centro de administração do Exchange na Proteção do Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: O EAC (Centro de administração do Exchange) é o console de gerenciamento baseado na Web da EOP (Proteção do Exchange Online) da Microsoft.
ms.openlocfilehash: 58f339e2ebbb566b8656eed68453841ca011a72f
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970547"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="d4183-103">Centro de administração do Exchange na Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d4183-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="d4183-104">O EAC (Centro de administração do Exchange) é o console de gerenciamento baseado na Web da EOP (Proteção do Exchange Online) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4183-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="d4183-105">Procurando a versão do Exchange Server deste tópico?</span><span class="sxs-lookup"><span data-stu-id="d4183-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="d4183-106">Confira [centro de administração do Exchange no Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="d4183-106">See [Exchange admin center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span></span>

<span data-ttu-id="d4183-107">Procurando a versão do Exchange Online deste tópico?</span><span class="sxs-lookup"><span data-stu-id="d4183-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="d4183-108">Confira [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="d4183-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="d4183-109">Acessando o EAC</span><span class="sxs-lookup"><span data-stu-id="d4183-109">Accessing the EAC</span></span>

<span data-ttu-id="d4183-110">Na maioria dos casos, os clientes do EOP acessarão a Eat através do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4183-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="d4183-111">Você encontra um link para a EOP no menu suspenso no bloco **Administrador**, que fica ao lado do bloco **Eu**.</span><span class="sxs-lookup"><span data-stu-id="d4183-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="d4183-112">Clique no bloco **Administrador** e selecione **Proteção do Exchange Online** no menu suspenso para ir até o EAC.</span><span class="sxs-lookup"><span data-stu-id="d4183-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span>

<span data-ttu-id="d4183-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span><span class="sxs-lookup"><span data-stu-id="d4183-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="d4183-116">Elementos da interface do usuário comuns no EAC</span><span class="sxs-lookup"><span data-stu-id="d4183-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="d4183-117">Esta seção descreve os elementos da interface do usuário encontrados no EAC.</span><span class="sxs-lookup"><span data-stu-id="d4183-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="d4183-119">Painel de recursos</span><span class="sxs-lookup"><span data-stu-id="d4183-119">Feature Pane</span></span>

<span data-ttu-id="d4183-p105">Este é o primeiro nível de navegação para a maioria das tarefas que você executará no EAC. O painel de recursos é organizado por áreas de recursos.</span><span class="sxs-lookup"><span data-stu-id="d4183-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="d4183-122">**Destinatários**: aqui você exibirá usuários internos e contatos externos.</span><span class="sxs-lookup"><span data-stu-id="d4183-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="d4183-123">**Permissões**: Este é o local em que você gerenciará as funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="d4183-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="d4183-124">**Gerenciamento de conformidade**: aqui você encontrará logs e relatórios de auditoria, como o relatório do grupo de funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="d4183-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="d4183-125">**Proteção**: aqui você gerenciará a proteção antimalware e antispam para sua organização, além de gerenciar as mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="d4183-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="d4183-126">**Fluxo de emails**: aqui você gerenciará regras, domínios aceitos e conectores, bem como onde você vai para executar o rastreamento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="d4183-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="d4183-127">Guias</span><span class="sxs-lookup"><span data-stu-id="d4183-127">Tabs</span></span>

<span data-ttu-id="d4183-p106">As guias são seu segundo nível de navegação. Cada uma das áreas de recursos contém várias guias, cada uma representando um recurso.</span><span class="sxs-lookup"><span data-stu-id="d4183-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="d4183-130">Barra de ferramentas</span><span class="sxs-lookup"><span data-stu-id="d4183-130">Toolbar</span></span>

<span data-ttu-id="d4183-p107">Ao clicar na maioria das guias, você verá uma barra de ferramentas. A barra de ferramentas possui ícones que realizam ações específicas, A tabela a seguir descreve os ícones e suas ações.</span><span class="sxs-lookup"><span data-stu-id="d4183-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="d4183-134">**Ícone**</span><span class="sxs-lookup"><span data-stu-id="d4183-134">**Icon**</span></span>|<span data-ttu-id="d4183-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d4183-135">**Name**</span></span>|<span data-ttu-id="d4183-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="d4183-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Ícone Adicionar](../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="d4183-138">Adicionar, Novo</span><span class="sxs-lookup"><span data-stu-id="d4183-138">Add, New</span></span>|<span data-ttu-id="d4183-p108">Use esse ícone para criar um novo objeto. Alguns desses ícones têm uma seta para baixo associada, na qual é possível clicar para exibir objetos adicionais que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="d4183-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Ícone de edição](../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="d4183-142">Editar</span><span class="sxs-lookup"><span data-stu-id="d4183-142">Edit</span></span>|<span data-ttu-id="d4183-143">Use esse ícone para editar um objeto.</span><span class="sxs-lookup"><span data-stu-id="d4183-143">Use this icon to edit an object.</span></span>|
|![Excluir ícone](../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="d4183-145">Excluir</span><span class="sxs-lookup"><span data-stu-id="d4183-145">Delete</span></span>|<span data-ttu-id="d4183-p109">Use esse ícone para excluir um objeto. Alguns ícones excluídos têm uma seta para baixo na qual é possível clicar para mostrar opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="d4183-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Ícone Pesquisar](../media/ITPro-EAC-.gif)|<span data-ttu-id="d4183-149">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="d4183-149">Search</span></span>|<span data-ttu-id="d4183-150">Use esse ícone para abrir uma caixa de pesquisa na qual é possível digitar a frase de pesquisa para um objeto que você deseja encontrar.</span><span class="sxs-lookup"><span data-stu-id="d4183-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ícone Atualizar](../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="d4183-152">Atualizar</span><span class="sxs-lookup"><span data-stu-id="d4183-152">Refresh</span></span>|<span data-ttu-id="d4183-153">Use essa opção para atualizar a exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="d4183-153">Use this icon to refresh the list view.</span></span>|
|![Ícone Mais opções](../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="d4183-155">Mais opções</span><span class="sxs-lookup"><span data-stu-id="d4183-155">More options</span></span>|<span data-ttu-id="d4183-p110">Use esse ícone para ver mais ações que podem ser realizadas para os objetos dessa guia. Por exemplo, em **Destinatários \> Usuários**, um clique neste ícone mostra a opção para executar uma **Pesquisa Avançada**.  </span><span class="sxs-lookup"><span data-stu-id="d4183-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ícone Seta para cima](../media/ITPro-EAC-UpArrowIcon.gif)![Ícone Seta para baixo](../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="d4183-160">Seta para cima e seta para baixo</span><span class="sxs-lookup"><span data-stu-id="d4183-160">Up arrow and down arrow</span></span>|<span data-ttu-id="d4183-161">Use esses ícones para mover a prioridade de um objeto para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="d4183-161">Use these icons to move an object's priority up or down.</span></span>|
|![ícone Remover](../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="d4183-163">Remover</span><span class="sxs-lookup"><span data-stu-id="d4183-163">Remove</span></span>|<span data-ttu-id="d4183-164">Use esse ícone para remover objetos de uma lista.</span><span class="sxs-lookup"><span data-stu-id="d4183-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="d4183-165">Exibição de Lista</span><span class="sxs-lookup"><span data-stu-id="d4183-165">List View</span></span>

<span data-ttu-id="d4183-166">Ao selecionar uma guia, na maioria dos casos, você verá uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="d4183-166">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="d4183-167">O limite visualizável com o modo de exibição em lista do EAC é de aproximadamente 10.000 objetos.</span><span class="sxs-lookup"><span data-stu-id="d4183-167">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="d4183-168">Além disso, a paginação está incluída, para que você possa paginar os resultados.</span><span class="sxs-lookup"><span data-stu-id="d4183-168">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="d4183-169">Painel de Detalhes</span><span class="sxs-lookup"><span data-stu-id="d4183-169">Details Pane</span></span>

<span data-ttu-id="d4183-p112">Quando você seleciona um objeto na exibição de lista, informações sobre esse objeto são exibidas no painel de detalhes. Em alguns casos, o painel de detalhes inclui tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d4183-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="d4183-172">Bloco Eu e Ajuda</span><span class="sxs-lookup"><span data-stu-id="d4183-172">Me tile and Help</span></span>

<span data-ttu-id="d4183-173">O bloco **Eu** permite sair do EAC e entrar como um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="d4183-173">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="d4183-174">No menu **suspenso do**![ícone](../media/ITPro-EAC-HelpIcon.gif) ajuda da ajuda, é possível executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d4183-174">From the **Help**![Help Icon](../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="d4183-175">**Ajuda**: clique ![no ícone](../media/ITPro-EAC-HelpIcon.gif) ajuda para exibir o conteúdo da ajuda online.</span><span class="sxs-lookup"><span data-stu-id="d4183-175">**Help**: Click ![Help Icon](../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="d4183-176">**Desabilitar bolha de ajuda**: a bolha de ajuda exibe a ajuda contextual para os campos quando você cria ou edita um objeto.</span><span class="sxs-lookup"><span data-stu-id="d4183-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="d4183-177">Você pode desativar a bolha de Ajuda ou ativá-la se tiver sido desabilitada.</span><span class="sxs-lookup"><span data-stu-id="d4183-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="d4183-178">**Copyright**: clique neste link para ler o aviso de direitos autorais para o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="d4183-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="d4183-179">**Privacidade**: clique para ler a política de privacidade do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="d4183-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="d4183-180">Navegadores com suporte</span><span class="sxs-lookup"><span data-stu-id="d4183-180">Supported Browsers</span></span>

<span data-ttu-id="d4183-181">Para ter a melhor experiência ao usar o EAC, recomendamos que você sempre use os navegadores, clientes do Office e aplicativos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d4183-181">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="d4183-182">Também recomendamos que você instale as atualizações de software quando elas estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d4183-182">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="d4183-183">Para obter mais informações sobre os navegadores e requisitos de sistema suportados para o serviço, consulte [System Requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="d4183-183">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="d4183-184">Idiomas com suporte na EOP</span><span class="sxs-lookup"><span data-stu-id="d4183-184">Supported languages in EOP</span></span>

<span data-ttu-id="d4183-185">Os seguintes idiomas têm suporte e estão disponíveis para o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="d4183-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="d4183-186">Amárico</span><span class="sxs-lookup"><span data-stu-id="d4183-186">Amharic</span></span>

- <span data-ttu-id="d4183-187">Árabe</span><span class="sxs-lookup"><span data-stu-id="d4183-187">Arabic</span></span>

- <span data-ttu-id="d4183-188">Basco (Basco)</span><span class="sxs-lookup"><span data-stu-id="d4183-188">Basque (Basque)</span></span>

- <span data-ttu-id="d4183-189">Bengali (Índia)</span><span class="sxs-lookup"><span data-stu-id="d4183-189">Bengali (India)</span></span>

- <span data-ttu-id="d4183-190">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="d4183-190">Bulgarian</span></span>

- <span data-ttu-id="d4183-191">Catalão</span><span class="sxs-lookup"><span data-stu-id="d4183-191">Catalan</span></span>

- <span data-ttu-id="d4183-192">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="d4183-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="d4183-193">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="d4183-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="d4183-194">Croata</span><span class="sxs-lookup"><span data-stu-id="d4183-194">Croatian</span></span>

- <span data-ttu-id="d4183-195">Tcheco</span><span class="sxs-lookup"><span data-stu-id="d4183-195">Czech</span></span>

- <span data-ttu-id="d4183-196">Dinamarquês</span><span class="sxs-lookup"><span data-stu-id="d4183-196">Danish</span></span>

- <span data-ttu-id="d4183-197">Holandês</span><span class="sxs-lookup"><span data-stu-id="d4183-197">Dutch</span></span>

- <span data-ttu-id="d4183-198">Holandês</span><span class="sxs-lookup"><span data-stu-id="d4183-198">Dutch</span></span>

- <span data-ttu-id="d4183-199">Inglês</span><span class="sxs-lookup"><span data-stu-id="d4183-199">English</span></span>

- <span data-ttu-id="d4183-200">Estoniano</span><span class="sxs-lookup"><span data-stu-id="d4183-200">Estonian</span></span>

- <span data-ttu-id="d4183-201">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="d4183-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="d4183-202">Finlandês</span><span class="sxs-lookup"><span data-stu-id="d4183-202">Finnish</span></span>

- <span data-ttu-id="d4183-203">Francês</span><span class="sxs-lookup"><span data-stu-id="d4183-203">French</span></span>

- <span data-ttu-id="d4183-204">Galego</span><span class="sxs-lookup"><span data-stu-id="d4183-204">Galician</span></span>

- <span data-ttu-id="d4183-205">Alemão</span><span class="sxs-lookup"><span data-stu-id="d4183-205">German</span></span>

- <span data-ttu-id="d4183-206">Grego</span><span class="sxs-lookup"><span data-stu-id="d4183-206">Greek</span></span>

- <span data-ttu-id="d4183-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="d4183-207">Gujarati</span></span>

- <span data-ttu-id="d4183-208">Hebraico</span><span class="sxs-lookup"><span data-stu-id="d4183-208">Hebrew</span></span>

- <span data-ttu-id="d4183-209">Híndi</span><span class="sxs-lookup"><span data-stu-id="d4183-209">Hindi</span></span>

- <span data-ttu-id="d4183-210">Húngaro</span><span class="sxs-lookup"><span data-stu-id="d4183-210">Hungarian</span></span>

- <span data-ttu-id="d4183-211">Islandês</span><span class="sxs-lookup"><span data-stu-id="d4183-211">Icelandic</span></span>

- <span data-ttu-id="d4183-212">Indonésio</span><span class="sxs-lookup"><span data-stu-id="d4183-212">Indonesian</span></span>

- <span data-ttu-id="d4183-213">Italiano</span><span class="sxs-lookup"><span data-stu-id="d4183-213">Italian</span></span>

- <span data-ttu-id="d4183-214">Japonês</span><span class="sxs-lookup"><span data-stu-id="d4183-214">Japanese</span></span>

- <span data-ttu-id="d4183-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="d4183-215">Kannada</span></span>

- <span data-ttu-id="d4183-216">Cazaque</span><span class="sxs-lookup"><span data-stu-id="d4183-216">Kazakh</span></span>

- <span data-ttu-id="d4183-217">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="d4183-217">Kiswahili</span></span>

- <span data-ttu-id="d4183-218">Coreano</span><span class="sxs-lookup"><span data-stu-id="d4183-218">Korean</span></span>

- <span data-ttu-id="d4183-219">Letão</span><span class="sxs-lookup"><span data-stu-id="d4183-219">Latvian</span></span>

- <span data-ttu-id="d4183-220">Lituano</span><span class="sxs-lookup"><span data-stu-id="d4183-220">Lithuanian</span></span>

- <span data-ttu-id="d4183-221">Malaio (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="d4183-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="d4183-222">Malaio (Malásia)</span><span class="sxs-lookup"><span data-stu-id="d4183-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="d4183-223">Malaiala</span><span class="sxs-lookup"><span data-stu-id="d4183-223">Malayalam</span></span>

- <span data-ttu-id="d4183-224">Marati</span><span class="sxs-lookup"><span data-stu-id="d4183-224">Marathi</span></span>

- <span data-ttu-id="d4183-225">Norueguês (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="d4183-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="d4183-226">Norueguês (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="d4183-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="d4183-227">Oriá</span><span class="sxs-lookup"><span data-stu-id="d4183-227">Oriya</span></span>

- <span data-ttu-id="d4183-228">Persa</span><span class="sxs-lookup"><span data-stu-id="d4183-228">Persian</span></span>

- <span data-ttu-id="d4183-229">Polonês</span><span class="sxs-lookup"><span data-stu-id="d4183-229">Polish</span></span>

- <span data-ttu-id="d4183-230">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="d4183-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="d4183-231">Português (Portugal)</span><span class="sxs-lookup"><span data-stu-id="d4183-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="d4183-232">Romeno</span><span class="sxs-lookup"><span data-stu-id="d4183-232">Romanian</span></span>

- <span data-ttu-id="d4183-233">Russo</span><span class="sxs-lookup"><span data-stu-id="d4183-233">Russian</span></span>

- <span data-ttu-id="d4183-234">Sérvio (cirílico, Sérvia)</span><span class="sxs-lookup"><span data-stu-id="d4183-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="d4183-235">Sérvio (latino)</span><span class="sxs-lookup"><span data-stu-id="d4183-235">Serbian (Latin)</span></span>

- <span data-ttu-id="d4183-236">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="d4183-236">Slovak</span></span>

- <span data-ttu-id="d4183-237">Esloveno</span><span class="sxs-lookup"><span data-stu-id="d4183-237">Slovenian</span></span>

- <span data-ttu-id="d4183-238">Espanhol</span><span class="sxs-lookup"><span data-stu-id="d4183-238">Spanish</span></span>

- <span data-ttu-id="d4183-239">Sueco</span><span class="sxs-lookup"><span data-stu-id="d4183-239">Swedish</span></span>

- <span data-ttu-id="d4183-240">Tâmil</span><span class="sxs-lookup"><span data-stu-id="d4183-240">Tamil</span></span>

- <span data-ttu-id="d4183-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="d4183-241">Telugu</span></span>

- <span data-ttu-id="d4183-242">Tailandês</span><span class="sxs-lookup"><span data-stu-id="d4183-242">Thai</span></span>

- <span data-ttu-id="d4183-243">Turco</span><span class="sxs-lookup"><span data-stu-id="d4183-243">Turkish</span></span>

- <span data-ttu-id="d4183-244">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="d4183-244">Ukrainian</span></span>

- <span data-ttu-id="d4183-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="d4183-245">Urdu</span></span>

- <span data-ttu-id="d4183-246">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="d4183-246">Vietnamese</span></span>

- <span data-ttu-id="d4183-247">Galês</span><span class="sxs-lookup"><span data-stu-id="d4183-247">Welsh</span></span>


