---
title: Gerenciador de Conformidade da Microsoft e o RGPD
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O Microsoft Compliance Manager é uma ferramenta gratuita de avaliação de risco baseada em fluxo de trabalho no Portal de Confiança do Serviço da Microsoft. O Gerenciador de Conformidade permite rastrear, atribuir e verificar atividades de conformidade regulamentar relacionadas aos serviços de nuvem da Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595798"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="5ef01-104">Gerenciador de Conformidade da Microsoft e o RGPD</span><span class="sxs-lookup"><span data-stu-id="5ef01-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="5ef01-105">O RGPD (Regulamento Geral sobre a Proteção de Dados) imposto pela União Europeia pode afetar sua estratégia de conformidade e autorizar ações específicas para gerenciar informações de usuários e clientes usadas no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="5ef01-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="5ef01-106">Configurações de privacidade do usuário</span><span class="sxs-lookup"><span data-stu-id="5ef01-106">User Privacy settings</span></span>

<span data-ttu-id="5ef01-107">Determinadas regulamentações exigem que uma organização deve ser capaz de excluir dados do histórico do usuário.</span><span class="sxs-lookup"><span data-stu-id="5ef01-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="5ef01-108">O Gerenciador de Conformidade **fornece funções de Configurações de Privacidade** do Usuário que permitem aos administradores:</span><span class="sxs-lookup"><span data-stu-id="5ef01-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="5ef01-109">Procurar um usuário</span><span class="sxs-lookup"><span data-stu-id="5ef01-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="5ef01-110">Exportar um relatório do histórico de dados da conta</span><span class="sxs-lookup"><span data-stu-id="5ef01-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="5ef01-111">Excluir o histórico de dados do usuário</span><span class="sxs-lookup"><span data-stu-id="5ef01-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="5ef01-112">Procurar um usuário</span><span class="sxs-lookup"><span data-stu-id="5ef01-112">Search for a user</span></span>

<span data-ttu-id="5ef01-113">Para procurar uma conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="5ef01-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="5ef01-114">Insira o alias de email do usuário (as informações à esquerda do símbolo @) e escolha o nome de domínio na lista de sufixos de domínio à direita.</span><span class="sxs-lookup"><span data-stu-id="5ef01-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="5ef01-115">Para organizações com vários domínios registrados, verifique o sufixo de nome de domínio para garantir que ele esteja correto.</span><span class="sxs-lookup"><span data-stu-id="5ef01-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="5ef01-116">Quando você tiver o nome de usuário inserido corretamente, selecione **Pesquisar.**</span><span class="sxs-lookup"><span data-stu-id="5ef01-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="5ef01-117">Para contas de usuário não retornadas, a página exibe **o usuário não encontrado.**</span><span class="sxs-lookup"><span data-stu-id="5ef01-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="5ef01-118">Verifique as informações de endereço de email do usuário e faça as correções necessárias.</span><span class="sxs-lookup"><span data-stu-id="5ef01-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="5ef01-119">Para tentar novamente, selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="5ef01-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="5ef01-120">Para contas de usuário retornadas, o texto do botão muda de **Pesquisar** para **Limpar.**</span><span class="sxs-lookup"><span data-stu-id="5ef01-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="5ef01-121">Isso indica que a conta de usuário retornada é o contexto operacional para as funções adicionais e que essas funções se aplicam a essa conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5ef01-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="5ef01-122">Para limpar os resultados da pesquisa e procurar um usuário diferente, selecione **Limpar.**</span><span class="sxs-lookup"><span data-stu-id="5ef01-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="5ef01-123">Exportar um relatório do histórico de dados da conta</span><span class="sxs-lookup"><span data-stu-id="5ef01-123">Export a report of account data history</span></span>

<span data-ttu-id="5ef01-124">Para cada conta de usuário identificada, você pode gerar um relatório de dependências vinculadas à conta.</span><span class="sxs-lookup"><span data-stu-id="5ef01-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="5ef01-125">Essas informações permitem reatribuir itens de ação abertos ou garantir o acesso a evidências carregadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5ef01-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="5ef01-126">Para gerar e exportar um relatório:</span><span class="sxs-lookup"><span data-stu-id="5ef01-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="5ef01-127">Selecione **Exportar** para gerar e baixar um relatório dos Itens de Ação de controle do Gerenciador de Conformidade atualmente atribuídos à conta de usuário retornada e a lista de documentos carregados por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="5ef01-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="5ef01-128">Se não houver ações atribuídas ou documentos carregados, uma mensagem de erro informa "Nenhum dado para este usuário".</span><span class="sxs-lookup"><span data-stu-id="5ef01-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="5ef01-129">O relatório é baixado em segundo plano na janela ativa do navegador — se você não vir um pop-up de download que você deseja verificar o histórico de download do navegador.</span><span class="sxs-lookup"><span data-stu-id="5ef01-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="5ef01-130">Abra o documento para verificar os dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="5ef01-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ef01-131">Os dados do relatório não são uma lista histórica que retém e exibe alterações de estado no histórico de atribuições do Item de Ação.</span><span class="sxs-lookup"><span data-stu-id="5ef01-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="5ef01-132">O relatório gerado é um instantâneo do controle Itens de Ação atribuídos no momento em que o relatório é executado (carimbo de data e hora gravado no relatório).</span><span class="sxs-lookup"><span data-stu-id="5ef01-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="5ef01-133">Por exemplo, qualquer reatribuição subsequente de Itens de Ação resultará em dados de relatório de instantâneos diferentes se o relatório for gerado novamente para o mesmo usuário.</span><span class="sxs-lookup"><span data-stu-id="5ef01-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="5ef01-134">Excluir o histórico de dados do usuário</span><span class="sxs-lookup"><span data-stu-id="5ef01-134">Delete user data history</span></span>

<span data-ttu-id="5ef01-135">Define todos os Itens de Ação de controle atribuídos ao usuário retornado como "não atribuído".</span><span class="sxs-lookup"><span data-stu-id="5ef01-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="5ef01-136">Define o **carregamento pelo valor** de todos os documentos carregados pelo usuário retornado como "usuário removido".</span><span class="sxs-lookup"><span data-stu-id="5ef01-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="5ef01-137">Para excluir o Item de Ação da conta de usuário e o histórico de carregamento do documento:</span><span class="sxs-lookup"><span data-stu-id="5ef01-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="5ef01-138">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5ef01-138">Select **Delete**.</span></span>

    <span data-ttu-id="5ef01-139">Uma caixa de diálogo de confirmação é exibida: " Isso remove todas as atribuições de Item de Ação de controle e o histórico de carregamento do documento *para o usuário selecionado. Essa ação é permanente. Tem certeza de que deseja continuar?*"</span><span class="sxs-lookup"><span data-stu-id="5ef01-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="5ef01-140">Para continuar a selecionar **OK,** caso contrário, **selecione Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5ef01-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
