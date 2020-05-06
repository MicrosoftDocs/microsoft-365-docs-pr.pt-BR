---
title: Notas de versão para descoberta eletrônica avançada
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
description: Este artigo contém as notas de versão da descoberta eletrônica avançada, incluindo problemas conhecidos, problemas corrigidos e novos recursos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 45a4647856fef0186840ec5465bb9250e5d78de4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034615"
---
# <a name="release-notes-for-advanced-ediscovery"></a><span data-ttu-id="4bf44-103">Notas de versão para descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="4bf44-103">Release notes for Advanced eDiscovery</span></span>

<span data-ttu-id="4bf44-104">O programa de visualização pública para descoberta eletrônica avançada é a maneira de obter acesso antecipado à funcionalidade e às atualizações futuras.</span><span class="sxs-lookup"><span data-stu-id="4bf44-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="4bf44-105">Para obter acesso antecipado aos recursos mais recentes, basta criar e usar uma caixa de descoberta eletrônica avançada no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="4bf44-105">To get early access to the newest features, just create and use an Advanced eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="4bf44-106">Confira [criar um novo caso](create-new-ediscovery-case.md).</span><span class="sxs-lookup"><span data-stu-id="4bf44-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="4bf44-107">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="4bf44-107">Known issues</span></span>

<span data-ttu-id="4bf44-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="4bf44-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="4bf44-109">Os dados correspondentes a um formulário criado antes de 31 de janeiro de 2019 não poderão ser pesquisados ao usar a ferramenta de pesquisa na descoberta eletrônica avançada para pesquisar caixas de correio de responsáveis.</span><span class="sxs-lookup"><span data-stu-id="4bf44-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="4bf44-110">Formulários criados após essa data estarão disponíveis para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4bf44-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="4bf44-111">Um formulário criado por um usuário ainda pode receber respostas, mesmo depois que o usuário que criou o formulário é excluído.</span><span class="sxs-lookup"><span data-stu-id="4bf44-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="4bf44-112">No entanto, os dados correspondentes para essas respostas (que ocorreram depois da exclusão da caixa de correio) não poderão ser pesquisados ao usar a ferramenta de pesquisa na descoberta eletrônica avançada para pesquisar caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="4bf44-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span>
 
<span data-ttu-id="4bf44-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="4bf44-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="4bf44-114">Se um usuário editar um Sway imediatamente antes da exclusão da conta de usuário para o proprietário desse Sway, essas alterações poderão não ser pesquisadas ao usar a ferramenta de pesquisa na descoberta eletrônica avançada para pesquisar caixas de correio de responsáveis.</span><span class="sxs-lookup"><span data-stu-id="4bf44-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="4bf44-115">O Sway bloqueia alterações em um Sway assim que recebe um sinal de que a conta foi excluída.</span><span class="sxs-lookup"><span data-stu-id="4bf44-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="4bf44-116">No entanto, há uma pequena chance de que um Sway possa ser editado antes que esse sinal seja recebido.</span><span class="sxs-lookup"><span data-stu-id="4bf44-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="4bf44-117">Problemas corrigidos nesta versão</span><span class="sxs-lookup"><span data-stu-id="4bf44-117">Issues fixed in this release</span></span>

- <span data-ttu-id="4bf44-118">DCR: manipulação de exceção para itens não indexados e itens órfãos</span><span class="sxs-lookup"><span data-stu-id="4bf44-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="4bf44-119">DCR: notificações de bloqueio</span><span class="sxs-lookup"><span data-stu-id="4bf44-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="4bf44-120">DCR: responsáveis pela descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="4bf44-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="4bf44-121">Novidades</span><span class="sxs-lookup"><span data-stu-id="4bf44-121">What's new</span></span>

- <span data-ttu-id="4bf44-122">**Navegação reprojetada no centro de conformidade e segurança &** – a descoberta eletrônica avançada tem uma nova aparência.</span><span class="sxs-lookup"><span data-stu-id="4bf44-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery has a new look and feel.</span></span> <span data-ttu-id="4bf44-123">Use a descoberta eletrônica avançada para gerenciar mais de seu fluxo de trabalho de caso.</span><span class="sxs-lookup"><span data-stu-id="4bf44-123">Use Advanced eDiscovery to manage more of your case workflow.</span></span>

- <span data-ttu-id="4bf44-124">**Gerenciamento de casos** – há suporte adicional para novos tipos de caso.</span><span class="sxs-lookup"><span data-stu-id="4bf44-124">**Case management** – There's additional support for new case types.</span></span> <span data-ttu-id="4bf44-125">Você também pode selecionar e salvar seus casos recentes e favoritos.</span><span class="sxs-lookup"><span data-stu-id="4bf44-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="4bf44-126">Controlar e monitorar a atividade em e entre casos usando novos painéis.</span><span class="sxs-lookup"><span data-stu-id="4bf44-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="4bf44-127">**Gerenciamento de responsáveis** – adicione e remova usuários como responsáveis por dados em um caso.</span><span class="sxs-lookup"><span data-stu-id="4bf44-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="4bf44-128">**Integração com o Exchange, o onedrive e o Teams** – adicione automaticamente a caixa de correio de um usuário, a conta do onedrive for Business e os sites do Microsoft Teams a uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="4bf44-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user's current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="4bf44-129">**Comunicações de responsáveis** – envie e gerencie notificações de retenção legal em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4bf44-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="4bf44-130">**Portal de responsáveis** – novo portal para que os responsáveis acessem seus avisos de isenção ativos.</span><span class="sxs-lookup"><span data-stu-id="4bf44-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="4bf44-131">**Indexação profunda** – Rastreie novamente os itens parcialmente indexados sob demanda.</span><span class="sxs-lookup"><span data-stu-id="4bf44-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="4bf44-132">**Correção de erro** : corrigir ou baixar erros de processamento; Isso inclui suporte de correção para tipos de arquivo grandes, arquivos protegidos por senha e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4bf44-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="4bf44-133">**Melhorias na pesquisa** – crie uma pesquisa identificando os responsáveis e/ou locais.</span><span class="sxs-lookup"><span data-stu-id="4bf44-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="4bf44-134">**Conjuntos de revisão** – gerencie, rastreie e faça auditoria de conjuntos estáticos de documentos.</span><span class="sxs-lookup"><span data-stu-id="4bf44-134">**Review sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="4bf44-135">**Revisão** – use um modo de exibição nativo, de texto e quase nativo para revisar os documentos adicionados ao conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="4bf44-135">**Review** – Use a native, text, and near-native view to review documents added to your review set.</span></span>

- <span data-ttu-id="4bf44-136">**Redigir, marcar e anotar** – redigir texto, aplicar marcas e fazer anotações à medida que você revisar documentos.</span><span class="sxs-lookup"><span data-stu-id="4bf44-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="4bf44-137">**Análise com capacidade para análise**– Aproveite a análise de descoberta eletrônica avançada para localizar, Pesquisar e buscar resultados em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="4bf44-137">**Analytics-powered review**– Leverage Advanced eDiscovery analytics to find, search, and cull results within a review set.</span></span>

- <span data-ttu-id="4bf44-138">**Jobs** – rastreie o status de processos de execução longa.</span><span class="sxs-lookup"><span data-stu-id="4bf44-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="4bf44-139">**Novas atividades de auditoria** – rastrear e exibir novas atividades de auditoria para descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="4bf44-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
