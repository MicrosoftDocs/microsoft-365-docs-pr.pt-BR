---
title: Usar DMARC para validar emails
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
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Saiba como configurar uma autenticação de mensagem baseada em domínio, relatórios e conformidade (DMARC) para validar as mensagens enviadas da sua organização.
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016314"
---
# <a name="use-dmarc-to-validate-email"></a>Usar DMARC para validar emails

A autenticação de mensagens baseada em domínio, os relatórios e a conformidade ([DMARC](https://dmarc.org)) funciona com a SPF (estrutura de políticas de remetente) e com o DomainKeys Identified Mail (DKIM) para autenticar remetentes de email e garantir que as mensagens confiáveis de sistemas de email de destino sejam enviadas de seu domínio. Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email. O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM.

> [!TIP]
> Visite o catálogo [Associação de Segurança Inteligente da Microsoft (MISA)](https://www.microsoft.com/misapartnercatalog) para exibir os fornecedores de terceiros que oferecem relatórios de DMARC para o Microsoft 365.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>Como o SPF e o DMARC trabalham juntos para proteger o e-mail no Microsoft 365?

 Uma mensagem de email pode conter vários endereços originadores ou de remetente. Esses endereços são usados com finalidades diferentes. Por exemplo, considere esses endereços:

- **Endereço de "Email de"**: identifica o remetente e especifica onde enviar avisos de retorno se algum problema ocorrer com a entrega da mensagem, como notificações de falha na entrega. Isso aparece na parte do envelope de uma mensagem de email, e normalmente não é exibido pelo seu aplicativo de email. Isso algumas vezes é chamado de endereço 5321.MailFrom ou endereço reverso.

- **Endereço "De"** O endereço exibido como o endereço De pelo seu aplicativo de email. Esse endereço identifica o autor do email. Ou seja, a caixa de correio da pessoa ou sistema responsável por escrever a mensagem. Isso também é conhecido como endereço 5322.From.

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

Nesta transcrição, os endereços de remetente são os seguintes:

- Endereço MailFrom (5321.MailFrom): phish@phishing.contoso.com

- Endereço De (5322.From): segurança@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>O que é um registro TXT do DMARC?

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

O registro TXT DMARC da Microsoft tem a seguinte aparência:

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

A Microsoft envia seus relatórios de DMARC à [Agari](https://agari.com), uma terceirizada. A Agari coleta e analisa os relatórios de DMARC. Visite o [catálogo MISA](https://www.microsoft.com/misapartnercatalog) para ver mais fornecedores de terceiros que oferecem relatórios de DMARC para o Microsoft 365.

## <a name="implement-dmarc-for-inbound-mail"></a>Implementar DMARC para email de entrada

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Implementar DMARC para emails de saída do Microsoft 365

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [Etapa 1: Identificar fontes válidas de email para seu domínio](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Etapa 2: Definir o SPF para seu domínio](#step-2-set-up-spf-for-your-domain)

- [Etapa 3: Configurar o DKIM para o seu domínio personalizado](#step-3-set-up-dkim-for-your-custom-domain)

- [Etapa 4: Formar o registro TXT do DMARC para seu domínio](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Etapa 1: Identificar fontes válidas de email para seu domínio

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- Que endereços IP enviam mensagens do meu domínio?

- Para emails enviados de terceiros em meu nome, os domínios de 5321.MailFrom e 5322.From são iguais?

### <a name="step-2-set-up-spf-for-your-domain"></a>Etapa 2: Definir o SPF para seu domínio

Agora que você tem uma lista de todos os seus remetentes válidos, pode seguir as etapas para [Set up SPF in to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

Por exemplo, supondo que contoso.com envia emails do Exchange Online, um servidor Exchange local cujo endereço IP é 192.168.0.1 e um aplicativo Web cujo endereço IP é 192.168.100.100, o registro TXT do SPF teria a seguinte aparência:

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Como prática recomendada, certifique-se de que seu registro TXT do SPF leva em consideração contas de remetentes terceirizados.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>Etapa 3: Configurar o DKIM para o seu domínio personalizado

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

Para obter instruções sobre como configurar o DKIM para seu domínio, incluindo como configurar o DKIM para remetentes terceirizados para que possam imitar o seu domínio, confira [Usar DKIM para validar emails enviados de seu domínio personalizado](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Etapa 4: Formar o registro TXT do DMARC para seu domínio 

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

em que:

- *domain* é o domínio que você deseja proteger. Por padrão, o registro protege os emails do domínio e de todos os seus subdomínios. Por exemplo, se você especificar\_dmarc.contoso.com, então o DMARC protegerá os emails desse domínio e de todos os seus subdomínios, como eletrodomesticos.contoso.com ou encanamento.contoso.com.

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* indica que esta regra deve ser usada para 100% dos emails.

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

Para saber mais sobre quais opções usar, familiarize-se com os conceitos em [Práticas recomendadas para implementar o DMARC no Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).

Exemplos:

- Política definida como none

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Política definida como quarantine

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Política definida como reject

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Práticas recomendadas para implementar o DMARC no Microsoft 365

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. Monitorar o impacto da implementação do DMARC

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. Solicitar que sistemas de email externos coloquem em quarentena as mensagens que não passam na verificação do DMARC

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. Solicitar que sistemas de email externos rejeitem as mensagens que não passam na verificação do DMARC

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Como o Microsoft 365 lida com emails de saída que não passam na verificação do DMARC

Se uma mensagem que está saindo do Microsoft 365 falhar na verificação do DMARC e você tiver a política definida como p=quarentena ou p=rejeitar, a mensagem será direcionada pelo [pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md). Não há cancelamentos para emails de saída.

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Como o Microsoft 365 lida com emails de entrada que não passam na verificação do DMARC

Se a política do DMARC do servidor de envio for `p=reject`, o EOP marca a mensagem como spoof ao invés de rejeitá-la. Em outras palavras, para emails de entrada, o Microsoft 365 trata `p=reject` e `p=quarantine` da mesma maneira. Os administradores podem definir a ação a ser executada nas mensagens classificadas como spoof dentro da [política antiphishing](set-up-anti-phishing-policies.md).

O Microsoft 365 é configurado assim porque alguns emails legítimos podem falhar na verificação do DMARC. Por exemplo, uma mensagem pode não passar na verificação do DMARC se for enviada a uma lista de endereçamento que retransmite a mensagem a todos os participantes da lista. Se o Microsoft 365 rejeitar essas mensagens, as pessoas podem perder emails legítimos e não têm como recuperá-los. Em vez disso, essas mensagens ainda falharão na verificação do DMARC, mas serão marcadas como spam e não rejeitadas. Se quiserem, os usuários ainda podem receber essas mensagens em suas caixas de entrada fazendo o seguinte:

- Os usuários podem adicionar os remetentes seguros individualmente usando seus clientes de email.

- Os administradores podem atualizar o relatório de [Inteligência de Spoof](learn-about-spoof-intelligence.md) para permitir o spoof.

- Os administradores podem criar uma Regra de Transporte do Exchange (ETR) para todos os usuários que permitem mensagens desses remetentes específicos. 

Para obter mais informações, confira [Criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Como o Microsoft 365 usa o Authenticated Received Chain (ARC)

Todas as caixas de correio hospedadas no Microsoft 365 agora terão os benefícios do ARC com capacidade de entrega de mensagens e proteção anti-falsificação aprimoradas. O ARC preserva os resultados de autenticação de email de todos os participantes intermediários, ou saltos, quando um email é roteado do servidor de origem para a caixa de correio do destinatário. Antes do ARC, as modificações realizadas pelos intermediários no roteamento de emails, como as regras de encaminhamento ou assinaturas automáticas, podiam causar falhas no DMARC quando o email chegava à caixa de correio do destinatário. Com o ARC, a preservação criptográfica dos resultados da autenticação permite ao Microsoft 365 verificar a autenticidade do remetente de um email.

Atualmente, o Microsoft 365 usa o ARC para verificar os resultados da autenticação quando a Microsoft é o ARC Sealer, porém está nos planos adicionar suporte para o ARC Sealer de terceiros no futuro.

## <a name="troubleshooting-your-dmarc-implementation"></a>Solucionar problemas com sua implementação do DMARC

Se você tiver configurado os registros MX de seu domínio de forma que o EOP não é a primeira entrada, o DMARC não será aplicado ao seu domínio.

Se você é um cliente e o registro MX primário de seu domínio não aponta para o EOP, você não terá os benefícios do DMARC. Por exemplo, o DMARC não funcionará se você apontar o registro MX para seu servidor de email local e direcionar os emails para o EOP usando um conector. Neste cenário, o domínio receptor é um de seus Domínios Aceitos, mas o EOP não é o MX primário. Por exemplo, suponha que contoso.com aponta seu registro MX para si mesmo e usa o EOP como registro MX secundário. O registro MX de contoso.com tem a seguinte aparência:

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Todos os, ou a maioria dos, emails primeiro serão direcionados a mail.contoso.com, já que este é o MX primário e, então, serão direcionados para o EOP. Em alguns casos, o EOP pode nem estar listado como registro MX e você usa conectores para direcionar os emails. EOP não precisa ser a primeira entrada para a validação do DMARC. Ele só garante a validação, pois nem todos os servidores locais/não O365 farão a verificação de DMARCs.  A DMARC está qualificada para ser imposta para o domínio de um cliente (não para o servidor) ao configurar o registro TXT do DMARC, mas fica até o servidor de recebimento para realmente fazer a imposição.  Se você configurar o EOP como o servidor de recebimento, o EOP fará a imposição de DMARC.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="Um gráfico de solução de problemas para DMARC, cortesia de Daniel Mande":::

## <a name="for-more-information"></a>Para saber mais

Want more information about DMARC? These resources can help.

- [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md) inclui a sintaxe e os campos de cabeçalho usados pelo Microsoft 365 para verificações de DMARC.

- Faça a [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) do M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Use a lista de verificação em [dmarcian](https://space.dmarcian.com/deployment/).

- Vá direto à fonte em [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Confira também

[Como o Microsoft 365 usa SPF (Sender Policy Framework) para evitar falsificação](how-office-365-uses-spf-to-prevent-spoofing.md)

[Configure a SPF no Microsoft 365 para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[Use o DKIM para validar emails enviados de seu domínio personalizado no Microsoft 365](use-dkim-to-validate-outbound-email.md)
