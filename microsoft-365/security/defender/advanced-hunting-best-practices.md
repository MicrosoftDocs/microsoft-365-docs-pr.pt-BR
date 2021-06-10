---
title: Práticas recomendadas de consulta de busca avançada no Microsoft 365 Defender
description: Saiba como construir consultas de busca de ameaças rápidas, eficientes e sem erros com a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, esquema, kusto, evitar tempo de espera, linhas de comando, id do processo, otimizar, prática prática melhor, analisar, participar, resumir
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: abc6b561c2fca8106397b1656432628c983e2ece
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952687"
---
# <a name="advanced-hunting-query-best-practices"></a>Práticas recomendadas de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Aplique essas recomendações para obter resultados mais rápidos e evitar tempo de execução de consultas complexas. Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Compreender cotas de recursos da CPU
Dependendo de seu tamanho, cada locatário tem acesso a uma quantidade definida de recursos de CPU alocados para executar consultas de busca avançadas. Para obter informações detalhadas sobre vários limites de serviço, [leia sobre cotas de busca avançadas e parâmetros de uso.](advanced-hunting-limits.md)

Os clientes que executarem várias consultas regularmente devem controlar o consumo e aplicar as diretrizes de otimização neste artigo para minimizar a interrupção resultante de cotas excedentes ou parâmetros de uso.

## <a name="general-optimization-tips"></a>Dicas gerais de otimização

- **Tamanho de novas consultas**— Se você suspeitar que uma consulta retornará um conjunto de resultados grandes, avalie-a primeiro usando o operador [de contagem](/azure/data-explorer/kusto/query/countoperator). Use [limite](/azure/data-explorer/kusto/query/limitoperator) ou seu sinônimo `take` para evitar grandes conjuntos de resultados.
- **Aplicar filtros** mais cedo — aplique filtros de tempo e outros filtros para reduzir o conjunto de dados, especialmente antes de usar funções de transformação e análise, como [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)ou [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). No exemplo abaixo, a função de análise [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) é usada após os operadores de filtragem reduzirem o número de registros.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Tem batidas que contêm**— Para evitar pesquisar subdstrings em palavras desnecessariamente, use o `has` operador em vez de `contains` . [Saiba mais sobre operadores de cadeia de caracteres](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Procure em colunas específicas**— procure em uma coluna específica em vez de executar pesquisas de texto completo em todas as colunas. Não use para `*` verificar todas as colunas.
- **Case-sensitive para velocidade —** pesquisas sensíveis a caso são mais específicas e geralmente mais performant. Nomes de operadores de cadeia de caracteres sensíveis a [caso,](/azure/data-explorer/kusto/query/datatypes-string-operators) `has_cs` como e , geralmente `contains_cs` terminam com `_cs` . Você também pode usar o operador igual a minúsculas em `==` vez de `=~` .
- **Analisar, não extraia**— sempre que [](/azure/data-explorer/kusto/query/parseoperator) possível, use o operador de análise ou uma função de [análise como parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Evite o `matches regex` operador de cadeia de caracteres ou a função [extract(),](/azure/data-explorer/kusto/query/extractfunction)ambos usam expressão regular. Reserve o uso da expressão regular para cenários mais complexos. [Leia mais sobre funções de análise](#parse-strings)
- **Filtrar tabelas não expressões**— Não filtre em uma coluna calculada se você puder filtrar em uma coluna de tabela.
- **Sem termos de três caracteres**— Evite comparar ou filtrar usando termos com três caracteres ou menos. Esses termos não são indexados e a correspondência deles exigirá mais recursos.
- **Project seletivamente**— facilmente entenda seus resultados projetando apenas as colunas de que você precisa. Projetar colunas específicas antes de executar a [junção](/azure/data-explorer/kusto/query/joinoperator) ou operações semelhantes também ajuda a melhorar o desempenho.

## <a name="optimize-the-join-operator"></a>Otimizar o `join` operador
O [operador de junção](/azure/data-explorer/kusto/query/joinoperator) mescla linhas de duas tabelas combinando valores em colunas especificadas. Aplique essas dicas para otimizar consultas que usam esse operador.

- **Tabela menor à esquerda**— o operador corresponde a registros na tabela no lado esquerdo da instrução join aos `join` registros à direita. Ao ter a tabela menor à esquerda, menos registros precisarão ser corresponder, acelerando a consulta. 

    Na tabela abaixo, reduzimos a tabela esquerda para abranger apenas três dispositivos específicos antes de junção a ela por `DeviceLogonEvents` `IdentityLogonEvents` SIDs de conta.
 
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

- **Use** o sabor de junção interna — O sabor de junção padrão ou as linhas deduplicações de junção interna na tabela esquerda pela tecla de junção antes de retornar uma linha para cada partida à tabela direita. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) Se a tabela esquerda tiver várias linhas com o mesmo valor da chave, essas linhas serão deduplicadas para deixar uma única linha aleatória para `join` cada valor exclusivo.

    Esse comportamento padrão pode deixar de fora informações importantes da tabela esquerda que podem fornecer informações úteis. Por exemplo, a consulta abaixo mostrará apenas um email contendo um anexo específico, mesmo que esse mesmo anexo foi enviado usando várias mensagens de email:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Para resolver essa limitação, aplicamos o sabor de junção interna especificando para mostrar todas as linhas na tabela esquerda com valores [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `kind=inner` correspondentes à direita:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Ingressar registros de uma janela de** tempo — ao investigar eventos de segurança, os analistas pesquisam eventos relacionados que ocorrem ao redor do mesmo período de tempo. Aplicar a mesma abordagem ao usar também `join` beneficia o desempenho, reduzindo o número de registros a verificar.
    
    A consulta abaixo verifica se há eventos de logon dentro de 30 minutos após receber um arquivo mal-intencionado:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Aplique filtros** de tempo em ambos os lados — Mesmo que você não esteja investigando uma janela de tempo específica, a aplicação de filtros de tempo nas tabelas esquerda e direita pode reduzir o número de registros para verificar e melhorar o `join` desempenho. A consulta a seguir se aplica a ambas as tabelas para que ela `Timestamp > ago(1h)` insisse apenas registros da última hora:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Use dicas para desempenho**— Use dicas com o operador para instruir o back-end a distribuir carga ao executar operações de uso `join` intensivo de recursos. [Saiba mais sobre dicas de junção](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Por exemplo, **[](/azure/data-explorer/kusto/query/shufflequery)** a dica de embaralhar ajuda a melhorar o desempenho da consulta ao ingressar em tabelas usando uma chave com alta cardinalidade , uma chave com muitos valores exclusivos, como a consulta `AccountObjectId` abaixo:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    A **[dica de](/azure/data-explorer/kusto/query/broadcastjoin)** transmissão ajuda quando a tabela esquerda é pequena (até 100.000 registros) e a tabela direita é extremamente grande. Por exemplo, a consulta a seguir está tentando ingressar  alguns emails que têm assuntos específicos com todas as mensagens que contêm links na `EmailUrlInfo` tabela:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Otimizar o `summarize` operador
O [operador resumir](/azure/data-explorer/kusto/query/summarizeoperator) agrega o conteúdo de uma tabela. Aplique essas dicas para otimizar consultas que usam esse operador.

- **Encontre valores distintos**— em geral, use `summarize` para encontrar valores distintos que podem ser repetitivos. Pode ser desnecessário usá-lo para agregar colunas que não têm valores repetitivos.

    Embora um único email possa fazer parte de  vários eventos, o exemplo a seguir não é um uso eficiente porque uma ID de mensagem de rede para um email individual sempre vem com um endereço de `summarize` remetente exclusivo.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    O `summarize` operador pode ser facilmente substituído por , produtividade potencialmente os mesmos resultados enquanto consome menos `project` recursos:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    O exemplo a seguir é um uso mais eficiente porque pode haver várias instâncias distintas de um endereço de remetente enviando `summarize` emails para o mesmo endereço de destinatário. Essas combinações são menos distintas e provavelmente terão duplicatas.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Embaralhar** a consulta — embora seja melhor usado em colunas com valores repetitivos, as mesmas colunas também podem ter alta cardinalidade ou um grande número `summarize` de valores  exclusivos. Assim como o operador, você também pode aplicar a dica de embaralhar para distribuir a carga de processamento e potencialmente melhorar o desempenho ao operar em colunas com `join` alta [](/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalidade.

    A consulta a seguir usa para contar endereço de email de destinatário distinto, que pode ser executado em centenas `summarize` de milhares em grandes organizações. Para melhorar o desempenho, ele incorpora `hint.shufflekey` :

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
Há várias maneiras de criar uma linha de comando para executar uma tarefa. Por exemplo, um invasor pode fazer referência a um arquivo de imagem sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou com aspas. O invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.

Para criar consultas mais duráveis ao redor das linhas de comando, aplique as seguintes práticas:

- Identifique os processos conhecidos (comonet.exe *ou* *psexec.exe*) correspondendo aos campos de nome do arquivo, em vez de filtrar na própria linha de comando.
- Analisar seções de linha de comando usando a [função parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) 
- Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem. Em vez disso, use expressões regulares ou use vários operadores Contém separados.
- Correspondências que não diferenciam letras maiúsculas de minúsculas. Por exemplo, use `=~` `in~` , e, em vez de `contains` , e `==` `in` `contains_cs` .
- Para atenuar técnicas de ofuscação de linha de comando, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço. Há técnicas de ofuscação mais complexas que exigem outras abordagens, mas esses ajustes podem ajudar a resolver as comuns.

Os exemplos a seguir mostram várias maneiras de construir uma consulta que procura o arquivonet.exe *parar* o serviço de firewall "MpsSvc":

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

### <a name="ingest-data-from-external-sources"></a>Ingerir dados de fontes externas
Para incorporar listas longas ou tabelas grandes à sua consulta, use o operador [externaldata](/azure/data-explorer/kusto/query/externaldata-operator) para ingerir dados de um URI especificado. Você pode obter dados de arquivos em TXT, CSV, JSON ou [outros formatos.](/azure/data-explorer/ingestion-supported-formats) O exemplo a seguir mostra como você pode utilizar a extensa lista de hashes sha-256 de malware fornecidos pelo MalwareBazaar (abuse.ch) para verificar anexos em emails:

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
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Cadeias de caracteres de análise
Há várias funções que você pode usar para lidar com cadeias de caracteres com eficiência que precisam de análise ou conversão. 

| Cadeia de caracteres | Função | Exemplo de uso |
|--|--|--|
| Linhas de comando | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Extraia o comando e todos os argumentos. | 
| Caminhos | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Extraia as seções de um arquivo ou caminho de pasta. |
| Números de versão | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Desconstrua um número de versão com até quatro seções e até oito caracteres por seção. Use os dados analisados para comparar a idade da versão. |
| Endereços IPv4 | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Converta um endereço IPv4 em um inteiro longo. Para comparar endereços IPv4 sem convertê-los, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Endereços IPv6 | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Converta um endereço IPv4 ou IPv6 para a notação IPv6 canônica. Para comparar endereços IPv6, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Para saber mais sobre todas as funções de análise com suporte, [leia sobre as funções de cadeia de caracteres kusto](/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

>[!NOTE]
>Algumas tabelas neste artigo podem não estar disponíveis no Microsoft Defender para Ponto de Extremidade. [A Microsoft 365 Defender para](m365d-enable.md) procurar ameaças usando mais fontes de dados. Você pode mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender seguindo as etapas em Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de [Extremidade.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Tópicos relacionados
- [Documentação de idioma de consulta kusto](/azure/data-explorer/kusto/query/)
- [Cotas e parâmetros de uso](advanced-hunting-limits.md)
- [Manipular erros avançados de busca](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)