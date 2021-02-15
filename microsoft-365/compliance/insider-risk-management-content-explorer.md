---
title: Explorador de Conteúdo de gerenciamento de riscos do Insider
description: Saiba mais sobre o Explorador de Conteúdo de Gerenciamento de Riscos Insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de riscos insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 6eb8bf91f5af60658686066b75b33b7a8dabe6bc
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070865"
---
# <a name="insider-risk-management-content-explorer"></a>Explorador de Conteúdo de gerenciamento de riscos do Insider

O Explorador de Conteúdo de gerenciamento de riscos insider permite que os usuários atribuídos à função Investigadores de Gerenciamento de Riscos Do *Insider* examinem o contexto e os detalhes do conteúdo associado à atividade em alertas. Para todos os alertas confirmados para um caso, cópias de dados e arquivos de mensagens são arquivadas como um instantâneo no tempo dos itens, mantendo os arquivos e mensagens originais nas fontes de armazenamento. A cópia de dados e mensagens é transparente para o usuário associado ao alerta e para o proprietário do conteúdo. Se o conteúdo incluir permissões de gerenciamento de Direitos de Informação, essas permissões serão mantidas para o conteúdo copiado e os usuários atribuídos à função Investigadores do Gerenciamento de Riscos Do *Insider* precisarão dessas permissões e direitos se eles precisam abrir e exibir os arquivos. Cada arquivo e mensagem recebe automaticamente uma ID de arquivo exclusiva no caso de gerenciamento de riscos interno para fins de gerenciamento. Documentos associados a atividades de indicador de dispositivo não são incluídos no Explorador de Conteúdo.

![Explorador de conteúdo de gerenciamento de riscos do Insider](../media/insider-risk-content-explorer.png)

## <a name="column-options"></a>Opções de coluna

Para facilitar a análise de dados e mensagens capturadas por analistas de risco e investigadores, além de analisar o contexto do caso, várias ferramentas de filtragem e classificação estão incluídas no Explorador de Conteúdo. Para classificação básica, as  colunas de classe **Data** e Arquivo suportam a classificação usando os títulos de coluna no painel de fila de conteúdo. Outras colunas de fila estão disponíveis para adicionar ao modo de exibição e fornecer pivôs diferentes nos arquivos e mensagens.

Para adicionar ou remover títulos de coluna para a fila de conteúdo, use o controle Editar **colunas** e selecione uma das opções de coluna a seguir. Essas colunas são mapeadas para as condições comuns, de email e de propriedade do documento com suporte no Explorador de Conteúdo e listadas posteriormente neste artigo.

| **Opção de coluna** | **Descrição** |
|:------------------|:----------------|
| **Author** | O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário criar um documento e enviá-lo por email para outra pessoa que o carrega no SharePoint, o documento ainda manterá o autor original. |
| **Bcc** | Disponível para mensagens de email, os usuários no campo de mensagem Cc. |
| **Cc** | Disponível para mensagens de email, os usuários no campo de mensagem Cc. |
| **Caminho composto** | Caminho acessível para humanos que descreve a origem do item. |
| **ID da Conversa** | ID da conversa da mensagem. |
| **Índice de conversa** | Índice de conversa da mensagem. |
| **Hora de criação** | A hora em que o arquivo ou a mensagem de email foi criado. |
| **Date** | Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez. |
| **Tema dominante** | Tema dominante conforme calculado para análise. |
| **ID do conjunto de emails** | ID do grupo para todas as mensagens no mesmo conjunto de emails. |
| **ID da Família** | A ID de família reúne todos os itens; para email, esta coluna inclui a mensagem e todos os anexos; para documentos, essa coluna inclui o documento e todos os itens incorporados. |
| **Classe file** | Para conteúdo do SharePoint e do OneDrive: **Documento**; para conteúdo do Exchange: **Email ou **Anexo.** |
| **ID do arquivo** | Identificador de documento exclusivo dentro da ocorrência. |
| **Ícone de tipo de arquivo** | A extensão de um arquivo; por exemplo, docx, um, pptx ou xlsx. Esse campo é a mesma propriedade que a propriedade do site FileExtension. |
| **ID** | O identificador GUID do arquivo. |
| **ID Imutável** | ID imutável armazenada no Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análise: **0** - não inclusivo; **1** - inclusive; **2** - menos inclusivo; **3** - cópia inclusiva. |
| **Última modificação** | A data em que um documento foi alterado pela última vez. |
| **Marcado como representante** | Um documento de cada conjunto de duplicatas exatas é marcado como representantes. |
| **Tipo de mensagem** | O tipo de mensagem de email a ser pesquisada. Valores possíveis: contatos, documentos, email, dados externos, faxes, mensagens, diários, reuniões, microsoft teams (retorna itens de chats, reuniões e chamadas no Microsoft Teams), anotações, postagens, rssfeeds, tarefas, caixa postal |
| **Participantes** | Lista de todos os participantes de uma mensagem; por exemplo, Remetente, Para, Cc, Cc. |
| **ID do pivô** | A ID de um pivô. |
| **Received** | A data em que uma mensagem de email foi recebida pelo destinatário. Esse campo é a mesma propriedade da propriedade de email Received. |
| **Destinatários** | Todos os campos de destinatário em uma mensagem de email. Esses campos são Para, Cc e Cc. |
| **ID do Representante** | Identificador numérico de cada conjunto de duplicatas exatas. |
| **Sender** | O remetente de uma mensagem de email. |
| **Remetente/Autor** | Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo autor de documentos do Office. Você pode digitar mais de um nome, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |
| **Sent** | A data em que uma mensagem de email foi enviada pelo remetente. Esse campo é a mesma propriedade que a propriedade de email Enviado. |
| **Tamanho** | Para emails e documentos, o tamanho do item (em bytes). |
| **Assunto** | O texto na linha de assunto de uma mensagem de email. |
| **Assunto/Título** | Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. Conforme explicado anteriormente, a propriedade Title são metadados especificados nos documentos do Microsoft Office. Você pode digitar o nome de mais de um assunto/título, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |
| **Lista de temas** | Lista de temas conforme calculado para análise. |
| **Title** | O título do documento. A propriedade Title consiste em metadados que são especificados em documentos do Office. É diferente do nome do arquivo do documento. |
| **To** | O destinatário de uma mensagem de email no campo Para. |

## <a name="advanced-search-conditions"></a>Condições de pesquisa avançada

Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) por um operador lógico (que é representado como c:c) que é semelhante em funcionalidade ao operador AND. Isso significa que os itens devem atender à consulta de palavra-chave e a uma ou mais condições a serem incluídas nos resultados da pesquisa. Essa funcionalidade é como as condições ajudam a restringir seus resultados.

Para ferramentas avançadas de  pesquisa e filtro, expanda o painel Filtro no lado esquerdo da fila de conteúdo. Selecione o **botão Adicionar uma** condição para abrir a lista de condições:

### <a name="operators-used-with-conditions"></a>Operadores usados com condições

|**Operator**|**Equivalente de consulta**|**Descrição**|
|:-----------|:-------------------|:--------------|
| **After** |`property>date`| Usado com condições de data. Retorna itens que foram enviados, recebidos ou modificados após a data especificada.|
| **Before** |`property<date`| Usado com condições de data. Retorna itens que foram enviados, recebidos ou modificados antes da data especificada.|
| **Between** |`date..date`| Use com condições de data e tamanho. Quando usado com uma condição de data, retorna itens que foram enviados, recebidos ou modificados no intervalo de datas especificado. Quando usado com uma condição de tamanho, retorna itens cujo tamanho está dentro do intervalo especificado.|
| **Contém todos os** |`(property:value) OR (property:value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que contêm todos os valores de cadeia de caracteres especificados. |
| **Contains any of** |`(property:value) OR (property:value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que contêm qualquer parte de um ou mais valores da cadeia de caracteres especificada.|
| **Contém nenhum dos** |`-property:value`  <br/> `NOT property:value`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não contêm qualquer parte do valor da cadeia de caracteres especificada.|
| **Não é igual a nenhum dos** |`-property=value`  <br/> `NOT property=value`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não contêm a cadeia de caracteres específica.|
| **Igual a** |`size=value`| Retorna itens que são iguais ao tamanho especificado. <sup>1</sup>|
| **Igual a qualquer** |`(property=value) OR (property=value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que são uma correspondência exata de um ou mais valores da cadeia de caracteres especificada.|
| **Igual a nenhum dos** |`(property=value) OR (property=value)`| Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não corresponderem a um ou mais valores de cadeia de caracteres especificados. |
| **Maior que** |`size>value`| Retorna itens em que a propriedade especificada é maior do que o valor especificado. <sup>1</sup>|
| **Greater or equal** |`size>=value`| Retorna itens em que a propriedade especificada é maior ou igual ao valor especificado. <sup>1</sup>|
| **Menor que** |`size<value`| Retorna itens que são maiores ou iguais ao valor específico. <sup>1</sup>|
| **Less or equal** |`size<=value`| Retorna itens que são maiores ou iguais ao valor específico. <sup>1</sup>|
| **Not equal** |`size<>value`| Retorna itens que não são iguais ao tamanho especificado. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> Esse operador está disponível somente para condições que usam a propriedade Size.

### <a name="common-property-conditions"></a>Condições comuns de propriedade

| **Opção de condição** | **Descrição** |
|:---------------------|:----------------|
| **Date** | Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez. |
| **Remetente/Autor** | Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo autor de documentos do Office. Você pode digitar mais de um nome, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador **OR**. |
| **Tamanho** | Para emails e documentos, o tamanho do item (em bytes). |
| **Assunto/Título** | Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. A propriedade Title em documentos são metadados especificados nos documentos do Microsoft Office. Você pode digitar o nome de mais de um assunto/título, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |

### <a name="email-property-conditions"></a>Condições de propriedade de email

A tabela a seguir lista as condições de propriedade de mensagem de email disponíveis no Explorador de Conteúdo.

| **Opção de condição** | **Descrição** |
|:---------------------|:----------------|
| **Bcc** | O campo Cc de uma mensagem de email. |
| **Cc** | O campo Cc de uma mensagem de email. |
| **Segurança de email** | Configuração de segurança da mensagem. |
| **Sensibilidade de email** | Configuração de sensibilidade da mensagem. |
| **ID do conjunto de emails** | ID do grupo para todas as mensagens no mesmo conjunto de emails. |
| **De** | O remetente de uma mensagem de email. |
| **Tem anexo** | Indica se uma mensagem tem um anexo. Use os valores **true** ou **false**. |
| **Importance** | A prioridade de uma mensagem de email, que um remetente pode especificar ao enviar uma mensagem. Por padrão, as mensagens são enviadas com prioridade normal, a menos que o remetente defina a prioridade como **alta** ou **baixa**. |
| **Data de término da reunião** | Data de término da reunião para reuniões. |
| **Data de início da reunião** | Data de início da reunião para reuniões. |
| **Tipo de mensagem** | O tipo de mensagem de email a ser pesquisada. Valores possíveis: contatos, documentos, email, dados externos, faxes, mensagens, diários, reuniões, microsoft teams (retorna itens de chats, reuniões e chamadas no Microsoft Teams), anotações, postagens, rssfeeds, tarefas, caixa postal |
| **Domínio do participante** | Lista de todos os domínios de participantes de uma mensagem. |
| **Participantes** | Todos os campos de pessoas em uma mensagem de email. Esses campos são From, To, Cc e Cc. |
| **Received** | A data em que uma mensagem de email foi recebida pelo destinatário. |
| **Domínios de destinatários** | Lista de todos os domínios de destinatários de uma mensagem. |
| **Sender** | Campo Remetente (De) para tipos de mensagem.  O formato é **DisplayName \<SmtpAddress>**. |
| **Domínio do remetente** | Domínio do remetente. |
| **Assunto** | O texto na linha de assunto de uma mensagem de email.  <br/> **Observação:** Quando você usa a propriedade Subject em uma consulta, a pesquisa retorna todas as mensagens nas quais a linha de assunto contém o texto que você está procurando. Em outras palavras, a consulta não retorna apenas as mensagens que têm uma combinação exata. Por exemplo, se você pesquisar , seus resultados incluirão mensagens com o assunto `subject:"Quarterly Financials"` "Finanças Trimestrais de 2018". |
| **To** | O campo Para de uma mensagem de email. |
| **Exclusivo no conjunto de emails** | False se houver uma duplicata do anexo em seu conjunto de emails. |

## <a name="document-property-conditions"></a>Condições de propriedade do documento

A tabela a seguir lista as condições de propriedade de documentos disponíveis no Explorador de Conteúdo. Muitas dessas condições de propriedade são compartilhadas com conjuntos de revisão incluídos [em casos de Descoberta Avançada.](document-metadata-fields-in-Advanced-eDiscovery.md)

| **Opção de condição** | **Descrição** |
|:---------------------|:----------------|
| **Pontuação de privilégio advogado-cliente** | Pontuação de conteúdo do modelo de privilégio advogado-cliente. |
| **Author** | O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário criar um documento e enviá-lo por email para outra pessoa que o carrega no SharePoint, o documento ainda manterá o autor original. |
| **Rótulos de conformidade** | Rótulos de conformidade aplicados no Office 365. |
| **Caminho composto** | Caminho acessível para humanos que descreve a origem do item. |
| **ID da Conversa** | ID da conversa da mensagem. |
| **Hora de criação** | A hora em que o arquivo ou a mensagem de email foi criado. |
| **Custodian** | Nome do custodiatário ao que o item estava associado. |
| **Tema dominante** | Tema dominante conforme calculado para análise. |
| **ID da Família** | A ID de família reúne todos os itens; para email, esse campo inclui a mensagem e todos os anexos; para documentos, esse campo inclui o documento e todos os itens incorporados. |
| **Classe file** | Para conteúdo do SharePoint e do OneDrive: **Documento**; para conteúdo do Exchange: **Email ou **Anexo.** |
| **Tipos de arquivo** | A extensão de um arquivo; por exemplo, docx, um, pptx ou xlsx. |
| **Tem um participante advogado** | True quando pelo menos um dos participantes é encontrado na lista de advogados; Caso contrário, o valor será False. |
| **ID Imutável** | ID imutável armazenada no Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análise: **0** - não inclusivo; **1** - inclusive; **2** - menos inclusivo; **3** - cópia inclusiva. |
| **Classe item** | Classe de item fornecida pelo servidor exchange; por exemplo, **IPM. Observação** |
| **Última modificação** | A data em que um documento foi alterado pela última vez. |
| **ID de carregamento** | ID de carregamento, na qual o item foi carregado em um conjunto de revisão. |
| **Nome do local** | Cadeia de caracteres que identifica a origem do item.  Para o Exchange, esse campo será o endereço SMTP da caixa de correio. Para o SharePoint e o OneDrive, a URL para o conjunto de sites. |
| **Marcado como representante** | Um documento de cada conjunto de duplicatas exatas é marcado como representantes. |
| **Extensão de arquivo nativa** | Extensão nativa do item. |
| **Nome do arquivo nativo** | Nome de arquivo nativo do item. |
| **NdEtSortExclAttach** | Concatenação de conjunto de emails e conjunto de ND para uma classificação eficiente no momento da revisão; D é adicionado como um prefixo para conjuntos de ND e E é adicionado a conjuntos de email. |
| **ID do pivô** | A ID de um pivô. |
| **Potencialmente privilegiado** | True se o modelo de detecção de privilégio advogado-cliente considerar o documento potencialmente privilegiado. |
| **Status do processamento** | Status de processamento depois que o item foi adicionado a um conjunto de revisão. |
| **Percentil de leitura** | Percentil de leitura do documento com base na relevância. |
| **Pontuação de relevância** | Pontuação de relevância de um documento com base na relevância. |
| **Marca de relevância** | Pontuação de relevância de um documento com base na relevância. |
| **ID do Representante** | Identificador numérico de cada conjunto de duplicatas exatas. |
| **Marcas** | Marcas aplicadas em um conjunto de revisão. |
| **Lista de temas** | Lista de temas conforme calculado para análise. |
| **Title** | O título do documento. A propriedade Title consiste em metadados que são especificados em documentos do Office. É diferente do nome do arquivo do documento. |
| **Foi remediado** | True se o item foi remediado; caso contrário, False. |
| **Contagem de palavras** | O número de palavras em um arquivo. |
