---
title: Etapa 1. Use SharePoint Syntex para identificar arquivos de contrato e extrair dados
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como usar o SharePoint Syntex para identificar arquivos de contrato e extrair dados usando uma solução Microsoft 365.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281058"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Etapa 1. Use SharePoint Syntex para identificar arquivos de contrato e extrair dados

Sua organização precisa de uma maneira de identificar e classificar todos os documentos de contrato dos muitos arquivos recebidos. Você também deseja poder exibir rapidamente vários elementos-chave em cada um dos arquivos de contrato identificados (por exemplo, *Cliente,* Prestador de Serviços *e* Valor *da Taxa).* Você pode fazer isso usando SharePoint [Syntex](index.md) para criar um modelo de compreensão de documentos e aplica-lo a uma biblioteca de documentos.

[A compreensão do](document-understanding-overview.md) documento usa modelos de inteligência artificial (AI) para automatizar a classificação de arquivos e a extração de informações. Os modelos de compreensão de documentos também são ideais para extrair informações de documentos não estruturados e semiestruturados, onde as informações de que você precisa não estão contidas em tabelas ou formulários, como contratos.

1. Primeiro, você precisa encontrar pelo menos cinco arquivos de exemplo que você pode usar para "treinar" o modelo para pesquisar características específicas do tipo de conteúdo que você está tentando identificar (um contrato). 

2. Usando SharePoint Syntex, crie um novo modelo de compreensão de documentos. Usando seus arquivos de exemplo, você precisa [criar um classificador](create-a-classifier.md). Ao treinar o classificador com seus arquivos de exemplo, você o ensina a pesquisar características específicas do que você verá nos contratos da sua empresa. Por exemplo, crie uma ["explicação"](create-a-classifier.md#create-an-explanation) que procure cadeias de caracteres específicas que estão em seus contratos, como Contrato de *Serviço,* Termos de Contrato *e* *Compensação.* Você pode até mesmo treinar sua explicação para procurar essas cadeias de caracteres em seções específicas do documento ou localizadas ao lado de outras cadeias de caracteres. Quando você acha que treinou seu classificador com as informações necessárias, você pode testar seu modelo em um conjunto de exemplos de arquivos para ver o quão eficiente ele é. Após o teste, se necessário, você pode optar por fazer alterações em suas explicações para torná-las mais eficientes. 

3. Em seu modelo, você pode [criar um extrator](create-an-extractor.md) para extrair partes específicas de dados de cada contrato. Por exemplo, para cada contrato, as informações que você mais se preocupa são quem é o cliente, o nome do prestador de serviços e o custo total.

4. Depois de criar seu modelo com êxito, [aplique-o a](apply-a-model.md)uma SharePoint de documentos. À medida que você carrega documentos na biblioteca de documentos, seu modelo de compreensão de documentos será executado e identificará e classificará todos os arquivos que corresponderem ao tipo de conteúdo de contratos definido em seu modelo. Todos os arquivos classificados como contratos serão exibidos em um exibição de biblioteca personalizado. Os arquivos também exibirão os valores de cada contrato que você definiu em seu extrator.

   ![Contratos na biblioteca de documentos](../media/content-understanding/doc-lib-solution.png)

5. Além disso, se você tiver requisitos de retenção para [](apply-a-retention-label-to-a-model.md) seus contratos, também poderá usar seu modelo para aplicar um rótulo de retenção que impedirá que seus contratos sejam excluídos por um período de tempo especificado.

## <a name="next-step"></a>Próxima etapa

[Etapa 2. Use Microsoft Teams para criar seu canal de gerenciamento de contratos](solution-manage-contracts-step2.md)