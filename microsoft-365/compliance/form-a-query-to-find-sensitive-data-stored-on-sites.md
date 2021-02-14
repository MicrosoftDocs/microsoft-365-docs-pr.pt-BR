---
title: Criar uma consulta para encontrar dados confidenciais armazenados em sites
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Use a prevenção contra perda de dados (DLP) no SharePoint Online para descobrir documentos que contêm dados confidenciais em todo o locatário.
ms.openlocfilehash: b6a0943aa4e71b61c5f430034d9e445462eebde7
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817700"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Criar uma consulta para encontrar dados confidenciais armazenados em sites

Os usuários armazenam frequentemente dados confidenciais em seus sites, como números de cartão de crédito, de previdência social ou pessoais, e com o passar do tempo isso pode expor a organização a um risco significativo de perda de dados. Documentos armazenados em sites, incluindo sites do OneDrive for Business, podem ser compartilhados com pessoas de fora da organização que não devem ter acesso às informações. Com a prevenção contra perda de dados (DLP) no SharePoint Online, você pode descobrir documentos que contêm dados confidenciais em todo o seu locatário. Após descobrir os documentos, você pode trabalhar com os proprietários do documento para proteger os dados. Este tópico pode ajudá-lo a formar uma consulta para procurar dados confidenciais.
  
> [!NOTE]
> Descoberta eletrônica ou Descoberta Eletrônica e DLP são recursos premium que exigem [o SharePoint Online Plano 2.](https://go.microsoft.com/fwlink/?LinkId=510080) 
  
## <a name="forming-a-basic-dlp-query"></a>Criando uma consulta básica de DLP

Uma consulta básica de DLP é composta por três partes: SensitiveType, intervalo de contagem, e intervalo de confiança. Conforme ilustrado no gráfico a seguir, **SensitiveType:" \<type\> "** é obrigatório e ambos **|\<count range\>** e são **|\<confidence range\>** opcionais. 
  
![Consulta de exemplo dividida em necessária e opcional](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>Tipo confidencial - necessário

Portanto, o que é cada parte? As consultas DLP do SharePoint normalmente começam com a propriedade e um nome de tipo de informação do inventário de tipos de informações confidenciais e terminam `SensitiveType:"` com um [](https://go.microsoft.com/fwlink/?LinkID=509999) `"` . Você também pode usar o nome de um [tipo personalizado de](create-a-custom-sensitive-information-type.md) informação confidenciais criado para sua organização. Por exemplo, você pode estar procurando por documentos que contenham números de cartão de crédito. Nesse caso, você usaria o seguinte formato:  `SensitiveType:"Credit Card Number"` . Como você não incluiu o intervalo de contagem ou o intervalo de confiança, a consulta retorna todos os documentos em que um número de cartão de crédito é detectado. Esta é a consulta mais simples que você pode executar, e a que retorna mais resultados. Tenha em mente que a ortografia e o espaçamento do tipo confidencial são importantes. 
  
### <a name="ranges---optional"></a>Intervalos - opcionais

Ambas as próximas duas partes são intervalos, portanto, vamos examinar rapidamente a aparência de um intervalo. Em consultas DLP do SharePoint, um intervalo básico é representado por dois números separados por dois pontos, que tem esta aparência:  `[number]..[number]` . Por exemplo, se  `10..20` for usado, esse intervalo capturaria números de 10 a 20. Existem várias combinações de intervalos e vários são abordados neste tópico. 
  
Vamos adicionar um intervalo de contagem à consulta. Você pode usar o intervalo de contagem para definir o número de ocorrências de informações confidenciais que um documento precisa conter antes de ser incluído nos resultados da consulta. Por exemplo, se você quiser que sua consulta retorne apenas documentos que contenham exatamente cinco números de cartão de crédito, use este:  `SensitiveType:"Credit Card Number|5"` . O intervalo de contagem também pode ajudá-lo a identificar documentos que apresentam níveis elevados de risco. Por exemplo, a sua organização pode considerar documentos com cinco ou mais números de cartão de crédito como de alto risco. Para encontrar documentos que se ajustem a esse critério, use esta consulta:  `SensitiveType:"Credit Card Number|5.."` . Como alternativa, você pode encontrar documentos com cinco ou menos números de cartão de crédito usando esta consulta:  `SensitiveType:"Credit Card Number|..5"` . 
  
#### <a name="confidence-range"></a>Intervalo de confiança

Finalmente, intervalo de confiança é o nível de confiança a que o tipo confidencial detectado corresponde. Os valores de intervalo de confiança funcionam da mesma forma para o intervalo de contagem. É possível formar uma consulta sem incluir uma variedade de contagem. Por exemplo, para pesquisar documentos com qualquer número de números de cartão de crédito, desde que o intervalo de confiança seja de 85% ou mais, você usaria esta consulta:  `SensitiveType:"Credit Card Number|*|85.."` . 
  
> [!IMPORTANT]
> O asterisco ( `*` ) é um caractere curinga que significa que qualquer valor funciona. Você pode usar o caractere curinga ( ) no intervalo de contagem ou no intervalo de `*` confiança, mas não em um tipo sensível. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Propriedades de pesquisa e operadores de consulta adicionais disponíveis no Centro de Descoberta Eletrônica

A DLP no SharePoint também apresenta a propriedade LastSensitiveContentScan, que pode ajudá-lo a pesquisar arquivos verificados em um período de tempo específico. Para ver exemplos de consulta com a propriedade, consulte exemplos de consultas  `LastSensitiveContentScan` [complexas](#examples-of-complex-queries) na próxima seção. 
  
Você pode usar não apenas propriedades específicas de DLP para criar uma consulta, mas também propriedades padrão de pesquisa de Descobertas Do SharePoint, como  `Author` ou  `FileExtension` . Você pode usar operadores para criar consultas complexas. Para ver a lista de operadores e propriedades disponíveis, consulte a postagem usando operadores e propriedades de pesquisa com a postagem [de](https://go.microsoft.com/fwlink/?LinkId=510093) blog de DescobertaScoberta. 
  
## <a name="examples-of-complex-queries"></a>Exemplos

Os exemplos a seguir usam diferentes tipos, propriedades e operadores confidenciais para ilustrar como você pode refinar suas consultas para encontrar exatamente o que você está procurando.
  
|**Query**|**Explicação**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |O nome pode parecer estranho por ser muito longo, mas é o nome correto para esse tipo sensível. Certifique-se de usar nomes exatos do inventário [de tipos de informações confidenciais.](https://go.microsoft.com/fwlink/?LinkID=509999) Você também pode usar o nome de um [tipo personalizado de](create-a-custom-sensitive-information-type.md) informação confidenciais criado para sua organização.  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |Isso retorna documentos com pelo menos uma combinação com o tipo sensível "Número de cartão de crédito". Os valores para cada intervalo são os respectivos valores mínimo e máximo. Uma maneira mais simples de escrever essa consulta  `SensitiveType:"Credit Card Number"` é, mas qual é a diversão disso?  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |Isso retorna documentos com 5 a 25 números de cartão de crédito que foram verificados de 11 de agosto de 2018 a 13 de agosto de 2018.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |Isso retorna documentos com 5 a 25 números de cartão de crédito que foram verificados de 11 de agosto de 2018 a 13 de agosto de 2018. Os arquivos com uma extensão XLSX não são incluídos nos resultados da consulta.  `FileExtension` é uma das muitas propriedades que você pode incluir em uma consulta. Para obter mais informações, consulte Usando operadores e [propriedades de pesquisa com Descobertas e Descobertas.](https://go.microsoft.com/fwlink/?LinkId=510093)  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |Isso retornará documentos que contenham um número de cartão de crédito ou um número de previdência social.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Exemplos

Nem todas as consultas são criadas da mesma forma. A tabela a seguir fornece exemplos de consultas que não funcionam com DLP no SharePoint e descreve o motivo.
  
|**Consulta incompatível**|**Motivo**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |Você deve adicionar pelo menos um serviço.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" não é um nome de tipo sensível válido. Apenas nomes no inventário [de tipos de informações confidenciais](https://go.microsoft.com/fwlink/?LinkID=509999) funcionam em consultas DLP.  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |Zero não é válido como o valor mínimo ou o valor máximo em um intervalo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Pode ser difícil de ver, mas há um espaço em branco extra entre "Crédito" e "Cartão" que torna a consulta inválida. Use nomes de tipos confidenciais exatos do inventário [de tipos de informações confidenciais.](https://go.microsoft.com/fwlink/?LinkID=509999)  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |A parte de dois pontos não deve ser separada por um espaço.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |Há muitos delimitadores de pipe (|). Siga este formato em vez disso: `SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |Como os valores de confiança representam uma porcentagem, eles não podem exceder 100. Escolha um número de 1 a 100 em vez disso.  <br/> |
   
## <a name="for-more-information"></a>Para obter mais informações

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Executar uma Pesquisa de Conteúdo](content-search.md)
- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
  

