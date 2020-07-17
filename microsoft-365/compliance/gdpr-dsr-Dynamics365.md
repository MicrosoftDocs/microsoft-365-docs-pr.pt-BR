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

O [Regulamento Geral sobre a Proteção de Dados da União Europeia (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) concede direitos a pessoas (conhecidas no regulamento como *titulares de dados*) para gerenciar dados pessoais coletados por um empregador ou outro tipo de agência ou organização (conhecido como *controlador de dados* ou apenas *controlador*). Os dados pessoais são definidos amplamente sob o RGPD como quaisquer dados relacionados a uma pessoa natural identificada ou identificável. O RGPD concede aos titulares dos dados direitos específicos aos seus dados pessoais; esses direitos incluem a obtenção de cópias, a solicitação de alterações, a restrição do processamento, a exclusão ou o recebimento em formato eletrônico dos dados, para que possam ser transferidos para outro controlador. Um pedido formal de um titular de dados a um responsável pelo tratamento para efetuar uma ação sobre os seus dados pessoais é chamado neste documento de *Solicitação de Direitos do Titular dos Dados* ou solicitação de DSR.

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
- Grave os dados e a hora da solicitação. (Você terá 30 dias para concluir a solicitação).
- Afirme que a solicitação atende aos requisitos da sua organização para honrar ou recusar a solicitação de um titular de dados. Por exemplo, você deve garantir que a execução da solicitação não entre em conflito com outras obrigações legais, financeiras ou regulamentares que você tenha, nem viole os direitos e liberdades de outras pessoas.
- Verifique se tem as informações relacionadas à solicitação.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Parte 1: Respondendo a Solicitações de Direitos de Titulares de Dados para dados pessoais incluídos nos dados do cliente

Nos artigos abaixo, você encontrará informações para ajudá-lo a se preparar e responder às solicitações DSR de dados pessoais incluídas nos dados do cliente processados no Dynamics 365. É importante observar que os dados pessoais podem estar presentes em outras categorias de dados processados pelo Microsoft durante o serviço de uma assinatura de serviços on-ine, como dados de administrador ou de suporte definidos na Declaração de privacidade da Microsoft. Este documento é limitado para ajudá-lo no processo de descoberta e gerenciamento de solicitações DSR que afetam os dados pessoais presentes nos dados do cliente que você forneceu ao Dynamics 365.

O Dynamics 365 é um serviço online que oferece vários recursos de processamento de dados como um software como um serviço (SaaS). Dessa forma, o Dynamics 365 oferece uma ampla variedade de recursos para processar diversos tipos de dados, que podem variar de acordo com sua natureza, finalidade ou outros atributos específicos, como dados financeiros, de vendas, transações, informações de RH etc. Devido a essa diversidade, o Dynamics 365 oferece vários formulários, campos, esquemas, pontos de extremidade e lógicas para processar dados do cliente, o que também reflete nas várias formas com as quais as solicitações de DSR podem ser resolvidas em cada aplicativo. Como os aplicativos do Dynamics 365 oferecem várias maneiras para atender às solicitações de DSR específicas, elas serão mencionadas neste guia, com descrições técnicas de cada aplicativo.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Localizar os dados do cliente

A primeira etapa ao responder a uma solicitação de direitos de entidade de dados é procurar e identificar os dados do cliente que estão sendo solicitados.

A classificação correta dos dados do cliente é a base para trabalhar com dados pessoais no Microsoft Dynamics 365 Customer Engagement. O Dynamics 365 for Customer Engagement oferece flexibilidade para criar uma extensão de aplicativo de acordo com a classificação dos dados. A classificação correta permite identificar informações como dados pessoais, possibilitando a localização e recuperação dessas informações ao responder às solicitações de um titular de dados. Ela também ajuda no cumprimento de requisitos legais e regulamentares para coleta e gerenciamento de dados pessoais.

A Microsoft fornece recursos que podem ajudá-lo a responder às solicitações de direitos de entidade de dados e, assim, a acessar os dados do cliente. No entanto, é sua responsabilidade garantir que os dados pessoais sejam localizados e classificados adequadamente.

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

Além disso, para o Dynamics 365 for Marketing, é fornecida uma [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) para criar extensões que recuperem registros adicionais de interações de clientes capturadas, que podem conter dados pessoais do cliente. A API carrega as informações relevantes do sistema de back-end e as reúne em um único documento portátil.

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
- Preparar uma página de [centros de assinatura](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) que contém quantos campos de contato editáveis puderem ser incluídos. Isso permite que um usuário final atualize suas próprias informações na medida do possível.

O ***Dynamics 365 Customer Service Insights*** também fornece recursos que permitem [correção ou alterações nos dados do cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary) pelas organizações.

No ***Dynamics 365 for Finance and Operations***, você também pode usar as [*ferramentas de personalização*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), mas a implementação e a decisão estão sob sua responsabilidade.

O ***Dynamics 365 Business Central*** oferece duas maneiras de corrigir dados imprecisos ou incompletos do cliente.

Para editar em massa vários registros do Business Central, você pode exportar listas para o Excel usando o [suplemento para Excel do Business Central](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para corrigir vários registros e publicar os dados modificados do Excel no Business Central. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

Você pode alterar dados do cliente armazenados em qualquer campo, como as informações do cliente no cartão do cliente — ao editar manualmente o elemento de dados com os dados pessoais de destino. Para saber mais, confira [inserir dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Nota curta sobre como modificar entradas em transações de negócios

Registros transacionais, como entradas contábeis gerais, do cliente e tributárias, são essenciais para a integridade de um sistema de planejamento de recursos empresariais. Dados pessoais que fazem parte de uma transação financeira ou de outro tipo são mantidos “no estado em que se encontram” para cumprir as leis financeiras (por exemplo, leis tributárias), impedir fraudes (como uma trilha de auditoria de segurança ou para estar em conformidade com as certificações do setor). Dessa forma, o Dynamics 365 for Finance and Operations e o Dynamics 365 Business Central restringem a modificação dos dados nesses registros.

Se você armazenar dados pessoais em registros de transação de negócios, a única maneira de corrigir, excluir ou restringir o processamento de dados pessoais para atender à solicitação de um titular de dados é usar os [recursos de personalização](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index) Dynamics 365 Business Central. A[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)decisão de atender a uma solicitação do titular de dados de modificação e sua implementação é de sua responsabilidade.

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

- Para editar em massa vários registros do Business Central, você pode exportar dados para o Excel usando o [suplemento para Excel do Business Central](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) para excluir vários registros e publicar essas mudanças do Excel para o Business Central. Para saber mais, consulte [Exportar seus dados empresariais para o Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Você pode excluir dados do cliente armazenados em qualquer campo excluindo manualmente o elemento de dados que contém os dados do cliente-alvo. Para saber mais, confira [inserir dados](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Você pode excluir diretamente os dados do cliente, por exemplo, ao excluir um contato e executar o trabalho em lote Excluir Entradas do Log de Interações Canceladas para excluir as interações para esse contato.
- Você pode [excluir documentos](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) com dados do cliente como, por exemplo, memorandos, vendas lançadas e faturas de compra.

Além da exclusão individual ou em massa de registros discretos, observe que apenas funcionários desligados da organização podem ser totalmente excluídos do ***Dynamics 365 for Talent***. [Siga estas etapas para excluir funcionários desligados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportação de dados do cliente

Para atender a uma solicitação de portabilidade de dados, os dados do cliente no ***Dynamics 365 for Customer Engagement*** podem ser exportados usando os recursos abrangentes de exportação de entidade. Dados do cliente podem ser exportados para um arquivo estático do Excel para facilitar uma solicitação de portabilidade de dados. Usando o Excel, você pode editar os dados pessoais a serem incluídos na solicitação de portabilidade e depois salvar como um formato comum legível por máquina, como .csv ou .xml.

Além disso, para o Dynamics 365 for Marketing, é fornecida uma [API dedicada](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) para criar extensões que recuperem registros adicionais de interações de clientes capturadas, que podem conter dados pessoais do cliente. A API carrega as informações relevantes do sistema de back-end e as reúne em um único documento portátil.

Para ***Dynamics 365 Customer Service Insights***, você [exporta dados do cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) por meio do portal de gerenciamento do Azure.

O ***Dynamics 365 for Finance and Operations*** fornece [entidades de integração e de gerenciamento de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), habilitando entidades fornecidas ou estendidas para exportação de dados pessoais repetidos para o Excel ou outros formatos comuns usando [Importar e exportar trabalhos de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Dados do cliente podem ser exportados para um arquivo estático do Excel para facilitar a solicitação de portabilidade de dados. Ao exportar dados do cliente para o Excel dessa forma, você pode editar os dados pessoais a serem incluídos na solicitação de portabilidade e depois salvar como um formato comum legível por máquina, como .csv ou .xml.

Tanto o Dynamics 365 for Finance and Operations quanto o ***Dynamics 365 for Talent*** oferecem o Relatório de pesquisa de pessoa para fornecer ao titular os dados que você tenha classificado como pessoais. 

O ***Dynamics 365 Business Central*** oferece os seguintes recursos:

- Você pode exportar dados do cliente para um arquivo do Excel. No Excel, você pode editar os dados do cliente a serem incluídos na solicitação de portabilidade, e depois salvar como um formato comum legível por máquina, como .csv ou .xml. Para saber mais, confira [exportar dados corporativos para o Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Você pode exportar dados do cliente para um arquivo do Excel. No Excel, você pode editar os dados do cliente a serem incluídos na solicitação de portabilidade, e depois salvar como um formato comum legível por máquina, como .csv ou .xml. Para saber mais, confira [exportar dados corporativos para o Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: Responder aos DSRs para logs gerados pelo sistema

A Microsoft também oferece a capacidade de acessar, exportar e excluir logs gerados pelo sistema que podem ser considerados pessoais de acordo com a definição ampla de "dados pessoais" do RGPD. Exemplos de logs gerados pelo sistema que podem ser considerados pessoais pelo RGPD incluem:

- Dados de uso de produtos e serviços, como os log de atividades do usuário
- Dados de solicitações e consultas de pesquisa do usuário
- Dados gerados por produtos e serviços como resultado da funcionalidade do sistema e da interação de usuários ou de outros sistemas

Observe que não há suporte para a capacidade de restringir ou retificar dados nos logs gerados pelo sistema. Os dados em logs gerados pelo sistema constituem ações concretas realizadas na nuvem da Microsoft e dados de diagnóstico. A modificação de tais dados comprometeria o registro histórico de ações e aumentaria os riscos de segurança e fraude.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acessar e exportar logs gerados pelo sistema

Os administradores podem acessar logs gerados pelo sistema associados ao uso de serviços e aplicativos do Dynamics 365 por um usuário específico. Para acessar e exportar logs gerados pelo sistema:

1. Acesse o [Portal de Confiança do Serviço da Microsoft](https://servicetrust.microsoft.com/) e entre usando as credenciais de um administrador global do Dynamics 365.
2. Na lista suspensa **Privacidade** localizada na parte superior da página, clique em **Solicitação de Titular dos Dados**.
3. Na página **Solicitação de Titular dos Dados**, em **Logs Gerados pelo Sistema**, clique em **Exportação de Log de Dados**.
    > [!NOTE]
    > A janela **Exportação de Log de Dados** é exibida. Observe que é exibida uma lista de solicitações de exportação de dados enviadas por sua organização.
4. Para criar uma nova solicitação para um usuário, clique em **Criar Solicitação de Exportação de Dados**.

Depois de criar uma nova solicitação, ela será listada na página **Exportação de log de dados**, na qual é possível rastrear seu status. Após a conclusão de uma solicitação, você pode clicar em um link para acessar os logs gerados pelo sistema, que serão exportados para o local de armazenamento do Azure da organização dentro de 30 dias após a criação da solicitação. Os dados serão salvos em formatos comuns de arquivos legíveis por máquina, como JSON ou XML. Se você não tiver uma conta do Azure e um local de armazenamento do Azure, precisará criar uma conta do Azure e/ou local de armazenamento do Azure para a sua organização, para que a ferramenta de Exportação do log de dados possa exportar os logs gerados pelo sistema.

O Azure possibilita que sua organização exporte os dados no formato JSON nativo para um Contêiner de Armazenamento do Azure especificado[. Artigo Introdução ao Armazenamento do Microsoft Azure — Armazenamento de blobs](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage). Os dados recuperados não incluirão dados que possam comprometer a segurança e a estabilidade do serviço.

> [!IMPORTANT]
> Você deve ser um administrador de locatários para exportar dados de usuário do locatário.

A tabela a seguir resume como acessar e exportar os logs gerados pelo sistema:

| | |
|:----|:---|
| | |
|**Quanto tempo a ferramenta de Exportação de Log de Dados da Microsoft leva para concluir uma solicitação?**| Isso pode depender de vários fatores. Na maioria dos casos, uma solicitação deve ser concluída em um ou dois dias, mas pode levar até 30 dias. |
|**Qual será o formato da saída?**| A saída será em arquivos estruturados legíveis por máquina, como JSON, CSV ou XML. |
|**Quais são os dados retornados pela ferramenta Exportação de Log de Dados?**| A ferramenta Exportação de Log de Dados retorna logs gerados pelo sistema que a Microsoft armazena. Os dados exportados serão distribuídos em vários serviços da Microsoft, incluindo o Office 365, o Azure e o Dynamics. |
|***Quem tem acesso à ferramenta de Exportação de Log de Dados para enviar solicitações de acesso para logs gerados pelo sistema?**| Os administradores globais do Dynamics 365 terão acesso ao utilitário de Gerenciamento de Logs do RGPD. |
|**Como os dados são retornados ao usuário?**| Os dados serão exportados para o local de armazenamento do Azure da sua organização. Caberá aos administradores da sua organização determinar como eles mostrarão/retornarão esses dados para os usuários. |
|**Qual será a aparência dos dados nos logs gerados pelo sistema?**| Exemplo de um registro de log gerado pelo sistema no formato JSON: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>Excluir os logs gerados pelo sistema

Para excluir logs gerados pelo sistema recuperados por meio de uma solicitação de acesso, você deve remover o usuário do serviço e excluir permanentemente a conta do Azure Active Directory. Para obter instruções sobre como excluir permanentemente um usuário, confira a seção [Etapa 5: Excluir](gdpr-dsr-azure.md#step-5-delete) no tópico Solicitações do Titular dos Dados do Azure. É importante observar que, após iniciar a exclusão permanente de uma conta de usuário, esta ação será irreversível. Excluir permanentemente uma conta de usuário remove os dados do usuário dos logs gerados pelo sistema, exceto dados que possam comprometer a segurança ou estabilidade do serviço, para quase todos os serviços do Dynamics 365 em 30 dias.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
