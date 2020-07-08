---
title: Automatizar retenção orientada a eventos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Este tópico explica como configurar os fluxos dos processos empresariais para automatizar a retenção por meio de eventos usando a API REST do Microsoft 365.
ms.openlocfilehash: 15d2dd8417cf0a22b8db63f64c0bbb288e74880c
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046059"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="8d2fc-103">Automatizar retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-103">Automate event-based retention</span></span>

><span data-ttu-id="8d2fc-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="8d2fc-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8d2fc-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span></span> <span data-ttu-id="8d2fc-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span></span> <span data-ttu-id="8d2fc-107">Retaining only important, pertinent information is key to an organization's success.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-107">Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="8d2fc-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="8d2fc-109">Retention can be triggered by using [retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-109">Retention can be triggered by using [retention labels](labels.md).</span></span> <span data-ttu-id="8d2fc-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span></span> <span data-ttu-id="8d2fc-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span></span> <span data-ttu-id="8d2fc-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="8d2fc-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span></span> <span data-ttu-id="8d2fc-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="8d2fc-115">Event-based retention solves this problem.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-115">Event-based retention solves this problem.</span></span> <span data-ttu-id="8d2fc-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="8d2fc-117">Sobre a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-117">About event-based retention</span></span>

<span data-ttu-id="8d2fc-118">An organization can be small, medium, or large.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-118">An organization can be small, medium, or large.</span></span> <span data-ttu-id="8d2fc-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="8d2fc-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span></span> <span data-ttu-id="8d2fc-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span></span> <span data-ttu-id="8d2fc-122">This process is subject to the different retention policies outlined for the business:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-122">This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="8d2fc-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span></span> <span data-ttu-id="8d2fc-124">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-124">For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="8d2fc-125">**The period of retention of content can also be an unknown date**.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-125">**The period of retention of content can also be an unknown date**.</span></span> <span data-ttu-id="8d2fc-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="8d2fc-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span> <span data-ttu-id="8d2fc-128">This is called event-based retention.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-128">This is called event-based retention.</span></span> <span data-ttu-id="8d2fc-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="8d2fc-130">Configurar a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-130">Set up event-based retention</span></span>

<span data-ttu-id="8d2fc-131">Esta seção descreve o que é necessário fazer antes da retenção do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="8d2fc-132">Identificar as funções</span><span class="sxs-lookup"><span data-stu-id="8d2fc-132">Identify roles</span></span>

<span data-ttu-id="8d2fc-133">Identificar as diferentes funções dentro de uma organização que executam as tarefas de Gerenciamento de Registros e que seriam responsáveis pela retenção eficaz e eficiente de documentos comerciais.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="8d2fc-134">Persona</span><span class="sxs-lookup"><span data-stu-id="8d2fc-134">Persona</span></span> | <span data-ttu-id="8d2fc-135">Função</span><span class="sxs-lookup"><span data-stu-id="8d2fc-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="8d2fc-136">Administrador</span><span class="sxs-lookup"><span data-stu-id="8d2fc-136">Admin</span></span> | <span data-ttu-id="8d2fc-137">Cria tipos de evento de retenção, rótulos de retenção e repositórios de registro no SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d2fc-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="8d2fc-138">Gerente de registros</span><span class="sxs-lookup"><span data-stu-id="8d2fc-138">Records Manager</span></span>                                  | <span data-ttu-id="8d2fc-139">Fornece políticas de retenção, diretrizes de agendamento de retenção e detalhes de conformidade</span><span class="sxs-lookup"><span data-stu-id="8d2fc-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="8d2fc-140">Administrador do sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="8d2fc-140">System Admin (business)</span></span>                          | <span data-ttu-id="8d2fc-141">Configura e gerencia sistemas externos para trabalhar com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d2fc-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="8d2fc-142">Operador de Informações</span><span class="sxs-lookup"><span data-stu-id="8d2fc-142">Information Worker</span></span>                               | <span data-ttu-id="8d2fc-143">Gerencia o ciclo de vida dos seus processos empresariais (RH, finanças, TI e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="8d2fc-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="8d2fc-144">Configurar o Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="8d2fc-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="8d2fc-145">O administrador de conformidade cria um tipo de evento &ndash;, por exemplo, Rescisão de Funcionário, Vencimento de Contrato ou Término de Fabricação de Produto.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="8d2fc-146">(confira o processo passo a passo na [ Retenção orientada por eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="8d2fc-147">O administrador de conformidade cria um rótulo de retenção com base em um evento e associa o rótulo a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="8d2fc-148">Há quatro tipos de fatores desencadeantes para rótulos de retenção:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="8d2fc-149">Data de criação</span><span class="sxs-lookup"><span data-stu-id="8d2fc-149">Create date</span></span>
                
    2. <span data-ttu-id="8d2fc-150">Última modificação</span><span class="sxs-lookup"><span data-stu-id="8d2fc-150">Last modified</span></span>
                
    3. <span data-ttu-id="8d2fc-151">Data do rótulo (quando o conteúdo foi rotulado)</span><span class="sxs-lookup"><span data-stu-id="8d2fc-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="8d2fc-152">Com base em eventos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-152">Event-based</span></span>
    
3. <span data-ttu-id="8d2fc-153">O administrador de conformidade publica o rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="8d2fc-154">Configurar o SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d2fc-154">Set up SharePoint</span></span>
   
<span data-ttu-id="8d2fc-155">Para criar um repositório de registros, o administrador de conformidade:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="8d2fc-156">Cria um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="8d2fc-157">Faz um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="8d2fc-158">Creates a SharePoint library: Set event-based label at the library level.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-158">Creates a SharePoint library: Set event-based label at the library level.</span></span> <span data-ttu-id="8d2fc-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="8d2fc-160">Faz a configuração de um conjunto de documentos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="8d2fc-161">Para saber mais, confira [Introdução a conjuntos de documentos](https://support.microsoft.com/pt-BR/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-161">For more information, see [Introduction to document sets](https://support.microsoft.com/pt-BR/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="8d2fc-162">Atribui uma ID de ativo ao conjunto de documentos de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="8d2fc-163">Uma ID do ativo é um nome do produto ou código do produto usado pela organização, por exemplo, o Número do funcionário pode ser uma ID do ativo.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="8d2fc-164">Ao atribuir a ID do ativo à pasta, todos os itens dessa pasta passar a ter automaticamente a mesma ID do ativo.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="8d2fc-165">Isso significa que todos os itens podem ter o período de retenção desencadeado pelo mesmo evento.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="8d2fc-166">Maneiras de disparar a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="8d2fc-167">Há duas maneiras pelas quais a retenção baseada em eventos pode ser disparada:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="8d2fc-168">**Usando a interface do usuário do centro de administração** Esse é um processo que pode ser usado para reter menos conteúdo de cada vez ou no caso de o gatilho que ativa a retenção não ser muito frequente (mensal ou anual, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="8d2fc-169">Para mais informações sobre esse método, confira a [Visão geral dos rótulos de retenção baseada em eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="8d2fc-170">No entanto, esse método de gatilho de retenção pode ser demorado e propenso a erros, desse modo inibindo escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="8d2fc-171">Portanto, uma solução automatizada e ordenada para acionar a retenção pode melhorar a segurança e a conformidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="8d2fc-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span></span> <span data-ttu-id="8d2fc-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span></span> <span data-ttu-id="8d2fc-174">You don't need to manually create an event in the UI each time one occurs.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-174">You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="8d2fc-175">Há duas opções de uso para a API REST:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="8d2fc-176">**O Microsoft Flow ou um aplicativo semelhante** pode ser usado para desencadear automaticamente a ocorrência de um evento.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="8d2fc-177">O Microsoft Flow é um orquestrador para a conexão com outros sistemas.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="8d2fc-178">Usar o Microsoft Flow não requer uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="8d2fc-179">**PowerShell ou um cliente HTTP para chamar a REST API** Usando o PowerShell (versão 6 ou superior) para chamar a API REST do Microsoft 365 para criar eventos.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="8d2fc-180">Uma API REST é um ponto de extremidade de serviço que oferece suporte a conjuntos de operações HTTP (métodos), que fornecem o acesso criar/recuperar/atualizar/deletar aos recursos do serviço.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="8d2fc-181">Para saber mais, confira [Componenente de uma solicitação/resposta do API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="8d2fc-182">Nesse caso, usando o Microsoft 365 REST API, eventos podem ser criados e recuperados usando operações (métodos) POST e GET.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="8d2fc-183">Exemplos de cenários</span><span class="sxs-lookup"><span data-stu-id="8d2fc-183">Example scenarios</span></span>

<span data-ttu-id="8d2fc-184">Vamos considerar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="8d2fc-185">Cenário 1: funcionários que deixam a organização</span><span class="sxs-lookup"><span data-stu-id="8d2fc-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="8d2fc-186">Uma organização cria e armazena vários documentos relativos ao contrato de trabalho para cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="8d2fc-187">Esses documentos são gerenciados e mantidos enquanto durar o vínculo de emprego de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="8d2fc-188">No entanto, quando o funcionário deixa a organização ou o contrato de trabalho chega ao fim, a organização é obrigada por requisitos legais e comerciais a guardar os documentos desse funcionário por um período estipulado.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="8d2fc-189">Agora, se vários funcionários deixarem a organização todos os dias, ela deverá disparar o tempo de retenção de centenas ou milhares de documentos por dia.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="8d2fc-190">Além disso, o período de retenção deve ser calculado para cada um desses funcionários, como a Data de rescisão + número de dias, meses ou anos, com base no tipo de registro do funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="8d2fc-191">Por exemplo, a remuneração versus os registros de benefícios desse funcionário pode precisar de uma retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="8d2fc-192">O diagrama abaixo mostra como pode haver diversos rótulos associados a um único evento.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="8d2fc-193">Aqui estão todos os arquivos sob o rótulo de Indenização do trabalhador e todos os arquivos sob o rótulo de Benefícios dos funcionários estão ambos associados a um único evento, que é o funcionário deixando a organização.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="8d2fc-194">Cada um desses arquivos tem diferentes relógios de retenção.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="8d2fc-195">Portanto, quando um funcionário deixa a organização, esses arquivos dentro de cada etiqueta têm um período de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="8d2fc-196">Disparar todos esses relógios diferentes para cada tipo de arquivo ou rótulo para cada funcionário é uma tarefa bastante desafiadora.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="8d2fc-197">Imagine fazer isso para vários funcionários.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-197">Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, eventos e rótulos](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="8d2fc-199">Portanto, um processo automatizado para acionar esses diferentes relógios de retenção para vários funcionários economizaria tempo, seria isento de erros e extremamente eficiente.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="8d2fc-200">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="8d2fc-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e ações para o cenário de saída do funcionário da organização](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="8d2fc-202">O administrador criar pastas de funcionários para o Conjunto de documentos, como Sara Melo, Diogo Martins.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="8d2fc-203">O administrador adiciona arquivos de funcionários, como Benefícios, Folha de pagamento e Seguro-doença, à pasta de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="8d2fc-204">O administrador atribui uma ID de ativo para a pasta de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="8d2fc-205">O administrador do CCS entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="8d2fc-206">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Rescisão de Funcionário" e "Contratação de Funcionário".</span><span class="sxs-lookup"><span data-stu-id="8d2fc-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="8d2fc-207">O administrador do Centro de Conformidade e Segurança cria o rótulo "Retenção de Funcionários".</span><span class="sxs-lookup"><span data-stu-id="8d2fc-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="8d2fc-208">O rótulo "Retenção de Funcionário" é publicado e aplicado de forma automática ou manual aos arquivos de funcionários no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="8d2fc-209">Um sistema de gerenciamento de RH, como o Workday, pode trabalhar com o Microsoft Flow para realizar periodicamente o gerenciamento de arquivos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="8d2fc-210">Quando um funcionário deixa a organização, o Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="8d2fc-211">Usando o Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="8d2fc-211">Using Microsoft Flow</span></span>

<span data-ttu-id="8d2fc-212">Etapa 1 – Criar um fluxo para criar um evento usando a API REST do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d2fc-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usando o Flow para criar um evento](../media/automate-event-driven-retention-flow-1.png)

![Usando um fluxo para chamar a API REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="8d2fc-215">Criar um evento</span><span class="sxs-lookup"><span data-stu-id="8d2fc-215">Create an event</span></span>

<span data-ttu-id="8d2fc-216">Exemplo de código para chamar a API REST</span><span class="sxs-lookup"><span data-stu-id="8d2fc-216">Sample code to call the REST API</span></span>

- <span data-ttu-id="8d2fc-217">**Método**: POSTAR</span><span class="sxs-lookup"><span data-stu-id="8d2fc-217">**Method**: POST</span></span>
- <span data-ttu-id="8d2fc-218">**URL**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="8d2fc-218">**URL**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</span></span>
- <span data-ttu-id="8d2fc-219">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d2fc-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="8d2fc-220">**Corpo**:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-220">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- <span data-ttu-id="8d2fc-221">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="8d2fc-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="8d2fc-222">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="8d2fc-223">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="8d2fc-224">Parâmetros disponíveis</span><span class="sxs-lookup"><span data-stu-id="8d2fc-224">Available parameters</span></span>


|<span data-ttu-id="8d2fc-225">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8d2fc-225">Parameters</span></span>|<span data-ttu-id="8d2fc-226">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d2fc-226">Description</span></span>|<span data-ttu-id="8d2fc-227">Observações</span><span class="sxs-lookup"><span data-stu-id="8d2fc-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="8d2fc-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="8d2fc-228"><d:Name></d:Name></span></span>|<span data-ttu-id="8d2fc-229">Fornece um nome exclusivo para o evento,</span><span class="sxs-lookup"><span data-stu-id="8d2fc-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="8d2fc-230">Não pode conter espaços à direita nem os seguintes caracteres: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="8d2fc-230">Cannot contain trailing spaces, and the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="8d2fc-231">, : ;</span><span class="sxs-lookup"><span data-stu-id="8d2fc-231">, : ;</span></span>|
|<span data-ttu-id="8d2fc-232"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="8d2fc-232"><d:EventType></d:EventType></span></span>|<span data-ttu-id="8d2fc-233">Insere o nome do tipo de evento (ou GUID).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-233">Enter event type name (or Guid),</span></span>|<span data-ttu-id="8d2fc-234">Example: “Employee termination”.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-234">Example: “Employee termination”.</span></span> <span data-ttu-id="8d2fc-235">Event type has to be associated with a retention label.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-235">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="8d2fc-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="8d2fc-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="8d2fc-237">Insere "ComplianceAssetId:"” + ID do funcionário.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-237">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="8d2fc-238">Example: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-238">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="8d2fc-239"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="8d2fc-239"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="8d2fc-240">Data e hora do evento</span><span class="sxs-lookup"><span data-stu-id="8d2fc-240">Event Date and Time</span></span>|<span data-ttu-id="8d2fc-241">Formato: yyyy-MM-ddTHH:mm:ssZ. Exemplo: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="8d2fc-241">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="8d2fc-242">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-242">Response codes</span></span>

| <span data-ttu-id="8d2fc-243">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-243">Response Code</span></span> | <span data-ttu-id="8d2fc-244">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d2fc-244">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="8d2fc-245">302</span><span class="sxs-lookup"><span data-stu-id="8d2fc-245">302</span></span>               | <span data-ttu-id="8d2fc-246">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="8d2fc-246">Redirect</span></span>              |
| <span data-ttu-id="8d2fc-247">201</span><span class="sxs-lookup"><span data-stu-id="8d2fc-247">201</span></span>               | <span data-ttu-id="8d2fc-248">Criado em</span><span class="sxs-lookup"><span data-stu-id="8d2fc-248">Created</span></span>               |
| <span data-ttu-id="8d2fc-249">403</span><span class="sxs-lookup"><span data-stu-id="8d2fc-249">403</span></span>               | <span data-ttu-id="8d2fc-250">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="8d2fc-250">Authorization Failed</span></span>  |
| <span data-ttu-id="8d2fc-251">401</span><span class="sxs-lookup"><span data-stu-id="8d2fc-251">401</span></span>               | <span data-ttu-id="8d2fc-252">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="8d2fc-252">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="8d2fc-253">Obter eventos com base em intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="8d2fc-253">Get Events based on time range</span></span>

- <span data-ttu-id="8d2fc-254">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="8d2fc-254">**Method**: GET</span></span>

- <span data-ttu-id="8d2fc-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="8d2fc-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="8d2fc-256">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d2fc-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d2fc-257">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="8d2fc-257">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d2fc-258">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-258">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d2fc-259">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-259">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="8d2fc-260">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-260">Response codes</span></span>

| <span data-ttu-id="8d2fc-261">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-261">Response Code</span></span> | <span data-ttu-id="8d2fc-262">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d2fc-262">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="8d2fc-263">200</span><span class="sxs-lookup"><span data-stu-id="8d2fc-263">200</span></span>               | <span data-ttu-id="8d2fc-264">OK. Uma lista de eventos em atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d2fc-264">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="8d2fc-265">404</span><span class="sxs-lookup"><span data-stu-id="8d2fc-265">404</span></span>               | <span data-ttu-id="8d2fc-266">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="8d2fc-266">Not found</span></span>                         |
| <span data-ttu-id="8d2fc-267">302</span><span class="sxs-lookup"><span data-stu-id="8d2fc-267">302</span></span>               | <span data-ttu-id="8d2fc-268">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="8d2fc-268">Redirect</span></span>                          |
| <span data-ttu-id="8d2fc-269">401</span><span class="sxs-lookup"><span data-stu-id="8d2fc-269">401</span></span>               | <span data-ttu-id="8d2fc-270">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="8d2fc-270">Authorization Failed</span></span>              |
| <span data-ttu-id="8d2fc-271">403</span><span class="sxs-lookup"><span data-stu-id="8d2fc-271">403</span></span>               | <span data-ttu-id="8d2fc-272">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="8d2fc-272">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="8d2fc-273">Obter um evento por ID</span><span class="sxs-lookup"><span data-stu-id="8d2fc-273">Get an event by ID</span></span>

- <span data-ttu-id="8d2fc-274">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="8d2fc-274">**Method**: GET</span></span>

- <span data-ttu-id="8d2fc-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="8d2fc-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="8d2fc-276">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d2fc-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d2fc-277">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="8d2fc-277">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d2fc-278">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-278">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d2fc-279">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-279">**Password**: "Compliancepassword"</span></span>



##### <a name="response-codes"></a><span data-ttu-id="8d2fc-280">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-280">Response codes</span></span>

| <span data-ttu-id="8d2fc-281">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-281">Response Code</span></span> | <span data-ttu-id="8d2fc-282">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d2fc-282">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="8d2fc-283">200</span><span class="sxs-lookup"><span data-stu-id="8d2fc-283">200</span></span>               | <span data-ttu-id="8d2fc-284">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-284">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="8d2fc-285">404</span><span class="sxs-lookup"><span data-stu-id="8d2fc-285">404</span></span>               | <span data-ttu-id="8d2fc-286">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="8d2fc-286">Not found</span></span>                                            |
| <span data-ttu-id="8d2fc-287">302</span><span class="sxs-lookup"><span data-stu-id="8d2fc-287">302</span></span>               | <span data-ttu-id="8d2fc-288">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="8d2fc-288">Redirect</span></span>                                             |
| <span data-ttu-id="8d2fc-289">401</span><span class="sxs-lookup"><span data-stu-id="8d2fc-289">401</span></span>               | <span data-ttu-id="8d2fc-290">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="8d2fc-290">Authorization Failed</span></span>                                 |
| <span data-ttu-id="8d2fc-291">403</span><span class="sxs-lookup"><span data-stu-id="8d2fc-291">403</span></span>               | <span data-ttu-id="8d2fc-292">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="8d2fc-292">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="8d2fc-293">Obter um evento por nome</span><span class="sxs-lookup"><span data-stu-id="8d2fc-293">Get an event by name</span></span>

- <span data-ttu-id="8d2fc-294">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="8d2fc-294">**Method**: GET</span></span>

- <span data-ttu-id="8d2fc-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="8d2fc-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="8d2fc-296">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d2fc-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d2fc-297">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="8d2fc-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d2fc-298">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d2fc-299">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="8d2fc-299">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="8d2fc-300">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-300">Response codes</span></span>

| <span data-ttu-id="8d2fc-301">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="8d2fc-301">Response Code</span></span> | <span data-ttu-id="8d2fc-302">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d2fc-302">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="8d2fc-303">200</span><span class="sxs-lookup"><span data-stu-id="8d2fc-303">200</span></span>               | <span data-ttu-id="8d2fc-304">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-304">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="8d2fc-305">404</span><span class="sxs-lookup"><span data-stu-id="8d2fc-305">404</span></span>               | <span data-ttu-id="8d2fc-306">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="8d2fc-306">Not found</span></span>                                            |
| <span data-ttu-id="8d2fc-307">302</span><span class="sxs-lookup"><span data-stu-id="8d2fc-307">302</span></span>               | <span data-ttu-id="8d2fc-308">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="8d2fc-308">Redirect</span></span>                                             |
| <span data-ttu-id="8d2fc-309">401</span><span class="sxs-lookup"><span data-stu-id="8d2fc-309">401</span></span>               | <span data-ttu-id="8d2fc-310">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="8d2fc-310">Authorization Failed</span></span>                                 |
| <span data-ttu-id="8d2fc-311">403</span><span class="sxs-lookup"><span data-stu-id="8d2fc-311">403</span></span>               | <span data-ttu-id="8d2fc-312">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="8d2fc-312">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="8d2fc-313">Usando o PowerShell (versão 6 ou posterior) ou um cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="8d2fc-313">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="8d2fc-314">Etapa 1 – Conectar-se ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-314">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="8d2fc-315">Etapa 2 – Executar o seguinte script.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-315">Step 2: Run the following script.</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="8d2fc-316">Verificar o resultado nas duas opções</span><span class="sxs-lookup"><span data-stu-id="8d2fc-316">Verify the outcome in both options</span></span>

<span data-ttu-id="8d2fc-317">Etapa 1: Vá para o Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-317">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="8d2fc-318">Etapa 2: Selecione **Eventos** em **Governança de informações**.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-318">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="8d2fc-319">Etapa 3 : Verifique se o Evento foi criado.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-319">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="8d2fc-320">Da mesma forma, as opções acima para automatizar a retenção baseada em eventos também podem ser usadas também para os cenários a seguir.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-320">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="8d2fc-321">Cenário 2 : Expiração de Contratos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-321">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="8d2fc-322">Uma organização pode fazer registros múltiplos para um único contrato com clientes, fornecedores e parceiros.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-322">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="8d2fc-323">Esse documentos podem ser colocados em uma biblioteca de documentos como o Sharepoint.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-323">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="8d2fc-324">O término de um contrato determina o início do período de retenção dos documentos associados àquele contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-324">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="8d2fc-325">Por exemplo, todos os registros relacionados a contratos precisam ser retidos por cinco anos contados da data em que o contrato expirou.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-325">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="8d2fc-326">O evento que desencadeia o período de retenção de cinco anos é a expiração do contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-326">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="8d2fc-327">Um sistema de CRM (Gerenciamento de Relacionamento com o cliente) pode trabalhar com o Microsoft 365 e desencadear a retenção de documentos do contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-327">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="8d2fc-328">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="8d2fc-328">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e tarefas para o cenário de expiração de contrato](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="8d2fc-330">O administrador cria uma biblioteca do SharePoint com várias pastas para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-330">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="8d2fc-331">O administrador adiciona arquivos de contrato, como Contratos de Licença e Contratos de Desenvolvimento, a cada pasta de contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-331">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="8d2fc-332">O administrador atribui uma ID de ativo à pasta de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-332">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="8d2fc-333">O administrador do CCS entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-333">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="8d2fc-334">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a contratos, como "Criação de Contrato" e "Expiração de Contrato".</span><span class="sxs-lookup"><span data-stu-id="8d2fc-334">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="8d2fc-335">O administrador do Centro de Conformidade e Segurança cria o rótulo "Expiração do Contrato".</span><span class="sxs-lookup"><span data-stu-id="8d2fc-335">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="8d2fc-336">O rótulo "Expiração de Contrato" é publicado e aplicado de forma automática ou manual aos arquivos de contratos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-336">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="8d2fc-337">O Sistema de Gerenciamento de Contratos pode trabalhar com o Microsoft Flow ou um aplicativo semelhante para realizar periodicamente o gerenciamento de arquivos de contratos.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-337">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="8d2fc-338">Quando um contrato expira, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do contrato.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-338">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="8d2fc-339">Cenário 3 – Término de fabricação de produto</span><span class="sxs-lookup"><span data-stu-id="8d2fc-339">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="8d2fc-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span></span> <span data-ttu-id="8d2fc-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="8d2fc-342">Um sistema de ERP (Planejamento de Recursos Empresariais) pode trabalhar com o Microsoft 365 e o Microsoft Flow para disparar a retenção.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-342">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="8d2fc-343">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="8d2fc-343">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e tarefas para o cenário de ciclo de vida do produto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="8d2fc-345">O administrador cria pastas de produtos no Conjunto de documentos, como Produto 1, Produto 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-345">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="8d2fc-346">O administrador adiciona arquivos de produto, como Especificações de Fabricação, Preços de Produto e Licenciamento de Produto, a cada pasta de produto.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-346">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="8d2fc-347">O administrador atribui uma ID de ativo à pasta de cada produto.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-347">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="8d2fc-348">O administrador do CCS entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-348">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="8d2fc-349">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Início de Fabricação de Produto" e "Término de Fabricação de Produto".</span><span class="sxs-lookup"><span data-stu-id="8d2fc-349">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="8d2fc-350">O administrador do Centro de Conformidade e Segurança cria o rótulo "Término de Fabricação de Produto".</span><span class="sxs-lookup"><span data-stu-id="8d2fc-350">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="8d2fc-351">O rótulo "Término de Fabricação de Produto" é publicado e aplicado de forma automática ou manual aos arquivos de produtos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-351">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="8d2fc-352">Os sistemas de ERP podem trabalhar com o Microsoft Flow ou com aplicativos semelhantes para realizar periodicamente o gerenciamento de arquivos de produtos.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-352">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="8d2fc-353">Quando a fabricação de um produto é encerrada, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do produto.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-353">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="8d2fc-354">Apêndice</span><span class="sxs-lookup"><span data-stu-id="8d2fc-354">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="8d2fc-355">Como usar resultados de resposta de Redirecionamento 302 para chamar a API REST</span><span class="sxs-lookup"><span data-stu-id="8d2fc-355">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="8d2fc-356">Invoque uma chamada de evento de retenção de POSTAGEM usando a URL da API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (é necessário ter permissões do administrador global).</span><span class="sxs-lookup"><span data-stu-id="8d2fc-356">Invoke a POST retention event call by using the REST API URL, <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required).</span></span>

2. <span data-ttu-id="8d2fc-357">Verifique o código de resposta.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-357">Check the response code.</span></span> <span data-ttu-id="8d2fc-358">Se for 302, obtenha a URL redirecionada da propriedade Local do cabeçalho da resposta.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-358">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="8d2fc-359">Invoque a chamada de evento de retenção POST usando a URL redirecionada.</span><span class="sxs-lookup"><span data-stu-id="8d2fc-359">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="8d2fc-360">Créditos</span><span class="sxs-lookup"><span data-stu-id="8d2fc-360">Credits</span></span>

<span data-ttu-id="8d2fc-361">Este tópico foi revisado por:</span><span class="sxs-lookup"><span data-stu-id="8d2fc-361">This topic was reviewed by:</span></span>

<span data-ttu-id="8d2fc-362">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="8d2fc-362">Antonio Maio</span></span><br/><span data-ttu-id="8d2fc-363">MVP de aplicativos e serviços do Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="8d2fc-363">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="8d2fc-364">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="8d2fc-364">Antonio.Maio@Protiviti.com</span></span>
