---
title: Document metadata fields in Advanced eDiscovery
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
description: Este artigo define os campos de metadados para documentos em um conjunto de revisão em um caso de Descoberta Avançada no Microsoft 365.
ms.openlocfilehash: 2bf9773f6c36e53231bb577c30e9900bf3e24df7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358439"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Document metadata fields in Advanced eDiscovery

A tabela a seguir lista os campos de metadados para documentos em um conjunto de revisão em um caso na Descoberta Avançada. A tabela fornece as seguintes informações:

- **Nome do** campo e nome do campo de exibição: o nome do campo de metadados e o nome do campo exibido ao exibir os metadados de arquivo de um documento selecionado em um conjunto de revisão.  Alguns campos de metadados não são incluídos ao exibir os metadados de arquivo de um documento. Esses campos são realçados com um asterisco (*).

- **Nome do campo pesquisável:** O nome da propriedade que você pode pesquisar ao executar uma consulta [de conjunto de revisão.](review-set-search.md) Uma célula em branco significa que você não pode procurar o campo em uma consulta de conjunto de revisão.

- **Nome do campo exportado:** O nome do campo de metadados incluído quando os documentos são exportados.  Uma célula em branco significa que o campo não está incluído com os metadados exportados.

- **Descrição:** Uma descrição do campo de metadados.

> [!NOTE]
> O **campo Palavras-chave** na pesquisa [do conjunto de revisão](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) usa Linguagem de Consulta de Palavra-chave (KQL). Os campos listados na coluna Nome do campo Pesquisável podem ser usados no campo Palavras-chave em uma pesquisa de conjunto de revisão para formar consultas complexas sem que você tenha que usar o construtor de consultas.   Para obter mais informações sobre KQL, consulte Referência de sintaxe da Linguagem de [Consulta de Palavra-chave.](https://go.microsoft.com/fwlink/?LinkId=269603)

|**Nome do campo** e **nome do campo de exibição**|**Nome do campo pesquisável**|**Nome do campo exportado**|**Descrição**|
|:-----|:-----|:-----|:-----|
|ID do conteúdo do anexo|AttachmentContentId||ID do conteúdo do anexo do item.|
|Nomes de anexos|AttachmentNames|Attachment_Names|Lista de nomes de anexos.|
|Pontuação de privilégios de cliente advogado|AttorneyClientPrivilegeScore||Pontuação de conteúdo do modelo de privilégio advogado-cliente.|
|Autor|Autor|Doc_authors|Autor dos metadados do documento.|
|BCC|Cco|Email_bcc|Campo Cc para tipos de mensagem. O formato é **DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Campo Cc para tipos de mensagem. O formato é **DisplayName \<SMTPAddress>**.|
|Rótulos de conformidade|ComplianceLabels|Compliance_labels|[Rótulos de](retention.md) retenção aplicados ao conteúdo no Office 365.|
|Caminho composto|CompoundPath|Compound_path|Caminho acessível para humanos que descreve a origem do item.|
|Conteúdo*|Conteúdo||Texto extraído do item.|
|Corpo da conversa|Corpo da conversa||Corpo da conversa do item.|
|Tópico da Conversa|Tópico da Conversa||Tópico de conversa do item.|
|ID da Conversa|ConversationId|Conversation_ID|ID da conversa da mensagem.|
|Índice de Conversa||Conversation_index|Índice de conversa da mensagem.|
|Hora da Conversa em Pdf|ConversationPdfTime||Data em que a versão em PDF da conversa foi criada.|
|Tempo de gravar da redação de conversa|ConversationRedactionBurnTime||Data em que a versão em PDF da conversa foi criada para Chat.|
|Data de criação do documento|CreatedTime|Doc_date_created|Criar data a partir de metadados do documento.|
|Custodian|Custodian|Custodian|Nome do custodiatário ao que o item estava associado.|
|Data|Data|Data|Data é um campo calculado que depende do tipo de arquivo.<br /><br />Email: Data de envio<br />Anexos de email: data da última modificação do documento; se não estiver disponível, a data de envio do pai<br />Documentos incorporados: data da última modificação do documento; se não estiver disponível, a data da última modificação do pai<br />Documentos SPO (inclui anexos modernos): data da última modificação do SharePoint; se não estiver disponível, os documentos foram modificados pela última vez<br />Documentos que não são do Office 365: Data da última modificação<br />Reuniões: Data de início da reunião<br />VoiceMail: Data de enviado<br />IM: Data de enviado|
|Outros caminhos|Dedupedcompoundpath|Deduped_compound_path|Lista de caminhos compostos de documentos que são duplicatas exatas (email: com base no conteúdo, documentos: com base no hash).|
|Outros custodiantes|DedupedCustodians|Deduped_custodians|Lista de custodiantes de documentos que são duplicatas exatas (para email, com base no conteúdo; para documentos, com base no hash).|
|Outras IDs de arquivo|DedupedFileIds|Deduped_file_IDs|Lista de IDs de arquivo de documentos que são duplicatas exatas (para email, com base no conteúdo; para documentos, com base no hash).|
|Comentários do documento|DocComments|Doc_comments|Comentários dos metadados do documento.|
|Empresa do documento||Doc_company|Empresa dos metadados do documento.|
|DocIndex*|||O índice na família. **-1** ou **0** significa que é a raiz.|
|Palavras-chave do documento||Doc_keywords|Palavras-chave dos metadados do documento.|
|Documento modificado por||Doc_modified_by|Data da última modificação dos metadados do documento.|
|Revisão de Documento||Doc_revision|Revisão dos metadados do documento.|
|Assunto do documento||Doc_subject|Assunto dos metadados do documento.|
|Modelo de documento||Doc_template|Modelo dos metadados do documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante conforme calculado para análise.|
|Subconjunto duplicado||Duplicate_subset|ID de grupo para duplicatas exatas.|
|EmailAction*||Email_action|Os valores são **None**, **Reply** ou **Forward**; com base na linha de assunto de uma mensagem.|
|Recibo de entrega de email||Email_delivery_receipt|Endereço de email fornecido nos Internet Headers para confirmação de entrega.|
|Importance|EmailImportance|Email_importance|Importância da mensagem: **0** - Baixa; **1** - Normal; **2** - Alto|
|EmailLevel*||Email_level|Indica o nível de uma mensagem dentro do thread de email ao que ela pertence; os anexos herdam o valor da mensagem pai.|
|ID da Mensagem de Email||Email_message_ID|ID de mensagem da Internet da mensagem.|
|EmailReadReceipt*||Email_read_receipt|Endereço de email fornecido nos Internet Headers para confirmação de leitura.|
|Segurança de Email|EmailSecurity|Email_security|Configuração de segurança da mensagem: **0** - Nenhum; **1** - Assinado; **2** - Criptografado; **3** - Criptografado e assinado.|
|Sensibilidade de Email|EmailSensitivity|email_sensitivity|Configuração de sensibilidade da mensagem: **0** - Nenhum; **1** Pessoal; **2** - Particular; **3** - CompanyConfidential.|
|Conjunto de emails|EmailSet|Email_set|ID do grupo para todas as mensagens no mesmo conjunto de emails.|
|EmailThread*||Email_thread|Posição da mensagem dentro do conjunto de emails; consiste em IDs de nó da raiz para a mensagem atual e são separadas por pontos (.).|
|Tipo de conteúdo extraído||Extracted_content_type|Tipo de conteúdo extraído, na forma de tipo mime; por exemplo, **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres no texto extraído.|
|Pontuação de relevância da família Problema de caso 1*||Family_relevance_score_case_issue_1|Pontuação de relevância da família Problema de caso 1 da Relevância.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico para famílias que são duplicatas exatas umas das outras (mesmo conteúdo e todos os mesmos anexos).|
|ID da Família|FamilyId|Family_ID|A ID de família reúne todos os itens; para email, isso inclui a mensagem e todos os anexos; para documentos, isso inclui o documento e todos os itens incorporados.|
|Tamanho da Família||Family_size|Número de documentos na família.|
|Pontuação de relevância do arquivo Problema de caso 1*||File_relevance_score_case_issue_1|Pontuação de relevância do arquivo Problema de ocorrência 1 da Relevância.|
|Classe file|FileClass|File_class|Para conteúdo do SharePoint e do OneDrive: **Documento**; para conteúdo do Exchange: **Email** ou **Anexo.**|
|ID do arquivo|FileId|File_ID|Identificador de documento exclusivo dentro da ocorrência.|
|Data de criação do sistema de arquivos||File_system_date_created|Data de criação do sistema de arquivos (aplica-se somente a dados que não são do Office 365).|
|Data de modificação do sistema de arquivos||File_system_date_modified|Data de modificação do sistema de arquivos (aplica-se somente a dados que não são do Office 365).|
|Tipo de arquivo|FileType||Tipo de arquivo do item com base na extensão do arquivo.|
|ID do Grupo| GroupID|  |ID do grupo para conteúdo agrupado.|
|Tem anexo|HasAttachment|Email_has_attachment|Indica se a mensagem tem anexos ou não.|
|Tem advogado|HasAttorney||**True** quando pelo menos um dos participantes é encontrado na lista de advogados; Caso contrário, o valor é **False**.|
|HasText*||Has_text|Indica se o item tem texto ou não; os valores possíveis **são True** e **False**.|
|ID Imutável||Immutable_ID|Essa ID é usada para identificar exclusivamente um documento dentro de um conjunto de revisão. Esse campo não pode ser usado em uma pesquisa de conjunto de revisão e a ID não pode ser usada para acessar um documento em seu local nativo.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para análise: **0** - não inclusivo; **1** - inclusive; **2** - menos inclusivo; **3** - cópia inclusiva.|
|Em Responder a ID||In_reply_to_ID|Em resposta à ID da mensagem.|
|É um anexo moderno| IsModernAttachment|  |Esse arquivo é um anexo moderno ou um arquivo vinculado.|
|É da versão do documento | IsFromDocumentVersion |  |O documento atual é de uma versão diferente de outro documento.|
|É anexo de email | IsEmailAttachment|  |Esse item é de um anexo de email que aparece como um item anexado à mensagem.|
|É anexo em linha| IsInlineAttachment|  |Isso foi anexado em linha e aparece no corpo da mensagem.|
|É Representativo|IsRepresentative|Is_representative|Um documento em cada conjunto de duplicatas exatas é marcado como representativo.|
|Classe item|ItemClass|Item_class|Classe de item fornecida pelo servidor exchange; por exemplo, **IPM. Observação**|
|Last modified date|LastModifiedDate|Doc_date_modified|Data da última modificação dos metadados do documento.|
|ID de carregamento|LoadId|Load_ID|A ID do conjunto de carga no qual o item foi adicionado a um conjunto de revisão.|
|Localização|Localização|Localização|Cadeia de caracteres que indica o tipo de local de origem dos documentos.<br /><br />**Dados importados** - dados que não são do Office 365<br />**Teams** - Microsoft Teams<br />**Exchange** - Caixas de correio do Exchange<br />**SharePoint** – sites do SharePoint<br />**OneDrive** - contas do OneDrive|
|Nome do local|LocationName|Location_name|Cadeia de caracteres que identifica a origem do item. Para o Exchange, esse será o endereço SMTP da caixa de correio; para o SharePoint e o OneDrive, a URL do conjunto de sites.|
|Marcado como representante|MarkAsRepresentative||Um documento de cada conjunto de duplicatas exatas é marcado como representantes.|
|Marcado como pré-marcado Caso problema 1*||Marked_as_pre_tagged_Case_issue_1|Marcado como pré-marcado Caso problema 1 da Relevância.|
|Marcado como problema de caso de semente 1*||Marked_as_seed_Case_issue_1|Marcado como problema de caso de semente 1 da Relevância.|
|Data de Término da Reunião|MeetingEndDate|Meeting_end_date|Data de término da reunião para reuniões.|
|Data de Início da Reunião|MeetingStartDate|Meeting_start_date|Data de início da reunião para reuniões.|
|Tipo de mensagem|MessageKind|Message_kind|O tipo de mensagem a ser pesquisada. Valores **<br /> <br /> possíveis: contatos <br /> docs <br /> email <br /> externaldata <br /> faxes <br /> im <br /> diários <br /> reuniões <br /> microsoftteams** (retorna itens de chats, reuniões e chamadas no Microsoft Teams) **<br /> anotações <br /> postagens <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|Extensão Nativa|NativeExtension|Native_extension|Extensão nativa do item.|
|Nome do arquivo nativo|NativeFileName|Native_file_name|Nome de arquivo nativo do item.|
|NativeMD5||Native_MD5|Hash MD5 (valor de hash de 128 bits) do fluxo de arquivo.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor de hash de 256 bits) do fluxo de arquivos.|
|Classificação de ND/ET: Excluindo anexos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenação do conjunto de threads de email (ET) e conjunto de duplicatas próximas (ND). Esse campo é usado para uma classificação eficiente no momento da revisão. Um **D** é prefixado para conjuntos de ND e **um E** é prefixado para conjuntos ET.|
|Classificação de ND/ET: Incluindo anexos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenação de um conjunto de threads de email (ET) e conjunto de ND (quase duplicados). Esse campo é usado para uma classificação eficiente no momento da revisão. Um **D** é prefixado para conjuntos de ND e **um E** é prefixado para conjuntos ET. Cada item de email em um conjunto ET é seguido por seus anexos apropriados.|
|Pontuação de relevância normalizada Problema de caso 1||Normalized_relevance_score_case_issue_1|Pontuação de relevância normalizada Problema de caso 1 da Relevância.|
|Autores do O365||O365_authors|Autor do SharePoint.|
|O365 criado por||O365_created_by|Criado pelo SharePoint.|
|Data de criação do O365||O365_date_created|Data de criação do SharePoint.|
|Data de modificação do O365||O365_date_modified|Data da última modificação do SharePoint.|
|O365 modificado por||O365_modified_by|Modificado pelo SharePoint.|
|ID do pai|ParentId|Parent_ID|ID do pai do item.|
|ParentNode||Parent_node|A mensagem de email anterior mais próxima no thread de email.|
|Caminho pai|ParentPath|Parent_path|Caminho composto do pai direto do item.|
|Domínios do participante|ParticipantDomains|Email_participant_domains|Lista de todos os domínios de participantes de uma mensagem.|
|Participantes|Participantes|Email_participants|Lista de todos os participantes de uma mensagem; por exemplo, Remetente, Para, Cc, Cc.|
|ID do pivô|PivotId|Pivot_ID|A ID de um pivô.|
|Potencialmente privilegiado|PotentiallyPrivileged|Potentially_privileged|True se o modelo de detecção de privilégio advogado-cliente considera o documento potencialmente privilegiado|
|Status do processamento|ProcessingStatus|Error_code|Status de processamento depois que o item foi adicionado a um conjunto de revisão.|
|Ler porcentagem Problema de caso 1||Read_percent_Case_issue_1|Problema de caso de leitura percentual 1 da Relevância.|
|Percentil de leitura|ReadPercentile||Percentil de leitura do documento com base na relevância.|
|Contagem de destinatários||Recipient_count|Número de destinatários na mensagem.|
|Domínios de destinatários|RecipientDomains|Email_recipient_domains|Lista de todos os domínios de destinatários de uma mensagem.|
|Destinatários|Destinatários|Email_recipients|Lista de todos os destinatários de uma mensagem (Para, Cc, Cócc).|
|Problema 1 do caso 1 do grupo de carga de relevância||Relevance_load_group_case_issue_1|Problema 1 do Caso de grupo de carga de relevância da Relevância.|
|Descrição do status de relevância Problema de caso 1||Relevance_status_description_Case_issue_1|Descrição do status de relevância Problema de caso 1 da Relevância.|
|Problema 1 do caso de marca de relevância||Relevance_tag_case_issue_1|Problema 1 do Caso de marca de relevância da Relevância.|
|Comentário de Relevância||Relevance_comment|Campo Comentário da Relevância.|
|Pontuação de relevância|RelevanceScore||Pontuação de relevância de um documento com base na relevância.|
|Marca de relevância|RelevanceTag||Pontuação de relevância de um documento com base na relevância.|
|ID do Representante|RepresentativeId||Identificador numérico de cada conjunto de duplicatas exatas.|
|Remetente|Remetente|Email_sender|Campo Remetente (De) para tipos de mensagem. O formato é **DisplayName \<SmtpAddress>**.|
|Remetente/Autor|SenderAuthor||Campo calculado composto pelo remetente ou autor do item.|
|Domínio do remetente|SenderDomain|Email_sender_domain|Domínio do remetente.|
|Sent|Sent|Email_date_sent|Data de enviado da mensagem.|
|Definir Ordem: Inclusivo Primeiro|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de classificação - email e anexos: contador-cronológica; documents: pivot first then by descending similarity score.|
|SimilarityPercent||Similarity_percent|Indica como um documento é semelhante ao pivô do conjunto duplicado próximo.|
|Tamanho do arquivo nativo|Size|Native_size|Número de bytes do item nativo.|
|Assunto|Assunto|Email_subject|Assunto da mensagem.|
|Assunto/Título|SubjectTitle||Campo calculado composto pelo assunto ou título do item.|
|Marcado por Problema de Caso 1||Tagged_by_Case_issue_1|Usuário que marcou este documento para o problema de caso 1 em Relevância.|
|Etiquetas|Etiquetas|Etiquetas|Marcas aplicadas em um conjunto de revisão.|
|Lista de temas|ThemesList|Themes_list|Lista de temas conforme calculado para análise.|
|Título|Título|Doc_title|Título dos metadados do documento.|
|To|To|Email_to|Campo Para tipos de mensagem. O formato é **DisplayName \<SmtpAddress>**|
|Exclusivo no conjunto de emails|UniqueInEmailSet||**False** se houver uma duplicata do anexo em seu conjunto de emails.|
|Foi remediado|WasRemediated|Was_Remediated|**True** se o item foi remediado, caso contrário **False**.|
|Contagem de palavras|WordCount|Word_count|Número de palavras no item.|
|||||

> [!NOTE]
> Para obter mais informações sobre propriedades pesquisáveis ao pesquisar locais de conteúdo do Office 365 quando você estiver coletando dados para um caso de Descoberta Avançada, consulte Consultas de palavra-chave e condições de pesquisa para Pesquisa de [Conteúdo.](keyword-queries-and-search-conditions.md)
