---
title: Trabalhar com os responsáveis na descoberta eletrônica avançada
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
description: A ferramenta de gerenciamento de responsáveis em descoberta eletrônica avançada permite que você gerencie o fluxo de trabalho em torno da identificação, preservação e coleta de dados associados às pessoas de interesse em um caso jurídico.
ms.openlocfilehash: fd796471ae4caeafbabc7b588dcf03b8cad80bc4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600488"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="fd543-103">Trabalhar com os responsáveis na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="fd543-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="fd543-104">Quando uma organização responde a uma investigação legal, o fluxo de trabalho em torno da identificação, preservação e coleta de conteúdo potencialmente relevante é baseado nas pessoas da organização que são os responsáveis por dados relevantes.</span><span class="sxs-lookup"><span data-stu-id="fd543-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="fd543-105">Na descoberta eletrônica, esses indivíduos são chamados de *responsáveis por dados de dados* (ou apenas *responsáveis*) e são definidos como "pessoas com controle administrativo de um documento ou arquivo eletrônico".</span><span class="sxs-lookup"><span data-stu-id="fd543-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="fd543-106">Por exemplo, os responsáveis por uma mensagem de email podem ser o proprietário da caixa de correio que contém a mensagem relevante.</span><span class="sxs-lookup"><span data-stu-id="fd543-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="fd543-107">Quando uma investigação começa, a equipe de descoberta eletrônica deve identificar rapidamente todos os responsáveis e fontes de dados relevantes relacionados ao caso.</span><span class="sxs-lookup"><span data-stu-id="fd543-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="fd543-108">Com o tempo, a lista de responsáveis e suas fontes de dados podem aumentar ou decreasser.</span><span class="sxs-lookup"><span data-stu-id="fd543-108">Over time, the list of custodians and their data sources may increase or decreasse.</span></span> <span data-ttu-id="fd543-109">Como resultado, as organizações devem manter um processo controlado em torno da identificação, preservação e coleta de conteúdo do custodial ao longo do ciclo de vida de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="fd543-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="fd543-110">Em um caso de descoberta eletrônica avançada, as equipes jurídicas podem adicionar pessoas em sua organização como responsáveis e identificar e preservar automaticamente as fontes de dados do custodial, como caixas de correio do Exchange, contas do OneDrive e sites do SharePoint e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd543-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="fd543-111">Usando a ferramenta de gerenciamento de responsáveis interna na descoberta eletrônica avançada, as organizações podem proteger as informações armazenadas eletronicamente de forma inadvertida (ou intencional).</span><span class="sxs-lookup"><span data-stu-id="fd543-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="fd543-112">Isso permite eliminar o processo demorado e sujeito a erros de ter que executar manualmente os processos de retenção legal.</span><span class="sxs-lookup"><span data-stu-id="fd543-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="fd543-113">Para obter mais informações sobre como trabalhar com os responsáveis, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd543-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="fd543-114">Adicionar custodiantes a uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="fd543-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="fd543-115">Gerenciar os responsáveis em um caso</span><span class="sxs-lookup"><span data-stu-id="fd543-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="fd543-116">Exibir a atividade custodiante</span><span class="sxs-lookup"><span data-stu-id="fd543-116">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a><span data-ttu-id="fd543-117">Permissões de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="fd543-117">Advanced eDiscovery permissions</span></span>

<span data-ttu-id="fd543-118">Na descoberta eletrônica avançada, você pode usar o grupo de função Gerenciador de descoberta eletrônica interno para atribuir as permissões necessárias aos investigadores legais para que eles possam gerenciar o fluxo de trabalho de ponta a ponta na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="fd543-118">In Advanced eDiscovery, you can use the built-in eDiscovery Manager role group to assign the necessary permissions to legal investigators so they can manage the end-to-end workflow in Advanced eDiscovery.</span></span> <span data-ttu-id="fd543-119">Como alternativa, você pode criar grupos de função personalizados com um subconjunto das funções necessárias para executar determinadas ações em um caso de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="fd543-119">Alternatively, you can create custom role groups with a subset of the roles necessary to perform certain actions in a case in Advanced eDiscovery.</span></span> <span data-ttu-id="fd543-120">Para obter mais informações sobre funções relacionadas à descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica no centro de conformidade de & de segurança](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fd543-120">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
