---
title: Cabeçalhos de mensagem antispam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender sobre os campos de cabeçalho adicionados às mensagens pelo EOP (Exchange Online Protection). Esses campos de cabeçalho fornecem informações sobre a mensagem e como ela foi processada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb3b2eb9e4ce4a63d4bef276dde9e19b491aae53
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615535"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Cabeçalhos de mensagens anti-spam no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Em todas as organizações do Microsoft 365, o EOP (Proteção do Exchange Online) verifica todas as mensagens recebidas em busca de spam, malware e outras ameaças. Os resultados dessas verificações são adicionados aos seguintes campos de cabeçalho nas mensagens:

- **X-Forefront-Antispam-Report**: contém informações sobre a mensagem e como ela foi processada.

- **X-Microsoft-Antispam**: contém informações adicionais sobre email em massa e phishing.

- **Authentication-results**: contém informações sobre resultados de SPF, DKIM e DMARC (autenticação de email).

Este artigo descreve o que está disponível nesses campos de cabeçalho.

Para saber mais sobre como exibir um cabeçalho de mensagem de email em vários clientes de email, confira [Exibir cabeçalhos de mensagens de Internet no Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Você pode copiar e colar o conteúdo de um cabeçalho da mensagem na ferramenta [Analisador do cabeçalho da mensagem](https://mha.azurewebsites.net/). Essa ferramenta ajuda a analisar os cabeçalhos, deixando-os em um formato mais legível.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos de cabeçalho da mensagem X-Forefront-Antispam-Report

Depois de obter as informações do cabeçalho da mensagem, localize o cabeçalho **X-Forefront-Antispam-Report**. Haverá vários pares de valores e campos neste cabeçalho separados por ponto-e-vírgula (;). Por exemplo:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

Os campos e valores individuais são descritos na tabela a seguir.

> [!NOTE]
> O cabeçalho **X-Forefront-Antispam-Report** contém muitos campos e valores diferentes. Os campos que não estão descritos na tabela são usados exclusivamente pela equipe antispam da Microsoft para fins de diagnóstico.

****

|Campo|Descrição|
|---|---|
|`ARC`|O protocolo `ARC` tem os seguintes campos: <ul><li>`AAR`: registra o conteúdo do cabeçalho **Authentication-results** do DMARC.</li><li>`AMS`: inclui assinaturas criptográficas da mensagem.</li><li>`AS`: inclui assinaturas criptográficas dos cabeçalhos da mensagem. Este campo contém uma marca de validação da cadeia chamada `"cv="`, que inclui o resultado da validação de cadeia como **nenhum**, **aprovado** ou **falha**.</li></ul>|
|`CAT:`|A categoria da política de proteção, aplicada à mensagem: <ul><li>`BULK`: Em massa</li><li>`DIMP`: Usurpação de identidade de domínio</li><li>`GIMP`: [Usurpação de identidade baseada em inteligência de caixa de correio](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>`HPHSH` ou `HPHISH` : Phishing de alta confiança</li><li>`HSPM`: Spam de alta confiança</li><li>`MALW`: Malware</li><li>`PHSH`: Phishing</li><li>`SPM`: Spam</li><li>`SPOOF`: Spoofing</li><li>`UIMP`: Usurpação de identidade de usuário</li><li>`AMP`: Antimalware</li><li>`SAP`: Anexos seguros</li><li>`OSPM`: Spam de saída</li></ul> <p> Uma mensagem de entrada pode ser sinalizada por várias formas de proteção e várias verificações de detecção. As políticas possuem prioridades diferentes, sendo que a política com a prioridade mais alta é aplicada primeiro. Para obter mais informações, consulte [Qual política se aplica quando vários métodos de proteção e verificações de detecção são executados em seus e-mails](how-policies-and-protections-are-combined.md).|
|`CIP:[IP address]`|O endereço IP de conexão. Você pode usar esse endereço IP na Lista de permissões de IP ou na Lista de bloqueios de IP. Para obter mais informações, confira [Configurar a filtragem da conexão](configure-the-connection-filter-policy.md).|
|`CTRY`|O país/região de origem, conforme determinado pelo endereço IP da conexão, que pode ser diferente do endereço IP de origem.|
|`H:[helostring]`|A sequência HELO ou EHLO do servidor de emails de conexão.|
|`IPV:CAL`|A mensagem ignorou a filtragem de spam porque o endereço de IP de origem estava na Lista de permissões do IP. Para obter mais informações, confira [Configurar a filtragem da conexão](configure-the-connection-filter-policy.md).|
|`IPV:NLI`|O endereço IP não foi encontrado em nenhuma lista de reputação de IP.|
|`LANG`|O idioma no qual a mensagem foi escrita, conforme especificado pelo código de país/região (por exemplo, ru_RU para russo).|
|`PTR:[ReverseDNS]`|O registro PTR do endereço IP de envio, também conhecido como o endereço de DNS reverso.|
|`SCL`|O nível de confiança do spam (SCL) da mensagem. Um valor mais alto indica que é mais provável que a mensagem seja spam. Para obter mais informações, confira [Nível de confiança de Spam (SCL)](spam-confidence-levels.md).|
|`SFTY`|A mensagem foi identificada como phishing e também será marcada com um dos seguintes valores: <ul><li>9.1: Valor padrão. A mensagem contém alguns ou todos os seguintes elementos: uma URL de phishing, outro conteúdo de phishing, ou foi marcada como phishing pelo Exchange local.</li><li>9.11: [Falsificação dentro da organização ou self-to-self](anti-spoofing-protection.md#different-types-of-spoofing). A dica de segurança para falsificação dentro da organização será adicionada à mensagem.</li><li>9.19: Usurpação de identidade de domínio. O domínio de envio está tentando [usurpar a identidade de um domínio protegido](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). A dica de segurança contra a usurpação de identidade de domínio é adicionada à mensagem (se estiver habilitada).</li><li>9.20: Usurpação de identidade de usuário. O usuário remetente está tentando usurpar a identidade de um usuário na organização do destinatário ou um usuário protegido que está especificado em uma política anti-phishing no Microsoft Defender para Office 365. A dica de segurança contra a usurpação de identidade de usuário é adicionada à mensagem (se estiver habilitada).</li><li>9.21: [Falsificação entre domínios](anti-spoofing-protection.md#different-types-of-spoofing). A mensagem falhou nas verificações antifalsificação. O domínio de email do remetente no cabeçalho De não autentica e é um domínio externo. Usado em combinação com a [autenticação composta](#authentication-results-message-header-fields).</li><li>9.22: Igual a 9.21, exceto pelo fato de o usuário ter um remetente seguro que foi substituído.</li><li>9.23: Igual a 9.22, exceto que a organização tem um remetente ou domínio permitido que foi substituído.</li><li>9.24: O mesmo que 9.23, exceto que o usuário possui uma regra de fluxo de mensagens do Exchange (também conhecida como regra de transporte) que foi substituída.</li></ul>|
|`SFV:BLK`|A filtragem foi ignorada e a mensagem foi bloqueada, pois foi enviada de um endereço da lista de remetentes bloqueados de um usuário. <p> Para saber mais sobre como os administradores podem gerenciar a lista de remetentes bloqueados de um usuário, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:NSPM`|A filtragem de spam marcou a mensagem como não spam e a mensagem foi enviada aos destinatários pretendidos.|
|`SFV:SFE`|A filtragem foi ignorada e a mensagem foi permitida porque foi enviada de um endereço na lista de remetentes Confiáveis ​​de um Usuário. <p> Para obter mais informações sobre como os administradores podem gerenciar a lista de remetentes confiáveis de um usuário, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:SKA`|A mensagem ignorou a filtragem de spam e foi entregue na caixa de entrada, pois o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos em uma política antispam. Para saber mais, confira [Configurar políticas antispam](configure-your-spam-filter-policies.md).|
|`SFV:SKB`|A mensagem foi marcada como spam, pois correspondeu a um remetente da lista de remetentes bloqueados ou da lista de domínios bloqueados em uma política antispam. Para saber mais, confira [Configurar políticas antispam](configure-your-spam-filter-policies.md).|
|`SFV:SKI`|Semelhante a SFV:SKN, a mensagem ignorou a filtragem de spam por outro motivo (por exemplo, um email intraorganizacional em um locatário).|
|`SFV:SKN`|A mensagem foi marcada como não sendo spam antes de ser processada pela filtragem de spam. Por exemplo, a mensagem foi marcada como SCL -1 ou **Ignorar filtragem de spam** por uma regra de fluxo de email.|
|`SFV:SKQ`|A mensagem foi liberada da quarentena e enviada aos destinatários pretendidos.|
|`SFV:SKS`|A mensagem foi marcada como spam antes de ser processada pela filtragem de spam. Por exemplo, a mensagem foi marcada como SCL 5 a 9 por uma regra de fluxo de email.|
|`SFV:SPM`|A mensagem foi marcada como spam pela filtragem de spam.|
|`SRV:BULK`|A mensagem foi identificada como e-mail em massa pela filtragem de spam e pelo limite do nível de reclamação em massa (BCL). Quando o parâmetro _MarkAsSpamBulkMail_ estiver `On` (está ativado por padrão), uma mensagem de e-mail em massa é marcada como spam de alta confiança (SCL 9). Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).|
|`X-CustomSpam: [ASFOption]`|A mensagem correspondeu a uma configuração de Filtro de spam avançado (ASF). Para ver o valor do cabeçalho X de cada configuração ASF, confira [configurações do Filtro de Spam Avançado (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de cabeçalho da mensagem X-Microsoft-Antispam

A tabela a seguir descreve campos úteis no cabeçalho da mensagem **X-Microsoft-Antispam**. Outros campos neste cabeçalho são usados exclusivamente pela equipe anti-spam da Microsoft para fins de diagnóstico.

****

|Campo|Descrição|
|---|---|
|`BCL`|O nível de reclamação em massa (BCL) da mensagem. Um BCL mais alto indica que uma mensagem de email em massa tem mais chances de gerar reclamações (e, portanto, mais chances que seja spam). Para saber mais, confira [Nível de reclamação em massa (BCL)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Cabeçalho da mensagem Authentication-results

Os resultados das verificações de autenticação de email para SPF, DKIM e DMARC são registrados (carimbados) no cabeçalho da mensagem **Authentication-results** nas mensagens de entrada.

A lista a seguir descreve o texto adicionado ao cabeçalho **Authentication-Results** para cada tipo de verificação de autenticação de email:

- O SPF usa a seguinte sintaxe:

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  Por exemplo:

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- O DKIM usa a seguinte sintaxe:

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  Por exemplo:

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- O DMARC usa a seguinte sintaxe:

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  Por exemplo:

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Campos do cabeçalho de mensagem Authentication-results

A tabela a seguir descreve os campos e valores possíveis para cada verificação de autenticação de email.

****

|Campo|Descrição|
|---|---|
|`action`|Indica a ação executada pelo filtro de spam com base nos resultados da verificação do DMARC. Por exemplo: <ul><li>**oreject** ou **o.reject**: Significa substituir a rejeição. Neste caso, o Microsoft 365 usa essa ação quando recebe uma mensagem informando que houve falha na verificação do DMARC de um domínio cujo registro TXT do DMARC tem uma política p=reject. Em vez de excluir ou rejeitar a mensagem, o Microsoft 365 marca a mensagem como spam. Para saber mais sobre o motivo pelo qual o Microsoft 365 é configurado dessa maneira, confira [Como o Microsoft 365 lida com emails de entrada que falham DMARC](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</li><li>**pct.quarantine**: Indica que uma porcentagem menor que 100% das mensagens que não passam na verificação do DMARC será enviada de qualquer forma. Isso significa que houve falha de DMARC na mensagem e a política foi definida como quarentena, mas o campo pct não foi definido como 100% e o sistema aleatoriamente determinou não aplicar a ação do DMARC, conforme a política especificada do domínio.</li><li>**pct.reject**: Indica que uma porcentagem menor que 100% das mensagens que não passam na verificação do DMARC será enviada de qualquer forma. Isso significa que houve falha de DMARC na mensagem e a política foi definida como rejeitar, mas o campo pct não foi definido como 100% e o sistema aleatoriamente determinou não aplicar a ação do DMARC, conforme a política especificada do domínio.</li><li>**permerror**: Ocorreu um erro permanente durante a avaliação do DMARC, como encontrar um registro TXT do DMARC formado incorretamente no DNS. Tentar reenviar esta mensagem provavelmente não terminará com um resultado diferente. Em vez disso, talvez seja necessário entrar em contato com o proprietário do domínio para resolver o problema.</li><li>**temperror**: Ocorreu um erro temporário durante a avaliação do DMARC. Você poderá solicitar ao remetente que reenvie a mensagem mais tarde para processar o email corretamente.</li></ul>|
|`compauth`|Resultado da autenticação composta. Usado pelo Microsoft 365 para combinar vários tipos de autenticação como SPF, DKIM, DMARC ou qualquer outra parte da mensagem para determinar se a mensagem foi autenticada. Usa o domínio De: como base de avaliação.|
|`dkim`|Descreve os resultados da verificação do DKIM para a mensagem. Os valores possíveis incluem:<ul><li>**pass**: Indica que a verificação DKIM para a mensagem foi aprovada.</li><li>**fail (motivo)**: Indica que a verificação do DKIM para a mensagem falhou e o porquê. Por exemplo, se a mensagem não foi assinada ou se a assinatura não foi verificada.</li><li>**none**: Indica que a mensagem não foi assinada. Isso pode ou não indicar que o domínio tem um registro DKIM ou o registro DKIM não foi avaliado como um resultado, apenas que essa mensagem não foi assinada.</li></ul>|
|`dmarc`|Descreve os resultados da verificação do DMARC para a mensagem. Os valores possíveis incluem:<ul><li>**pass**: Indica que a verificação do DMARC para a mensagem foi aprovada.</li><li>**fail**: Indica que houve falha na verificação do DMARC para a mensagem.</li><li>**bestguesspass**: Indica que não existe nenhum registro TXT do DMARC para o domínio, mas, se houvesse, a verificação do DMARC para a mensagem teria passado. Isso ocorre porque o domínio no `5321.MailFrom` endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) corresponde ao domínio no `5322.From` endereço (também conhecido como Endereço De ou Remetente P2).</li><li>**none**: Indica que não há nenhum registro DMARC TXT para o domínio de envio no DNS.|
|`header.d`|Domínio identificado na assinatura DKIM, se houver. Este é o domínio consultado para a chave pública.|
|`header.from`|O domínio do `5322.From` endereço no cabeçalho da mensagem de e-ail (também conhecido como endereço De ou remetente P2). Destinatário, consulte o Endereço De nos clientes de e-mail.|
|`reason`|O motivo pelo qual a autenticação composta foi aprovada ou falhou. O valor é um código de 3 dígitos. Por exemplo: <ul><li>**000**: A mensagem foi reprovada na autenticação explícita (`compauth=fail`). Por exemplo, a mensagem recebeu uma falha DMARC com uma ação de quarentena ou de rejeitada.</li><li>**001**: A mensagem foi reprovada na autenticação implícita (`compauth=fail`). Isso significa que o domínio de envio não tinha registros de autenticação de email publicados ou, se os tinha, eles usavam uma política de falha mais fraca (falha não grave do SPF ou neutra; política do DMARC de `p=none`).</li><li>**002**: A organização possui uma política para o par remetente/domínio, que é explicitamente proibido de enviar emails falsificados. Essa configuração é definida manualmente por um administrador.</li><li>**010**: A mensagem foi reprovada no DMARC com uma ação de rejeição ou quarentena, e o domínio de envio é um dos domínios aceitos da sua organização (isso faz parte da falsificação self-to-self ou dentro da organização).</li><li>**1xx** ou **7xx**: A mensagem passou pela autenticação (`compauth=pass`). Os últimos dois dígitos são códigos internos usados pelo Microsoft 365.</li><li>**2xx**: A mensagem passou facilmente pela autenticação implícita (`compauth=softpass`). Os últimos dois dígitos são códigos internos usados pelo Microsoft 365.</li><li>**3xx**: A mensagem não foi verificada pela autenticação composta (`compauth=none`).</li><li>**4xx** ou **9xx**: A mensagem ignorou a autenticação composta (`compauth=none`). Os últimos dois dígitos são códigos internos usados pelo Microsoft 365.</li><li>**6xx**: A mensagem foi reprovada na autenticação implícita de email, e o domínio de envio é um dos domínios aceitos da sua organização (isso faz parte da falsificação self-to-self ou dentro da organização).</li></ul>|
|`smtp.mailfrom`|O domínio do `5321.MailFrom` endereço (também conhecido como endereço ENVIAR DE, remetente P1 ou remetente do envelope). Este é o endereço de e-mail usado para relatórios de falha na entrega (também conhecido como NDRs ou mensagens de devolução).|
|`spf`|Descreve os resultados da verificação do SPF para a mensagem. Os valores possíveis incluem: <ul><li>`pass (IP address)`: a verificação do SPF para a mensagem foi aprovada e inclui um endereço IP do remetente. O cliente está autorizado a enviar ou retransmitir emails em nome do domínio do remetente.</li><li>`fail (IP address)`: a verificação do SPF para a mensagem reprovada e inclui um endereço IP do remetente. Isso também é conhecido como _falha grave_.</li><li>`softfail (reason)`: o registro SPF designou o host como não tendo permissão para enviar, mas está em transição.</li><li>`neutral`: o registro SPF afirma explicitamente que não informa se o endereço IP está autorizado a enviar.</li><li>`none`: o domínio não tem um registro SPF ou o registro do SPF não é avaliado como um resultado.</li><li>`temperror`: ocorreu um erro temporário. Por exemplo, um erro de DNS. A mesma verificação mais tarde pode ter êxito.</li><li>`permerror`: ocorreu um erro permanente. Por exemplo, o domínio tem um registro SPF mal formatado.</li></ul>|
|
