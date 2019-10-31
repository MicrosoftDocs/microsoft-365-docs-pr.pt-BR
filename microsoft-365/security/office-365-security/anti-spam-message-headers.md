---
title: Cabeçalhos de mensagem antispam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Aprenda sobre os campos e valores do cabeçalho que são adicionados às mensagens pela Proteção do Exchange Online.
ms.openlocfilehash: df0e31ad6d1c67c8d7ed92e9b42efb1da0c37731
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772255"
---
# <a name="anti-spam-message-headers"></a>Cabeçalhos de mensagem antispam

Quando o Proteção do Exchange Online examina emails de entrada, insere o cabeçalho **X-Forefront-Antispam-Report** em cada mensagem. Os campos nesse cabeçalho podem ajudar a fornecer aos administradores informações sobre a mensagem e sobre como ela foi processada. Os campos no cabeçalho **X-Microsoft-Antispam** fornecem mais informações sobre email em massa e phishing. Além esses dois cabeçalhos, o Proteção do Exchange Online também insere resultados de autenticação de email para cada mensagem que ele processa no cabeçalho **Authentication-results**.

Para obter informações sobre como exibir um cabeçalho de mensagem de email em vários clientes de email, veja [Analisador de Cabeçalho de Mensagens](https://go.microsoft.com/fwlink/p/?LinkId=306583). 

> [!TIP]
> Você pode copiar e colar o conteúdo do cabeçalho da mensagem na ferramenta [Analisador de Mensagem](https://testconnectivity.microsoft.com/?tabid=mha). Essa ferramenta ajuda a analisar os cabeçalhos, deixando-os em um formato mais legível.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos de cabeçalho da mensagem X-Forefront-Antispam-Report

Depois de acessar as informações do cabeçalho da mensagem, procure **X-Forefront-Antispam-Report** e por estes campos. Outros campos neste cabeçalho são usados exclusivamente pela equipe anti-spam da Microsoft para fins de diagnóstico.

|**Campo do cabeçalho**|**Descrição**|
|:-----|:-----|
|CIP: \[endereço IP\]|O endereço IP de conexão. Talvez você queira especificar esse endereço IP quando estiver criando uma Lista de IPs Permitidos ou uma Lista de IPs Bloqueados no filtro de conexão. Para obter mais informações, consulte [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md).|
|CTRY|O país/região a partir do qual a mensagem se conectou ao serviço. Isso é determinado pelo endereço IP de conexão, que pode não ser o mesmo que o endereço IP de envio original.|
|LANG|O idioma no qual a mensagem foi escrita, conforme especificado pelo código de país/região (por exemplo, ru_RU para russo).|
|SCL|O valor de Nível de Confiança de Spam (SCL) da mensagem. Para obter mais informações sobre como interpretar esses valores, consulte [Níveis de confiança de spam](spam-confidence-levels.md).  |
|SRV:BULK|A mensagem foi identificada como uma mensagem de email em massa. Se a **opção de filtragem de spam avançada Bloquear todas as mensagens de email em massa estiver habilitada**, ela será marcada como spam. Se não estiver habilitada, ela será apenas marcada como spam se o restante das regras de filtragem determinar que a mensagem é spam.|
|SFV:SFE|A filtragem foi ignorada e foi permitida a passagem da mensagem porque ela foi enviada de um endereço em uma lista de remetentes seguros de um indivíduo.|
|SFV:BLK|A filtragem foi ignorada e foi bloqueada a passagem da mensagem porque ela foi enviada de um endereço em uma lista de remetentes bloqueados de um indivíduo.  <br/> **Dica:** Para obter mais informações sobre como os usuários finais podem criar listas de remetentes seguros e bloqueados, confira [Bloquear ou permitir (configurações de lixo eletrônico)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook na Web) e [Visão geral do Filtro de Lixo Eletrônico](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).|
|IPV:CAL|A mensagem foi permitida pelos filtros de spam porque o endereço IP estava especificado em uma Lista de Permissões de IP do filtro de conexão.|
|IPV:NLI|O endereço IP não está listado em qualquer lista de reputação de IP.|
|SFV:SPM|O filtro de conteúdo marcou a mensagem como spam.|
|SFV:SKS|A mensagem foi marcada como spam antes de ser processada pelo filtro de conteúdo. Isso inclui mensagens que atenderam a uma regra de fluxo de emails (também conhecida como uma regra de Transporte) para marcá-la automaticamente como spam e ignorar toda filtragem adicional.|
|SFV:SKA|A mensagem ignorou a filtragem e foi entregue à caixa de entrada porque correspondeu a uma lista de permissões na política de filtro de spam, como a lista de **permissões do remetente**.|
|SFV:SKB|A mensagem foi marcada como spam porque correspondeu a uma lista de bloqueios na política de filtro de spam, como a lista de **bloqueio de remetente**.|
|SFV:SKN|A mensagem foi marcada como não sendo spam antes de ser processada pelo filtro de conteúdo. Isso inclui mensagens que atenderam a uma regra de fluxo de emails para marcá-la automaticamente como não sendo spam e ignorar qualquer filtragem adicional.|
|SFV:SKI|De forma semelhante a SFV:SKN, a filtragem de mensagem é ignorada por outro motivo, como sendo email intraorganizacional em um locatário.|
|SFV:SKQ|A mensagem foi liberada da quarentena e enviada para os destinatários pretendidos.|
|SFV:NSPM|A mensagem foi marcada como não spam e enviada aos destinatários pretendidos.|
|H: \[helostring\]|A cadeia de caracteres HELO ou EHLO do servidor de email que está se conectando.|
|PTR: \[ReverseDNS\]|O registro PTR, ou registro do ponteiro, do endereço IP de envio, também conhecido como o endereço de DNS reverso.|
|CAT:|A categoria da política de proteção, aplicada à mensagem: <br/>MALW: malware <br/>PHSH: phishing <br/>HSPM: spam de alta confiança <br/>SPOOF: falsificação <br/>SPM: spam <br/>BULK: em massa <br/>DIMP: representação de domínio <br/>UIMP: representação de usuário <br/>Potencialmente, uma mensagem de entrada pode ser sinalizada por várias formas de proteção e várias verificações de detecção. As políticas têm prioridades diferentes, e a política com a prioridade mais alta será aplicada. Confira [Qual política se aplica quando vários métodos de proteção e varreduras são executados em seu email](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-policies-and-protections-are-combined).|
|SFTY|A mensagem foi identificada como phishing e também será marcada com um dos seguintes valores: <br/>9.1: Valor padrão. A mensagem contém uma URL de phishing, pode conter outro conteúdo de phishing ou pode ter sido marcada como phishing por outro filtro de email, como uma versão local do Exchange Server, antes de retransmitir a mensagem para o Office 365. <br/>9.11: A mensagem falhou nas verificações de antifalsificação em que o domínio de envio em De: o cabeçalho é o mesmo, está alinhado ou faz parte da mesma organização que o domínio de recebimento. Isso indica que uma dica de segurança de dentro da organização contra falsificação será adicionada à mensagem. <br/>9.19: A mensagem falhou na verificação de usurpação de identidade de domínio em que o domínio de envio está tentando representar um domínio de propriedade do destinatário ou um domínio personalizado protegido pela política de anti-phishing. Isso indica que uma dica de segurança de representação será adicionada à mensagem, se habilitada pela política anti-phishing. <br/>9.20: A mensagem falhou na verificação de usurpação de identidade de domínio em que o domínio de envio está tentando representar um usuário na organização de receptores ou um domínio personalizado protegido pela política de anti-phishing. Isso indica que uma dica de segurança de representação será adicionada à mensagem, se habilitada pela política anti-phishing. <br/>9.21: A mensagem falhou em verificações de antifalsificação e o domínio de envio em De: o cabeçalho não autentica e é de um domínio externo. Usado em combinação com o CompAuth (consulte Resultados-de-Autenticação). <br/>9.22: Igual a 9.21, exceto pelo fato de o usuário ter um remetente seguro que foi substituído. <br/>9.23: Igual a 9.22, exceto que a organização tem um remetente ou domínio permitido que foi substituído. <br/>9.24: Igual a 9.23, exceto pelo fato de o usuário ter uma regra de fluxo de emails do Exchange que foi substituído.|
|X-CustomSpam: \[ASFOption\]|A mensagem corresponde a uma opção avançada de filtragem de spam. Por exemplo, **X-CustomSpam: os links de Imagem para sites remotos** indica que os** links de Imagem para sites remotos de** ASF foram correspondidas. Para descobrir qual texto do cabeçalho X é adicionado para cada opção ASF específica, confira [Opções adicionais de filtragem de spam](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de cabeçalho da mensagem X-Microsoft-Antispam

A tabela a seguir descreve campos úteis no cabeçalho da mensagem **X-Microsoft-Antispam**. Outros campos neste cabeçalho são usados exclusivamente pela equipe anti-spam da Microsoft para fins de diagnóstico.

|**Campo do cabeçalho**|**Descrição**|
|:-----|:-----|
|BCL|O Nível de Reclamação em Massa (BCL) da mensagem ajuda a distinguir os diferentes tipos de remetentes de envio em massa. Isso é representado como um valor entre 0 e 9. Para valores e outras informações sobre BCL, consulte [Valores de Nível de Reclamação em Massa](bulk-complaint-level-values.md).|

## <a name="authentication-results-message-header"></a>Cabeçalho da mensagem Authentication-results

Os resultados das verificações em relação a SPF, DKIM e DMARC são gravados ou marcados pelo Office 365 no cabeçalho da mensagem **Authentication-results** quando os servidores de email recebem uma mensagem de email.

### <a name="check-stamp-syntax-and-examples"></a>Verifique a sintaxe e os exemplos do carimbo

Os exemplos de sintaxe a seguir mostram uma parte do texto "carimbo" que o Office 365 aplica ao cabeçalho da mensagem para cada email que passa por uma verificação de autenticação de email quando é recebida por nossos servidores de email. O carimbo é adicionado ao cabeçalho **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Sintaxe: Carimbo de verificação do SPF

Para SPF, a seguinte sintaxe é aplicada.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**Exemplos: carimbo de verificação de SPF

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Sintaxe: Carimbo de verificação do DKIM

Para DKIM, a seguinte sintaxe é aplicada.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

** Exemplos: carimbo de verificação de DKIM

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Sintaxe: Carimbo de verificação do DMARC

Para DMARC, a seguinte sintaxe é aplicada.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

#### <a name="examples-dmarc-check-stamp"></a>Exemplos: Carimbo de verificação do DMARC

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campos do cabeçalho da mensagem Authentication-results usados pela autenticação de email do Office 365

Esta tabela descreve os campos e os valores possíveis para cada verificação de autenticação de email.

|**Campo do cabeçalho**|**Descrição**|
|:-----|:-----|
|spf|Descreve os resultados da verificação do SPF para a mensagem. Os valores possíveis incluem:<br/>**pass (endereço IP)**: Indica que a verificação do SPF para a mensagem foi aprovada e inclui um endereço IP do remetente. O cliente está autorizado a enviar ou retransmitir emails em nome do domínio do remetente. <br/>**fail (endereço IP)**: Indica a verificação do SPF para a mensagem reprovada e inclui um endereço IP do remetente. Isso também é conhecido como _falha grave_. <br/>**softfail (motivo)**: Indica que o registro SPF designou o host como não tendo permissão para enviar, mas está em transição. <br/>**neutral**: Indica que o registro SPF declarou explicitamente que não definiu se o endereço IP está autorizado. <br/>**none**: Indica que o domínio não tem um registro SPF ou o registro SPF não é avaliado como um resultado. <br/>**temperror**: Indica que ocorreu um erro que pode ser temporário, por exemplo, um erro de DNS. Tentar novamente mais tarde poderá ser bem sucedido sem qualquer ação do administrador. <br/>**permerror**: Indica que um erro permanente ocorreu. Isso acontece quando, por exemplo, o domínio tem um registro SPF mal formatado.|
|smtp.mailfrom|Contém o domínio da fonte a partir da qual a mensagem foi enviada. Os erros sobre esta mensagem de email serão enviados para o postmaster ou entidade responsável pelo domínio. Isso algumas vezes é chamado de endereço 5321.MailFrom ou endereço reverso no envelope da mensagem.|
|dkim|Descreve os resultados da verificação do DKIM para a mensagem. Os valores possíveis incluem:<br/>**pass**: Indica que a verificação DKIM para a mensagem foi aprovada. <br/>**fail (motivo)**: Indica que a verificação do DKIM para a mensagem falhou e o porquê. Por exemplo, se a mensagem não foi assinada ou se a assinatura não foi verificada. <br/>**none**: Indica que a mensagem não foi assinada. Isso pode ou não indicar que o domínio tem um registro DKIM ou o registro DKIM não foi avaliado como um resultado, apenas que essa mensagem não foi assinada.|
|header.d|Domínio identificado na assinatura DKIM, se houver. Este é o domínio consultado para a chave pública.|
|dmarc|Descreve os resultados da verificação do DMARC para a mensagem. Os valores possíveis incluem:<br/>**pass**: Indica que a verificação do DMARC para a mensagem foi aprovada. <br/>**fail**: Indica que houve falha na verificação do DMARC para a mensagem. <br/>**bestguesspass**: Indica que não existe nenhum registro TXT do DMARC para o domínio, mas, se houvesse, a verificação do DMARC para a mensagem teria passado. Isso ocorre porque o domínio no endereço 5321.MailFrom corresponde ao domínio no endereço 5322.From. <br/>**none**: Indica que não há nenhum registro TXT do DKIM para o domínio de envio no DNS.|
|ação|Indica a ação executada pelo filtro de spam com base nos resultados da verificação do DMARC. Por exemplo:<br/>**permerror**: Ocorreu um erro permanente durante a avaliação do DMARC, como encontrar um registro TXT do DMARC formado incorretamente no DNS. Tentar reenviar esta mensagem provavelmente não terminará com um resultado diferente. Em vez disso, talvez seja necessário entrar em contato com o proprietário do domínio para resolver o problema. <br/>**temperror**: Ocorreu um erro temporário durante a avaliação do DMARC. Você poderá solicitar ao remetente que reenvie a mensagem mais tarde para processar o email corretamente. <br/>**oreject** ou **o.reject**: Significa substituir a rejeição. Neste caso, o Office 365 usa essa ação quando recebe uma mensagem informando que houve falha na verificação do DMARC de um domínio cujo registro TXT do DMARC tem uma política p=reject. Em vez de excluir ou rejeitar a mensagem, o Office 365 marca a mensagem como spam. Para saber mais sobre por que o Office 365 está configurado dessa forma, confira [Como o Office 365 lida com emails de entrada que não passam na verificação do DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail). <br/>**pct.quarantine**: Indica que uma porcentagem menor que 100% das mensagens que não passam na verificação do DMARC será enviada de qualquer forma. Isso significa que houve falha de DMARC na mensagem e a política foi definida como quarentena, mas o campo pct não foi definido como 100% e o sistema aleatoriamente determinou não aplicar a ação do DMARC, conforme a política especificada do domínio. <br/>**pct.reject**: Indica que uma porcentagem menor que 100% das mensagens que não passam na verificação do DMARC será enviada de qualquer forma. Isso significa que houve falha de DMARC na mensagem e a política foi definida como rejeitar, mas o campo pct não foi definido como 100% e o sistema aleatoriamente determinou não aplicar a ação do DMARC, conforme a política especificada do domínio.|
|header.from|O domínio de endereço From no cabeçalho da mensagem de email. Isso também é conhecido como endereço _5322.From_.|
|compauth|Resultado da autenticação composta. Usado pelo Office 365 para combinar vários tipos de autenticação, como SPF, DKIM, DMARC ou qualquer outra parte da mensagem, para determinar se a mensagem é autenticada ou não. Usa o domínio De: como base de avaliação.|
|motivo|O motivo pelo qual a autenticação composta foi aprovada ou falhou. O valor da razão é formado por três dígitos: <br/>**000**: A mensagem falhou explicitamente na autenticação. Por exemplo, a mensagem recebeu uma falha DMARC com uma ação de quarentena ou de rejeitada. <br/>**001**: A mensagem implicitamente falhou a autenticação falhou a autenticação e o domínio de envio não publicaram políticas de autenticação. Por exemplo, uma política de DMARC de p = nenhum. <br/>**1xx**: A mensagem passou pela autenticação. Os segundos dois dígitos são códigos internos usados pelo Office 365. <br/>**2xx**: A mensagem passou facilmente pela autenticação. Os segundos dois dígitos são códigos internos usados pelo Office 365. <br/>**3xx**: A mensagem não foi verificada pela autenticação composta. <br/>**4xx**: A mensagem ignorou a autenticação composta. Os segundos dois dígitos são códigos internos usados pelo Office 365.|
|
