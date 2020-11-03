---
title: Condições e exceções de política de DLP (versão prévia)
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
ms.openlocfilehash: 2ce49b15bdb13035a37f6895b4b8865b55a62f78
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841464"
---
# <a name="dlp-policy-conditions-and-exceptions-preview"></a>Condições e exceções de política de DLP (versão prévia)

As condições e exceções nas políticas de DLP identificam os itens confidenciais aos quais a política é aplicada. As condições definem o que incluir e exceções definem o que excluir. Para cada condição, há uma exceção correspondente e usam a mesma sintaxe exata.

 A maioria das condições e exceções têm uma propriedade que oferece suporte a um ou mais valores. Por exemplo, se a política de DLP estiver sendo aplicada aos emails do Exchange, a condição **de remetente** será necessária para o remetente da mensagem. Algumas condições têm duas propriedades. Por exemplo, o **cabeçalho de uma mensagem inclui qualquer uma destas palavras** condição requer uma propriedade para especificar o campo de cabeçalho da mensagem e uma segunda propriedade para especificar o texto a ser procurado no campo de cabeçalho. Algumas condições ou exceções não têm propriedades. Por exemplo, o **anexo é uma condição protegida por senha** simplesmente procura anexos em mensagens protegidas por senha.

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condições e exceções para políticas de DLP

As tabelas nas seções a seguir descrevem as condições e exceções disponíveis no DLP.

- [Remetentes](#senders)
- [Destinatários](#recipients)
- [Assunto ou corpo da mensagem](#message-subject-or-body)
- [Anexos](#attachments)
- [Cabeçalhos de mensagem](#message-headers)
- [Propriedades da mensagem](#message-properties)

## <a name="senders"></a>Senders


|**condição ou exceção no DLP**  |**parâmetros de condição/exceção no Microsoft 365 PowerShell** |**tipo de propriedade**  |**description**|
|---------|---------|---------|---------|
|Remetente é |condição: *de* <br/> exceção: *ExceptIfFrom*      |Endereços |     Mensagens enviadas por caixas de correio, usuários de email, contatos de email ou grupos do Microsoft 365 especificados na organização.|
|O endereço IP do remetente é     |condição: *SenderIPRanges*<br/> exceção: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensagens em que o endereço IP do remetente corresponde ao endereço IP especificado ou está dentro do intervalo de endereços IP especificado.       |
|Endereço do remetente contém palavras   | condição: *FromAddressContainsWords* <br/> exceção: *ExceptIfFromAddressContainsWords*        |   Palavras      |   Mensagens que contêm as palavras especificadas no endereço de email do remetente.|
| O endereço do remetente corresponde aos padrões    | condição: *FromAddressMatchesPatterns* <br/> exceção: *ExceptFromAddressMatchesPatterns*       |      Padrões   |  Mensagens em que o endereço de email do remetente contém padrões de texto que correspondem às expressões regulares especificadas.  |
|Domínio do remetente é  |  condição: *SenderDomainIs* <br/> exceção: *ExceptIfSenderDomainIs*       |DomainName         |     Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado. Se você precisar localizar domínios de remetente que *contenham* o domínio especificado (por exemplo, qualquer subdomínio de um domínio), use **a condição endereço do remetente correspondente** ( *FromAddressMatchesPatterns* ) e especifique o domínio usando a sintaxe: ' \. domínio \. com $ '.    |

## <a name="recipients"></a>Destinatários

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell** |    **tipo de propriedade** | **description**|
|---------|---------|---------|---------|
|O destinatário é|  condição: *SentTo* <br/> exceção: *ExceptIfSentTo* | Endereços | Mensagens em que um dos destinatários é a caixa de correio, o usuário de email ou o contato de email especificado na organização. Os destinatários podem estar nos campos **para** , **CC** ou **Cco** da mensagem.|
|O domínio do destinatário é|   condição: *RecipientDomainIs* <br/> exceção: *ExceptIfRecipientDomainIs* |   DomainName |    Mensagens em que o domínio do endereço de email do remetente corresponde ao valor especificado.|
|Endereço do destinatário contém palavras|  condição: *RecipientAddressContainsWords* <br/> exceção: *ExceptIfRecipientAddressContainsWords*|    Palavras|  Mensagens que contêm as palavras especificadas no endereço de email do destinatário. <br/>**Observação** : Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|O endereço do destinatário corresponde aos padrões| condição: *RecipientAddressMatchesPatterns* <br/> exceção: *ExceptIfRecipientAddressMatchesPatterns*|   Padrões    |Mensagens em que o endereço de email de um destinatário contém padrões de texto que correspondem às expressões regulares especificadas. <br/> **Observação** : Essa condição não considera mensagens que são enviadas a endereços proxy de destinatários. Ela só faz a correspondência de mensagens que são enviadas ao endereço de email principal do destinatário.|
|Enviado para o membro de| condição: *SentToMemberOf* <br/> exceção: *ExceptIfSentToMemberOf*|  Endereços|  Mensagens que contêm destinatários que são membros do grupo de distribuição especificado, grupo de segurança habilitado para email ou grupo do Microsoft 365. O grupo pode estar nos campos **para** , **CC** ou **Cco** da mensagem.|

## <a name="message-subject-or-body"></a>Assunto ou corpo da mensagem

|**condição ou exceção no DLP** | **parâmetros de condição/exceção no Microsoft 365 PowerShell** |**tipo de propriedade**| **description**|
|---------|---------|---------|---------|
|O assunto contém palavras ou frases| condição: *SubjectContainsWords* <br/> exceção: *ExceptIf SubjectContainsWords*| Palavras   |Mensagens com as palavras especificadas no campo assunto.|
|Assunto corresponde a padrões|condição: *SubjectMatchesPatterns* <br/> exceção: *ExceptIf SubjectMatchesPatterns*|Padrões   |Mensagens em que o campo assunto contém padrões de texto que correspondem às expressões regulares especificadas.|
|Conteúdo contém|  condição: *ContentContainsSensitiveInformation* <br/> exceção *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensagens ou documentos que contêm informações confidenciais, conforme definido pelas políticas de prevenção de perda de dados (DLP).|


## <a name="attachments"></a>Attachments

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|O anexo é protegido por senha|condição: *DocumentIsPasswordProtected* <br/> exceção: *ExceptIfDocumentIsPasswordProtected*|none| Mensagens em que um anexo está protegido por senha (e, portanto, não pode ser verificado). A detecção de senha só funciona para documentos do Office e arquivos. zip.|
|A extensão do arquivo do anexo é|condição: *ContentExtensionMatchesWords* <br/> exceção: *ExceptIfContentExtensionMatchesWords*|  Palavras   |Mensagens em que a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O conteúdo de qualquer anexo de email não pôde ser verificado|condição: *DocumentIsUnsupported* <br/>exceção: *ExceptIf DocumentIsUnsupported*|   n/d|    Mensagens em que um anexo não é reconhecido nativamente pelo Exchange Online.|
|O conteúdo de qualquer anexo de email não concluiu a verificação|   condição: *ProcessingLimitExceeded* <br/> exceção: *ExceptIfProcessingLimitExceeded*|    n/d |Mensagens em que o mecanismo de regras não pôde concluir a verificação dos anexos. Você pode usar essa condição para criar regras que trabalham juntas para identificar e processar mensagens em que o conteúdo não pôde ser totalmente verificado.|
|O nome do documento contém palavras|condição: *DocumentNameMatchesWords* <br/> exceção: *ExceptIfDocumentNameMatchesWords* |Palavras  |Mensagens em que o nome de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O nome do documento corresponde aos padrões|condição: *DocumentNameMatchesPatterns* <br/> exceção: *ExceptIfDocumentNameMatchesPatterns*|    Padrões    |Mensagens em que o nome de arquivo de um anexo contém padrões de texto que correspondem às expressões regulares especificadas.|
|A propriedade do documento é|condição: *ContentPropertyContainsWords* <br/> exceção: *ExceptIfContentPropertyContainsWords* |Palavras| Mensagens ou documentos onde a extensão de arquivo de um anexo corresponde a qualquer uma das palavras especificadas.|
|O tamanho do documento é igual a ou maior que| condição: *DocumentSizeOver* <br/> exceção: *ExceptIfDocumentSizeOver*|    Size    |Mensagens em que qualquer anexo é maior ou igual ao valor especificado.|

## <a name="message-headers"></a>Cabeçalhos de mensagem

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**|  **description**|
|---------|---------|---------|---------|
|Cabeçalho contém palavras ou frases|condição: *HeaderContainsWords* <br/> exceção: *ExceptIfHeaderContainsWords*|  Tabela de hash  |Mensagens que contêm o campo de cabeçalho especificado e o valor desse campo de cabeçalho contém as palavras especificadas.|
|Cabeçalho corresponde a padrões|   condição: *HeaderMatchesPatterns* <br/> exceção: *ExceptIfHeaderMatchesPatterns*|    Tabela de hash  |Mensagens que contêm o campo de cabeçalho especificado e o valor desse campo de cabeçalho contém as expressões regulares especificadas.|

## <a name="message-properties"></a>Propriedades da mensagem

|**condição ou exceção no DLP**| **parâmetros de condição/exceção no Microsoft 365 PowerShell**| **tipo de propriedade**   |**description**|
|---------|---------|---------|---------|
|Tamanho da mensagem sobre|condição: *MessageSizeOver* <br/> exceção: *ExceptIfMessageSizeOver*| Size    |Mensagens em que o tamanho total (mensagem mais anexos) é maior ou igual ao valor especificado. <br/>**Observação** : os limites de tamanho de mensagem nas caixas de correio são avaliados antes das regras de fluxo de email. Uma mensagem muito grande para uma caixa de correio será rejeitada antes que uma regra com essa condição seja capaz de atuar na mensagem.|

