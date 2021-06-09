---
title: Configurar configurações de pesquisa e análise - Advanced eDiscovery
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
description: Configure Advanced eDiscovery configurações que se aplicam a todo o conjunto de revisão em um caso. Isso inclui configurações para análise e reconhecimento óptico de caracteres.
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751298"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Configurar configurações de pesquisa e análise em Advanced eDiscovery

Você pode configurar configurações para cada Advanced eDiscovery caso para controlar a funcionalidade a seguir.

- Duplicatas próximas e threading de email

- Temas

- Consulta de conjunto de revisão autogerada

- Ignorar texto

- Reconhecimento óptico de caracteres

Para definir as configurações de pesquisa e análise de um caso:

1. Na página **Descoberta Eletrônica Avançada**, selecione o caso.

2. Na guia **Configurações**, em **Pesquisa e análise**, clique em **Selecionar**.

   A página de configurações de caso é exibida. Essas configurações são aplicadas a todos os conjuntos de revisão em um caso.

   ![Configurar configurações de análise e pesquisa para um Advanced eDiscovery caso](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Duplicatas próximas e threading de email

Nesta seção, você pode definir parâmetros para detecção duplicada, detecção quase duplicada e threading de email. Para obter mais informações, consulte [Near duplicate detection](near-duplicate-detection-in-advanced-ediscovery.md) and Email [threading](email-threading-in-advanced-ediscovery.md).

- **Quase duplicatas/threads de email:** Quando ligado, a detecção duplicada, a detecção quase duplicada e o threading de email são incluídos como parte do fluxo de trabalho quando você executar análises nos dados em um conjunto de revisão.

- **Limite de semelhança de documentos e emails:** Se o nível de semelhança de dois documentos estiver acima do limite, ambos os documentos serão colocados no mesmo conjunto quase duplicado.

- **Número mínimo/máximo de palavras:** Essas configurações especificam que quase duplicatas e análise de threading de email são executadas somente em documentos que tenham pelo menos o número mínimo de palavras e, no máximo, o número máximo de palavras.

## <a name="themes"></a>Temas

Nesta seção, você pode definir parâmetros para temas. Para obter mais informações, consulte [Temas](themes-in-advanced-ediscovery.md).

- **Temas:** Quando ligado, o cluster de temas é executado como parte do fluxo de trabalho quando você executar análises nos dados em um conjunto de revisão.

- **Número máximo de temas:** Especifica o número máximo de temas que podem ser gerados quando você executar análises nos dados em um conjunto de revisão.

- **Incluir números em temas:** Quando ligado, os números (que identificam um tema) são incluídos ao gerar temas. 

- **Ajuste o número máximo de temas dinamicamente:** Em determinadas situações, talvez não haja documentos suficientes em um conjunto de revisão para produzir o número desejado de temas. Quando esta configuração está habilitada, a Descoberta Eletrônica Avançada ajusta dinamicamente o número máximo de temas em vez de tentar impor o número máximo de temas. 

## <a name="review-set-query"></a>Consulta de conjunto de revisão

Se você selecionar **a** caixa de seleção Criar automaticamente uma pesquisa salva para Revisão após análise, Advanced eDiscovery automaticamente gera a consulta de conjunto de revisão chamada **For Review.** 

![A consulta para revisão automática](../media/AeDForReviewQuery.png)

Essa consulta basicamente filtra itens duplicados do conjunto de revisão. Isso permite que você revise os itens exclusivos no conjunto de revisão. Essa consulta é criada apenas quando você executa uma análise de um conjunto de revisão no caso. Para obter mais informações sobre consultas de conjunto de revisão, consulte [Consulta dos dados em um conjunto de revisão](review-set-search.md).

## <a name="ignore-text"></a>Ignorar texto

Há situações em que determinado texto diminuirá a qualidade da análise, como avisos de isenção de responsabilidade longos que são adicionados a mensagens de email, independentemente do conteúdo do email. Se conhece texto que deve ser ignorado, você pode excluí-lo da análise ao especificar a cadeia de texto e a funcionalidade de análise (duplicadas próximas, threading de email, Temas e Relevância) que o texto deve ser excluído. O uso de expressões regulares (RegEx) como texto ignorado também é suportado. 

## <a name="optical-character-recognition-ocr"></a>Reconhecimento óptico de caracteres (OCR)

Quando essa configuração estiver configurada, o processamento OCR será executado em arquivos de imagem. O processamento OCR é executado nas seguintes situações:

- Quando os custodiantes e fontes de dados não [custodiais](non-custodial-data-sources.md) são adicionados a um caso. O processamento do OCR é realizado durante o processo de indexação avançada. Isso significa que o texto em arquivos de imagem que corresponde aos critérios de pesquisa será retornado em uma pesquisa de coleção.

- Quando o conteúdo de outras fontes de dados (que não estão associados a um custodiante e adicionado ao caso em uma fonte de dados não custodiada) é adicionado a um conjunto de revisão.

Depois que os dados são adicionados a um conjunto de revisão, o texto da imagem pode ser revisado, pesquisado, marcado e analisado. Você pode exibir o texto extraído no visualizador de texto do arquivo de imagem selecionado no conjunto de revisão. Para saber mais, confira:

- [Indexação avançada de dados custodiantes](indexing-custodian-data.md)

- [Adicionar os resultados da pesquisa a um conjunto de revisão](add-data-to-review-set.md#optical-character-recognition)

- [Tipos de arquivo de imagem com suporte](supported-filetypes-ediscovery20.md#image)
