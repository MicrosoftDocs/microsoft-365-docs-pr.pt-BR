---
title: Extensibilidade de conformidade do Microsoft 365
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
description: Saiba mais sobre como estender soluções de conformidade do Microsoft 365 usando conectores de dados de terceiros e APIs do Microsoft Graph.
ms.openlocfilehash: 676c0ba41e517dd0c3692fec29a1d4034641b634
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919717"
---
# <a name="microsoft-365-compliance-extensibility"></a>Extensibilidade de conformidade do Microsoft 365

As soluções de conformidade do Microsoft 365 ajudam as organizações a avaliar de forma inteligente seus riscos de conformidade, reger e proteger dados confidenciais e responder efetivamente aos requisitos regulatórios. A conformidade do Microsoft 365 é rica em cenários de extensibilidade e permite que as organizações adaptem, estendam, integrem, acelerem e apoiem suas soluções de conformidade.

Há dois blocos principais de construção para extensibilidade de conformidade:

- **Conectores de dados**. Use para importar e arquivar dados que não são da Microsoft para que você possa aplicar recursos de proteção e governança do Microsoft 365 a dados de terceiros.

- **APIs**. Habilita o acesso programático aos recursos de conformidade do Microsoft 365.

## <a name="data-connectors"></a>Conectores de dados

A Microsoft fornece conectores de dados de terceiros que podem ser configurados no centro de conformidade do Microsoft 365. Para ver uma lista de conectores de dados fornecidos pela Microsoft, consulte a tabela Conectores de dados [de terceiros.](archiving-third-party-data.md#third-party-data-connectors) A tabela de conectores de dados de terceiros também resume as soluções de conformidade que você pode aplicar a dados de terceiros após importar e arquivar dados no Microsoft 365 e links para as instruções passo a passo para cada conector.

Para saber mais sobre conectores de dados do Microsoft 365, consulte [Archiving third-party data](archiving-third-party-data.md). Se um tipo de dados de terceiros não for suportado pelos conectores de dados disponíveis no centro de conformidade do Microsoft 365, você poderá trabalhar com um parceiro que possa fornecer um conector personalizado. Para uma lista de parceiros com os que você pode trabalhar e o processo passo a passo para esse método, consulte Trabalhar com um parceiro para arquivar dados [de terceiros.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Pré-requisitos para conectores de dados

Muitos dos conectores de dados disponíveis no centro de conformidade do Microsoft 365 para importar e arquivar dados de terceiros exigem que você prepare e execute tarefas de configuração na fonte de dados de terceiros. Esses pré-requisitos são documentados em detalhes para cada conector de dados de terceiros.

Para conectores de dados no centro de conformidade do Microsoft 365 fornecido por um dos parceiros da Microsoft, sua organização precisará de uma relação comercial com o parceiro antes de poder implantar um conector.

Você pode encontrar requisitos de licenciamento para conectores de dados de terceiros no documento de Comparação de Licenciamento de Conformidade [do Microsoft 365.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>APIs

As APIs de conformidade do Microsoft 365 estão disponíveis no SDK da Proteção de Informações da Microsoft, na API do Microsoft Graph e na API de Atividade de Gerenciamento do Office 365. Algumas APIs de conformidade fazem parte de um novo conjunto de APIs de segurança e conformidade que permitem que desenvolvedores para clientes do Microsoft 365, fornecedores de software independentes, integradores de sistema e provedores de serviços de segurança gerenciados criem soluções de segurança e conformidade de alto valor.

Para saber mais sobre como acessar APIs do Graph, consulte [Overview of Microsoft Graph](/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

O SDK MIP expõe os serviços de rotulagem e proteção dos centros de segurança e conformidade do Microsoft 365 para aplicativos e serviços de terceiros. Os desenvolvedores podem usar o SDK para criar suporte nativo para aplicar rótulos e proteção a arquivos. Os desenvolvedores podem determinar quais ações devem ser tomadas quando rótulos específicos são detectados e motivo sobre informações criptografadas por MIP.

Os casos de uso de SDK MIP de alto nível incluem:

- Um aplicativo de linha de negócios que aplica rótulos de classificação a arquivos em exportação.

- Um aplicativo de design CAD/CAM que fornece suporte nativo para rotulagem MIP.

- Um agente de segurança de acesso à nuvem ou uma solução de prevenção contra perda de dados que pode criptografar dados com a Proteção de Informações do Azure.

Para saber mais sobre o SDK MIP, pré-requisitos, cenários adicionais e exemplos, consulte [MIP SDK Overview](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API do Microsoft Graph para DLP do Teams

Os recursos de prevenção contra perda de dados [(DLP)](dlp-microsoft-teams.md) são amplamente usados no Microsoft Teams, especialmente quando as organizações mudaram para o trabalho remoto. No início deste ano, [anunciamos a visualização pública](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) da API de Notificação de Alterações do Microsoft Graph para mensagens no Teams. Essa API permite que os desenvolvedores criem aplicativos que possam ouvir mensagens do Microsoft Teams em tempo quase real e, em seguida, implementar cenários de DLP para clientes e parceiros. Além disso, a API de Patch do Microsoft Graph permite aplicar ações DLP às mensagens do Teams.

Essas duas APIs formam a API do Microsoft Graph para a DLP do Teams. Você pode começar a experimentar o [aplicativo de exemplo](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Para obter mais informações sobre webhooks de mensagens do Microsoft Teams, consulte a [documentação](/graph/api/subscription-post-subscriptions).

Para obter os requisitos de licenciamento para a DLP do Teams, consulte Diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API do Microsoft Graph para Descoberta e (visualização)

Com a Descoberta Eletrônica [Avançada,](overview-ediscovery-20.md)as organizações podem descobrir os dados onde residem e gerenciar mais fluxos de trabalho de Descoberta Eletrônica de ponta a ponta com recursos inteligentes de aprendizado de máquina e análise para reduzir os dados ao conjunto relevante, enquanto os dados permanecem dentro do limite de segurança e conformidade do Microsoft 365.

As APIs do Graph para Descoberta Avançada podem ser usadas para criar e gerenciar casos, revisar conjuntos e revisar consultas de conjunto de dados de forma escalonável e repetitiva. Isso permite que clientes e parceiros criem aplicativos e fluxos de trabalho para automatizar processos comuns e repetitivos, como a criação de casos e o gerenciamento de custodiantes e retivementos legais.

O primeiro conjunto de APIs do Graph para Descoberta eDiscovery está disponível na visualização pública. Planejamos adicionar mais recursos até o final do ano civil. Para saber mais sobre essas APIs e outras atualizações para Descoberta Automática Avançada, consulte este [blog](https://aka.ms/Ignite2020AeDAA).

Para obter os requisitos de licenciamento para a Descoberta Externa Avançada e a API, consulte a seção "Descoberta eDiscovery" na orientação de licenciamento do [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)para conformidade & segurança.

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API do Microsoft Graph para Exportação do Teams (visualização)

O EIA (Enterprise Information Archiving) para o Microsoft Teams é um cenário importante para nossos clientes, pois permite que eles resolvam os requisitos regulatórios. Além de nossos recursos integrados para arquivamento de conteúdo no Microsoft Teams, os clientes e parceiros agora podem usar APIs de Exportação do Teams para resolver cenários personalizados de aplicativo e integração. As APIs de Exportação do Teams suportam exportação em massa (até 200 solicitações por segundo/por aplicativo/por locatário) de mensagens do Teams e anexos de mensagens. As mensagens excluídas também são acessíveis pela API por até 30 dias após a exclusão. Para obter mais informações sobre essas APIs de Exportação do Teams e como usá-las em seus aplicativos, consulte Exportar conteúdo com as APIs de Exportação do [Microsoft Teams.](/microsoftteams/export-teams-content)

Para obter os requisitos de licenciamento para o uso das APIs de Exportação do Teams, consulte Diretrizes de licenciamento do [Microsoft 365 para](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)conformidade & segurança.