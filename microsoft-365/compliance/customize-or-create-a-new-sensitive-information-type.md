---
title: Personalizar ou criar um novo tipo de informação confidencial
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Saiba como modificar ou criar novos tipos de informação confidencial do Office 365 para GDPR.
ms.openlocfilehash: 264e310c019c47d1b3109b20fbdd61b323ec5530
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072011"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a>Personalizar ou criar um novo tipo de informação confidencial

Este artigo fornece três exemplos para demonstrar como modificar ou criar novos tipos de informação confidencial do Office 365 para GDPR.

- Modificar um tipo de informação confidencial existente – Número de Cartão de Débito da UE

- Criar um novo tipo de informação confidencial – endereço de email

- Criar um novo tipo de informação confidencial com o arquivo XML de exemplo – número de cliente da Contoso

Confira também:

- [Criar um tipo de informação confidencial personalizado usando o PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [Personalizar um tipo de informação confidencial interno](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a>Modificar um tipo de informação confidencial para melhorar a precisão

Se você estiver usando a Pesquisa de Conteúdo para pesquisar dados pessoais usando tipos de informação confidencial e não estiver recebendo os resultados esperados ou a consulta retornar muitos falsos positivos, considere a possibilidade de modificar o tipo de informação confidencial para se adequar melhor ao seu ambiente.

A prática recomendada ao criar ou personalizar um tipo de informação confidencial é criar um novo tipo de informação confidencial com base em uma informação existente, dando a ela um nome exclusivo e identificadores. Por exemplo, se quiser ajustar os parâmetros do tipo de informação confidencial do "Número de Cartão de Débito da UE", dê o nome "Cartão de Débito da UE Aprimorado" à sua cópia da regra para diferenciá-la do tipo original.

No novo tipo de informação confidencial, basta modificar os valores que você deseja alterar para melhorar a precisão. Depois de concluído, carregue seu novo tipo de informação confidencial e crie uma nova regra DLP (ou modifique uma existente) para usar o novo tipo de informação confidencial que você acabou de adicionar. Modificar a precisão de tipos de informação confidencial pode exigir algumas tentativas e erros, portanto, manter uma cópia do tipo original permite recuperá-lo posteriormente, caso isso seja necessário.

Para personalizar um tipo de informação confidencial:

1.  Exporte o Pacote de Regras da Microsoft existente de tipos de informação confidencial internos no Office 365.

2.  Renomeie este arquivo XML e abra-o em seu editor de XML favorito.

3.  Isole o tipo de informação confidencial e remova os demais.

4.  Use o PowerShell para gerar dois novos GUIDs para o tipo de informação confidencial que você está modificando.

5.  Modifique a ID e outros elementos básicos para que o tipo de informação confidencial seja exclusivo (isso inclui substituir dois GUIDs pelos novos GUIDs gerados).

6.  Ajuste os requisitos de correspondência para melhorar a precisão.

    1.  Modificações de proximidade – Modifique a proximidade do padrão de caracteres para expandir ou reduzir a janela na qual as palavras-chave devem ser encontradas em todos os tipos de informação confidencial.

    2.  Modificações de palavras-chave – Adicione palavras-chave a um dos elementos \<Keywords\> para fornecer ao tipo de informação confidencial evidências comprobatórias mais específicas para a pesquisa com o intuito de sinalizar uma correspondência nessa regra. Você também pode remover palavras-chave que estejam gerando falsos positivos.

    3.  Modificações de confiança – Modifique a confiança com que o tipo de informação confidencial deverá corresponder aos critérios especificados nessa definição antes de uma correspondência ser sinalizada e relatada.

7.  Carregue o novo tipo de informação confidencial.

8.  Repita o rastreamento do conteúdo para identificar informações confidenciais. Confira [Solicitar manualmente o rastreamento e a reindexação de um site](https://support.office.com/pt-BR/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a>Exemplo: modificar o tipo de informação confidencial do 'Número de Cartão de Débito da UE'

Melhorar a precisão das regras de DLP nos sistemas exige testes para detectar um conjunto de dados de exemplo e pode exigir um ajuste aprimorado por meio de testes e modificações repetitivas. Este exemplo demonstra modificações realizadas no tipo de informação confidencial do "Número de Cartão de Débito da UE" para melhorar a precisão.

Ao pesquisar um Número de Cartão de Débito da UE em nosso exemplo, a definição do número estará rigorosamente definida como 16 dígitos usando um padrão complexo e estará sujeita à validação de uma soma de verificação. Não será possível alterar esse padrão devido à definição da cadeia de caracteres desse tipo de informação confidencial. No entanto, podemos fazer os seguintes ajustes para aumentar a precisão da forma como o Office 365 DLP localiza esse tipo de informação confidencial no Office 365.

### <a name="proximity-modification"></a>Modificação de proximidade

Reduziremos a janela modificando o valor patternProximity em nosso elemento \<Entity\> de 300 a 150 caracteres. Isso significa que nossas evidências comprobatórias, ou nossas palavras-chave, devem estar mais próximas do tipo de informação confidencial para sinalizar uma correspondência nessa regra.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

### <a name="keyword-modifications"></a>Modificações de palavras-chave

Algumas palavras-chave podem levar a falsos positivos, por isso, convém removê-las. Veja as palavras-chave neste exemplo:

\<Keyword id="Keyword\_card\_terms\_dict"\>

\<Group\>

\<Term\>corporate card\</Term\>

\<Term\>organization card\</Term\>

\<Term\>acct nbr\</Term\>

\<Term\>acct num\</Term\>

\<Term\>acct no\</Term\>

…

\</Group\>

\</Keyword\>

### <a name="confidence-modifications"></a>Modificações de confiança

Se você removesse palavras-chave da definição, geralmente desejaria ajustar seu nível de certeza que indica que esse tipo de informação confidencial foi encontrado com a redução desse valor. O nível padrão do tipo de Número do cartão de débito da UE é 85.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

…

\</Pattern\>

\</Entity\>

## <a name="create-a-new-custom-sensitive-information-type"></a>Criar um novo tipo de informação confidencial personalizada

Para criar um novo tipo de informação confidencial personalizada, comece usando a Pesquisa de Conteúdo:

-   Otimizar uma consulta KQL

-   Ver quais palavras-chave são mais úteis

Use esses resultados para criar um novo tipo de informação confidencial e otimize o novo tipo de informação confidencial para seu ambiente.

Observação: vários novos tipos de informação confidencial estarão brevemente disponíveis para dados pessoais de países da UE. Se precisar criar novos tipos de informação confidencial, comece direcionando dados personalizados para seu ambiente.

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a>Etapa 1: Usar consultas KQL e palavras-chave para encontrar dados adicionais em seu ambiente

Talvez seja preciso criar outras consultas para localizar dados pessoais sujeitos à GDPR. A Pesquisa de Conteúdo usa a Keyword Query Language (KQL) para localizar os dados. Não é possível detectar os dados confidenciais mais importantes com precisão usando apenas a KQL sem os tipos de informação confidencial. Portanto, o objetivo é testar e otimizar cadeias de caracteres da KQL usando a Pesquisa de Conteúdo e usá-las para criar e ajustar novos tipos de informação confidencial para alcançar ainda mais precisão.

Use estes recursos para formular e otimizar consultas usando KQL:

-   [Referência de sintaxe (DMC) da Keyword Query Language(KQL)](https://docs.microsoft.com/pt-BR/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

-   [Executar uma Pesquisa de Conteúdo](https://support.office.com/pt-BR/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) 

A Pesquisa de Conteúdo oferece outro recurso para ajudar você a desenvolver consultas KQL e tipos de informação confidencial – as palavras-chave. Por que usar a lista de palavras-chave? Para ver estatísticas que mostram o número de itens que correspondem a cada palavra-chave, o que pode ajudar a identificar rapidamente quais palavras-chave são mais (e menos) eficientes. Para saber mais sobre as estatísticas de pesquisas, confira [Exibir as estatísticas de palavras-chave dos resultados da Pesquisa de Conteúdo](https://support.office.com/pt-BR/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).

As palavras-chave de cada linha são conectadas pelo operador OR na consulta da pesquisa que é criada. Você também pode usar uma frase de palavra-chave (entre parênteses) em uma linha.

Para saber mais, confira [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](https://support.office.com/pt-BR/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).

### <a name="exampleusing-content-search-to-identify-email-addresses"></a>Exemplo – Usar a Pesquisa de Conteúdo para identificar endereços de email

Os endereços de email são considerados informações confidenciais relacionadas aos assuntos de dados. Isso é um exemplo simples para demonstrar como a Pesquisa de Conteúdo pode ajudar.

As palavras-chave e o KQL não podem ser usados em conjunto. Use essas ferramentas separadamente para aperfeiçoar sua consulta e determinar as palavras-chave que podem ser úteis para os tipos de informação confidencial.

### <a name="kql-query"></a>Consulta KQL

(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)

Observações:

-   você pode usar NEAR e ONEAR para pesquisas de proximidade.

-   Infelizmente, o KQL não oferece suporte a consultas com a Classe Regex (por exemplo: IdRef="Regex\_email\_address")

### <a name="keywords"></a>Palavras-chave

Insira cada palavra-chave em uma linha separada. Essas são palavras-chave de exemplo:

-   endereço de email

-   email

-   contato

-   remetente

-   destinatário

-   cc

-   bcc

Neste exemplo, você pode perceber que as palavras-chave não são necessárias e geram muitos resultados falsos positivos.

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a>Etapa 2 – Criar um novo tipo de informação confidencial personalizada

Após usar as consultas KQL e palavras-chave para identificar informações confidenciais, use-as para criar novos tipos de informação confidencial personalizadas. Em muitos casos, você precisará da sofisticação dos tipos de informação confidencial para atingir o nível certo de precisão. Em seguida, use esses tipos de informação confidencial personalizadas com a Pesquisa de Conteúdo em políticas DLP, em outras ferramentas e em outras consultas KQL.

A prática recomendada é criar um novo tipo de informação confidencial com base em um tipo existente. Use o mesmo processo descrito anteriormente neste artigo.

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a>Exemplo – Criar um novo tipo de informação confidencial para endereços de email 

Por ser simples, vamos continuar a usar o endereço de email como exemplo. A tabela a seguir fornece detalhes sobre as alterações recomendadas para um novo tipo de informação confidencial de email.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></th>
<th align="left"><strong>Modificação </strong></th>
<th align="left"><strong>Exemplo de sintaxe XML</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Definir a propriedade IdRef
<p>No elemento &lt;Entity&gt;, modifique o elemento &lt;IdMatch&gt; para que sua propriedade idRef seja = a um valor único. Esse valor apontará para um elemento que define nossa expressão regular para localizar endereços de email.</p></td>
<td align="left">IdRef=&quot;Regex_email_address&quot;</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left"><p>Atributo de proximidade</p>
<p>Vamos começar com um valor patternProximity de 300 em nosso elemento &lt;entity&gt;.</p></td>
<td align="left">patternsProximity=&quot;300&quot;</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left"><p>Nível de confiança</p>
<p>Defina a propriedade recommendedConfidence com um valor que você sente que representará a confiança de encontrar uma correspondência precisa. Isso provavelmente exigirá testes com um conjunto representativo de dados para obter um resultado preciso. Para uma configuração inicial, defina esse valor como 75.</p></td>
<td align="left"><p>recommendedConfidence=&quot;75&quot;&gt;</p>
<p>O XML resultante desses três primeiros elementos combinados tem a seguinte aparência:</p>
<p>&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</p>
<p>&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</p>
<p>&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</p>
<p>&lt;Any minMatches=&quot;1&quot;&gt;</p>
<p>&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</p>
<p>&lt;/Any&gt;</p>
<p>&lt;/Pattern&gt;</p>
<p>&lt;/Entity&gt;</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left"><p>Elemento Regex</p>
<p>Adicione um novo elemento &lt;Regex&gt; logo abaixo dos elementos &lt;Entity&gt; que definem a expressão regular usada para identificar os endereços de email.</p></td>
<td align="left">&lt;Regex id=&quot;Endereço_email_Regex&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left"><p>Palavras-chave</p>
<p>Adicione um novo elemento &lt;Keyword&gt; abaixo do elemento &lt;Regex&gt; que define a lista de palavras-chave relacionadas dos endereços de email. Verifique se o valor de id do elemento &lt;Keyword&gt; corresponde ao valor &lt;Match idRef&gt; no elemento &lt;Entity&gt;&lt;Pattern&gt;. Se necessário, você pode continuar a adicionar suas próprias palavras-chave.</p>
<p>Há palavras-chave que provavelmente não precisarão ser incluídas em um tipo de informação confidencial de email. Elas são fornecidas como exemplo.</p></td>
<td align="left"><p>&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</p>
<p>&lt;Group&gt;</p>
<p>&lt;Term&gt;email&lt;/Term&gt;</p>
<p>&lt;Term&gt;email address&lt;/Term&gt;</p>
<p>&lt;Term&gt;contact&lt;/Term&gt;</p>
<p>&lt;/Group&gt;</p>
<p>&lt;/Keyword&gt;</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left"><p>Elemento LocalizedStrings</p>
<p>No elemento &lt;LocalizedStrings&gt;&lt;Resource&gt;, verifique você se tem um nome exclusivo para identificar seu tipo de informação confidencial.</p></td>
<td align="left"><p>&lt;LocalizedStrings&gt;</p>
<p>&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</p>
<p>&lt;Name default=&quot;true&quot; langcode=&quot;pt-br&quot;&gt;Endereço de Email&lt;/Name&gt;</p>
<p>&lt;Description default=&quot;true&quot; langcode=&quot;pt-br&quot;&gt;Detecta endereços de email.&lt;/Description&gt;</p>
<p>&lt;/Resource&gt;</p>
<p>&lt;/LocalizedStrings&gt;</p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a>Criar um novo tipo de informação confidencial com o exemplo do PowerShell e do arquivo XML - número de cliente da Contoso

A Contoso usa um Número de cliente da Contoso (CCN) para identificar cada cliente em seu banco de dados do cliente. Um CCN tem a seguinte taxonomia:

-   Dois dígitos para representar o ano em que o registro foi criado. A Contoso foi fundada em 2002, portanto, o valor mais antigo possível seria 02.

-   Três dígitos para representar o órgão responsável pela criação do registro. O intervalo de valores possível do órgão vai do 000 ao 999.

-   Um caractere alfabético para representar o ramo de atividade. Os valores possíveis vão de A a Z e não devem diferenciar maiúsculas de minúsculas.

-   Um número de série de quatro dígitos. O intervalo de valores possível de um número de série que vai de 0000 a 9999.

Exemplos de CCNs:

> 15080P9562
>
> 14040O1119
>
> 15020J8317
>
> 14050E2330
>
> 16050E2166
>
> 17040O1118

A Contoso sempre faz referência aos clientes usando um CCN nas correspondências interna e externa, em documentos, etc. A empresa deseja criar um tipo de informação confidencial personalizado para detectar o uso do CCN no Office 365 e assim aplicar proteção no uso desse formulário de dados pessoais.

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a>Criar um novo tipo de informação confidencial para o número de cliente da Contoso

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></th>
<th align="left"><strong>Ação</strong></th>
<th align="left"><strong>Resultado</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">A Contoso usa o PowerShell e a Pesquisa de Conteúdo para encontrar documentos que correspondem a um conjunto de exemplos de CCNs.</td>
<td align="left">

<p>#Conectar-se ao Centro de Conformidade e Segurança do Office 365</p>
<p>$adminUser = &quot;davib@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Criar e iniciar pesquisa de dados de exemplo</p>
<p>$searchName = &quot;Exemplo de Pesquisa de informações do cliente&quot;</p>
<p>$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</p>
<p>New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</p>
<p>Start-ComplianceSearch -Identity $searchName</p>
</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">A Contoso analisa os resultados. Todas as vezes que o CCN foi usado, uma data com formato da UE foi utilizada e uma dessas palavras-chave também foi usada em cerca de 300 caracteres.</td>
<td align="left">número de cliente, núm de cliente, n.º de cliente, n.cliente, cliente da Contoso</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">A Contoso desenvolveu o seguinte padrão de Expressão Regular (RegEx) para identificar seu CCN.</td>
<td align="left">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">A Contoso desenvolveu o seguinte padrão de Expressão Regular (RegEx) para identificar datas com formatos da UE usadas por suas diversas subsidiárias.</td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">A Contoso usa o PowerShell para gerar três GUIDs exclusivos.</td>
<td align="left"><p>#Gerar um GUID exclusivo para RulePack Id, Publisher Id e Entity Id</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left">A Contoso define os seguintes parâmetros para a regra de tipo de item confidencial.</td>
<td align="left"><p>Nome: Número de cliente da Contoso (CCN)</p>
<p>Descrição: o Número de cliente da Contoso (CCN) que procura outras palavras-chave e datas com o formato da UE</p></td>
</tr>
<tr class="odd">
<td align="left">7</td>
<td align="left">A Contoso cria um arquivo XML de um novo tipo de informação confidencial usado para detectar um Número de cliente da Contoso (CCN) e salva-o em um sistema de arquivos local como C:\Scripts\ContosoCCN.xml com codificação UTF-8.</td>
<td align="left">Veja o arquivo XML abaixo desta tabela.</td>
</tr>
<tr class="even">
<td align="left">8</td>
<td align="left">A Contoso cria o tipo de informação confidencial personalizada com o seguinte PowerShell.</td>
<td align="left"><p>#Conectar-se ao Centro de Conformidade e Segurança do Office 365</p>
<p>$adminUser = &quot;davib@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Criar novo tipo de informação confidencial</p>
<p>New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a>Exemplo de arquivo XML para o novo tipo de informação confidencial (etapa 7)
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
