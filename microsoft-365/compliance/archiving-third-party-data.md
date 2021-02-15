---
title: Arquivar dados de terceiros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Saiba como importar dados de terceiros de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos para caixas de correio do Microsoft 365.
ms.openlocfilehash: 18fb9c757652cbebb456da18285444272766167f
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722854"
---
# <a name="archive-third-party-data"></a>Arquivar dados de terceiros

O Microsoft 365 permite que os administradores usem conectores de dados para importar e arquivar dados de terceiros de plataformas de redes sociais, plataformas de mensagens instantâneas e plataformas de colaboração de documentos para caixas de correio em sua organização do Microsoft 365. Um dos principais benefícios de usar conectores de dados para importar e arquivar dados de terceiros no Microsoft 365 é que você pode aplicar várias soluções de conformidade do Microsoft 365 a isso depois que eles são importados. Isso ajuda a garantir que os dados que não são da Microsoft da sua organização estão em conformidade com os regulamentos e padrões que afetam sua organização.

## <a name="third-party-data-connectors"></a>Conectores de dados de terceiros

A tabela a seguir lista os conectores de dados de terceiros disponíveis no centro de conformidade do Microsoft 365. A tabela também resume as soluções de conformidade que você pode aplicar a dados de terceiros depois de importar e arquivar no Microsoft 365. Consulte a [próxima seção para](#overview-of-compliance-solutions-that-support-third-party-data) obter uma descrição mais detalhada de cada solução de conformidade e como ela pode beneficiar dados de terceiros.

> [!TIP]
> Clique no link na coluna **de** dados de terceiros para seguir as instruções passo a passo para criar um conector para esse tipo de dados.

|Dados de terceiros  |1.000.|Descoberta eletrônica  |Configurações de retenção  |Gerenciamento de registros  |Conformidade de comunicações  |Gerenciamento de risco interno  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Rede Sino <sup>1</sup>](archive-bell-network-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Mensagem da Bloomberg](archive-bloomberg-message-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Número <sup>1 da Empresa</sup>](archive-enterprise-number-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Recursos humanos (RH)](import-hr-data.md) ||||||![Marca de seleção](../media/checkmark.png)
|[Bate-papo ICE](archive-icechat-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Banco de Dados SQL do MS <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Rede O2 <sup>1</sup>](archive-o2-network-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Badging físico](import-physical-badging-data.md) ||||||![Marca de seleção](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Reuters Lidando <sup>2</sup>](archive-reutersdealing-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Salesforce <sup>2</sup>](archive-salesforcechatter-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[2 <sup></sup>](archive-symphony-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Rede TELUS <sup>1</sup>](archive-telus-network-data.md)    |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Texto delimitado <sup>2</sup>](archive-text-delimited-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Páginas da Web <sup>2</sup>](archive-webpagecapture-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Workplace from Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|[Zoom Meetings <sup>2</sup>](archive-zoommeetings-data.md)     |![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Conector de dados fornecido pela TeleMessage. Antes de poder arquivar dados no Microsoft 365, você precisa trabalhar com a TeleMessage para configurar o serviço de arquivamento para sua organização. Para obter mais informações, consulte a seção de pré-requisitos nas instruções passo a passo para esse tipo de dados.<br/><br/><sup>2</sup> Conector de dados fornecido pela Globalnet. Antes de arquivar dados no Microsoft 365, você precisa trabalhar com a Globalnet para configurar o serviço de arquivamento para sua organização. Para obter mais informações, consulte a seção de pré-requisitos nas instruções passo a passo para esse tipo de dados.

Os dados de terceiros listados na tabela anterior (exceto os dados de RH e os dados de danos físicos) são importados para as caixas de correio do usuário. As soluções de conformidade correspondentes que suportam dados de terceiros são aplicadas à caixa de correio do usuário onde os dados estão armazenados.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Visão geral das soluções de conformidade que suportam dados de terceiros

As seções a seguir descrevem algumas das coisas que as soluções de conformidade do Microsoft 365 podem ajudá-lo a gerenciar os dados de terceiros listados na tabela anterior.

### <a name="litigation-hold"></a>1.000.

Você coloca uma retenção [de litígio](create-a-litigation-hold.md) em uma caixa de correio de usuário para reter dados de terceiros. Ao criar uma espera, você pode especificar uma duração de espera (também chamada de espera baseada em *tempo)* para que os dados de terceiros excluídos e modificados sejam mantidos por um período especificado e, em seguida, excluídos permanentemente da caixa de correio. Ou você pode simplesmente reter o conteúdo indefinidamente (chamado de retenção *infinita)* ou até que a retenção de litígio seja removida.

### <a name="ediscovery"></a>Descoberta eletrônica

As três principais ferramentas de Descoberta Online no Microsoft 365 são Pesquisa de Conteúdo, Descoberta Principal e Descoberta Avançada.

- **[Pesquisa de conteúdo.](content-search.md)** Você pode usar a ferramenta de pesquisa de conteúdo para pesquisar em caixas de correio dados de terceiros que você importou. Você pode usar consultas e condições de pesquisa para restringir os resultados da pesquisa e exportar os resultados da pesquisa.

- **[Descobertas principais do eDiscovery](get-started-core-ediscovery.md).** Essa ferramenta se baseia na funcionalidade básica de pesquisa e exportação, permitindo que você crie casos que permitem controlar quem pode acessar dados de caso, colocar em espera caixas de correio de usuário ou conteúdo de caixa de correio que corresponde aos critérios de pesquisa. Isso significa que você pode colocar uma espera de Descoberta Eletrônico nos dados de terceiros que foram importados para as caixas de correio do usuário.

- **[Descobertas es avançadas.](overview-ediscovery-20.md)** Essa poderosa ferramenta expande a funcionalidade de ocorrência da Descoberta Principal, ao permitir que você adicione custodiantes a uma ocorrência, colocando os dados do custodiante em espera e carregando os dados de terceiros de um custodiante em uma revisão para análise posterior, como temas e detecção duplicada. Depois de carregar dados de terceiros em um conjunto de revisão, você pode consultar e filtre-os para um conjunto de resultados estreito.

   A Descoberta Principal e a Descoberta Avançada permitem que você gerencie dados de terceiros que possam ser relevantes para as investigações legais ou internas da sua organização.

### <a name="retention-settings"></a>Configurações de retenção

Você pode aplicar uma política [de](retention.md) retenção às caixas de correio do usuário para reter e excluir dados de terceiros (e outro conteúdo de caixa de correio) após o período de retenção expirar. Você também pode usar políticas de retenção para excluir [](disposition.md) dados de terceiros de uma determinada idade ou usar rótulos de retenção para disparar uma revisão de disposição quando o período de retenção de dados de terceiros expirar.

### <a name="records-management"></a>Gerenciamento de registros

O [recurso de gerenciamento](records-management.md) de registros no Microsoft 365 permite declarar dados de terceiros como um registro. Isso pode ser feito manualmente por usuários que aplicam um rótulo de retenção que marca os dados de terceiros em sua caixa de correio como registro. Ou você pode aplicar automaticamente rótulos de retenção identificando informações confidenciais, palavras-chave ou tipos de conteúdo em dados de terceiros.

### <a name="communication-compliance"></a>Conformidade de comunicações

Você pode usar [a conformidade de](communication-compliance.md) comunicação para examinar dados de terceiros para garantir que eles estão em conformidade com os padrões de dados da sua organização. Você pode fazer isso detectando, capturando e tomando ações de correção para mensagens inadequadas em sua organização. Por exemplo, você pode monitorar os dados de terceiros importados para linguagem ofensiva, informações confidenciais e conformidade regulamentar.

### <a name="insider-risk-management"></a>Gerenciamento de risco interno

Sinais de dados de terceiros, como dados seletivos [](insider-risk-management.md) de RH, podem ser usados pela solução de gerenciamento de riscos internos para minimizar riscos internos, deixando que você detecte, investigue e aja em atividades arriscadas em sua organização. Por exemplo, os dados importados pelo conector de dados de RH são usados como indicadores de risco para ajudar a detectar o roubo de dados de funcionários.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Trabalhar com um parceiro da Microsoft para arquivar dados de terceiros

Outra opção para importar e arquivar dados de terceiros é sua organização trabalhar com um Microsoft Partner. Se um tipo de dados de terceiros não for compatível com os conectores de dados disponíveis no centro de conformidade da Microsoft, você poderá trabalhar com um parceiro que possa fornecer um conector personalizado que será configurado para extrair itens da fonte de dados de terceiros regularmente e, em seguida, conectar-se à nuvem da Microsoft por uma API de terceiros e importar esses itens para o Microsoft 365. O conector parceiro também converte o conteúdo de um item da fonte de dados de terceiros em uma mensagem de email e o importa para uma caixa de correio no Microsoft 365.

Para uma lista de parceiros com quem você pode trabalhar e o processo passo a passo para esse método, consulte Trabalhar com um parceiro para arquivar dados de terceiros no [Microsoft 365.](work-with-partner-to-archive-third-party-data.md)
