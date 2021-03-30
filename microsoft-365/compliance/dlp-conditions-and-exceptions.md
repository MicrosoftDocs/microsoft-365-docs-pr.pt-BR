---
title: Condições de política de DLP, exceções e ações
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
description: saiba mais sobre as condições e exceções da política dlp
ms.openlocfilehash: cf9bc4ea220c319233a5eaec09352045190883e2
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418017"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>Condições de política de DLP, exceções e ações

As condições e exceções nas políticas DLP identificam itens confidenciais aos quais a política é aplicada. As ações definem o que acontece como consequência de uma condição de exceção sendo atendida.

- Condições definem o que incluir
- As exceções definem o que excluir.
- Ações definem o que acontece como consequência da condição ou exceção que está sendo atendida
 
A maioria das condições e exceções tem uma propriedade que dá suporte a um ou mais valores. Por exemplo, se a política de DLP estiver  sendo aplicada aos emails do Exchange, a condição O remetente é exigirá o remetente da mensagem. Algumas condições têm duas propriedades. Por exemplo, **o header A** message inclui qualquer uma dessas condições de palavras que exige uma propriedade para especificar o campo de header da mensagem e uma segunda propriedade para especificar o texto a ser buscado no campo de header. Algumas condições ou exceções não têm nenhuma propriedade. Por exemplo, **a condição Attachment é protegida por senha** simplesmente procura anexos em mensagens protegidas por senha.

As ações normalmente exigem propriedades adicionais. Por exemplo, quando a regra de política de DLP redireciona uma mensagem, você precisa especificar para onde a mensagem é redirecionada. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condições e exceções para políticas de DLP

As tabelas nas seções a seguir descrevem as condições e exceções disponíveis na DLP.

- [Remetentes](#senders)
- [Destinatários](#recipients)
- [Assunto ou corpo da mensagem](#message-subject-or-body)
- [Anexos](#attachments)
- [Headers de mensagem](#message-headers)
- [Propriedades da mensagem](#message-properties)

### <a name="senders"></a>Senders


|**condição ou exceção em DLP**  |**parâmetros condition/exception no Microsoft 365 PowerShell** |**tipo de propriedade**  |**description**|
|---------|---------|---------|---------|
|Remetente é |condição: *From* <br/> exception: *ExceptIfFrom*      |Endereços |     Mensagens enviadas pelas caixas de correio especificadas, usuários de email, contatos de email ou grupos do Microsoft 365 na organização.|
|O endereço IP do remetente é     |condição: *SenderIPRanges*<br/> exceção: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensagens em que o endereço IP do remetente corresponde ao endereço IP especificado ou se enquadram no intervalo de endereços IP especificado.       |
|Endereço do remetente contém palavras   | condição: *FromAddressContainsWords* <br/> exception: *ExceptIfFromAddressContainsWords*        |   Palavras      |   Mensagens que contêm as palavras especificadas no endereço de email do remetente.|
| Endereço de remetente corresponde a padrões    | condição: *FromAddressMatchesPatterns* <br/> exceção: *ExceptFromAddressMatchesPatterns*       |      Padrões   |  Mensagens em que o endereço de email do remetente contém padrões de texto que combinam com as expressões regulares especificadas.  |
|O domínio do remetente é  |  condição: *SenderDomainIs* <br/> exception: *ExceptIfSenderDomainIs*       |DomainName         |     Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado. Se você precisar encontrar domínios  de remetente que contenham o domínio especificado (por exemplo, qualquer subdomínio de um domínio), use a condição *DeAddressMatchesPatterns* do endereço do remetente e especifique o domínio usando a sintaxe: ' \. domain \. com$'.    |
|Escopo do remetente    | condição: *FromScope* <br/> exception: *ExceptIfFromScope*    | UserScopeFrom    |    Mensagens enviadas por senders internos ou externos.    |
|As propriedades especificadas do remetente incluem qualquer uma destas palavras|condição: *SenderADAttributeContainsWords* <br/> exceção: *ExceptIfSenderADAttributeContainsWords*|Primeira propriedade: `ADAttribute` <p> Segunda propriedade: `Words`|Mensagens onde o atributo Do Active Directory especificado do remetente contém qualquer uma das palavras especificadas.|
|As propriedades especificadas do remetente correspondem a estes padrões de texto|condição: *SenderADAttributeMatchesPatterns* <br/> exceção: *ExceptIfSenderADAttributeMatchesPatterns*|Primeira propriedade: `ADAttribute` <p> Segunda propriedade: `Patterns`|Mensagens em que o atributo Do Active Directory especificado do remetente contém padrões de texto que corresponderem às expressões regulares especificadas.|

### <a name="recipients"></a>Recipients

|**condição ou exceção em DLP**| **parâmetros condition/exception no Microsoft 365 PowerShell** |    **tipo de propriedade** | **description**|
|---------|---------|---------|---------|
|O destinatário é|  condição: *SentTo* <br/> exception: *ExceptIfSentTo* | Endereços | Mensagens em que um dos destinatários é a caixa de correio, o usuário de email ou o contato de email especificado na organização. Os destinatários podem estar nos campos **Para,** **Cc** ou **Cc** da mensagem.|
|O domínio do destinatário é|   condição: *RecipientDomainIs* <br/> exception: *ExceptIfRecipientDomainIs* |   DomainName |    Mensagens em que o domínio do endereço de email do destinatário corresponde ao valor especificado.|
|Endereço de destinatário contém palavras|  condição: *AnyOfRecipientAddressContainsWords* <br/> exception: *ExceptIfAnyOfRecipientAddressContainsWords*|  Palavras|  Mensagens que contêm as palavras especificadas no endereço de email do destinatário. <br/>**Observação**: Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|Endereço de destinatário corresponde a padrões| condição: *AnyOfRecipientAddressMatchesPatterns* <br/> exceção: *ExceptIfAnyOfRecipientAddressMatchesPatterns*| Padrões    |Mensagens em que o endereço de email de um destinatário contém padrões de texto que corresponderem às expressões regulares especificadas. <br/> **Observação**: Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|Enviado para membro do| condição: *SentToMemberOf* <br/> exception: *ExceptIfSentToMemberOf*|  Endereços|  Mensagens que contêm destinatários que são membros do grupo de distribuição especificado, grupo de segurança habilitado para email ou grupo do Microsoft 365. O grupo pode estar nos campos **Para,** **Cc** ou **Cc** da mensagem.|

### <a name="message-subject-or-body"></a>Assunto ou corpo da mensagem

|**condição ou exceção em DLP** | **parâmetros condition/exception no Microsoft 365 PowerShell** |**tipo de propriedade**| **description**|
|---------|---------|---------|---------|
|Subject contém palavras ou frases| condição: *SubjectContainsWords* <br/> exception: *ExceptIf SubjectContainsWords*| Palavras   |Mensagens que têm as palavras especificadas no campo Assunto.|
|Subject corresponde a padrões|condição: *SubjectMatchesPatterns* <br/> exception: *ExceptIf SubjectMatchesPatterns*|Padrões   |Mensagens onde o campo Assunto contém padrões de texto que corresponderem às expressões regulares especificadas.|
|Conteúdo contém|  condição: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensagens ou documentos que contêm informações confidenciais conforme definido pelas políticas de prevenção contra perda de dados (DLP).|
| Subject ou Body corresponde ao padrão    | condição: *SubjectOrBodyMatchesPatterns* <br/> exceção: *ExceptIfSubjectOrBodyMatchesPatterns*    | Padrões    | Mensagens onde o campo de assunto ou o corpo da mensagem contém padrões de texto que corresponderem às expressões regulares especificadas.    |
| Assunto ou Corpo contém palavras    | condição: *SubjectOrBodyContainsWords* <br/> exceção: *ExceptIfSubjectOrBodyContainsWords*    | Palavras    | Mensagens que têm as palavras especificadas no campo assunto ou no corpo da mensagem    |


### <a name="attachments"></a>Attachments

|**condição ou exceção em DLP**| **parâmetros condition/exception no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|O anexo é protegido por senha|condição: *DocumentIsPasswordProtected* <br/> exception: *ExceptIfDocumentIsPasswordProtected*|nenhuma| Mensagens em que um anexo está protegido por senha (e, portanto, não podem ser verificados). A detecção de senha só funciona para documentos do Office, arquivos .zip e arquivos .7z.|
|Extensão de arquivo do anexo é|condição: *ContentExtensionMatchesWords* <br/> exception: *ExceptIfContentExtensionMatchesWords*|  Palavras   |Mensagens em que a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O conteúdo de qualquer anexo de email não pôde ser verificado|condição: *DocumentIsUnsupported* <br/>exception: *ExceptIf DocumentIsUnsupported*|   n/d|    Mensagens em que um anexo não é reconhecido na verdade pelo Exchange Online.|
|O conteúdo de qualquer anexo de email não concluiu a verificação|   condição: *ProcessingLimitExceeded* <br/> exceção: *ExceptIfProcessingLimitExceeded*|    n/d |Mensagens em que o mecanismo de regras não pôde concluir a verificação dos anexos. Você pode usar essa condição para criar regras que funcionam em conjunto para identificar e processar mensagens em que o conteúdo não pôde ser totalmente verificado.|
|Nome do documento contém palavras|condição: *DocumentNameMatchesWords* <br/> exception: *ExceptIfDocumentNameMatchesWords* |Palavras  |Mensagens em que o nome de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|Nome do documento corresponde a padrões|condição: *DocumentNameMatchesPatterns* <br/> exception: *ExceptIfDocumentNameMatchesPatterns*|    Padrões    |Mensagens em que o nome de arquivo de um anexo contém padrões de texto que corresponderem às expressões regulares especificadas.|
|A propriedade do documento é|condição: *ContentPropertyContainsWords* <br/> exceção: *ExceptIfContentPropertyContainsWords* |Palavras| Mensagens ou documentos em que a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|Tamanho do documento é igual ou maior do que| condição: *DocumentSizeOver* <br/> exception: *ExceptIfDocumentSizeOver*|    Size    |Mensagens em que qualquer anexo é maior ou igual ao valor especificado.|
|O conteúdo de qualquer anexo inclui qualquer uma dessas palavras| condição: *DocumentContainsWords* <br/> exception: *ExceptIfDocumentContainsWords* |`Words`|Mensagens em que um anexo contém as palavras especificadas.|
|Qualquer conteúdo de anexo corresponde a esses padrões de texto|condição: *DocumentMatchesPatterns* <br/> exception: *ExceptIfDocumentMatchesPatterns* |`Patterns`|Mensagens em que um anexo contém padrões de texto que corresponderem às expressões regulares especificadas. |

### <a name="message-headers"></a>Headers de mensagem

|**condição ou exceção em DLP**| **parâmetros condition/exception no Microsoft 365 PowerShell**| **tipo de propriedade**|  **description**|
|---------|---------|---------|---------|
|O header contém palavras ou frases|condição: *HeaderContainsWords* <br/> exceção: *ExceptIfHeaderContainsWords*|  Tabela hash  |As mensagens que contêm o campo de header especificado e o valor desse campo de header contêm as palavras especificadas.|
|O header corresponde aos padrões|   condição: *HeaderMatchesPatterns* <br/> exceção: *ExceptIfHeaderMatchesPatterns*|    Tabela hash  |As mensagens que contêm o campo de header especificado e o valor desse campo de header contêm as expressões regulares especificadas.|

### <a name="message-properties"></a>Propriedades da mensagem

|**condição ou exceção em DLP**| **parâmetros condition/exception no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
| Com importância    | condição: *WithImportance* <br/> exception: *ExceptIfWithImportance*    | Importance    | Mensagens marcadas com o nível de importância especificado.    |
| Conjunto de caracteres de conteúdo contém palavras    | condição: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Mensagens que têm qualquer um dos nomes de conjunto de caracteres especificados.    |
| Tem substituição de remetente    | condição: *HasSenderOverride* <br/> exception: *ExceptIfHasSenderOverride*    | n/d    | Mensagens em que o remetente optou por substituir uma política de prevenção contra perda de dados (DLP). Para obter mais informações sobre políticas de DLP, consulte [Prevenção contra perda de dados](./data-loss-prevention-policies.md).   |
| Tipo de mensagem corresponde    | condição: *MessageTypeMatches* <br/> exception: *ExceptIfMessageTypeMatches*    | MessageType    | Mensagens do tipo especificado.    |
|O tamanho da mensagem é maior ou igual a| condição: *MessageSizeOver* <br/> exception: *ExceptIfMessageSizeOver* |`Size`|Mensagens em que o tamanho total (mensagem mais anexos) é maior ou igual ao valor especificado. **Observação:** os limites de tamanho da mensagem em caixas de correio são avaliados antes das regras de fluxo de emails. Uma mensagem muito grande para uma caixa de correio será rejeitada antes que uma regra com essa condição seja capaz de agir na mensagem.|

## <a name="actions-for-dlp-policies"></a>Ações para políticas DLP

Esta tabela descreve as ações que estão disponíveis na DLP.


|**ação em DLP**|**parâmetros de ação no Microsoft 365 PowerShell**|**tipo de propriedade**|**description**|
|---------|---------|---------|---------|
|Definir o header|SetHeader|Primeira propriedade: *Nome do Header* </br> Segunda propriedade: *Valor do Header*|O parâmetro SetHeader especifica uma ação para a regra DLP que adiciona ou modifica um campo de header e um valor no header da mensagem. Este parâmetro usa a sintaxe "HeaderName:HeaderValue". Você pode especificar vários pares de nome de header e valor separados por vírgulas|
|Remover o header| RemoveHeader| Primeira propriedade: *MessageHeaderField*</br> Segunda propriedade: *String*|  O parâmetro RemoveHeader especifica uma ação para a regra DLP que remove um campo de header do header da mensagem. Este parâmetro usa a sintaxe "HeaderName" ou "HeaderName:HeaderValue". Você pode especificar vários nomes de header ou nomes de header e pares de valores separados por vírgulas|
|Redirecionar a mensagem para usuários específicos|*RedirectMessageTo*|Endereços| Redireciona a mensagem para os destinatários especificados. A mensagem não é entregue aos destinatários originais, e nenhuma notificação é enviada ao remetente ou aos destinatários originais.|
|Encaminhar a mensagem para aprovação ao gerente do remetente| Moderado|Primeira propriedade: *ModerateMessageByManager*</br> Segunda propriedade: *Boolean*|O parâmetro Moderate especifica uma ação para a regra DLP que envia a mensagem de email para um moderador. Este parâmetro usa a sintaxe: @{ModerateMessageByManager = <$true \| $false>;|
|Encaminhar a mensagem para aprovação para aprovações específicas| Moderado|Primeira propriedade: *ModerateMessageByUser*</br>Segunda propriedade: *Endereços*|O parâmetro Moderate especifica uma ação para a regra DLP que envia a mensagem de email para um moderador. Este parâmetro usa a sintaxe: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Adicionar destinatário|AddRecipients|Primeira propriedade: *Field*</br>Segunda propriedade: *Endereços*| Adiciona um ou mais destinatários ao campo To/Cc/Bcc da mensagem. Este parâmetro usa a sintaxe: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Adicionar o gerente do remetente como destinatário|AddRecipients | Primeira propriedade: *AddedManagerAction*</br>Segunda propriedade: *Field* | Adiciona o gerente do remetente à mensagem como o tipo de destinatário especificado ( Para, Cc, Cc ) ou redireciona a mensagem para o gerente do remetente sem notificar o remetente ou o destinatário. Essa ação só funcionará se o atributo Manager do remetente for definido no Active Directory. Este parâmetro usa a sintaxe: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Assunto prepend    |PrependSubject    |String    |Adiciona o texto especificado ao início do campo Assunto da mensagem. Considere usar um espaço ou dois pontos (:) como o último caractere do texto especificado para diferenciá-lo do texto de assunto original.</br>Para impedir que a mesma cadeia de caracteres seja adicionada a mensagens que já contenham o texto no assunto (por exemplo, respostas), adicione a exceção "O assunto contém palavras" (ExceptIfSubjectContainsWords) à regra.    
|Aplicar aviso de isenção de responsabilidade HTML    |AplicarHtmlDisclaimer    |Primeira propriedade: *Text*</br>Segunda propriedade: *Location*</br>Terceira propriedade: *ação fallback*    |Aplica o aviso de isenção de responsabilidade HTML especificado ao local necessário da mensagem.</br>Este parâmetro usa a sintaxe: @{ Text = " " ; Location = <Append \| Prepend>; FallbackAction = <Wrap \| Ignore \| Reject> }
|Remover a Criptografia de Mensagens do Office 365 e a proteção de direitos    | RemoveRMSTemplate | n/d| Remove a criptografia do Office 365 aplicada em um email|
