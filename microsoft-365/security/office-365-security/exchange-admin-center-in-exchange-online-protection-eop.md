---
title: Centro de administração do Exchange no EOP standalone
f1.keywords:
- NOCSH
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
description: Saiba mais sobre a interface de gerenciamento da Web no proteção autônoma do Exchange Online (EOP).
ms.openlocfilehash: 732991befa9084b62c152295d10a2bbf94bc36ec
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202946"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="c4a50-103">Centro de administração do Exchange no EOP standalone</span><span class="sxs-lookup"><span data-stu-id="c4a50-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c4a50-104">O centro de administração do Exchange (Eat) é um console de gerenciamento baseado na Web para o proteção do Exchange Online (EOP) autônomo.</span><span class="sxs-lookup"><span data-stu-id="c4a50-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="c4a50-105">Procurando a versão do Exchange Online deste tópico?</span><span class="sxs-lookup"><span data-stu-id="c4a50-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="c4a50-106">Confira [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c4a50-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="c4a50-107">Abra o Eat no EOP</span><span class="sxs-lookup"><span data-stu-id="c4a50-107">Open the EAC in EOP</span></span>

<span data-ttu-id="c4a50-108">Clientes autônomos do EOP podem acessar o Eat usando os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="c4a50-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="c4a50-109">**No centro de administração do Microsoft 365**:</span><span class="sxs-lookup"><span data-stu-id="c4a50-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="c4a50-110">Vá para <https://admin.microsoft.com> e clique em **Mostrar tudo**.</span><span class="sxs-lookup"><span data-stu-id="c4a50-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Clique em Mostrar tudo no centro de administração do Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="c4a50-112">Na seção **centros de administração** que aparece, clique em **todos os centros de administração**.</span><span class="sxs-lookup"><span data-stu-id="c4a50-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Clique em todos os centros de administração no centro de administração do Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="c4a50-114">Na página **todos os centros de administração** que aparece, clique em **proteção do Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="c4a50-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="c4a50-115">Ir diretamente para `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="c4a50-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="c4a50-116">Elementos de interface do usuário comuns no Eat no EOP</span><span class="sxs-lookup"><span data-stu-id="c4a50-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="c4a50-117">Esta seção descreve os elementos da interface do usuário encontrados no EAC.</span><span class="sxs-lookup"><span data-stu-id="c4a50-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="c4a50-119">Painel de recursos</span><span class="sxs-lookup"><span data-stu-id="c4a50-119">Feature Pane</span></span>

<span data-ttu-id="c4a50-p102">Este é o primeiro nível de navegação para a maioria das tarefas que você executará no EAC. O painel de recursos é organizado por áreas de recursos.</span><span class="sxs-lookup"><span data-stu-id="c4a50-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="c4a50-122">**Destinatários**: Este é o local em que você exibirá grupos e contatos externos.</span><span class="sxs-lookup"><span data-stu-id="c4a50-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="c4a50-123">**Permissões**: Este é o local em que você gerenciará funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="c4a50-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="c4a50-124">**Gerenciamento de conformidade**: aqui você encontrará o relatório do grupo de funções de administrador e o relatório de log de auditoria do administrador.</span><span class="sxs-lookup"><span data-stu-id="c4a50-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="c4a50-125">**Proteção**: aqui você pode gerenciar políticas Antimalware, a política de filtro de conexão padrão e o DKIM.</span><span class="sxs-lookup"><span data-stu-id="c4a50-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c4a50-126">Você deve gerenciar políticas antimalware e a política de filtro de conexão padrão no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="c4a50-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="c4a50-127">Para obter mais informações, consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md) e [Configure Connection Filtering in EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c4a50-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="c4a50-128">**Fluxo de email**: aqui você gerenciará as regras de fluxo de emails (também conhecidas como regras de transporte), domínios aceitos e conectores, bem como onde você pode ir para executar o rastreamento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="c4a50-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="c4a50-129">**Híbrido**: Este é o local onde você pode executar o [Assistente de configuração híbrida](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)e onde é possível instalar o [módulo do PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c4a50-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="c4a50-130">Guias</span><span class="sxs-lookup"><span data-stu-id="c4a50-130">Tabs</span></span>

<span data-ttu-id="c4a50-p104">As guias são seu segundo nível de navegação. Cada uma das áreas de recursos contém várias guias, cada uma representando um recurso.</span><span class="sxs-lookup"><span data-stu-id="c4a50-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="c4a50-133">Barra de ferramentas</span><span class="sxs-lookup"><span data-stu-id="c4a50-133">Toolbar</span></span>

<span data-ttu-id="c4a50-p105">Ao clicar na maioria das guias, você verá uma barra de ferramentas. A barra de ferramentas possui ícones que realizam ações específicas, A tabela a seguir descreve os ícones e suas ações.</span><span class="sxs-lookup"><span data-stu-id="c4a50-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="c4a50-137">Ícone</span><span class="sxs-lookup"><span data-stu-id="c4a50-137">Icon</span></span>|<span data-ttu-id="c4a50-138">Nome</span><span class="sxs-lookup"><span data-stu-id="c4a50-138">Name</span></span>|<span data-ttu-id="c4a50-139">Action</span><span class="sxs-lookup"><span data-stu-id="c4a50-139">Action</span></span>|
|---|---|---|
|![Ícone Adicionar](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="c4a50-141">Adicionar, Novo</span><span class="sxs-lookup"><span data-stu-id="c4a50-141">Add, New</span></span>|<span data-ttu-id="c4a50-p106">Use esse ícone para criar um novo objeto. Alguns desses ícones têm uma seta para baixo associada, na qual é possível clicar para exibir objetos adicionais que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="c4a50-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Ícone de edição](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="c4a50-145">Editar</span><span class="sxs-lookup"><span data-stu-id="c4a50-145">Edit</span></span>|<span data-ttu-id="c4a50-146">Use esse ícone para editar um objeto.</span><span class="sxs-lookup"><span data-stu-id="c4a50-146">Use this icon to edit an object.</span></span>|
|![Excluir ícone](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="c4a50-148">Excluir</span><span class="sxs-lookup"><span data-stu-id="c4a50-148">Delete</span></span>|<span data-ttu-id="c4a50-p107">Use esse ícone para excluir um objeto. Alguns ícones excluídos têm uma seta para baixo na qual é possível clicar para mostrar opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="c4a50-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Ícone Pesquisar](../../media/ITPro-EAC-.gif)|<span data-ttu-id="c4a50-152">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="c4a50-152">Search</span></span>|<span data-ttu-id="c4a50-153">Use esse ícone para abrir uma caixa de pesquisa na qual é possível digitar a frase de pesquisa para um objeto que você deseja encontrar.</span><span class="sxs-lookup"><span data-stu-id="c4a50-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ícone Atualizar](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="c4a50-155">Atualizar</span><span class="sxs-lookup"><span data-stu-id="c4a50-155">Refresh</span></span>|<span data-ttu-id="c4a50-156">Use essa opção para atualizar a exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="c4a50-156">Use this icon to refresh the list view.</span></span>|
|![Ícone Mais opções](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="c4a50-158">Mais opções</span><span class="sxs-lookup"><span data-stu-id="c4a50-158">More options</span></span>|<span data-ttu-id="c4a50-p108">Use esse ícone para ver mais ações que podem ser realizadas para os objetos dessa guia. Por exemplo, em **Destinatários \> Usuários**, um clique neste ícone mostra a opção para executar uma **Pesquisa Avançada**.  </span><span class="sxs-lookup"><span data-stu-id="c4a50-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.gif)![Ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="c4a50-163">Seta para cima e seta para baixo</span><span class="sxs-lookup"><span data-stu-id="c4a50-163">Up arrow and down arrow</span></span>|<span data-ttu-id="c4a50-164">Use esses ícones para mover a prioridade de um objeto para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="c4a50-164">Use these icons to move an object's priority up or down.</span></span>|
|![ícone Remover](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="c4a50-166">Remover</span><span class="sxs-lookup"><span data-stu-id="c4a50-166">Remove</span></span>|<span data-ttu-id="c4a50-167">Use esse ícone para remover objetos de uma lista.</span><span class="sxs-lookup"><span data-stu-id="c4a50-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="c4a50-168">Exibição de Lista</span><span class="sxs-lookup"><span data-stu-id="c4a50-168">List View</span></span>

<span data-ttu-id="c4a50-169">Ao selecionar uma guia, na maioria dos casos, você verá uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="c4a50-169">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="c4a50-170">O limite visualizável com o modo de exibição em lista do EAC é de aproximadamente 10.000 objetos.</span><span class="sxs-lookup"><span data-stu-id="c4a50-170">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="c4a50-171">Além disso, a paginação está incluída, para que você possa paginar os resultados.</span><span class="sxs-lookup"><span data-stu-id="c4a50-171">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="c4a50-172">Painel de Detalhes</span><span class="sxs-lookup"><span data-stu-id="c4a50-172">Details Pane</span></span>

<span data-ttu-id="c4a50-p110">Quando você seleciona um objeto na exibição de lista, informações sobre esse objeto são exibidas no painel de detalhes. Em alguns casos, o painel de detalhes inclui tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c4a50-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="c4a50-175">Bloco Eu e Ajuda</span><span class="sxs-lookup"><span data-stu-id="c4a50-175">Me tile and Help</span></span>

<span data-ttu-id="c4a50-176">O bloco **Eu** permite sair do EAC e entrar como um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="c4a50-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="c4a50-177">No **Help** ![ menu suspenso do ícone ajuda da ajuda ](../../media/ITPro-EAC-HelpIcon.gif) , é possível executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c4a50-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="c4a50-178">**Ajuda**: clique ![ no ícone ajuda ](../../media/ITPro-EAC-HelpIcon.gif) para exibir o conteúdo da ajuda online.</span><span class="sxs-lookup"><span data-stu-id="c4a50-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="c4a50-179">**Feedback**: deixar comentários.</span><span class="sxs-lookup"><span data-stu-id="c4a50-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="c4a50-180">**Comunidade**: poste uma pergunta para localizar respostas nos fóruns da Comunidade.</span><span class="sxs-lookup"><span data-stu-id="c4a50-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="c4a50-181">**Desabilitar bolha de ajuda**: a bolha de ajuda exibe a ajuda contextual para os campos quando você cria ou edita um objeto.</span><span class="sxs-lookup"><span data-stu-id="c4a50-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="c4a50-182">Você pode desativar a bolha de Ajuda ou ativá-la se tiver sido desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c4a50-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="c4a50-183">**Show Command Logging**: uma nova janela é aberta e mostra os comandos equivalentes do PowerShell com base no que você configurou no Eat.</span><span class="sxs-lookup"><span data-stu-id="c4a50-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="c4a50-184">Navegadores com suporte</span><span class="sxs-lookup"><span data-stu-id="c4a50-184">Supported Browsers</span></span>

<span data-ttu-id="c4a50-185">Para ter a melhor experiência ao usar o EAC, recomendamos que você sempre use os navegadores, clientes do Office e aplicativos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="c4a50-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="c4a50-186">Também recomendamos que você instale as atualizações de software quando elas estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c4a50-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="c4a50-187">Para obter mais informações sobre os navegadores e requisitos de sistema suportados para o serviço, consulte [System Requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="c4a50-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="c4a50-188">Idiomas compatíveis</span><span class="sxs-lookup"><span data-stu-id="c4a50-188">Supported languages</span></span>

<span data-ttu-id="c4a50-189">Os seguintes idiomas têm suporte e estão disponíveis para o Eat no EOP autônomo.</span><span class="sxs-lookup"><span data-stu-id="c4a50-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="c4a50-190">Amárico</span><span class="sxs-lookup"><span data-stu-id="c4a50-190">Amharic</span></span>
- <span data-ttu-id="c4a50-191">Árabe</span><span class="sxs-lookup"><span data-stu-id="c4a50-191">Arabic</span></span>
- <span data-ttu-id="c4a50-192">Basco (Basco)</span><span class="sxs-lookup"><span data-stu-id="c4a50-192">Basque (Basque)</span></span>
- <span data-ttu-id="c4a50-193">Bengali (Índia)</span><span class="sxs-lookup"><span data-stu-id="c4a50-193">Bengali (India)</span></span>
- <span data-ttu-id="c4a50-194">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="c4a50-194">Bulgarian</span></span>
- <span data-ttu-id="c4a50-195">Catalão</span><span class="sxs-lookup"><span data-stu-id="c4a50-195">Catalan</span></span>
- <span data-ttu-id="c4a50-196">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="c4a50-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="c4a50-197">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="c4a50-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="c4a50-198">Croata</span><span class="sxs-lookup"><span data-stu-id="c4a50-198">Croatian</span></span>
- <span data-ttu-id="c4a50-199">Tcheco</span><span class="sxs-lookup"><span data-stu-id="c4a50-199">Czech</span></span>
- <span data-ttu-id="c4a50-200">Dinamarquês</span><span class="sxs-lookup"><span data-stu-id="c4a50-200">Danish</span></span>
- <span data-ttu-id="c4a50-201">Holandês</span><span class="sxs-lookup"><span data-stu-id="c4a50-201">Dutch</span></span>
- <span data-ttu-id="c4a50-202">Inglês</span><span class="sxs-lookup"><span data-stu-id="c4a50-202">English</span></span>
- <span data-ttu-id="c4a50-203">Estoniano</span><span class="sxs-lookup"><span data-stu-id="c4a50-203">Estonian</span></span>
- <span data-ttu-id="c4a50-204">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="c4a50-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="c4a50-205">Finlandês</span><span class="sxs-lookup"><span data-stu-id="c4a50-205">Finnish</span></span>
- <span data-ttu-id="c4a50-206">Francês</span><span class="sxs-lookup"><span data-stu-id="c4a50-206">French</span></span>
- <span data-ttu-id="c4a50-207">Galego</span><span class="sxs-lookup"><span data-stu-id="c4a50-207">Galician</span></span>
- <span data-ttu-id="c4a50-208">Alemão</span><span class="sxs-lookup"><span data-stu-id="c4a50-208">German</span></span>
- <span data-ttu-id="c4a50-209">Grego</span><span class="sxs-lookup"><span data-stu-id="c4a50-209">Greek</span></span>
- <span data-ttu-id="c4a50-210">Gujarati</span><span class="sxs-lookup"><span data-stu-id="c4a50-210">Gujarati</span></span>
- <span data-ttu-id="c4a50-211">Hebraico</span><span class="sxs-lookup"><span data-stu-id="c4a50-211">Hebrew</span></span>
- <span data-ttu-id="c4a50-212">Híndi</span><span class="sxs-lookup"><span data-stu-id="c4a50-212">Hindi</span></span>
- <span data-ttu-id="c4a50-213">Húngaro</span><span class="sxs-lookup"><span data-stu-id="c4a50-213">Hungarian</span></span>
- <span data-ttu-id="c4a50-214">Islandês</span><span class="sxs-lookup"><span data-stu-id="c4a50-214">Icelandic</span></span>
- <span data-ttu-id="c4a50-215">Indonésio</span><span class="sxs-lookup"><span data-stu-id="c4a50-215">Indonesian</span></span>
- <span data-ttu-id="c4a50-216">Italiano</span><span class="sxs-lookup"><span data-stu-id="c4a50-216">Italian</span></span>
- <span data-ttu-id="c4a50-217">Japonês</span><span class="sxs-lookup"><span data-stu-id="c4a50-217">Japanese</span></span>
- <span data-ttu-id="c4a50-218">Kannada</span><span class="sxs-lookup"><span data-stu-id="c4a50-218">Kannada</span></span>
- <span data-ttu-id="c4a50-219">Cazaque</span><span class="sxs-lookup"><span data-stu-id="c4a50-219">Kazakh</span></span>
- <span data-ttu-id="c4a50-220">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="c4a50-220">Kiswahili</span></span>
- <span data-ttu-id="c4a50-221">Coreano</span><span class="sxs-lookup"><span data-stu-id="c4a50-221">Korean</span></span>
- <span data-ttu-id="c4a50-222">Letão</span><span class="sxs-lookup"><span data-stu-id="c4a50-222">Latvian</span></span>
- <span data-ttu-id="c4a50-223">Lituano</span><span class="sxs-lookup"><span data-stu-id="c4a50-223">Lithuanian</span></span>
- <span data-ttu-id="c4a50-224">Malaio (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="c4a50-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="c4a50-225">Malaio (Malásia)</span><span class="sxs-lookup"><span data-stu-id="c4a50-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="c4a50-226">Malaiala</span><span class="sxs-lookup"><span data-stu-id="c4a50-226">Malayalam</span></span>
- <span data-ttu-id="c4a50-227">Marati</span><span class="sxs-lookup"><span data-stu-id="c4a50-227">Marathi</span></span>
- <span data-ttu-id="c4a50-228">Norueguês (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="c4a50-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="c4a50-229">Norueguês (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="c4a50-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="c4a50-230">Oriá</span><span class="sxs-lookup"><span data-stu-id="c4a50-230">Oriya</span></span>
- <span data-ttu-id="c4a50-231">Persa</span><span class="sxs-lookup"><span data-stu-id="c4a50-231">Persian</span></span>
- <span data-ttu-id="c4a50-232">Polonês</span><span class="sxs-lookup"><span data-stu-id="c4a50-232">Polish</span></span>
- <span data-ttu-id="c4a50-233">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="c4a50-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="c4a50-234">Português (Portugal)</span><span class="sxs-lookup"><span data-stu-id="c4a50-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="c4a50-235">Romeno</span><span class="sxs-lookup"><span data-stu-id="c4a50-235">Romanian</span></span>
- <span data-ttu-id="c4a50-236">Russo</span><span class="sxs-lookup"><span data-stu-id="c4a50-236">Russian</span></span>
- <span data-ttu-id="c4a50-237">Sérvio (cirílico, Sérvia)</span><span class="sxs-lookup"><span data-stu-id="c4a50-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="c4a50-238">Sérvio (latino)</span><span class="sxs-lookup"><span data-stu-id="c4a50-238">Serbian (Latin)</span></span>
- <span data-ttu-id="c4a50-239">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="c4a50-239">Slovak</span></span>
- <span data-ttu-id="c4a50-240">Esloveno</span><span class="sxs-lookup"><span data-stu-id="c4a50-240">Slovenian</span></span>
- <span data-ttu-id="c4a50-241">Espanhol</span><span class="sxs-lookup"><span data-stu-id="c4a50-241">Spanish</span></span>
- <span data-ttu-id="c4a50-242">Sueco</span><span class="sxs-lookup"><span data-stu-id="c4a50-242">Swedish</span></span>
- <span data-ttu-id="c4a50-243">Tâmil</span><span class="sxs-lookup"><span data-stu-id="c4a50-243">Tamil</span></span>
- <span data-ttu-id="c4a50-244">Telugu</span><span class="sxs-lookup"><span data-stu-id="c4a50-244">Telugu</span></span>
- <span data-ttu-id="c4a50-245">Tailandês</span><span class="sxs-lookup"><span data-stu-id="c4a50-245">Thai</span></span>
- <span data-ttu-id="c4a50-246">Turco</span><span class="sxs-lookup"><span data-stu-id="c4a50-246">Turkish</span></span>
- <span data-ttu-id="c4a50-247">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="c4a50-247">Ukrainian</span></span>
- <span data-ttu-id="c4a50-248">Urdu</span><span class="sxs-lookup"><span data-stu-id="c4a50-248">Urdu</span></span>
- <span data-ttu-id="c4a50-249">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="c4a50-249">Vietnamese</span></span>
- <span data-ttu-id="c4a50-250">Galês</span><span class="sxs-lookup"><span data-stu-id="c4a50-250">Welsh</span></span>
