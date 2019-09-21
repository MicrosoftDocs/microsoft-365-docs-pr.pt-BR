---
title: Documentar campos de metadados em investigações de dados (versão prévia)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 41e551850b47bec88f6dd8353c6db02048255e74
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071909"
---
# <a name="document-metadata-fields-in-data-investigations-preview"></a>Documentar campos de metadados em investigações de dados (versão prévia)

A tabela a seguir lista os campos de metadados para documentos em um conjunto de evidências em uma investigação em investigações de dados (prévia). A tabela indica o nome do campo de metadados, se o campo pode ser pesquisado durante a execução de uma consulta em um conjunto de evidências, se o campo está presente ao exibir os metadados de arquivo de um documento selecionado em um conjunto de evidências e se o campo é incluído quando os documentos são exportados. 

> [!NOTE]
> Os valores entre parênteses na coluna de **conjunto de evidência pesquisável** é o nome da propriedade que você pode pesquisar. Os valores entre parênteses na coluna de **metadados de arquivo visível** é o nome da propriedade que é exibida quando você está exibindo os metadados do arquivo.

|**Nome do campo** </br>|**Pesquisável no conjunto de evidências** |**Visível nos metadados do arquivo** |**Exported** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Marcas de caso                  | Sim (marcas)                                      |                         | Sim         |
|Rótulos de conformidade          |                                                 |                         | Sim         |
|Caminho composto              |                                                 |                         | Sim         |
|ID do contêiner               |                                                 |                         | Sim         |
|Índice de conversa         |                                                 |                         | Sim         |
|Custodian                  | Sim (responsáveis)                                 |   Sim (responsáveis)       | Sim         |
|Fonte de dados                | Sim (origem)                                    |   Sim (carga de trabalho)          | Sim         |
|Data                       | Sim (Data)                                      |   Sim (data UTC)        | Sim         |
|Caminho composto deduplicado      |                                                 |                         | Sim         |
|Responsáveis pela eliminação de duplicação         |                                                 |                         | Sim         |
|IDs de arquivo com eliminação de duplicação           |                                                 |                         | Sim         |
|Autores de Doc                | Sim (autor) *                                   |    Sim (autor)         | Sim         |
|Comentários doc               | Sim (comentários)                                  |                         | Sim         |
|Empresa doc                |                                                 |                         | Sim         |
|Data de criação do documento           | Sim (criadotime) *                              |    Sim (hora de criação)   | Sim         |
|Data de modificação do documento          | Sim (lastModifiedDate) *                         |                         | Sim         |
|Palavras-chave de Doc               |                                                 |                         | Sim         |
|Doc salvo pela última vez por          |                                                 |                         | Sim         |
|Doc modificado por            |                                                 |                         | Sim         |
|Assunto doc                |                                                 |  Sim (assunto/título)    | Sim         |
|Modelo de documento               |                                                 |                         | Sim         |
|Título do documento                  | Sim (título)                                     |  Sim (título)            | Sim         |
|Versão doc                |                                                 |                         | Sim         |
|Tema dominante             | Sim (dominantTheme)                             |  Sim (tema dominante)   | Sim         |
|Subconjunto duplicado           |                                                 |                         | Sim         |
|Ação de email               |                                                 |                         | Sim         |
|Email Cco                  | Sim (Cco)                                       |                         | Sim         |
|Email CC                   | Sim (CC)                                        |                         | Sim         |
|ID da conversa de email      |                                                 |                         | Sim         |
|Data de recebimento do email        | Sim (recebido)                                  |   Sim (recebido)        | Sim         |
|Data de envio do email            | Sim (enviado)                                      |   Sim (enviado)            | Sim         |
|Email com anexo       |                                                 |                         | Sim         |
|Importância de email           |                                                 |                         | Sim         |
|Cabeçalhos de email da Internet     |                                                 |                         | Sim         |
|Nível de email                |                                                 |                         | Sim         |
|ID da mensagem de email           |                                                 |                         | Sim         |
|Domínios de participante de email  | Sim (participantDomains)                        |                         | Sim         |
|Participantes de email         | Sim (participantes)                              |                         | Sim         |
|Domínios de destinatários de email    | Sim (recipientDomains)                          |                         | Sim         |
|Destinatários de email           | Sim (destinatários)                                |                         | Sim         |
|Segurança de email             |                                                 |                         | Sim         |
|Remetente de email               | Sim (remetente)                                    |   Sim (remetente)          | Sim         |
|Domínio do remetente do email        | Sim (senderDomain)                              |                         | Sim         |
|Confidencialidade de email          |                                                 |                         | Sim         |
|Conjunto de emails                  | Sim (emailSetId)                                |   Sim (EmailSetID)      | Sim         |
|Assunto do email              | Sim (assunto)                                   |   Sim (assunto/título)   | Sim         |
|Thread de email               |                                                 |                         | Sim         |
|Email para                   | Sim (para)                                        |                         | Sim         |
|Código de erro                 | Sim (processingStatus)                          |                         | Sim         |
|Exportar caminho nativo         |                                                 |                         | Sim         |
|Comprimento de texto extraído      |                                                 |                         | Sim         |
|Caminho de texto extraído        |                                                 |                         | Sim         |
|ID da família                  | Sim (FamilyID)                                  |   Sim (FamilyID)        | Sim         |
|Tamanho da família                |                                                 |                         | Sim         |
|Classe de arquivo                 | Sim (fileclass)                                 |   Sim (classe de arquivo)      | Sim         |
|ID de arquivo                    | Sim (fileid)                                    |   Sim (ID)              | Sim         |
|Tem texto                   |                                                 |                         | Sim         |
|Tipo inclusivo             | Sim (inclusivo)                             |   Sim (tipo inclusivo)  | Sim         |
|Data de entrada modificada        |                                                 |                         | Sim         |
|ID do arquivo de entrada              |                                                 |                         | Sim         |
|Caminho de entrada                 |                                                 |                         | Sim         |
|ID de mensagem da Internet        |                                                 |                         | Sim         |
|É representante          | Sim (markAsRepresentative)                      |                         | Sim         |
|Classe de item                 |                                                 |                         | Sim         |
|ID de carregamento                    | Sim (loadid)                                    |                         | Sim         |
|Nome do local              |                                                 |                         | Sim         |
|Marcado como dinâmico            | Sim (markAsPivot)                               |   Sim (marcado como dinâmico) | Sim         |
|Tipo de mensagem               | Sim (messageKind)                               |                         | Sim         |
|Extensão nativa           |                                                 |                         | Sim         |
|Nome do arquivo nativo           |                                                 |    Sim (nome de arquivo)      | Sim         |
|MD5 nativo                 |                                                 |                         | Sim         |
|SHA nativo 256             |                                                 |                         | Sim         |
|Tamanho nativo                | Sim (tamanho)                                      |   Sim (NativeSize)     | Sim         |
|Tipo nativo                | Sim (fileType)                                  |   Sim (tipo de arquivo)       | Sim         |
|ND ET classificar excl anexar     |                                                 |                         | Sim         |
|Ordem de classificação do ND ET incl Attach     |                                                 |                         | Sim         |
|Conjunto de ND                     |                                                 |                         | Sim         |
|Autores do O365               | Sim (autor) *                                   |   Sim (remetente/autor)   | Sim         |
|O365 criado por            |                                                 |                         | Sim         |
|Data do O365 criada          | Sim (criadotime) *                              |                         | Sim         |
|Data de modificação do O365         | Sim (lastModifiedDate) *                         |   Sim (data da última modificação) | Sim      |
|O365 modificado por           |                                                 |                         | Sim         |
|Nó pai                |                                                 |                         | Sim         |
|ID da tabela dinâmica                   | Sim (pivotid)                                   |  Sim (Pivotid)          | Sim         |
|Contagem de destinatários            |                                                 |                         | Sim         |
|Número da linha                 |                                                 |                         | Sim         |
|ID do conjunto                     |                                                 |                         | Sim         |
|Definir ordem inclusive primeiro |                                                 |                         | Sim         |
|Porcentagem de similaridade         |                                                 |                         | Sim         |
|Lista de temas                | Sim (temas)                                | Sim (lista de temas)       | Sim         |
|Word count                 | Sim (wordCount)                                 |                         | Sim         |
|Pontuação de relevância (problema)    | Sim (relevanceScore_issueNum)                   |                         |             |
|Ler percentil (problema)    | Sim (readPercentile_issueNum)                   |                         |             |
|Marca de relevância (problema)      | Sim (relevanceTag_issueNum)                     |                         |             |
|||||

  \*Para esses campos, se houver valores incorporados dentro de um documento, a pesquisa priorizará esses valores; caso contrário, ele tentará exibir o valor do Office 365.
