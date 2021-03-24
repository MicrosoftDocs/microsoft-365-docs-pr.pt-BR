---
title: Regras de fluxo de emails no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Você pode usar regras de fluxo de emails (regras de transporte) para identificar e tomar medidas em mensagens que fluem pela sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ff4c723d0c7d8bba2e24ece1b62007f14198e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054149"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>Regras de fluxo de email (regras de transporte) no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar regras de fluxo de emails (também conhecidas como regras de transporte) para identificar e tomar medidas em mensagens que fluem pela sua organização.

Este tópico explica os componentes das regras de fluxo de emails e como elas funcionam.

Para etapas para criar, copiar e gerenciar regras de fluxo de emails, consulte [Gerenciar regras de fluxo](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)de emails no Exchange Online . Você pode impor e testar cada regra ou testar e notificar o remetente. Para saber mais sobre as opções de teste, consulte [Test mail flow rules](/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) and Policy Tips in Exchange [Online](/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Para relatórios resumidos e detalhados sobre mensagens que corresponderam às regras de fluxo de emails, consulte Use mail protection reports to view data [about malware, spam, and rule detections](/exchange/monitoring/use-mail-protection-reports).

Para implementar políticas de mensagens específicas usando regras do fluxo de emails, confira estes tópicos:

- [Usar regras de fluxo de emails para inspecionar anexos de mensagens no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Configure a criptografia no Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Avisos de isenção de responsabilidade de mensagens em toda a organização, assinaturas, rodapés ou headers no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Criar listas de remetentes de bloco no EOP](create-block-sender-lists-in-office-365.md)

- [Redução de ameaças de malware com o bloqueio de anexos de arquivo no Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definir regras para criptografar ou descriptografar mensagens de email no Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

O vídeo a seguir fornece uma demonstração de configuração de regras de fluxo de emails no EOP autônomo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Componentes de regra de fluxo de email

Um regra de fluxo de emails é formada por condições, exceções, ações e propriedades:

- **Condições**: Identifique as mensagens às quais você deseja aplicar as ações. Algumas condições examinam campos de cabeçalhos de mensagens (por exemplo, os campos Para, De ou Cc). Outras condições examinam propriedades de mensagens (por exemplo, assunto, corpo, anexos, tamanho e classificação da mensagem). A maioria das condições exige que você especifique um operador de comparação (por exemplo, igual a, diferente de ou contém) e um valor a ser correspondido. Se não houver condições ou exceções, a regra será aplicada a todas as mensagens.

Para obter mais informações sobre as condições de regra de fluxo de emails no EOP autônomo, consulte Condições e exceções de regra de fluxo de email [(predicados) no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Exceções**: Opcionalmente, identifique as mensagens às quais as ações não devem ser aplicadas. Os mesmos identificadores de mensagens disponíveis nas condições também estão disponíveis nas exceções. As exceções substituem as condições e impedem que as ações da regra sejam aplicadas a uma mensagem, mesmo que a mensagem atenda a todas as condições configuradas.

- **Ações**: Especifique o que fazer com as mensagens que corresponderem às condições da regra e não corresponderem a nenhuma das exceções. Há muitas ações disponíveis, como rejeitar, excluir ou redirecionar mensagens, incluir destinatários adicionais, incluir prefixos no assunto da mensagem ou inserir avisos de isenção legal no corpo da mensagem.

Para obter mais informações sobre ações de regra de fluxo de emails disponíveis no EOP autônomo, consulte Ações de regra de fluxo de email [no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Propriedades**: Especifique outras configurações de regras que não sejam condições, exceções ou ações. Por exemplo, quando a regra deve ser aplicada, se devemos impor ou testar a regra e o período em que a regra é ativa.

  Para obter mais informações, consulte a seção Propriedades da [regra de fluxo de](#mail-flow-rule-properties) email neste artigo.

### <a name="multiple-conditions-exceptions-and-actions"></a>Várias condições, exceções e ações

Use a transport rule so messages can bypass Clutter

****

|Componente|Lógica|Comments|
|---|---|---|
|Comentários|E|Uma mensagem deve atender a todas as condições da regra. Se você precisar combinar uma condição ou outra, use regras separadas para cada condição. Por exemplo, se quiser adicionar o mesmo aviso de isenção legal a mensagens com anexos e mensagens com texto específico, crie uma regra para cada condição. No EAC, você pode facilmente copiar uma regra.|
|Uma mensagem deve atender a todas as condições da regra. Se você precisar combinar uma condição ou outra, use regras separadas para cada condição. Por exemplo, se quiser adicionar o mesmo aviso de isenção legal a mensagens com anexos e mensagens com conteúdo que corresponde a um padrão, crie uma regra para cada condição. Você pode facilmente copiar uma regra.|OU|Algumas condições permitem especificar mais de um valor. A mensagem deve corresponder a qualquer um dos valores especificados (não todos). Por exemplo, se o assunto de uma mensagem de email for Informações sobre o mercado de ações e a condição **O assunto inclui qualquer uma destas palavras** estiver configurada para corresponder às palavras Contoso ou ações, a condição será atendida, pois o assunto contém pelo menos um dos valores especificados.  |
|Algumas condições permitem especificar mais de um valor. Se uma condição permitir inserir vários valores, a mensagem deverá corresponder a qualquer um dos valores especificados naquela condição. Por exemplo, se o assunto de uma mensagem de email for Informações sobre o mercado de ações e a condição O assunto inclui qualquer uma destas palavras estiver configurada para corresponder às palavras Contoso ou ações, a condição será atendida, pois o assunto contém pelo menos um dos valores da condição.|OU|Se uma mensagem corresponder a qualquer uma das exceções, as ações não são aplicadas na mensagem. A mensagem não precisa coincidir com todas as exceções.|
|Se uma mensagem corresponder a qualquer uma das exceções, as ações não são processadas. A mensagem não precisa coincidir com todas as exceções.|E|As mensagens que atendem às condições de uma regra recebem todas as ações que estão especificadas na regra. Por exemplo, se as ações **Preceder o assunto da mensagem com** e **Adicionar destinatários à caixa Cco** estiverem selecionadas, ambas as ações serão aplicadas à mensagem.  <p> As mensagens que atendem às condições de uma regra recebem todas as ações especificadas na regra. Por exemplo, se as ações Preceder o assunto da mensagem com e Adicionar destinatários à caixa Cco estiverem selecionadas, ambas as ações serão aplicadas à mensagem. A mensagem receberá a cadeia de caracteres assinalada no assunto da mensagem e os destinatários especificados serão adicionados como destinatários de Cco.<p> Também é possível configurar uma ação em uma regra de tal forma que, quando ela for aplicada, as regras seguintes não sejam aplicadas à mensagem.|
|

### <a name="mail-flow-rule-properties"></a>Propriedades de regras de fluxo de email

A tabela a seguir descreve as propriedades das regras que estão disponíveis nas regras de fluxo de emails.

****

|Nome da propriedade no EAC|Nome do parâmetro no PowerShell|Descrição|
|---|---|---|
|**Prioridade**|_Priority_|Indica a ordem que as regras são aplicadas às mensagens. A prioridade padrão se baseia no momento em que a regra é criada (regras mais antigas têm uma prioridade mais alta que as regras mais recentes e as regras de prioridade mais alta são processadas antes das regras de prioridade mais baixa).   <p> Altere a prioridade da regra no EAC movendo a regra para cima ou para baixo na lista de regras. No PowerShell, você definirá o número de prioridade (0 é a prioridade mais alta). <p> Por exemplo, se tiver uma regra para rejeitar mensagens que incluam um número de cartão de crédito e outra exigindo aprovação, você desejará que a regra de rejeição ocorra primeiro e pare a aplicação das outras regras.  |
|**Modo**|_Mode_|Você pode especificar se deseja que a regra comece a processar as mensagens imediatamente, ou se deseja testar as regras sem afetar a entrega da mensagem (com ou sem Prevenção contra Perda de Dados ou Dicas de Política DLP). <p> As dicas de política apresentam uma anotação breve no Outlook ou no Outlook na Web que fornecem informações sobre possíveis violações de política para a pessoa que está criando a mensagem. Para saber mais, veja **Policy Tips**.  <p> Para saber mais sobre os modos, confira **Test a mail flow rule**.|
|**Ativar esta regra na seguinte data** <p> **Desativar esta regra na seguinte data**|_ActivationDate_ <p> _ExpiryDate_|Especifica o intervalo de datas quando a regra está ativa.|
|**Na** caixa de seleção selecionada ou não selecionada|Novas regras: _Parâmetro habilitado_ no cmdlet **New-TransportRule.** <p> Regras existentes: Use os cmdlets **Enable-TransportRule** ou **Disable-TransportRule**. <p> O valor é exibido na propriedade **State** da regra.|Você pode criar uma regra desabilitada e ativá-la quando estiver pronto para testá-la. Ou, você pode desativar uma regra sem excluí-la para preservar as configurações.|
|**Adiar a mensagem se o processamento de regra não for concluído**|_RuleErrorAction_|Você pode especificar como a mensagem deveria ser tratada se o processamento de regra não puder ser concluído. Por padrão, a regra será ignorada, mas você pode optar por reenviar a mensagem para processamento.|
|**Corresponder endereço do remetente da mensagem**|_SenderAddressLocation_|Se a regra usa condições ou exceções que examinam o endereço de email do remetente, você pode procurar o valor no cabeçalho da mensagem, no envelope da mensagem ou em ambos.|
|**Parar o processamento de mais regras**|_SenderAddressLocation_|Essa é uma ação para a regra, mas se parece com uma propriedade no EAC. Você pode optar por evitar a aplicação de regras adicionais a uma mensagem após uma regra processar uma mensagem.|
|**Comentários**|_Comments_|Você pode inserir comentários descritivos sobre a regra.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Como as regras de fluxo de emails são aplicadas a mensagens

Todas as mensagens que fluem por sua organização são avaliadas pelas regras de fluxo de emails habilitadas para a sua organização. As regras são processadas  na ordem listada na página Regras de fluxo de email no EAC ou com base no valor de parâmetro \>  _Priority_ correspondente no PowerShell.

Cada regra também oferece a opção de parar o processamento de outras quando é encontrada correspondência com a regra. Esta configuração é importante para as mensagens que atendem às condições em várias regras de fluxo de emails (qual regra você deseja aplicar à mensagem? Todas? Apenas uma?).

### <a name="differences-in-processing-based-on-message-type"></a>Diferenças no processamento com base no tipo de mensagem

Existem vários tipos de mensagens que transitam por uma organização. A tabela a seguir mostra quais tipos de mensagens podem ser processados por regras de fluxo de emails.

****

|Existem vários tipos de mensagens que transitam por uma organização. A tabela a seguir mostra quais tipos de mensagens podem ser processados por regras de transporte.|Tipo de mensagem|
|---|---|
|**Mensagens regulares**: Mensagens que contêm um único formato de texto rico (RTF), HTML ou corpo de mensagem de texto sem formatação ou um conjunto de várias partes ou de corpos de mensagem alternativos.|Sim|
|**Criptografia de Mensagem do Office 365**: Mensagens criptografadas pela Criptografia de Mensagens do Office 365 no Office 365. Para saber mais informações, consulte [Criptografia no Office 365](../../compliance/encryption.md).|As regras sempre podem acessar os cabeçalhos de envelope e processar as mensagens com base nas condições que inspecionam cabeçalhos. <p> Para uma regra inspecionar ou modificar o conteúdo de uma mensagem criptografada, é preciso verificar se a descriptografia de transporte está habilitada (Obrigatória ou Opcional; o padrão é Opcional). Para obter mais informações, consulte [Definir regras para criptografar ou descriptografar mensagens de email no Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).|
|**Mensagens criptografadas em S/MIME**|As regras podem apenas acessar os cabeçalhos de envelope e processar as mensagens com base nas condições que inspecionam cabeçalhos. <p> As regras com condições que exigem a inspeção do conteúdo da mensagem ou ações que modificam o conteúdo da mensagem não podem ser processadas.|
|**Mensagens protegidas** por RMS : mensagens que tinham uma política Active Directory Rights Management Services (AD RMS) ou rms do Azure Rights Management (RMS) aplicada.|As regras sempre podem acessar os cabeçalhos de envelope e processar as mensagens com base nas condições que inspecionam cabeçalhos. <p> Para uma regra inspecionar ou modificar o conteúdo de uma mensagem protegida por RMS, é preciso verificar se a descriptografia de transporte está habilitada (Obrigatória ou opcional; o padrão é opcional).|
|**Mensagens não assinadas:** mensagens assinadas, mas não criptografadas.|Sim|
|**Mensagens de UM**: Mensagens criadas ou processadas pelo serviço de Unificação de Mensagens, como caixa postal, fax, notificações de chamada perdidas e mensagens criadas ou encaminhadas usando o Microsoft Outlook Voice Access.|Sim|
|**Mensagens anônimas**: mensagens enviadas por envios anônimos.|Sim|
|**Relatórios de leitura**: relatórios gerados em resposta às solicitações de recebimento de leitura pelos envios. Os relatórios de leitura têm uma classe de `IPM.Note*.MdnRead` mensagem de ou `IPM.Note*.MdnNotRead` .|Sim|
|

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- O **valor da** propriedade Version ou **RuleVersion** para uma regra não é importante na Proteção do Exchange Online.

- Após criar ou alterar uma regra de fluxo de emails, pode levar até 30 minutos para a regra nova ou atualizada ser aplicada às mensagens.

## <a name="for-more-information"></a>Para saber mais

[Usar regras de fluxo de emails para inspecionar anexos de mensagens no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Criptografia de email no Office 365](../../compliance/email-encryption.md)

[Limites de regras de diário, transporte e caixa de entrada](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)