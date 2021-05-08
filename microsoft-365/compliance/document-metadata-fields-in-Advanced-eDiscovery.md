---
title: Campos de metadados do documento na Descoberta Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Este artigo define os campos de metadados para documentos em um conjunto de revisão em um caso em Advanced eDiscovery em Microsoft 365.
ms.openlocfilehash: e801f60b69c796dfcd2cb6d83cc4fbc721dc7658
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259458"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadados do documento na Descoberta Avançada

A tabela a seguir lista os campos de metadados para documentos em um conjunto de revisão em um caso em Advanced eDiscovery. A tabela fornece as seguintes informações:

- **Nome do** campo e nome do campo De exibição: o nome do campo de metadados e o nome do campo exibido ao exibir os metadados de arquivo de um documento selecionado em um conjunto de revisão.  Alguns campos de metadados não são incluídos ao exibir os metadados de arquivo de um documento. Esses campos são realçados com um asterisco (*).

- **Nome do campo pesquisável:** O nome da propriedade que você pode pesquisar ao executar uma consulta [de conjunto de revisão.](review-set-search.md) Uma célula em branco significa que você não pode pesquisar o campo em uma consulta de conjunto de revisão.

- **Nome do campo exportado:** O nome do campo de metadados incluído quando os documentos são exportados.  Uma célula em branco significa que o campo não está incluído nos metadados exportados.

- **Descrição:** Uma descrição do campo de metadados.

> [!NOTE]
> O **campo Palavras-chave** na [pesquisa do conjunto de revisão](./review-set-search.md) usa KQL (Keyword Query Language). Os campos listados na coluna **Nome** do campo **Pesquisável** podem ser usados no campo Palavras-chave em uma pesquisa de conjunto de revisão para formar consultas complexas sem que você tenha que usar o construtor de consultas. Para obter mais informações sobre KQL, consulte [Keyword Query Language sintaxe reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

|**Nome do campo** e **nome do campo De exibição**|**Nome do campo pesquisável**|**Nome do campo exportado**|**Descrição**|
|:-----|:-----|:-----|:-----|
|ID de conteúdo de anexo|AttachmentContentId||ID de conteúdo de anexo do item.|
|Pontuação de privilégio do cliente advogado|AttorneyClientPrivilegeScore||Pontuação de conteúdo do modelo de privilégio advogado-cliente.|
|Autor|Autor|Doc_authors|Autor dos metadados do documento.|
|BCC|Cco|Email_bcc|Campo Cc para tipos de mensagem. Format é **DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Campo Cc para tipos de mensagem. Format é **DisplayName \<SMTPAddress>**.|
|Rótulos de conformidade|ComplianceLabels|Compliance_labels|[Rótulos de](retention.md) retenção aplicados ao conteúdo em Office 365.|
|Caminho Composto|CompoundPath|Compound_path|Caminho acessível para humanos que descreve a origem do item.|
|Content*|Conteúdo||Texto extraído do item.|
|Corpo da Conversa|Corpo da Conversa||Corpo da conversa do item.|
|Tópico de Conversa|Tópico de Conversa||Tópico de conversa do item.|
|ID da conversa|ConversationId|Email_conversation_ID|ID da conversa da mensagem.|
|Índice de Conversa||Conversation_index|Índice de conversa da mensagem.|
|Hora do Pdf da Conversa|ConversationPdfTime||Data em que a versão em PDF da conversa foi criada.|
|Tempo de queima de redação de conversa|ConversationRedactionBurnTime||Data em que a versão PDF da conversa foi criada para Chat.|
|||Converted_file_path|O caminho do arquivo de exportação convertido. Somente para uso interno da Microsoft.|
|Data de documento criada|CreatedTime|Doc_date_created|Criar data a partir de metadados de documento.|
|Custodian|Custodian|Custodian|Nome do custodiado ao item associado.|
|Data|Data|Data|Date é um campo calculado que depende do tipo de arquivo.<br /><br />Email: Data de envio<br />Anexos de email: Data da última modificação do documento; se não estiver disponível, a data de envio do pai<br />Documentos incorporados: Data da última modificação do documento; se não estiver disponível, a última data modificada do pai<br />Documentos SPO (inclui anexos modernos): SharePoint última data modificada; se não estiver disponível, a data da última modificação dos documentos<br />Documentos não Office 365: Data da última modificação<br />Reuniões: Data de início da reunião<br />VoiceMail: Data de enviado<br />IM: Data de enviado|
|Outros caminhos|Dedupedcompoundpath|Deduped_compound_path|Lista de caminhos compostos de documentos que são duplicatas exatas (email: com base no conteúdo, documentos: com base no hash).|
|Outros custodiantes|DedupedCustodians|Deduped_custodians|Lista de custodiantes de documentos que são duplicatas exatas (para email, com base no conteúdo; para documentos, com base no hash).|
|Outras IDs de arquivo|DedupedFileIds|Deduped_file_IDs|Lista de IDs de arquivo de documentos que são duplicatas exatas (para email, com base no conteúdo; para documentos, com base no hash).|
|Comentários do documento|DocComments|Doc_comments|Comentários dos metadados do documento.|
|Empresa de documentos||Doc_company|Empresa dos metadados do documento.|
|DocIndex*|||O índice na família. **-1** ou **0** significa que é a raiz.|
|Palavras-chave do documento||Doc_keywords|Palavras-chave dos metadados do documento.|
|Documento modificado por||Doc_modified_by|Data da última modificação de metadados do documento.|
|Revisão de Documento|Doc_Version|Doc_Version|Revisão dos metadados do documento.|
|Assunto do documento||Doc_subject|Assunto dos metadados do documento.|
|Modelo de documento||Doc_template|Modelo dos metadados do documento.|
|DocLastSavedBy||Doc_last_saved_by|O nome do usuário que salvou o documento pela última vez.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante conforme calculado para análise.|
|Subconjunto duplicado||Duplicate_subset|ID do grupo para duplicatas exatas.|
|EmailAction*||Email_action|Os valores **são None,** **Reply** ou **Forward;** com base na linha de assunto de uma mensagem.|
|Recibo de Entrega de Email Solicitado||Email_delivery_receipt_requested|Endereço de email fornecido em Headers da Internet para recebimento de entrega.|
|Importance|EmailImportance|Email_importance|Importância da mensagem: **0** - Baixo; **1** - Normal; **2** - Alto|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|O conjunto completo de headers de email da mensagem de email|
|EmailLevel*||Email_level|Indica o nível de uma mensagem dentro do thread de email a que ela pertence; os anexos herdam o valor da mensagem pai.|
|ID da mensagem de email||Email_message_ID|ID de mensagem da Internet da mensagem.|
|EmailReadReceiptRequested||Email_read_receipt_requested|Endereço de email fornecido nos Headers da Internet para recebimento de leitura.|
|Segurança de Email|EmailSecurity|Email_security|Configuração de segurança da mensagem: **0** - Nenhuma; **1** - Assinado; **2** - Criptografado; **3** - Criptografado e assinado.|
|Sensibilidade de Email|EmailSensitivity|email_sensitivity|Configuração de sensibilidade da mensagem: **0** - Nenhuma; **1** Pessoal; **2** - Privado; **3** - CompanyConfidential.|
|Conjunto de email|EmailSet|Email_set|ID do grupo para todas as mensagens no mesmo conjunto de emails.|
|EmailThread*||Email_thread|Posição da mensagem dentro do conjunto de emails; consiste em IDs de nó da raiz para a mensagem atual e são separadas por períodos (.).|
|||Export_native_path|O caminho do arquivo exportado.|
|Tipo de conteúdo extraído||Native_type|Tipo de conteúdo extraído, na forma de tipo mime; por exemplo, **image/jpeg**|
|||Extracted_text_path|O caminho para o arquivo de texto extraído na exportação.|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres no texto extraído.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico para famílias que são duplicatas exatas umas das outras (mesmo conteúdo e todos os mesmos anexos).|
|ID da família|FamilyId|Family_ID|Grupos de ID da família reúnem todos os itens; para email, isso inclui a mensagem e todos os anexos; para documentos, isso inclui o documento e todos os itens incorporados.|
|Tamanho da família||Family_size|Número de documentos na família.|
|Classe File|FileClass|File_class|Para conteúdo de SharePoint e OneDrive: **Documento;** para conteúdo de Exchange: **Email** ou **Anexo.**|
|ID do arquivo|FileId|File_ID|Identificador de documento exclusivo dentro do caso.|
|Data do sistema de arquivos criada||File_system_date_created|Data criada a partir do sistema de arquivos (só se aplica a dados que não Office 365 dados).|
|Data do sistema de arquivos modificada||File_system_date_modified|Data modificada do sistema de arquivos (só se aplica a dados que não Office 365 dados).|
|Tipo de arquivo|FileType||Tipo de arquivo do item com base na extensão de arquivo.|
|Id do grupo|GroupID||ID do grupo para conteúdo agrupado.|
|Tem anexo|HasAttachment|Email_has_attachment|Indica se a mensagem tem anexos ou não.|
|Tem advogado|HasAttorney||**True** quando pelo menos um dos participantes é encontrado na lista de advogados; caso contrário, o valor será **False**.|
|HasText*||Has_text|Indica se o item tem texto ou não; os valores possíveis **são True** e **False**.|
|ID Imutável||Immutable_ID|Essa ID é usada para identificar exclusivamente um documento em um conjunto de revisão. Esse campo não pode ser usado em uma pesquisa de conjunto de revisão e a ID não pode ser usada para acessar um documento em seu local nativo.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para análise: **0** - não inclusivo; **1** - inclusive; **2** - inclusive menos; **3** - cópia inclusiva.|
|Em Responder a Id||In_reply_to_ID|Em resposta à ID da mensagem.|
|InputFileExtension||Original_file_extension|A extensão de arquivo original do arquivo.|
|InputFileID||Input_file_ID|A ID do arquivo do item de nível superior no conjunto de revisão. Para um anexo, essa ID será a ID do pai. Isso pode ser usado para agrupar famílias.|
|É anexo moderno| IsModernAttachment|  |Esse arquivo é um anexo moderno ou arquivo vinculado.|
|É da versão do documento | IsFromDocumentVersion |  |O documento atual é de uma versão diferente de outro documento.|
|É anexo de email | IsEmailAttachment|  |Esse item é de um anexo de email que aparece como um item anexado à mensagem.|
|É anexo em linha| IsInlineAttachment|  |Isso foi anexado em linha e aparece no corpo da mensagem.|
|É representativo|IsRepresentative|Is_representative|Um documento em cada conjunto de duplicatas exatas é marcado como representativo.|
|Classe Item|ItemClass|Item_class|Classe item fornecida pelo servidor exchange; por exemplo, **IPM. Observação**|
|Last modified date|LastModifiedDate|Doc_date_modified|Data da última modificação dos metadados do documento.|
|ID de carga|LoadId|Load_ID|A ID do conjunto de carga no qual o item foi adicionado a um conjunto de revisão.|
|Location|Location|Location|Cadeia de caracteres que indica o tipo de local do qual os documentos foram fonte.<br /><br />**Dados Importados** - Dados não Office 365 dados<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange caixas de correio<br />**SharePoint** - SharePoint sites<br />**OneDrive** - OneDrive contas|
|Nome do local|LocationName|Location_name|Cadeia de caracteres que identifica a origem do item. Para o exchange, esse será o endereço SMTP da caixa de correio; para SharePoint e OneDrive, a URL do conjunto de sites.|
|||Marked_as_pivot|Este arquivo é o pivô em um conjunto quase duplicado.|
|Marcado como representativo|MarkAsRepresentative||Um documento de cada conjunto de duplicatas exatas é marcado como representantes.|
|Data de Término da Reunião|MeetingEndDate|Meeting_end_date|Data de término da reunião para reuniões.|
|Data de início da reunião|MeetingStartDate|Meeting_start_date|Data de início da reunião para reuniões.|
|Tipo de mensagem|MessageKind|Message_kind|O tipo de mensagem a ser pesquisada. Valores possíveis: contatos docs email **<br /> <br /> <br /> <br /> <br /> externaldata <br /> faxes <br /> im journals reuniões <br /> <br /> <br /> microsoftteams** (retorna itens de chats, reuniões e chamadas no Microsoft Teams) anotações de mensagens **<br /> <br /> <br /> rssfeeds <br /> <br />** tarefas de caixa postal| 
|ID pai do anexo moderno||ModernAttachment_ParentId|A ID Imutável do pai do documento.|
|Extensão Nativa|NativeExtension|Native_extension|Extensão nativa do item.|
|Nome de arquivo nativo|NativeFileName|Native_file_name|Nome de arquivo nativo do item.|
|NativeMD5||Native_MD5|Hash MD5 (valor de hash de 128 bits) do fluxo de arquivos.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor de hash de 256 bits) do fluxo de arquivos.|
|Classificação ND/ET: Excluindo anexos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenação do conjunto de threads de email (ET) e conjunto quase duplicado (ND). Esse campo é usado para uma classificação eficiente no momento da revisão. Um **D** é prefixado para conjuntos de ND e **um E** é prefixado para conjuntos ET.|
|Classificação do ND/ET: Incluindo anexos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenação de um conjunto de threads de email (ET) e conjunto ND (quase duplicado). Esse campo é usado para uma classificação eficiente no momento da revisão. Um **D** é prefixado para conjuntos de ND e **um E** é prefixado para conjuntos ET. Cada item de email em um conjunto ET é seguido por seus anexos apropriados.|
|Autores do O365||O365_authors|Autor de SharePoint.|
|O365 criado por||O365_created_by|Criado por SharePoint.|
|Data do O365 criada||O365_date_created|Data criada a partir SharePoint.|
|Modificação de data do O365||O365_date_modified|Data da última modificação do SharePoint.|
|O365 modificado por||O365_modified_by|Modificado por SharePoint.|
|ID pai|ParentId|Container_ID|ID do pai do item.|
|ParentNode||Parent_node|A mensagem de email anterior mais próxima no thread de email.|
|Domínios participantes|ParticipantDomains|Email_participant_domains|Lista de todos os domínios de participantes de uma mensagem.|
|Participantes|Participantes|Email_participants|Lista de todos os participantes de uma mensagem; por exemplo, Remetente, Para, Cc, Cc.|
|ID dinâmica|PivotId|Pivot_ID|A ID de um pivô.|
|Potencialmente privilegiado|PotentiallyPrivileged|Potentially_privileged|True se o modelo de detecção de privilégio advogado-cliente considerar o documento potencialmente privilegiado|
|Status do processamento|ProcessingStatus|Error_code|Status de processamento depois que o item foi adicionado a um conjunto de revisão.|
|Percentil de leitura|ReadPercentile||Ler percentil para o documento com base em Relevância.|
|Received|Received|Email_date_received|A data e a hora em que o email foi recebido em UTC.|
|Contagem de destinatários||Recipient_count|Número de destinatários na mensagem.|
|Domínios de destinatário|RecipientDomains|Email_recipient_domains|Lista de todos os domínios de destinatários de uma mensagem.|
|Destinatários|Destinatários|Email_recipients|Lista de todos os destinatários de uma mensagem (Para, Cc, Cc).|
|||Redacted_file_path|O caminho do arquivo de substituição redacted na exportação.|
|||Redacted_text_path|O caminho da substituição do arquivo de texto redacionado na exportação. Somente para uso interno da Microsoft.|
|Problema de caso de marca de relevância 1||Relevance_tag_case_issue_1|Marca de relevância Problema de caso 1 de Relevância.|
|Pontuação de relevância|RelevanceScore||Pontuação de relevância de um documento com base na Relevância.|
|Marca de relevância|RelevanceTag||Pontuação de relevância de um documento com base na Relevância.|
|ID representativa|RepresentativeId||Identificador numérico de cada conjunto de duplicatas exatas.|
|||Row_number|O número da linha do item no arquivo de carga.|
|Remetente|Remetente|Email_sender|Campo Remetente (De) para tipos de mensagem. Format é **DisplayName \<SmtpAddress>**.|
|Remetente/Autor|SenderAuthor||Campo calculado composto pelo remetente ou autor do item.|
|Domínio do remetente|SenderDomain|Email_sender_domain|Domínio do remetente.|
|Sent|Sent|Email_date_sent|Data enviada da mensagem.|
|Definir Ordem: Inclusiva Primeiro|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de classificação - email e anexos: contra-cronologia; documents: pivot primeiro, em seguida, pela pontuação de semelhança decrescente.|
|SimilarityPercent||Similarity_percent|Indica como um documento é semelhante ao pivô do conjunto duplicado próximo.|
|Tamanho do arquivo nativo|Size|Native_size|Número de bytes do item nativo.|
|Subject|Subject|Email_subject|Assunto da mensagem.|
|Assunto/Título|SubjectTitle||Campo calculado composto pelo assunto ou título do item.|
|Marcas|Marcas|Marcas|Marcas aplicadas em um conjunto de revisão.|
|Lista de temas|ThemesList|Themes_list|Lista de temas conforme calculado para análise.|
|Título|Título|Doc_title|Título dos metadados do documento.|
|Para|Para|Email_to|Para campo para tipos de mensagem. Format é **DisplayName \<SmtpAddress>**|
|Exclusivo no conjunto de emails|UniqueInEmailSet||**False** se houver uma duplicata do anexo em seu conjunto de emails.|
|ID do Grupo de Versão||Version_Group_Id|Reúne as diferentes versões do mesmo documento.|
|Foi remediado|WasRemediated|Was_Remediated|**True** se o item foi remediado, caso **contrário, False**.|
|Contagem de palavras|WordCount|Word_count|Número de palavras no item.|
|||||

> [!NOTE]
> Para obter mais informações sobre propriedades pesquisáveis ao pesquisar Office 365 de conteúdo quando você estiver coletando dados para um caso Advanced eDiscovery, consulte Consultas de palavra-chave e condições de pesquisa para Pesquisa de [Conteúdo](keyword-queries-and-search-conditions.md).
