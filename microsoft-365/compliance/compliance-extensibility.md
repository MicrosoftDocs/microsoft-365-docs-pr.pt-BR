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
description: Saiba como estender as soluções de conformidade da Microsoft 365 usando conectores de dados de terceiros e APIs do Microsoft Graph.
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204261"
---
# <a name="microsoft-365-compliance-extensibility"></a>Extensibilidade de conformidade do Microsoft 365

As soluções de conformidade da Microsoft 365 ajudam as organizações a avaliar com inteligência seus riscos de conformidade, controlar e proteger dados confidenciais e responder efetivamente aos requisitos normativos. A conformidade da Microsoft 365 é rica em cenários de extensibilidade e permite que as organizações adaptem, estendam, integrem, acelerem e ofereçam suporte a suas soluções de conformidade.

Há dois blocos principais de construção para a extensibilidade de conformidade:

- **Conectores de dados**. Use para importar e arquivar dados não-Microsoft para que você possa aplicar os recursos de proteção e governança do Microsoft 365 a dados de terceiros.

- **APIs**. Permite o acesso programático a recursos de conformidade da Microsoft 365.

## <a name="data-connectors"></a>Conectores de dados

A Microsoft fornece conectores de dados de terceiros que podem ser configurados no centro de conformidade da Microsoft 365. Para obter uma lista de conectores de dados fornecidos pela Microsoft, confira a tabela [conectores de dados de terceiros](archiving-third-party-data.md#third-party-data-connectors) . A tabela de conectores de dados de terceiros também resume as soluções de conformidade que podem ser aplicadas a dados de terceiros após a importação e o arquivamento de dados no Microsoft 365 e links para as instruções passo a passo para cada conector.

Para saber mais sobre os conectores de dados do Microsoft 365, confira [arquivamento de dados de terceiros](archiving-third-party-data.md). Se não houver suporte para um tipo de dados de terceiros nos conectores de dados disponíveis no centro de conformidade da Microsoft 365, você poderá trabalhar com um parceiro que possa fornecer um conector personalizado. Para obter uma lista de parceiros com os quais você pode trabalhar e o processo passo a passo desse método, confira [trabalhar com um parceiro para arquivar dados de terceiros](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Pré-requisitos para conectores de dados

Muitos dos conectores de dados disponíveis no centro de conformidade da Microsoft 365 para importar e arquivar dados de terceiros exigem que você prepare e execute tarefas de configuração na fonte de dados de terceiros. Esses pré-requisitos são documentados detalhadamente para cada conector de dados de terceiros.

Para conectores de dados no centro de conformidade da Microsoft 365 fornecido por um dos parceiros da Microsoft, sua organização precisará de um relacionamento de negócios com o parceiro para que você possa implantar um conector.

Você pode encontrar requisitos de licenciamento para conectores de dados de terceiros no documento de [comparação de licenciamento de conformidade da Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) .

## <a name="apis"></a>APIs

As APIs de conformidade da Microsoft 365 estão disponíveis no SDK do Microsoft Information Protection, na API do Microsoft Graph e na API da atividade de gerenciamento do Office 365. Algumas APIs de conformidade fazem parte de um novo conjunto de APIs de segurança e conformidade que habilitam os desenvolvedores para clientes do Microsoft 365, fornecedores de software independentes, integradores de sistema e provedores de serviços de segurança gerenciados para criar soluções de segurança e conformidade de alto valor.

Para saber mais sobre como acessar APIs de gráfico, confira [visão geral do Microsoft Graph](https://docs.microsoft.com/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>SDK de proteção de informações da Microsoft (MIP)

O SDK MIP expõe os serviços de rotulação e proteção dos centros de segurança e conformidade da Microsoft 365 para aplicativos e serviços de terceiros. Os desenvolvedores podem usar o SDK para criar suporte nativo para a aplicação de rótulos e proteção a arquivos. Os desenvolvedores podem determinar quais ações devem ser executadas quando rótulos específicos forem detectados e motivo de informações criptografadas de MIP.

Os casos de uso do SDK MIP de alto nível incluem:

- Um aplicativo de linha de negócios que aplica rótulos de classificação a arquivos na exportação.

- Um aplicativo de design CAD/CAM que fornece suporte nativo para rotulação MIP.

- Um agente de segurança de acesso à nuvem ou uma solução de prevenção contra perda de dados que pode criptografar dados com a proteção de informações do Azure.

Para saber mais sobre o SDK MIP, pré-requisitos, cenários adicionais e exemplos, confira [visão geral do SDK MIP](https://docs.microsoft.com/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API do Microsoft Graph para Teams DLP

[Os recursos de prevenção contra perda de dados (DLP)](dlp-microsoft-teams.md) são amplamente usados no Microsoft Teams, particularmente como as organizações mudaram para o trabalho remoto. No início do ano, [anunciamos a visualização pública](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) da API de notificação de alteração do Microsoft Graph para mensagens no Teams. Essa API permite que os desenvolvedores criem aplicativos que podem escutar mensagens do Microsoft Teams em tempo quase real e, em seguida, implementar cenários de DLP para clientes e parceiros. Além disso, a API do patch do Microsoft Graph permite que você aplique ações DLP às mensagens do teams.

Essas duas APIs formam a API do Microsoft Graph para Teams DLP. Você pode começar experimentando o aplicativo de [exemplo](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Para obter mais informações sobre os WebHooks de mensagens do Microsoft Teams, consulte a [documentação](https://docs.microsoft.com/graph/api/subscription-post-subscriptions).

Para obter os requisitos de licenciamento para o Teams DLP, consulte [o guia de licenciamento do Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API do Microsoft Graph para descoberta eletrônica (prévia)

Com a [descoberta eletrônica avançada](overview-ediscovery-20.md), as organizações podem descobrir dados em que residem e gerenciar mais fluxos de trabalho de descoberta eletrônica, com recursos inteligentes de aprendizado e análise de máquina para reduzir os dados para o conjunto relevante, tudo isso enquanto os dados permanecem dentro do limite de segurança e conformidade da Microsoft 365.

As APIs de gráfico para descoberta eletrônica avançada podem ser usadas para criar e gerenciar ocorrências, revisar conjuntos e analisar consultas de definição de forma escalonável e reproduzível. Isso permite que os clientes e parceiros criem aplicativos e fluxos de trabalho para automatizar processos comuns e repetitivos, como a criação de casos e o gerenciamento de responsáveis e isenções legais.

O primeiro conjunto de APIs de gráfico para eDiscovery está disponível em visualização pública. Planejamos adicionar mais recursos pelo final do ano civil. Para saber mais sobre essas APIs e outras atualizações para descoberta eletrônica avançada, confira este [blog](https://aka.ms/Ignite2020AeDAA).

Para obter os requisitos de licenciamento para descoberta eletrônica avançada e API, consulte a seção "descoberta eletrônica" no [Guia de licenciamento da Microsoft 365 para obter segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API do Microsoft Graph para exportação de equipes (versão prévia)

O Enterprise Information Archiving (EIA) para o Microsoft Teams é um cenário importante para nossos clientes, pois permite que eles resolvam os requisitos normativos. Além de nossos recursos internos para o arquivamento de conteúdo no Microsoft Teams, os clientes e parceiros agora podem usar as APIs de exportação do teams para resolver os cenários de integração e aplicativos personalizados. As APIs de exportação do teams suportam a exportação em massa (até 200 solicitações por segundo/por aplicativo/por locatário) de mensagens e anexos de mensagens do teams. As mensagens excluídas também podem ser acessadas pela API por até 30 dias após serem excluídas. Para obter mais informações sobre essas equipes de exportação de APIs e como usá-las em seus aplicativos, confira [exportar conteúdo com as APIs de exportação do Microsoft Teams](https://docs.microsoft.com/microsoftteams/export-teams-content).

Para obter os requisitos de licenciamento para o uso das APIs de exportação do Teams, consulte o [Guia de licenciamento da Microsoft 365 para conformidade com segurança &](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).
