---
title: Análise do uso do modelo de compreensão de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda a aplicar um rótulo de retenção a um modelo de compreensão de documentos
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080406"
---
# <a name="document-understanding-model-usage-analytics"></a>Análise do uso do modelo de compreensão de documentos

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


O centro de conteúdo do Microsoft SharePoint Syntex disponibiliza a você análises de uso de modelos para fornecer mais informações de como seus modelos publicados no centro de conteúdo estão sendo usados. A seção <b>Como está o desempenho de seus modelos nos últimos 30 dias</b> do centro de conteúdo inclui uma distribuição de 30 dias de dados de análise de uso fornecidos nos gráficos e listas a seguir:

- Classificação por modelo
- Classificação por biblioteca
- Uso de modelo 

 ![Análise de modelos](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>Distribuição dos dados de uso do modelo no centro de conteúdo padrão

No SharePoint Syntex, o centro de conteúdo padrão é criado durante a instalação. Centros de conteúdo adicionais também podem ser criados conforme necessário. Por exemplo, os departamentos podem criar seus próprios centros de conteúdo para criar e gerenciar seus modelos. 

Em relação à análise de uso do modelo, observe que:

- Seu centro de conteúdo padrão mostrará a análise de uso do modelo para todos os centros de conteúdo e modelos na sua organização, incluindo aqueles criados em centros de conteúdo adicionais. Isso oferece aos gerentes de conteúdo e a outros participantes um portal centralizado para gerenciar e supervisionar os centros de conteúdo e modelos em toda a empresa.  
- Outros centros de conteúdo mostrarão somente a análise de uso do modelo para os modelos que foram criados neles. Isso fornece informações aos gerentes de conteúdo sobre os dados de uso apenas dos modelos com os quais estão preocupados.


## <a name="classification-by-model"></a>Classificação por modelo

   ![Porcentagem total dos modelos](../media/content-understanding/total-model-percentage.png) </br>

O gráfico de pizza **Classificação por modelo** exibe quais modelos classificaram a maioria dos arquivos. Ele exibe cada modelo publicado como uma porcentagem do total de arquivos processados por todos os modelos publicados no centro de conteúdo.

Cada modelo também mostra a **Taxa de conclusão**, a porcentagem de arquivos carregados que foram analisados com êxito pelo modelo. Uma taxa de conclusão insuficiente pode significar que há problemas com o modelo ou com os arquivos que estão sendo analisados.

## <a name="classification-by-library"></a>Classificação por biblioteca

   ![Arquivos processados](../media/content-understanding/files-processed-over-time.png) </br>

O gráfico de barras **Classificação por biblioteca** ajuda a determinar a eficácia da compreensão de conteúdo em sua organização.  Ele mostra não apenas o número de arquivos processados ao longo do tempo para cada modelo, mas também mostra a biblioteca de documentos para a qual o modelo foi aplicado.


## <a name="model-usage"></a>Uso de modelo

A lista Uso do Modelo mostrará a análise de uso dos modelos criados por meio do centro de conteúdo.  

> [!NOTE]
> Se você estiver no centro de conteúdo padrão e tiver centros de conteúdo adicionais em sua organização, a lista de uso do modelo será agrupada por centro de conteúdo.

Cada modelo na lista de uso do modelo mostrará os dados de uso:

- Contagem de itens classificados: Número de arquivos processados pelo modelo.
- Pontuação média de confiança: Pontuação de precisão média do modelo quando executado contra arquivos.
- URL da lista de destino: A biblioteca de documentos do Microsoft Office SharePoint Online à qual o modelo é aplicado.



## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Criar um extrator](create-an-extractor.md)

[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).

[Criar um modelo de processamento de formulário](create-a-form-processing-model.md)  
