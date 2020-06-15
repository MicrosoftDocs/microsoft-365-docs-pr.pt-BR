---
title: Campos de metadados de documentos na descoberta eletrônica avançada
f1.keywords:
- NOCSH
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
description: Este artigo define os campos de metadados para documentos em uma revisão configurada em um caso de descoberta eletrônica avançada no Microsoft 365.
ms.openlocfilehash: 19a8b4968ea4b1d82cd6a9e9278530e6c155ef3f
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726451"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadados de documentos na descoberta eletrônica avançada

A tabela a seguir lista os campos de metadados para documentos em uma revisão definida em um caso na descoberta eletrônica avançada. A tabela fornece as seguintes informações:

- Nome do **campo** e **nome do campo de exibição:** o nome do campo de metadados e o nome do campo que é exibido ao exibir os metadados de arquivo de um documento selecionado em um conjunto de revisão. Alguns campos de metadados não estão incluídos ao exibir os metadados de arquivo de um documento. Esses campos são realçados com um asterisco (*).

- **Nome do campo pesquisável:** O nome da propriedade que você pode pesquisar ao executar uma consulta de [conjunto de revisão](review-set-search.md). Uma célula em branco significa que você não pode pesquisar o campo em uma consulta de conjunto de revisão.

- **Nome do campo exportado:** O nome do campo de metadados que incluiu quando os documentos são exportados.  Uma célula em branco significa que o campo não está incluído nos metadados exportados.

- **Descrição:** Uma descrição do campo de metadados.

> [!NOTE]
> O campo **palavras-chave** em [Review Set Search](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) use keyword Query Language (KQL). Os campos listados na coluna **nome do campo pesquisável** podem ser usados no campo **palavras-chave** em uma revisão definir pesquisa para formar consultas complexas sem ter que usar o construtor de consultas. Para obter mais informações sobre o KQL, consulte [keyword Query Language Syntax Reference](https://go.microsoft.com/fwlink/?LinkId=269603).

|Nome do **campo** e **nome do campo de exibição**|**Nome do campo pesquisável**|**Nome do campo exportado**|**Descrição**|
|:-----|:-----|:-----|:-----|
|ID de conteúdo do anexo|AttachmentContentId||ID do conteúdo do anexo do item.|
|Nomes de anexos|Attachmentnames|Attachment_Names|Lista de nomes de anexos.|
|Pontuação de privilégio de cliente advogado|AttorneyClientPrivilegeScore||Advogado-Pontuação de conteúdo do modelo de privilégio do cliente.|
|Autor|Autor|Doc_authors|Autor dos metadados do documento.|
|BCC|Cco|Email_bcc|Campo Cco para tipos de mensagem. O formato **é \<SMTPAddress> DisplayName **.|
|CC|Cc|Email_cc|Campo CC para tipos de mensagem. O formato **é \<SMTPAddress> DisplayName **.|
|Rótulos de conformidade|ComplianceLabels|Compliance_labels|[Rótulos de retenção](labels.md) aplicados ao conteúdo no Office 365.|
|Caminho composto|CompoundPath|Compound_path|Caminho legível humana que descreve a fonte do item.|
|Content|Conteúdo||Texto extraído do item.|
|Corpo da conversa|Corpo da conversa||Corpo da conversa do item.|
|Tópico de conversa|Tópico de conversa||Tópico de conversa do item.|
|ID da conversa|ConversationId|Conversation_ID|ID da conversa da mensagem.|
|Índice de conversa||Conversation_index|Índice de conversa da mensagem.|
|Hora do PDF da conversa|ConversationPdfTime||Data em que a versão do PDF da conversa foi criada.|
|Tempo de gravação da redação da conversa|ConversationRedactionBurnTime||Data em que a versão do PDF da conversa foi criada para o chat.|
|Data de criação do documento|CreatedTime|Doc_date_created|Criar data a partir de metadados de documento.|
|Custodian|Custodian|Custodian|Nome dos responsáveis com os quais o item foi associado.|
|Data|Data|Data|Data é um campo computado que depende do tipo de arquivo.<br /><br />Email: data de envio<br />Anexos de email: data da última modificação do documento; se não estiver disponível, a data de envio do pai<br />Documentos incorporados: data da última modificação do documento; Se não estiver disponível, a data da última modificação do pai<br />Documentos do SPO (inclui anexos modernos): data da última modificação do SharePoint; Se não estiver disponível, a data da última modificação dos documentos<br />Documentos que não são do Office 365: data da última modificação<br />Reuniões: data de início da reunião<br />Caixa postal: data de envio<br />IM: data de envio|
|Outros caminhos|Dedupedcompoundpath|Deduped_compound_path|Lista de caminhos compostos de documentos que são duplicatas exatas (email: com base no conteúdo, documentos: com base no hash).|
|Outros responsáveis|DedupedCustodians|Deduped_custodians|Lista de responsáveis por documentos que são duplicatas exatas (por email, com base no conteúdo; para documentos, com base no hash).|
|Outras IDs de arquivo|DedupedFileIds|Deduped_file_IDs|Lista de IDs de arquivo de documentos que são duplicatas exatas (para email, com base no conteúdo; para documentos, com base no hash).|
|Comentários do documento|DocComments|Doc_comments|Comentários dos metadados do documento.|
|Empresa de documentos||Doc_company|Empresa dos metadados do documento.|
|DocIndex*|||O índice da família. **-1** ou **0** significa que é a raiz.|
|Palavras-chave do documento||Doc_keywords|Palavras-chave dos metadados do documento.|
|Documento modificado por||Doc_modified_by|Data da última modificação por dos metadados do documento.|
|Revisão do documento||Doc_revision|Revisão dos metadados do documento.|
|Assunto do documento||Doc_subject|Assunto dos metadados do documento.|
|Modelo de documento||Doc_template|Modelo dos metadados do documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante conforme calculado para a análise.|
|Subconjunto duplicado||Duplicate_subset|ID de grupo para duplicatas exatas.|
|Emailaction *||Email_action|Os valores são **nenhum**, **responder**ou **encaminhar**; com base na linha de assunto de uma mensagem.|
|Confirmação de entrega de email||Email_delivery_receipt|Endereço de email fornecido em cabeçalhos da Internet para confirmação de entrega.|
|Importance|EmailImportance|Email_importance|Importância da mensagem: **0** -baixa; **1** -normal; **2** -alto|
|EmailLevel*||Email_level|Indica o nível de uma mensagem dentro do thread de email ao qual ela pertence; os anexos herdam o valor da mensagem pai.|
|ID da mensagem de email||Email_message_ID|ID de mensagem da Internet da mensagem.|
|EmailReadReceipt*||Email_read_receipt|Endereço de email fornecido em cabeçalhos da Internet para confirmação de leitura.|
|Segurança de email|EmailSecurity|Email_security|Configuração de segurança da mensagem: **0** -nenhum; **1** -assinado; **2** -criptografado; **3** -criptografado e assinado.|
|Confidencialidade de email|EmailSensitivity|email_sensitivity|Configuração de sensibilidade da mensagem: **0** -nenhum; **1** pessoal; **2** -privado; **3** -CompanyConfidential.|
|Conjunto de emails|Emailset|Email_set|ID de grupo para todas as mensagens no mesmo conjunto de email.|
|EmailThread*||Email_thread|Posição da mensagem dentro do conjunto de emails; consiste em IDs de nó da raiz para a mensagem atual e separadas por pontos (.).|
|Tipo de conteúdo extraído||Extracted_content_type|Tipo de conteúdo extraído, na forma de tipo MIME; por exemplo, **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres no texto extraído.|
|Pontos de relevância da família-problema de caso 1 *||Family_relevance_score_case_issue_1|Pontuação de relevância da família caso o problema 1 de relevância.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico para famílias que são duplicatas exatas entre si (mesmo conteúdo e todos os mesmos anexos).|
|ID da família|FamilyId|Family_ID|Grupos de ID de família juntos todos os itens; para email, isso inclui a mensagem e todos os anexos; para documentos, isso inclui o documento e todos os itens incorporados.|
|Tamanho da família||Family_size|Número de documentos na família.|
|Nota de relevância de arquivo problema de caso 1 *||File_relevance_score_case_issue_1|Pontuação de relevância de arquivo caso problema 1 de relevância.|
|Classe de arquivo|Fileclass|File_class|Para conteúdo do SharePoint e do OneDrive: **Document**; para o conteúdo do Exchange: **email** ou **anexo**.|
|ID de arquivo|FileId|File_ID|Identificador de documento exclusivo no caso.|
|Data do sistema de arquivos criada||File_system_date_created|Data de criação do sistema de arquivos (só se aplica a dados não-Office 365).|
|Data do sistema de arquivos modificada||File_system_date_modified|Data de modificação do sistema de arquivos (só se aplica a dados não-Office 365).|
|Tipo de arquivo|FileType||Tipo de arquivo do item com base na extensão de arquivo.|
|Tem anexo|HasAttachment|Email_has_attachment|Indica se a mensagem tem ou não anexos.|
|O advogado é|HasAttorney||**True** quando pelo menos um dos participantes é encontrado na lista advogado; caso contrário, o valor será **false**.|
|HasText||Has_text|Indica se o item tem ou não texto; os valores possíveis são **true** e **false**.|
|ID Imutável||Immutable_ID|Essa ID é usada para identificar exclusivamente um documento dentro de um conjunto de revisão. Este campo não pode ser usado em um conjunto de análise de pesquisa e a ID não pode ser usada para acessar um documento em seu local nativo.|
|Tipo inclusivo|Inclusivtype|Inclusive_type|Tipo inclusivo calculado para análise: **0** -não inclusivo; **1** -inclusive; **2** – menos inclusivo; cópia **3** incluindo.|
|Em responder à ID||In_reply_to_ID|Em resposta à ID da mensagem.|
|É representante|Isrepresentativo|Is_representative|Um documento em cada conjunto de duplicatas exatas é marcado como representante.|
|Classe de item|ItemClass|Item_class|Classe de item fornecida pelo Exchange Server; por exemplo, **IPM. Observação**|
|Last modified date|LastModifiedDate|Doc_date_modified|Data da última modificação dos metadados do documento.|
|ID de carregamento|Loadid|Load_ID|A ID do conjunto de carga no qual o item foi adicionado a um conjunto de revisão.|
|Location|Location|Location|Cadeia de caracteres que indica o tipo de local de onde os documentos foram originados.<br /><br />**Dados importados** de dados que não sejam do Office 365<br />**Teams** -Microsoft Teams<br />Caixas **de correio do Exchange-** Exchange<br />**SharePoint** -sites do SharePoint<br />**Onedrive** -contas do onedrive|
|Nome do local|LocationName|Location_name|Cadeia de caracteres que identifica a origem do item. Para o Exchange, este será o endereço SMTP da caixa de correio; para o SharePoint e o OneDrive, a URL do conjunto de sites.|
|Marcado como representante|MarkAsRepresentative||Um documento de cada conjunto de duplicatas exatas é marcado como representante.|
|Marcado como o problema de caso anterior à marca 1 *||Marked_as_pre_tagged_Case_issue_1|Marcado como problema de caso de marca 1 de relevância.|
|Marcado como problema de caso de propagação 1 *||Marked_as_seed_Case_issue_1|Marcado como o problema de caso de propagação 1 de relevância.|
|Data de término da reunião|MeetingEndDate|Meeting_end_date|Data de término da reunião para reuniões.|
|Data de início da reunião|MeetingStartDate|Meeting_start_date|Data de início da reunião para reuniões.|
|Tipo de mensagem|MessageKind|Message_kind|O tipo de mensagem a ser pesquisada. Valores possíveis: ** <br /> <br /> contatos <br /> de <br /> email <br /> externaldata <br /> faxes <br /> registros de mensagens instantâneas <br /> <br /> reuniões <br /> microsoftteams** (retorna itens de chats, reuniões e chamadas no Microsoft Teams) ** <br /> notas <br /> postagens <br /> rssfeeds <br /> caixa de <br /> correio de tarefas**| 
|Extensão nativa|NativeExtension|Native_extension|Extensão nativa do item.|
|Nome do arquivo nativo|NativeFileName|Native_file_name|Nome do arquivo nativo do item.|
|NativeMD5||Native_MD5|Hash MD5 (valor de hash de 128 bits) do fluxo de arquivo.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor de hash de 256 bits) do fluxo de arquivos.|
|Classificação ND/ET: excluindo anexos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenação do conjunto de threads de email (ET) definido e conjunto Near-Duplicate (ND). Este campo é usado para classificação eficiente no momento da revisão. Um **D** é prefixado para conjuntos de ND e um **E** é prefixado para conjuntos et.|
|Classificação ND/ET: incluindo anexos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenação de um conjunto de threads de email (ET) definido e conjunto Near-Duplicate (ND). Este campo é usado para classificação eficiente no momento da revisão. Um **D** é prefixado para conjuntos de ND e um **E** é prefixado para conjuntos et. Cada item de email em um conjunto ET é seguido pelos seus anexos apropriados.|
|A pontuação de relevância normalizada problema de caso 1||Normalized_relevance_score_case_issue_1|Pontuação de relevância normalizada o problema de caso 1 de relevância.|
|Autores do O365||O365_authors|Autor do SharePoint.|
|O365 criado por||O365_created_by|Criado pelo SharePoint.|
|Data do O365 criada||O365_date_created|Data de criação do SharePoint.|
|Data de modificação do O365||O365_date_modified|Data da última modificação do SharePoint.|
|O365 modificado por||O365_modified_by|Modificadas pelo SharePoint.|
|ID do pai|ParentId|Parent_ID|ID do item pai.|
|ParentNode||Parent_node|A mensagem de email anterior à mais próxima no thread de email.|
|Caminho pai|ParentPath|Parent_path|Caminho composto do pai direto do item.|
|Domínios participantes|ParticipantDomains|Email_participant_domains|Lista de todos os domínios de participantes de uma mensagem.|
|Participante|Participante|Email_participants|Lista de todos os participantes de uma mensagem; por exemplo, remetente, para, CC, Cco.|
|ID da tabela dinâmica|Pivotid|Pivot_ID|A ID de uma tabela dinâmica.|
|Potencialmente privilegiado|PotentiallyPrivileged|Potentially_privileged|True se o modelo de detecção de privilégio de cliente do advogado considerar o documento potencialmente privilegiado|
|Status de processamento|ProcessingStatus|Error_code|Status de processamento após o item ter sido adicionado a um conjunto de revisão.|
|Ler o problema de caso de porcentagem 1||Read_percent_Case_issue_1|Leia o problema de porcentagem de caso 1 de relevância.|
|Ler percentil|ReadPercentile||Leia o percentil do documento com base na relevância.|
|Contagem de destinatários||Recipient_count|Número de destinatários na mensagem.|
|Domínios de destinatário|RecipientDomains|Email_recipient_domains|Lista de todos os domínios de destinatários de uma mensagem.|
|Destinatários|Destinatários|Email_recipients|Lista de todos os destinatários de uma mensagem (para, CC, Cco).|
|Problema de caixa de grupo de carga de relevância 1||Relevance_load_group_case_issue_1|Grupo de carga de relevância problema de caso 1 de relevância.|
|Descrição do status de relevância problema 1||Relevance_status_description_Case_issue_1|Descrição do status de relevância problema 1 da relevância.|
|Problema de caso de marca de relevância 1||Relevance_tag_case_issue_1|Problema de caso de marca de relevância 1 da relevância.|
|Comentário de relevância||Relevance_comment|Campo de comentário de relevância.|
|Pontuação de relevância|RelevanceScore||Pontuação de relevância de um documento com base na relevância.|
|Marca de relevância|RelevanceTag||Pontuação de relevância de um documento com base na relevância.|
|ID do representante|Representativo||Identificador numérico de cada conjunto de duplicatas exatas.|
|Sender|Sender|Email_sender|Campo remetente (de) para tipos de mensagem. O formato **é \<SmtpAddress> DisplayName **.|
|Remetente/autor|SenderAuthor||Campo calculado composto pelo remetente ou autor do item.|
|Domínio do remetente|SenderDomain|Email_sender_domain|Domínio do remetente.|
|Sent|Sent|Email_date_sent|Data de envio da mensagem.|
|Definir ordem: inclusivo primeiro|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de classificação-email e anexos: deordem cronológica; Documents: pivot First, then por Pontuação de similaridade decrescente.|
|SimilarityPercent||Similarity_percent|Indica a aparência de um documento para a tabela dinâmica do conjunto próximo duplicado.|
|Tamanho do arquivo nativo|Size|Native_size|Número de bytes do item nativo.|
|Subject|Subject|Email_subject|Assunto da mensagem.|
|Assunto/título|SubjectTitle||Campo calculado composto pelo assunto ou título do item.|
|Marcado por problema de caso 1||Tagged_by_Case_issue_1|Usuário que marcou este documento para o problema de caso 1, em relevância.|
|Marcas|Marcas|Marcas|Marcas aplicadas em um conjunto de revisão.|
|Lista de temas|Themelist|Themes_list|Lista de temas conforme calculado para análise.|
|Title|Title|Doc_title|Título dos metadados do documento.|
|To|To|Email_to|Campo para para tipos de mensagem. O formato **é \<SmtpAddress> DisplayName**|
|Exclusivo no conjunto de emails|UniqueInEmailSet||**False** se houver uma duplicata do anexo em seu conjunto de emails.|
|Foi corrigido|WasRemediated|Was_Remediated|**True** se o item foi corrigido, caso contrário, **false**.|
|Contagem de palavras|WordCount|Word_count|Número de palavras no item.|
|||||

> [!NOTE]
> Para obter mais informações sobre as propriedades pesquisáveis ao pesquisar os locais de conteúdo do Office 365 quando você estiver coletando dados para um caso de descoberta eletrônica avançada, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).
