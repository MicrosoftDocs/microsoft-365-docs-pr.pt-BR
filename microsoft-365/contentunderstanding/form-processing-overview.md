---
title: Visão geral do processamento de formulário (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre o processamento de formulários no Project Cortex.
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612721"
---
# <a name="form-processing-overview-preview"></a>Visão geral do processamento de formulário (versão prévia)
> [!Note]
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

O Project Cortex usa o processamento de formulário do Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) para criar modelos em bibliotecas de documentos do SharePoint.
Você pode usar o processamento de formulário do Construtor AI para criar modelos AI que usam a tecnologia de aprendizado de máquina para identificar e extrair pares de chave-valor e dados de tabela de documentos estruturados ou semi-estruturados, como formulário e faturas.

As empresas geralmente recebem faturas em grandes quantidades e de várias fontes, como email, fax, email ou pessoalmente. O processamento desses documentos e a inserção manual deles no banco de dados pode demorar bastante tempo. Usando o AI para extrair o texto, os pares de chave/valor e as tabelas de seus documentos, o processamento de formulários automatizará esse processo. 

Por exemplo, você pode criar um modelo de processamento de formulário que identifique todos os documentos de ordem de compra que são carregados na biblioteca de documentos. E de cada ordem de compra, você pode extrair e exibir dados específicos que são importantes para você, como *número da OC*, *Data*ou *custo total*.

Você usa arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário. O layout do seu documento é aprendido ao treinar seu modelo. Você precisa apenas de cinco documentos de formulário para começar. A compilação do AI analisará seus arquivos de exemplo para pares de chave-valor, e você também poderá identificar manualmente aqueles que podem não ter sido detectados.  O Construtor AI permite que você teste a precisão do seu modelo em seus arquivos de amostra.

Depois de treinar e publicar seu modelo, use-o para criar um [fluxo automatizado de energia](https://docs.microsoft.com/power-automate/getting-started) que será executado quando um arquivo for carregado na biblioteca de documentos do SharePoint e extrairá os dados que foram identificados no modelo. Os dados extraídos serão exibidos em colunas no modo de exibição de biblioteca de documentos do modelo.

Um administrador do Office 365 precisa [habilitar o processamento de formulários](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) para a biblioteca de documentos do SharePoint para que os usuários possam [criar um modelo de processamento de formulários](create-a-form-processing-model.md) nele.



## <a name="see-also"></a>Confira também
  
[Documentação da automatização de energia](https://docs.microsoft.com/power-automate/)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Treinamento: aprimore o desempenho de negócios com o Construtor AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




