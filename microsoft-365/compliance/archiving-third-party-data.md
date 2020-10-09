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
ms.openlocfilehash: 7ce515e99e4ddded1cfeccd346bd33a445fe17d7
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398532"
---
# <a name="archive-third-party-data"></a>Arquivar dados de terceiros

A Microsoft 365 permite que os administradores usem os conectores de dados para importar e arquivar dados de terceiros de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos, para caixas de correio em sua organização do Microsoft 365. Um dos principais benefícios do uso de conectores de dados para importar e arquivar dados de terceiros no Microsoft 365 é que você pode aplicar várias soluções de conformidade da Microsoft 365 para isso após sua importação. Isso ajuda a garantir que os dados não-Microsoft da sua organização estejam em conformidade com as regulamentações e os padrões que afetam sua organização.

## <a name="third-party-data-connectors"></a>Conectores de dados de terceiros

A tabela a seguir lista os conectores de dados de terceiros disponíveis no centro de conformidade da Microsoft 365. A tabela também resume as soluções de conformidade que podem ser aplicadas a dados de terceiros após a importação e o arquivamento no Microsoft 365. Consulte a [próxima seção](#overview-of-compliance-solutions-that-support-third-party-data) para obter uma descrição mais detalhada de cada solução de conformidade e como ela pode beneficiar dados de terceiros.

> [!TIP]
> Clique no link na coluna **dados de terceiros** para ir para as instruções passo a passo para criar um conector para esse tipo de dados.

|Dados de terceiros  |Retenção de litígio|Descoberta Eletrônica  |Configurações de retenção  |Gerenciamento de registros  |Conformidade em comunicações  |Gerenciamento de risco interno  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[EM&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Mensagem da Bloomberg](archive-bloomberg-message-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Número de empresa <sup>1</sup>](archive-enterprise-number-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Conexão FX <sup>2</sup>](archive-fxconnect-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Recursos humanos (RH)](import-hr-data.md) ||||||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[Bate-papo ICE](archive-icechat-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Rede <sup>1</sup> do O2](archive-o2-network-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Símbolos físico](import-physical-badging-data.md) ||||||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[Reuters EIKON <sup>2</sup>](archive-reuterseikon-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Margem de atraso <sup>2</sup>](archive-slack-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Symphony <sup>2</sup>](archive-symphony-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Rede <sup>1</sup> do Telus](archive-telus-network-data.md)    |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Texto delimitado <sup>2</sup>](archive-text-delimited-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Equipes do WebEx <sup>2</sup>](archive-webexteams-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Local de trabalho do Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Compromissos de zoom <sup>2</sup>](archive-zoommeetings-data.md)     |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
||||||||

> [!NOTE]
> <sup>1</sup> este conector de dados é fornecido por telemessage. Antes de poder arquivar dados no Microsoft 365, você tem que trabalhar com Telemensagem para configurar o serviço de arquivamento para sua organização. Para obter mais informações, consulte a seção de pré-requisito nas instruções passo a passo para esse tipo de dados.<br/><br/><sup>2</sup> conector fornecido pelo Globanet. Antes de poder arquivar dados no Microsoft 365, você tem que trabalhar com o Globanet para configurar o serviço de arquivamento para sua organização. Para obter mais informações, consulte a seção de pré-requisito nas instruções passo a passo para esse tipo de dados.

Os dados de terceiros listados na tabela anterior (exceto para dados de RH e dados de símbolos físicos) são importados para caixas de correio do usuário. As soluções de conformidade correspondentes que dão suporte a dados de terceiros são aplicadas à caixa de correio do usuário onde os dados estão armazenados.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Visão geral das soluções de conformidade que dão suporte a dados de terceiros

As seções a seguir descrevem algumas das coisas que as soluções de conformidade da Microsoft 365 podem ajudá-lo a gerenciar os dados de terceiros listados na tabela anterior.

### <a name="litigation-hold"></a>Retenção de litígio

Você coloca uma [retenção de litígio](create-a-litigation-hold.md) em uma caixa de correio de usuário para manter os dados de terceiros. Ao criar uma retenção, você pode especificar uma duração de retenção (também chamada de *retenção baseada em tempo*), para que os dados de terceiros excluídos e modificados sejam mantidos por um período especificado e, em seguida, excluídos permanentemente da caixa de correio. Ou você pode simplesmente reter o conteúdo indefinidamente (chamado de *retenção infinita*) ou até que a retenção de litígio seja removida.

### <a name="ediscovery"></a>Descoberta Eletrônica

As três principais ferramentas de descoberta eletrônica no Microsoft 365 são pesquisa de conteúdo, descoberta eletrônica principal e descoberta eletrônica avançada.

- **[Pesquisa de conteúdo](content-search.md).** Você pode usar a ferramenta de pesquisa de conteúdo para pesquisar caixas de correio de dados de terceiros que você importou. Você pode usar as condições e consultas de pesquisa para restringir os resultados da pesquisa e exportar os resultados da pesquisa.

- **[Descoberta eletrônica principal](get-started-core-ediscovery.md).** Essa ferramenta se baseia na funcionalidade básica de pesquisa e exportação permitindo que você crie casos que permitam que você controle quem pode acessar os dados de caso, coloque um bloqueio de caixas de correio de usuário ou conteúdo de caixa de correio que corresponda aos critérios de pesquisa. Isso significa que você pode colocar um controle de descoberta eletrônica em dados de terceiros que foram importados para caixas de correio de usuários.

- **[Descoberta eletrônica avançada](overview-ediscovery-20.md).** Essa poderosa ferramenta expande a funcionalidade de casos da descoberta eletrônica principal, permitindo que você adicione os responsáveis a um caso, colocando os dados dos responsáveis em espera e, em seguida, carregando dados de terceiros de um dos responsáveis em uma revisão para análise adicional, como temas e detecção de duplicidades. Depois de carregar dados de terceiros em um conjunto de análise, você pode consultá-los e filtrá-los em um conjunto de resultados estreito.

   A descoberta eletrônica principal e a descoberta eletrônica avançada permitem gerenciar dados de terceiros que podem ser relevantes para as investigações legais ou internas da sua organização.

### <a name="retention-settings"></a>Configurações de retenção

É possível aplicar uma [política de retenção](retention.md) a caixas de correio de usuário para manter e excluir dados de terceiros (e outros conteúdos de caixa de correio) após o período de retenção expirar. Você também pode usar as políticas de retenção para excluir dados de terceiros de uma determinada idade ou [usar rótulos de retenção para acionar uma revisão de disposição](disposition.md) quando o período de retenção de dados de terceiros expirar.

### <a name="records-management"></a>Gerenciamento de registros

O recurso de [Gerenciamento de registros](records-management.md) no Microsoft 365 permite que você declare dados de terceiros como um registro. Isso pode ser feito manualmente por usuários que aplicam um rótulo de retenção que marca dados de terceiros em suas caixas de correio como registro. Ou você pode aplicar automaticamente os rótulos de retenção identificando informações confidenciais, palavras-chave ou tipos de conteúdo em dados de terceiros.

### <a name="communication-compliance"></a>Conformidade em comunicações

Você pode usar a [conformidade de comunicação](communication-compliance.md) para examinar dados de terceiros para garantir que eles sejam compatíveis com os padrões de dados da sua organização. Você pode fazer isso ao detectar, capturar e realizar ações de correção para mensagens inadequadas em sua organização. Por exemplo, você pode monitorar os dados de terceiros que você importou para uma linguagem ofensiva, informações confidenciais e conformidade normativa.

### <a name="insider-risk-management"></a>Gerenciamento de risco interno

Os sinais de dados de terceiros, como dados de RH seletivos, podem ser usados pela solução de [Gerenciamento de riscos Insider](insider-risk-management.md) para minimizar os riscos internos, permitindo que você detecte, investigue e atue em atividades arriscadas em sua organização. Por exemplo, os dados importados pelo conector de dados de RH são usados como indicadores de risco para ajudar a detectar a parte do roubo de dados de funcionários.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Trabalhar com um parceiro da Microsoft para arquivar dados de terceiros

Outra opção para importar e arquivar dados de terceiros é para sua organização para trabalhar com um parceiro da Microsoft. Se não houver suporte para um tipo de dados de terceiros nos conectores de dados disponíveis no centro de conformidade da Microsoft, você poderá trabalhar com um parceiro que pode fornecer um conector personalizado que será configurado para extrair itens da fonte de dados de terceiros regularmente e, em seguida, conectar-se ao Microsoft Cloud por uma API de terceiros e importar esses itens para o Microsoft 365. O conector de parceiro também converte o conteúdo de um item da fonte de dados de terceiros em uma mensagem de email e, em seguida, importa-o para uma caixa de correio no Microsoft 365.

Para obter uma lista de parceiros com os quais você pode trabalhar e o processo passo a passo desse método, confira [trabalhar com um parceiro para arquivar dados de terceiros no Microsoft 365](work-with-partner-to-archive-third-party-data.md).
