---
title: Gerenciar contratos usando uma solução do Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Saiba como gerenciar contratos usando uma solução Microsoft 365 de SharePoint Syntex, SharePoint Listas, Microsoft Teams e Power Automate.
ms.openlocfilehash: bc2570b08add2fa93637b9f64931c5903795a079
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287312"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="89363-103">Gerenciar contratos usando uma solução do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89363-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="89363-104">Este artigo descreve como criar uma solução de gerenciamento de contratos para sua organização usando SharePoint Syntex e componentes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89363-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="89363-105">Ele fornece uma estrutura para ajudá-lo a planejar e criar uma solução que se ajuste às suas necessidades de negócios exclusivas.</span><span class="sxs-lookup"><span data-stu-id="89363-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="89363-106">Mesmo que essa solução fale sobre gerenciamento de contratos, você pode adaptá-la para criar outras soluções de gerenciamento de documentos, como instruções de trabalho ou faturas.</span><span class="sxs-lookup"><span data-stu-id="89363-106">Even though this solution talks about contract management, you can adapt it to create other document management solutions, such as for statements of work or invoices.</span></span>

<span data-ttu-id="89363-107">*Esse conjunto de conteúdo documenta uma Microsoft 365 desenvolvida por Thomas Molbach com a Equipe de Estratégia de Solução de Trabalho Moderna da Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="89363-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="89363-108">Identificar o problema de negócios</span><span class="sxs-lookup"><span data-stu-id="89363-108">Identify the business problem</span></span>

<span data-ttu-id="89363-109">A primeira etapa no planejamento do sistema de gerenciamento de contratos é entender o problema que você está tentando resolver.</span><span class="sxs-lookup"><span data-stu-id="89363-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="89363-110">Para essa solução, quatro problemas principais precisam ser resolvidos:</span><span class="sxs-lookup"><span data-stu-id="89363-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="89363-111">**Identificar contratos**.</span><span class="sxs-lookup"><span data-stu-id="89363-111">**Identify contracts**.</span></span> <span data-ttu-id="89363-112">Sua organização trabalha com muitos documentos, como faturas, contratos, instruções de trabalho e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="89363-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="89363-113">Alguns são ativos digitais enviados por email e alguns são ativos de papel enviados por email tradicional.</span><span class="sxs-lookup"><span data-stu-id="89363-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="89363-114">Você precisa de uma maneira de identificar todos os contratos de clientes de todos os outros documentos e classificá-los como tal.</span><span class="sxs-lookup"><span data-stu-id="89363-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="89363-115">**Acompanhe o histórico de aprovações de contrato.**</span><span class="sxs-lookup"><span data-stu-id="89363-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="89363-116">Sua organização precisa de uma maneira confiável de descobrir se os contratos foram aprovados ou rejeitados e se o pagamento foi processado.</span><span class="sxs-lookup"><span data-stu-id="89363-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="89363-117">**Site para gerenciar aprovações de contrato**.</span><span class="sxs-lookup"><span data-stu-id="89363-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="89363-118">Sua organização precisa configurar um site colaborativo no qual todos os participantes necessários possam revisar facilmente contratos.</span><span class="sxs-lookup"><span data-stu-id="89363-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="89363-119">As partes interessadas devem ser capazes de revisar todo o contrato, se necessário, mas principalmente se preocupam em ver vários campos principais de cada contrato (por exemplo, nome do cliente, número de PO e custo total).</span><span class="sxs-lookup"><span data-stu-id="89363-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="89363-120">As partes interessadas devem ser capazes de aprovar ou rejeitar facilmente contratos de entrada.</span><span class="sxs-lookup"><span data-stu-id="89363-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="89363-121">**Roteia contratos revisados**.</span><span class="sxs-lookup"><span data-stu-id="89363-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="89363-122">Contratos aprovados e rejeitados precisam ser roteados por meio de um fluxo de trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="89363-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="89363-123">Os contratos aprovados precisam ser roteados para um aplicativo de terceiros para processamento de pagamento.</span><span class="sxs-lookup"><span data-stu-id="89363-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="89363-124">Os contratos rejeitados precisam ser roteados para revisão adicional.</span><span class="sxs-lookup"><span data-stu-id="89363-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="89363-125">Visão geral da solução</span><span class="sxs-lookup"><span data-stu-id="89363-125">Overview of the solution</span></span>

  ![Diagrama da solução usando SharePoint Syntex, SharePoint listas, Teams e Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="89363-127">Esta orientação de solução de gerenciamento de contratos inclui quatro componentes de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="89363-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="89363-128">**Microsoft SharePoint Syntex:** crie modelos para identificar e classificar seus arquivos de contrato e, em seguida, extrair os dados apropriados deles.</span><span class="sxs-lookup"><span data-stu-id="89363-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="89363-129">**Listas SharePoint** Microsoft : Use a formatação disponível em listas SharePoint modernas para apresentar contratos em um formato amigável para os negócios.</span><span class="sxs-lookup"><span data-stu-id="89363-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="89363-130">**Microsoft Teams**: use a funcionalidade de um canal Teams e guias associadas para permitir que seus participantes revisem e gerenciem contratos.</span><span class="sxs-lookup"><span data-stu-id="89363-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="89363-131">**Power Automate**: use fluxos para orientar contratos por meio do processo de aprovação e, em seguida, para um aplicativo de terceiros para pagamento.</span><span class="sxs-lookup"><span data-stu-id="89363-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="89363-132">Como tudo funciona</span><span class="sxs-lookup"><span data-stu-id="89363-132">How it all works</span></span>

  ![Diagrama da solução mostrando o fluxo de trabalho para carregar documentos, extrair dados, notificar as partes interessadas e aprovar ou rejeitar o contrato.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="89363-134">Os documentos são carregados em uma biblioteca SharePoint de documentos.</span><span class="sxs-lookup"><span data-stu-id="89363-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="89363-135">Um SharePoint Syntex de entendimento de documentos foi aplicado à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="89363-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="89363-136">Ele verifica cada arquivo para ver se algum corresponder a um tipo de conteúdo "contrato" que ele está treinado para procurar.</span><span class="sxs-lookup"><span data-stu-id="89363-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="89363-137">Se encontrar uma combinação, ele classifica o arquivo como um "contrato" e atualiza o tipo de conteúdo do documento.</span><span class="sxs-lookup"><span data-stu-id="89363-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="89363-138">O modelo também retira dados específicos de cada arquivo de contrato que as partes interessadas em ver, como *o Cliente,* o Prestador *de* Serviços e o valor da *taxa.*</span><span class="sxs-lookup"><span data-stu-id="89363-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="89363-139">A página a seguir é um exemplo de um contrato que o modelo é treinado para identificar.</span><span class="sxs-lookup"><span data-stu-id="89363-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![Exemplo de um contrato.](../media/content-understanding/contract.png)

3. <span data-ttu-id="89363-141">No Microsoft Teams, todos os participantes são membros de um canal seguro Teams no qual todos os contratos na biblioteca de documentos ficam visíveis para aprovação ou rejeição.</span><span class="sxs-lookup"><span data-stu-id="89363-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="89363-142">Usando Teams funcionalidade, todas as partes interessadas são notificadas quando novos contratos precisam ser revistos.</span><span class="sxs-lookup"><span data-stu-id="89363-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>

4. <span data-ttu-id="89363-143">Usando o Power Automate, os contratos são movidos pelo processo de aprovação no Teams canal.</span><span class="sxs-lookup"><span data-stu-id="89363-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="89363-144">Quando um membro aprova um contrato, o status do contrato é alterado para aprovado, todos os membros são notificados por meio de uma postagem Teams e um item de linha é criado para mostrar que o contrato está pronto para pagamento.</span><span class="sxs-lookup"><span data-stu-id="89363-144">When a member approves a contract, the contract status is changed to approved, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="89363-145">Esse processo pode ser estendido para gravar diretamente em um aplicativo financeiro de terceiros para pagamento.</span><span class="sxs-lookup"><span data-stu-id="89363-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5. <span data-ttu-id="89363-146">Quando um membro rejeita um contrato, o status é alterado para rejeitado e todos os membros são notificados por meio de Teams postagem.</span><span class="sxs-lookup"><span data-stu-id="89363-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="89363-147">O resultado final dessa solução é um processo de negócios automatizado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="89363-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="89363-148">Os funcionários podem usar facilmente a exibição de Teams para iniciar e monitorar o fluxo de trabalho de aprovação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="89363-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![Guia Contratos.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="89363-150">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="89363-150">Licensing requirements</span></span>

<span data-ttu-id="89363-151">Essa solução se baseia na seguinte funcionalidade, tudo disponível como parte de uma licença de Microsoft 365 Enterprise (E1, E3, E5, F3) ou Business (Basic, Standard ou Premium).</span><span class="sxs-lookup"><span data-stu-id="89363-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

- <span data-ttu-id="89363-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="89363-152">Microsoft SharePoint Syntex</span></span>
- <span data-ttu-id="89363-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89363-153">Microsoft Teams</span></span>
- <span data-ttu-id="89363-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="89363-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="89363-155">Criar a solução</span><span class="sxs-lookup"><span data-stu-id="89363-155">Create the solution</span></span>

<span data-ttu-id="89363-156">As próximas seções entrarão em detalhes sobre como configurar a solução de gerenciamento de contratos.</span><span class="sxs-lookup"><span data-stu-id="89363-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="89363-157">Ele é dividido em três etapas:</span><span class="sxs-lookup"><span data-stu-id="89363-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="89363-158">Etapa 1. Use SharePoint Syntex para identificar arquivos de contrato e extrair dados</span><span class="sxs-lookup"><span data-stu-id="89363-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="89363-159">Etapa 2. Use Microsoft Teams para criar seu canal de gerenciamento de contratos</span><span class="sxs-lookup"><span data-stu-id="89363-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="89363-160">Etapa 3. Use Power Automate para criar seu fluxo para processar seus contratos</span><span class="sxs-lookup"><span data-stu-id="89363-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
