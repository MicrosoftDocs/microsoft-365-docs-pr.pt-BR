---
title: Definir configurações de pesquisa e análise - Descoberta Avançada
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
ms.custom: seo-marvel-mar2020
description: Definir configurações de Descobertas Avançadas que se aplicam a todo o conjunto de revisão em um caso. Isso inclui configurações para análise e reconhecimento óptico de caracteres.
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751298"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Definir configurações de pesquisa e análise na Descoberta Avançada

Você pode definir configurações para cada ocorrência de Descoberta Descoberta Avançada para controlar a funcionalidade a seguir.

- Duplicatas próximas e threading de email

- Temas

- Consulta do conjunto de revisão gerado automaticamente

- Ignorar texto

- Reconhecimento óptico de caracteres

Para definir as configurações de pesquisa e análise para uma ocorrência:

1. Na página **Descobertas Avançadas,** selecione a ocorrência.

2. Na guia **Configurações,** em **Search & analytics,** clique em **Selecionar**.

   A página de configurações de caso é exibida. Essas configurações são aplicadas a todos os conjuntos de revisão em um caso.

   ![Definir configurações de análise e pesquisa para um caso de Descoberta Descoberta Avançada](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Duplicatas próximas e threading de email

Nesta seção, você pode definir parâmetros para detecção duplicada, detecção quase duplicada e threading de email. Para obter mais informações, consulte [Detecção duplicada próxima](near-duplicate-detection-in-advanced-ediscovery.md) e [threading de email.](email-threading-in-advanced-ediscovery.md)

- **Duplicatas próximas/threading de email:** Quando está ligado, a detecção duplicada, a detecção quase duplicada e o threading de email são incluídos como parte do fluxo de trabalho quando você executar análises nos dados em um conjunto de revisão.

- **Limite de similaridade entre documentos e emails:** Se o nível de semelhança de dois documentos estiver acima do limite, ambos os documentos serão colocados no mesmo conjunto duplicado próximo.

- **Número mínimo/máximo de palavras:** Essas configurações especificam que duplicatas próximas e análise de threading de email são executadas apenas em documentos que tenham pelo menos o número mínimo de palavras e, no máximo, o número máximo de palavras.

## <a name="themes"></a>Temas

Nesta seção, você pode definir parâmetros para temas. Para obter mais informações, consulte [Temas.](themes-in-advanced-ediscovery.md)

- **Temas:** Quando ligado, o cluster de temas é executado como parte do fluxo de trabalho quando você executar análise nos dados em um conjunto de revisão.

- **Número máximo de temas:** Especifica o número máximo de temas que podem ser gerados quando você executar a análise dos dados em um conjunto de revisão.

- **Inclua números em temas:** Quando ligado, os números (que identificam um tema) são incluídos ao gerar temas. 

- **Ajuste o número máximo de temas dinamicamente:** Em determinadas situações, talvez não haja documentos suficientes em um conjunto de revisão para produzir o número desejado de temas. Quando essa configuração está habilitada, a Descoberta Eletrônica Avançada ajusta dinamicamente o número máximo de temas, em vez de tentar impor o número máximo de temas.

## <a name="review-set-query"></a>Revisar a consulta de conjunto

Se você marcar a caixa de seleção Criar automaticamente uma pesquisa salva para Revisão após análise, a Descoberta Automática Avançada gerará automaticamente **a** consulta do conjunto de revisão chamada **Para Revisão.** 

![A consulta Para Revisão gerado automaticamente](../media/AeDForReviewQuery.png)

Essa consulta basicamente filtra itens duplicados do conjunto de revisão. Isso permite que você revise os itens exclusivos no conjunto de revisão. Essa consulta é criada somente quando você executar análises para um conjunto de revisão no caso. Para obter mais informações, sobre consultas de conjunto de revisão, consulte [Consultar os dados em um conjunto de revisão.](review-set-search.md)

## <a name="ignore-text"></a>Ignorar texto

Há situações em que determinado texto diminuirá a qualidade da análise, como avisos de isenção de responsabilidade longos que são adicionados a mensagens de email, independentemente do conteúdo do email. Se você sabe do texto que deve ser ignorado, pode excluí-lo da análise especificando a cadeia de caracteres de texto e a funcionalidade de análise (Duplicatas próximas, thread de email, temas e relevância) para a qual o texto deve ser excluído. Também há suporte para o uso de expressões regulares (RegEx) como texto ignorado. 

## <a name="optical-character-recognition-ocr"></a>Reconhecimento óptico de caracteres (OCR)

Quando essa configuração estiver tiva, o processamento de OCR será executado em arquivos de imagem. O processamento de OCR é executado nas seguintes situações:

- Quando custodiantes [e fontes de dados não custodial](non-custodial-data-sources.md) são adicionadas a uma ocorrência. O processamento de OCR é executado durante o processo de indexação avançado. Isso significa que o texto em arquivos de imagem que corresponde aos critérios de pesquisa será retornado em uma pesquisa de coleção.

- Quando o conteúdo de outras fontes de dados (que não estão associados a um custodiante e adicionado ao caso em uma fonte de dados não custodial) é adicionado a um conjunto de revisão.

Depois que os dados são adicionados a um conjunto de revisão, o texto da imagem pode ser revisado, pesquisado, marcado e analisado. Você pode exibir o texto extraído no Visualizador de texto do arquivo de imagem selecionado no conjunto de revisão. Para saber mais, confira:

- [Indexação avançada de dados custodiantes](indexing-custodian-data.md)

- [Adicionar os resultados da pesquisa a um conjunto de revisão](add-data-to-review-set.md#optical-character-recognition)

- [Tipos de arquivo de imagem com suporte](supported-filetypes-ediscovery20.md#image)
