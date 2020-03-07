---
title: Exportar campos de relatório na descoberta eletrônica avançada do Office 365
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: Descreve todos os campos incluídos nos relatórios de exportação para descoberta eletrônica avançada.
ms.openlocfilehash: 8c932dac9218e2020bfcd57d21483728325e488f
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558202"
---
# <a name="export-report-fields-in-advanced-ediscovery-classic"></a>Exportar campos de relatório na descoberta eletrônica avançada (clássico)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Este tópico descreve os campos de relatório de exportação de descoberta eletrônica avançada para o padrão e todos os modelos.
  
## <a name="export-report-fields"></a>Campos do relatório de exportação

A tabela a seguir lista os campos de cada modelo de exportação.
  
|**Nome do campo de exportação**|**Group**|**Descrição**|**Disponível no modelo padrão**|**Disponível em todos os modelos**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |Geral  <br/> |Número da linha.  <br/> |Sim  <br/> |Sim  <br/> |
|File_ID  <br/> |Geral  <br/> |ID de arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|File_class  <br/> |Processamento   <br/> |Classe de arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|Family_ID  <br/> |Processamento   <br/> |Identificador numérico usado para agrupar arquivos (geralmente a instância de email e seus anexos).  <br/> |Sim  <br/> |Sim  <br/> |
|For_review  <br/> |Processamento   <br/> |Sinalizador para indicar que o campo será incluído na exportação para revisão.  <br/> |Sim  <br/> |Sim  <br/> |
|Native_file_name  <br/> |Processamento   <br/> |Nome do arquivo nativo, sem fazer referência à pasta e à extensão.  <br/> |Sim  <br/> |Sim  <br/> |
|Responsáveis  <br/> |Geral  <br/> |Os responsáveis pelo arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|Set_ID  <br/> |Análise  <br/> |ID "ND set" ou "conjunto de emails".  <br/> |Sim  <br/> |Sim  <br/> |
|Inclusive_type  <br/> |Email  <br/> |Indica se o arquivo é inclusivo, de acordo com os seguintes valores: 0-não inclusivo, 1-inclusive, 2, incluindo menos, 3-inclusive a cópia.  <br/> |Sim  <br/> |Sim  <br/> |
|Marked_as_pivot  <br/> |Duplicatas próximas  <br/> |Indica se o arquivo é uma tabela dinâmica.  <br/> |Sim  <br/> |Sim  <br/> |
|Similarity_percent  <br/> |Duplicatas próximas  <br/> |Porcentagem de similaridade em relação à tabela dinâmica.  <br/> |Sim  <br/> |Sim  <br/> |
|Duplicate_subset  <br/> |Duplicatas próximas  <br/> |Identificador exclusivo do subconjunto duplicado. Indica se o arquivo tem duplicatas de texto exatas.  <br/> |Sim  <br/> |Sim  <br/> |
|Data  <br/> |Geral  <br/> |Data do arquivo (depende do tipo de arquivo-email: data de envio; documento: data de modificação).  <br/> |Sim  <br/> |Sim  <br/> |
|Dominant_theme  <br/> |Análise  <br/> |Tema principal do arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|Themes_list  <br/> |Temas  <br/> |Lista de nomes de temas.  <br/> |Sim  <br/> |Sim  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Identificador numérico exclusivo de um conjunto de Nearduplicate.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_set  <br/> |Email  <br/> |Identificador numérico exclusivo de um conjunto de emails.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_thread  <br/> |Email  <br/> |Descreve a posição do email dentro do conjunto de emails que consiste em todas as IDs de nó da raiz para o email atual, separadas por pontos.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_subject  <br/> |Email  <br/> |Assunto do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_date_sent  <br/> |Email  <br/> |Data de envio do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_participants  <br/> |Email  <br/> |Endereços de email de todos os participantes de um thread de email, incluindo links ausentes.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_participant_domains  <br/> |Email  <br/> |Domínios de todos os participantes em um thread de email, incluindo o link ausente.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_sender  <br/> |Email  <br/> |Nome e/ou endereço do remetente do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_sender_domain  <br/> |Email  <br/> |Domínio do remetente do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_to  <br/> |Email  <br/> |Para o destinatário do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_cc  <br/> |Email  <br/> |Destinatário CC do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_bcc  <br/> |Email  <br/> |Destinatário Cco do email.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_recipient_domains  <br/> |Email  <br/> |Domínios de destinatários de email (para, CC e Cco).  <br/> |Sim  <br/> |Sim  <br/> |
|Email_date_received  <br/> |Email  <br/> |Data em que o email foi recebido.  <br/> |Sim  <br/> |Sim  <br/> |
|Email_action  <br/> |Email  <br/> |Valores: de acordo com o assunto do email: "encaminhar" (para "FW:"), "responder" (para "RE:") ou "outros" (outro texto do assunto).  <br/> |Sim  <br/> |Sim  <br/> |
|Meeting_Start_Date/time  <br/> ||A data e a hora em que um item de reunião foi iniciado.  <br/> |Sim  <br/> |Sim  <br/> |
|Meeting_End_Date/time  <br/> ||A data e a hora em que um item de reunião terminou.  <br/> |Sim  <br/> |Sim  <br/> |
|File_relevance_score  <br/> |Relevância  <br/> |Pontuação de relevância (0-100). Por problema.  <br/> |Sim  <br/> |Sim  <br/> |
|Family_relevance_score  <br/> |Relevância  <br/> |Pontuação de relevância da família máx (0-100). Por problema.  <br/> |Sim  <br/> |Sim  <br/> |
|Relevance_tag  <br/> |Relevância  <br/> |Marcação do arquivo, se o arquivo foi marcado manualmente em relevância. Por problema.  <br/> |Sim  <br/> |Sim  <br/> |
|Relevance_load_group  <br/> |Relevância  <br/> |Grupo de carga de relevância do arquivo especificado, com um campo por problema.  <br/> |Sim  <br/> |Sim  <br/> |
|Normalized_relevance_score  <br/> |Relevância  <br/> |Pontuação de relevância normalizada (0-100), que é comparável entre problemas e cargas.  <br/> |Sim  <br/> |Sim  <br/> |
|Marked_as_seed  <br/> |Relevância  <br/> |Marcação do arquivo, se ele tiver sido definido como um arquivo semente em relevância por problema/categoria.  <br/> |Sim  <br/> |Sim  <br/> |
|Marcadas Marked_as_pre  <br/> |Relevância  <br/> |Marcação do arquivo, se ele tiver sido definido como previamente marcado em relevância por problema/categoria.  <br/> |Sim  <br/> |Sim  <br/> |
|Relevance_status_description  <br/> |Relevância  <br/> |Descrição do status de relevância.  <br/> |Sim  <br/> |Sim  <br/> |
|Comentário  <br/> |Geral  <br/> |Comentário inserido pelo usuário.  <br/> |Sim  <br/> |Sim  <br/> |
|Export_input_path  <br/> |Processamento   <br/> |Exportar caminho de entrada.  <br/> |Sim  <br/> |Sim  <br/> |
|Pivot_ID  <br/> |Duplicatas próximas  <br/> |ID da tabela dinâmica do arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|Family_size  <br/> |Processamento   <br/> |Número de arquivos em uma família.  <br/> |Sim  <br/> |Sim  <br/> |
|Native_type  <br/> |Processamento   <br/> |Tipo de arquivo nativo. Por exemplo, planilha ou apresentação.  <br/> |Sim  <br/> |Sim  <br/> |
|Native_MD5  <br/> |Processamento   <br/> |Valor de hash MD5 do arquivo nativo.  <br/> |Sim  <br/> |Sim  <br/> |
|Native_size  <br/> |Processamento   <br/> |Tamanho do arquivo nativo.  <br/> |Sim  <br/> |Sim  <br/> |
|Native_extension  <br/> |Processamento   <br/> |Extensão de arquivo nativo.  <br/> |Sim  <br/> |Sim  <br/> |
|Doc_date_modified  <br/> |Propriedades do documento  <br/> |O arquivo nativo da data foi modificado, obtido dos metadados do arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|Doc_date_created  <br/> |Propriedades do documento  <br/> |O arquivo de data nativo foi criado, obtido dos metadados do arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|Doc_modified_by  <br/> |Propriedades do documento  <br/> |Usuário que modificou o arquivo nativo, obtido dos metadados do arquivo.  <br/> |Sim  <br/> |Sim  <br/> |
|O365_date_modified  <br/> |Propriedades do documento  <br/> |O arquivo nativo da data foi modificado, obtido dos campos do SharePoint ou do Exchange.  <br/> |Sim  <br/> |Sim  <br/> |
|O365_date_created  <br/> |Propriedades do documento  <br/> |Data o arquivo nativo foi criado, obtido de campos do SharePoint ou do Exchange.  <br/> |Sim  <br/> |Sim  <br/> |
|O365_modified_by  <br/> |Propriedades do documento  <br/> |Usuário que modificou o arquivo nativo por último, obtido de campos do SharePoint ou do Exchange.  <br/> |Sim  <br/> |Sim  <br/> |
|Compound_path  <br/> |Processamento   <br/> |Caminho de arquivo nativo incluindo sua fonte composta.  <br/> |Sim  <br/> |Sim  <br/> |
|Input_path  <br/> |Processamento   <br/> |Caminho do arquivo de entrada.  <br/> |Sim  <br/> |Sim  <br/> |
|Input_date_modified  <br/> |Processamento   <br/> |O arquivo de entrada de data foi modificado pela última vez.  <br/> |Sim  <br/> |Sim  <br/> |
|ND_ET_sort_excl_attach  <br/> |Análise  <br/> |Concatenação de conjunto de emails e ND definidos para revisão. ' D' é adicionado como um prefixo para conjuntos ND, e ' E ' é adicionado a email ssets.  <br/> |Sim  <br/> |Sim  <br/> |
|ND_ET_sort_incl_attach  <br/> |Análise  <br/> |A concatenação do conjunto de emails e da ND definida para revisar é adicionada como um prefixo para conjuntos de ND, e ' E ' é adicionado aos conjuntos de emails. Além disso, cada email dentro de um Email_set é seguido pelos seus anexos apropriados.  <br/> |Sim  <br/> |Sim  <br/> |
|Deduped_custodians  <br/> |Geral  <br/> |Responsáveis por arquivos com eliminação de duplicação  <br/> |Sim  <br/> |Sim  <br/> |
|Deduped_file_IDs  <br/> |Geral  <br/> |IDs de arquivos com eliminação da duplicação  <br/> |Sim  <br/> |Sim  <br/> |
|Deduped_paths  <br/> |Geral  <br/> |Caminhos dos arquivos com eliminação da duplicação  <br/> |Sim  <br/> |Sim  <br/> |
|File_key  <br/> |Geral  <br/> |Identificador interno para uso futuro.  <br/> |Sim  <br/> |Sim  <br/> |
|Export_native_path  <br/> |Processamento   <br/> |Caminho do arquivo nativo no pacote de exportação.  <br/> |Sim  <br/> |Sim  <br/> |
|Extracted_text_path  <br/> |Processamento   <br/> |Caminho do arquivo extraído.  <br/> |Sim  <br/> |Sim  <br/> |
|Process_batch  <br/> |Processamento   <br/> |Identificador de lote para o lote de importação.  <br/> |Sim  <br/> |Sim  <br/> |
|Process_status_ID  <br/> |Processamento   <br/> |Identificador que representa o status do estágio do processo.  <br/> |Sim  <br/> |Sim  <br/> |
|Process_status_description  <br/> |Processamento   <br/> |Descrição do status do estágio de processo: Descrição bem-sucedida ou erro.  <br/> |Sim  <br/> |Sim  <br/> |
|Export_status_ID  <br/> |Processamento   <br/> |ID do status de exportação.  <br/> |Sim  <br/> |Sim  <br/> |
|Export_status_description  <br/> |Processamento   <br/> |Descrição do status de exportação; Descrição bem-sucedida ou de erro.  <br/> |Sim  <br/> |Sim  <br/> |
|Read_percent  <br/> |Relevância  <br/> |Leia% (0-100). Por problema.  <br/> |Sim  <br/> |Sim  <br/> |
|Doc_author  <br/> |Propriedades do documento  <br/> |Propriedades do documento: autor.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_comments  <br/> |Propriedades do documento  <br/> |Propriedades do documento: comentários.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_keywords  <br/> |Propriedades do documento  <br/> |Propriedades do documento: palavras-chave.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_last_saved_by  <br/> |Propriedades do documento  <br/> |Propriedades do documento: última gravação por.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_revision  <br/> |Propriedades do documento  <br/> |Propriedades do documento: número de revisão.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_subject  <br/> |Propriedades do documento  <br/> |Propriedades do documento: assunto.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_template  <br/> |Propriedades do documento  <br/> |Propriedades do documento: template.  <br/> |Não  <br/> |Sim  <br/> |
|Doc_title  <br/> |Propriedades do documento  <br/> |Propriedades do documento: título.  <br/> |Não  <br/> |Sim  <br/> |
|Email_has_attachment  <br/> |Email  <br/> |Indica se o email tem um ou mais anexos.  <br/> |Não  <br/> |Sim  <br/> |
|Email_importance  <br/> |Email  <br/> |Propriedade email-importância.  <br/> |Não  <br/> |Sim  <br/> |
|Email_level  <br/> |Email  <br/> |Indica o nível de email no thread de email. Para anexos, o valor do email anexado.  <br/> |Não  <br/> |Sim  <br/> |
|Email_recipients  <br/> |Email  <br/> |Destinatários de email nome e/ou endereços (para, CC e Cco).  <br/> |Não  <br/> |Sim  <br/> |
|Email_security  <br/> |Email  <br/> |Propriedade de segurança de email.  <br/> |Não  <br/> |Sim  <br/> |
|Email_sensitivity  <br/> |Email  <br/> |Propriedade de confidencialidade de email.  <br/> |Não  <br/> |Sim  <br/> |
|Export_batch  <br/> |Processamento   <br/> |Nome do lote de exportação do último arquivo.  <br/> |Não  <br/> |Sim  <br/> |
|Export_session  <br/> |Processamento   <br/> |ID da sessão de exportação do último arquivo, incluindo a data.  <br/> |Não  <br/> |Sim  <br/> |
|Extracted_text_length  <br/> |Processamento   <br/> |Comprimento de caracteres do arquivo de texto extraído.  <br/> |Não  <br/> |Sim  <br/> |
|Family_duplicate_set  <br/> |Processamento   <br/> |Identificador numérico para famílias que são duplicatas de texto exatas umas das outras (respectivamente-todos os membros das famílias são duplicatas exatas).  <br/> |Não  <br/> |Sim  <br/> |
|Has_Text  <br/> |Processamento   <br/> |Indica se há texto no arquivo: 0-não; 1-Sim.  <br/> |Não  <br/> |Sim  <br/> |
|Input_file_ID  <br/> |Processamento   <br/> |ID do arquivo de entrada do qual o arquivo foi extraído.  <br/> |Não  <br/> |Sim  <br/> |
|Native_SHA_256  <br/> |Processamento   <br/> |SHA-256 valor de hash do arquivo nativo.  <br/> |Não  <br/> |Sim  <br/> |
|O365_authors  <br/> |Propriedades do documento  <br/> |Usuários que modificaram o arquivo nativo, obtidos de campos do SharePoint ou do Exchange.  <br/> |Não  <br/> |Sim  <br/> |
|O365_created_by  <br/> |Propriedades do documento  <br/> |Usuário que criou o arquivo nativo, obtido de campos do SharePoint ou do Exchange.  <br/> |Não  <br/> |Sim  <br/> |
|Parent_node  <br/> |Email  <br/> |Relaciona um nó em um thread de email ao nó pai mais próximo que não está em um link ausente.  <br/> |Não  <br/> |Sim  <br/> |
|Set_order_inclusives_first  <br/> |Email  <br/> |Emails e anexos: ordem cronológica do contador (inclusive primeiro). Documents: pivô primeiro e o restante por Pontuação de similaridade, decrescente.  <br/> |Não  <br/> |Sim  <br/> |
|Tagged_By  <br/> |Relevância  <br/> |Usuário que marcou o arquivo em relevância para o problema específico.  <br/> |Não  <br/> |Sim  <br/> |
|Word_count  <br/> |Análise  <br/> |Número de palavras no documento.  <br/> |Não  <br/> |Sim  <br/> |
|
   
## <a name="related-topics"></a>Tópicos Relacionados

[Descoberta eletrônica avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Exportar dados de caso com a descoberta eletrônica avançada](export-case-data-in-advanced-ediscovery.md)
  
[Exportação de resultados](export-results-in-advanced-ediscovery.md)
  
[Exibindo histórico de lotes e exportando resultados passados](view-batch-history-and-export-past-results.md)
  

