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
# <a name="automate-event-based-retention"></a>Automatizar retenção baseada em eventos

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.

To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.

To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.

Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.

## <a name="about-event-based-retention"></a>Sobre a retenção baseada em eventos

An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.

For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:

- **The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.

- **The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.

The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>Configurar a retenção baseada em eventos

Esta seção descreve o que é necessário fazer antes da retenção do conteúdo.

### <a name="identify-roles"></a>Identificar as funções

Identificar as diferentes funções dentro de uma organização que executam as tarefas de Gerenciamento de Registros e que seriam responsáveis pela retenção eficaz e eficiente de documentos comerciais.

  | Persona | Função |
  | - | - |
  | Administrador | Cria tipos de evento de retenção, rótulos de retenção e repositórios de registro no SharePoint |
  | Gerente de registros                                  | Fornece políticas de retenção, diretrizes de agendamento de retenção e detalhes de conformidade   |
  | Administrador do sistema (empresa)                          | Configura e gerencia sistemas externos para trabalhar com o Microsoft 365                       |
  | Operador de Informações                               | Gerencia o ciclo de vida dos seus processos empresariais (RH, finanças, TI e assim por diante)                 |

### <a name="set-up-the-security--compliance-center"></a>Configurar o Centro de Conformidade e Segurança
  
1. O administrador de conformidade cria um tipo de evento &ndash;, por exemplo, Rescisão de Funcionário, Vencimento de Contrato ou Término de Fabricação de Produto. (confira o processo passo a passo na [ Retenção orientada por eventos](event-driven-retention.md).
    
2. O administrador de conformidade cria um rótulo de retenção com base em um evento e associa o rótulo a um tipo de evento.
    
    Há quatro tipos de fatores desencadeantes para rótulos de retenção:
            
    1. Data de criação
                
    2. Última modificação
                
    3. Data do rótulo (quando o conteúdo foi rotulado)
                
    4. Com base em eventos
    
3. O administrador de conformidade publica o rótulo de retenção.

### <a name="set-up-sharepoint"></a>Configurar o SharePoint
   
Para criar um repositório de registros, o administrador de conformidade:

1. Cria um site do SharePoint.

2. Faz um dos seguintes procedimentos:
        
   - Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
   - Faz a configuração de um conjunto de documentos no SharePoint. Para saber mais, confira [Introdução a conjuntos de documentos](https://support.microsoft.com/pt-BR/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).
      
3. Atribui uma ID de ativo ao conjunto de documentos de cada funcionário. Uma ID do ativo é um nome do produto ou código do produto usado pela organização, por exemplo, o Número do funcionário pode ser uma ID do ativo. Ao atribuir a ID do ativo à pasta, todos os itens dessa pasta passar a ter automaticamente a mesma ID do ativo. Isso significa que todos os itens podem ter o período de retenção desencadeado pelo mesmo evento.

## <a name="ways-to-trigger-event-based-retention"></a>Maneiras de disparar a retenção baseada em eventos

Há duas maneiras pelas quais a retenção baseada em eventos pode ser disparada:

- **Usando a interface do usuário do centro de administração** Esse é um processo que pode ser usado para reter menos conteúdo de cada vez ou no caso de o gatilho que ativa a retenção não ser muito frequente (mensal ou anual, por exemplo). Para mais informações sobre esse método, confira a [Visão geral dos rótulos de retenção baseada em eventos](event-driven-retention.md). No entanto, esse método de gatilho de retenção pode ser demorado e propenso a erros, desse modo inibindo escalabilidade. Portanto, uma solução automatizada e ordenada para acionar a retenção pode melhorar a segurança e a conformidade dos dados.

- **Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.

Há duas opções de uso para a API REST:

- **O Microsoft Flow ou um aplicativo semelhante** pode ser usado para desencadear automaticamente a ocorrência de um evento. O Microsoft Flow é um orquestrador para a conexão com outros sistemas. Usar o Microsoft Flow não requer uma solução personalizada.

- **PowerShell ou um cliente HTTP para chamar a REST API** Usando o PowerShell (versão 6 ou superior) para chamar a API REST do Microsoft 365 para criar eventos. 

Uma API REST é um ponto de extremidade de serviço que oferece suporte a conjuntos de operações HTTP (métodos), que fornecem o acesso criar/recuperar/atualizar/deletar aos recursos do serviço. Para saber mais, confira [Componenente de uma solicitação/resposta do API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). Nesse caso, usando o Microsoft 365 REST API, eventos podem ser criados e recuperados usando operações (métodos) POST e GET.

## <a name="example-scenarios"></a>Exemplos de cenários

Vamos considerar os seguintes cenários:

### <a name="scenario-1-employees-leaving-the-organization"></a>Cenário 1: funcionários que deixam a organização 

Uma organização cria e armazena vários documentos relativos ao contrato de trabalho para cada funcionário. Esses documentos são gerenciados e mantidos enquanto durar o vínculo de emprego de cada funcionário. No entanto, quando o funcionário deixa a organização ou o contrato de trabalho chega ao fim, a organização é obrigada por requisitos legais e comerciais a guardar os documentos desse funcionário por um período estipulado.

Agora, se vários funcionários deixarem a organização todos os dias, ela deverá disparar o tempo de retenção de centenas ou milhares de documentos por dia.

Além disso, o período de retenção deve ser calculado para cada um desses funcionários, como a Data de rescisão + número de dias, meses ou anos, com base no tipo de registro do funcionário. Por exemplo, a remuneração versus os registros de benefícios desse funcionário pode precisar de uma retenção diferente.

O diagrama abaixo mostra como pode haver diversos rótulos associados a um único evento. Aqui estão todos os arquivos sob o rótulo de Indenização do trabalhador e todos os arquivos sob o rótulo de Benefícios dos funcionários estão ambos associados a um único evento, que é o funcionário deixando a organização. Cada um desses arquivos tem diferentes relógios de retenção. Portanto, quando um funcionário deixa a organização, esses arquivos dentro de cada etiqueta têm um período de retenção diferente. Disparar todos esses relógios diferentes para cada tipo de arquivo ou rótulo para cada funcionário é uma tarefa bastante desafiadora. Imagine fazer isso para vários funcionários.

![Diagrama de tipo de evento, eventos e rótulos](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

Portanto, um processo automatizado para acionar esses diferentes relógios de retenção para vários funcionários economizaria tempo, seria isento de erros e extremamente eficiente.

**Como configurar a retenção automatizada baseada em eventos para este cenário:**

![Diagrama de funções e ações para o cenário de saída do funcionário da organização](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - O administrador criar pastas de funcionários para o Conjunto de documentos, como Sara Melo, Diogo Martins.

  - O administrador adiciona arquivos de funcionários, como Benefícios, Folha de pagamento e Seguro-doença, à pasta de cada funcionário.

  - O administrador atribui uma ID de ativo para a pasta de cada funcionário. 

  - O administrador do CCS entra no Centro de Conformidade e Segurança.

  - O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Rescisão de Funcionário" e "Contratação de Funcionário".

  - O administrador do Centro de Conformidade e Segurança cria o rótulo "Retenção de Funcionários".

  - O rótulo "Retenção de Funcionário" é publicado e aplicado de forma automática ou manual aos arquivos de funcionários no SharePoint.

  - Um sistema de gerenciamento de RH, como o Workday, pode trabalhar com o Microsoft Flow para realizar periodicamente o gerenciamento de arquivos de funcionários.

  - Quando um funcionário deixa a organização, o Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do funcionário.

#### <a name="using-microsoft-flow"></a>Usando o Microsoft Flow

Etapa 1 – Criar um fluxo para criar um evento usando a API REST do Microsoft 365

![Usando o Flow para criar um evento](../media/automate-event-driven-retention-flow-1.png)

![Usando um fluxo para chamar a API REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>Criar um evento

Exemplo de código para chamar a API REST

- **Método**: POSTAR
- **URL**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
- **Cabeçalhos**: Chave = content-type, valor = application/atom+xml
- **Corpo**:
    
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
- **Autenticação**: Básica
- **Nome de usuário**: "Complianceuser"
- **Senha**: "Senhadeconformidade"


##### <a name="available-parameters"></a>Parâmetros disponíveis


|Parâmetros|Descrição|Observações|
|--- |--- |--- |
|<d:Name></d:Name>|Fornece um nome exclusivo para o evento,|Não pode conter espaços à direita nem os seguintes caracteres: % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|Insere o nome do tipo de evento (ou GUID).|Example: “Employee termination”. Event type has to be associated with a retention label.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|Insere "ComplianceAssetId:"” + ID do funcionário.|Example: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|Data e hora do evento|Formato: yyyy-MM-ddTHH:mm:ssZ. Exemplo: 2018-12-01T00:00:00Z
|

##### <a name="response-codes"></a>Códigos de resposta

| Código da resposta | Descrição       |
| ----------------- | --------------------- |
| 302               | Redirecionamento              |
| 201               | Criado em               |
| 403               | Falha na autorização  |
| 401               | Falha na autenticação |

##### <a name="get-events-based-on-time-range"></a>Obter eventos com base em intervalo de tempo

- **Método**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **Cabeçalhos**: Chave = content-type, valor = application/atom+xml

- **Autenticação**: Básica

- **Nome de usuário**: "Complianceuser"

- **Senha**: "Senhadeconformidade"


##### <a name="response-codes"></a>Códigos de resposta

| Código da resposta | Descrição                   |
| ----------------- | --------------------------------- |
| 200               | OK. Uma lista de eventos em atom+xml |
| 404               | Não encontrado                         |
| 302               | Redirecionamento                          |
| 401               | Falha na autorização              |
| 403               | Falha na autenticação             |

##### <a name="get-an-event-by-id"></a>Obter um evento por ID

- **Método**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **Cabeçalhos**: Chave = content-type, valor = application/atom+xml

- **Autenticação**: Básica

- **Nome de usuário**: "Complianceuser"

- **Senha**: "Senhadeconformidade"



##### <a name="response-codes"></a>Códigos de resposta

| Código da resposta | Descrição                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK. O corpo da resposta contém o evento em atom+xml. |
| 404               | Não encontrado                                            |
| 302               | Redirecionamento                                             |
| 401               | Falha na autorização                                 |
| 403               | Falha na autenticação                                |

##### <a name="get-an-event-by-name"></a>Obter um evento por nome

- **Método**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **Cabeçalhos**: Chave = content-type, valor = application/atom+xml

- **Autenticação**: Básica

- **Nome de usuário**: "Complianceuser"

- **Senha**: "Senhadeconformidade"


##### <a name="response-codes"></a>Códigos de resposta

| Código da resposta | Descrição                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK. O corpo da resposta contém o evento em atom+xml. |
| 404               | Não encontrado                                            |
| 302               | Redirecionamento                                             |
| 401               | Falha na autorização                                 |
| 403               | Falha na autenticação                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a>Usando o PowerShell (versão 6 ou posterior) ou um cliente HTTP

Etapa 1 – Conectar-se ao PowerShell.

Etapa 2 – Executar o seguinte script.

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


#### <a name="verify-the-outcome-in-both-options"></a>Verificar o resultado nas duas opções

Etapa 1: Vá para o Centro de Conformidade e Segurança.

Etapa 2: Selecione **Eventos** em **Governança de informações**.

Etapa 3 : Verifique se o Evento foi criado.

Da mesma forma, as opções acima para automatizar a retenção baseada em eventos também podem ser usadas também para os cenários a seguir.

### <a name="scenario-2-contracts-expiring"></a>Cenário 2 : Expiração de Contratos

Uma organização pode fazer registros múltiplos para um único contrato com clientes, fornecedores e parceiros. Esse documentos podem ser colocados em uma biblioteca de documentos como o Sharepoint. O término de um contrato determina o início do período de retenção dos documentos associados àquele contrato. Por exemplo, todos os registros relacionados a contratos precisam ser retidos por cinco anos contados da data em que o contrato expirou. O evento que desencadeia o período de retenção de cinco anos é a expiração do contrato.

Um sistema de CRM (Gerenciamento de Relacionamento com o cliente) pode trabalhar com o Microsoft 365 e desencadear a retenção de documentos do contrato.

**Como configurar a retenção automatizada baseada em eventos para este cenário:**

![Diagrama de funções e tarefas para o cenário de expiração de contrato](../media/automate-event-driven-retention-contract-expiration.png)

  - O administrador cria uma biblioteca do SharePoint com várias pastas para cada tipo de contrato.

  - O administrador adiciona arquivos de contrato, como Contratos de Licença e Contratos de Desenvolvimento, a cada pasta de contrato.

  - O administrador atribui uma ID de ativo à pasta de cada contrato.

  - O administrador do CCS entra no Centro de Conformidade e Segurança.

  - O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a contratos, como "Criação de Contrato" e "Expiração de Contrato".

  - O administrador do Centro de Conformidade e Segurança cria o rótulo "Expiração do Contrato".

  - O rótulo "Expiração de Contrato" é publicado e aplicado de forma automática ou manual aos arquivos de contratos no SharePoint.

  - O Sistema de Gerenciamento de Contratos pode trabalhar com o Microsoft Flow ou um aplicativo semelhante para realizar periodicamente o gerenciamento de arquivos de contratos.

  - Quando um contrato expira, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do contrato.

### <a name="scenario-3-end-of-product-manufacturing"></a>Cenário 3 – Término de fabricação de produto

A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.

Um sistema de ERP (Planejamento de Recursos Empresariais) pode trabalhar com o Microsoft 365 e o Microsoft Flow para disparar a retenção.

**Como configurar a retenção automatizada baseada em eventos para este cenário:**

![Diagrama de funções e tarefas para o cenário de ciclo de vida do produto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - O administrador cria pastas de produtos no Conjunto de documentos, como Produto 1, Produto 2 e assim por diante.

  - O administrador adiciona arquivos de produto, como Especificações de Fabricação, Preços de Produto e Licenciamento de Produto, a cada pasta de produto.

  - O administrador atribui uma ID de ativo à pasta de cada produto.

  - O administrador do CCS entra no Centro de Conformidade e Segurança.

  - O administrador do Centro de Conformidade e Segurança cria tipos de eventos relacionados a funcionários, como "Início de Fabricação de Produto" e "Término de Fabricação de Produto".

  - O administrador do Centro de Conformidade e Segurança cria o rótulo "Término de Fabricação de Produto".

  - O rótulo "Término de Fabricação de Produto" é publicado e aplicado de forma automática ou manual aos arquivos de produtos no SharePoint.

  - Os sistemas de ERP podem trabalhar com o Microsoft Flow ou com aplicativos semelhantes para realizar periodicamente o gerenciamento de arquivos de produtos.

  - Quando a fabricação de um produto é encerrada, o Microsoft Flow dispara a API REST de retenção baseada em eventos do Microsoft 365, que inicia o relógio de retenção nos arquivos específicos do produto.

## <a name="appendix"></a>Apêndice

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Como usar resultados de resposta de Redirecionamento 302 para chamar a API REST

1. Invoque uma chamada de evento de retenção de POSTAGEM usando a URL da API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (é necessário ter permissões do administrador global).

2. Verifique o código de resposta. Se for 302, obtenha a URL redirecionada da propriedade Local do cabeçalho da resposta.

3. Invoque a chamada de evento de retenção POST usando a URL redirecionada.

## <a name="credits"></a>Créditos

Este tópico foi revisado por:

Antonio Maio<br/>MVP de aplicativos e serviços do Microsoft Office<br/> Antonio.Maio@Protiviti.com
