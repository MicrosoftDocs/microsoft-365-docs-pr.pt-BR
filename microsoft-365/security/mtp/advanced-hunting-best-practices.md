---
title: Práticas recomendadas de consulta de busca avançada no Microsoft 365 Defender
description: Saiba como criar consultas rápidas, eficientes e livres de erros de busca de ameaças com busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, esquema, kusto, evitar tempo limites, linhas de comando, id do processo, otimizar, prática melhor, analisar, ingressar, resumir
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928469"
---
# <a name="advanced-hunting-query-best-practices"></a>Práticas recomendadas de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Aplique essas recomendações para obter resultados mais rapidamente e evitar tempos finais durante a execução de consultas complexas. Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Compreender as cotas de recursos da CPU
Dependendo de seu tamanho, cada locatário tem acesso a uma quantidade definida de recursos da CPU alocados para executar consultas de busca avançadas. Para obter informações detalhadas sobre vários limites de serviço, leia sobre cotas de busca avançada [e parâmetros de uso.](advanced-hunting-limits.md)

Os clientes que executarem várias consultas regularmente devem controlar o consumo e aplicar as diretrizes de otimização neste artigo para minimizar a interrupção resultante da exceção de cotas ou parâmetros de uso.

## <a name="general-optimization-tips"></a>Dicas gerais de otimização

- **Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Use [o limite](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) ou seu sinônimo para evitar grandes conjuntos de `take` resultados.
- Aplicar filtros cedo **—** Aplique filtros de tempo e outros filtros para reduzir o conjunto de dados, especialmente antes de usar funções de transformação e análise, como [substring(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction) [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction) [ou parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). No exemplo a seguir, a função de análise [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) é usada após os operadores de filtragem reduzirem o número de registros.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Tem batidas contém** para evitar pesquisar substrings dentro de palavras desnecessariamente, use o `has` operador em vez de `contains` . [Saiba mais sobre operadores de cadeia de caracteres](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Procure em colunas específicas**— procure em uma coluna específica em vez de executar pesquisas de texto completo em todas as colunas. Não use para `*` verificar todas as colunas.
- **Sensível a caso para velocidade —** as pesquisas que fazem parte de casos são mais específicas e geralmente mais bem-desempenho. Nomes de operadores de cadeia [de](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)caracteres que não são sensíveis a minúsculas, `has_cs` como e geralmente `contains_cs` terminam com `_cs` . Você também pode usar o operador igual a minúsculas em `==` vez de `=~` .
- **Analisar, não extraia sempre que** possível, use o operador de análise ou uma função de análise como [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) Evite o `matches regex` operador de cadeia de [caracteres ou a função extract(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)ambos usam expressão regular. Reserve o uso da expressão regular para cenários mais complexos. [Leia mais sobre funções de análise](#parse-strings)
- **Filtrar tabelas não expressões**— Não filtre em uma coluna calculada se você puder filtrar em uma coluna de tabela.
- **Sem termos de três caracteres**: evite comparar ou filtrar usando termos com três caracteres ou menos. Esses termos não são indexados e a correspondência deles exigirá mais recursos.
- **Projetar seletivamente**— Facilmente entenda seus resultados projetando apenas as colunas de que você precisa. Projetar colunas específicas antes de executar [junção ou](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) operações semelhantes também ajuda a melhorar o desempenho.

## <a name="optimize-the-join-operator"></a>Otimizar o `join` operador
O [operador de junção](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) mescla linhas de duas tabelas correspondendo valores em colunas especificadas. Aplique essas dicas para otimizar consultas que usam esse operador.

- **Tabela menor à esquerda**— O operador corresponde aos registros da tabela no lado esquerdo da instrução de junção com `join` os registros à direita. Ao ter a tabela menor à esquerda, menos registros precisarão ser corresponder, acelerando a consulta. 

    Na tabela a seguir, reduzimos a tabela esquerda para abranger apenas três dispositivos específicos antes de ingressar nele por `DeviceLogonEvents` `IdentityLogonEvents` SIDs de conta.
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- **Use** o tipo de junção interna — O tipo de junção padrão ou [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplica linhas na tabela esquerda pela tecla de junção antes de retornar uma linha para cada combinação à tabela direita. [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) Se a tabela esquerda tiver várias linhas com o mesmo valor para a chave, essas linhas serão desuplicadas para deixar uma única linha aleatória para `join` cada valor exclusivo.

    Esse comportamento padrão pode deixar de fora informações importantes da tabela esquerda que podem fornecer informações úteis. Por exemplo, a consulta abaixo mostrará apenas um email que contém um anexo específico, mesmo se esse mesmo anexo tiver sido enviado usando várias mensagens de email:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Para resolver essa limitação, aplicamos o tipo de junção interna especificando para mostrar todas as linhas na tabela esquerda com valores [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `kind=inner` correspondentes à direita:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Ingressar registros de uma janela de tempo**— Ao investigar eventos de segurança, os analistas pesquisam eventos relacionados que ocorrem durante o mesmo período de tempo. Aplicar a mesma abordagem ao usar também `join` beneficia o desempenho, reduzindo o número de registros a verificar.
    
    A consulta abaixo verifica se há eventos de logon dentro de 30 minutos após o recebimento de um arquivo mal-intencionado:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Aplicar filtros** de tempo em ambos os lados — Mesmo que você não esteja investigando uma janela de tempo específica, a aplicação de filtros de tempo nas tabelas esquerda e direita pode reduzir o número de registros para verificar e melhorar o `join` desempenho. A consulta a seguir se aplica `Timestamp > ago(1h)` a ambas as tabelas para que ela adera somente aos registros da última hora:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Use dicas de desempenho**— Use dicas com o operador para instruir o back-end a distribuir a carga ao executar operações que utilizam muitos `join` recursos. [Saiba mais sobre as dicas de junção](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Por exemplo, **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** a dica de embaralhar ajuda a melhorar o desempenho da consulta ao ingressar em tabelas usando uma chave com alta cardinalidade — uma chave com muitos valores exclusivos — como na consulta `AccountObjectId` abaixo:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    A **[dica de](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** transmissão ajuda quando a tabela esquerda é pequena (até 100.000 registros) e a tabela direita é extremamente grande. Por exemplo, a consulta abaixo está tentando juntar alguns  emails que têm assuntos específicos com todas as mensagens que contêm links na `EmailUrlInfo` tabela:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Otimizar o `summarize` operador
O [operador resumido](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) agrega o conteúdo de uma tabela. Aplique essas dicas para otimizar consultas que usam esse operador.

- **Encontre valores distintos**— Em geral, use `summarize` para encontrar valores distintos que possam ser repetitivos. Pode ser desnecessário usá-lo para agregar colunas que não têm valores repetitivos.

    Embora um único email possa fazer parte de  vários eventos, o exemplo a seguir não é um uso eficiente porque uma ID de mensagem de rede para um email individual sempre vem com um endereço de remetente `summarize` exclusivo.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    O `summarize` operador pode ser facilmente substituído por , o que gera `project` potencialmente os mesmos resultados enquanto consome menos recursos:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    O exemplo a seguir é um uso mais eficiente porque pode haver várias instâncias distintas de um endereço de remetente enviando emails para `summarize` o mesmo endereço de destinatário. Essas combinações são menos distintas e provavelmente têm duplicatas.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Embaralhar** a consulta — Embora seja melhor usado em colunas com valores repetitivos, as mesmas colunas também podem ter alta cardinalidade ou um grande número `summarize` de valores exclusivos.  Assim como o operador, você também pode aplicar a dica de embaralhar para distribuir a carga de processamento e potencialmente melhorar o desempenho ao operar em colunas com `join` alta [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalidade.

    A consulta abaixo usa para contar endereços de email de destinatário distintos, que podem ser executados em `summarize` centenas de milhares em grandes organizações. Para melhorar o desempenho, ele `hint.shufflekey` incorpora:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Cenários de consulta

### <a name="identify-unique-processes-with-process-ids"></a>Identificar processos exclusivos com IDs de processo
As IDs de processo (PIDs) são recicladas no Windows e reutilizadas para novos processos. Por si só, eles não servem como identificadores exclusivos para processos específicos.

Para obter um identificador exclusivo para um processo em um computador específico, use a ID do processo juntamente com o tempo de criação do processo. Ao juntar ou resumir dados em um processo, inclua colunas para o identificador da máquina (`DeviceId` ou `DeviceName`), a ID do processo (`ProcessId` ou `InitiatingProcessId`) e o tempo de criação do processo (`ProcessCreationTime` ou `InitiatingProcessCreationTime`)

O exemplo de consulta a seguir localiza processos que acessam mais de 10 endereços IP na porta 445 (SMB), possivelmente procurando por compartilhamentos de arquivos.

Exemplo de consulta:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

A consulta é resumida por tanto `InitiatingProcessId` quanto`InitiatingProcessCreationTime` para que ela examine um único processo, sem misturar vários processos com a mesma ID de processo.

### <a name="query-command-lines"></a>Linhas de comando de consulta
Há várias maneiras de criar uma linha de comando para executar uma tarefa. Por exemplo, um invasor pode fazer referência a um arquivo de imagem sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou entre aspas. O invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.

Para criar consultas mais duráveis ao redor das linhas de comando, aplique as seguintes práticas:

- Identifique os processos conhecidos (como *net.exe* ou *psexec.exe)* correspondendo aos campos de nome de arquivo, em vez de filtrar na própria linha de comando.
- Analisar seções de linha de comando usando a [função parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem. Em vez disso, use expressões regulares ou use vários operadores Contém separados.
- Correspondências que não diferenciam letras maiúsculas de minúsculas. Por exemplo, use `=~` , e em vez de , e `in~` `contains` `==` `in` `contains_cs` .
- Para atenuar as técnicas de ofuscação de linha de comando, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço. Há técnicas de ofuscação mais complexas que exigem outras abordagens, mas esses ajustes podem ajudar a resolver problemas comuns.

Os exemplos a seguir mostram várias maneiras de construir uma consulta que procura o arquivo *net.exe* para parar o serviço de firewall "MpsSvc":

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a>Ingestão de dados de fontes externas
Para incorporar listas longas ou tabelas grandes à sua consulta, use o operador [externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) para ingerir dados de um URI especificado. Você pode obter dados de arquivos em TXT, CSV, JSON ou [outros formatos.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) O exemplo a seguir mostra como você pode utilizar a lista extensa de hashes SHA-256 de malware fornecidos pelo MalwareBazaar (abuse.ch) para verificar anexos em emails:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Analisar cadeias de caracteres
Há várias funções que você pode usar para lidar com eficiência com cadeias de caracteres que precisam de análise ou conversão. 

| Cadeia de caracteres | Função | Exemplo de uso |
|--|--|--|
| Linhas de comando | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extraia o comando e todos os argumentos. | 
| Caminhos | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extraia as seções de um caminho de arquivo ou pasta. |
| Números de versão | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Descontrua um número de versão com até quatro seções e até oito caracteres por seção. Use os dados analisados para comparar a idade da versão. |
| Endereços IPv4 | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Converter um endereço IPv4 em um inteiro longo. Para comparar endereços IPv4 sem convertê-los, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Endereços IPv6 | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Converta um endereço IPv4 ou IPv6 para a notação IPv6 canônica. Para comparar endereços IPv6, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Para saber mais sobre todas as funções de análise com suporte, leia sobre as funções de cadeia [de caracteres Kusto.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Tópicos relacionados
- [Documentação da linguagem de consulta Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Cotas e parâmetros de uso](advanced-hunting-limits.md)
- [Lidar com erros de busca avançada](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
