---
title: Solicitações de entidades de dados do Dynamics 365 para o RGPD e CCPA
description: Aprenda como encontrar e agir sobre dados pessoais e responder a solicitações de DSR e CCPA feitas pelos clientes do Dynamics 365.
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817660"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de entidades de dados do Dynamics 365 para o RGPD e CCPA

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

Da mesma forma, a Lei de Privacidade do Consumidor da Califórnia (CCPA), fornece direitos e obrigações de privacidade aos consumidores da Califórnia, incluindo direitos semelhantes aos Direitos do Titular dos Dados do GDPR, como o direito de excluir, acessar e receber (portabilidade) suas informações pessoais.  O CCPA também fornece certas divulgações, proteções contra discriminação ao eleger direitos de exercício e requisitos de "aceitação/recusa" para determinadas transferências de dados classificadas como "vendas". As vendas são amplamente definidas para incluir o compartilhamento de dados para uma consideração valiosa. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

O guia explica como usar produtos, serviços e ferramentas administrativas da Microsoft para ajudar nossos clientes controladores a encontrarem e tomarem medidas em relação a dados pessoais para responder a solicitações de DSR. Especificamente, o guia mostra como localizar e acessar os dados pessoais ou informações pessoais que residem na nuvem da Microsoft e como executar ações relacionadas a eles. Aqui está uma rápida visão geral dos processos descritos neste guia:

- **Descobrir** – Use ferramentas de pesquisa e descoberta para localizar dados pessoais que possam ser a entidade de uma solicitação DSR. Após a coleta dos documentos que atendem à solicitação, você pode executar uma ou mais das ações de DSR a seguir para responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes da sua organização para responder às solicitações DSR.
- **Acesso:** recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.
- **Retificação:** faça alterações ou implemente outras ações solicitadas nos dados pessoais, onde for possível.
- **Restringir** Restrinja o processamento dos dados pessoais, removendo licenças de diversos serviços online ou desabilitando os serviços desejados, sempre que possível. Você pode
- **Excluir:** remova permanentemente os dados pessoais que residem na nuvem da Microsoft.
- **Exportar/Receber (Portabilidade): ** forneça uma cópia eletrônica (em formato legível para computador) de dados pessoais ou informações pessoais para o titular dos dados. Os dados pessoais do CCPA são quaisquer informações relacionadas a uma pessoa, identificável ou não. Não há distinção entre as funções pública, privada ou de trabalho de uma pessoa. O termo definido "informações pessoais" se alinha aproximadamente aos "dados pessoais" do RGPD. No entanto, o CCPA também inclui dados da família e do domicílio. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

Cada seção deste guia descreve os procedimentos técnicos que uma organização controladora de dados pode realizar para responder a uma solicitação de DSR para dados pessoais na nuvem da Microsoft

### <a name="gdpr-terminology"></a>Terminologia de RGPD

Veja a seguir as definições dos termos que são relevantes para este guia:

- **Controlador:** a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, onde tais fins e meios são determinados por lei da União ou Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou Estado-Membro.
- **Dados pessoais e titular dos dados:** qualquer informação relativa a uma pessoa natural identificada ou identificável (“titular dos dados”); uma pessoa natural identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou um ou mais fatores específicos de natureza física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa natural.
- **Processador:** uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.
- **Dados do cliente:** Todos os dados, incluindo todos os arquivos de texto, som, vídeo ou imagem e software, fornecidos à Microsoft por um cliente, em nome de um cliente ou por meio do uso do serviço corporativo. Os Dados do Cliente incluem (1) informações de identificação de usuários finais (por exemplo, nomes de usuário e informações de contato no Azure Active Directory) e Conteúdo do Cliente que um cliente carrega ou cria em serviços específicos (por exemplo, conteúdo do cliente em uma conta de Armazenamento do Azure, conteúdo do cliente de um Banco de Dados SQL do Azure ou imagem da máquina virtual de um cliente nas Máquinas Virtuais do Azure).
- **Logs gerados pelo sistema:** logs e dados relacionados gerados pela Microsoft que ajudam a Microsoft a fornecer serviços corporativos aos usuários. Os logs gerados pelo sistema contêm principalmente dados pseudonimizados, como identificadores exclusivos — normalmente, um número gerado pelo sistema que não pode, por si só, identificar uma pessoa individual, mas é usado para fornecer os serviços corporativos aos usuários. Os logs gerados pelo sistema também podem conter informações identificáveis sobre os usuários finais, como um nome de usuário.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Como este guia pode ajudar você a cumprir suas responsabilidades de controlador

O guia, dividido em duas partes, descreve como usar os produtos, serviços e ferramentas administrativas do Dynamics 365 para ajudar a localizar e executar ações em dados na nuvem da Microsoft em resposta a solicitações de titulares de dados exercendo seus direitos no RGPD. A primeira parte aborda dados pessoais incluídos nos dados do cliente, seguida por uma parte que aborda outros dados pessoais pseudonimizados obtidos de registros gerados pelo sistema.

- **Parte 1: Respondendo a solicitações de Direitos do Titular dos Dados (DSR) para Dados Pessoais incluídos nos dados do cliente:** A parte 1 deste guia aborda como acessar, corrigir, restringir, excluir e exportar dados pessoais a partir de aplicativos do Dynamics 365 (software como um serviço), que é processado como parte dos dados do cliente que você forneceu ao serviço online.
- **Parte 2: Responder a solicitações de direitos de assunto de dados para dados do Pseudonymized:** ao usar os serviços corporativos do Dynamics 365, a Microsoft gera algumas informações (mencionadas neste documento, como *logs gerados pelo sistema*) para fornecer o serviço, o que limita o espaço de uso deixado pelos usuários finais para identificar suas ações no sistema. Embora esses dados não possam ser atribuídos a uma entidade de dados específica sem o uso de informações adicionais, alguns deles podem ser considerados pessoais de acordo com o RGPD. A Parte 2 deste guia discute como acessar, excluir e exportar logs gerados pelo sistema produzidos pelo Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Preparar para investigações de direitos de entidades de dados

Quando titulares de dados exercem seus direitos e fazem solicitações, considere os seguintes pontos:

- Identifique adequadamente a pessoa e a função — como funcionário, cliente, fornecedor — usando as informações que o titular dos dados forneceu como parte da sua solicitação. Essas informações podem ser um nome, um ID de funcionário, um número de cliente ou outro identificador.
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- Verifique se tem as informações relacionadas à solicitação.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Parte 1: Respondendo a Solicitações de Direitos de Titulares de Dados para dados pessoais incluídos nos dados do cliente

In the articles below, you'll find information to help you prepare for and respond to DSR requests for personal data included in customer data processed in Dynamics 365. It is important to note that personal data could be present in other categories of data processed by Microsoft during the course of the service of an online services subscription, such as administrator data or support data defined in the Microsoft Privacy Statement. This document is limited to assist you in the process of discovery and management of DSR requests affecting personal data present in the customer data that you have provided to Dynamics 365.

Dynamics 365 is an online service that offers multiple data processing capabilities as a software-as-a-service (SaaS). As such, Dynamics 365 offers a broad array of functionality intended to process a diverse collection of data, which could vary by nature, purpose or other specific attributes, such as sales data, transactions, financials, HR information, etc. In light of this diversity, Dynamics 365 offers multiple forms, fields, schemas, end points, and logic to process customer data, which is also reflected in the multiple ways in which DSR requests could be addressed in each application. When Dynamics 365 applications offer several ways to address specific DSR requests, we will note those in this guide by pointing to the technical descriptions offered by each application.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Localizar os dados do cliente

A primeira etapa ao responder a uma solicitação de direitos de entidade de dados é procurar e identificar os dados do cliente que estão sendo solicitados.

Classifying customer data appropriately is the cornerstone of working with personal data in Dynamics 365 Customer Engagement business applications. Dynamics 365 for Customer Engagement offers flexibility to build out an application extension around data classification. Proper classification enables you to identify information as personal data, thereby making it possible to locate and retrieve it when responding to requests from a data subject. It can also help enable compliance with legislative and regulatory requirements for collecting and managing personal data.

Microsoft provides capabilities that assist you in responding to data subject rights requests, and thereby accessing customer data. However, it is your responsibility to ensure that personal data is located and classified appropriately.

O ***Dynamics 365 para o Customer Engagement*** fornece vários métodos para você procurar dados pessoais em registros como: Pesquisa Avançada de Pesquisa e Pesquisa de Registros. Todas essas funções permitem identificar (localizar) dados pessoais.

- [Pesquisa de Localização Avançada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Pesquisa por Registros](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) entre vários tipos de registro

No Dynamics 365 for Marketing, você tem os seguintes recursos adicionais:

1. [Criar relatórios do Power BI](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) para filtrar e identificar os dados do cliente.
2. Utilize os modos de exibição de informações em contatos e objetos de execução de marketing para identificar os pontos de dados adicionais que podem conter dados do cliente.

O ***Dynamics 365 Customer Service Insights*** fornece uma lista de recursos para ajudá-lo a [encontrar dados de clientes](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery) para responder às solicitações de RGPD dos clientes. 

O ***Dynamics 365 Finance and Operations*** oferece várias maneiras para você pesquisar por dados de clientes. Um administrador locatário pode executar as seguintes ações para pesquisar dados dos clientes:

- Para organizar os dados do cliente para agilizar a localização de dados pessoas, consulte [Como classificar o estoque de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).
- Use o [Relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para localizar e coletar dados pessoais.
- [Expanda o relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) criando uma nova entidade ou ampliando uma existente.
- Use os recursos de pesquisa e filtragem para localizar dados pessoas específicos e exportar dados usando o recurso de exportação do Microsoft Office ou imprima essas informações em PDF usando extensões do navegador.
- Crie um formulário personalizado que localize e exporte dados pessoais.
- Crie um portal ou site externo que permita que um cliente autenticado veja seus próprios dados pessoais.

O ***Dynamics 365 for Business Central*** oferece várias formas de pesquisar dados de clientes. Para saber mais, confira [Pesquisar, filtrar e classificar dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters).

***O Dynamics 365 for Talent*** fornece recursos avançados de pesquisa e filtragem para localizar dados pessoais específicos e o recurso de exportação do Microsoft Office para exportar ou imprimir essas informações em PDF usando extensões do navegador.

- Use o [Relatório de pesquisa de pessoas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para localizar e coletar dados do cliente.
- [Expanda o relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) criando uma nova entidade ou ampliando uma existente.

### <a name="providing-a-copy-of-customer-data"></a>Fornecer uma cópia dos dados do cliente

Dados do cliente no ***Dynamics 365 for Customer Engagement*** podem ser exportados usando os recursos abrangentes de exportação de entidade. Dados do cliente podem ser exportados para um arquivo estático do Excel para facilitar uma solicitação de portabilidade de dados. Usando o Excel, você pode editar os dados pessoais a serem incluídos na solicitação de portabilidade e depois salvar como um formato comum legível por máquina, como .csv ou .xml. O Dynamics 365 para registros de envolvimento do cliente também pode ser exportado por meio da [API da Web do serviço de dados comuns](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview).

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

O ***Dynamics 365 Customer Service*** permite que você [forneça uma cópia dos dados de cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) usando a exportação de dados.

Dados do cliente no ***Dynamics 365 for Finance and Operations*** podem ser exportados usando os recursos abrangentes de exportação de entidade. Usando as [*entidades de integração e de gerenciamento de dados*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), o administrador locatário pode utilizar entidades fornecidas, criar novas ou estender entidades existentes para exportação de dados pessoais repetidos para o Excel ou outros formatos comuns usando [*importar e exportar trabalhos de dados*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Dados do cliente podem ser exportados para um arquivo estático do Excel para facilitar a solicitação de portabilidade de dados. Ao exportar dados do cliente para o Excel, você pode editar os dados pessoais a serem incluídos na solicitação de portabilidade e depois salvar como um formato comum legível por máquina, como .csv ou .xml. Você também pode usar o *Relatório de Pesquisa de Pessoas* para fornecer o titular com os dados que você classificou como dados pessoais.

No ***Dynamics 365 Business Central***, você pode usar dois recursos para fornecer uma cópia dos dados do cliente para um titular de dados:

Você pode exportar dados do cliente para um arquivo do Excel. No Excel, você pode editar os dados do cliente a serem incluídos na solicitação de portabilidade, e depois salvar como um formato comum legível por máquina, como .csv ou .xml. Para saber mais, confira [exportar dados corporativos para o Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)

No ***Dynamics 365 for Talent***, você pode [estender o relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) para coletar informações para oferecer suporte a uma solicitação de uma cópia de dados pessoais do titular de dados.

### <a name="rectifying-customer-data"></a>Corrigir os dados do cliente

O ***Dynamics 365 for Customer Engagement*** fornece os seguintes métodos para corrigir dados imprecisos ou incompletos do cliente ou apagar dados do cliente:

- Pesquise dados do cliente usando os recursos mencionados em "Localizando dados do cliente" e edite diretamente os dados nos Formulários de envolvimento do cliente. Um nível de linha única ou várias linhas poderão ser editadas diretamente.
- Para editar vários registros de Customer Engagement ao mesmo tempo, você pode utilizar o suplemento do Microsoft Office para exportar dados para o Excel, fazer suas alterações e importar os dados modificados do Excel para o Dynamics 365 for Customer Engagement.

Além disso, para o Dynamics 365 for Marketing, você também pode:

- Atualizar a página de chegada dos dados editando uma ou várias linhas diretamente
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

O ***Dynamics 365 Customer Service Insights*** também fornece recursos que permitem [correção ou alterações nos dados do cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary) pelas organizações.

No ***Dynamics 365 for Finance and Operations***, você também pode usar as [*ferramentas de personalização*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), mas a implementação e a decisão estão sob sua responsabilidade.

O ***Dynamics 365 Business Central*** oferece duas maneiras de corrigir dados imprecisos ou incompletos do cliente.

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

Você pode alterar dados do cliente armazenados em qualquer campo, como as informações do cliente no cartão do cliente — ao editar manualmente o elemento de dados com os dados pessoais de destino. Para saber mais, confira [inserir dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Nota curta sobre como modificar entradas em transações de negócios

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>Restrição do processamento de dados do cliente

Ao receber uma solicitação de um titular de dados para restringir o processamento de dados do cliente, você pode extrair facilmente os dados afetados do serviço online e armazená-los em um contêiner separado (ou seja, um armazenamento local ou em um serviço Web separado com recursos de isolamento de dados) isolado das funções de processamento fornecidas por qualquer aplicativo da nuvem.

O mecanismo alternativo, como o bloco de processamento de dados, é oferecido pelo ***Dynamics 365 Business Central***, em que os usuários podem bloquear o registro de assunto de dados específico. Para saber mais, confira [Restrição de processamento de dados para um titular de dados](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Quando um registro for bloqueado, o Dynamics 365 Business Central irá interromper o processamento de dados do cliente daquele titular de dados. Não é possível criar novas transações que usam um registro bloqueado como, por exemplo, uma nova fatura para um cliente, se o cliente ou vendedor estiver bloqueado.

### <a name="deleting-customer-data"></a>Exclusão de dados do cliente

Quando um titular de dados solicita a exclusão de seus dados do cliente, há várias maneiras de fazer isso:

- Para editar vários registros do Dynamics 365 em massa, você pode utilizar o suplemento do Microsoft Office para exportar dados para o Excel, fazer suas alterações e importar os dados modificados do Excel para o serviço online.
- Você pode excluir os dados do cliente armazenados em qualquer campo ao localizar os dados que deseja excluir e, em seguida, excluir manualmente o elemento de dados com os dados do cliente-alvo, por exemplo, realizando uma exclusão permanente do registro de contato que representa o titular de dados e outros registros que contêm dados pessoais

Além disso, para o Dynamics 365 Marketing, a exclusão de um contato irá garantir que a interação de dados com as informações pessoais também serão removidas. Para quaisquer entidades ou campos personalizados, personalizar o seu sistema garante que ele exclui todos os dados do cliente dos registros relacionados e/ou desvinculá-los do registro de contato para que todas as informações pessoais sejam removidas. Saiba mais: [Guia do Desenvolvedor (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

O ***Dynamics 365 Customer Service Insights*** também fornece às organizações recursos para [excluir dados do cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

Como alternativa, no ***Dynamics 365 for Finance and Operations***, você pode usar [*ferramentas de personalização*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) para excluir/modificar dados do cliente.

No ***Dynamics 365 Business Central***, quando um titular de dados solicitar que você exclua seus dados pessoais incluídos nos dados do cliente, há várias maneiras para atender a essa solicitação:

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Você pode excluir dados do cliente armazenados em qualquer campo excluindo manualmente o elemento de dados que contém os dados do cliente-alvo. Para saber mais, confira [inserir dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Você pode excluir diretamente os dados do cliente, por exemplo, ao excluir um contato e executar o trabalho em lote Excluir Entradas do Log de Interações Canceladas para excluir as interações para esse contato.
- Você pode [excluir documentos](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) com dados do cliente como, por exemplo, memorandos, vendas lançadas e faturas de compra.

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportação de dados do cliente

Para atender a uma solicitação de portabilidade de dados, os dados do cliente no ***Dynamics 365 for Customer Engagement*** podem ser exportados usando os recursos abrangentes de exportação de entidade. Dados do cliente podem ser exportados para um arquivo estático do Excel para facilitar uma solicitação de portabilidade de dados. Usando o Excel, você pode editar os dados pessoais a serem incluídos na solicitação de portabilidade e depois salvar como um formato comum legível por máquina, como .csv ou .xml.

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

Para ***Dynamics 365 Customer Service Insights***, você [exporta dados do cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) por meio do portal de gerenciamento do Azure.

O ***Dynamics 365 for Finance and Operations*** fornece [entidades de integração e de gerenciamento de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), habilitando entidades fornecidas ou estendidas para exportação de dados pessoais repetidos para o Excel ou outros formatos comuns usando [Importar e exportar trabalhos de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Dados do cliente podem ser exportados para um arquivo estático do Excel para facilitar a solicitação de portabilidade de dados. Ao exportar dados do cliente para o Excel dessa forma, você pode editar os dados pessoais a serem incluídos na solicitação de portabilidade e depois salvar como um formato comum legível por máquina, como .csv ou .xml.

Tanto o Dynamics 365 for Finance and Operations quanto o ***Dynamics 365 for Talent*** oferecem o Relatório de pesquisa de pessoa para fornecer ao titular os dados que você tenha classificado como pessoais. 

O ***Dynamics 365 Business Central*** oferece os seguintes recursos:

- Você pode exportar dados do cliente para um arquivo do Excel. No Excel, você pode editar os dados do cliente a serem incluídos na solicitação de portabilidade, e depois salvar como um formato comum legível por máquina, como .csv ou .xml. Para saber mais, confira [exportar dados corporativos para o Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Você pode exportar dados do cliente para um arquivo do Excel. No Excel, você pode editar os dados do cliente a serem incluídos na solicitação de portabilidade, e depois salvar como um formato comum legível por máquina, como .csv ou .xml. Para saber mais, confira [exportar dados corporativos para o Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: Responder aos DSRs para logs gerados pelo sistema

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- Dados de uso de produtos e serviços, como os log de atividades do usuário
- Dados de solicitações e consultas de pesquisa do usuário
- Dados gerados por produtos e serviços como resultado da funcionalidade do sistema e da interação de usuários ou de outros sistemas

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acessar e exportar logs gerados pelo sistema

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. Acesse o [Portal de Confiança do Serviço da Microsoft](https://servicetrust.microsoft.com/) e entre usando as credenciais de um administrador global do Dynamics 365.
2. Na lista suspensa **Privacidade** localizada na parte superior da página, clique em **Solicitação de Titular dos Dados**.
3. Na página **Solicitação de Titular dos Dados**, em **Logs Gerados pelo Sistema**, clique em **Exportação de Log de Dados**.
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. Para criar uma nova solicitação para um usuário, clique em **Criar Solicitação de Exportação de Dados**.

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

O Azure possibilita que sua organização exporte os dados no formato JSON nativo para um Contêiner de Armazenamento do Azure especificado[. Artigo Introdução ao Armazenamento do Microsoft Azure — Armazenamento de blobs](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage). Os dados recuperados não incluirão dados que possam comprometer a segurança e a estabilidade do serviço.

> [!IMPORTANT]
> Você deve ser um administrador de locatários para exportar dados de usuário do locatário.

A tabela a seguir resume como acessar e exportar os logs gerados pelo sistema:

| | |
|:----|:---|
| | |
|**Quanto tempo a ferramenta de Exportação de Log de Dados da Microsoft leva para concluir uma solicitação?**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**Qual será o formato da saída?**| A saída será em arquivos estruturados legíveis por máquina, como JSON, CSV ou XML. |
|**Quais são os dados retornados pela ferramenta Exportação de Log de Dados?**| A ferramenta Exportação de Log de Dados retorna logs gerados pelo sistema que a Microsoft armazena. Os dados exportados serão distribuídos em vários serviços da Microsoft, incluindo o Office 365, o Azure e o Dynamics. |
|***Quem tem acesso à ferramenta de Exportação de Log de Dados para enviar solicitações de acesso para logs gerados pelo sistema?**| Os administradores globais do Dynamics 365 terão acesso ao utilitário de Gerenciamento de Logs do RGPD. |
|**Como os dados são retornados ao usuário?**| Os dados serão exportados para o local de armazenamento do Azure da sua organização. Caberá aos administradores da sua organização determinar como eles mostrarão/retornarão esses dados para os usuários. |
|**Qual será a aparência dos dados nos logs gerados pelo sistema?**| Exemplo de um registro de log gerado pelo sistema no formato JSON: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>Excluir os logs gerados pelo sistema

Para excluir logs gerados pelo sistema recuperados por meio de uma solicitação de acesso, você deve remover o usuário do serviço e excluir permanentemente a conta do Azure Active Directory. Para obter instruções sobre como excluir permanentemente um usuário, confira a seção [Etapa 5: Excluir](gdpr-dsr-azure.md#step-5-delete) no tópico Solicitações do Titular dos Dados do Azure. É importante observar que, após iniciar a exclusão permanente de uma conta de usuário, esta ação será irreversível. Excluir permanentemente uma conta de usuário remove os dados do usuário dos logs gerados pelo sistema, exceto dados que possam comprometer a segurança ou estabilidade do serviço, para quase todos os serviços do Dynamics 365 em 30 dias.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
