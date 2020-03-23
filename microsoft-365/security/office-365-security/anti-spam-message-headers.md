---
title: Cabeçalhos de mensagem antispam
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 55ba5435b181506cd39314275a9d8c8c6b459b28
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894177"
---
# <a name="anti-spam-message-headers-in-office-365"></a>Cabeçalhos de mensagens anti-spam no Office 365

Ao examinar e-mails de entrada, a Proteção do Exchange Online insere o cabeçalho **X-Forefront-Antispam-Report**em cada mensagem. Os campos nesse cabeçalho podem ajudar os administradores fornecendo informações da mensagem e sobre como ela foi processada. Os campos no cabeçalho **X-Microsoft-Antispam** fornecem mais informações de e-mail em massa e phishing. Além desses dois cabeçalhos, a Proteção do Exchange Online também insere resultados de autenticação de e-mails para cada mensagem que ele processa no cabeçalho **Authentication-results**.

Para saber mais sobre como exibir um cabeçalho de mensagem de email em vários clientes de email, confira [Exibir cabeçalhos de mensagens de Internet no Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Você pode copiar e colar o conteúdo do cabeçalho da mensagem na ferramenta [Analisador de Mensagem](https://testconnectivity.microsoft.com/?tabid=mha). Essa ferramenta ajuda a analisar os cabeçalhos, deixando-os em um formato mais legível.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos de cabeçalho da mensagem X-Forefront-Antispam-Report

Depois de acessar as informações do cabeçalho da mensagem, procure **X-Forefront-Antispam-Report** e por estes campos. Outros campos neste cabeçalho são usados exclusivamente pela equipe anti-spam da Microsoft para fins de diagnóstico.

|||
|---|---|
|**Campo do cabeçalho**|**Descrição**|
|ARC|O protocolo ARC tem os seguintes cabeçalhos: <ul><li>AAR: registra o conteúdo do cabeçalho de resultados de autenticação do DMARC.</li><li>AMS: esse cabeçalho inclui assinaturas criptográficas da mensagem.</li><li>AS: inclui assinaturas criptográficas dos cabeçalhos da mensagem. Este cabeçalho contém uma marca de validação da cadeia chamada "cv=", que inclui o resultado da validação de cadeia como **nenhum**, **aprovado** ou **falha**.</li></ul>|
|CAT:|A categoria da política de proteção, aplicada à mensagem: <ul><li>BULK: em massa</li><li>DIMP: representação de domínio</li><li>GIMP: Inteligência da caixa de correio</li><li>HPHSH ou HPHISH : Phishing de alta confiança </li><li>HSPM: Spam de alta confiança</li><li>MALW: malware</li><li>PHSH: phishing</li><li>SPM: Spam</li><li>SPOOF: Falsificação</li><li>UIMP: Representação do usuário</li></ul><br/>Uma mensagem de entrada pode ser sinalizada por várias formas de proteção e várias verificações de detecção. As políticas possuem prioridades diferentes, sendo que a política com a prioridade mais alta é aplicada primeiro. Para obter mais informações, consulte [Qual política se aplica quando vários métodos de proteção e verificações de detecção são executados em seus e-mails](how-policies-and-protections-are-combined.md).|
|CIP: \[endereço IP\]|O endereço IP de conexão. Você pode usar esse endereço IP na Lista de permissões de IP ou na Lista de bloqueios de IP. Para obter mais informações, consulte [Configure a filtragem de conexão no Office 365](configure-the-connection-filter-policy.md).|
|CTRY|O país de origem, conforme determinado pelo endereço de IP de conexão, que pode não ser o mesmo que o do endereço de IP de origem.|
|H:\[helostring\]|A sequência HELO ou EHLO do servidor de e-mails de conexão.|
|IPV:CAL|A mensagem ignorou a filtragem de spam porque o endereço de IP de origem estava na Lista de permissões do IP. Para obter mais informações, consulte [Configure a filtragem de conexão no Office 365](configure-the-connection-filter-policy.md).|
|IPV:NLI|O endereço IP não está listado em qualquer lista de reputação de IP.|
|LANG|O idioma no qual a mensagem foi escrita, conforme especificado pelo código de país/região (por exemplo, ru_RU para russo).|
|PTR:\[ReverseDNS\]|O registro PTR (também conhecido como registro do ponteiro ou endereço DNS reverso) do endereço de IP de origem.|
|SCL|O nível de confiança do spam (SCL) da mensagem. Um valor mais alto indica que é mais provável que a mensagem seja spam. Para obter mais informações, consulte [Nível de confiança de spams (SCL) no Office 365.](spam-confidence-levels.md).|
|SFTY|A mensagem foi identificada como phishing e também será marcada com um dos seguintes valores: <ul><li>9.1: Valor padrão. A mensagem contém uma URL de phishing, pode conter outro conteúdo de phishing ou pode ter sido marcada como phishing por outro filtro de email, como uma versão local do Exchange Server, antes de retransmitir a mensagem para o Office 365.</li><li>9.11: A mensagem falhou nas verificações de antifalsificação em que o domínio de envio em De: o cabeçalho é o mesmo, está alinhado ou faz parte da mesma organização que o domínio de recebimento. Isso indica que uma dica de segurança de dentro da organização contra falsificação será adicionada à mensagem.</li><li>9.19: A mensagem falhou na verificação de usurpação de identidade de domínio em que o domínio de envio está tentando representar um domínio de propriedade do destinatário ou um domínio personalizado protegido pela política de anti-phishing. Isso indica que uma dica de segurança de representação será adicionada à mensagem, se habilitada pela política anti-phishing.</li><li>9.20: A mensagem falhou na verificação de usurpação de identidade de domínio em que o domínio de envio está tentando representar um usuário na organização de receptores ou um domínio personalizado protegido pela política de anti-phishing. Isso indica que uma dica de segurança de representação será adicionada à mensagem, se habilitada pela política anti-phishing.</li><li>9.21: A mensagem falhou em verificações de antifalsificação e o domínio de envio em De: o cabeçalho não autentica e é de um domínio externo. Usado em combinação com o CompAuth (consulte Resultados-de-Autenticação).</li><li>9.22: Igual a 9.21, exceto pelo fato de o usuário ter um remetente seguro que foi substituído.</li><li>9.23: Igual a 9.22, exceto que a organização tem um remetente ou domínio permitido que foi substituído.</li><li>9.24: O mesmo que 9.23, exceto que o usuário possui uma regra de fluxo de mensagens do Exchange (também conhecida como regra de transporte) que foi substituída.</li></ul>|
|SFV:BLK|A filtragem foi ignorada e a mensagem foi bloqueada pois foi enviada de um endereço dos Remetentes bloqueados no Outlook de um usuário (a lista de Remetentes bloqueados do usuário).<br/></br> Para obter mais informações de como os administradores podem gerenciar a lista de Remetentes bloqueados de um usuário, consulte [Definir configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:NSPM|A filtragem de spam marcou a mensagem como não spam e a mensagem foi enviada aos destinatários pretendidos.|
|SFV:SFE|A filtragem foi ignorada e a mensagem foi transmitida pois foi enviada de um endereço dos Remetentes seguros do Outlook de um usuário (a lista de Remetentes confiáveis do usuário).<br/></br> Para obter mais informações de como os administradores podem gerenciar a lista de Remetentes confiáveis de um usuário, consulte [Definir configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365.](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:SKA|A mensagem ignorou a filtragem de spam e foi entregue à Caixa de entrada pois correspondia a uma entrada em uma lista de remetentes permitidos ou em uma lista de domínios permitidos em uma política anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).|
|SFV:SKB|A mensagem foi marcada como spam pois correspondia a uma entrada em uma lista de remetentes bloqueados ou em uma lista de domínios bloqueados em uma política anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).|
|SFV:SKI|Semelhante ao SFV:SKN, a mensagem ignorou a filtragem de spam por outro motivo (por exemplo: um e-mail intra-organizacional dentro de um locatário).|
|SFV:SKN|A mensagem foi marcada como não spam antes de ser processada pela filtragem de spam (por exemplo: a mensagem foi marcada como SCL -1 ou **Ignorar a filtragem** de spam por uma regra de fluxo de e-mails).|
|SFV:SKQ|A mensagem foi liberada da quarentena e enviada para os destinatários pretendidos.|
|SFV:SKS|A mensagem foi marcada como spam antes de ser processada pela filtragem de spam (por exemplo: a mensagem foi marcada como SCL 5 a 9 por uma regra de fluxo de e-mails).|
|SFV:SPM|A mensagem foi marcada como spam pela filtragem de spam.|
|SRV:BULK|A mensagem foi identificada como e-mail em massa pela filtragem de spam e pelo limite do nível de reclamação em massa (BCL). Quando o parâmetro _MarkAsSpamBulkMail_ estiver `On` (está ativado por padrão), uma mensagem de e-mail em massa é marcada como spam de alta confiança (SCL 9). Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).|
|X-CustomSpam: \[ASFOption\]|A mensagem correspondeu a uma configuração de Filtro de spam avançado (ASF). Para visualizar o valor do cabeçalho X de cada configuração de ASF, consulte [Configurações avançadas de filtro de spam (ASF) no Office 365](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de cabeçalho da mensagem X-Microsoft-Antispam

A tabela a seguir descreve campos úteis no cabeçalho da mensagem **X-Microsoft-Antispam**. Outros campos neste cabeçalho são usados exclusivamente pela equipe anti-spam da Microsoft para fins de diagnóstico.

|||
|---|---|
|**Campo do cabeçalho**|**Descrição**|
|BCL|O Nível de reclamação em massa (BCL) da mensagem. Uma BCL mais alta indica que uma mensagem de correio em massa (também conhecida como _correio cinza_) tem mais chances de gerar reclamações (e, portanto, é mais provável que seja spam). Para obter mais informações, consulte [Nível de reclamação em massa (BCL) no Office 365)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Cabeçalho da mensagem Authentication-results

Os resultados das verificações em relação a SPF, DKIM e DMARC são gravados ou marcados pelo Office 365 no cabeçalho da mensagem **Authentication-results** quando os servidores de email recebem uma mensagem de email.

### <a name="check-stamp-syntax-and-examples"></a>Verifique a sintaxe e os exemplos do carimbo

Os exemplos de sintaxe a seguir mostram uma parte do texto "carimbo" que o Office 365 aplica ao cabeçalho da mensagem para cada email que passa por uma verificação de autenticação de email quando é recebida por nossos servidores de email. O carimbo é adicionado ao cabeçalho **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Sintaxe: Carimbo de verificação do SPF

Para SPF, a seguinte sintaxe é aplicada.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>Exemplos: Carimbo de verificação do SPF

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Sintaxe: Carimbo de verificação do DKIM

Para DKIM, a seguinte sintaxe é aplicada.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>Exemplos: Carimbo de verificação do DKIM

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Sintaxe: Carimbo de verificação do DMARC

Para DMARC, a seguinte sintaxe é aplicada.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>Exemplos: Carimbo de verificação do DMARC

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campos do cabeçalho da mensagem Authentication-results usados pela autenticação de email do Office 365

Esta tabela descreve os campos e os valores possíveis para cada verificação de autenticação de email.

|||
|---|---|
|**Campo do cabeçalho**|**Descrição**|
|ação|Indica a ação executada pelo filtro de spam com base nos resultados da verificação do DMARC. Por exemplo:<ul><li>**oreject** ou **o.reject**: Significa substituir a rejeição. Neste caso, o Office 365 usa essa ação quando recebe uma mensagem informando que houve falha na verificação do DMARC de um domínio cujo registro TXT do DMARC tem uma política p=reject. Em vez de excluir ou rejeitar a mensagem, o Office 365 marca a mensagem como spam. Para saber mais sobre por que o Office 365 está configurado dessa forma, confira [Como o Office 365 lida com emails de entrada que não passam na verificação do DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</li><li>**pct.quarantine**: Indica que uma porcentagem menor que 100% das mensagens que não passam na verificação do DMARC será enviada de qualquer forma. Isso significa que houve falha de DMARC na mensagem e a política foi definida como quarentena, mas o campo pct não foi definido como 100% e o sistema aleatoriamente determinou não aplicar a ação do DMARC, conforme a política especificada do domínio.</li><li>**pct.reject**: Indica que uma porcentagem menor que 100% das mensagens que não passam na verificação do DMARC será enviada de qualquer forma. Isso significa que houve falha de DMARC na mensagem e a política foi definida como rejeitar, mas o campo pct não foi definido como 100% e o sistema aleatoriamente determinou não aplicar a ação do DMARC, conforme a política especificada do domínio.</li><li>**permerror**: Ocorreu um erro permanente durante a avaliação do DMARC, como encontrar um registro TXT do DMARC formado incorretamente no DNS. Tentar reenviar esta mensagem provavelmente não terminará com um resultado diferente. Em vez disso, talvez seja necessário entrar em contato com o proprietário do domínio para resolver o problema.</li><li>**temperror**: Ocorreu um erro temporário durante a avaliação do DMARC. Você poderá solicitar ao remetente que reenvie a mensagem mais tarde para processar o email corretamente.</li></ul>|
|compauth|Resultado da autenticação composta. Usado pelo Office 365 para combinar vários tipos de autenticação, como SPF, DKIM, DMARC ou qualquer outra parte da mensagem, para determinar se a mensagem é autenticada ou não. Usa o domínio De: como base de avaliação.|
|dkim|Descreve os resultados da verificação do DKIM para a mensagem. Os valores possíveis incluem:<ul><li>**pass**: Indica que a verificação DKIM para a mensagem foi aprovada.</li><li>**fail (motivo)**: Indica que a verificação do DKIM para a mensagem falhou e o porquê. Por exemplo, se a mensagem não foi assinada ou se a assinatura não foi verificada.</li><li>**none**: Indica que a mensagem não foi assinada. Isso pode ou não indicar que o domínio tem um registro DKIM ou o registro DKIM não foi avaliado como um resultado, apenas que essa mensagem não foi assinada.</li></ul>|
|dmarc|Descreve os resultados da verificação do DMARC para a mensagem. Os valores possíveis incluem:<ul><li>**pass**: Indica que a verificação do DMARC para a mensagem foi aprovada.</li><li>**fail**: Indica que houve falha na verificação do DMARC para a mensagem.</li><li>**bestguesspass**: Indica que não existe nenhum registro TXT do DMARC para o domínio, mas, se houvesse, a verificação do DMARC para a mensagem teria passado. Isso ocorre porque o domínio no `5321.MailFrom` endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) corresponde ao domínio no `5322.From` endereço (também conhecido como Endereço De ou Remetente P2).</li><li>**none**: Indica que não há nenhum registro TXT do DKIM para o domínio de envio no DNS.|
|header.d|Domínio identificado na assinatura DKIM, se houver. Este é o domínio consultado para a chave pública.|
|header.from|O domínio do `5322.From` endereço no cabeçalho da mensagem de e-ail (também conhecido como endereço De ou remetente P2). Destinatário, consulte o Endereço De nos clientes de e-mail.|
|motivo|O motivo pelo qual a autenticação composta foi aprovada ou falhou. O valor da razão é formado por três dígitos: <ul><li>**000**: A mensagem falhou explicitamente na autenticação. Por exemplo, a mensagem recebeu uma falha DMARC com uma ação de quarentena ou de rejeitada.</li><li>**001**: A mensagem implicitamente falhou a autenticação falhou a autenticação e o domínio de envio não publicaram políticas de autenticação. Por exemplo, uma política de DMARC de p = nenhum.</li><li>**1xx** ou **7xx**: A mensagem passou pela autenticação. Os segundos dois dígitos são códigos internos usados pelo Office 365.</li><li>**2xx**: A mensagem passou facilmente pela autenticação. Os segundos dois dígitos são códigos internos usados pelo Office 365.</li><li>**3xx**: A mensagem não foi verificada pela autenticação composta.</li><li>**4xx** ou **9xx**: A mensagem ignorou a autenticação composta. Os segundos dois dígitos são códigos internos usados pelo Office 365.</li></ul>|
|smtp.mailfrom|O domínio do `5321.MailFrom` endereço (também conhecido como endereço ENVIAR DE, remetente P1 ou remetente do envelope). Este é o endereço de e-mail usado para relatórios de falha na entrega (também conhecido como NDRs ou mensagens de devolução).|
|spf|Descreve os resultados da verificação do SPF para a mensagem. Os valores possíveis incluem:<ul><li>**pass (endereço IP)**: Indica que a verificação do SPF para a mensagem foi aprovada e inclui um endereço IP do remetente. O cliente está autorizado a enviar ou retransmitir emails em nome do domínio do remetente.</li><li>**fail (endereço IP)**: Indica a verificação do SPF para a mensagem reprovada e inclui um endereço IP do remetente. Isso também é conhecido como _falha grave_.</li><li>**softfail (motivo)**: Indica que o registro SPF designou o host como não tendo permissão para enviar, mas está em transição.</li><li>**neutral**: Indica que o registro SPF declarou explicitamente que não definiu se o endereço IP está autorizado.</li><li>**none**: Indica que o domínio não tem um registro SPF ou o registro SPF não é avaliado como um resultado.</li><li>**temperror**: Indica que ocorreu um erro que pode ser temporário, por exemplo, um erro de DNS. Tentar novamente mais tarde poderá ser bem sucedido sem qualquer ação do administrador.</li><li>**permerror**: Indica que um erro permanente ocorreu. Isso acontece quando, por exemplo, o domínio tem um registro SPF mal formatado.</li></ul>|
|
