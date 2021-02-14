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
description: Saiba como estender as soluções de conformidade do Microsoft 365 usando conectores de dados de terceiros e APIs do Microsoft Graph.
ms.openlocfilehash: 8eeb83013ec412ed82973b37c4c10e2250f5eaf8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285737"
---
# <a name="microsoft-365-compliance-extensibility"></a>Extensibilidade de conformidade do Microsoft 365

As soluções de conformidade do Microsoft 365 ajudam as organizações a avaliar de forma inteligente seus riscos de conformidade, reger e proteger dados confidenciais e responder efetivamente aos requisitos regulatórios. A conformidade do Microsoft 365 é rica em cenários de extensibilidade e permite que as organizações adaptem, estendam, integrem, acelerem e deem suporte a suas soluções de conformidade.

Há dois blocos de construção principais para extensibilidade de conformidade:

- **Conectores de dados.** Use para importar e arquivar dados que não são da Microsoft para que você possa aplicar recursos de proteção e governança do Microsoft 365 a dados de terceiros.

- **APIs**. Permite o acesso programático aos recursos de conformidade do Microsoft 365.

## <a name="data-connectors"></a>Conectores de dados

A Microsoft fornece conectores de dados de terceiros que podem ser configurados no centro de conformidade do Microsoft 365. Para uma lista de conectores de dados fornecidos pela Microsoft, consulte a [tabela conectores de dados de](archiving-third-party-data.md#third-party-data-connectors) terceiros. A tabela de conectores de dados de terceiros também resume as soluções de conformidade que você pode aplicar a dados de terceiros depois de importar e arquivar dados no Microsoft 365 e links para as instruções passo a passo para cada conector.

Para saber mais sobre conectores de dados do Microsoft 365, consulte Arquivamento [de dados de terceiros.](archiving-third-party-data.md) Se um tipo de dados de terceiros não for compatível com os conectores de dados disponíveis no centro de conformidade do Microsoft 365, você poderá trabalhar com um parceiro que possa fornecer um conector personalizado. Para uma lista de parceiros com quem você pode trabalhar e o processo passo a passo para esse método, consulte Trabalhar com um parceiro para arquivar dados [de terceiros.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Pré-requisitos para conectores de dados

Muitos dos conectores de dados disponíveis no centro de conformidade do Microsoft 365 para importar e arquivar dados de terceiros exigem que você prepare e execute tarefas de configuração na fonte de dados de terceiros. Esses pré-requisitos são documentados em detalhes para cada conector de dados de terceiros.

Para conectores de dados no centro de conformidade do Microsoft 365 fornecido por um dos parceiros da Microsoft, sua organização precisará de um relacionamento comercial com o parceiro antes de implantar um conector.

Você pode encontrar requisitos de licenciamento para conectores de dados de terceiros no documento de Comparação de Licenciamento de Conformidade [do Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>APIs

As APIs de conformidade do Microsoft 365 estão disponíveis no SDK da Proteção de Informações da Microsoft, na API do Microsoft Graph e na API da Atividade de Gerenciamento do Office 365. Algumas APIs de conformidade fazem parte de um novo conjunto de APIs de segurança e conformidade que permitem que os desenvolvedores para clientes do Microsoft 365, fornecedores independentes de software, integradores de sistema e provedores de serviços de segurança gerenciados criem soluções de conformidade e segurança de alto valor.

Para saber mais sobre como acessar as APIs do Graph, consulte [Visão geral do Microsoft Graph.](https://docs.microsoft.com/graph/overview)

### <a name="microsoft-information-protection-mip-sdk"></a>SDK da Proteção de Informações da Microsoft (MIP)

O SDK do MIP expõe os serviços de rotulagem e proteção dos centros de segurança e conformidade do Microsoft 365 para aplicativos e serviços de terceiros. Os desenvolvedores podem usar o SDK para criar suporte nativo para aplicar rótulos e proteção a arquivos. Os desenvolvedores podem determinar quais ações devem ser tomadas quando rótulos específicos são detectados e avaliar as informações criptografadas pelo MIP.

Os casos de uso do SDK MIP de alto nível incluem:

- Um aplicativo de linha de negócios que aplica rótulos de classificação a arquivos na exportação.

- Um aplicativo de design CAD/CAM que fornece suporte nativo para rotulagem MIP.

- Um agente de segurança de acesso à nuvem ou uma solução de prevenção contra perda de dados que pode criptografar dados com a Proteção de Informações do Azure.

Para saber mais sobre o SDK MIP, pré-requisitos, cenários adicionais e exemplos, consulte Visão geral [do SDK MIP.](https://docs.microsoft.com/information-protection/develop/overview)

### <a name="microsoft-graph-api-for-teams-dlp"></a>API do Microsoft Graph para DLP do Teams

Os recursos de prevenção contra perda de dados [(DLP)](dlp-microsoft-teams.md) são amplamente usados no Microsoft Teams, especialmente quando as organizações mudaram para o trabalho remoto. No início deste ano, [anunciamos a visualização pública](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) da API de Notificação de Alterações do Microsoft Graph para mensagens no Teams. Essa API permite que os desenvolvedores criem aplicativos que podem ouvir as mensagens do Microsoft Teams quase em tempo real e, em seguida, implementar cenários de DLP para clientes e parceiros. Além disso, a API de Patch do Microsoft Graph permite que você aplique ações DLP às mensagens do Teams.

Essas duas APIs formam a API do Microsoft Graph para DLP do Teams. Você pode começar tentando o aplicativo [de exemplo.](https://github.com/microsoftgraph/csharp-webhook-with-resource-data) Para obter mais informações sobre webhooks de mensagens do Microsoft Teams, consulte a [documentação.](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)

Para obter os requisitos de licenciamento para a DLP do Teams, confira as diretrizes de licenciamento do [Microsoft 365 para](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)segurança & conformidade.

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API do Microsoft Graph para eDiscovery (visualização)

Com a Descoberta Eletrônica [Avançada,](overview-ediscovery-20.md)as organizações podem descobrir dados onde residem e gerenciar mais fluxos de trabalho de Descoberta Eletrônica de ponta a ponta com recursos inteligentes de aprendizado de máquina e análise para reduzir os dados ao conjunto relevante, tudo enquanto os dados permanecem dentro do limite de segurança e conformidade do Microsoft 365.

As APIs do Graph para Descobertas Avançadas podem ser usadas para criar e gerenciar ocorrências, conjuntos de revisão e revisar as consultas do conjunto de forma escalonável e repetitiva. Isso permite que clientes e parceiros criem aplicativos e fluxos de trabalho para automatizar processos comuns e repetitivos, como a criação de casos e o gerenciamento de custodiantes e retém legais.

O primeiro conjunto de APIs do Graph para eDiscovery está disponível na visualização pública. Planejamos adicionar mais recursos até o final do ano civil. Para saber mais sobre essas APIs e outras atualizações da Descoberta Automática Avançada, confira este [blog.](https://aka.ms/Ignite2020AeDAA)

Para obter os requisitos de licenciamento para a Api e Descobertas e Descobertas Avançadas, confira a seção "Descoberta eDiscovery" nas diretrizes de licenciamento do [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)para conformidade & segurança.

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Api do Microsoft Graph para Exportação do Teams (visualização)

O EIA (Enterprise Information Archiving) para o Microsoft Teams é um cenário importante para nossos clientes, pois permite que eles resolvam os requisitos regulatórios. Além de nossos recursos integrados para arquivamento de conteúdo no Microsoft Teams, os clientes e parceiros agora podem usar as APIs de exportação do Teams para resolver cenários personalizados de aplicação e integração. As APIs de exportação do Teams suportam exportação em massa (até 200 solicitações por segundo/por aplicativo/por locatário) de mensagens e anexos de mensagens do Teams. As mensagens excluídas também podem ser acessadas pela API por até 30 dias após a exclusão. Para saber mais sobre essas APIs de exportação do Teams e como usá-las em seus aplicativos, confira Exportar conteúdo com as APIs de exportação do [Microsoft Teams.](https://docs.microsoft.com/microsoftteams/export-teams-content)

Para obter os requisitos de licenciamento para o uso das APIs de exportação do Teams, confira as diretrizes de licenciamento do [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para segurança & conformidade.
