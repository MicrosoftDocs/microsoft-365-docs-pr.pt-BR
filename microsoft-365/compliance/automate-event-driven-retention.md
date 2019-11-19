---
title: Automatizar retenção orientada a eventos
ms.author: laurawi
author: laurawi
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
ms.openlocfilehash: 5977b79c47166fdafc76dfdb122b4fd37b63a875
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38708014"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="48477-103">Automatizar retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="48477-103">Automate event-based retention</span></span>

<span data-ttu-id="48477-p101">A massificação de conteúdo nas organizações e como ele pode se tornar ROT (redundante, obsoleto, trivial) é um negócio sério. Para continuar atendendo aos desafios legais, comerciais e de conformidade regulamentar, as empresas devem poder manter e proteger informações importantes, e encontrar rapidamente o conteúdo relevante. Para que uma empresa seja bem-sucedida, é fundamental que ela mantenha apenas informações importantes e pertinentes.</span><span class="sxs-lookup"><span data-stu-id="48477-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="48477-p102">Portanto, as organizações podem aproveitar as soluções de retenção no Centro de Conformidade e Segurança do Office 365. A retenção pode ser disparada por meio de [rótulos de retenção](labels.md). O rótulo de retenção tem a opção de [basear o período de retenção em um evento específico](event-driven-retention.md). Normalmente, o período de retenção se baseia em uma data conhecida, como a data de criação ou a data da última modificação do conteúdo. No entanto, as organizações também têm requisitos para descartar conteúdo com base na ocorrência de um evento, por exemplo, sete anos depois que um funcionário deixa a organização.</span><span class="sxs-lookup"><span data-stu-id="48477-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="48477-p103">Para garantir o descarte de conteúdo de acordo com as regras, é fundamental saber quando um evento ocorre. Com o volume de conteúdo aumentando rapidamente, fica cada vez mais difícil reter e descartá-lo em conformidade e de maneira oportuna.</span><span class="sxs-lookup"><span data-stu-id="48477-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="48477-p104">A retenção baseada em eventos resolve esse problema. Este tópico explica como configurar os fluxos dos processos empresariais para automatizar a retenção por meio de eventos usando a API REST do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48477-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="48477-116">Sobre a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="48477-116">About event-based retention</span></span>

<span data-ttu-id="48477-p105">Sejam de pequeno, médio ou grande porte, a quantidade de documentos comerciais e jurídicos, arquivos de funcionários, contratos e documentação de produtos que as empresas criam e gerenciam todos os dias está aumentando radicalmente.</span><span class="sxs-lookup"><span data-stu-id="48477-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="48477-p106">Por exemplo, todos os dias, dezenas ou centenas de funcionários entram e saem das organizações. O departamento de RH continua a criar, atualizar ou excluir documentos relacionados a funcionários de acordo com as exigências comerciais. Esse processo está sujeito às diferentes políticas de retenção descritas para o negócio:</span><span class="sxs-lookup"><span data-stu-id="48477-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="48477-p107">**O período de retenção do conteúdo pode ser uma data conhecida**, como a data da criação, a data da última modificação ou da rotulagem do conteúdo. Por exemplo, você pode reter documentos por sete anos depois de criados e excluí-los em seguida.</span><span class="sxs-lookup"><span data-stu-id="48477-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="48477-p108">**O período de retenção do conteúdo pode ser uma data desconhecida**. Por exemplo, com os rótulos de retenção, é possível basear o período de retenção na ocasião em que ocorre um tipo específico de evento, como a data em que um funcionário sai da empresa.</span><span class="sxs-lookup"><span data-stu-id="48477-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="48477-p109">O evento dispara o início do período de retenção, e todo o conteúdo com um rótulo aplicado para esse tipo de evento faz com que as ações de retenção do rótulo sejam aplicadas a ele. Isso se chama retenção baseada em eventos. Para saber mais, confira [Visão geral da retenção orientada a eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="48477-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="48477-128">Configurar a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="48477-128">Set up event-based retention</span></span>

<span data-ttu-id="48477-129">Esta seção descreve o que precisa ser feito antes da retenção do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="48477-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="48477-130">Identificar as funções</span><span class="sxs-lookup"><span data-stu-id="48477-130">Identify roles</span></span>

<span data-ttu-id="48477-131">Identifique as diferentes funções de uma organização que executam as tarefas de Gerenciamento de Registros que seriam responsáveis pela retenção eficaz e eficiente de documentos comerciais.</span><span class="sxs-lookup"><span data-stu-id="48477-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="48477-132">**Pessoal**</span><span class="sxs-lookup"><span data-stu-id="48477-132">**Persona**</span></span>| <span data-ttu-id="48477-133">**Função**</span><span class="sxs-lookup"><span data-stu-id="48477-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="48477-134">Administrador</span><span class="sxs-lookup"><span data-stu-id="48477-134">Admin</span></span> | <span data-ttu-id="48477-135">Cria tipos de evento de retenção, rótulos de retenção e repositórios de registro no SharePoint</span><span class="sxs-lookup"><span data-stu-id="48477-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="48477-136">Gerente de registros</span><span class="sxs-lookup"><span data-stu-id="48477-136">Records Manager</span></span>                                  | <span data-ttu-id="48477-137">Fornece políticas de retenção, diretrizes de agendamento de retenção e detalhes de conformidade</span><span class="sxs-lookup"><span data-stu-id="48477-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="48477-138">Administrador do sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="48477-138">System Admin (business)</span></span>                          | <span data-ttu-id="48477-139">Configura e gerencia sistemas externos para trabalhar com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48477-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="48477-140">Operador de Informações</span><span class="sxs-lookup"><span data-stu-id="48477-140">Information Worker</span></span>                               | <span data-ttu-id="48477-141">Gerencia o ciclo de vida dos processos empresariais (RH, finanças, TI, etc.)</span><span class="sxs-lookup"><span data-stu-id="48477-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="48477-142">Configurar o Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="48477-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="48477-143">O administrador de conformidade cria um tipo de evento. Por exemplo, rescisão de funcionário, vencimento de contrato ou término de fabricação de produto (confira o processo passo a passo na [retenção orientada por eventos](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="48477-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
1. <span data-ttu-id="48477-144">O administrador de conformidade cria um rótulo de retenção com base em um evento e associa o rótulo a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="48477-144">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
1. <span data-ttu-id="48477-145">Há quatro tipos de disparadores para rótulos de retenção:</span><span class="sxs-lookup"><span data-stu-id="48477-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="48477-146">Data de criação</span><span class="sxs-lookup"><span data-stu-id="48477-146">Create date</span></span>
                
    1. <span data-ttu-id="48477-147">Última modificação</span><span class="sxs-lookup"><span data-stu-id="48477-147">Last modified</span></span>
                
    1. <span data-ttu-id="48477-148">Data do rótulo (quando o conteúdo foi rotulado)</span><span class="sxs-lookup"><span data-stu-id="48477-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="48477-149">Com base em eventos</span><span class="sxs-lookup"><span data-stu-id="48477-149">Event-based</span></span>
    
1. <span data-ttu-id="48477-150">O administrador de conformidade publica o rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="48477-150">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="48477-151">Configurar o SharePoint</span><span class="sxs-lookup"><span data-stu-id="48477-151">Set up SharePoint</span></span>
   
<span data-ttu-id="48477-152">Para criar um repositório de registros, o administrador de conformidade:</span><span class="sxs-lookup"><span data-stu-id="48477-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="48477-153">Cria um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48477-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="48477-154">Faz um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="48477-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="48477-p110">Cria uma biblioteca do SharePoint: ele define um rótulo baseado em eventos no nível da biblioteca. Para saber mais, confira [Como aplicar um rótulo de retenção padrão a todo o conteúdo de uma biblioteca, pasta ou de um conjunto de documentos do SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="48477-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="48477-p111">Configura um conjunto de documentos no SharePoint. Para saber mais, confira [Introdução a conjuntos de documentos](https://support.office.com/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="48477-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="48477-p112">Atribui uma ID de ativo (a ID de ativo é um nome de produto ou código usado pela organização, por exemplo, um número de funcionário) a cada conjunto de documentos de funcionários. Ao atribuir a ID de ativo à pasta, todos os itens dessa pasta herdam automaticamente a mesma ID. Isso significa que todos os itens podem ter o período de retenção disparado pelo mesmo evento.</span><span class="sxs-lookup"><span data-stu-id="48477-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="48477-161">Maneiras de disparar a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="48477-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="48477-162">Há duas maneiras pelas quais a retenção baseada em eventos pode ser disparada:</span><span class="sxs-lookup"><span data-stu-id="48477-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="48477-p113">**Usando a IU do centro de administração** Esse processo que pode ser usado para reter menos conteúdo por vez ou para reduzir a frequência de disparo da retenção, como mensal ou anual. Para saber mais sobre este método, confira [Visão geral da retenção orientada a eventos](event-driven-retention.md). No entanto, essa maneira de disparar a retenção pode ser demorada e passível de erros, retardando a escalabilidade. Portanto, uma solução automatizada e perfeita para acionar a retenção pode aumentar a segurança e a conformidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="48477-p113">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="48477-p114">**Usando uma API REST do Microsoft 365** Esse processo pode ser usado quando grandes quantidades de conteúdo devem ser retidas por vez e/ou quando a frequência de disparo da retenção for mais frequente, como diária ou semanal. O fluxo detecta quando um evento ocorre no sistema de linha de negócios e cria automaticamente um evento relacionado no Centro de Conformidade e Segurança. Não é necessário criar manualmente um evento na interface do usuário sempre que ocorrer um.</span><span class="sxs-lookup"><span data-stu-id="48477-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="48477-170">Há duas opções de uso para a API REST:</span><span class="sxs-lookup"><span data-stu-id="48477-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="48477-p115">**O Microsoft Flow ou um aplicativo semelhante** pode ser usado para disparar automaticamente a ocorrência de um evento. O Microsoft Flow é um orquestrador de conexão com outros sistemas. O uso deste aplicativo não exige uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="48477-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="48477-174">**PowerShell ou um cliente HTTP para chamar a REST API** Usando o PowerShell (versão 6 ou superior) para chamar a API REST do Microsoft 365 para criar eventos.</span><span class="sxs-lookup"><span data-stu-id="48477-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="48477-p116">Uma API REST é um ponto de extremidade de serviço com suporte para conjuntos de operações HTTP (métodos), que fornecem acesso para criação/recuperação/atualização/exclusão aos recursos do serviço. Para saber mais, confira [Componentes de uma solicitação/resposta da API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). Nesse caso, é possível criar e recuperar eventos usando operações (métodos) POST e GET com a API REST do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48477-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="48477-177">Exemplos de cenários</span><span class="sxs-lookup"><span data-stu-id="48477-177">Example scenarios</span></span>

<span data-ttu-id="48477-178">Vamos considerar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="48477-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="48477-179">Cenário 1: funcionários que deixam a organização</span><span class="sxs-lookup"><span data-stu-id="48477-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="48477-p117">Uma organização cria e armazena vários documentos relacionados a funcionários para cada funcionário. Esses documentos são gerenciados e retidos durante a vigência do contrato de cada funcionário. No entanto, quando o funcionário deixa a organização ou o contrato dele é rescindido, a organização é obrigada por exigências legais e comerciais a reter os documentos desse funcionário por um determinado período.</span><span class="sxs-lookup"><span data-stu-id="48477-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="48477-183">Agora, se vários funcionários deixarem a organização todos os dias, ela deverá disparar o tempo de retenção de centenas ou milhares de documentos por dia.</span><span class="sxs-lookup"><span data-stu-id="48477-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="48477-p118">Além disso, o período de retenção deve ser calculado para cada um desses funcionários, como a data de rescisão + número de dias, meses ou anos, com base no tipo de registro do funcionário. Por exemplo, a remuneração versus os registros de benefícios desse funcionário pode precisar de uma retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="48477-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="48477-p119">O diagrama abaixo mostra como pode haver vários rótulos associados a um único evento. Aqui, todos os arquivos com rótulo de "remuneração do funcionário" e todos os arquivos com rótulo de "benefícios do funcionário" estão associados a um único evento, representado pelo funcionário que deixa a organização. Cada um desses diferentes arquivos tem diferentes relógios de retenção. Assim, quando um funcionário deixa a organização, esses arquivos, no âmbito de cada rótulo, passam por um período de retenção diferente. Disparar todos esses relógios de retenção diferentes para cada tipo de arquivo ou rótulo para cada funcionário é uma tarefa extremamente complexa. Imagine fazer isso para vários funcionários.</span><span class="sxs-lookup"><span data-stu-id="48477-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, eventos e rótulos](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="48477-193">Portanto, um processo automatizado para disparar esses diferentes relógios de retenção para vários funcionários economizará tempo, será isento de erros e extremamente eficiente.</span><span class="sxs-lookup"><span data-stu-id="48477-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="48477-194">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="48477-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e ações para o cenário de saída do funcionário da organização](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="48477-196">O administrador criar pastas de funcionários para o conjunto de documentos, como Sara Melo, Diogo Martins.</span><span class="sxs-lookup"><span data-stu-id="48477-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="48477-197">O administrador adiciona arquivos de funcionários, como Benefícios, Folha de pagamento e Remuneração, à pasta de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="48477-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="48477-198">O administrador atribui uma ID de ativo à pasta de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="48477-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="48477-199">Administrador do Centro de Conformidade e Segurança I</span><span class="sxs-lookup"><span data-stu-id="48477-199">SCC Admin l</span></span>

  - <span data-ttu-id="48477-200">Entra no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="48477-200">Logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="48477-201">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Rescisão de funcionário" e "Contratação de funcionário".</span><span class="sxs-lookup"><span data-stu-id="48477-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="48477-202">O administrador do Centro de Conformidade e Segurança cria o rótulo "Retenção de funcionários".</span><span class="sxs-lookup"><span data-stu-id="48477-202">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="48477-203">O rótulo "Retenção de funcionário" é publicado e aplicado de forma automática ou manual aos arquivos de funcionários no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48477-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="48477-204">Um sistema de gerenciamento de RH, como o Workday, pode trabalhar com o Microsoft Flow para executar periodicamente o gerenciamento de arquivos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="48477-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="48477-205">Quando um funcionário deixa a organização, o Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do funcionário.</span><span class="sxs-lookup"><span data-stu-id="48477-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="48477-206">Usando o Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="48477-206">Using Microsoft Flow</span></span>

<span data-ttu-id="48477-207">Etapa 1 – Criar um fluxo para criar um evento usando a API REST do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48477-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usando o Flow para criar um evento](media/automate-event-driven-retention-flow-1.png)

![Usando um fluxo para chamar a API REST](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="48477-210">Criar um evento</span><span class="sxs-lookup"><span data-stu-id="48477-210">Create an event</span></span>

<span data-ttu-id="48477-211">Exemplo de código para chamar a API REST</span><span class="sxs-lookup"><span data-stu-id="48477-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="48477-212">Método</span><span class="sxs-lookup"><span data-stu-id="48477-212">Method</span></span></th>
<th><span data-ttu-id="48477-213">POST</span><span class="sxs-lookup"><span data-stu-id="48477-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="48477-214">URL</span><span class="sxs-lookup"><span data-stu-id="48477-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-215">Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="48477-215">Headers</span></span></td>
<td><span data-ttu-id="48477-216">Content-Type</span><span class="sxs-lookup"><span data-stu-id="48477-216">Content-Type</span></span></td>
<td><span data-ttu-id="48477-217">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="48477-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48477-218">Corpo</span><span class="sxs-lookup"><span data-stu-id="48477-218">Body</span></span></td>
<td><p><span data-ttu-id="48477-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="48477-220">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="48477-220">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="48477-221">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="48477-221">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="48477-222">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-222">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="48477-223">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-223">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="48477-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="48477-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="48477-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="48477-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="48477-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="48477-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="48477-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="48477-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="48477-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="48477-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-234">Autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-234">Authentication</span></span></td>
<td><span data-ttu-id="48477-235">Básica</span><span class="sxs-lookup"><span data-stu-id="48477-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48477-236">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="48477-236">Username</span></span></td>
<td><span data-ttu-id="48477-237">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-238">Senha</span><span class="sxs-lookup"><span data-stu-id="48477-238">Password</span></span></td>
<td><span data-ttu-id="48477-239">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="48477-240">Parâmetros disponíveis</span><span class="sxs-lookup"><span data-stu-id="48477-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="48477-241"><strong>Parâmetros</strong></span><span class="sxs-lookup"><span data-stu-id="48477-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="48477-242"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="48477-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="48477-243"><strong>Anotações</strong></span><span class="sxs-lookup"><span data-stu-id="48477-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="48477-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="48477-245">Fornece um nome exclusivo para o evento.</span><span class="sxs-lookup"><span data-stu-id="48477-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="48477-p120">Não pode conter espaços à direita nem os seguintes caracteres: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="48477-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="48477-249">Insere o nome do tipo de evento (ou GUID).</span><span class="sxs-lookup"><span data-stu-id="48477-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="48477-p121">Exemplo: "Rescisão de funcionário". O Tipo de evento deve estar associado a um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="48477-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48477-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="48477-253">Insere "ComplianceAssetId:"” + ID do funcionário.</span><span class="sxs-lookup"><span data-stu-id="48477-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="48477-254">Exemplo: &quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="48477-256">Data e hora do evento</span><span class="sxs-lookup"><span data-stu-id="48477-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="48477-257">Formato: yyyy-MM-ddTHH:mm:ssZ. Exemplo:</span><span class="sxs-lookup"><span data-stu-id="48477-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="48477-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="48477-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="48477-259">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="48477-259">Response codes</span></span>

| <span data-ttu-id="48477-260">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="48477-260">**Response Code**</span></span> | <span data-ttu-id="48477-261">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="48477-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="48477-262">302</span><span class="sxs-lookup"><span data-stu-id="48477-262">302</span></span>               | <span data-ttu-id="48477-263">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="48477-263">Redirect</span></span>              |
| <span data-ttu-id="48477-264">201</span><span class="sxs-lookup"><span data-stu-id="48477-264">201</span></span>               | <span data-ttu-id="48477-265">Criado em</span><span class="sxs-lookup"><span data-stu-id="48477-265">Created</span></span>               |
| <span data-ttu-id="48477-266">403</span><span class="sxs-lookup"><span data-stu-id="48477-266">403</span></span>               | <span data-ttu-id="48477-267">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="48477-267">Authorization Failed</span></span>  |
| <span data-ttu-id="48477-268">401</span><span class="sxs-lookup"><span data-stu-id="48477-268">401</span></span>               | <span data-ttu-id="48477-269">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="48477-270">Obter eventos com base em intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="48477-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="48477-271">Método</span><span class="sxs-lookup"><span data-stu-id="48477-271">Method</span></span></th>
<th><span data-ttu-id="48477-272">GET</span><span class="sxs-lookup"><span data-stu-id="48477-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="48477-273">URL</span><span class="sxs-lookup"><span data-stu-id="48477-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="48477-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="48477-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-275">Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="48477-275">Headers</span></span></td>
<td><span data-ttu-id="48477-276">Content-Type</span><span class="sxs-lookup"><span data-stu-id="48477-276">Content-Type</span></span></td>
<td><span data-ttu-id="48477-277">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="48477-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-278">Autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-278">Authentication</span></span></td>
<td><span data-ttu-id="48477-279">Básica</span><span class="sxs-lookup"><span data-stu-id="48477-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48477-280">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="48477-280">Username</span></span></td>
<td><span data-ttu-id="48477-281">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48477-282">Senha</span><span class="sxs-lookup"><span data-stu-id="48477-282">Password</span></span></td>
<td><span data-ttu-id="48477-283">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="48477-284">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="48477-284">Response codes</span></span>

| <span data-ttu-id="48477-285">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="48477-285">**Response Code**</span></span> | <span data-ttu-id="48477-286">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="48477-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="48477-287">200</span><span class="sxs-lookup"><span data-stu-id="48477-287">200</span></span>               | <span data-ttu-id="48477-288">OK. Uma lista de eventos em atom+xml</span><span class="sxs-lookup"><span data-stu-id="48477-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="48477-289">404</span><span class="sxs-lookup"><span data-stu-id="48477-289">404</span></span>               | <span data-ttu-id="48477-290">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="48477-290">Not found</span></span>                         |
| <span data-ttu-id="48477-291">302</span><span class="sxs-lookup"><span data-stu-id="48477-291">302</span></span>               | <span data-ttu-id="48477-292">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="48477-292">Redirect</span></span>                          |
| <span data-ttu-id="48477-293">401</span><span class="sxs-lookup"><span data-stu-id="48477-293">401</span></span>               | <span data-ttu-id="48477-294">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="48477-294">Authorization Failed</span></span>              |
| <span data-ttu-id="48477-295">403</span><span class="sxs-lookup"><span data-stu-id="48477-295">403</span></span>               | <span data-ttu-id="48477-296">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="48477-297">Obter um evento por ID</span><span class="sxs-lookup"><span data-stu-id="48477-297">Get an event by ID</span></span>

| <span data-ttu-id="48477-298">Método</span><span class="sxs-lookup"><span data-stu-id="48477-298">Method</span></span>         | <span data-ttu-id="48477-299">GET</span><span class="sxs-lookup"><span data-stu-id="48477-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="48477-300">URL</span><span class="sxs-lookup"><span data-stu-id="48477-300">URL</span></span>            | <span data-ttu-id="48477-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="48477-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="48477-302">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="48477-302">Header</span></span>         | <span data-ttu-id="48477-303">Content-Type</span><span class="sxs-lookup"><span data-stu-id="48477-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="48477-304">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="48477-304">application/atom+xml</span></span> |
| <span data-ttu-id="48477-305">Autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-305">Authentication</span></span> | <span data-ttu-id="48477-306">Básica</span><span class="sxs-lookup"><span data-stu-id="48477-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="48477-307">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="48477-307">Username</span></span>       | <span data-ttu-id="48477-308">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="48477-309">Senha</span><span class="sxs-lookup"><span data-stu-id="48477-309">Password</span></span>       | <span data-ttu-id="48477-310">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="48477-311">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="48477-311">Response codes</span></span>

| <span data-ttu-id="48477-312">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="48477-312">**Response Code**</span></span> | <span data-ttu-id="48477-313">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="48477-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="48477-314">200</span><span class="sxs-lookup"><span data-stu-id="48477-314">200</span></span>               | <span data-ttu-id="48477-315">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="48477-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="48477-316">404</span><span class="sxs-lookup"><span data-stu-id="48477-316">404</span></span>               | <span data-ttu-id="48477-317">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="48477-317">Not found</span></span>                                            |
| <span data-ttu-id="48477-318">302</span><span class="sxs-lookup"><span data-stu-id="48477-318">302</span></span>               | <span data-ttu-id="48477-319">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="48477-319">Redirect</span></span>                                             |
| <span data-ttu-id="48477-320">401</span><span class="sxs-lookup"><span data-stu-id="48477-320">401</span></span>               | <span data-ttu-id="48477-321">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="48477-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="48477-322">403</span><span class="sxs-lookup"><span data-stu-id="48477-322">403</span></span>               | <span data-ttu-id="48477-323">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="48477-324">Obter um evento por nome</span><span class="sxs-lookup"><span data-stu-id="48477-324">Get an event by name</span></span>

| <span data-ttu-id="48477-325">Método</span><span class="sxs-lookup"><span data-stu-id="48477-325">Method</span></span>         | <span data-ttu-id="48477-326">GET</span><span class="sxs-lookup"><span data-stu-id="48477-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="48477-327">URL</span><span class="sxs-lookup"><span data-stu-id="48477-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="48477-328">Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="48477-328">Headers</span></span>        | <span data-ttu-id="48477-329">Content-Type</span><span class="sxs-lookup"><span data-stu-id="48477-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="48477-330">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="48477-330">application/atom+xml</span></span> |
| <span data-ttu-id="48477-331">Autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-331">Authentication</span></span> | <span data-ttu-id="48477-332">Básica</span><span class="sxs-lookup"><span data-stu-id="48477-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="48477-333">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="48477-333">Username</span></span>       | <span data-ttu-id="48477-334">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="48477-335">Senha</span><span class="sxs-lookup"><span data-stu-id="48477-335">Password</span></span>       | <span data-ttu-id="48477-336">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="48477-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="48477-337">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="48477-337">Response codes</span></span>

| <span data-ttu-id="48477-338">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="48477-338">**Response Code**</span></span> | <span data-ttu-id="48477-339">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="48477-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="48477-340">200</span><span class="sxs-lookup"><span data-stu-id="48477-340">200</span></span>               | <span data-ttu-id="48477-341">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="48477-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="48477-342">404</span><span class="sxs-lookup"><span data-stu-id="48477-342">404</span></span>               | <span data-ttu-id="48477-343">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="48477-343">Not found</span></span>                                            |
| <span data-ttu-id="48477-344">302</span><span class="sxs-lookup"><span data-stu-id="48477-344">302</span></span>               | <span data-ttu-id="48477-345">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="48477-345">Redirect</span></span>                                             |
| <span data-ttu-id="48477-346">401</span><span class="sxs-lookup"><span data-stu-id="48477-346">401</span></span>               | <span data-ttu-id="48477-347">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="48477-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="48477-348">403</span><span class="sxs-lookup"><span data-stu-id="48477-348">403</span></span>               | <span data-ttu-id="48477-349">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="48477-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="48477-350">Usando o PowerShell (versão 6 ou posterior) ou um cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="48477-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="48477-351">Etapa 1 – Conectar-se ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48477-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="48477-352">Etapa 2 – Executar o seguinte script.</span><span class="sxs-lookup"><span data-stu-id="48477-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48477-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="48477-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="48477-354">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="48477-355">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="48477-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="48477-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="48477-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="48477-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="48477-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="48477-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="48477-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="48477-361">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="48477-361">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="48477-362">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="48477-362">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="48477-363">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-363">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="48477-364">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-364">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="48477-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="48477-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="48477-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="48477-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="48477-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="48477-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="48477-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="48477-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="48477-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="48477-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="48477-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="48477-374">$event = $null</span></span></p>
<p><span data-ttu-id="48477-375">try</span><span class="sxs-lookup"><span data-stu-id="48477-375">try</span></span></p>
<p><span data-ttu-id="48477-376">{</span><span class="sxs-lookup"><span data-stu-id="48477-376">{</span></span></p>
<p><span data-ttu-id="48477-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="48477-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="48477-378">}</span><span class="sxs-lookup"><span data-stu-id="48477-378">}</span></span></p>
<p><span data-ttu-id="48477-379">catch</span><span class="sxs-lookup"><span data-stu-id="48477-379">catch</span></span></p>
<p><span data-ttu-id="48477-380">{</span><span class="sxs-lookup"><span data-stu-id="48477-380">{</span></span></p>
<p><span data-ttu-id="48477-381">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="48477-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="48477-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="48477-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="48477-383">{</span><span class="sxs-lookup"><span data-stu-id="48477-383">{</span></span></p>
<p><span data-ttu-id="48477-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="48477-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="48477-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="48477-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="48477-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="48477-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="48477-387">}</span><span class="sxs-lookup"><span data-stu-id="48477-387">}</span></span></p>
<p><span data-ttu-id="48477-388">}</span><span class="sxs-lookup"><span data-stu-id="48477-388">}</span></span></p>
<p><span data-ttu-id="48477-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="48477-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="48477-390">Verificar o resultado nas duas opções</span><span class="sxs-lookup"><span data-stu-id="48477-390">Verify the outcome in both options</span></span>

<span data-ttu-id="48477-391">Etapa 1 – Ir para o Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="48477-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="48477-392">Etapa 2 – Clicar em Eventos, em Governança de dados.</span><span class="sxs-lookup"><span data-stu-id="48477-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="48477-393">Etapa 3 – Verificar se o evento foi criado.</span><span class="sxs-lookup"><span data-stu-id="48477-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="48477-394">Da mesma forma, as opções acima para automatizar a retenção baseada em eventos também podem ser usadas para os cenários a seguir.</span><span class="sxs-lookup"><span data-stu-id="48477-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="48477-395">Cenário 2 – Expiração de contratos</span><span class="sxs-lookup"><span data-stu-id="48477-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="48477-p122">Uma organização pode ter vários registros para um único contrato com clientes, fornecedores e parceiros. Esses documentos podem residir em uma biblioteca de documentos, como o SharePoint. O término de um contrato determina o início do período de retenção dos documentos associados a esse contrato. Por exemplo: todos os registros relacionados a contratos devem ser retidos por cinco anos, a partir do momento em que o contrato expira. O evento que dispara o período de retenção de cinco anos é o término do contrato.</span><span class="sxs-lookup"><span data-stu-id="48477-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="48477-401">Um sistema de CRM (gerenciamento de relacionamento com o cliente) pode trabalhar com o Microsoft 365 e disparar a retenção de documentos do contrato.</span><span class="sxs-lookup"><span data-stu-id="48477-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="48477-402">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="48477-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e tarefas para o cenário de expiração de contrato](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="48477-404">O administrador cria uma biblioteca do SharePoint com várias pastas para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="48477-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="48477-405">O administrador adiciona arquivos de contrato, como Contratos de licença e Contratos de desenvolvimento, a cada pasta de contrato.</span><span class="sxs-lookup"><span data-stu-id="48477-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="48477-406">O administrador atribui uma ID de ativo à pasta de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="48477-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="48477-407">O administrador entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="48477-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="48477-408">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a contratos, como "Criação de contrato" e "Expiração de contrato".</span><span class="sxs-lookup"><span data-stu-id="48477-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="48477-409">O administrador do Centro de Conformidade e Segurança cria o rótulo "Expiração do contrato".</span><span class="sxs-lookup"><span data-stu-id="48477-409">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="48477-410">O rótulo "Expiração de contrato" é publicado e aplicado de forma automática ou manual aos arquivos de contratos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48477-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="48477-411">O sistema de gerenciamento de contratos pode trabalhar com o Microsoft Flow ou um aplicativo semelhante para executar periodicamente o gerenciamento de arquivos de contratos.</span><span class="sxs-lookup"><span data-stu-id="48477-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="48477-412">Quando um contrato expira, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do contrato.</span><span class="sxs-lookup"><span data-stu-id="48477-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="48477-413">Cenário 3 – Término de fabricação de produto</span><span class="sxs-lookup"><span data-stu-id="48477-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="48477-p123">Uma empresa que fabrica diferentes linhas de produtos cria muitas especificações de fabricação e documentos de precificação. Quando o produto deixa de ser fabricado, todas as especificações e os documentos vinculados a esse produto devem ser retidos por um período específico, após o término da vida útil do produto.</span><span class="sxs-lookup"><span data-stu-id="48477-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="48477-416">Um sistema de ERP (Planejamento de Recursos Empresariais) pode trabalhar com o Microsoft 365 e o Microsoft Flow para disparar a retenção.</span><span class="sxs-lookup"><span data-stu-id="48477-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="48477-417">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="48477-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e tarefas para o cenário de ciclo de vida do produto](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="48477-419">O administrador cria pastas de produtos no conjunto de documentos, como Produto 1, Produto 2, etc.</span><span class="sxs-lookup"><span data-stu-id="48477-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="48477-420">O administrador adiciona arquivos de produto, como Especificações de fabricação, Preços de produto e Licenciamento de produto, a cada pasta de produto.</span><span class="sxs-lookup"><span data-stu-id="48477-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="48477-421">O administrador atribui uma ID de ativo à pasta de cada produto.</span><span class="sxs-lookup"><span data-stu-id="48477-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="48477-422">O administrador entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="48477-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="48477-423">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a produtos, como "Início de fabricação de produto" e "Término de fabricação de produto".</span><span class="sxs-lookup"><span data-stu-id="48477-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="48477-424">O administrador do Centro de Conformidade e Segurança cria o rótulo "Término de fabricação de produto".</span><span class="sxs-lookup"><span data-stu-id="48477-424">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="48477-425">O rótulo "Término de fabricação de produto" é publicado e aplicado de forma automática ou manual aos arquivos de produtos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48477-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="48477-426">Os sistemas de ERP podem trabalhar com o Microsoft Flow ou com aplicativos semelhantes para executar periodicamente o gerenciamento de arquivos de produtos.</span><span class="sxs-lookup"><span data-stu-id="48477-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="48477-427">Quando a fabricação de um produto é encerrada, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do produto.</span><span class="sxs-lookup"><span data-stu-id="48477-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="48477-428">Apêndice</span><span class="sxs-lookup"><span data-stu-id="48477-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="48477-429">Como usar resultados de resposta de Redirecionamento 302 para chamar a API REST</span><span class="sxs-lookup"><span data-stu-id="48477-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="48477-430">Invoque uma chamada de evento de retenção POST usando a URL da API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (é necessário ter permissões de administrador global).</span><span class="sxs-lookup"><span data-stu-id="48477-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="48477-p124">Verifique o código da resposta. Se for 302, obtenha a URL redirecionada da propriedade Location do cabeçalho da resposta.</span><span class="sxs-lookup"><span data-stu-id="48477-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="48477-433">Invoque a chamada de evento de retenção POST usando a URL redirecionada.</span><span class="sxs-lookup"><span data-stu-id="48477-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="48477-434">Créditos</span><span class="sxs-lookup"><span data-stu-id="48477-434">Credits</span></span>

<span data-ttu-id="48477-435">Este tópico foi revisado por:</span><span class="sxs-lookup"><span data-stu-id="48477-435">This topic was reviewed by:</span></span>

<span data-ttu-id="48477-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="48477-436">Antonio Maio</span></span><br/><span data-ttu-id="48477-437">MVP de aplicativos e serviços do Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="48477-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="48477-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="48477-438">Antonio.Maio@Protiviti.com</span></span>
