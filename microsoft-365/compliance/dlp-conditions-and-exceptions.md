---
title: Condições, exceções e ações da política de DLP (visualização)
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
description: saiba mais sobre condições e exceções de política dlp
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604211"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>Condições, exceções e ações da política de DLP (visualização)

Condições e exceções em políticas DLP identificam itens confidenciais aos quais a política é aplicada. Ações definem o que acontece como consequência de uma condição de exceção ser atendida.

- Condições definem o que incluir
- As exceções definem o que excluir.
- Ações definem o que acontece como consequência da condição ou exceção sendo atendida
 
A maioria das condições e exceções tem uma propriedade que oferece suporte a um ou mais valores. Por exemplo, se a política de DLP estiver  sendo aplicada a emails do Exchange, a condição do remetente exigirá o remetente da mensagem. Algumas condições têm duas propriedades. Por exemplo, o **header A** de mensagem inclui qualquer uma dessas palavras, que exige uma propriedade para especificar o campo de header da mensagem e uma segunda propriedade para especificar o texto a ser buscado no campo de texto. Algumas condições ou exceções não têm propriedades. Por exemplo, o **Anexo é uma** condição protegida por senha simplesmente procura por anexos em mensagens protegidas por senha.

As ações normalmente exigem propriedades adicionais. Por exemplo, quando a regra de política de DLP redireciona uma mensagem, você precisa especificar para onde a mensagem é redirecionada. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condições e exceções para políticas DLP

As tabelas nas seções a seguir descrevem as condições e exceções disponíveis na DLP.

- [Remetentes](#senders)
- [Destinatários](#recipients)
- [Assunto ou corpo da mensagem](#message-subject-or-body)
- [Anexos](#attachments)
- [Headers de mensagem](#message-headers)
- [Propriedades da mensagem](#message-properties)

### <a name="senders"></a>Senders


|**condição ou exceção em DLP**  |**parâmetros de condição/exceção no Microsoft 365 PowerShell** |**tipo de propriedade**  |**description**|
|---------|---------|---------|---------|
|O remetente é |condição: *From* <br/> exceção: *ExceptIfFrom*      |Endereços |     Mensagens enviadas pelas caixas de correio especificadas, usuários de email, contatos de email ou grupos do Microsoft 365 na organização.|
|O endereço IP do remetente é     |condição: *SenderIPRanges*<br/> exceção: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensagens em que o endereço IP do remetente corresponde ao endereço IP especificado ou se enquadra no intervalo de endereços IP especificado.       |
|O endereço do remetente contém palavras   | condição: *FromAddressContainsWords* <br/> exceção: *ExceptIfFromAddressContainsWords*        |   Palavras      |   Mensagens que contêm as palavras especificadas no endereço de email do remetente.|
| O endereço do remetente corresponde a padrões    | condição: *FromAddressMatchesPatterns* <br/> exceção: *ExceptFromAddressMatchesPatterns*       |      Padrões   |  Mensagens em que o endereço de email do remetente contém padrões de texto que corresponderem às expressões regulares especificadas.  |
|O domínio do remetente é  |  condição: *SenderDomainIs* <br/> exceção: *ExceptIfSenderDomainIs*       |DomainName         |     Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado. Se você precisar encontrar domínios  de remetente que contenham o domínio especificado (por exemplo, qualquer subdomínio de um domínio), use a condição *DeAddressMatchesPatterns ( Sender AddressMatchesPatterns)* e especifique o domínio usando a sintaxe: '  \. domain \. com$'.    |
|Escopo do remetente    | condição: *FromScope* <br/> exceção: *ExceptIfFromScope*    | UserScopeFrom    |    Mensagens enviadas por remententes internos ou externos.    |

### <a name="recipients"></a>Destinatários

|**condição ou exceção em DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell** |    **tipo de propriedade** | **description**|
|---------|---------|---------|---------|
|O destinatário é|  condição: *SentTo* <br/> exceção: *ExceptIfSentTo* | Endereços | Mensagens em que um dos destinatários é a caixa de correio especificada, o usuário de email ou o contato de email na organização. Os destinatários podem estar nos campos **Para**, **Cc** ou **Cc** da mensagem.|
|O domínio do destinatário é|   condição: *RecipientDomainIs* <br/> exceção: *ExceptIfRecipientDomainIs* |   DomainName |    Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado.|
|O endereço do destinatário contém palavras|  condição: *RecipientAddressContainsWords* <br/> exceção: *ExceptIfRecipientAddressContainsWords*|    Palavras|  Mensagens que contêm as palavras especificadas no endereço de email do destinatário. <br/>**Observação**: Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|O endereço do destinatário corresponde a padrões| condição: *RecipientAddressMatchesPatterns* <br/> exceção: *ExceptIfRecipientAddressMatchesPatterns*|   Padrões    |Mensagens em que o endereço de email de um destinatário contém padrões de texto que corresponderem às expressões regulares especificadas. <br/> **Observação**: Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|Enviado para membro de| condição: *SentToMemberOf* <br/> exceção: *ExceptIfSentToMemberOf*|  Endereços|  Mensagens que contêm destinatários que são membros do grupo de distribuição especificado, grupo de segurança habilitado para email ou grupo do Microsoft 365. O grupo pode estar nos **campos Para**, **Cc** ou **Cc** da mensagem.|

### <a name="message-subject-or-body"></a>Assunto ou corpo da mensagem

|**condição ou exceção em DLP** | **parâmetros de condição/exceção no Microsoft 365 PowerShell** |**tipo de propriedade**| **description**|
|---------|---------|---------|---------|
|O assunto contém palavras ou frases| condição: *SubjectContainsWords* <br/> exceção: *ExceptIf SubjectContainsWords*| Palavras   |Mensagens com as palavras especificadas no campo Assunto.|
|O assunto corresponde a padrões|condição: *SubjectMatchesPatterns* <br/> exceção: *ExceptIf SubjectMatchesPatterns*|Padrões   |Mensagens em que o campo Assunto contém padrões de texto que corresponderem às expressões regulares especificadas.|
|O conteúdo contém|  condição: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensagens ou documentos que contenham informações confidenciais conforme definido pelas políticas de prevenção contra perda de dados (DLP).|
| Assunto ou corpo corresponde ao padrão    | condição: *SubjectOrBodyMatchesPatterns* <br/> exceção: *ExceptIfSubjectOrBodyMatchesPatterns*    | Padrões    | Mensagens em que o campo de assunto ou o corpo da mensagem contém padrões de texto que corresponderem às expressões regulares especificadas.    |
| Assunto ou Corpo contém palavras    | condição: *SubjectOrBodyContainsWords* <br/> exceção: *ExceptIfSubjectOrBodyContainsWords*    | Palavras    | Mensagens com as palavras especificadas no campo de assunto ou no corpo da mensagem    |


### <a name="attachments"></a>Attachments

|**condição ou exceção em DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|O anexo é protegido por senha|condição: *DocumentIsPasswordProtected* <br/> exceção: *ExceptIfDocumentIsPasswordProtected*|nenhum| Mensagens em que um anexo está protegido por senha (e, portanto, não podem ser verificados). A detecção de senha só funciona para documentos do Office, arquivos .zip e arquivos .7z.|
|A extensão de arquivo do anexo é|condição: *ContentExtensionMatchesWords* <br/> exceção: *ExceptIfContentExtensionMatchesWords*|  Palavras   |Mensagens em que a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O conteúdo de qualquer anexo de email não pôde ser verificado|condição: *DocumentIsUnsupported* <br/>exceção: *ExceptIf DocumentIsUnsupported*|   n/d|    Mensagens em que um anexo não é reconhecido na verdade pelo Exchange Online.|
|O conteúdo de qualquer anexo de email não concluiu a verificação|   condição: *ProcessingLimitExceeded* <br/> exceção: *ExceptIfProcessingLimitExceeded*|    n/d |Mensagens em que o mecanismo de regras não pôde concluir a verificação dos anexos. Você pode usar essa condição para criar regras que funcionam em conjunto para identificar e processar mensagens em que o conteúdo não pôde ser completamente verificado.|
|O nome do documento contém palavras|condição: *DocumentNameMatchesWords* <br/> exceção: *ExceptIfDocumentNameMatchesWords* |Palavras  |Mensagens em que o nome de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O nome do documento corresponde a padrões|condição: *DocumentNameMatchesPatterns* <br/> exceção: *ExceptIfDocumentNameMatchesPatterns*|    Padrões    |Mensagens em que o nome do arquivo de um anexo contém padrões de texto que corresponderem às expressões regulares especificadas.|
|A propriedade do documento é|condição: *ContentPropertyContainsWords* <br/> exceção: *ExceptIfContentPropertyContainsWords* |Palavras| Mensagens ou documentos em que a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O tamanho do documento é igual ou maior que| condição: *DocumentSizeOver* <br/> exceção: *ExceptIfDocumentSizeOver*|    Size    |Mensagens em que qualquer anexo é maior ou igual ao valor especificado.|

### <a name="message-headers"></a>Message Headers

|**condição ou exceção em DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**|  **description**|
|---------|---------|---------|---------|
|O header contém palavras ou frases|condição: *HeaderContainsWords* <br/> exceção: *ExceptIfHeaderContainsWords*|  Tabela hash  |As mensagens que contêm o campo de cabeça especificado e o valor desse campo de header contêm as palavras especificadas.|
|O header corresponde a padrões|   condição: *HeaderMatchesPatterns* <br/> exceção: *ExceptIfHeaderMatchesPatterns*|    Tabela hash  |As mensagens que contêm o campo de cabeça especificado e o valor desse campo de header contêm as expressões regulares especificadas.|

### <a name="message-properties"></a>Propriedades da mensagem

|**condição ou exceção em DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|Tamanho da mensagem acima|condição: *MessageSizeOver* <br/> exceção: *ExceptIfMessageSizeOver*| Size    |Mensagens em que o tamanho total (mensagem mais anexos) é maior ou igual ao valor especificado. <br/>**Observação:** os limites de tamanho de mensagem em caixas de correio são avaliados antes das regras de fluxo de emails. Uma mensagem muito grande para uma caixa de correio será rejeitada antes que uma regra com essa condição possa agir sobre a mensagem.|
| Com importância    | condição: *WithImportance* <br/> exceção: *ExceptIfWithImportance*    | Importance    | Mensagens marcadas com o nível de importância especificado.    |
| O conjunto de caracteres de conteúdo contém palavras    | condição: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Mensagens que têm qualquer um dos nomes de conjunto de caracteres especificados.    |
| Tem substituição de remetente    | condição: *HasSenderOverride* <br/> exceção: *ExceptIfHasSenderOverride*    | n/d    | Mensagens em que o remetente optou por substituir uma política de prevenção de perda de dados (DLP). Para obter mais informações sobre políticas DLP, consulte [Prevenção contra perda de dados.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)   |
| O tipo de mensagem corresponde    | condição: *MessageTypeMatches* <br/> exceção: *ExceptIfMessageTypeMatches*    | MessageType    | Mensagens do tipo especificado.    |

## <a name="actions-for-dlp-policies"></a>Ações para políticas DLP

Esta tabela descreve as ações que estão disponíveis na DLP.


|**ação na DLP**|**parâmetros de ação no Microsoft 365 PowerShell**|**tipo de propriedade**|**description**|
|---------|---------|---------|---------|
|Definir o header|SetHeader|Primeira propriedade: *Nome do Header* </br> Segunda propriedade: *Header Value*|O parâmetro SetHeader especifica uma ação para a regra de DLP que adiciona ou modifica um campo de header e um valor no header da mensagem. Esse parâmetro usa a sintaxe "HeaderName:HeaderValue". Você pode especificar vários nomes de header e pares de valores separados por vírgulas|
|Remover o header| RemoveHeader| Primeira propriedade: *MessageHeaderField*</br> Segunda propriedade: *String*|  O parâmetro RemoveHeader especifica uma ação para a regra de DLP que remove um campo de header do header da mensagem. Esse parâmetro usa a sintaxe "HeaderName" ou "HeaderName:HeaderValue". Você pode especificar vários nomes de header ou nomes de cabeça e pares de valores separados por vírgulas|
|Redirecionar a mensagem para usuários específicos|*RedirectMessageTo*|Endereços| Redireciona a mensagem para os destinatários especificados. A mensagem não é entregue aos destinatários originais, e nenhuma notificação é enviada ao remetente ou aos destinatários originais.|
|Encaminhar a mensagem para aprovação ao gerente do remetente| Moderado|Primeira propriedade: *ModerateMessageByManager*</br> Segunda propriedade: *Boolean*|O parâmetro Moderate especifica uma ação para a regra de DLP que envia a mensagem de email para um moderador. Esse parâmetro usa a sintaxe: @{ModerateMessageByManager = <$true \| $false>;|
|Encaminhar a mensagem para aprovação a aprovadores específicos| Moderado|Primeira propriedade: *ModerateMessageByUser*</br>Segunda propriedade: *Addresses*|O parâmetro Moderate especifica uma ação para a regra de DLP que envia a mensagem de email para um moderador. Este parâmetro usa a sintaxe: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Adicionar destinatário|AddRecipients|Primeira propriedade: *Field*</br>Segunda propriedade: *Addresses*| Adiciona um ou mais destinatários ao campo Para/Cc/Cc da mensagem. Este parâmetro usa a sintaxe: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Adicionar o gerente do remetente como destinatário|AddRecipients | Primeira propriedade: *AddedManagerAction*</br>Segunda propriedade: *Field* | Adiciona o gerente do remetente à mensagem como o tipo de destinatário especificado ( Para, Cc, Cc ) ou redireciona a mensagem para o gerente do remetente sem notificar o remetente ou o destinatário. Essa ação só funcionará se o atributo Manager do remetente for definido no Active Directory. Este parâmetro usa a sintaxe: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Pré-anexar assunto    |PrependSubject    |Cadeia de caracteres    |Adiciona o texto especificado ao início do campo Assunto da mensagem. Considere usar um espaço ou dois-pontos (:) como o último caractere do texto especificado para diferenciá-lo do texto de assunto original.</br>Para impedir que a mesma cadeia de caracteres seja adicionada a mensagens que já contêm o texto no assunto (por exemplo, respostas), adicione a exceção "O assunto contém palavras" (ExceptIfSubjectContainsWords) à regra.    |
Aplicar aviso de isenção de responsabilidade html    |ApplyHtmlDisclaimer    |Primeira propriedade: *Text*</br>Segunda propriedade: *Location*</br>Terceira propriedade: *ação de fallback*    |Aplica o aviso de isenção de responsabilidade HTML especificado ao local necessário da mensagem.</br>Este parâmetro usa a sintaxe: @{ Text = " " ; Local = <\| anexar>; FallbackAction = <Wrap \| Ignore \| Reject> }




