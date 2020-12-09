---
title: Condições, exceções e ações da política DLP (versão prévia)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre condições e exceções de política de DLP
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604211"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>Condições, exceções e ações da política DLP (versão prévia)

As condições e exceções nas políticas de DLP identificam os itens confidenciais aos quais a política é aplicada. As ações definem o que acontece como consequência de uma condição de exceção sendo atendida.

- As condições definem o que incluir
- As exceções definem o que excluir.
- As ações definem o que acontece como uma conseqüência de condição ou exceção que está sendo atendida
 
A maioria das condições e exceções têm uma propriedade que oferece suporte a um ou mais valores. Por exemplo, se a política de DLP estiver sendo aplicada aos emails do Exchange, a condição **de remetente** será necessária para o remetente da mensagem. Algumas condições têm duas propriedades. Por exemplo, o **cabeçalho de uma mensagem inclui qualquer uma destas palavras** condição requer uma propriedade para especificar o campo de cabeçalho da mensagem e uma segunda propriedade para especificar o texto a ser procurado no campo de cabeçalho. Algumas condições ou exceções não têm propriedades. Por exemplo, o **anexo é uma condição protegida por senha** simplesmente procura anexos em mensagens protegidas por senha.

As ações normalmente exigem propriedades adicionais. Por exemplo, quando a regra de política de DLP redireciona uma mensagem, você precisa especificar para onde a mensagem é redirecionada. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condições e exceções para políticas de DLP

As tabelas nas seções a seguir descrevem as condições e exceções disponíveis no DLP.

- [Remetentes](#senders)
- [Destinatários](#recipients)
- [Assunto ou corpo da mensagem](#message-subject-or-body)
- [Anexos](#attachments)
- [Cabeçalhos de mensagem](#message-headers)
- [Propriedades da mensagem](#message-properties)

### <a name="senders"></a>Senders


|**condição ou exceção no DLP**  |**parâmetros de condição/exceção no Microsoft 365 PowerShell** |**tipo de propriedade**  |**description**|
|---------|---------|---------|---------|
|Remetente é |condição: *de* <br/> exceção: *ExceptIfFrom*      |Endereços |     Mensagens enviadas por caixas de correio, usuários de email, contatos de email ou grupos do Microsoft 365 especificados na organização.|
|O endereço IP do remetente é     |condição: *SenderIPRanges*<br/> exceção: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensagens em que o endereço IP do remetente corresponde ao endereço IP especificado ou está dentro do intervalo de endereços IP especificado.       |
|Endereço do remetente contém palavras   | condição: *FromAddressContainsWords* <br/> exceção: *ExceptIfFromAddressContainsWords*        |   Palavras      |   Mensagens que contêm as palavras especificadas no endereço de email do remetente.|
| O endereço do remetente corresponde aos padrões    | condição: *FromAddressMatchesPatterns* <br/> exceção: *ExceptFromAddressMatchesPatterns*       |      Padrões   |  Mensagens em que o endereço de email do remetente contém padrões de texto que correspondem às expressões regulares especificadas.  |
|Domínio do remetente é  |  condição: *SenderDomainIs* <br/> exceção: *ExceptIfSenderDomainIs*       |DomainName         |     Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado. Se você precisar localizar domínios de remetente que *contenham* o domínio especificado (por exemplo, qualquer subdomínio de um domínio), use **a condição endereço do remetente correspondente**(*FromAddressMatchesPatterns*) e especifique o domínio usando a sintaxe: ' \. domínio \. com $ '.    |
|Escopo do remetente    | condição: *FromScope* <br/> exceção: *ExceptIfFromScope*    | UserScopeFrom    |    Mensagens enviadas por remetentes internos ou externos.    |

### <a name="recipients"></a>Destinatários

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell** |    **tipo de propriedade** | **description**|
|---------|---------|---------|---------|
|O destinatário é|  condição: *SentTo* <br/> exceção: *ExceptIfSentTo* | Endereços | Mensagens em que um dos destinatários é a caixa de correio, o usuário de email ou o contato de email especificado na organização. Os destinatários podem estar nos campos **para**, **CC** ou **Cco** da mensagem.|
|O domínio do destinatário é|   condição: *RecipientDomainIs* <br/> exceção: *ExceptIfRecipientDomainIs* |   DomainName |    Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado.|
|Endereço do destinatário contém palavras|  condição: *RecipientAddressContainsWords* <br/> exceção: *ExceptIfRecipientAddressContainsWords*|    Palavras|  Mensagens que contêm as palavras especificadas no endereço de email do destinatário. <br/>**Observação**: Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|O endereço do destinatário corresponde aos padrões| condição: *RecipientAddressMatchesPatterns* <br/> exceção: *ExceptIfRecipientAddressMatchesPatterns*|   Padrões    |Mensagens em que o endereço de email de um destinatário contém padrões de texto que correspondem às expressões regulares especificadas. <br/> **Observação**: Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|Enviado para o membro de| condição: *SentToMemberOf* <br/> exceção: *ExceptIfSentToMemberOf*|  Endereços|  Mensagens que contêm destinatários que são membros do grupo de distribuição especificado, grupo de segurança habilitado para email ou grupo do Microsoft 365. O grupo pode estar nos campos **para**, **CC** ou **Cco** da mensagem.|

### <a name="message-subject-or-body"></a>Assunto ou corpo da mensagem

|**condição ou exceção no DLP** | **parâmetros de condição/exceção no Microsoft 365 PowerShell** |**tipo de propriedade**| **description**|
|---------|---------|---------|---------|
|O assunto contém palavras ou frases| condição: *SubjectContainsWords* <br/> exceção: *ExceptIf SubjectContainsWords*| Palavras   |Mensagens com as palavras especificadas no campo assunto.|
|Assunto corresponde a padrões|condição: *SubjectMatchesPatterns* <br/> exceção: *ExceptIf SubjectMatchesPatterns*|Padrões   |Mensagens em que o campo assunto contém padrões de texto que correspondem às expressões regulares especificadas.|
|Conteúdo contém|  condição: *ContentContainsSensitiveInformation* <br/> exceção *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensagens ou documentos que contêm informações confidenciais, conforme definido pelas políticas de prevenção de perda de dados (DLP).|
| Padrão de correspondência de assunto ou corpo    | condição: *SubjectOrBodyMatchesPatterns* <br/> exceção: *ExceptIfSubjectOrBodyMatchesPatterns*    | Padrões    | Mensagens em que o campo de assunto ou o corpo da mensagem contém padrões de texto que correspondem às expressões regulares especificadas.    |
| Assunto ou corpo contém palavras    | condição: *SubjectOrBodyContainsWords* <br/> exceção: *ExceptIfSubjectOrBodyContainsWords*    | Palavras    | Mensagens com as palavras especificadas no campo assunto ou no corpo da mensagem    |


### <a name="attachments"></a>Attachments

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|O anexo é protegido por senha|condição: *DocumentIsPasswordProtected* <br/> exceção: *ExceptIfDocumentIsPasswordProtected*|Nenhuma| Mensagens em que um anexo está protegido por senha (e, portanto, não pode ser verificado). A detecção de senha só funciona para documentos do Office, arquivos. zip e arquivos. 7z.|
|A extensão do arquivo do anexo é|condição: *ContentExtensionMatchesWords* <br/> exceção: *ExceptIfContentExtensionMatchesWords*|  Palavras   |Mensagens em que a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O conteúdo de qualquer anexo de email não pôde ser verificado|condição: *DocumentIsUnsupported* <br/>exceção: *ExceptIf DocumentIsUnsupported*|   n/d|    Mensagens em que um anexo não é reconhecido nativamente pelo Exchange Online.|
|O conteúdo de qualquer anexo de email não concluiu a verificação|   condição: *ProcessingLimitExceeded* <br/> exceção: *ExceptIfProcessingLimitExceeded*|    n/d |Mensagens em que o mecanismo de regras não pôde concluir a verificação dos anexos. Você pode usar essa condição para criar regras que trabalham juntas para identificar e processar mensagens em que o conteúdo não pôde ser totalmente verificado.|
|O nome do documento contém palavras|condição: *DocumentNameMatchesWords* <br/> exceção: *ExceptIfDocumentNameMatchesWords* |Palavras  |Mensagens em que o nome de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O nome do documento corresponde aos padrões|condição: *DocumentNameMatchesPatterns* <br/> exceção: *ExceptIfDocumentNameMatchesPatterns*|    Padrões    |Mensagens em que o nome de arquivo de um anexo contém padrões de texto que correspondem às expressões regulares especificadas.|
|A propriedade do documento é|condição: *ContentPropertyContainsWords* <br/> exceção: *ExceptIfContentPropertyContainsWords* |Palavras| Mensagens ou documentos onde a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O tamanho do documento é igual a ou maior que| condição: *DocumentSizeOver* <br/> exceção: *ExceptIfDocumentSizeOver*|    Size    |Mensagens em que qualquer anexo é maior ou igual ao valor especificado.|

### <a name="message-headers"></a>Cabeçalhos de mensagem

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**|  **description**|
|---------|---------|---------|---------|
|Cabeçalho contém palavras ou frases|condição: *HeaderContainsWords* <br/> exceção: *ExceptIfHeaderContainsWords*|  Tabela de hash  |Mensagens que contêm o campo de cabeçalho especificado e o valor desse campo de cabeçalho contém as palavras especificadas.|
|Cabeçalho corresponde a padrões|   condição: *HeaderMatchesPatterns* <br/> exceção: *ExceptIfHeaderMatchesPatterns*|    Tabela de hash  |Mensagens que contêm o campo de cabeçalho especificado e o valor desse campo de cabeçalho contém as expressões regulares especificadas.|

### <a name="message-properties"></a>Propriedades da mensagem

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|Tamanho da mensagem sobre|condição: *MessageSizeOver* <br/> exceção: *ExceptIfMessageSizeOver*| Size    |Mensagens em que o tamanho total (mensagem mais anexos) é maior ou igual ao valor especificado. <br/>**Observação**: os limites de tamanho de mensagem nas caixas de correio são avaliados antes das regras de fluxo de email. Uma mensagem muito grande para uma caixa de correio será rejeitada antes que uma regra com essa condição seja capaz de atuar na mensagem.|
| Com prioridade    | condição: *WithImportance* <br/> exceção: *ExceptIfWithImportance*    | Importance    | Mensagens marcadas com o nível de prioridade especificado.    |
| Conjunto de caracteres de conteúdo contém palavras    | condição: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Mensagens que têm qualquer um dos nomes de conjunto de caracteres especificados.    |
| Tem substituição de remetente    | condição: *HasSenderOverride* <br/> exceção: *ExceptIfHasSenderOverride*    | n/d    | Mensagens em que o remetente optou por substituir uma política de prevenção de perda de dados (DLP). Para obter mais informações sobre políticas de DLP, consulte [prevenção de perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies).   |
| Correspondência de tipo de mensagem    | condição: *MessageTypeMatches* <br/> exceção: *ExceptIfMessageTypeMatches*    | MessageType    | Mensagens do tipo especificado.    |

## <a name="actions-for-dlp-policies"></a>Ações para políticas de DLP

Esta tabela descreve as ações que estão disponíveis no DLP.


|**ação no DLP**|**parâmetros de ação no Microsoft 365 PowerShell**|**tipo de propriedade**|**description**|
|---------|---------|---------|---------|
|Definir cabeçalho|SetHeader|Primeira propriedade: *nome do cabeçalho* </br> Segunda Propriedade: *valor do cabeçalho*|O parâmetro SetHeader especifica uma ação para a regra de DLP que adiciona ou modifica um campo de cabeçalho e um valor no cabeçalho da mensagem. Esse parâmetro usa a sintaxe "HeaderName: HeaderValue". Você pode especificar vários pares de nome de cabeçalho e valor separados por vírgulas|
|Remover cabeçalho| RemoveHeader| Primeira propriedade: *MessageHeaderField*</br> Segunda Propriedade: *String*|  O parâmetro RemoveHeader especifica uma ação para a regra de DLP que remove um campo de cabeçalho do cabeçalho da mensagem. Esse parâmetro usa a sintaxe "HeaderName" ou "HeaderName: HeaderValue". Você pode especificar vários nomes de cabeçalho ou de nome e pares de valores separados por vírgulas|
|Redirecionar a mensagem para usuários específicos|*RedirectMessageTo*|Endereços| Redireciona a mensagem para os destinatários especificados. A mensagem não é entregue aos destinatários originais, e nenhuma notificação é enviada ao remetente ou aos destinatários originais.|
|Encaminhar a mensagem para aprovação ao gerente do remetente| Moderado|Primeira propriedade: *ModerateMessageByManager*</br> Segunda Propriedade: *Boolean*|O parâmetro moderado especifica uma ação para a regra de DLP que envia a mensagem de email para um moderador. Esse parâmetro usa a sintaxe: @ {ModerateMessageByManager = <$true \| $false>;|
|Encaminhar a mensagem para aprovação a aprovadores específicos| Moderado|Primeira propriedade: *ModerateMessageByUser*</br>Segunda Propriedade: *Addresses*|O parâmetro moderado especifica uma ação para a regra de DLP que envia a mensagem de email para um moderador. Esse parâmetro usa a sintaxe: @ {ModerateMessageByUser = @ ("emailaddress1", "emailaddress2",... "EmailAddressN")}|
|Adicionar destinatário|Addrecipients|Primeira propriedade: *Field*</br>Segunda Propriedade: *Addresses*| Adiciona um ou mais destinatários ao campo para/CC/Cco da mensagem. Esse parâmetro usa a sintaxe: @ {<AddToRecipients \| CopyTo \| BlindCopyTo> = "EmailAddress"}|
|Adicionar o gerente do remetente como destinatário|Addrecipients | Primeira propriedade: *AddedManagerAction*</br>Segunda Propriedade: *Field* | Adiciona o gerente do remetente à mensagem como o tipo de destinatário especificado (para, CC, Cco) ou redireciona a mensagem para o gerente do remetente sem notificar o remetente ou o destinatário. Esta ação só funcionará se o atributo do Gerenciador do remetente estiver definido no Active Directory. Este parâmetro usa a sintaxe: @ {AddManagerAsRecipientType = "<para \| CC \| Cco>"}|    
Preceder assunto    |PrependSubject    |String    |Adiciona o texto especificado ao início do campo de assunto da mensagem. Considere usar um espaço ou dois-pontos (:) como o último caractere do texto especificado para diferenciá-lo do texto do assunto original.</br>Para impedir que a mesma cadeia de caracteres seja adicionada a mensagens que já contêm o texto do assunto (por exemplo, respostas), adicione a exceção "a entidade contém palavras" (ExceptIfSubjectContainsWords) à regra.    |
Aplicar isenção de responsabilidade HTML    |ApplyHtmlDisclaimer    |Primeira propriedade: *Text*</br>Segunda Propriedade: *local*</br>Terceira Propriedade: *ação de fallback*    |Aplica o aviso de isenção HTML especificado ao local necessário da mensagem.</br>Esse parâmetro usa a sintaxe: @ {Text = ""; Location = <anexar \|> de preceder; FallbackAction = <disposição \| ignorar \| rejeitar>}




