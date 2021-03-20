---
title: Centro de administração do Exchange no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Saiba mais sobre a interface de gerenciamento da Web no EOP (Proteção autônoma do Exchange Online).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916989"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="24896-103">Centro de administração do Exchange no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="24896-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="24896-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="24896-104">**Applies to**</span></span>
-  [<span data-ttu-id="24896-105">Proteção autônoma do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="24896-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="24896-106">O Centro de administração do Exchange (EAC) é um console de gerenciamento baseado na Web para a Proteção autônoma do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="24896-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="24896-107">Procurando a versão do Exchange Online deste tópico?</span><span class="sxs-lookup"><span data-stu-id="24896-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="24896-108">Confira [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="24896-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="24896-109">Abra o EAC no EOP</span><span class="sxs-lookup"><span data-stu-id="24896-109">Open the EAC in EOP</span></span>

<span data-ttu-id="24896-110">Os clientes EOP autônomos podem acessar o EAC usando os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="24896-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="24896-111">No Centro de administração **do Microsoft 365:**</span><span class="sxs-lookup"><span data-stu-id="24896-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="24896-112">Vá até <https://admin.microsoft.com> e clique em Mostrar **tudo**.</span><span class="sxs-lookup"><span data-stu-id="24896-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Clique em Mostrar tudo no centro de administração do Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="24896-114">Na seção **Centros de administração** que aparece, clique em Todos os centros de **administração**.</span><span class="sxs-lookup"><span data-stu-id="24896-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Clique em Todos os centros de administração no Centro de administração do Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="24896-116">Na página **Todos os centros de administração** que aparece, clique em Proteção do Exchange **Online**.</span><span class="sxs-lookup"><span data-stu-id="24896-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="24896-117">Vá diretamente para `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="24896-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="24896-118">Elementos comuns da interface do usuário no EAC no EOP</span><span class="sxs-lookup"><span data-stu-id="24896-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="24896-119">Esta seção descreve os elementos da interface do usuário encontrados no EAC.</span><span class="sxs-lookup"><span data-stu-id="24896-119">This section describes the user interface elements that are found in the EAC.</span></span>

![O Centro de administração do Exchange na Proteção do Exchange Online](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="24896-121">Painel de recursos</span><span class="sxs-lookup"><span data-stu-id="24896-121">Feature Pane</span></span>

<span data-ttu-id="24896-p102">Este é o primeiro nível de navegação para a maioria das tarefas que você executará no EAC. O painel de recursos é organizado por áreas de recursos.</span><span class="sxs-lookup"><span data-stu-id="24896-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="24896-124">**Destinatários**: é aqui que você exibirá grupos e contatos externos.</span><span class="sxs-lookup"><span data-stu-id="24896-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="24896-125">**Permissões**: é onde você gerenciará funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="24896-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="24896-126">**Gerenciamento de** Conformidade : é aqui que você encontrará o relatório do grupo de funções de administrador e o relatório de log de auditoria do administrador.</span><span class="sxs-lookup"><span data-stu-id="24896-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="24896-127">**Proteção**: é onde você pode gerenciar políticas anti-malware, a política de filtro de conexão padrão e o DKIM.</span><span class="sxs-lookup"><span data-stu-id="24896-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="24896-128">Você deve gerenciar políticas anti-malware e a política de filtro de conexão padrão no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="24896-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="24896-129">Para obter mais informações, consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="24896-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="24896-130">**Fluxo de** Emails : é onde você gerenciará as regras de fluxo de emails (também conhecidas como regras de transporte), domínios aceitos e conectores, bem como onde você pode ir para executar o rastreamento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="24896-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="24896-131">**Híbrido**: é onde você pode executar o [Assistente](/Exchange/hybrid-configuration-wizard)de Configuração Híbrida e onde você pode instalar o módulo [do PowerShell do Exchange Online.](/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="24896-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="24896-132">Guias</span><span class="sxs-lookup"><span data-stu-id="24896-132">Tabs</span></span>

<span data-ttu-id="24896-p104">As guias são seu segundo nível de navegação. Cada uma das áreas de recursos contém várias guias, cada uma representando um recurso.</span><span class="sxs-lookup"><span data-stu-id="24896-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="24896-135">Barra de ferramentas</span><span class="sxs-lookup"><span data-stu-id="24896-135">Toolbar</span></span>

<span data-ttu-id="24896-p105">Ao clicar na maioria das guias, você verá uma barra de ferramentas. A barra de ferramentas possui ícones que realizam ações específicas, A tabela a seguir descreve os ícones e suas ações.</span><span class="sxs-lookup"><span data-stu-id="24896-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="24896-139">Ícone</span><span class="sxs-lookup"><span data-stu-id="24896-139">Icon</span></span>|<span data-ttu-id="24896-140">Nome</span><span class="sxs-lookup"><span data-stu-id="24896-140">Name</span></span>|<span data-ttu-id="24896-141">Action</span><span class="sxs-lookup"><span data-stu-id="24896-141">Action</span></span>|
|---|---|---|
|![Ícone Adicionar](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="24896-143">Adicionar, Novo</span><span class="sxs-lookup"><span data-stu-id="24896-143">Add, New</span></span>|<span data-ttu-id="24896-p106">Use esse ícone para criar um novo objeto. Alguns desses ícones têm uma seta para baixo associada, na qual é possível clicar para exibir objetos adicionais que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="24896-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Ícone de edição](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="24896-147">Editar</span><span class="sxs-lookup"><span data-stu-id="24896-147">Edit</span></span>|<span data-ttu-id="24896-148">Use esse ícone para editar um objeto.</span><span class="sxs-lookup"><span data-stu-id="24896-148">Use this icon to edit an object.</span></span>|
|![Excluir ícone](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="24896-150">Excluir</span><span class="sxs-lookup"><span data-stu-id="24896-150">Delete</span></span>|<span data-ttu-id="24896-p107">Use esse ícone para excluir um objeto. Alguns ícones excluídos têm uma seta para baixo na qual é possível clicar para mostrar opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="24896-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Ícone Pesquisar](../../media/ITPro-EAC-.gif)|<span data-ttu-id="24896-154">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="24896-154">Search</span></span>|<span data-ttu-id="24896-155">Use esse ícone para abrir uma caixa de pesquisa na qual é possível digitar a frase de pesquisa para um objeto que você deseja encontrar.</span><span class="sxs-lookup"><span data-stu-id="24896-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ícone Atualizar](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="24896-157">Atualizar</span><span class="sxs-lookup"><span data-stu-id="24896-157">Refresh</span></span>|<span data-ttu-id="24896-158">Use essa opção para atualizar a exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="24896-158">Use this icon to refresh the list view.</span></span>|
|![Ícone Mais opções](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="24896-160">Mais opções</span><span class="sxs-lookup"><span data-stu-id="24896-160">More options</span></span>|<span data-ttu-id="24896-p108">Use esse ícone para ver mais ações que podem ser realizadas para os objetos dessa guia. Por exemplo, em **Destinatários \> Usuários**, um clique neste ícone mostra a opção para executar uma **Pesquisa Avançada**.  </span><span class="sxs-lookup"><span data-stu-id="24896-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.gif)![Ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="24896-165">Seta para cima e seta para baixo</span><span class="sxs-lookup"><span data-stu-id="24896-165">Up arrow and down arrow</span></span>|<span data-ttu-id="24896-166">Use esses ícones para mover a prioridade de um objeto para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="24896-166">Use these icons to move an object's priority up or down.</span></span>|
|![ícone Remover](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="24896-168">Remover</span><span class="sxs-lookup"><span data-stu-id="24896-168">Remove</span></span>|<span data-ttu-id="24896-169">Use esse ícone para remover objetos de uma lista.</span><span class="sxs-lookup"><span data-stu-id="24896-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="24896-170">Exibição de Lista</span><span class="sxs-lookup"><span data-stu-id="24896-170">List View</span></span>

<span data-ttu-id="24896-171">Ao selecionar uma guia, na maioria dos casos, você verá uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="24896-171">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="24896-172">O limite visualizável com o modo de exibição em lista do EAC é de aproximadamente 10.000 objetos.</span><span class="sxs-lookup"><span data-stu-id="24896-172">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="24896-173">Além disso, a paginação está incluída, para que você possa paginar os resultados.</span><span class="sxs-lookup"><span data-stu-id="24896-173">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="24896-174">Painel de Detalhes</span><span class="sxs-lookup"><span data-stu-id="24896-174">Details Pane</span></span>

<span data-ttu-id="24896-p110">Quando você seleciona um objeto na exibição de lista, informações sobre esse objeto são exibidas no painel de detalhes. Em alguns casos, o painel de detalhes inclui tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="24896-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="24896-177">Bloco Eu e Ajuda</span><span class="sxs-lookup"><span data-stu-id="24896-177">Me tile and Help</span></span>

<span data-ttu-id="24896-178">O bloco **Eu** permite sair do EAC e entrar como um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="24896-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="24896-179">No menu **suspenso Ícone** de Ajuda ![ da ](../../media/ITPro-EAC-HelpIcon.gif) Ajuda, você pode fazer as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="24896-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="24896-180">**Ajuda**: Clique ![ em Ícone de Ajuda para exibir o conteúdo da ajuda ](../../media/ITPro-EAC-HelpIcon.gif) online.</span><span class="sxs-lookup"><span data-stu-id="24896-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="24896-181">**Comentários**: Deixe comentários.</span><span class="sxs-lookup"><span data-stu-id="24896-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="24896-182">**Comunidade**: poste uma pergunta para encontrar respostas nos fóruns da comunidade.</span><span class="sxs-lookup"><span data-stu-id="24896-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="24896-183">**Desabilitar a bolha de** Ajuda : a bolha de Ajuda exibe ajuda contextual para campos quando você cria ou edita um objeto.</span><span class="sxs-lookup"><span data-stu-id="24896-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="24896-184">Você pode desativar a bolha de Ajuda ou ativá-la se tiver sido desabilitada.</span><span class="sxs-lookup"><span data-stu-id="24896-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="24896-185">**Mostrar Log de Comando**: uma nova janela é aberta que mostra os comandos equivalentes do PowerShell com base no que você configurou no EAC.</span><span class="sxs-lookup"><span data-stu-id="24896-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="24896-186">Navegadores com suporte</span><span class="sxs-lookup"><span data-stu-id="24896-186">Supported Browsers</span></span>

<span data-ttu-id="24896-187">Para ter a melhor experiência ao usar o EAC, recomendamos que você sempre use os navegadores, clientes do Office e aplicativos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="24896-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="24896-188">Também recomendamos que você instale as atualizações de software quando elas estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="24896-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="24896-189">Para obter mais informações sobre os navegadores com suporte e os requisitos do sistema para o serviço, consulte [System requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="24896-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="24896-190">Idiomas compatíveis</span><span class="sxs-lookup"><span data-stu-id="24896-190">Supported languages</span></span>

<span data-ttu-id="24896-191">Os idiomas a seguir são suportados e disponíveis para o EAC no EOP autônomo.</span><span class="sxs-lookup"><span data-stu-id="24896-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="24896-192">Amharic</span><span class="sxs-lookup"><span data-stu-id="24896-192">Amharic</span></span>
- <span data-ttu-id="24896-193">Árabe</span><span class="sxs-lookup"><span data-stu-id="24896-193">Arabic</span></span>
- <span data-ttu-id="24896-194">Basco (Basco)</span><span class="sxs-lookup"><span data-stu-id="24896-194">Basque (Basque)</span></span>
- <span data-ttu-id="24896-195">Bengali (Índia)</span><span class="sxs-lookup"><span data-stu-id="24896-195">Bengali (India)</span></span>
- <span data-ttu-id="24896-196">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="24896-196">Bulgarian</span></span>
- <span data-ttu-id="24896-197">Catalão</span><span class="sxs-lookup"><span data-stu-id="24896-197">Catalan</span></span>
- <span data-ttu-id="24896-198">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="24896-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="24896-199">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="24896-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="24896-200">Croata</span><span class="sxs-lookup"><span data-stu-id="24896-200">Croatian</span></span>
- <span data-ttu-id="24896-201">Tcheco</span><span class="sxs-lookup"><span data-stu-id="24896-201">Czech</span></span>
- <span data-ttu-id="24896-202">Dinamarquês</span><span class="sxs-lookup"><span data-stu-id="24896-202">Danish</span></span>
- <span data-ttu-id="24896-203">Holandês</span><span class="sxs-lookup"><span data-stu-id="24896-203">Dutch</span></span>
- <span data-ttu-id="24896-204">Inglês</span><span class="sxs-lookup"><span data-stu-id="24896-204">English</span></span>
- <span data-ttu-id="24896-205">Estoniano</span><span class="sxs-lookup"><span data-stu-id="24896-205">Estonian</span></span>
- <span data-ttu-id="24896-206">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="24896-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="24896-207">Finlandês</span><span class="sxs-lookup"><span data-stu-id="24896-207">Finnish</span></span>
- <span data-ttu-id="24896-208">Francês</span><span class="sxs-lookup"><span data-stu-id="24896-208">French</span></span>
- <span data-ttu-id="24896-209">Galego</span><span class="sxs-lookup"><span data-stu-id="24896-209">Galician</span></span>
- <span data-ttu-id="24896-210">Alemão</span><span class="sxs-lookup"><span data-stu-id="24896-210">German</span></span>
- <span data-ttu-id="24896-211">Grego</span><span class="sxs-lookup"><span data-stu-id="24896-211">Greek</span></span>
- <span data-ttu-id="24896-212">Gujarati</span><span class="sxs-lookup"><span data-stu-id="24896-212">Gujarati</span></span>
- <span data-ttu-id="24896-213">Hebraico</span><span class="sxs-lookup"><span data-stu-id="24896-213">Hebrew</span></span>
- <span data-ttu-id="24896-214">Híndi</span><span class="sxs-lookup"><span data-stu-id="24896-214">Hindi</span></span>
- <span data-ttu-id="24896-215">Húngaro</span><span class="sxs-lookup"><span data-stu-id="24896-215">Hungarian</span></span>
- <span data-ttu-id="24896-216">Islandês</span><span class="sxs-lookup"><span data-stu-id="24896-216">Icelandic</span></span>
- <span data-ttu-id="24896-217">Indonésio</span><span class="sxs-lookup"><span data-stu-id="24896-217">Indonesian</span></span>
- <span data-ttu-id="24896-218">Italiano</span><span class="sxs-lookup"><span data-stu-id="24896-218">Italian</span></span>
- <span data-ttu-id="24896-219">Japonês</span><span class="sxs-lookup"><span data-stu-id="24896-219">Japanese</span></span>
- <span data-ttu-id="24896-220">Kannada</span><span class="sxs-lookup"><span data-stu-id="24896-220">Kannada</span></span>
- <span data-ttu-id="24896-221">Cazaque</span><span class="sxs-lookup"><span data-stu-id="24896-221">Kazakh</span></span>
- <span data-ttu-id="24896-222">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="24896-222">Kiswahili</span></span>
- <span data-ttu-id="24896-223">Coreano</span><span class="sxs-lookup"><span data-stu-id="24896-223">Korean</span></span>
- <span data-ttu-id="24896-224">Letão</span><span class="sxs-lookup"><span data-stu-id="24896-224">Latvian</span></span>
- <span data-ttu-id="24896-225">Lituano</span><span class="sxs-lookup"><span data-stu-id="24896-225">Lithuanian</span></span>
- <span data-ttu-id="24896-226">Malaio (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="24896-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="24896-227">Malaio (Malásia)</span><span class="sxs-lookup"><span data-stu-id="24896-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="24896-228">Malaiala</span><span class="sxs-lookup"><span data-stu-id="24896-228">Malayalam</span></span>
- <span data-ttu-id="24896-229">Marati</span><span class="sxs-lookup"><span data-stu-id="24896-229">Marathi</span></span>
- <span data-ttu-id="24896-230">Norueguês (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="24896-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="24896-231">Norueguês (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="24896-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="24896-232">Oriá</span><span class="sxs-lookup"><span data-stu-id="24896-232">Oriya</span></span>
- <span data-ttu-id="24896-233">Persa</span><span class="sxs-lookup"><span data-stu-id="24896-233">Persian</span></span>
- <span data-ttu-id="24896-234">Polonês</span><span class="sxs-lookup"><span data-stu-id="24896-234">Polish</span></span>
- <span data-ttu-id="24896-235">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="24896-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="24896-236">Português (Portugal)</span><span class="sxs-lookup"><span data-stu-id="24896-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="24896-237">Romeno</span><span class="sxs-lookup"><span data-stu-id="24896-237">Romanian</span></span>
- <span data-ttu-id="24896-238">Russo</span><span class="sxs-lookup"><span data-stu-id="24896-238">Russian</span></span>
- <span data-ttu-id="24896-239">Sérvio (cirílico, Sérvia)</span><span class="sxs-lookup"><span data-stu-id="24896-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="24896-240">Sérvio (latino)</span><span class="sxs-lookup"><span data-stu-id="24896-240">Serbian (Latin)</span></span>
- <span data-ttu-id="24896-241">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="24896-241">Slovak</span></span>
- <span data-ttu-id="24896-242">Esloveno</span><span class="sxs-lookup"><span data-stu-id="24896-242">Slovenian</span></span>
- <span data-ttu-id="24896-243">Espanhol</span><span class="sxs-lookup"><span data-stu-id="24896-243">Spanish</span></span>
- <span data-ttu-id="24896-244">Sueco</span><span class="sxs-lookup"><span data-stu-id="24896-244">Swedish</span></span>
- <span data-ttu-id="24896-245">Tâmil</span><span class="sxs-lookup"><span data-stu-id="24896-245">Tamil</span></span>
- <span data-ttu-id="24896-246">Telugu</span><span class="sxs-lookup"><span data-stu-id="24896-246">Telugu</span></span>
- <span data-ttu-id="24896-247">Tailandês</span><span class="sxs-lookup"><span data-stu-id="24896-247">Thai</span></span>
- <span data-ttu-id="24896-248">Turco</span><span class="sxs-lookup"><span data-stu-id="24896-248">Turkish</span></span>
- <span data-ttu-id="24896-249">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="24896-249">Ukrainian</span></span>
- <span data-ttu-id="24896-250">Urdu</span><span class="sxs-lookup"><span data-stu-id="24896-250">Urdu</span></span>
- <span data-ttu-id="24896-251">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="24896-251">Vietnamese</span></span>
- <span data-ttu-id="24896-252">Galês</span><span class="sxs-lookup"><span data-stu-id="24896-252">Welsh</span></span>