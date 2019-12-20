---
title: Campos de metadados de documentos na descoberta eletrônica avançada
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
ms.openlocfilehash: 39ce4518e12b4446b339cbf7341a354bf5bd8876
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805964"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadados de documentos na descoberta eletrônica avançada

A tabela a seguir lista os campos de metadados para documentos em uma revisão definida em um caso na descoberta eletrônica avançada. A tabela fornece as seguintes informações:

- O nome do campo de metadados (na coluna **nome do campo** ).

- O nome da propriedade que você pode pesquisar ao executar uma consulta de [conjunto de revisão](review-set-search.md) (na coluna **nome do campo pesquisável** ). Uma célula em branco significa que você não pode pesquisar o campo em uma consulta de conjunto de revisão.

- O nome do campo de metadados que inclui quando os documentos são exportados (na coluna **nome do campo exportado** ).  Uma célula em branco significa que o campo meta data não está incluído nos metadados exportados.

- O nome do campo de metadados que é exibido ao exibir os metadados de arquivo de um documento selecionado em um conjunto de revisão (na coluna **exibir nome do campo** ). Uma célula em branco significa que o campo meta dados não está incluído ao exibir os metadados de arquivo de um documento.

- Uma descrição do campo meta dados (na **coluna Descrição**).

|Nome do campo|Nome do campo pesquisável|Nome do campo exportado|Nome do campo de exibição|Descrição|
|:-|:-|:-|:-|:-|
| ID de conteúdo do anexo | AttachmentContentId |  | ID de conteúdo do anexo | ID do conteúdo do anexo do item. |
| Nomes de anexos | Attachmentnames | Attachment_Names | Nomes de anexos | Lista de nomes de anexos. |
| Pontuação de privilégio de cliente advogado | AttorneyClientPrivilegeScore |  | Pontuação de privilégio de cliente advogado | Advogado-Pontuação de conteúdo do modelo de privilégio do cliente. |
| Autor | Autor | Doc_authors | Autor | Autor dos metadados do documento. |
| BCC | Cco | Email_bcc | BCC | Campo Cco para tipos de mensagem.  Format é **DisplayName \<SmtpAddress>**. |
| CC | Cc | Email_cc | CC | Campo CC para tipos de mensagem.  Format é **DisplayName \<SmtpAddress>**. |
| Rótulos de conformidade | ComplianceLabels | Compliance_labels | Rótulos de conformidade |[Rótulos de retenção](labels.md) aplicados ao conteúdo no Office 365. |
| Caminho composto | CompoundPath | Compound_path | Caminho composto | Caminho legível humana que descreve a fonte do item. |
| Conteúdo | Conteúdo |  |  | Texto extraído do item. |
| Corpo da conversa | Corpo da conversa |  | Corpo da conversa | Corpo da conversa do item. |
| Tópico de conversa | Tópico de conversa |  | Tópico de conversa | Tópico de conversa do item. |
| ID da conversa | ConversationId | Conversation_ID | ID da conversa | ID da conversa da mensagem. |
| Índice de conversa |  | Conversation_index | Índice de conversa | Índice de conversa da mensagem. |
| Hora do PDF da conversa | ConversationPdfTime |  | Hora do PDF da conversa | Data em que a versão do PDF da conversa foi criada. |
| Tempo de gravação da redação da conversa | ConversationRedactionBurnTime |  | Tempo de gravação da redação da conversa | Data em que a versão do PDF da conversa foi criada para o chat. |
| Data de criação do documento | Createdtime | Doc_date_created | Data de criação do documento | Criar data a partir de metadados de documento. |
| Custodian | Custodian | Custodian | Custodian | Nome dos responsáveis com os quais o item foi associado. |
| Data | Data | Data | Data | Data é um campo computado que depende do tipo de arquivo.<br />**Email**: data de envio<br />**Anexos de email**: data da última modificação do documento, se não estiver disponível, a data de envio do pai<br />**Documentos incorporados**: data da última modificação do documento, se não estiver disponível, a data da última modificação do pai.<br />**Documentos do SPO (inclui anexos modernos)**: data da última modificação do SharePoint, se não estiver disponível, a data da última modificação dos documentos<br />**Documentos que não são do Office**: data da última modificação<br />**Reuniões**: data de início da reunião<br />**Caixa postal**: data de envio<br />**Im**: data de envio. |
| Outros caminhos | Dedupedcompoundpath | Deduped_compound_path | Outros caminhos | Lista de caminhos compostos de documentos que são duplicatas exatas (email: com base no conteúdo, documentos: com base no hash). |
| Outros responsáveis | DedupedCustodians | Deduped_custodians | Outros responsáveis | Lista de responsáveis por documentos que são duplicatas exatas (por email: com base no conteúdo; para documentos: com base no hash). |
| Outras IDs de arquivo | DedupedFileIds | Deduped_file_IDs | Outras IDs de arquivo | Lista de IDs de arquivo de documentos que são duplicatas exatas (para email: com base no conteúdo; para documentos: com base no hash). |
| Comentários do documento | DocComments | Doc_comments | Comentários do documento | Comentários dos metadados do documento. |
| Empresa de documentos |  | Doc_company | Empresa de documentos | Empresa dos metadados do documento. |
| DocIndex |  |  |  | O índice da família. -1 ou 0 significa que é a raiz. |
| Palavras-chave do documento |  | Doc_keywords | Palavras-chave do documento | Palavras-chave dos metadados do documento. |
| Documento modificado por |  | Doc_modified_by | Documento modificado por | Data da última modificação por dos metadados do documento. |
| Revisão do documento |  | Doc_revision | Revisão do documento | Revisão dos metadados do documento. |
| Assunto do documento |  | Doc_subject | Assunto do documento | Assunto dos metadados do documento. |
| Modelo de documento |  | Doc_template | Modelo de documento | Modelo dos metadados do documento. |
| Tema dominante | DominantTheme | Dominant_theme | Tema dominante | Tema dominante conforme calculado para a análise. |
| Subconjunto duplicado |  | Duplicate_subset | Subconjunto duplicado | ID de grupo para duplicatas exatas. |
| Emailaction |  | Email_action |  | Nenhum, responder, encaminhar com base na linha de assunto de uma mensagem. |
| Confirmação de entrega de email |  | Email_delivery_receipt | Confirmação de entrega de email | Endereço de email fornecido em cabeçalhos da Internet para confirmação de entrega. |
| Importance | EmailImportance | Email_importance | Importance | Importância da mensagem: **0**: baixa; **1**: normal; **2**: alta |
| EmailLevel |  | Email_level |  | Indica o nível de uma mensagem dentro do thread de email ao qual ela pertence; os anexos herdam o valor da mensagem pai. |
| ID da mensagem de email |  | Email_message_ID | ID da mensagem de email | ID de mensagem da Internet da mensagem. |
| EmailReadReceipt |  | Email_read_receipt |  | Endereço de email fornecido em cabeçalhos da Internet para confirmação de leitura. |
| Segurança de email | EmailSecurity | Email_security | Segurança de email | Configuração de segurança da mensagem: **0**: nenhum; **1**: assinado; **2**: criptografado; **3**: criptografado e assinado. |
| Confidencialidade de email | EmailSensitivity | email_sensitivity | Confidencialidade de email | Configuração de sensibilidade da mensagem: **0**: nenhum; **1**: pessoal; **2**: particular; **3**: CompanyConfidential. |
| Conjunto de emails | Emailset | Email_set | Conjunto de emails | ID de grupo para todas as mensagens no mesmo conjunto de email. |
| EmailThread |  | Email_thread |  | Posição da mensagem dentro do conjunto de emails; consiste em todas as IDs de nó da raiz para a mensagem atual, separadas por período. |
| Tipo de conteúdo extraído |  | Extracted_content_type | Tipo de conteúdo extraído | Tipo de conteúdo extraído, na forma de tipo MIME; por exemplo, image/jpeg. |
| ExtractedTextLength |  | Extracted_text_length |  | Número de caracteres no texto extraído. |
| Pontos de relevância da família-problema de caso 1 |  | Family_relevance_score_case_issue_1 |  | Pontuação de relevância da família caso o problema 1 de relevância. |
| FamilyDuplicateSet |  | Family_duplicate_set |  | Identificador numérico para famílias que são duplicatas exatas entre si (mesmo conteúdo e todos os mesmos anexos). |
| ID da família | FamilyId | Family_ID | ID da família | Grupos de ID de família juntos todos os itens; para email, isso inclui a mensagem e todos os anexos; para documentos, isso inclui o documento e todos os itens incorporados. |
| Tamanho da família |  | Family_size | Tamanho da família | Número de documentos na família. |
| Nota de relevância de arquivo problema de caso 1 |  | File_relevance_score_case_issue_1 |  | Pontuação de relevância de arquivo caso problema 1 de relevância. |
| Classe de arquivo | Fileclass | File_class | Classe de arquivo | Para conteúdo do SharePoint e do OneDrive: **Document**; para o conteúdo do Exchange: * * email ou **anexo**. |
| ID de arquivo | FileId | File_ID | ID de arquivo | Identificador de documento exclusivo no caso.|
| Data do sistema de arquivos criada |  | File_system_date_created | Data do sistema de arquivos criada | Data de criação do sistema de arquivos (só se aplica a dados não-Office 365). |
| Data do sistema de arquivos modificada |  | File_system_date_modified | Data do sistema de arquivos modificada | Data de modificação do sistema de arquivos (só se aplica a dados não-Office 365). |
| Tipo de arquivo | FileType |  | Tipo de arquivo | Tipo de arquivo do item, com base na extensão de arquivo. |
| Tem anexo | HasAttachment | Email_has_attachment | Tem anexo | Indica se a mensagem tem ou não anexos. |
| O advogado é | HasAttorney |  | O advogado é | True quando pelo menos um dos participantes é encontrado na lista advogado; caso contrário, o valor será false. |
| HasText |  | Has_text |  | Indica se o item tem ou não texto, valores possíveis são true e false. |
| ID Imutável | Imutávelid | Immutable_ID | ID Imutável | ID imutável, conforme armazenado no Office 365. |
| Tipo inclusivo | Inclusivtype | Inclusive_type | Tipo inclusivo | Tipo inclusivo calculado para análise: **0** -não inclusivo; **1** -inclusive; **2** – menos inclusivo; cópia **3** incluindo. |
| Em responder à ID |  | In_reply_to_ID | Em responder à ID | Em resposta à ID da mensagem. |
| É representante | Isrepresentativo | Is_representative | É representante | Um documento em cada conjunto de duplicatas exatas é marcado como representante. |
| Classe de item | ItemClass | Item_class | Classe de item | Classe de item fornecida pelo Exchange Server; por exemplo, **IPM. Observação** |
| Last modified date | LastModifiedDate | Doc_date_modified | Last modified date | Data da última modificação dos metadados do documento. |
| ID de carregamento | Loadid | Load_ID | ID de carregamento | ID de carregamento, no qual o item foi carregado em um conjunto de revisão. |
| Locais | Locais | Locais | Locais | Cadeia de caracteres que indica o tipo de local de onde os documentos foram originados;<br />Dados importados não-O365 ><br />Equipes > Teams<br />EXO-> Exchange<br />SPO-> SharePoint<br />OneDrive for Business-> OneDrive |
| Nome do local | LocationName | Location_name | Nome do local | Cadeia de caracteres que identifica a origem do item.  Para o Exchange, esse será o endereço SMTP da caixa de correio.  Para o SharePoint e o OneDrive, a URL para o conjunto de sites. |
| Marcado como representante | MarkAsRepresentative |  | Marcado como representante | Um documento de cada conjunto de duplicatas exatas é marcado como representante. |
| Marcado como o problema de caso anterior à marca 1 |  | Marked_as_pre_tagged_Case_issue_1 |  | Marcado como problema de caso de marca 1 de relevância. |
| Marcado como problema de caso de propagação 1 |  | Marked_as_seed_Case_issue_1 |  | Marcado como o problema de caso de propagação 1 de relevância. |
| Data de término da reunião | MeetingEndDate | Meeting_end_date | Data de término da reunião | Data de término da reunião para reuniões. |
| Data de início da reunião | MeetingStartDate | Meeting_start_date | Data de início da reunião | Data de início da reunião para reuniões. |
| Tipo de mensagem | MessageKind | Message_kind | Tipo de mensagem | O tipo de mensagem a ser pesquisada.<br />Valores possíveis: <br />contacts <br />docs <br />email <br />externaldata <br />fax <br />respectiva <br />diários <br />treinamento <br />microsoftteams (retorna itens de chats, reuniões e chamadas no Microsoft Teams) <br />notes <br />postagens <br />rssfeeds <br />tarefas <br />postal |
| Extensão nativa | NativeExtension | Native_extension | Extensão nativa | Extensão nativa do item. |
| Nome do arquivo nativo | NativeFileName | Native_file_name | Nome do arquivo nativo | Nome do arquivo nativo do item. |
| NativeMD5 |  | Native_MD5 |  | Hash MD5 do fluxo de arquivos. |
| Classificação ND/ET: excluindo anexos | NdEtSortExclAttach | ND_ET_sort_excl_attach | Classificação ND/ET: excluindo anexos | Concatenação de conjunto de emails e ND definidos para classificação eficiente no momento da revisão; D é adicionado como um prefixo a ND sets e e é adicionado aos conjuntos de emails. |
| Classificação ND/ET: incluindo anexos | NdEtSortInclAttach | ND_ET_sort_incl_attach | Classificação ND/ET: incluindo anexos | Concatenação de conjunto de emails e ND definidos para classificação eficiente no momento da revisão; D é adicionado como um prefixo a ND sets e e é adicionado aos conjuntos de emails. Cada email dentro de um conjunto de emails é seguido por seus anexos apropriados. |
| A pontuação de relevância normalizada problema de caso 1 |  | Normalized_relevance_score_case_issue_1 |  | Pontuação de relevância normalizada o problema de caso 1 de relevância. |
| Autores do O365 |  | O365_authors | Autores do O365 | Autor do SharePoint. |
| O365 criado por |  | O365_created_by | O365 criado por | Criado pelo SharePoint. |
| Data do O365 criada |  | O365_date_created | Data do O365 criada | Data de criação do SharePoint. |
| Data de modificação do O365 |  | O365_date_modified | Data de modificação do O365 | Data da última modificação do SharePoint. |
| O365 modificado por |  | O365_modified_by | O365 modificado por | Modificadas pelo SharePoint. |
| ID do pai | ParentId | Parent_ID | ID do pai | ID do item pai. |
| ParentNode |  | Parent_node |  | A mensagem de email anterior à mais próxima no thread de email. |
| Caminho pai | ParentPath | Parent_path | Caminho pai | Caminho composto do pai direto do item. |
| Domínios participantes | ParticipantDomains | Email_participant_domains | Domínios participantes | Lista de todos os domínios de participantes de uma mensagem. |
| Participante | Participante | Email_participants | Participante | Lista de todos os participantes de uma mensagem; por exemplo, remetente, para, CC, Cco. |
| ID da tabela dinâmica | Pivotid | Pivot_ID | ID da tabela dinâmica | A ID de uma tabela dinâmica. |
| Potencialmente privilegiado | PotentiallyPrivileged | Potentially_privileged | Potencialmente privilegiado | True se o modelo de detecção de privilégio de cliente do advogado considerar o documento potencialmente privilegiado |
| Status de processamento | ProcessingStatus | Error_code | Status de processamento | Status de processamento após o item ter sido adicionado a um conjunto de revisão. |
| Ler o problema de caso de porcentagem 1 |  | Read_percent_Case_issue_1 |  | Leia o problema de porcentagem de caso 1 de relevância. |
| Ler percentil | ReadPercentile |  | Ler percentil | Leia o percentil do documento com base na relevância. |
| Contagem de destinatários |  | Recipient_count | Contagem de destinatários | Número de destinatários na mensagem. |
| Domínios de destinatário | RecipientDomains | Email_recipient_domains | Domínios de destinatário | Lista de todos os domínios de destinatários de uma mensagem. |
| Destinatários | Destinatários | Email_recipients | Destinatários | Lista de todos os destinatários de uma mensagem (para, CC, Cco). |
| Problema de caixa de grupo de carga de relevância 1 |  | Relevance_load_group_case_issue_1 |  | Grupo de carga de relevância problema de caso 1 de relevância. |
| Descrição do status de relevância problema 1 |  | Relevance_status_description_Case_issue_1 |  | Descrição do status de relevância problema 1 da relevância. |
| Problema de caso de marca de relevância 1 |  | Relevance_tag_case_issue_1 |  | Problema de caso de marca de relevância 1 da relevância. |
| Comentário de relevância |  | Relevance_comment | Comentário de relevância | Campo de comentário de relevância. |
| Pontuação de relevância | RelevanceScore |  | Pontuação de relevância | Pontuação de relevância de um documento com base na relevância. |
| Marca de relevância | RelevanceTag |  | Marca de relevância | Pontuação de relevância de um documento com base na relevância. |
| ID do representante | Representativo |  | ID do representante | Identificador numérico de cada conjunto de duplicatas exatas. |
| Remetente | Remetente | Email_sender | Remetente | Campo remetente (de) para tipos de mensagem.  Format é **DisplayName \<SmtpAddress>**. |
| Remetente/autor | SenderAuthor |  | Remetente/autor | Campo calculado composto pelo remetente ou autor do item. |
| Domínio do remetente | SenderDomain | Email_sender_domain | Domínio do remetente | Domínio do remetente. |
| Sent | Sent | Email_date_sent | Sent | Data de envio da mensagem. |
| Definir ordem: inclusivo primeiro | SetOrderInclusivesFirst | Set_order_inclusives_first | Definir ordem: inclusive primeiro. | Campo de classificação-email e anexos: contador-cronológico, documentos: tabela dinâmica primeiro, por Pontuação de similaridade, decrescente. |
| SimilarityPercent |  | Similarity_percent |  | Indica a aparência de um documento para a tabela dinâmica do conjunto próximo duplicado. |
| Tamanho do arquivo nativo | Tamanho | Native_size | Tamanho do arquivo nativo | Número de bytes do item nativo. |
| Assunto | Assunto | Email_subject | Assunto | Assunto da mensagem. |
| Assunto/título | SubjectTitle |  | Assunto/título | Campo calculado composto pelo assunto ou título do item. |
| Marcado por problema de caso 1 |  | Tagged_by_Case_issue_1 |  | Usuário que marcou este documento para o problema de caso 1, em relevância. |
| Marcações | Marcações | Marcações | Marcações | Marcas aplicadas em um conjunto de revisão. |
| Lista de temas | Themelist | Themes_list | Lista de temas | Lista de temas conforme calculado para análise. |
| Cargo | Cargo | Doc_title | Cargo | Título dos metadados do documento. |
| To | To | Email_to | To | Campo para para tipos de mensagem.  Format é **DisplayName\<SmtpAddress>** |
| Exclusivo no conjunto de emails | UniqueInEmailSet |  | Exclusivo no conjunto de emails | False se houver uma duplicata do anexo em seu conjunto de emails. |
| Foi corrigido | WasRemediated | Was_Remediated | Foi corrigido | True se o item foi corrigido, caso contrário, false. |
| Contagem de palavras | WordCount | Word_count | Contagem de palavras | Número de palavras no item. |
||||||

  > [!NOTE]
  > Para obter mais informações sobre as propriedades pesquisáveis ao pesquisar os locais de conteúdo do Office 365 quando você estiver coletando dados para um caso de descoberta eletrônica avançada, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).