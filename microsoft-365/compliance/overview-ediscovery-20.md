---
title: Visão geral da solução de descoberta eletrônica avançada no Microsoft 365
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
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Este artigo fornece uma visão geral da descoberta eletrônica avançada no Microsoft 365, uma ferramenta para investigações internas e externas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95c864b9e2222000b1114ae42dbbb5705228d531
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944339"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Visão geral da solução de descoberta eletrônica avançada no Microsoft 365

A solução de descoberta eletrônica avançada no Microsoft 365 baseia-se nos recursos de descoberta eletrônica e análise existentes no Office 365. Essa nova solução, chamada de *descoberta eletrônica avançada* , fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar conteúdo que responde às investigações internas e externas da sua organização. Também permite que as equipes jurídicas gerenciem todo o fluxo de trabalho de notificação de retenção legal para se comunicarem com os responsáveis envolvidos em um caso. 

> [!NOTE]
> A descoberta eletrônica avançada requer uma assinatura empresarial do Office 365 ou do Microsoft 365 e5. Para obter mais informações sobre licenciamento de descoberta eletrônica avançada, consulte [o guia de licenciamento do Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-ediscovery).

## <a name="alignment-with-edrm"></a>Alinhamento com EDRM

O fluxo de trabalho interno de descoberta eletrônica avançada se alinha com o processo de descoberta eletrônica descrito pelo modelo de referência de descoberta eletrônica (EDRM). 

![O modelo de referência de descoberta eletrônica (EDRM)](../media/EDRMv1.png)

(Imagem de origem cortesia de edrm.net. A imagem de origem foi disponibilizada sob a licença do Creative Commons 3,0 Unported License.)

Em um nível alto, veja como a descoberta eletrônica avançada é compatível com o fluxo de trabalho do EDRM:

- **Identificador.** Após identificar as possíveis pessoas de interesse em uma investigação, você poderá adicioná-las como responsáveis (também chamados de *responsáveis por dados* , pois elas podem ter informações relevantes para a investigação) a uma ocorrência de descoberta eletrônica avançada. Depois que os usuários são adicionados como responsáveis, é fácil preservar, coletar e revisar documentos de responsáveis.

- **Preservação.** Para preservar e proteger dados relevantes para uma investigação, a descoberta eletrônica avançada permite que você coloque um controle legal nas fontes de dados associadas aos responsáveis em um caso. Você também pode colocar dados não custodial em espera. A descoberta eletrônica avançada também tem um fluxo de trabalho de comunicações interno para que você possa enviar notificações de retenção legal para os responsáveis e controlar suas confirmações.

- **Coletânea.** Após identificar (e preservar) as fontes de dados relevantes para a investigação, você pode usar a ferramenta de pesquisa interna na pesquisa de descoberta eletrônica avançada e coletar dados ao vivo das fontes de dados do custodial (e fontes de dados não-custodial, se aplicável) que podem ser relevantes para o caso.

- **Processe.** Após coletar todos os dados relevantes para o caso, a próxima etapa será processá-lo para revisão e análise mais detalhada. Na descoberta eletrônica avançada, os dados no local que você identificou na fase de coleta são copiados para um local de armazenamento do Azure (chamado de *conjunto de revisão* ), que fornece uma exibição estática dos dados de caso. 

- **Exame.** Depois que os dados forem adicionados a um conjunto de revisão, você poderá exibir documentos específicos e executar outras consultas para reduzir os dados para o que é mais relevante para o caso. Além disso, pode anotar e marcar documentos específicos.

- **Analisa.** A descoberta eletrônica avançada fornece uma ferramenta de análise integrada que ajuda você a buscar mais dados do conjunto de revisão que você determinar não é relevante para a investigação. Além de reduzir o volume de dados relevantes, a descoberta eletrônica avançada também ajuda você a salvar os custos de análise jurídica, permitindo que você organize o conteúdo para tornar o processo de revisão mais fácil e eficiente.

- **Produção** e **apresentação.** Quando estiver pronto, você pode exportar documentos de um conjunto de revisão para análise jurídica. Você pode exportar documentos em seu formato nativo ou em um formato especificado pelo EDRM para que eles possam ser importados para aplicativos de revisão de terceiros.

## <a name="advanced-ediscovery-architecture"></a>Arquitetura de descoberta eletrônica avançada

Este é um diagrama avançado de arquitetura de descoberta eletrônica que mostra o fluxo de trabalho de ponta a ponta em um ambiente de Geografia único e em um ambiente multigeográfico e o fluxo de dados de ponta a ponta que é alinhado com o EDRM.

[![Cartaz de modelo: arquitetura de descoberta eletrônica avançada no Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Exibir como uma imagem](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Baixar como um arquivo PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Baixar como um arquivo do Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Para obter mais informações sobre o fluxo de trabalho de ponta a ponta na descoberta eletrônica avançada, consulte este [vídeo da Microsoft mecânica](https://go.microsoft.com/fwlink/?linkid=2066133).

As seções a seguir descrevem cada etapa no fluxo de trabalho interno na descoberta eletrônica avançada.

## <a name="managing-custodians-and-non-custodial-data-sources"></a>Gerenciando os responsáveis e as fontes de dados não custodial

Use a guia **fontes** para adicionar e gerenciar as pessoas que você identificou como pessoas de interesse no caso e outras fontes de dados que podem não estar associadas a um. Ao adicionar qualificações ou fontes de dados não-custodial, você pode rapidamente realizar ações como colocar um bloqueio legal em fontes de dados não-custodial, comunicar-se com os responsáveis e Pesquisar fontes de dados de usuários não custodial para coletar conteúdo relevante para o caso. À medida que o caso avança, é fácil adicionar novos responsáveis ou fontes de dados não custodial ou liberá-los do caso. Para obter mais informações, consulte [trabalhar com os responsáveis na descoberta eletrônica avançada](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Gerenciando notificações de retenção legal

Use a guia **comunicações** para gerenciar o processo de comunicação com os responsáveis no caso. Um aviso de retenção legal instrui os responsáveis a preservar qualquer conteúdo que seja relevante para o caso. As equipes jurídicas devem ser capazes de rastrear os avisos que foram recebidos, lidos e confirmados por responsáveis. O fluxo de trabalho de comunicações em descoberta eletrônica avançada permite que você crie e envie notificações iniciais, lembretes, avisos de lançamento e escalonamentos se os responsáveis não conseguirem confirmar uma notificação de bloqueio. Para obter mais informações, consulte [trabalhar com comunicações na descoberta eletrônica avançada](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Gerenciando preservação de conteúdo

Ao adicionar um membro a um caso, você pode colocar uma retenção em dados de custodial. Use a guia **isenções** para gerenciar a retenção criada ao adicionar os responsáveis e para gerenciar outros bloqueios legais associados ao caso; por exemplo, você pode identificar e colocar uma retenção em fontes de dados não custodial. Você também pode editar qualquer isenção no caso e torná-lo um bloqueio baseado em consulta para preservar apenas o conteúdo que corresponde à consulta. Por exemplo, você pode adicionar um intervalo de datas à isenção para que apenas o conteúdo criado em uma data específica seja rangedo em preservado. Você também pode obter estatísticas sobre o conteúdo que está em espera, remover a retenção após ela não ser mais relevante para o caso ou excluí-la. Para obter mais informações, consulte [gerenciar isenções na descoberta eletrônica avançada](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indexando dados de responsáveis

Quando você adiciona um Objecte as fontes de dados do custodial correspondentes a um caso, qualquer item parcialmente indexado de uma fonte de dados do responsáveis é reindexado por um processo chamado *indexação avançada*. Isso permite que o conteúdo do custodial, como imagens, tipos de arquivo não suportados, e outro conteúdo potencialmente não indexado seja totalmente pesquisável quando você executar pesquisas para coletar dados para o caso. Use a guia **processamento** para monitorar o status de erros de indexação avançada e de processamento de correção usando um processo chamado *correção de erros*. Para obter mais informações, consulte [corrigir erros de processamento em descoberta eletrônica avançada](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Coletar dados de ocorrência

Use a guia **pesquisas** para criar pesquisas a fim de Pesquisar as fontes de dados custodial e não custodial no local para o conteúdo relevante para o caso. Você pode criar e executar pesquisas baseadas em consulta (usando palavras-chave e condições) para identificar um conjunto de mensagens e documentos de email que são relevantes para o caso e que você deseja revisar e analisar em etapas subsequentes no fluxo de trabalho de descoberta eletrônica. Você pode criar uma ou mais pesquisas associadas à ocorrência. Você também pode usar a ferramenta de pesquisa para visualizar documentos de amostra e exibir estatísticas de pesquisa para ajudá-lo a refinar e aprimorar os resultados da pesquisa. Depois que você estiver satisfeito com os resultados da pesquisa contiver todos os dados relevantes para o caso, adicione os resultados da pesquisa a um conjunto de revisão para análise, análise e remoção posterior. Para obter mais informações, consulte [coletar dados por um caso na descoberta eletrônica avançada](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Revisando e analisando dados de caso

Use a guia **conjuntos de revisão** para analisar e analisar o conteúdo que você coletou do sistema em tempo real e adicionado a um conjunto de revisão. Um *conjunto de revisão* é uma coleção estática desses dados (em outras palavras, uma cópia offline de dados) de dados do custodial (e, se aplicável, dados não custodial) que você coletou na fase anterior do fluxo de trabalho de descoberta eletrônica. Quando você adiciona resultados de pesquisa a um conjunto de revisão, um processo é disparado que extrai arquivos de contêineres, extrai metadados e extrai texto. Quando esse processo é concluído, o sistema cria um novo índice de todos os dados coletados de responsáveis e os adiciona ao conjunto de revisão. Depois que os dados são adicionados ao conjunto de revisão, você pode executar mais consultas para restringir os dados de caso, exibir dados como texto ou no formato de arquivo nativo, e anotar, redigir e marcar documentos no conjunto de revisão. Você também pode executar análises avançadas, como identificar duplicação de documentos, threads de email e temas. Após a remoção dos dados para o que for relevante para o caso, você pode baixar documentos diretamente ou exportá-los junto com metadados, anotações e marcas de arquivo. Para saber mais, confira:

- [Exibir documentos em um conjunto de revisão](view-documents-in-review-set.md)

- [Consultar os dados em um conjunto de revisão](review-set-search.md)

- [Marcar documentos em um conjunto de revisão](tagging-documents.md)

- [Analisar dados em um conjunto de revisão](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Exportando dados para revisão e apresentação

Depois de exportar os dados de um conjunto de revisão, use a guia **exportações** para gerenciar um trabalho de exportação e baixar dados de um conjunto de revisão. Quando um conjunto de análise é exportado, os dados são carregados para um local de armazenamento fornecido pela Microsoft (ou um local de armazenamento do Azure gerenciado por sua organização). Após ser carregado para o Azure, ele é e está disponível para download para um computador local. Você pode obter a chave de avaliação de armazenamento necessária para baixar os dados exportados **na guia exportações** . Para obter mais informações, consulte [exportar dados de caso na descoberta eletrônica avançada](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Gerenciando trabalhos

Use a guia **trabalhos** para monitorar processos de execução longa para tarefas relacionadas a casos que você tenha iniciado. Entre os exemplos de trabalhos estão relacionados à reindexação, pesquisa e exportação de dados de caso. Por exemplo, se você criar uma pesquisa na guia **pesquisas** que inclui várias fontes de dados, o status desse processo de pesquisa será exibido na guia **trabalhos** . Para obter mais informações, consulte [gerenciar trabalhos na descoberta eletrônica avançada](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configurando as configurações de caso

Use a guia **configurações** para definir as configurações em todo o caso. Isso inclui adicionar membros a um caso, fechar ou excluir uma ocorrência e definir as configurações de pesquisa e análise.
