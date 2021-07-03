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
ms.openlocfilehash: 04bf2e97dd2b5530838aef9fcb4b4467270d2d9d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287474"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Criar uma consulta para encontrar dados confidenciais armazenados em sites

Os usuários armazenam frequentemente dados confidenciais em seus sites, como números de cartão de crédito, de previdência social ou pessoais, e com o passar do tempo isso pode expor a organização a um risco significativo de perda de dados. Os documentos armazenados em sites, incluindo OneDrive for Business sites, podem ser compartilhados com pessoas de fora da organização que não devem ter acesso às informações. Com a prevenção contra perda de dados (DLP) no SharePoint Online, você pode descobrir documentos que contêm dados confidenciais em todo o locatário. Após descobrir os documentos, você pode trabalhar com os proprietários do documento para proteger os dados. Este tópico pode ajudá-lo a formar uma consulta para procurar dados confidenciais.

> [!NOTE]
> Descoberta eletrônica ou Descoberta Eletrônica e DLP são recursos premium que exigem SharePoint [Plano Online 2](https://go.microsoft.com/fwlink/?LinkId=510080).

## <a name="forming-a-basic-dlp-query"></a>Criando uma consulta básica de DLP

Uma consulta básica de DLP é composta por três partes: SensitiveType, intervalo de contagem, e intervalo de confiança. Conforme ilustrado no gráfico a seguir, **SensitiveType:" \<type\> " " é** obrigatório e ambos e são **|\<count range\>** **|\<confidence range\>** opcionais.

![Consulta de exemplo dividida em necessária e opcional](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>Tipo confidencial - necessário

Portanto, o que é cada parte? SharePoint As consultas DLP geralmente começam com a propriedade e um nome de tipo de informação do inventário de tipos de informações confidenciais `SensitiveType:"` e terminam com um [](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) `"` . Você também pode usar o nome de um [tipo de informação confidenciais personalizado](create-a-custom-sensitive-information-type.md) que você criou para sua organização. Por exemplo, você pode estar procurando por documentos que contenham números de cartão de crédito. Nesse caso, você usaria o seguinte formato:  `SensitiveType:"Credit Card Number"` . Como você não incluiu intervalo de contagem ou intervalo de confiança, a consulta retorna cada documento no qual um número de cartão de crédito é detectado. Esta é a consulta mais simples que você pode executar, e a que retorna mais resultados. Tenha em mente que a ortografia e o espaçamento do tipo confidencial são importantes.

### <a name="ranges---optional"></a>Intervalos - opcionais

Ambas as próximas duas partes são intervalos, portanto, vamos examinar rapidamente a aparência de um intervalo. Em SharePoint DLP, um intervalo básico é representado por dois números separados por dois períodos, que são assim: `[number]..[number]` . Por exemplo, se  `10..20` for usado, esse intervalo capturaria números de 10 a 20. Existem várias combinações de intervalos e vários são abordados neste tópico.

Vamos adicionar um intervalo de contagem à consulta. Você pode usar o intervalo de contagem para definir o número de ocorrências de informações confidenciais que um documento precisa conter antes de ser incluído nos resultados da consulta. Por exemplo, se você quiser que sua consulta retorne apenas documentos que contenham exatamente cinco números de cartão de crédito, use este:  `SensitiveType:"Credit Card Number|5"` . O intervalo de contagem também pode ajudá-lo a identificar documentos que apresentam níveis elevados de risco. Por exemplo, a sua organização pode considerar documentos com cinco ou mais números de cartão de crédito como de alto risco. Para encontrar documentos que encaixem nesse critério, você usaria esta consulta:  `SensitiveType:"Credit Card Number|5.."` . Como alternativa, você pode encontrar documentos com cinco ou menos números de cartão de crédito usando esta consulta:  `SensitiveType:"Credit Card Number|..5"` .

#### <a name="confidence-range"></a>Intervalo de confiança

Finalmente, intervalo de confiança é o nível de confiança a que o tipo confidencial detectado corresponde. Os valores de intervalo de confiança funcionam da mesma forma para o intervalo de contagem. É possível formar uma consulta sem incluir uma variedade de contagem. Por exemplo, para pesquisar documentos com qualquer número de números de cartão de crédito, desde que o intervalo de confiança seja 85% ou superior, você usaria esta consulta:  `SensitiveType:"Credit Card Number|*|85.."` .

> [!IMPORTANT]
> O asterisco ( `*` ) é um caractere curinga que significa que qualquer valor funciona. Você pode usar o caractere curinga ( ) no intervalo de contagem ou no intervalo de `*` confiança, mas não em um tipo sensível.

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Propriedades de pesquisa e operadores de consulta adicionais disponíveis no Centro de Descoberta Eletrônica

A DLP no SharePoint também introduz a propriedade LastSensitiveContentScan, que pode ajudá-lo a pesquisar arquivos verificados em um período de tempo específico. Para ver exemplos de consulta com  `LastSensitiveContentScan` a propriedade, consulte [Examples of complex queries](#examples-of-complex-queries) in the next section.

Você pode usar não apenas propriedades específicas de DLP para criar uma consulta, mas também propriedades de pesquisa de Descoberta SharePoint eDiscovery padrão, como `Author` ou `FileExtension` . Você pode usar operadores para criar consultas complexas. Para ver a lista de propriedades e operadores disponíveis, consulte a postagem do blog Usando Propriedades e Operadores de Pesquisa com [Descoberta EDiscovery.](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)

## <a name="examples-of-complex-queries"></a>Exemplos

Os exemplos a seguir usam diferentes tipos, propriedades e operadores confidenciais para ilustrar como você pode refinar suas consultas para encontrar exatamente o que você está procurando.

<br>

****

|Consulta|Explicação|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|O nome pode parecer estranho porque é muito longo, mas é o nome correto para esse tipo sensível. Certifique-se de usar nomes exatos do inventário [de tipos de informações confidenciais.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) Você também pode usar o nome de um [tipo de informação confidenciais personalizado](create-a-custom-sensitive-information-type.md) que você criou para sua organização.|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|Isso retorna documentos com pelo menos uma combinação com o tipo sensível "Número do Cartão de Crédito". Os valores para cada intervalo são os respectivos valores mínimo e máximo. Uma maneira mais simples de escrever essa consulta é  `SensitiveType:"Credit Card Number"` , mas qual é a graça nisso?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|Isso retorna documentos com 5 a 25 números de cartão de crédito verificados de 11 de agosto de 2018 a 13 de agosto de 2018.|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|Isso retorna documentos com 5 a 25 números de cartão de crédito verificados de 11 de agosto de 2018 a 13 de agosto de 2018. Os arquivos com uma extensão XLSX não estão incluídos nos resultados da consulta.  `FileExtension` é uma das muitas propriedades que você pode incluir em uma consulta. Para obter mais informações, consulte [Using Search Properties and Operators with eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery).|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|Isso retornará documentos que contenham um número de cartão de crédito ou um número de previdência social.|
|

## <a name="examples-of-queries-to-avoid"></a>Exemplos

Nem todas as consultas são criadas da mesma forma. A tabela a seguir fornece exemplos de consultas que não funcionam com DLP no SharePoint e descreve o motivo.

<br>

****

|Consulta incompatível|Reason|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|Você deve adicionar pelo menos um serviço.|
|`SensitiveType:"NotARule"`|"NotARule" não é um nome de tipo sensível válido. Somente os nomes no inventário [de tipos de informações confidenciais](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) funcionam em consultas DLP.|
|`SensitiveType:"Credit Card Number|0"`|Zero não é válido como o valor mínimo ou o valor máximo em um intervalo.|
|`SensitiveType:"Credit Card Number"`|Pode ser difícil ver, mas há espaço em branco extra entre "Crédito" e "Cartão" que torna a consulta inválida. Use nomes de tipos confidenciais exatos do inventário [de tipos de informações confidenciais.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)|
|`SensitiveType:"Credit Card Number|1. .3"`|A parte de dois períodos não deve ser separada por um espaço.|
|`SensitiveType:"Credit Card Number| |1..|80.."`|Há delimitadores de canos demais ( \| ). Siga este formato em vez disso: `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|Como os valores de confiança representam uma porcentagem, eles não podem exceder 100. Escolha um número de 1 a 100 em vez disso.|
|

## <a name="for-more-information"></a>Para obter mais informações

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Executar uma Pesquisa de Conteúdo](content-search.md)
- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
