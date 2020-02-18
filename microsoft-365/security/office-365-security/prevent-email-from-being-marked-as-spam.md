---
title: Como impedir que falsos positivos aconteçam no Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Aprenda como evitar falsos positivos e manter o e-mail real fora do lixo eletrônico no Office 365, Exchange Online e no Exchange Online Protection (EOP) independentes.
ms.openlocfilehash: bf6149d21a5088e4507b65c6474918327faf3510
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598688"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>Como impedir que e-mails reais sejam marcados como spam no Office 365

 **Seu email real está sendo marcado como spam no Office 365? Faça isso.**

Se uma boa mensagem de e-mail for marcada como spam (um _falso positivo_) no Office 365, no Exchange Online ou no Exchange Online Protection (EOP) independente, você deve relatar a mensagem para a Microsoft utilizando [Usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Além disso, você pode enviar a mensagem utilizando [Inscrições do Explorer](admin-submission.md).

## <a name="determine-why-the-message-was-marked-as-spam"></a>Determinar por que a mensagem foi marcada como spam

É possível resolver muitos problemas com falsos positivos, exibindo o cabeçalho da mensagem de e-mail para determinar por que a mensagem foi marcada como spam. Para exibir o cabeçalho da mensagem, consulte [Exibir cabeçalhos de mensagens da Internet no Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

Especificamente, você precisa procurar um campo de cabeçalho denominado **X-Forefront-antispam-Report**. Os valores importantes a serem procurados são:

- **SFV:SPM**: a mensagem foi marcada como spam pelo filtro antispam (também conhecido como_filtro de conteúdo_). Para obter mais informações, consulte [Proteção antispam de e-mail do Office 365](anti-spam-protection.md).

- **SFV:BLK**: a mensagem foi marcada como spam porque o endereço de e-mail do remetente está na lista **Remetentes bloqueados** do destinatário. Para obter mais informações, consulte [Filtrar lixo eletrônico e spam no Outlook na Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) e [Visão geral do filtro do lixo eletrônico](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

- **SFV:SKS**: a mensagem foi marcada como spam **antes** que pudesse ser examinada pelo filtro antispam. Por exemplo, uma regra de fluxo de mensagens (também conhecida como regra de transporte) define o nível de confiança do spam (SCL) da mensagem com um valor elevado (9) que indica que a mensagem é spam. Para obter mais informações sobre SCL, consulte [Níveis de confiança de spam](spam-confidence-levels.md).

  Execute um rastreamento de mensagem para verificar se uma regra de fluxo de mensagens é responsável pelo elevado valor de SCL. Para obter mais informações, consulte [Rastreamento de mensagens no Centro de conformidade e segurança](message-trace-scc.md).

- **SFV:SKB**: a mensagem foi marcada como spam porque correspondia a uma entrada de bloqueio em uma política de filtro de spam (por exemplo, remetentes bloqueados ou domínios de remetente bloqueados). Para obter mais informações, consulte [Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).

- **SFV:BULK**: a mensagem foi identificada como e-mail em massa em vez de spam pelo filtro antispam. Isso acontece quando o valor do nível de reclamação em massa (BCL) da mensagem é **maior do que** o limite em massa definido nas configurações da política antispam (um valor mais baixo da BCL indica que é mais provável que a mensagem seja spam). Você pode ver o valor do BCL no campo de cabeçalho **X-Microsoft-Antispam**.

  Os e-mails em massa (também conhecidos como _e-mails cinza_) são indesejáveis, mas não maliciosos como os e-mails de marketing ou de publicidade que foram intencional ou involuntariamente solicitados pelo usuário. Diferentes usuários têm expectativas diferentes quanto ao nível de envio de e-mails em massa para que se possa criar políticas ou regras diferentes que permitem ou bloqueiam e-mails em massa de forma adequada. Para obter mais informações, consulte os seguintes tópicos:

  - [Qual é a diferença entre lixo eletrônico e e-mail em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [Valores do nível de reclamação em massa](bulk-complaint-level-values.md)

- **CAT:SPOOF** ou **CAT:PHISH**: indica que a mensagem aparenta ser falsa, o que significa que a origem da mensagem não pode ser validada e pode ser suspeita.

  Se a mensagem for de um remetente falso, o remetente legítimo correspondente precisará verificar os registros SPF e DKIM do seu domínio de e-mail no DNS público. Verifique o campo de cabeçalho **Resultados da autenticação** para obter mais informações. Embora possa ser difícil fazer com que todos os remetentes usem métodos adequados de autenticação de e-mail, ignorar essas verificações pode ser extremamente perigoso e é a principal causa de mensagens de falsificação e phishing.

> [!NOTE]
> • Para obter mais informações de outros cabeçalhos e valores de mensagens antispam, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md). <br/><br/>• Outros campos e valores de cabeçalho que não estejam especificamente descritos são utilizados de forma exclusiva pela equipe antispam da Microsoft para fins de diagnóstico. <br/><br/>• Um campo de cabeçalho **X-CustomSpam** no cabeçalho da mensagem indica que a mesma foi marcada como spam pela Filtragem de spam avançada (ASF). Estamos no processo de mover a funcionalidade ASF para outras partes da pilha de filtragem e recomendamos que você **desabilite** as configurações do ASF que estão atualmente disponíveis nas políticas antispam. Para obter mais informações, consulte [Opções avançadas de filtragem de spam](advanced-spam-filtering-asf-options.md).

## <a name="solutions-for-too-much-spam"></a>Soluções para o excesso de spam

Para que a filtragem antispam seja a mais eficaz possível, um administrador deve definir algumas configurações na organização. Se você não é um administrador, pode pular para a seção de usuários.

### <a name="for-admins"></a>Para administradores

- **Aponte o registro MX do seu domínio de e-mail para o Office 365**: para que o Office 365 forneça proteção, o registro MX para todos os domínios de e-mail no Office 365 deve apontar para o Office 365 e apenas para o Office 365 (ou seja, os e-mails dos destinatários desse domínio sempre são enviados primeiro para o Office 365). Se o registro MX apontar para outro local (por exemplo, uma solução ou um dispositivo antispam de terceiros), o Office 365 não fornecerá a filtragem de spam para seus usuários. Nesse cenário, considere criar uma regra de fluxo de e-mail que ignore a filtragem de spam para todas as mensagens (defina o valor SCL de todas as mensagens recebidas como -1). Se, mais tarde, você decidir apontar seu registro MX para o Office 365 primeiro, certifique-se de remover a regra.

- **Habilitar o suplemento de mensagem de relatório para usuários**: é altamente recomendável que você ative o suplemento Report Message dos seus usuários. Para instruções, consulte [Habilitar o suplemento Mensagem de relatório](enable-the-report-message-add-in.md).

- **Usar o Gerenciador de envios**: os administradores já podem enviar mensagens de e-mail para verificação através da Microsoft. Como administrador, você também pode exibir os comentários enviados por seus usuários. Você pode usar padrões em seus relatórios falsos positivos para ajustar as configurações de filtragem de spam. Para obter mais informações, consulte [Como enviar spam, phish, URLs e arquivos suspeitos para verificação da Microsoft do Office 365](admin-submission.md).

- **Verifique se os usuários estão dentro dos limites permitidos** conforme descrito em [Receber e limitar os limites](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) na descrição do serviço do Exchange Online.

- **Verifique os níveis do BCL nas suas políticas antispam** conforme descrito anteriormente neste tópico.

### <a name="for-users"></a>Para usuários

- **Adicione o remetente à sua lista de Remetentes confiáveis** no [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) ou [Outlook na Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d).

  O Office 365 usará a lista de Remetentes confiáveis e a lista de Destinatários confiáveis, mas não a lista de Domínios seguros. Isso ocorre independentemente de como você adiciona o domínio à lista (no Outlook, no Outlook na Web ou no Outlook, e após é sincronizado pela sincronização de diretórios).

- **Desabilitar a filtragem de SmartScreen no Outlook**: Em clientes mais antigos da área de trabalho do Outlook, não ative a filtragem do SmartScreen nas suas Opções de **Lixo eletrônico**. As atualizações de filtragem do SmartScreen foram encerradas em novembro de 2016. Se você habilitar a proteção de lixo eletrônico **Baixa** ou **Alta** no Outlook, estará usando a filtragem do SmartScreen e poderá obter falsos positivos. Observe que a filtragem do SmartScreen não está disponível nos modernos clientes da área de trabalho do Outlook. Para obter mais informações, consulte [Substituição do suporte para SmartScreen no Outlook e no Exchange](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332).

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>Solução de problemas: uma mensagem é enviada para a pasta Lixo eletrônico depois de passar a filtragem antispam

Se um usuário tiver a opção **Apenas listas de confiança** selecionada nas opções de lixo eletrônico do Outlook, todas as mensagens de pessoas que não estão na lista Remetentes confiáveis ou na lista Destinatários confiáveis do usuário serão enviadas para a pasta **Lixo eletrônico**, independentemente de a mensagem ter passado pela filtragem antispam da sua organização ou se uma regra de fluxo de e-mail marcou a mensagem como não spam (um valor de SCL de -1).

No Outlook na Web, o destinatário verá uma dica de segurança amarela que indica que a mensagem está na pasta **Lixo eletrônico** porque o remetente não está na lista Remetentes Confiáveis ou na lista Destinatários Confiáveis.

O cabeçalho da mensagem incluirá o valor **X-Forefront-Antispam-Report** do campo de cabeçalho `SFV:SKN` (a mensagem foi marcada como não sendo spam antes do processamento pelo filtro anti-spam) ou `SFV:NSPM` (o filtro anti-spam determinou que a mensagem não era spam), mas a mensagem ainda é entregue na pasta **Lixo eletrônico** do usuário.

Nada no cabeçalho da mensagem indicará que a mesma foi entregue como lixo eletrônico devido à configuração **Somente listas de confiança do usuário**. Mas você pode usar o cmdlet **Get-MailboxJunkEmailConfiguration** no Exchange Online PowerShell para verificar se um usuário permite apenas que mensagens de remetentes confiáveis sejam entregues na Caixa de Entrada.

Substitua \<MailboxIdentity\> pelo nome, pseudônimo ou endereço de e-mail da caixa de correio e execute o seguinte comando em [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- Se o valor da propriedade *TrustedListsOnly* for `True`: as mensagens que não são de remetentes ou destinatários confiáveis (ou seja, as pessoas que não estão na lista Remetentes confiáveis e na lista Destinatários confiáveis do usuário) vão para a pasta **Lixo eletrônico**.

- Se o valor da propriedade *ContactsTrusted* for `True`: os contatos do usuário também serão identificados como remetentes confiáveis. Se o valor da propriedade *TrustedListsOnly* for `True`: as mensagens de pessoas que não estão na lista Remetentes confiáveis, lista de Destinatários confiáveis ou Contatos do usuário irão para a pasta **Lixo eletrônico**.

- A propriedade *TrustedSendersAndDomains* contém a lista de Remetentes confiáveis do usuário.

Para alterar essas configurações na caixa de correio, substitua \<MailboxIdentity\> pelo nome, pseudônimo ou endereço de e-mail da caixa de correio e execute o seguinte comando:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

Para obter informações detalhadas sobre a sintaxe, parâmetros e permissões necessárias, consulte os tópicos [MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) e [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

## <a name="directory-synchronization-for-standalone-eop-customers"></a>Sincronização de diretório para clientes EOP independentes

Se você usar o EOP independente para ajudar a proteger sua organização local do Exchange, sincronize as configurações do usuário com o serviço usando a sincronização de diretórios. Isso garante que as listas de Remetentes confiáveis dos seus usuários sejam respeitadas pelo EOP. Para obter mais informações, consulte [Usar a sincronização de diretório para gerenciar usuários de e-mail](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).
