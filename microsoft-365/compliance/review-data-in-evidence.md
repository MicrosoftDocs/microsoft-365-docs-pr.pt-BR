---
title: Revise os dados em evidência
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 18d67983d4e5e934e606944c1502dd76331812a3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597628"
---
# <a name="review-the-data-in-evidence"></a>Revise os dados em evidência

Os dados em um conjunto de evidências em uma investigação de dados é um instantâneo dos resultados da pesquisa que você coletou e adicionou ao conjunto de evidências. Quando você adiciona resultados de pesquisa a evidências, um processo é disparado para extrair arquivos, metadados e texto dos itens retornados pela pesquisa. Em seguida, a ferramenta de investigações de dados (visualização) cria um novo índice (por um processo chamado *indexação avançada*) de todos os dados e adiciona a uma evidência definida na guia **evidência** . 

Para investigações temporais, isso permite que você contenha rapidamente o ambiente, excluindo os dados reais derramados ou mal-intencionados localizados na fonte de dados original e, ao mesmo tempo, permitindo que você investigue a evidência recriada em um ambiente em quarentena, que, nesse caso, são os dados copiados para o conjunto de evidências). Depois que as evidências são coletadas e adicionadas ao conjunto de evidências, você pode revisar documentos individuais no formato nativo, no formato de texto ou em um formato Near-nativo que você pode usar para anotar e redigir documentos. Além disso, você pode executar consultas para restringir o conjunto de dados por intervalo de tempo, tipos de arquivo, proprietários de dados e muitas outras propriedades e condições de pesquisa. Por exemplo, usando as condições autor, remetente ou destinatário, você pode identificar rapidamente as pessoas estão envolvidas no incidente e, se algum dado da sua organização tiver sido compartilhado com usuários externos. Para obter mais informações sobre como pesquisar dados em um conjunto de evidências, consulte [Query The data in Evidence](evidence-query.md).

Para agrupar documentos e obter mais assistência para revisão, selecione um conjunto de evidências na guia **evidência** e clique em **gerenciar evidência**. No bloco de **análise** , clique em **Recompilar análise de todo o conjunto**. Isso executará análises avançadas, como detecção de duplicidades, encadeamento de emails e análise de tema. Posteriormente, você pode ver os temas gerais dos dados e também organizar documentos por threads de email, próximos duplicatas e duplicatas exatas para ajudar sua investigação. Para obter mais informações, consulte [executar análise para investigar mais rápido](run-analytics-to-investigate-faster.md).

## <a name="view-documents-in-evidence"></a>Exibir documentos em evidência

As investigações de dados (visualização) permitem exibir conteúdo em vários visualizadores diferentes, com cada visualizador com uma finalidade diferente. Esses visualizadores são:

- Metadados de arquivo
- Modo de exibição nativo
- Exibição de texto
- Modo de anotações

Para acessar qualquer um desses visualizadores, basta selecionar um documento em um conjunto de evidências.

## <a name="file-metadata"></a>Metadados de arquivo

Este modo de exibição exibe várias propriedades de metadados associadas ao documento selecionado. Você pode ativar e desativar este modo de exibição clicando em **metadados de arquivo**. Ao revisar um documento, você pode exibir os metadados do arquivo e ainda alterar entre os diferentes visualizadores.

Veja um exemplo dos metadados de arquivo para um documento. Para obter mais informações sobre os campos de metadados, consulte [Document Metadata Fields in data investigações (Preview)](document-metadata-fields.md).

![Painel metadados de arquivo](media/Reviewimage2.png)

## <a name="native-view"></a>Modo de exibição nativo

O visualizador nativo exibe o modo de exibição mais preciso de um documento no formato nativo. O modo de exibição nativo é suportado para centenas de tipos de arquivo e deve exibir documentos na experiência nativa verdadeiramente mais verdadeira possível. Para arquivos do Microsoft Office, o visualizador nativo usa a versão da Web dos aplicativos do Office. Isso permite que você exiba conteúdo como comentários em diferentes documentos do Office, fórmulas e linhas/colunas ocultas no Excel e o modo de anotações no PowerPoint.

![Modo de exibição nativo
](media/Reviewimage3.png)

## <a name="text-view"></a>Exibição de texto

O Visualizador de texto fornece um modo de exibição do texto extraído de um arquivo. Ele ignora todas as imagens e formatação inseridas, mas esse modo de exibição é muito útil se você estiver tentando rapidamente revisar e entender o conteúdo em um documento. O modo de exibição de texto também inclui estes recursos:

  - Um contador de linhas, que facilita a referência a partes específicas de um documento.

  - Visitas de pesquisa realçando que realçar termos no documento e no ScrollBar

  - Um modo de exibição de comparação fornece um modo de exibição de comparação que realça as diferenças de texto ao exibir documentos usando o painel **próximo duplicatas** .

**Exemplo de contador de linha e realce de ocorrência de pesquisa em texto e ScrollBar**

![Exibição de texto
](media/Reviewimage4.png)

**Exemplo da exibição de comparação**

![Exibição de comparação
](media/Reviewimage5.png)

## <a name="annotate-view"></a>Modo de anotações

O modo de anotações fornece recursos que permitem que você aplique marcação em um documento durante o processo de revisão; Isso inclui as seguintes ferramentas:

  - **Redação de área** – você pode desenhar uma caixa opaca no documento que oculta conteúdo confidencial.

  - **Lápis** – você pode desenhar em um documento para dar atenção a certas partes do conteúdo

  - **Selecionar anotações** -você pode selecionar e excluir anotações em um documento.

  - **Alternar transparência da anotação** – é possível alternar a transparência de anotações (entre opaco e semi-transparente) para que você possa exibir o conteúdo por trás da anotação. Isso inclui a alternância da transparência de anotações e redaçãos de lápis.

O modo de anotações também fornece a seguinte funcionalidade de navegação:

  - **Página anterior**, **próxima página**e **ir para** controles de navegação de página para usar para documentos de várias páginas.

  - **Zoom** – aumenta ou diminui o tamanho dos documentos no modo de anotações.

  - **Girar** – girar documentos no sentido horário.

  - **Pesquisa** – pesquise palavras-chave em um documento e, em seguida, use os controles anteriores e próximos para exibir os acertos (que são realçados) no documento.

**Exemplo de exibição de anotações**

![Modo de anotações](media/Reviewimage1.png)

> [!NOTE]
> As anotações são aplicadas a uma cópia do documento que foi adicionado ao conjunto de evidências. Os documentos originais no serviço ativo não estão anotados.
