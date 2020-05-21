---
title: Gerenciador de conteúdo de gerenciamento de risco do insider
description: Saiba mais sobre o Gerenciador de conteúdo de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: e48b18ee905bc8589ad3fd6145630b436603ae15
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327045"
---
# <a name="insider-risk-management-content-explorer"></a>Gerenciador de conteúdo de gerenciamento de risco do insider

O Gerenciador de conteúdo do insider Management permite que os usuários tenham a função de **investigadores de gerenciamento de risco do insider** para examinar o contexto e detalhes das comunicações capturadas em alertas. Para todos os alertas, as cópias de dados e arquivos de mensagens são arquivadas como um instantâneo no momento dos itens, mantendo os arquivos e mensagens originais nas fontes de armazenamento. A cópia de dados e mensagens é transparente para o funcionário associado ao alerta e ao proprietário do conteúdo. As configurações de permissão e os direitos de acesso dos dados são mantidos para o conteúdo copiado e as mensagens e os analistas de risco e os investigadores precisam dessas permissões e direitos se precisarem abrir e exibir os arquivos. Cada arquivo e mensagem recebe automaticamente uma ID de arquivo exclusiva no caso de gerenciamento de risco do insider para fins de gerenciamento.

## <a name="column-options"></a>Opções de coluna

Para tornar mais fácil para os analistas e investigadores de risco analisar os dados capturados e as mensagens e revisar o contexto para o caso, várias ferramentas de filtragem e classificação estão incluídas no Gerenciador de conteúdo. Para classificação básica, as colunas de **classe** de **Data** e arquivo dão suporte à classificação usando os títulos de coluna no painel de fila de conteúdo. Outras colunas de fila estão disponíveis para adicionar ao modo de exibição para fornecer pivôs diferentes nos arquivos e mensagens.

Para adicionar ou remover cabeçalhos de coluna para a fila de conteúdo, use o controle **Editar colunas** e selecione uma das opções de coluna a seguir. Essas colunas são mapeadas para as condições de propriedade comuns, de email e de documento compatíveis com o Gerenciador de conteúdo e listadas posteriormente neste tópico.

| **Opção de coluna** | **Descrição** |
|:------------------|:----------------|
| **Author** | O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário cria um documento e o email para alguém que o carrega para o SharePoint, o documento ainda manterá o autor original. |
| **Bcc** | Disponível para mensagens de email, os usuários no campo mensagem Cco. |
| **Cc** | Disponível para mensagens de email, os usuários no campo mensagem CC. |
| **Caminho composto** | Caminho legível humana que descreve a fonte do item. |
| **ID da conversa** | ID da conversa da mensagem. |
| **Índice de conversa** | Índice de conversa da mensagem. |
| **Hora da criação** | A hora em que o arquivo ou a mensagem de email foi criada. |
| **Date** | Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez. |
| **Tema dominante** | Tema dominante conforme calculado para a análise. |
| **ID do conjunto de emails** | ID de grupo para todas as mensagens no mesmo conjunto de email. |
| **ID da família** | Grupos de ID de família juntos todos os itens; para email, isso inclui a mensagem e todos os anexos; para documentos, isso inclui o documento e todos os itens incorporados. |
| **Classe de arquivo** | Para conteúdo do SharePoint e do OneDrive: **Document**; para o conteúdo do Exchange: * * email ou **anexo**. |
| **ID de arquivo** | Identificador de documento exclusivo no caso. |
| **Ícone de tipo de arquivo** | A extensão de um arquivo; por exemplo, docx, One, pptx ou xlsx. Essa propriedade é igual à propriedade de site FileExtension. |
| **ID** | O identificador de GUID para o arquivo. |
| **ID Imutável** | ID imutável, conforme armazenado no Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análise: **0** -não inclusivo; **1** -inclusive; **2** – menos inclusivo; cópia **3** incluindo. |
| **Última modificação** | A data em que um documento foi alterado pela última vez. |
| **Marcado como representante** | Um documento de cada conjunto de duplicatas exatas é marcado como representante. |
| **Tipo de mensagem** | O tipo de mensagem de email a ser pesquisada. Valores possíveis: contatos, Docs, email, dados externos, faxes, mensagens instantâneas, diários, reuniões, Microsoft Teams (retorna itens de chats, reuniões e chamadas no Microsoft Teams), observações, postagens, rssfeeds, tarefas, caixa postal |
| **Participante** | Lista de todos os participantes de uma mensagem; por exemplo, remetente, para, CC, Cco. |
| **ID da tabela dinâmica** | A ID de uma tabela dinâmica. |
| **Received** | A data em que uma mensagem de email foi recebida pelo destinatário. Essa propriedade é igual à propriedade de email Received. |
| **Destinatários** | Todos os campos de destinatários em uma mensagem de email. Esses campos são para, CC e Cco. |
| **ID do representante** | Identificador numérico de cada conjunto de duplicatas exatas. |
| **Sender** | O remetente de uma mensagem de email. |
| **Remetente/autor** | Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo autor de documentos do Office. Você pode digitar mais de um nome, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |
| **Sent** | A data em que uma mensagem de email foi enviada pelo remetente. Essa propriedade é igual à propriedade de email Sent. |
| **Tamanho** | Para emails e documentos, o tamanho do item (em bytes). |
| **Assunto** | O texto na linha de assunto de uma mensagem de email. |
| **Assunto/título** | Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. Como explicado anteriormente, a propriedade Title é Metadata especificado em documentos do Microsoft Office. Você pode digitar o nome de mais de um assunto/título, separados por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |
| **Lista de temas** | Lista de temas conforme calculado para análise. |
| **Title** | O título do documento. A propriedade Title consiste em metadados que são especificados em documentos do Office. É diferente do nome de arquivo do documento. |
| **To** | O destinatário de uma mensagem de email no campo para. |

## <a name="advanced-search-conditions"></a>Condições de pesquisa avançada

Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é conectada logicamente à consulta de palavra-chave (especificada na caixa palavra-chave) por um operador lógico (que é representado como c:c) que é semelhante em funcionalidade ao operador AND. Isso significa que os itens precisam satisfazer a consulta de palavra-chave e uma ou mais condições a serem incluídas nos resultados da pesquisa. É assim que as condições ajudam a restringir os resultados.

Para ferramentas de filtro e pesquisa avançadas, expanda o painel de **filtro** no lado esquerdo da fila de conteúdo. Selecione o botão **Adicionar uma condição** para abrir a lista de condições:

### <a name="operators-used-with-conditions"></a>Operadores usados com condições

|**Operator**|**Equivalente de consulta**|**Descrição**|
|:-----------|:-------------------|:--------------|
| **After** |`property>date`| Usado com condições de data. Retorna itens que foram enviados, recebidos ou modificados após a data especificada.|
| **Before** |`property<date`| Usado com condições de data. Retorna itens que foram enviados, recebidos ou modificados antes da data especificada.|
| **Entre** |`date..date`| Use com condições de data e tamanho. Quando usado com uma condição de data, retorna itens que foram enviados, recebidos ou modificados no intervalo de datas especificado. Quando usado com uma condição de tamanho, retorna itens cujo tamanho está dentro do intervalo especificado.|
| **Contém todos os** |`(property:value) OR (property:value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que contêm todos os valores de cadeia de caracteres especificados. |
| **Contains any of** |`(property:value) OR (property:value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que contêm qualquer parte de um ou mais valores da cadeia de caracteres especificada.|
| **Não contém nenhum dos** |`-property:value`  <br/> `NOT property:value`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não contêm qualquer parte do valor da cadeia de caracteres especificada.|
| **Não é igual a qualquer um dos** |`-property=value`  <br/> `NOT property=value`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não contêm a cadeia de caracteres específica.|
| **Igual a** |`size=value`| Retorna itens que são iguais ao tamanho especificado. <sup>1</sup>|
| **Igual a qualquer** |`(property=value) OR (property=value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que são uma correspondência exata de um ou mais valores da cadeia de caracteres especificada.|
| **É igual a nenhum de** |`(property=value) OR (property=value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não correspondem a um ou mais valores de cadeia de caracteres especificados. |
| **Maior que** |`size>value`| Retorna itens em que a propriedade especificada é maior do que o valor especificado. <sup>1</sup>|
| **Greater or equal** |`size>=value`| Retorna itens em que a propriedade especificada é maior ou igual ao valor especificado. <sup>1</sup>|
| **Menos de** |`size<value`| Retorna itens que são maiores ou iguais ao valor específico. <sup>1</sup>|
| **Less or equal** |`size<=value`| Retorna itens que são maiores ou iguais ao valor específico. <sup>1</sup>|
| **Not equal** |`size<>value`| Retorna itens que não são iguais ao tamanho especificado. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> esse operador está disponível somente para condições que usam a propriedade Size.

### <a name="common-property-conditions"></a>Condições de propriedade comuns

| **Opção de condição** | **Descrição** |
|:---------------------|:----------------|
| **Date** | Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez. |
| **Remetente/autor** | Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo autor de documentos do Office. Você pode digitar mais de um nome, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador **OR**. |
| **Tamanho** | Para emails e documentos, o tamanho do item (em bytes). |
| **Assunto/título** | Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. A propriedade Title em documentos é metadados especificados em documentos do Microsoft Office. Você pode digitar o nome de mais de um assunto/título, separados por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |

### <a name="email-property-conditions"></a>Condições de propriedade de email

A tabela a seguir lista as condições de propriedade da mensagem de email disponíveis no Gerenciador de conteúdo.

| **Opção de condição** | **Descrição** |
|:---------------------|:----------------|
| **Bcc** | O campo Cco de uma mensagem de email. |
| **Cc** | O campo CC de uma mensagem de email. |
| **Segurança de email** | Configuração de segurança da mensagem. |
| **Confidencialidade de email** | Configuração de sensibilidade da mensagem. |
| **ID do conjunto de emails** | ID de grupo para todas as mensagens no mesmo conjunto de email. |
| **De** | O remetente de uma mensagem de email. |
| **Tem anexo** | Indica se uma mensagem tem um anexo. Use os valores **true** ou **false**. |
| **Importance** | A prioridade de uma mensagem de email, que um remetente pode especificar ao enviar uma mensagem. Por padrão, as mensagens são enviadas com prioridade normal, a menos que o remetente defina a prioridade como **alta** ou **baixa**. |
| **Data de término da reunião** | Data de término da reunião para reuniões. |
| **Data de início da reunião** | Data de início da reunião para reuniões. |
| **Tipo de mensagem** | O tipo de mensagem de email a ser pesquisada. Valores possíveis: contatos, Docs, email, dados externos, faxes, mensagens instantâneas, diários, reuniões, Microsoft Teams (retorna itens de chats, reuniões e chamadas no Microsoft Teams), observações, postagens, rssfeeds, tarefas, caixa postal |
| **Domínio participante** | Lista de todos os domínios de participantes de uma mensagem. |
| **Participante** | Todos os campos de pessoas em uma mensagem de email. Esses campos são de, para, CC e Cco. |
| **Received** | A data em que uma mensagem de email foi recebida pelo destinatário. |
| **Domínios de destinatário** | Lista de todos os domínios de destinatários de uma mensagem. |
| **Sender** | Campo remetente (de) para tipos de mensagem.  Format é **DisplayName \< smtpAddress>**. |
| **Domínio do remetente** | Domínio do remetente. |
| **Assunto** | O texto na linha de assunto de uma mensagem de email.  <br/> **Observação:** Quando você usa a propriedade Subject em uma consulta, a pesquisa retorna todas as mensagens nas quais a linha de assunto contém o texto que você está pesquisando. Em outras palavras, a consulta não retorna apenas as mensagens que têm uma correspondência exata. Por exemplo, se você procurar `subject:"Quarterly Financials"` , seus resultados incluirão mensagens com o assunto "Finanças Trimestralmente 2018". |
| **To** | O campo Para de uma mensagem de email. |
| **Exclusivo no conjunto de emails** | False se houver uma duplicata do anexo em seu conjunto de emails. |

## <a name="document-property-conditions"></a>Condições de Propriedade do documento

A tabela a seguir lista as condições de propriedade dos documentos disponíveis no Gerenciador de conteúdo. Muitas dessas condições de propriedade são compartilhadas com os conjuntos de revisão incluídos em [casos de descoberta eletrônica avançados](document-metadata-fields-in-Advanced-eDiscovery.md).

| **Opção de condição** | **Descrição** |
|:---------------------|:----------------|
| **Pontuação de privilégio de cliente advogado** | Advogado-Pontuação de conteúdo do modelo de privilégio do cliente. |
| **Author** | O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário cria um documento e o email para alguém que o carrega para o SharePoint, o documento ainda manterá o autor original. |
| **Rótulos de conformidade** | Rótulos de conformidade aplicados no Office 365. |
| **Caminho composto** | Caminho legível humana que descreve a fonte do item. |
| **ID da conversa** | ID da conversa da mensagem. |
| **Hora da criação** | A hora em que o arquivo ou a mensagem de email foi criada. |
| **Custodian** | Nome dos responsáveis com os quais o item foi associado. |
| **Tema dominante** | Tema dominante conforme calculado para a análise. |
| **ID da família** | Grupos de ID de família juntos todos os itens; para email, isso inclui a mensagem e todos os anexos; para documentos, isso inclui o documento e todos os itens incorporados. |
| **Classe de arquivo** | Para conteúdo do SharePoint e do OneDrive: **Document**; para o conteúdo do Exchange: * * email ou **anexo**. |
| **Tipos de arquivo** | A extensão de um arquivo; por exemplo, docx, One, pptx ou xlsx. |
| **Tem participante advogado** | True quando pelo menos um dos participantes é encontrado na lista advogado; caso contrário, o valor será false. |
| **ID Imutável** | ID imutável, conforme armazenado no Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análise: **0** -não inclusivo; **1** -inclusive; **2** – menos inclusivo; cópia **3** incluindo. |
| **Classe de item** | Classe de item fornecida pelo Exchange Server; por exemplo, **IPM. Observação** |
| **Última modificação** | A data em que um documento foi alterado pela última vez. |
| **ID de carregamento** | ID de carregamento, no qual o item foi carregado em um conjunto de revisão. |
| **Nome do local** | Cadeia de caracteres que identifica a origem do item.  Para o Exchange, esse será o endereço SMTP da caixa de correio. Para o SharePoint e o OneDrive, a URL para o conjunto de sites. |
| **Marcado como representante** | Um documento de cada conjunto de duplicatas exatas é marcado como representante. |
| **Extensão de arquivo nativo** | Extensão nativa do item. |
| **Nome do arquivo nativo** | Nome do arquivo nativo do item. |
| **NdEtSortExclAttach** | Concatenação de conjunto de emails e ND definidos para classificação eficiente no momento da revisão; D é adicionado como um prefixo a ND sets e e é adicionado aos conjuntos de emails. |
| **ID da tabela dinâmica** | A ID de uma tabela dinâmica. |
| **Potencialmente privilegiado** | True se o modelo de detecção de privilégio de cliente do advogado considerar o documento potencialmente privilegiado. |
| **Status de processamento** | Status de processamento após o item ter sido adicionado a um conjunto de revisão. |
| **Ler percentil** | Leia o percentil do documento com base na relevância. |
| **Pontuação de relevância** | Pontuação de relevância de um documento com base na relevância. |
| **Marca de relevância** | Pontuação de relevância de um documento com base na relevância. |
| **ID do representante** | Identificador numérico de cada conjunto de duplicatas exatas. |
| **Marcas** | Marcas aplicadas em um conjunto de revisão. |
| **Lista de temas** | Lista de temas conforme calculado para análise. |
| **Title** | O título do documento. A propriedade Title consiste em metadados que são especificados em documentos do Office. É diferente do nome de arquivo do documento. |
| **Foi corrigido** | True se o item foi corrigido, caso contrário, false. |
| **Contagem de palavras** | O número de palavras em um arquivo. |
