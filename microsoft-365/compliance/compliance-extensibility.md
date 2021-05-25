---
title: Microsoft 365 extensibilidade de conformidade
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre como estender Microsoft 365 soluções de conformidade usando conectores de dados de terceiros e APIs Graph Microsoft.
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651051"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 extensibilidade de conformidade

Microsoft 365 soluções de conformidade ajudam as organizações a avaliar de forma inteligente seus riscos de conformidade, reger e proteger dados confidenciais e responder efetivamente aos requisitos regulatórios. Microsoft 365 conformidade é rica em cenários de extensibilidade e permite que as organizações adaptem, estendam, integrem, acelerem e suportem suas soluções de conformidade.

Há dois blocos principais de construção para extensibilidade de conformidade:

- **Conectores de dados**. Use para importar e arquivar dados que não são da Microsoft para que você possa aplicar Microsoft 365 proteção e governança a dados de terceiros.

- **APIs**. Habilita o acesso programático aos Microsoft 365 de conformidade.

## <a name="data-connectors"></a>Conectores de dados

A Microsoft fornece conectores de dados de terceiros que podem ser configurados no Microsoft 365 de conformidade. Para ver uma lista de conectores de dados fornecidos pela Microsoft, consulte a tabela Conectores de dados [de terceiros.](archiving-third-party-data.md#third-party-data-connectors) A tabela de conectores de dados de terceiros também resume as soluções de conformidade que você pode aplicar a dados de terceiros após importar e arquivar dados no Microsoft 365 e links para as instruções passo a passo para cada conector.

Para saber mais sobre Microsoft 365 conectores de dados, consulte [Arquivando dados de terceiros.](archiving-third-party-data.md) Se um tipo de dados de terceiros não for suportado pelos conectores de dados disponíveis no centro de conformidade do Microsoft 365, você poderá trabalhar com um parceiro que possa fornecer um conector personalizado. Para uma lista de parceiros com os que você pode trabalhar e o processo passo a passo para esse método, consulte Trabalhar com um parceiro para arquivar dados [de terceiros.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Pré-requisitos para conectores de dados

Muitos dos conectores de dados disponíveis no centro de conformidade Microsoft 365 para importar e arquivar dados de terceiros exigem que você prepare e execute tarefas de configuração na fonte de dados de terceiros. Esses pré-requisitos são documentados em detalhes para cada conector de dados de terceiros.

Para conectores de dados no Microsoft 365 de conformidade fornecidos por um dos parceiros da Microsoft, sua organização precisará de uma relação de negócios com o parceiro antes de poder implantar um conector.

Você pode encontrar requisitos de licenciamento para conectores de dados de terceiros no documento [Microsoft 365 Comparação](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) de Licenciamento de Conformidade.

## <a name="apis"></a>APIs

Microsoft 365 APIs de conformidade estão disponíveis no SDK da Proteção de Informações da Microsoft, na API do Microsoft Graph e na API Office 365 Atividade de Gerenciamento. Algumas APIs de conformidade fazem parte de um novo conjunto de APIs de segurança e conformidade que permitem que desenvolvedores para clientes Microsoft 365, fornecedores de software independentes, integradores de sistema e provedores de serviços de segurança gerenciados criem soluções de segurança e conformidade de alto valor.

Para saber mais sobre como acessar Graph APIs, consulte [Overview of Microsoft Graph](/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

O SDK MIP expõe os serviços de rotulagem e proteção Microsoft 365 centros de segurança e conformidade para aplicativos e serviços de terceiros. Os desenvolvedores podem usar o SDK para criar suporte nativo para aplicar rótulos e proteção a arquivos. Os desenvolvedores podem determinar quais ações devem ser tomadas quando rótulos específicos são detectados e motivo sobre informações criptografadas por MIP.

Os casos de uso de SDK MIP de alto nível incluem:

- Um aplicativo de linha de negócios que aplica rótulos de classificação a arquivos em exportação.

- Um aplicativo de design CAD/CAM que fornece suporte nativo para rotulagem MIP.

- Um agente de segurança de acesso à nuvem ou uma solução de prevenção contra perda de dados que pode criptografar dados com a Proteção de Informações do Azure.

Para saber mais sobre o SDK MIP, pré-requisitos, cenários adicionais e exemplos, consulte [MIP SDK Overview](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API Graph Microsoft para Teams DLP

Os recursos de prevenção contra perda de dados [(DLP)](dlp-microsoft-teams.md) são amplamente usados no Microsoft Teams, especialmente quando as organizações mudaram para o trabalho remoto. No início deste ano, [anunciamos a visualização](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) pública da API de Notificação de Alterações do Microsoft Graph para mensagens Teams. Essa API permite que os desenvolvedores criem aplicativos que possam ouvir Microsoft Teams mensagens em tempo quase real e, em seguida, implementar cenários de DLP para clientes e parceiros. Além disso, a API Graph Patch da Microsoft permite que você aplique ações de DLP Teams mensagens.

Essas duas APIs formam a API do Microsoft Graph para Teams DLP. Você pode começar a experimentar o [aplicativo de exemplo](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Para obter mais informações sobre Microsoft Teams webhooks de mensagens, consulte a [documentação](/graph/api/subscription-post-subscriptions).

Para obter os requisitos de licenciamento para Teams DLP, consulte Microsoft 365 de licenciamento para conformidade [& segurança.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API Graph microsoft para Descoberta e (visualização)

Com [o Advanced eDiscovery,](overview-ediscovery-20.md)as organizações podem descobrir os dados onde eles residem e gerenciar mais fluxos de trabalho de Descoberta Eletrônica de ponta Microsoft 365 com recursos inteligentes de aprendizado de máquina e análise para reduzir dados ao conjunto relevante, enquanto os dados permanecem dentro do limite de segurança e conformidade do Microsoft 365.

Graph APIs para Advanced eDiscovery podem ser usadas para criar e gerenciar casos, revisar conjuntos e revisar consultas de conjunto de consultas escalonáveis e repetitivas. Isso permite que clientes e parceiros criem aplicativos e fluxos de trabalho para automatizar processos comuns e repetitivos, como a criação de casos e o gerenciamento de custodiantes e retivementos legais.

O primeiro conjunto de Graph APIs para Descoberta eDiscovery estão disponíveis na visualização pública. Planejamos adicionar mais recursos até o final do ano civil. Para saber mais sobre essas APIs e outras atualizações para Advanced eDiscovery, consulte este [blog](https://aka.ms/Ignite2020AeDAA).

Para obter os requisitos de licenciamento para Advanced eDiscovery e a API, consulte a seção "Descoberta eDiscovery" na Microsoft 365 de licenciamento para conformidade [& segurança.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API Graph Microsoft para Teams Export (visualização)

Enterprise O Arquivamento de Informações (EIA) para Microsoft Teams é um cenário importante para nossos clientes, pois permite que eles resolvam os requisitos regulatórios. Além de nossos recursos integrados para arquivamento de conteúdo no Microsoft Teams, os clientes e parceiros agora podem usar Teams APIs de Exportação para resolver cenários personalizados de integração e aplicativos. As TEAMS Export suportam exportação em massa (até 200 solicitações por segundo/por aplicativo/por locatário) de mensagens Teams e anexos de mensagens. As mensagens excluídas também são acessíveis pela API por até 30 dias após a exclusão. Para obter mais informações sobre essas Teams ApIs de Exportação e como usá-las em seus aplicativos, consulte Exportar conteúdo com as APIs Microsoft Teams [Export.](/microsoftteams/export-teams-content)

Para obter os requisitos de licenciamento para o uso das APIs Teams Export, consulte Microsoft 365 de licenciamento para conformidade [& segurança.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="microsoft-graph-connector-apis-preview"></a>APIs Graph Connector da Microsoft (visualização)

Com [os conectores Graph Microsoft,](/microsoftsearch/connectors-overview)as organizações podem indexar dados de terceiros para que apareçam nos resultados da Pesquisa da Microsoft. Esse recurso expande os tipos de fontes de conteúdo que podem ser pesquisadas nos aplicativos de produtividade do Microsoft 365 e no ecossistema da Microsoft mais amplo. Os dados de terceiros podem ser hospedados no local ou em nuvens públicas ou privadas. A partir Advanced eDiscovery, estamos habilitando a visualização do desenvolvedor do valor de conformidade integrado de Microsoft 365 aplicativos conectados. Isso permite a conformidade para aplicativos que se integram ao ecossistema Microsoft 365 capacitar os usuários com experiências de conformidade perfeitas. Para saber mais sobre como incorporar as APIs do Microsoft Graph Connector no seu exibição de aplicativos, consulte [Create, update,](/graph/search-index-manage-connections)and delete connections in the Microsoft Graph .

