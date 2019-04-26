---
title: Solicitações de Titulares de Dados do Dynamics 365 para o RGPD
description: Guia sobre como usar produtos, serviços e ferramentas administrativas da Microsoft para ajudar nossos clientes controladores a encontrarem e tomarem medidas em relação a dados pessoais para responder a solicitações de DSR.
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/10/2019
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: f5a7f347dc9b26b54cf6bc1fd3a6bdb55d46fe63
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285210"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr"></a>Solicitações de Titulares de Dados do Dynamics 365 para o RGPD

O RGPD (Regulamento sobre a Proteção de Dados) da UE fornece direitos às pessoas (conhecidas na regulamentação como *titulares de dados*) para gerenciar os dados pessoais que foram coletados por um funcionário ou outro tipo de órgão ou organização (conhecido como *controlador de dados* ou apenas *controlador*). Os dados pessoais são definidos amplamente no RGPD como quaisquer dados relacionados a uma pessoa identificada ou identificável. O RGPD fornece a titulares de dados direitos específicos a seus dados pessoais; esses direitos incluem a obtenção de cópias, a solicitação de alterações, a restrição do processamento, a exclusão ou seu recebimento em formato eletrônico para que possam ser migrados para outro controlador. Uma solicitação formal por um titular de dados a um controlador para realizar uma ação quanto a seus dados pessoais é chamada de *Solicitação de Direitos de Titular de Dados* ou DSR.<span id="_Toc510437912" class="anchor"><span id="_Toc508792504" class="anchor"></span></span>

O guia aborda como usar os produtos, os serviços e as ferramentas administrativas da Microsoft, de modo que ajudem nossos clientes controladores a encontrar dados pessoais e agir em relação a eles ao responder a solicitações de DSR. Especificamente, isso inclui como encontrar, acessar e agir sobre dados pessoais que residem na nuvem da Microsoft. Veja aqui uma breve visão geral dos processos descritos neste guia:

1. ***Descobrir***: use as ferramentas de pesquisa e descoberta para encontrar mais facilmente dados do clientes que possam ser o titular de uma solicitação de DSR. Depois que os documentos potencialmente responsivos são coletados, você pode executar uma ou mais ações de DSR descritas nas etapas a seguir para responder à solicitação de DSR. Se preferir, pode determinar que a solicitação não atende às diretrizes das suas organizações para responder às solicitações de DSR.

2. ***Acessar***: recupere os dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.

3. ***Retificar*** – faça alterações ou implemente outras ações solicitadas nos dados pessoais, onde for possível.

4.  ***Restringir*** — restrinja o processamento dos dados pessoais, seja removendo as licenças de vários serviços online ou desativando os serviços desejados, quando possível. Você também pode remover dados da nuvem da Microsoft e mantê-los no local ou onde preferir.

5. ***Excluir***: remova permanentemente os dados pessoais que residem na nuvem da Microsoft.

6. ***Exportar***: forneça uma cópia eletrônica (em um formato legível por máquina) dos dados pessoais para o titular dos dados.

Cada seção deste guia descreve os procedimentos técnicos que uma organização controladora de dados pode realizar para responder a uma solicitação de DSR para dados pessoais na nuvem da Microsoft

### <a name="gdpr-terminology"></a>Terminologia de RGPD

Veja a seguir as definições dos termos que são relevantes para este guia:

- <em>Controlador</em>: a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, em que tais fins e meios são determinados por lei da União ou do Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou do Estado-Membro.

- *Dados pessoais* e <em>titular dos dados</em>: quaisquer informações relacionadas a uma pessoa física identificada ou identificável ("titular dos dados"); uma pessoa física identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou por um ou mais fatores específicos à identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física.

- <em>Processador</em>: uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.

- *Dados do cliente*: todos os dados, incluindo texto, som, vídeo ou arquivos de imagem e software que são fornecidos para a Microsoft por ou em nome de um cliente por meio do uso do serviço empresarial, conforme é definido nos Termos de Serviços Online da Microsoft.

- *Sistema*-*Logs gerados pelo sistema*: logs e dados relacionados gerados pela Microsoft que nos ajudam a fornecer os serviços empresariais aos usuários. Logs gerados pelo sistema contêm principalmente dados com pseudônimos, como identificadores exclusivos, normalmente um número gerado pelo sistema que não pode, sozinho, identificar um indivíduo, mas que é usado para fornecer serviços empresariais aos usuários. Logs gerados pelo sistema também podem conter informações de identificação dos usuários finais, como nomes de usuário.  

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Como este guia pode ajudar você a cumprir suas responsabilidades de controlador

Este guia, dividido em duas partes, descreve como usar os produtos, serviços e ferramentas administrativas do Dynamics 365 para ajudar a encontrar e tomar medidas sobre os dados na nuvem da Microsoft em resposta a solicitações de titulares dados que exercem seus direitos de acordo com o RGPD. A primeira parte aborda os dados pessoais incluídos nos Dados do cliente, seguido por uma parte que aborda outros dados pessoais com pseudônimos capturados em logs gerados pelo sistema.

**Parte 1: responder a Solicitações de Direitos de Titulares de Dados (DSR) para dados pessoais incluídos nos Dados do cliente.** A parte 1 deste guia descreve como acessar, corrigir, restringir, excluir e exportar dados pessoais de aplicativos do Dynamics 365 (software como um serviço), que são processados como parte dos Dados do cliente que você forneceu ao serviço online.

**Parte 2: responder a Solicitações de Direitos de Titulares de Dados para dados com pseudônimos.** Quando você usa os serviços empresariais do Dynamics 365, a Microsoft gera informações (neste documento, chamadas de *logs gerados pelo sistema*) para fornecer o serviço, que é limitado ao volume de uso deixado pelos usuários finais para identificar suas ações no sistema. Embora esses dados não possam ser atribuídos a um titular de dados específico sem o uso de informações adicionais, alguns deles podem ser considerados pessoais no RGPD. A parte 2 deste guia descreve como acessar, excluir e exportar logs gerados pelo sistema produzidos pelo Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Preparar para investigações de direitos de entidades de dados

Quando titulares de dados exercem seus direitos e fazem solicitações, considere os seguintes pontos:

- Identifique corretamente a pessoa e sua função, como funcionário, cliente, fornecedor, ao usar as informações que o titular dos dados forneceu a você como parte da solicitação. Essas informações podem ser um nome, um número de cliente ou ID do funcionário ou outro identificador.

- Grave os dados e a hora da solicitação. (Você terá 30 dias para concluir a solicitação).

- Informe se a solicitação atende aos requisitos de sua organização para atender ou recusar a solicitação de um titular de dados. Por exemplo, você deve garantir que atender à solicitação não criará um conflito com qualquer outra obrigação jurídica, financeira ou regulamentar que você tenha e que não infringirá os direitos e liberdades de terceiros.

- Verifique se tem as informações relacionadas à solicitação.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-includced-in-customer-data"></a>Parte 1: Responder a solicitações de direitos de entidade de dados para dados pessoais incluídos nos dados do cliente

Nos artigos a seguir, você encontrará informações para ajudá-lo a preparar e responder a solicitações de DSR para dados pessoais incluídos nos Dados do cliente processados no Dynamics 365. É importante observar que dados pessoais podem estar presentes em outras categorias de dados processados pela Microsoft durante o período de serviço de uma assinatura de serviços online, como dados de administrador ou dados de suporte definidos na Política de Privacidade da Microsoft. Este documento é limitado a ajudá-lo no processo de descoberta e gerenciamento de solicitações de DSR que afetam os dados pessoais presentes nos Dados do cliente que você forneceu ao Dynamics 365.

O Dynamics 365 é um serviço online que oferece vários recursos de processamento de dados como um software como serviço (SaaS). Dessa forma, o Dynamics 365 oferece uma ampla variedade de recursos para processar diversos tipos de dados, que podem variar de acordo com sua natureza, finalidade ou outros atributos específicos, como dados de vendas, de transações, financeiros, informações de RH etc. Devido a essa diversidade, o Dynamics 365 oferece vários formulários, campos, esquemas, pontos de extremidade e lógicas para processar Dados do cliente, o que também se reflete nas várias maneiras com as quais as solicitações de DSR podem ser resolvidas em cada aplicativo. Como os aplicativos do Dynamics 365 oferecem várias maneiras para atender a solicitações de DSR específicas, elas serão indicadas neste guia, apontando para as descrições técnicas fornecidas por cada aplicativo.

### <a name="dynamics-365"></a>Dynamics 365
#### <a name="finding-customer-data"></a>Localizar os dados do cliente

A primeira etapa para responder a uma solicitação de direitos de titular de dados é procurar e identificar os Dados do cliente que estão sendo solicitados.

A classificação correta dos Dados do cliente é a base para trabalhar com dados pessoais no Microsoft Dynamics 365 Customer Engagement. O Dynamics 365 for Customer Engagement oferece flexibilidade para criar uma extensão de aplicativo de acordo com a classificação dos dados. A classificação adequada permite identificar informações como dados pessoais, tornando possível localizar e recuperar essas informações ao responder a solicitações de um titular de dados. Ela também pode ajudar a possibilitar o cumprimento de requisitos legais e regulamentares para coleta e gerenciamento de dados pessoais.

A Microsoft fornece recursos que podem ajudá-lo a responder a solicitações de direitos de titular de dados e, assim, acessar os Dados do cliente. No entanto, é sua responsabilidade garantir que os dados pessoais sejam localizados e classificados adequadamente.

<span id="_Toc511225657" class="anchor"></span>***O Dynamics 365 for Customer Engagement*** fornece vários métodos para pesquisar dados pessoais em registros, como: Pesquisa de Localização Avançada, Pesquisa por Relevância e Pesquisa por Registros. Todas essas funções permitem identificar (localizar) dados pessoais.

-   [Pesquisa de Localização Avançada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)

-   [Pesquisa de Relevância](https://docs.microsoft.com/dynamics365/customer-engagement/basics/relevance-search-results), que pode ser salva para referência futura usando os painéis

-   [Pesquisa por Registros](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) entre vários tipos de registro

No Dynamics 365 for Marketing, você tem os seguintes recursos adicionais:

1.  [Criar relatórios do Power BI](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) para filtrar e identificar os dados do cliente.

2.  Utilize os modos de exibição de informações em contatos e objetos de execução de marketing para identificar os pontos de dados adicionais que podem conter dados do cliente.

Insights do Atendimento ao Cliente do Dynamics 365 fornece recursos para você responder a solicitações de cópias de dados pessoais, para apagar dados pessoais e para encontrar os dados pessoas que são a entidade das Solicitações de Descoberta de Entidades de Dados (DSRs). Para saber mais, confira [Visão geral da conformidade com RGPD para Insights do Atendimento ao Cliente do Dynamics 365 ](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary).

<span id="_Toc511225658" class="anchor"></span>***O Dynamics 365 Finance and Operations*** oferece várias maneiras de pesquisar Dados do cliente. Como um Administrador de Locatários, você pode realizar as seguintes ações para pesquisar Dados do cliente:

-   Para organizar os Dados do cliente de forma que atenda ao objetivo de descobrir dados pessoas de forma rápida, consulte [Como classificar o inventário de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).

-   Use o [Relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para localizar e coletar dados pessoais.

-   [Expanda o relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) criando uma nova entidade ou ampliando uma existente.

-   Use os recursos de pesquisa e filtragem para localizar dados pessoas específicos e exportar dados usando o recurso de exportação do Microsoft Office ou imprima essas informações em PDF usando extensões do navegador.

-   Crie um formulário personalizado que localize e exporte dados pessoais.

-   Crie um portal ou site externo que permita que um cliente autenticado veja seus próprios dados pessoais.


***Dynamics para Business Central*** oferece várias maneiras de pesquisar Dados de Clientes. Para saber mais, confira [Pesquisa, filtragem e classificação de dados](https://docs.microsoft.com/dynamics-nav-app/ui-enter-criteria-filters).

<span id="_Toc511225660" class="anchor"></span>***O Dynamics 365 for Talent*** fornece recursos avançados de pesquisa e filtragem para localizar dados pessoais específicos e o recurso de exportação do Microsoft Office para exportar ou imprimir essas informações em PDF usando extensões do navegador.

-   Use o [Relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) para localizar e coletar Dados do cliente.

-   [Expanda o relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) criando uma nova entidade ou ampliando uma existente.

### <a name="providing-a-copy-of-customer-data"></a>Fornecer uma cópia dos dados do cliente

Dados do cliente no ***Dynamics 365 for Customer Engagement*** podem ser exportados usando os recursos abrangentes de exportação de entidades. Dados do cliente podem ser exportados para um arquivo do Excel estático para facilitar uma solicitação de portabilidade de dados. Usando o Excel, você poderá editar os dados pessoais a serem incluídos na solicitação de portabilidade e salvar como um formato legível por máquina comum, como .csv ou .xml.

Além disso, para o Dynamics 365 for Marketing, é fornecida uma [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) para criar extensões que recuperem registros adicionais de interações de clientes capturadas, que podem conter dados pessoais do cliente. A API carrega as informações relevantes do sistema de back-end e as reúne em um único documento portátil.

Dados do cliente no ***Dynamics 365 for Finance and Operations*** podem ser exportados usando os recursos abrangentes de exportação de entidades. Usando as [*entidades de integração e de gerenciamento de dados*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), o administrador de locatários pode utilizar entidades fornecidas, criar novas ou estender entidades existente para uma exportação de dados pessoais repetível do Excel ou para vários outros formatos comuns usando [*tarefas de importação e exportação de dados*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Como alternativa, é possível exportar muitas listas para um arquivo do Excel estático para facilitar uma solicitação de portabilidade de dados. Quando os dados do cliente forem exportados para o Excel, você poderá editar os dados pessoais a serem incluídos na solicitação de portabilidade e salvar o arquivo como um formato legível por máquina comum, como .csv ou .xml. Você também pode considerar usar o *Relatório de pesquisa de pessoa * para fornecer ao titular os dados que você classificou como dados pessoais. 

No ***Dynamics 365 Business Central***, você pode usar dois recursos para fornecer uma cópia dos Dados do cliente para um titular de dados:

Você pode exportar Dados do cliente para um arquivo do Excel. No Excel, você pode editar os Dados do cliente incluídos na solicitação de portabilidade e salvá-los em um formato legível por máquina comum, como .csv ou .xml. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/pt-BR/dynamics365/business-central/about-export-data).

No ***Dynamics 365 for Talent***, você pode [estender o relatório de pesquisa de pessoa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) para coletar informações para oferecer suporte a uma solicitação de uma cópia de dados pessoais do titular de dados.

### <a name="rectifying-customer-data"></a>Corrigir os dados do cliente

<span id="_Toc511225663" class="anchor"></span>***O Dynamics 365 for Customer Engagement*** oferece os seguintes métodos para corrigir dados imprecisos ou incompletos de clientes ou para excluir dados do clientes:

-   Pesquise os Dados do cliente usando os recursos mencionados em "Localizar dados do cliente" e edite os dados diretamente nos Formulários de Customer Engagement. Você pode fazer edições em uma linha ou em várias.

-   Para editar vários registros de Customer Engagement ao mesmo tempo, você pode utilizar o suplemento do Microsoft Office para exportar dados para o Excel, fazer suas alterações e importar os dados modificados do Excel para o Dynamics 365 for Customer Engagement.

Além disso, para o Dynamics 365 for Marketing, você também pode:

-   Atualizar a página de chegada dos dados editando uma ou várias linhas diretamente

-   Preparar uma página de [centros de assinatura](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) que contém quantos campos de contato editáveis puderem ser incluídos. Isso permite que um usuário final atualize suas próprias informações na medida do possível.

No ***Dynamics 365 for Finance and Operations***, você também pode usar as [ *ferramentas de personalização*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), mas a implementação e a decisão é responsabilidade sua.

<span id="_Toc511225664" class="anchor"></span>***O Dynamics 365 Business Central*** oferece duas maneiras de corrigir Dados do cliente incorretos ou incompletos.

Para editar em massa vários registros do Business Central, você pode exportar listas para o Excel usando o [suplemento para Excel do Business Central](https://docs.microsoft.com/pt-BR/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para corrigir vários registros e publicar os dados modificados do Excel no Business Central. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/pt-BR/dynamics365/business-central/about-export-data).

- Você pode alterar Dados do cliente armazenados em qualquer campo, como as informações do cliente no cartão Cliente, ao editar manualmente o elemento de dados que contém os dados pessoais de destino. Para saber mais, consulte [Inserir dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Nota curta sobre como modificar entradas em transações de negócios
Registros transacionais, como entradas contábeis gerais, do cliente e tributárias, são essenciais para a integridade de um sistema de planejamento de recursos empresariais. Dados pessoais que fazem parte de uma transação financeira ou de outro tipo são mantidos “no estado em que se encontram” para cumprir as leis financeiras (por exemplo, leis tributárias), impedir fraudes (como uma trilha de auditoria de segurança ou para estar em conformidade com as certificações do setor). Dessa forma, o Dynamics 365 for Finance and Operations e o Dynamics 365 Business Central restringem a modificação dos dados nesses registros.

Se você armazena dados pessoais em registros de transações empresariais, a única maneira de corrigir, excluir ou restringir o processamento de dados pessoais para atender à solicitação de um titular de dados é usar os [recursos de personalização](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index) do Dynamics 365 Business Central. [](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)A decisão de atender à solicitação de modificação de um titular de dados e sua implementação é responsabilidade sua.

### <a name="restricting-the-processing-of-customer-data"></a>Restrição de processamento de Dados de Clientes

Quando receber uma solicitação de um titular de dados para restringir o processamento de Dados do cliente, você pode facilmente extrair os dados afetados do serviço online e armazená-los em um contêiner separado (ou seja, um armazenamento local ou em um serviço Web separado com recursos de isolamento de dados) isolado das funções de processamento fornecidas por qualquer aplicativo de nuvem.

Um mecanismo alternativo para o bloqueio de processamento de dados é oferecido pelo ***Dynamics 365 Business Central***, no qual os usuários são oferecidos a capacidade de bloquear o registro específico do titular de dados. Para saber mais, consulte [Restringir o processamento de dados para um titular de dados](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Quando um registro é marcado como bloqueado, o Dynamics 365 Business Central deixará de processar os Dados do cliente desse titular de dados. Não será possível criar novas transações que usem um registro bloqueado; por exemplo, não será possível criar uma nova fatura para um cliente, quando o cliente ou vendedor em questão estiver bloqueado.

### <a name="deleting-customer-data"></a>Exclusão de dados do cliente

Quando um titular de dados solicita a exclusão de seus Dados do cliente, há várias maneiras de fazer isso:

-   Para editar vários registros do Dynamics 365 em massa, você pode utilizar o suplemento do Microsoft Office para exportar dados para o Excel, fazer suas alterações e importar os dados modificados do Excel para o serviço online.

-   Você pode excluir Dados do cliente armazenados em qualquer campo ao localizar os dados que deseja excluir e, em seguida, excluir manualmente o elemento de dados que contém os dados do clientes de destino, por exemplo, realizando uma exclusão permanente do registro de contato que representa o titular de dados e outros registros que contêm dados pessoais

Além disso, para o Dynamics 365 for Marketing, a exclusão de um contato garantirá que os dados de interação com informações pessoais também sejam removidos. Para quaisquer campos ou entidades personalizados, você deve personalizar o seu sistema para garantir que ele exclua todos os Dados do cliente dos registros relacionados e/ou desvincule-os do registro de contato para que todas as informações pessoais sejam removidas. Saiba mais: [Guia do Desenvolvedor (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

Como alternativa, no ***Dynamics 365 for Finance and Operations***, você pode usar [*ferramentas de personalização*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) para apagar/modificar Dados do cliente.

No ***Dynamics 365 Business Central***, quando um titular de dados solicitar que você exclua seus dados pessoais que estejam incluídos em Dados do cliente, há várias maneiras para atender a essa solicitação:

-   Para editar em massa vários registros do Business Central, você pode exportar dados para o Excel usando o [suplemento para Excel do Business Central](https://docs.microsoft.com/pt-BR/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para excluir vários registros e publicar essas mudanças do Excel para o Business Central. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/pt-BR/dynamics365/business-central/about-export-data).

-   Você pode excluir Dados do cliente armazenados em qualquer campo excluindo manualmente o elemento de dados que contém os Dados do cliente de destino. Para saber mais, consulte [Inserir dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

-   Você pode excluir diretamente os Dados do cliente, por exemplo, ao excluir um contato e executar a tarefa em massa Excluir Entradas de Log de Interações Canceladas para excluir as interações para esse contato.

-   Você pode [excluir documentos](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) com Dados do cliente, por exemplo, memorandos, vendas postadas e faturas de compra.

Além da exclusão individual ou em massa de registros discretos, observe que apenas funcionários desligados da organização podem ser totalmente excluídos do ***Dynamics 365 for Talent***. [Siga estas etapas para excluir funcionários desligados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportação de dados do cliente

Para responder a uma solicitação de portabilidade de dados, Dados do cliente no ***Dynamics 365 for Customer Engagement*** podem ser exportados usando os recursos abrangentes de exportação de entidades. Os Dados do cliente podem ser exportados para um arquivo do Excel estático para facilitar uma solicitação de portabilidade de dados. Usando o Excel, você pode editar os dados pessoais a incluir na solicitação de portabilidade e salvar como um formato legível por máquina comum, como .csv ou .xml.

Além disso, para o Dynamics 365 for Marketing, é fornecida uma [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) para criar extensões que recuperam registros adicionais de interações de clientes capturadas, que podem conter dados pessoais do cliente. A API carrega as informações relevantes do sistema de back-end e as reúne em um único documento portátil.

<span id="_Toc511225669" class="anchor"></span>***O Dynamics 365 for Finance and Operations*** oferece [entidades de integração e de gerenciamento de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), que possibilitam a entidades fornecidas, entidades criadas recentemente ou entidades estendidas uma exportação de dados pessoais repetível no Excel ou em vários outros formatos comuns usando [tarefas de importação e exportação de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job). Como alternativa, é possível exportar muitas listas para um arquivo do Excel estático para facilitar uma solicitação de portabilidade de dados. Quando os Dados do cliente forem exportados para o Excel dessa forma, você poderá editar os dados pessoais a serem incluídos na solicitação de portabilidade e salvar o arquivo como um formato legível por máquina comum, como .csv ou .xml.

Tanto o Dynamics 365 for Finance and Operations quanto o ***Dynamics 365 for Talent*** oferecem o Relatório de pesquisa de pessoa para fornecer ao titular os dados que você tenha classificado como pessoais. 

- <span id="_Toc511225670" class="anchor"></span>***O Dynamics 365 Business Central*** oferece os seguintes recursos:

- Você pode exportar Dados do cliente para um arquivo do Excel. No Excel, você pode editar os Dados do cliente incluídos na solicitação de portabilidade e salvá-los em um formato legível por máquina comum, como .csv ou .xml. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/dynamics-nav-app/about-export-data).

Você pode exportar Dados do cliente para um arquivo do Excel. No Excel, você pode editar os Dados do cliente incluídos na solicitação de portabilidade e salvá-los em um formato legível por máquina comum, como .csv ou .xml. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/pt-BR/dynamics365/business-central/about-export-data).

### <a name="microsoft-social-engagement"></a>Microsoft Social Engagement

<span id="_Toc511166412" class="anchor"></span>Como o Microsoft Social Engagement processa dados pessoais que podem ser encontrados em Dados do cliente e em Conteúdo social, esse aplicativo oferece uma maneira exclusiva de atender a solicitações de DSR relacionadas a dados pessoais recuperados de redes sociais. O Conteúdo social é um conteúdo publicamente disponível coletado de redes sociais (como Twitter, Facebook e YouTube) e a indexação de dados ou os serviços de agregação de dados em resposta a consultas de pesquisa do cliente executadas no Microsoft Social Engagement. Conteúdo social não é Dados do cliente. Outras restrições de processamento, uso e armazenamento de Conteúdo social são descritas nos Termos de Serviço Online da Microsoft.

### <a name="finding-personal-data"></a>Localizar dados pessoais

A primeira etapa para responder à solicitação de um titular de dados é pesquisar e identificar os dados pessoais que são o objeto dessa solicitação. O Microsoft Social Engagement armazena os seguintes dados:

#### <a name="for-social-media-users"></a>Para usuários de redes sociais

- Dados do usuário de redes sociais (chamado de *autor* no Social Engagement) que o Social Engagement adquire de plataformas sociais. Eles podem incluir o nome, o nome de usuário, a imagem de perfil, a localização, o site e a biografia, se fornecida pelo autor.

- Marcas do autor usadas por funcionários do Social Engagement para agrupar e classificar autores, por exemplo, como influenciadores, concorrentes ou fãs.

#### <a name="for-employees"></a>Para os funcionários

- Perfis de usuário que incluem o nome do funcionário, informações de contato e imagem de perfil e que sejam gerenciados no Office 365.

- Endereços de email fornecidos por funcionários que criaram alertas de postagens e alertas de tendências.

- Contas de redes sociais (chamadas de *perfis sociais* no Social Engagement) que são autenticadas no Social Engagement por funcionários para interagir com outras pessoas em uma plataforma social. Elas podem ser propriedade de um funcionário ou da organização e incluir dados que os funcionários forneceram ao se inscrever em uma conta em uma plataforma social. Esses perfis representam a organização nas redes sociais e são usados para interagir com postagens em nome da organização no aplicativo Social Engagement.

- Nomes de usuário no Power BI se sua organização usar o [pacote de conteúdo do Social Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) do Power BI para analisar o desempenho da equipe nas redes sociais.

Esta primeira etapa, ou seja, localizar e analisar os dados pessoais em questão, o ajudará a determinar se a solicitação do titular de dados atende aos requisitos da sua organização para aceitá-la ou recusá-la. Por exemplo, depois de localizar e analisar os dados pessoais, você pode determinar que a solicitação não atende aos requisitos da sua organização porque afetaria negativamente os direitos e liberdades de terceiros.

#### <a name="social-media-users-authors"></a>Usuários de redes sociais (autores)

-   Para localizar os dados pessoais dos usuários, siga as quatro primeiras etapas em [Localizar e excluir um autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#find-and-delete-an-author).

-   Os funcionários podem criar regras do Social Engagement que pesquisem em plataformas sociais por determinados conteúdos definidos; essas regras de pesquisa podem conter nomes de autores. Para garantir que você encontre essas regras, consulte as regras de pesquisa da plataforma social em questão, como o [Twitter](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-twitter-rule), o [Instagram](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-an-instagram-rule) e o [YouTube](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-includetnyoutubeincludestn-youtubemd-rule).

-   Para localizar as marcas de um autor, primeiro [filtre as postagens](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/use-filters#add-edit-or-remove-a-filter) realizadas pelo [autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/understand-filters#authors) e, em seguida, [exiba as marcas de autor](https://go.microsoft.com/fwlink/?linkid=864795).

##### <a name="your-employees"></a>Seus funcionários 

Para localizar:

-   Um perfil de usuário, acesse o [Centro de administração do Office 365](https://portal.office.com/adminportal/home). No **Centro de administração**, selecione **Usuários**. Na página **Usuários Ativos**, procure o usuário na lista.  
    No Social Engagement, vá até **Configurações \> Gerenciamento de usuários** para ver as informações que são automaticamente sincronizadas do Office 365.

-   O destinatário de um alerta, siga as duas primeiras etapas em [Gerenciar destinatários de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).

-   Dados de perfil de redes sociais que foram inseridos por funcionários, acesse **Configurações \> Perfis sociais**. (Para saber mais, consulte [Gerenciar perfis sociais](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles).)

-   Nomes de usuário no Power BI, abra o painel do Power BI no Social Engagement e filtre pelo nome do funcionário.

### <a name="providing-a-copy-of-personal-data"></a>Fornecer uma cópia dos dados pessoais

O RGPD concede aos titulares de dados o direito de obter uma cópia de dados pessoais por solicitação. Depois de encontrar o conteúdo do cliente que inclui dados que possam atender à solicitação, cabe a você e sua organização decidir se devem fornecer uma cópia ao titular de dados.

#### <a name="social-media-users-authors"></a>Usuários de redes sociais (autores)

- Para exportar dados pessoais de autores, siga as etapas em [Exportar informações do autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) para exportar os dados para um arquivo do Excel.

- Para extrair as marcas do autor que foram adicionadas a um autor específico, você pode [exportar os dados de marcas do autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data).

##### <a name="your-employees"></a>Seus funcionários
Para exportar:

- Para obter dados do cliente de perfis de usuário, acesse o [Centro de administração do Office 365](https://portal.office.com/adminportal/home). No **Centro de administração**, selecione **Usuários**. Na página **Usuários Ativos**, procure o usuário cujos dados você deseja exportar. Exclua todos os usuários, exceto o usuário de destino e, em seguida, selecione **Exportar** para exportar os dados para um arquivo .csv, então você poderá usar o Excel para exibir as informações.

- Endereços de email de um destinatário de alerta (somente os Dados do cliente em um alerta). Siga as etapas em [Gerenciar destinatários de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Em seguida, selecione **Exportar** para baixar uma lista do Excel dos alertas que incluem esse destinatário.

- Nomes de usuário do Power BI: os [Relatórios de envolvimento](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) mostram nomes de usuários em relatórios de desempenho da equipe nas redes sociais. Para exportar esses dados, filtre pelo usuário no painel do PowerBI ou acesse o [relatório](https://docs.microsoft.com/power-bi/power-bi-report-add-filter) e [exporte os dados](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

### <a name="rectifying-personal-data"></a>Corrigir dados pessoais

Para corrigir dados pessoais imprecisos ou incompletos:

#### <a name="social-media-users-authors"></a>Usuários de redes sociais (autores)

-   Você deve solicitar que o proprietário dos dados (autor) faça a alteração na plataforma social (como Twitter, WordPress ou Tumblr). O titular dos dados é o proprietário dos dados na conta de rede social, portanto, ele é o único que pode alterá-los. Depois que o autor fizer a alteração, o Social Engagement sincronizará automaticamente os detalhes revisados.

-   Marcas de autor, siga as etapas em [Alterar marcas de autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#change-author-tags).

##### <a name="your-employees"></a>Seus funcionários

-   Perfis de usuário: para alterar os Dados do cliente em um perfil de usuário, consulte [Alterar um nome de usuário e endereço de email no Office 365](https://support.office.com/article/change-a-user-name-and-email-address-in-office-365-fb5ac074-e203-4e1f-9843-b9d1a3e03297) e [Adicionar sua foto de perfil ao Office 365](https://support.office.com/article/add-your-profile-photo-to-office-365-2eaf93fd-b3f1-43b9-9cdc-bdcd548435b7).  
    Essas alterações serão sincronizadas automaticamente no Social Engagement. Para encontrá-las, acesse **Configurações** \> **Gerenciamento de usuários**.

-   Destinatários de alertas: você pode [alterar um alerta](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#change-an-alert).

### <a name="restricting-the-processing-of-personal-data"></a>Restrição de processamento de dados pessoais

#### <a name="social-media-users-authors"></a>Usuários de redes sociais (autores)
Para parar de processar os Dados do cliente de autores no Social Engagement [exclua o autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).

Isso bloqueará o processamento futuro dos dados desse titular e qualquer postagem futura, além de excluir todos os dados sobre e criados por esse autor. Sempre que o Social Engagement adquire novas postagens, ele automaticamente verifica se o autor foi excluído anteriormente e descarta postagens de autores excluídos. Isso não terá efeito sobre a conta do usuário na plataforma social.

##### <a name="your-employees"></a>Seus funcionários

- Para parar de processar os Dados do cliente de funcionários, você pode [remover a licença](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1) do funcionário no Office 365. Isso excluirá todos os itens relacionados ao Social Engagement, como funções e perfis de usuário, todas as configurações relacionadas definidas pelo usuário, alertas, mapas de atividades e streams. Tópicos de pesquisa e perfis sociais não serão excluídos; no entanto, os administradores herdarão a propriedade dos perfis sociais de usuários excluídos e poderão excluir esses perfis por solicitação.

- Para restringir o envio de mensagens de alerta por email, você pode remover um endereço de email de todos os alertas aos quais ele foi adicionado seguindo as etapas em [Gerenciar destinatários de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).

### <a name="deleting-personal-data"></a>Excluir dados pessoais

O RGPD concede aos titulares de dados o direito de solicitar que o controlador exclua dados pessoais em determinadas circunstâncias. O "direito de ser esquecido" ao remover esses dados de uma organização é uma proteção essencial do RGPD.

#### <a name="social-media-users-authors"></a>Usuários de redes sociais (autores)

Para excluir permanentemente todos os dados pessoais de um autor no Social Engagement, exclua o perfil de redes sociais completo desse autor. Consulte [](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors) [Excluir um autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).  
Essa ação não pode ser desfeita. Isso excluirá todos os dados sobre e criados por esse autor do Social Engagement e bloqueará o processamento futuro de seus dados e qualquer postagem futura. Sempre que o Social Engagement adquire novas postagens, ele automaticamente verifica se o autor foi excluído anteriormente e descarta postagens de autores excluídos. Isso não terá efeito sobre a conta do usuário na plataforma social.

Para excluir as marcas do autor, consulte [Remover marcas de autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#remove-author-tags).

>[Observação] Se você for solicitado a remover informações sobre um autor específico, recomendamos confirmar a identidade do autor para validar a solicitação primeiro. Para confirmar a identidade, você poderá solicitar uma mensagem particular do autor de suas contas de redes sociais.

O Social Engagement implementou feeds de conformidade de várias plataformas sociais (como Twitter, WordPress, Tumblr) para tomar medidas em relação a sinais como exclusões de postagens acionadas diretamente nas plataformas sociais. Este recurso é automaticamente ativado com cada instalação do Social Engagement e não exige nenhuma interação do usuário. Além disso, o Social Engagement fornece um mecanismo que permite que serviços (como o Dynamics 365 for Customer Engagement) que se baseiam em conteúdo social do Social Engagement herdem esses sinais.

##### <a name="your-employees"></a>Seus funcionários

Para excluir permanentemente todos os Dados do cliente de um funcionário, você pode [remover a licença](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1) desse funcionário no Office 365.

-   Isso excluirá todos os itens relacionados ao Social Engagement, como funções e perfis de usuário, todas as configurações relacionadas definidas pelo usuário, alertas, mapas de atividades e streams. Tópicos de pesquisa e perfis sociais não serão excluídos. Os administradores herdarão a propriedade dos perfis sociais de usuários excluídos e poderão excluir esses perfis sob solicitação.

-   Essas alterações serão sincronizadas automaticamente no Social Engagement. Para encontrá-las, acesse **Configurações \> Gerenciamento de usuários**.

-   As entradas de funcionários em um relatório de envolvimento do PowerBI se tornam anônimas quando seus dados pessoais são excluídos.

Você pode [excluir um perfil de rede social](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles#delete-a-social-profile).

Para excluir um endereço de email de todos os alertas aos quais ele foi adicionado, siga as etapas em [Gerenciar destinatários de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)

### <a name="exporting-personal-data"></a>Exportar dados pessoais
Você pode fornecer a titulares de dados seus dados pessoais em formato eletrônico.

#### <a name="social-media-users-authors"></a>Usuários de redes sociais (autores)

Para exportar dados pessoais de autores, siga as etapas em [Exportar informações do autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) para exportar os dados para um arquivo do Excel.

Para extrair as marcas do autor que foram adicionadas a um autor específico, você pode [exportar os dados de marcas do autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data).

##### <a name="your-employees"></a>Seus funcionários
Para exportar:

- Para obter dados do cliente de perfis de usuário, acesse o [Centro de administração do Office 365](https://portal.office.com/adminportal/home). No **Centro de administração**, selecione **Usuários**. Na página **Usuários Ativos**, procure o usuário cujos dados você deseja exportar. Exclua todos os usuários, exceto o usuário de destino e, em seguida, selecione **Exportar** para exportar os dados para um arquivo .csv, então você poderá usar o Excel para exibir as informações.

- Endereços de email de um destinatário de alerta (somente os dados pessoais em um alerta). Siga as etapas em [Gerenciar destinatários de alertas como administrador](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Em seguida, selecione **Exportar** para baixar uma lista do Excel dos alertas que incluem esse destinatário.

- Nomes de usuário do Power BI: os [Relatórios de envolvimento](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) mostram nomes de usuários em relatórios de desempenho da equipe nas redes sociais. Para exportar esses dados, filtre pelo usuário no painel do PowerBI ou acesse o [relatório](https://docs.microsoft.com/power-bi/power-bi-report-add-filter) e [exporte os dados](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: Responder aos DSRs para logs gerados pelo sistema

A Microsoft também oferece a capacidade de acessar, exportar e excluir logs gerados pelo sistema que podem ser considerados pessoais de acordo com a definição ampla de "dados pessoais" do RGPD. Exemplos de logs gerados pelo sistema que podem ser considerados pessoais pelo RGPD incluem:

-   Dados de uso de produtos e serviços, como os log de atividades do usuário

-   Dados de solicitações e consultas de pesquisa do usuário

-   Dados gerados por produtos e serviços como resultado da funcionalidade do sistema e da interação de usuários ou de outros sistemas

<span id="_Toc511045103" class="anchor"><span id="_Toc511043191" class="anchor"><span id="_Toc511041446" class="anchor"><span id="_Toc511030410" class="anchor"><span id="_Toc510769888" class="anchor"></span></span></span></span></span>Observe que não há suporte para a capacidade de restringir ou corrigir dados nos logs gerados pelo sistema. Dados em logs gerados pelo sistema constituem ações concretas realizadas na nuvem da Microsoft e dados de diagnóstico. A modificação de tais dados comprometeria o registro histórico de ações e aumentaria os riscos de segurança e fraude.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acessar e exportar logs gerados pelo sistema

Os administradores podem acessar os logs gerados pelo sistema associados ao uso dos serviços e aplicativos do Dynamics 365 por parte de um usuário específico. Para acessar e exportar logs gerados pelo sistema:

1.  Acesse o [Portal de Confiança do Serviço da Microsoft](https://servicetrust.microsoft.com/) e entre usando as credenciais de um administrador global do Dynamics 365.

2.  Na lista suspensa **Privacidade** localizada na parte superior da página, clique em **Solicitação de Titular de Dados**.

3.  Na página **Solicitação de Titular dos Dados**, em **Logs Gerados pelo Sistema**, clique em **Exportação de Log de Dados**.

> A janela **Exportação de Log de Dados** é exibida. Observe que é exibida uma lista de solicitações de exportação de dados enviadas por sua organização.

4.  Para criar uma nova solicitação para um usuário, clique em **Criar Solicitação de Exportação de Dados**.

Depois de criar uma nova solicitação, ela será listada na página **Exportação de Log de Dados**, onde você poderá acompanhar seu status. Após a conclusão de uma solicitação, você poderá clicar em um link para acessar os logs gerados pelo sistema que serão exportados para o local de armazenamento do Azure de sua organização dentro de 30 dias após a criação da solicitação. Os dados serão salvos em formato comum legível por máquina, como JSON ou XML. Se você não tiver uma conta do Azure e um local de armazenamento do Azure, será preciso criar uma conta do Azure e/ou um local de armazenamento do Azure para sua organização para que a ferramenta Exportação de Log de Dados possa exportar os logs gerados pelo sistema.

O Azure possibilita que sua organização exporte os dados no formato JSON nativo para um Contêiner de Armazenamento do Azure especificado[. Artigo Introdução ao Armazenamento do Microsoft Azure: armazenamento de blobs](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).

**Importante**: você deve ser um administrador de locatários para exportar dados de usuário do locatário.

A tabela a seguir resume como acessar e exportar os logs gerados pelo sistema:

<table>
<tbody>
<tr class="odd">
<td align="left"><strong>Quanto tempo a ferramenta Exportação de Log de Dados da Microsoft leva para concluir uma solicitação?</strong>
<td align="left">Isso pode depender de vários fatores. Na maioria dos casos, uma solicitação deve ser concluída em um ou dois dias, mas pode levar até 30 dias.</td>
</tr>
<tr class="odd">
<td align="left"><strong>Qual será o formato da saída?</strong></td>
<td align="left">A saída será em arquivos estruturados legíveis por máquina, como JSON, CSV ou XML.</td>
</tr>
<tr class="even">
<td align="left"><strong>Quais são os dados retornados pela ferramenta Exportação de Log de Dados?</strong></td>
<td align="left">A ferramenta Exportação de Log de Dados retorna logs gerados pelo sistema que a Microsoft armazena. Os dados exportados abrangerão vários serviços da Microsoft, incluindo o Office 365, o Azure e o Dynamics.</td>
</tr>
<tr class="odd">
<td align="left"><strong>Quem tem acesso à ferramenta Exportação de Log de Dados para enviar solicitações de acesso aos logs gerados pelo sistema?</strong></td>
<td align="left">Os administradores globais do Dynamics 365 terão acesso ao utilitário de Gerenciamento de Logs do RGPD.</td>
</tr>
<tr class="even">
<td align="left"><strong>Como os dados são retornados ao usuário?</strong></td>
<td align="left">Os dados serão exportados para o local de armazenamento do Azure da sua organização. Caberá aos administradores da sua organização determinar como eles mostrarão/retornarão esses dados para os usuários.</td>
</tr>
<tr class="odd">
<td align="left"><strong>Qual será a aparência dos dados nos logs gerados pelo sistema?</strong></td>
<td align="left"><p>Exemplo de um registro de log gerado pelo sistema no formato JSON:</p>
<p>[{</p>
<p>  &quot;DateTime&quot;: &quot;2017-04-28T12:09:29-07:00&quot;,</p>
<p>  &quot;AppName&quot;: &quot;SharePoint&quot;,</p>
<p>  &quot;Action&quot;: &quot;OpenFile&quot;,</p>
<p>  &quot;IP&quot;: &quot;154.192.13.131&quot;,</p>
<p>  &quot;DevicePlatform&quot;: &quot;Windows 1.0.1607&quot;</p>
<p>}]</p></td>
</tr>
</tbody>
</table>

[Observação] Alguns recursos não permitirão a exportação ou a exclusão de logs gerados pelo sistema com informações pessoais para manter a integridade dessas informações por motivos de segurança e auditoria.

### <a name="deleting-system-generated-logs"></a>Excluir os logs gerados pelo sistema
Para excluir logs gerados pelo sistema recuperados por meio de uma solicitação de acesso, você deve remover o usuário do serviço e excluir permanentemente sua conta do Azure Active Directory. Para obter instruções sobre como excluir permanentemente um usuário, consulte a seção [Excluir um usuário](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user) deste guia. É importante observar que excluir permanentemente uma conta de usuário é um processo irreversível após iniciado.

Excluir permanentemente uma conta de usuário removerá os dados do usuário de logs gerados pelo sistema de quase todos os serviços do Dynamics 365 dentro de 30 dias.

#### <a name="learn-more"></a>Saiba mais

[Central de Confiabilidade da Microsoft](https://www.microsoft.com/pt-BR/TrustCenter/Privacy/gdpr/default.aspx)
