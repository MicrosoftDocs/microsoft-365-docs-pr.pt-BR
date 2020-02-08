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
ms.openlocfilehash: 46276e1a40df8c5491d569337a683666984be23a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596318"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="31f5e-103">Automatizar retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="31f5e-103">Automate event-based retention</span></span>

<span data-ttu-id="31f5e-p101">O dramático aumento no volume de conteúdo nas organizações e como ele pode se tornar ROT (redundante, obsoleto, trivial) é um negócio sério. Para continuar encarando de frente os desafios legais, comerciais e de conformidade regulamentar, as empresas devem ser capaz de proteger informações importantes, e identificar rapidamente o que é relevante. Para que uma empresa seja bem-sucedida, é fundamental que ela retenha apenas informações importantes e pertinentes.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="31f5e-p102">Para atender à essa necessidade, as organizações podem aproveitar as soluções de retenção no Centro de Conformidade e Segurança do Office 365. A retenção pode ser ativada pelo uso de [rótulos de retenção](labels.md). O rótulo de retenção tem a opção de [basear o período de retenção em um evento específico](event-driven-retention.md). Normalmente, o período de retenção se baseia em uma data conhecida, como a data de criação ou a data da última modificação do conteúdo. No entanto, as organizações também têm requisitos para descartar conteúdo com base na ocorrência de um evento, por exemplo, sete anos depois que um funcionário deixa a organização.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="31f5e-p103">Para garantir o conteúdo seja descartado de acordo com as regras, é fundamental saber quando um evento ocorre. Com o volume de conteúdo aumentando rapidamente, fica cada vez mais difícil retê-lo e descartá-lo em conformidade e de maneira oportuna.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="31f5e-p104">A retenção baseada em eventos resolve esse problema. Este tópico explica como configurar os fluxos dos processos empresariais para automatizar a retenção por meio de eventos usando a API REST do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="31f5e-116">Sobre a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="31f5e-116">About event-based retention</span></span>

<span data-ttu-id="31f5e-p105">Sejam as organizações de pequeno, médio ou grande porte, a quantidade de documentos comerciais e jurídicos, arquivos de funcionários, contratos e documentação de produtos que se cria e se gerencia todos os dias está aumentando radicalmente.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="31f5e-p106">Por exemplo, todos os dias, dezenas ou centenas de funcionários entram e saem das organizações. O departamento de RH continua a criar, atualizar ou excluir documentos relacionados a funcionários de acordo com as exigências comerciais. Esse processo está sujeito às diferentes políticas de retenção descritas para o negócio:</span><span class="sxs-lookup"><span data-stu-id="31f5e-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="31f5e-p107">**O período de retenção do conteúdo pode ser uma data conhecida**, como a data da criação, a data da última modificação ou da rotulagem do conteúdo. Por exemplo, você pode reter documentos por sete anos depois de criá-los e excluí-los em seguida.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="31f5e-p108">**O período de retenção do conteúdo pode ser uma data desconhecida**. Por exemplo, com os rótulos de retenção, é possível basear o período de retenção na ocasião em que ocorre um tipo específico de evento, como a data em que um funcionário sai da empresa.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="31f5e-p109">O evento desencadeia o início do período de retenção, e todo o conteúdo com um rótulo aplicado para esse tipo de evento faz com que as ações de retenção do rótulo sejam aplicadas a ele. Isso se chama retenção baseada em eventos. Para saber mais, confira [Visão geral da retenção direcionada por eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="31f5e-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="31f5e-129">Configurar a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="31f5e-129">Set up event-based retention</span></span>

<span data-ttu-id="31f5e-130">Esta seção descreve o que é necessário fazer antes da retenção do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="31f5e-130">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="31f5e-131">Identificar as funções</span><span class="sxs-lookup"><span data-stu-id="31f5e-131">Identify roles</span></span>

<span data-ttu-id="31f5e-132">Identificar as diferentes funções dentro de uma organização que executam as tarefas de Gerenciamento de Registros e que seriam responsáveis pela retenção eficaz e eficiente de documentos comerciais.</span><span class="sxs-lookup"><span data-stu-id="31f5e-132">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="31f5e-133">**Pessoal**</span><span class="sxs-lookup"><span data-stu-id="31f5e-133">**Persona**</span></span>| <span data-ttu-id="31f5e-134">**Função**</span><span class="sxs-lookup"><span data-stu-id="31f5e-134">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="31f5e-135">Administrador</span><span class="sxs-lookup"><span data-stu-id="31f5e-135">Admin</span></span> | <span data-ttu-id="31f5e-136">Cria tipos de evento de retenção, rótulos de retenção e repositórios de registro no SharePoint</span><span class="sxs-lookup"><span data-stu-id="31f5e-136">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="31f5e-137">Gerente de registros</span><span class="sxs-lookup"><span data-stu-id="31f5e-137">Records Manager</span></span>                                  | <span data-ttu-id="31f5e-138">Fornece políticas de retenção, diretrizes de agendamento de retenção e detalhes de conformidade</span><span class="sxs-lookup"><span data-stu-id="31f5e-138">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="31f5e-139">Administrador do sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="31f5e-139">System Admin (business)</span></span>                          | <span data-ttu-id="31f5e-140">Configura e gerencia sistemas externos para trabalhar com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="31f5e-140">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="31f5e-141">Operador de Informações</span><span class="sxs-lookup"><span data-stu-id="31f5e-141">Information Worker</span></span>                               | <span data-ttu-id="31f5e-142">Gerencia o ciclo de vida dos seus processos empresariais (RH, finanças, TI e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="31f5e-142">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="31f5e-143">Configurar o Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="31f5e-143">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="31f5e-144">O administrador de conformidade cria um tipo de evento &ndash;, por exemplo, Rescisão de Funcionário, Vencimento de Contrato ou Término de Fabricação de Produto.</span><span class="sxs-lookup"><span data-stu-id="31f5e-144">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="31f5e-145">(confira o processo passo a passo na [ Retenção orientada por eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="31f5e-145">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="31f5e-146">O administrador de conformidade cria um rótulo de retenção com base em um evento e associa o rótulo a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31f5e-146">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="31f5e-147">Há quatro tipos de fatores desencadeantes para rótulos de retenção:</span><span class="sxs-lookup"><span data-stu-id="31f5e-147">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="31f5e-148">Data de criação</span><span class="sxs-lookup"><span data-stu-id="31f5e-148">Create date</span></span>
                
    2. <span data-ttu-id="31f5e-149">Última modificação</span><span class="sxs-lookup"><span data-stu-id="31f5e-149">Last modified</span></span>
                
    3. <span data-ttu-id="31f5e-150">Data do rótulo (quando o conteúdo foi rotulado)</span><span class="sxs-lookup"><span data-stu-id="31f5e-150">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="31f5e-151">Com base em eventos</span><span class="sxs-lookup"><span data-stu-id="31f5e-151">Event-based</span></span>
    
3. <span data-ttu-id="31f5e-152">O administrador de conformidade publica o rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="31f5e-152">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="31f5e-153">Configurar o SharePoint</span><span class="sxs-lookup"><span data-stu-id="31f5e-153">Set up SharePoint</span></span>
   
<span data-ttu-id="31f5e-154">Para criar um repositório de registros, o administrador de conformidade:</span><span class="sxs-lookup"><span data-stu-id="31f5e-154">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="31f5e-155">Cria um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31f5e-155">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="31f5e-156">Faz um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="31f5e-156">Does one of the following:</span></span>
        
    - <span data-ttu-id="31f5e-p111">Cria uma biblioteca do SharePoint: ele define um rótulo baseado em eventos no nível da biblioteca. Para saber mais, confira [Como aplicar um rótulo de retenção padrão a todo o conteúdo de uma biblioteca, pasta ou de um conjunto de documentos do SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="31f5e-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="31f5e-159">Faz a configuração de um conjunto de documentos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31f5e-159">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="31f5e-160">Para saber mais, confira [Introdução a conjuntos de documentos](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="31f5e-160">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="31f5e-161">Atribui uma ID de ativo ao conjunto de documentos de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-161">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="31f5e-162">Uma ID do ativo é um nome do produto ou código do produto usado pela organização, por exemplo, o Número do funcionário pode ser uma ID do ativo.</span><span class="sxs-lookup"><span data-stu-id="31f5e-162">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="31f5e-163">Ao atribuir a ID do ativo à pasta, todos os itens dessa pasta passar a ter automaticamente a mesma ID do ativo.</span><span class="sxs-lookup"><span data-stu-id="31f5e-163">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="31f5e-164">Isso significa que todos os itens podem ter o período de retenção desencadeado pelo mesmo evento.</span><span class="sxs-lookup"><span data-stu-id="31f5e-164">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="31f5e-165">Maneiras de disparar a retenção baseada em eventos</span><span class="sxs-lookup"><span data-stu-id="31f5e-165">Ways to trigger event-based retention</span></span>

<span data-ttu-id="31f5e-166">Há duas maneiras pelas quais a retenção baseada em eventos pode ser disparada:</span><span class="sxs-lookup"><span data-stu-id="31f5e-166">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="31f5e-167">**Usando a interface do usuário do centro de administração** Esse é um processo que pode ser usado para reter menos conteúdo de cada vez ou no caso de o gatilho que ativa a retenção não ser muito frequente (mensal ou anual, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="31f5e-167">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="31f5e-168">Para mais informações sobre esse método, confira a [Visão geral dos rótulos de retenção baseada em eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="31f5e-168">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="31f5e-169">No entanto, esse método de gatilho de retenção pode ser demorado e propenso a erros, desse modo inibindo escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="31f5e-169">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="31f5e-170">Portanto, uma solução automatizada e ordenada para acionar a retenção pode melhorar a segurança e a conformidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="31f5e-170">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="31f5e-p115">**Usando uma API REST do Microsoft 365** Esse processo pode ser usado quando grandes quantidades de conteúdo devem ser retidas por vez e/ou quando a frequência de disparo da retenção for mais frequente, como diária ou semanal. O fluxo detecta quando um evento ocorre no sistema de linha de negócios e cria automaticamente um evento relacionado no Centro de Conformidade e Segurança. Não é necessário criar manualmente um evento na interface do usuário sempre que ocorrer um.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="31f5e-174">Há duas opções de uso para a API REST:</span><span class="sxs-lookup"><span data-stu-id="31f5e-174">There are two options for using the REST API:</span></span>

- <span data-ttu-id="31f5e-175">**O Microsoft Flow ou um aplicativo semelhante** pode ser usado para desencadear automaticamente a ocorrência de um evento.</span><span class="sxs-lookup"><span data-stu-id="31f5e-175">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="31f5e-176">O Microsoft Flow é um orquestrador para a conexão com outros sistemas.</span><span class="sxs-lookup"><span data-stu-id="31f5e-176">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="31f5e-177">Usar o Microsoft Flow não requer uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="31f5e-177">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="31f5e-178">**PowerShell ou um cliente HTTP para chamar a REST API** Usando o PowerShell (versão 6 ou superior) para chamar a API REST do Microsoft 365 para criar eventos.</span><span class="sxs-lookup"><span data-stu-id="31f5e-178">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="31f5e-179">Uma API REST é um ponto de extremidade de serviço que oferece suporte a conjuntos de operações HTTP (métodos), que fornecem o acesso criar/recuperar/atualizar/deletar aos recursos do serviço.</span><span class="sxs-lookup"><span data-stu-id="31f5e-179">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="31f5e-180">Para saber mais, confira [Componenente de uma solicitação/resposta do API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="31f5e-180">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="31f5e-181">Nesse caso, usando o Microsoft 365 REST API, eventos podem ser criados e recuperados usando operações (métodos) POST e GET.</span><span class="sxs-lookup"><span data-stu-id="31f5e-181">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="31f5e-182">Exemplos de cenários</span><span class="sxs-lookup"><span data-stu-id="31f5e-182">Example scenarios</span></span>

<span data-ttu-id="31f5e-183">Vamos considerar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="31f5e-183">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="31f5e-184">Cenário 1: funcionários que deixam a organização</span><span class="sxs-lookup"><span data-stu-id="31f5e-184">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="31f5e-185">Uma organização cria e armazena vários documentos relativos ao contrato de trabalho para cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-185">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="31f5e-186">Esses documentos são gerenciados e mantidos enquanto durar o vínculo de emprego de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-186">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="31f5e-187">No entanto, quando o funcionário deixa a organização ou o contrato de trabalho chega ao fim, a organização é obrigada por requisitos legais e comerciais a guardar os documentos desse funcionário por um período estipulado.</span><span class="sxs-lookup"><span data-stu-id="31f5e-187">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="31f5e-188">Agora, se vários funcionários deixarem a organização todos os dias, ela deverá disparar o tempo de retenção de centenas ou milhares de documentos por dia.</span><span class="sxs-lookup"><span data-stu-id="31f5e-188">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="31f5e-189">Além disso, o período de retenção deve ser calculado para cada um desses funcionários, como a Data de rescisão + número de dias, meses ou anos, com base no tipo de registro do funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-189">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="31f5e-190">Por exemplo, a remuneração versus os registros de benefícios desse funcionário pode precisar de uma retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="31f5e-190">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="31f5e-191">O diagrama abaixo mostra como pode haver diversos rótulos associados a um único evento.</span><span class="sxs-lookup"><span data-stu-id="31f5e-191">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="31f5e-192">Aqui estão todos os arquivos sob o rótulo de Indenização do trabalhador e todos os arquivos sob o rótulo de Benefícios dos funcionários estão ambos associados a um único evento, que é o funcionário deixando a organização.</span><span class="sxs-lookup"><span data-stu-id="31f5e-192">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="31f5e-193">Cada um desses arquivos tem diferentes relógios de retenção.</span><span class="sxs-lookup"><span data-stu-id="31f5e-193">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="31f5e-194">Portanto, quando um funcionário deixa a organização, esses arquivos dentro de cada etiqueta têm um período de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="31f5e-194">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="31f5e-195">Disparar todos esses relógios diferentes para cada tipo de arquivo ou rótulo para cada funcionário é uma tarefa bastante desafiadora.</span><span class="sxs-lookup"><span data-stu-id="31f5e-195">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="31f5e-196">Imagine fazer isso para vários funcionários.</span><span class="sxs-lookup"><span data-stu-id="31f5e-196">Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, eventos e rótulos](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="31f5e-198">Portanto, um processo automatizado para acionar esses diferentes relógios de retenção para vários funcionários economizaria tempo, seria isento de erros e extremamente eficiente.</span><span class="sxs-lookup"><span data-stu-id="31f5e-198">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="31f5e-199">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="31f5e-199">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e ações para o cenário de saída do funcionário da organização](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="31f5e-201">O administrador criar pastas de funcionários para o Conjunto de documentos, como Sara Melo, Diogo Martins.</span><span class="sxs-lookup"><span data-stu-id="31f5e-201">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="31f5e-202">O administrador adiciona arquivos de funcionários, como Benefícios, Folha de pagamento e Seguro-doença, à pasta de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-202">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="31f5e-203">O administrador atribui uma ID de ativo para a pasta de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-203">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="31f5e-204">O administrador do CCS entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="31f5e-204">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="31f5e-205">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Rescisão de Funcionário" e "Contratação de Funcionário".</span><span class="sxs-lookup"><span data-stu-id="31f5e-205">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="31f5e-206">O administrador do Centro de Conformidade e Segurança cria o rótulo "Retenção de Funcionários".</span><span class="sxs-lookup"><span data-stu-id="31f5e-206">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="31f5e-207">O rótulo "Retenção de Funcionário" é publicado e aplicado de forma automática ou manual aos arquivos de funcionários no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31f5e-207">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="31f5e-208">Um sistema de gerenciamento de RH, como o Workday, pode trabalhar com o Microsoft Flow para realizar periodicamente o gerenciamento de arquivos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="31f5e-208">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="31f5e-209">Quando um funcionário deixa a organização, o Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-209">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="31f5e-210">Usando o Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="31f5e-210">Using Microsoft Flow</span></span>

<span data-ttu-id="31f5e-211">Etapa 1 – Criar um fluxo para criar um evento usando a API REST do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="31f5e-211">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usando o Flow para criar um evento](media/automate-event-driven-retention-flow-1.png)

![Usando um fluxo para chamar a API REST](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="31f5e-214">Criar um evento</span><span class="sxs-lookup"><span data-stu-id="31f5e-214">Create an event</span></span>

<span data-ttu-id="31f5e-215">Exemplo de código para chamar a API REST</span><span class="sxs-lookup"><span data-stu-id="31f5e-215">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="31f5e-216">Método</span><span class="sxs-lookup"><span data-stu-id="31f5e-216">Method</span></span></th>
<th><span data-ttu-id="31f5e-217">POST</span><span class="sxs-lookup"><span data-stu-id="31f5e-217">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="31f5e-218">URL</span><span class="sxs-lookup"><span data-stu-id="31f5e-218">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-219">Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="31f5e-219">Headers</span></span></td>
<td><span data-ttu-id="31f5e-220">Content-Type</span><span class="sxs-lookup"><span data-stu-id="31f5e-220">Content-Type</span></span></td>
<td><span data-ttu-id="31f5e-221">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31f5e-221">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="31f5e-222">Corpo</span><span class="sxs-lookup"><span data-stu-id="31f5e-222">Body</span></span></td>
<td><p><span data-ttu-id="31f5e-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="31f5e-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="31f5e-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="31f5e-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="31f5e-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="31f5e-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="31f5e-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="31f5e-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="31f5e-229">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-229">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="31f5e-230">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-230">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="31f5e-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="31f5e-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="31f5e-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="31f5e-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="31f5e-235">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-235">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="31f5e-236">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-236">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="31f5e-237">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-237">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-238">Autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-238">Authentication</span></span></td>
<td><span data-ttu-id="31f5e-239">Básica</span><span class="sxs-lookup"><span data-stu-id="31f5e-239">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="31f5e-240">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="31f5e-240">Username</span></span></td>
<td><span data-ttu-id="31f5e-241">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-241">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-242">Senha</span><span class="sxs-lookup"><span data-stu-id="31f5e-242">Password</span></span></td>
<td><span data-ttu-id="31f5e-243">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-243">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="31f5e-244">Parâmetros disponíveis</span><span class="sxs-lookup"><span data-stu-id="31f5e-244">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="31f5e-245"><strong>Parâmetros</strong></span><span class="sxs-lookup"><span data-stu-id="31f5e-245"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="31f5e-246"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="31f5e-246"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="31f5e-247"><strong>Anotações</strong></span><span class="sxs-lookup"><span data-stu-id="31f5e-247"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="31f5e-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="31f5e-249">Fornece um nome exclusivo para o evento.</span><span class="sxs-lookup"><span data-stu-id="31f5e-249">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="31f5e-p121">Não pode conter espaços à direita nem os seguintes caracteres: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="31f5e-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="31f5e-253">Insere o nome do tipo de evento (ou GUID).</span><span class="sxs-lookup"><span data-stu-id="31f5e-253">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="31f5e-p122">Exemplo: "Rescisão de funcionário". O Tipo de evento deve estar associado a um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="31f5e-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="31f5e-257">Insere "ComplianceAssetId:"” + ID do funcionário.</span><span class="sxs-lookup"><span data-stu-id="31f5e-257">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="31f5e-258">Exemplo: &quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-258">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="31f5e-260">Data e hora do evento</span><span class="sxs-lookup"><span data-stu-id="31f5e-260">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="31f5e-261">Formato: yyyy-MM-ddTHH:mm:ssZ. Exemplo:</span><span class="sxs-lookup"><span data-stu-id="31f5e-261">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="31f5e-262">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="31f5e-262">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="31f5e-263">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="31f5e-263">Response codes</span></span>

| <span data-ttu-id="31f5e-264">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="31f5e-264">**Response Code**</span></span> | <span data-ttu-id="31f5e-265">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="31f5e-265">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="31f5e-266">302</span><span class="sxs-lookup"><span data-stu-id="31f5e-266">302</span></span>               | <span data-ttu-id="31f5e-267">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="31f5e-267">Redirect</span></span>              |
| <span data-ttu-id="31f5e-268">201</span><span class="sxs-lookup"><span data-stu-id="31f5e-268">201</span></span>               | <span data-ttu-id="31f5e-269">Criado em</span><span class="sxs-lookup"><span data-stu-id="31f5e-269">Created</span></span>               |
| <span data-ttu-id="31f5e-270">403</span><span class="sxs-lookup"><span data-stu-id="31f5e-270">403</span></span>               | <span data-ttu-id="31f5e-271">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="31f5e-271">Authorization Failed</span></span>  |
| <span data-ttu-id="31f5e-272">401</span><span class="sxs-lookup"><span data-stu-id="31f5e-272">401</span></span>               | <span data-ttu-id="31f5e-273">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-273">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="31f5e-274">Obter eventos com base em intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="31f5e-274">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="31f5e-275">Método</span><span class="sxs-lookup"><span data-stu-id="31f5e-275">Method</span></span></th>
<th><span data-ttu-id="31f5e-276">GET</span><span class="sxs-lookup"><span data-stu-id="31f5e-276">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="31f5e-277">URL</span><span class="sxs-lookup"><span data-stu-id="31f5e-277">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="31f5e-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="31f5e-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-279">Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="31f5e-279">Headers</span></span></td>
<td><span data-ttu-id="31f5e-280">Content-Type</span><span class="sxs-lookup"><span data-stu-id="31f5e-280">Content-Type</span></span></td>
<td><span data-ttu-id="31f5e-281">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31f5e-281">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-282">Autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-282">Authentication</span></span></td>
<td><span data-ttu-id="31f5e-283">Básica</span><span class="sxs-lookup"><span data-stu-id="31f5e-283">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="31f5e-284">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="31f5e-284">Username</span></span></td>
<td><span data-ttu-id="31f5e-285">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-285">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31f5e-286">Senha</span><span class="sxs-lookup"><span data-stu-id="31f5e-286">Password</span></span></td>
<td><span data-ttu-id="31f5e-287">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-287">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="31f5e-288">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="31f5e-288">Response codes</span></span>

| <span data-ttu-id="31f5e-289">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="31f5e-289">**Response Code**</span></span> | <span data-ttu-id="31f5e-290">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="31f5e-290">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="31f5e-291">200</span><span class="sxs-lookup"><span data-stu-id="31f5e-291">200</span></span>               | <span data-ttu-id="31f5e-292">OK. Uma lista de eventos em atom+xml</span><span class="sxs-lookup"><span data-stu-id="31f5e-292">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="31f5e-293">404</span><span class="sxs-lookup"><span data-stu-id="31f5e-293">404</span></span>               | <span data-ttu-id="31f5e-294">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="31f5e-294">Not found</span></span>                         |
| <span data-ttu-id="31f5e-295">302</span><span class="sxs-lookup"><span data-stu-id="31f5e-295">302</span></span>               | <span data-ttu-id="31f5e-296">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="31f5e-296">Redirect</span></span>                          |
| <span data-ttu-id="31f5e-297">401</span><span class="sxs-lookup"><span data-stu-id="31f5e-297">401</span></span>               | <span data-ttu-id="31f5e-298">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="31f5e-298">Authorization Failed</span></span>              |
| <span data-ttu-id="31f5e-299">403</span><span class="sxs-lookup"><span data-stu-id="31f5e-299">403</span></span>               | <span data-ttu-id="31f5e-300">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-300">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="31f5e-301">Obter um evento por ID</span><span class="sxs-lookup"><span data-stu-id="31f5e-301">Get an event by ID</span></span>

| <span data-ttu-id="31f5e-302">Método</span><span class="sxs-lookup"><span data-stu-id="31f5e-302">Method</span></span>         | <span data-ttu-id="31f5e-303">GET</span><span class="sxs-lookup"><span data-stu-id="31f5e-303">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="31f5e-304">URL</span><span class="sxs-lookup"><span data-stu-id="31f5e-304">URL</span></span>            | <span data-ttu-id="31f5e-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="31f5e-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="31f5e-306">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="31f5e-306">Header</span></span>         | <span data-ttu-id="31f5e-307">Content-Type</span><span class="sxs-lookup"><span data-stu-id="31f5e-307">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="31f5e-308">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31f5e-308">application/atom+xml</span></span> |
| <span data-ttu-id="31f5e-309">Autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-309">Authentication</span></span> | <span data-ttu-id="31f5e-310">Básica</span><span class="sxs-lookup"><span data-stu-id="31f5e-310">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="31f5e-311">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="31f5e-311">Username</span></span>       | <span data-ttu-id="31f5e-312">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-312">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="31f5e-313">Senha</span><span class="sxs-lookup"><span data-stu-id="31f5e-313">Password</span></span>       | <span data-ttu-id="31f5e-314">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-314">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="31f5e-315">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="31f5e-315">Response codes</span></span>

| <span data-ttu-id="31f5e-316">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="31f5e-316">**Response Code**</span></span> | <span data-ttu-id="31f5e-317">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="31f5e-317">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="31f5e-318">200</span><span class="sxs-lookup"><span data-stu-id="31f5e-318">200</span></span>               | <span data-ttu-id="31f5e-319">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="31f5e-319">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="31f5e-320">404</span><span class="sxs-lookup"><span data-stu-id="31f5e-320">404</span></span>               | <span data-ttu-id="31f5e-321">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="31f5e-321">Not found</span></span>                                            |
| <span data-ttu-id="31f5e-322">302</span><span class="sxs-lookup"><span data-stu-id="31f5e-322">302</span></span>               | <span data-ttu-id="31f5e-323">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="31f5e-323">Redirect</span></span>                                             |
| <span data-ttu-id="31f5e-324">401</span><span class="sxs-lookup"><span data-stu-id="31f5e-324">401</span></span>               | <span data-ttu-id="31f5e-325">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="31f5e-325">Authorization Failed</span></span>                                 |
| <span data-ttu-id="31f5e-326">403</span><span class="sxs-lookup"><span data-stu-id="31f5e-326">403</span></span>               | <span data-ttu-id="31f5e-327">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-327">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="31f5e-328">Obter um evento por nome</span><span class="sxs-lookup"><span data-stu-id="31f5e-328">Get an event by name</span></span>

| <span data-ttu-id="31f5e-329">Método</span><span class="sxs-lookup"><span data-stu-id="31f5e-329">Method</span></span>         | <span data-ttu-id="31f5e-330">GET</span><span class="sxs-lookup"><span data-stu-id="31f5e-330">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="31f5e-331">URL</span><span class="sxs-lookup"><span data-stu-id="31f5e-331">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="31f5e-332">Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="31f5e-332">Headers</span></span>        | <span data-ttu-id="31f5e-333">Content-Type</span><span class="sxs-lookup"><span data-stu-id="31f5e-333">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="31f5e-334">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31f5e-334">application/atom+xml</span></span> |
| <span data-ttu-id="31f5e-335">Autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-335">Authentication</span></span> | <span data-ttu-id="31f5e-336">Básica</span><span class="sxs-lookup"><span data-stu-id="31f5e-336">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="31f5e-337">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="31f5e-337">Username</span></span>       | <span data-ttu-id="31f5e-338">"Usuáriodeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-338">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="31f5e-339">Senha</span><span class="sxs-lookup"><span data-stu-id="31f5e-339">Password</span></span>       | <span data-ttu-id="31f5e-340">"Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="31f5e-340">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="31f5e-341">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="31f5e-341">Response codes</span></span>

| <span data-ttu-id="31f5e-342">**Código de resposta**</span><span class="sxs-lookup"><span data-stu-id="31f5e-342">**Response Code**</span></span> | <span data-ttu-id="31f5e-343">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="31f5e-343">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="31f5e-344">200</span><span class="sxs-lookup"><span data-stu-id="31f5e-344">200</span></span>               | <span data-ttu-id="31f5e-345">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="31f5e-345">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="31f5e-346">404</span><span class="sxs-lookup"><span data-stu-id="31f5e-346">404</span></span>               | <span data-ttu-id="31f5e-347">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="31f5e-347">Not found</span></span>                                            |
| <span data-ttu-id="31f5e-348">302</span><span class="sxs-lookup"><span data-stu-id="31f5e-348">302</span></span>               | <span data-ttu-id="31f5e-349">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="31f5e-349">Redirect</span></span>                                             |
| <span data-ttu-id="31f5e-350">401</span><span class="sxs-lookup"><span data-stu-id="31f5e-350">401</span></span>               | <span data-ttu-id="31f5e-351">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="31f5e-351">Authorization Failed</span></span>                                 |
| <span data-ttu-id="31f5e-352">403</span><span class="sxs-lookup"><span data-stu-id="31f5e-352">403</span></span>               | <span data-ttu-id="31f5e-353">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="31f5e-353">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="31f5e-354">Usando o PowerShell (versão 6 ou posterior) ou um cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="31f5e-354">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="31f5e-355">Etapa 1 – Conectar-se ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31f5e-355">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="31f5e-356">Etapa 2 – Executar o seguinte script.</span><span class="sxs-lookup"><span data-stu-id="31f5e-356">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31f5e-357">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="31f5e-357">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="31f5e-358">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-358">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="31f5e-359">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-359">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="31f5e-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="31f5e-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="31f5e-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="31f5e-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="31f5e-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="31f5e-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="31f5e-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="31f5e-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="31f5e-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="31f5e-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="31f5e-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="31f5e-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="31f5e-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="31f5e-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="31f5e-370">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-370">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="31f5e-371">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-371">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="31f5e-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="31f5e-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="31f5e-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="31f5e-375">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-375">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="31f5e-376">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="31f5e-376">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="31f5e-377">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-377">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="31f5e-378">$event = $null</span><span class="sxs-lookup"><span data-stu-id="31f5e-378">$event = $null</span></span></p>
<p><span data-ttu-id="31f5e-379">try</span><span class="sxs-lookup"><span data-stu-id="31f5e-379">try</span></span></p>
<p><span data-ttu-id="31f5e-380">{</span><span class="sxs-lookup"><span data-stu-id="31f5e-380">{</span></span></p>
<p><span data-ttu-id="31f5e-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="31f5e-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="31f5e-382">}</span><span class="sxs-lookup"><span data-stu-id="31f5e-382">}</span></span></p>
<p><span data-ttu-id="31f5e-383">catch</span><span class="sxs-lookup"><span data-stu-id="31f5e-383">catch</span></span></p>
<p><span data-ttu-id="31f5e-384">{</span><span class="sxs-lookup"><span data-stu-id="31f5e-384">{</span></span></p>
<p><span data-ttu-id="31f5e-385">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="31f5e-385">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="31f5e-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="31f5e-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="31f5e-387">{</span><span class="sxs-lookup"><span data-stu-id="31f5e-387">{</span></span></p>
<p><span data-ttu-id="31f5e-388">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="31f5e-388">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="31f5e-389">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="31f5e-389">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="31f5e-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="31f5e-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="31f5e-391">}</span><span class="sxs-lookup"><span data-stu-id="31f5e-391">}</span></span></p>
<p><span data-ttu-id="31f5e-392">}</span><span class="sxs-lookup"><span data-stu-id="31f5e-392">}</span></span></p>
<p><span data-ttu-id="31f5e-393">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="31f5e-393">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="31f5e-394">Verificar o resultado nas duas opções</span><span class="sxs-lookup"><span data-stu-id="31f5e-394">Verify the outcome in both options</span></span>

<span data-ttu-id="31f5e-395">Etapa 1: Vá para o Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="31f5e-395">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="31f5e-396">Etapa 2: Selecione **Eventos** em **Governança de informações**.</span><span class="sxs-lookup"><span data-stu-id="31f5e-396">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="31f5e-397">Etapa 3 : Verifique se o Evento foi criado.</span><span class="sxs-lookup"><span data-stu-id="31f5e-397">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="31f5e-398">Da mesma forma, as opções acima para automatizar a retenção baseada em eventos também podem ser usadas também para os cenários a seguir.</span><span class="sxs-lookup"><span data-stu-id="31f5e-398">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="31f5e-399">Cenário 2 : Expiração de Contratos</span><span class="sxs-lookup"><span data-stu-id="31f5e-399">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="31f5e-400">Uma organização pode fazer registros múltiplos para um único contrato com clientes, fornecedores e parceiros.</span><span class="sxs-lookup"><span data-stu-id="31f5e-400">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="31f5e-401">Esse documentos podem ser colocados em uma biblioteca de documentos como o Sharepoint.</span><span class="sxs-lookup"><span data-stu-id="31f5e-401">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="31f5e-402">O término de um contrato determina o início do período de retenção dos documentos associados àquele contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-402">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="31f5e-403">Por exemplo, todos os registros relacionados a contratos precisam ser retidos por cinco anos contados da data em que o contrato expirou.</span><span class="sxs-lookup"><span data-stu-id="31f5e-403">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="31f5e-404">O evento que desencadeia o período de retenção de cinco anos é a expiração do contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-404">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="31f5e-405">Um sistema de CRM (gerenciamento de relacionamento com o cliente) pode trabalhar com o Microsoft 365 e disparar a retenção de documentos do contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-405">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="31f5e-406">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="31f5e-406">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e tarefas para o cenário de expiração de contrato](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="31f5e-408">O administrador cria uma biblioteca do SharePoint com várias pastas para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-408">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="31f5e-409">O administrador adiciona arquivos de contrato, como Contratos de Licença e Contratos de Desenvolvimento, a cada pasta de contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-409">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="31f5e-410">O administrador atribui uma ID de ativo à pasta de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-410">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="31f5e-411">O administrador do CCS entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="31f5e-411">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="31f5e-412">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a contratos, como "Criação de Contrato" e "Expiração de Contrato".</span><span class="sxs-lookup"><span data-stu-id="31f5e-412">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="31f5e-413">O administrador do Centro de Conformidade e Segurança cria o rótulo "Expiração do Contrato".</span><span class="sxs-lookup"><span data-stu-id="31f5e-413">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="31f5e-414">O rótulo "Expiração de Contrato" é publicado e aplicado de forma automática ou manual aos arquivos de contratos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31f5e-414">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="31f5e-415">O Sistema de Gerenciamento de Contratos pode trabalhar com o Microsoft Flow ou um aplicativo semelhante para realizar periodicamente o gerenciamento de arquivos de contratos.</span><span class="sxs-lookup"><span data-stu-id="31f5e-415">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="31f5e-416">Quando um contrato expira, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do contrato.</span><span class="sxs-lookup"><span data-stu-id="31f5e-416">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="31f5e-417">Cenário 3 – Término de fabricação de produto</span><span class="sxs-lookup"><span data-stu-id="31f5e-417">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="31f5e-p124">Uma empresa que fabrica diferentes linhas de produtos cria muitas especificações de fabricação e documentos de precificação. Quando o produto deixa de ser fabricado, todas as especificações e os documentos vinculados a esse produto devem ser retidos por um período específico, após o término da vida útil do produto.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="31f5e-420">Um sistema de ERP (Planejamento de Recursos Empresariais) pode trabalhar com o Microsoft 365 e o Microsoft Flow para disparar a retenção.</span><span class="sxs-lookup"><span data-stu-id="31f5e-420">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="31f5e-421">**Como configurar a retenção automatizada baseada em eventos para este cenário:**</span><span class="sxs-lookup"><span data-stu-id="31f5e-421">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funções e tarefas para o cenário de ciclo de vida do produto](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="31f5e-423">O administrador cria pastas de produtos no Conjunto de documentos, como Produto 1, Produto 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="31f5e-423">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="31f5e-424">O administrador adiciona arquivos de produto, como Especificações de Fabricação, Preços de Produto e Licenciamento de Produto, a cada pasta de produto.</span><span class="sxs-lookup"><span data-stu-id="31f5e-424">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="31f5e-425">O administrador atribui uma ID de ativo à pasta de cada produto.</span><span class="sxs-lookup"><span data-stu-id="31f5e-425">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="31f5e-426">O administrador do CCS entra no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="31f5e-426">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="31f5e-427">O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Início de Fabricação de Produto" e "Término de Fabricação de Produto".</span><span class="sxs-lookup"><span data-stu-id="31f5e-427">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="31f5e-428">O administrador do Centro de Conformidade e Segurança cria o rótulo "Término de Fabricação de Produto".</span><span class="sxs-lookup"><span data-stu-id="31f5e-428">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="31f5e-429">O rótulo "Término de Fabricação de Produto" é publicado e aplicado de forma automática ou manual aos arquivos de produtos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31f5e-429">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="31f5e-430">Os sistemas de ERP podem trabalhar com o Microsoft Flow ou com aplicativos semelhantes para realizar periodicamente o gerenciamento de arquivos de produtos.</span><span class="sxs-lookup"><span data-stu-id="31f5e-430">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="31f5e-431">Quando a fabricação de um produto é encerrada, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do produto.</span><span class="sxs-lookup"><span data-stu-id="31f5e-431">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="31f5e-432">Apêndice</span><span class="sxs-lookup"><span data-stu-id="31f5e-432">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="31f5e-433">Como usar resultados de resposta de Redirecionamento 302 para chamar a API REST</span><span class="sxs-lookup"><span data-stu-id="31f5e-433">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="31f5e-434">Invoque uma chamada de evento de retenção POST usando a URL da API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (é necessário ter permissões de administrador global).</span><span class="sxs-lookup"><span data-stu-id="31f5e-434">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="31f5e-p125">Verifique o código da resposta. Se for 302, obtenha a URL redirecionada da propriedade Location do cabeçalho da resposta.</span><span class="sxs-lookup"><span data-stu-id="31f5e-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="31f5e-437">Invoque a chamada de evento de retenção POST usando a URL redirecionada.</span><span class="sxs-lookup"><span data-stu-id="31f5e-437">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="31f5e-438">Créditos</span><span class="sxs-lookup"><span data-stu-id="31f5e-438">Credits</span></span>

<span data-ttu-id="31f5e-439">Este tópico foi revisado por:</span><span class="sxs-lookup"><span data-stu-id="31f5e-439">This topic was reviewed by:</span></span>

<span data-ttu-id="31f5e-440">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="31f5e-440">Antonio Maio</span></span><br/><span data-ttu-id="31f5e-441">MVP de aplicativos e serviços do Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="31f5e-441">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="31f5e-442">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="31f5e-442">Antonio.Maio@Protiviti.com</span></span>
