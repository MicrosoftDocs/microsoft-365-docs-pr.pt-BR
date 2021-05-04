---
title: Insider risk management Explorador de conteúdo
description: Saiba mais sobre o gerenciamento de risco interno Explorador de conteúdo no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: 44a17471f1e2ba92d0099f62b95dec8d0e56a224
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957488"
---
# <a name="insider-risk-management-content-explorer"></a>Insider risk management Explorador de conteúdo

O gerenciamento de risco interno O **Explorador** de conteúdo permite que os usuários atribuídos à função Investigadores de Gerenciamento de Riscos do *Insider* examinem o contexto e os detalhes do conteúdo associado à atividade em alertas. Os dados de caso no Explorador de Conteúdo são atualizados diariamente para incluir novas atividades. Para todos os alertas confirmados para um caso, cópias de arquivos de dados e mensagens são arquivadas como um instantâneo no tempo dos itens, mantendo os arquivos e mensagens originais nas fontes de armazenamento. Se necessário, os arquivos de dados de caso podem ser exportados como um arquivo de documento portátil (PDF) ou no formato de arquivo original.

A cópia de dados e mensagens é transparente para o usuário associado ao alerta e ao proprietário do conteúdo. Para novos casos, geralmente leva cerca de uma hora para o conteúdo ser preenchido no Explorador de conteúdo. Para casos com grandes quantidades de conteúdo, pode levar mais tempo para criar um instantâneo. Se o conteúdo ainda estiver sendo carregado no Explorador de conteúdo, você verá um indicador de progresso que exibe a porcentagem de conclusão.

Em alguns casos, os dados associados a um caso podem não estar disponíveis como um instantâneo para revisão no Explorador de Conteúdo. Essa situação pode ocorrer quando os dados de caso foram excluídos ou movidos ou quando ocorre um erro temporário ao processar dados de caso. Se essa situação ocorrer, selecione **Exibir** arquivos na barra de avisos para exibir os nomes de arquivo, o caminho do arquivo e o motivo da falha para cada arquivo. Se necessário, essas informações podem ser exportadas para um arquivo .csv (valores separados por vírgula).

Se o conteúdo incluir permissões de Gerenciamento de Direitos de Informação, essas permissões serão mantidas para o conteúdo copiado e os usuários atribuídos à função *Insider Risk Management Investigators* precisarão dessas permissões e direitos se precisarem abrir e exibir os arquivos. Cada arquivo e mensagem são atribuídos automaticamente a uma ID de arquivo exclusiva no caso de gerenciamento de risco interno para fins de gerenciamento. Os documentos associados às atividades de indicador de dispositivo não são incluídos no Explorador de conteúdo.

>[!Note]
>O explorador de conteúdo inclui atividades relacionadas Microsoft Office arquivos. Atividades no nível do site, como quando um site SharePoint é excluído ou se as permissões de site são alteradas, não são incluídas no Explorador de conteúdo.

## <a name="column-options"></a>Opções de coluna

Para facilitar que os analistas de risco e os investigadores revisem dados e mensagens capturados e revisem o contexto para o caso, várias ferramentas de filtragem e classificação são incluídas no explorador de conteúdo. Para classificação básica, as  colunas de classe **Data** e Arquivo suportam a classificação usando os títulos de coluna no painel de filas de conteúdo. Outras colunas de fila estão disponíveis para adicionar ao modo de exibição para fornecer pivôs diferentes nos arquivos e mensagens.

Para adicionar ou remover títulos de coluna para a fila de conteúdo, use o **controle Editar colunas** e selecione entre as seguintes opções de coluna. Essas colunas mapeiam para as condições comuns, de email e de propriedade de documento suportadas no explorador de conteúdo e listadas posteriormente neste artigo.

| **Opção Column** | **Descrição** |
|:------------------|:----------------|
| **Author** | O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário criar um documento e enviá-lo para outra pessoa que o carrega para SharePoint, o documento ainda manterá o autor original. |
| **Bcc** | Disponível para mensagens de email, os usuários no campo mensagem Cc. |
| **Cc** | Disponível para mensagens de email, os usuários no campo mensagem Cc. |
| **Caminho composto** | Caminho acessível para humanos que descreve a origem do item. |
| **ID da conversa** | ID da conversa da mensagem. |
| **Índice de conversa** | Índice de conversa da mensagem. |
| **Tempo criado** | A hora em que o arquivo ou mensagem de email foi criado. |
| **Data (UTC)** | Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez. A data está em Tempo Universal Coordenado (UTC).|
| **Tema dominante** | Tema dominante conforme calculado para análise. |
| **ID do conjunto de emails** | ID do grupo para todas as mensagens no mesmo conjunto de emails. |
| **ID da família** | Grupos de ID da família reúnem todos os itens; para email, esta coluna inclui a mensagem e todos os anexos; para documentos, esta coluna inclui o documento e todos os itens incorporados. |
| **Classe File** | Para conteúdo de SharePoint e OneDrive: **Documento;** para conteúdo de Exchange: **Email** ou **Anexo.** |
| **ID do arquivo** | Identificador de documento exclusivo dentro do caso. |
| **Ícone de tipo de arquivo** | A extensão de um arquivo; por exemplo, docx, um, pptx ou xlsx. Este campo é a mesma propriedade que a propriedade de site FileExtension. |
| **ID** | O identificador GUID do arquivo. |
| **ID Imutável** | Id imutável conforme armazenado em Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análise: **0** - não inclusivo; **1** - inclusive; **2** - inclusive menos; **3** - cópia inclusiva. |
| **Última modificação** | A data em que um documento foi alterado pela última vez. |
| **Marcado como representativo** | Um documento de cada conjunto de duplicatas exatas é marcado como representantes. |
| **Tipo de mensagem** | O tipo de mensagem de email a ser pesquisada. Valores possíveis: contatos, documentos, email, dados externos, faxes, im, diários, reuniões, microsoft teams (retorna itens de chats, reuniões e chamadas no Microsoft Teams), anotações, postagens, RSS feeds, tarefas, caixa postal |
| **Participantes** | Lista de todos os participantes de uma mensagem; por exemplo, Remetente, Para, Cc, Cc. |
| **ID dinâmica** | A ID de um pivô. |
| **Received** | A data em que uma mensagem de email foi recebida pelo destinatário. Esse campo é a mesma propriedade que a propriedade Received email. |
| **Destinatários** | Todos os campos de destinatário em uma mensagem de email. Esses campos são To, Cc e Cc. |
| **ID representativa** | Identificador numérico de cada conjunto de duplicatas exatas. |
| **Sender** | O remetente de uma mensagem de email. |
| **Remetente/Autor** | Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo autor de documentos do Office. Você pode digitar mais de um nome, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |
| **Tipos de informações confidenciais** | Os tipos de informações confidenciais identificados no conteúdo. |
| **Rótulos de confidencialidade** | Os rótulos de sensibilidade aplicados ao conteúdo. |
| **Sent** | A data em que uma mensagem de email foi enviada pelo remetente. Esse campo é a mesma propriedade que a propriedade Email Enviado. |
| **Tamanho** | Para emails e documentos, o tamanho do item (em bytes). |
| **Assunto** | O texto na linha de assunto de uma mensagem de email. |
| **Assunto/Título** | Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. Conforme explicado anteriormente, a propriedade Title é metadados especificados Microsoft Office documentos. Você pode digitar o nome de mais de um assunto/título, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |
| **Lista de temas** | Lista de temas conforme calculado para análise. |
| **Title** | O título do documento. A propriedade Title consiste em metadados que são especificados em documentos do Office. É diferente do nome do arquivo do documento. |
| **To** | O destinatário de uma mensagem de email no campo Para. |

## <a name="filtering"></a>Filtragem

Você pode usar um ou mais filtros para restringir o escopo de uma pesquisa e retornar um conjunto mais refinado de resultados. Para definir um filtro, selecione **Filtros** na parte superior da fila de conteúdo. Muitos filtros incluem opções de filtragem adicionais para ajudar a restringir os resultados retornados pelo filtro. Por exemplo, o *filtro Data* inclui controles para configurar uma data *de* início e data *de término* para o **filtro Data.** Selecione um ou mais itens de filtro das seguintes categorias:

### <a name="common-filters"></a>Filtros comuns

| **Filter** | **Descrição** |
|:---------------------|:----------------|
| **Data (UTC)** | Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez. |
| **Remetente/Autor** | Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo *Autor* Office documentos. Você pode digitar mais de um nome, separado por vírgulas. |
| **Fonte** | O local do documento em sua organização. Por exemplo, um local SharePoint site específico. |
| **Assunto/Título** | Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. A propriedade Title em documentos é metadados especificados em Microsoft Office documentos. Você pode digitar o nome de mais de um assunto/título, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador OR. |

### <a name="email-filters"></a>Filtros de email

| **Filter** | **Descrição** |
|:---------------------|:----------------|
| **Bcc** | O campo Cc de uma mensagem de email. |
| **Cc** | O campo Cc de uma mensagem de email. |
| **Tem anexo** | Indica se uma mensagem tem um anexo. Os valores são listados como **true** ou **false.** |
| **É anexo de email** | Se o documento for um anexo, o valor será listado como **Sim**. |
| **É um documento incorporado** | Se o documento estiver inserido na mensagem de email, o valor será listado como **Sim**. |
| **É anexo em linha** | Se o documento for um anexo em linha na mensagem de email, o valor será listado como **Sim**. |
| **Participantes** | Todos os campos de pessoas em uma mensagem de email. Esses campos são From, To, Cc e Cc. |
| **Received** | A data em que uma mensagem de email foi recebida pelo destinatário. |
| **Domínios de destinatário** | Lista de todos os domínios de destinatários de uma mensagem. |
| **Destinatários** | Os destinatários da mensagem de email. |
| **Sender** | Campo Remetente (De) para tipos de mensagem.  Format é **DisplayName \<SmtpAddress>**. |
| **Domínio do remetente** | Domínio do remetente. |
| **To** | O campo Para de uma mensagem de email. |
| **Exclusivo no conjunto de emails** | False se houver uma duplicata do anexo em seu conjunto de emails. |

## <a name="document-filters"></a>Filtros de documento

| **Filters** | **Descrição** |
|:---------------------|:----------------|
| **Rótulos de conformidade** | Rótulos de conformidade aplicados Office 365. |
| **Hora de criação (UTC)** | A data e a hora em que o arquivo ou mensagem de email foi criado. A data e a hora estão em Tempo Universal Coordenado (UTC). |
| **Data da última modificação (UTC)** | A data em que um documento foi alterado pela última vez. A data e a hora estão em Tempo Universal Coordenado (UTC). |
| **Extensão do arquivo** | O tipo de extensão do arquivo. |
| **Eventos de atividade do usuário** | Atividade para itens relacionados a atividades específicas do usuário em um caso.  Por exemplo, quando você seleciona um link para "Explorar Conteúdo" para uma atividade na página Atividade do Usuário de um caso, esse filtro é usado para exibir itens relacionados a essa atividade.  |
| **Produto de trabalho** | O tipo de produto de trabalho do documento. Por exemplo, anotações ou marcas no documento. |
