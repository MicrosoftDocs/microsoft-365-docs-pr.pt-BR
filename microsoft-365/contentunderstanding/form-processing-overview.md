---
title: Visão geral do processamento de formulário
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre o processamento de formulários no Microsoft SharePoint Syntex
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295171"
---
# <a name="form-processing-overview-preview"></a>Visão geral do processamento de formulário (versão prévia)

O conteúdo deste artigo é para a visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

O Project Cortex usa o processamento de formulário do Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) para criar modelos em bibliotecas de documentos do SharePoint.

Você pode usar o processamento de formulário do Construtor AI para criar modelos AI que usam a tecnologia de aprendizado de máquina para identificar e extrair pares de chave-valor e dados de tabela de documentos estruturados ou semi-estruturados, como formulários e faturas.

Use o processamento de formulário do AI Builder para criar modelos AI que utilizam a tecnologia de aprendizado da máquina (ML) para identificar e extrair pares chave-valor e dados de tabela de documentos estruturados ou semi-estruturados, como formulários e faturas.

As organizações geralmente recebem faturas em grandes quantidades de várias fontes, como email, fax, email, etc. O processamento desses documentos e a inserção manual deles em um banco de dados pode levar bastante tempo. Usando o AI para extrair o texto, os pares de chave/valor e as tabelas de seus documentos, o processamento de formulários automatiza esse processo. 

Por exemplo, você pode criar um modelo de processamento de formulário que identifique todos os documentos de ordem de compra que são carregados na biblioteca de documentos. A partir de cada ordem de compra, você pode extrair e exibir dados específicos que são importantes para você, como *número da OC*, *Data*ou *custo total*.

Você também pode usar arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário. O layout do seu documento é aprendido ao treinar seu modelo. Você precisa de um mínimo de cinco documentos de formulário para começar. A compilação do AI analisa seus arquivos de exemplo para pares de chave-valor e identifica manualmente aqueles que podem não ter sido detectados.  O Construtor AI permite que você teste a precisão do seu modelo em seus arquivos de amostra.

Depois de treinar e publicar seu modelo, use-o para criar um [fluxo automatizado de energia](https://docs.microsoft.com/power-automate/getting-started) que é executado depois que um arquivo é carregado na biblioteca de documentos do SharePoint. Em seguida, ele extrai os dados que foram identificados no modelo. Os dados extraídos serão exibidos em colunas no modo de exibição de biblioteca de documentos do modelo.

Você usa arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário. O layout do seu documento é aprendido ao treinar seu modelo. Você precisa apenas de cinco documentos de formulário para começar. O Construtor AI analisará seus arquivos de exemplo para pares de chave-valor, e você também poderá identificar manualmente aqueles que podem não ter sido detectados.  O Construtor AI permite que você teste a precisão do seu modelo em seus arquivos de amostra.

Depois de treinar e publicar seu modelo, use-o para criar um [fluxo automatizado de energia](https://docs.microsoft.com/power-automate/getting-started). O fluxo é executado quando um arquivo é carregado na biblioteca de documentos do SharePoint e extrai os dados que foram identificados no modelo. Os dados extraídos serão exibidos em colunas no modo de exibição de biblioteca de documentos do modelo.

Um administrador do Office 365 precisa [habilitar o processamento de formulários](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) para a biblioteca de documentos do SharePoint para que os usuários possam [criar um modelo de processamento de formulários](create-a-form-processing-model.md) nele.

## <a name="see-also"></a>Confira também
  
[Documentação da automatização de energia](https://docs.microsoft.com/power-automate/)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Treinamento: aprimore o desempenho de negócios com o Construtor AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
