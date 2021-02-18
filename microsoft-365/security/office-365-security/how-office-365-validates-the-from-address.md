---
title: Como o EOP valida o endereço De para evitar phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre os tipos de endereços de email aceitos ou rejeitados pelo Exchange Online Protection (EOP) e Outlook.com ajudar a evitar phishing.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ced200c2e521533c1dec8a9d0917add7ca058f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287814"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Como o EOP valida o endereço De para evitar phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Os ataques de phishing são uma ameaça constante a qualquer organização de email. Além de usar endereços de [email](anti-spoofing-protection.md)de remetente falsificados (forjados), os invasores geralmente usam valores no endereço De que violam os padrões da Internet. Para ajudar a evitar esse tipo de phishing, a Proteção do Exchange Online (EOP) e o Outlook.com agora exigem que as mensagens de entrada incluam um endereço From compatível com RFC, conforme descrito neste artigo. Essa imposição foi habilitada em novembro de 2017.

**Observações**:

- Se você receber emails regularmente de organizações que possuem endereços malformados, conforme descrito neste artigo, incentive essas organizações a atualizar seus servidores de email para atender aos padrões de segurança modernos.

- O campo Remetente relacionado (usado por Enviar em nome e listas de correspondência) não é afetado por esses requisitos. Para obter mais informações, consulte a seguinte postagem no blog: O que significa quando nos [referimos ao "remetente" de um email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Uma visão geral dos padrões de mensagens de email

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem. O envelope da mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP. O conteúdo da mensagem contém campos de título da mensagem (coletivamente chamado de título da *mensagem)* e o corpo da mensagem. O envelope da mensagem é descrito na [RFC 5321](https://tools.ietf.org/html/rfc5321)e o header da mensagem é descrito na [RFC 5322.](https://tools.ietf.org/html/rfc5322) Os destinatários nunca veem o envelope real da mensagem porque ele é gerado pelo processo de transmissão da mensagem e não faz parte realmente da mensagem.

- O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem. Esse endereço de email normalmente é registrado no campo de título **Return-Path** no título da mensagem (embora seja possível para o remetente designar um endereço de email **return-path** diferente).

- O (também conhecido como endereço De ou remetente P2) é o endereço de email no campo de título De e é o endereço de email do remetente exibido nos clientes de `5322.From` email.  O endereço De é o foco dos requisitos neste artigo.

O endereço De é definido em detalhes em vários RFCs (por exemplo, RFC 5322 seções 3.2.3, 3.4 e 3.4.1 e [RFC 3696).](https://tools.ietf.org/html/rfc3696) Há muitas variações no endereçamento e o que é considerado válido ou inválido. Para manter isso simples, recomendamos o seguinte formato e definições:

`From: "Display Name" <EmailAddress>`

- **Nome de** exibição : uma frase opcional que descreve o proprietário do endereço de email.

  - Recomendamos que você sempre coloque o nome de exibição entre aspas duplas (") conforme mostrado. Se o nome de exibição  contiver uma vírgula, você deverá colocar a cadeia de caracteres entre aspas duplas por RFC 5322.
  - Se o endereço De incluir um nome de exibição, o valor EmailAddress deverá estar entre colchetes angulares (< >) conforme mostrado.
  - A Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.

- **EmailAddress**: um endereço de email usa o `local-part@domain` formato:

  - **local-part**: uma cadeia de caracteres que identifica a caixa de correio associada ao endereço. Esse valor é exclusivo dentro do domínio. Frequentemente, o nome de usuário ou GUID do proprietário da caixa de correio é usado.
  - **domínio**: o FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email.

  Estas são algumas considerações adicionais para o valor EmailAddress:

  - Apenas um endereço de email.
  - Recomendamos que você não separe os colchetes angulares com espaços.
  - Não inclua texto adicional após o endereço de email.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exemplos de endereços De válidos e inválidos

Os seguintes endereços de email De são válidos:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Não recomendado porque há espaços entre os colchetes angulares e o endereço de email.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Não recomendado porque o nome de exibição não está entre aspas duplas.)

Os seguintes endereços de email De são inválidos:

- **Endereço Não De:** algumas mensagens automatizadas não incluem um endereço De. No passado, quando o Microsoft 365 ou o Outlook.com recebia uma mensagem sem um endereço De, o serviço adicionou o seguinte endereço De: padrão para tornar a mensagem entregue:

  `From: <>`

  Agora, as mensagens com um endereço De em branco não são mais aceitas.

- `From: Microsoft 365 sender@contoso.com` (O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Texto após o endereço de email.)

- `From: Sender, Example <sender.example@contoso.com>` (O nome de exibição contém uma vírgula, mas não está entre aspas duplas.)

- `From: "Microsoft 365 <sender@contoso.com>"` (O valor inteiro está incorretamente entre aspas duplas.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares.)

- `From: Microsoft 365<sender@contoso.com>` (Não há espaço entre o nome de exibição e o colchete angular esquerdo.)

- `From: "Microsoft 365"<sender@contoso.com>` (Não há espaço entre a aspas duplas de fechamento e o colchete angular esquerdo.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Suprimir respostas automáticas ao seu domínio personalizado

Não é possível usar o valor `From: <>` para suprimir respostas automáticas. Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado. As respostas automáticas (e todas as respostas) são suprimidas naturalmente porque não há endereço publicado para o que o servidor de resposta possa enviar mensagens.

- Escolha um domínio de email que não possa receber emails. Por exemplo, se seu domínio principal for contoso.com, você poderá escolher noreply.contoso.com.

- O registro MX nulo para este domínio consiste em um único período.

Por exemplo:

```text
noreply.contoso.com IN MX .
```

Para obter mais informações sobre como configurar registros MX, consulte Criar registros DNS em qualquer provedor de [hospedagem de DNS para o Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Substituir da imposição do endereço

Para ignorar os requisitos de endereço De para emails de entrada, você pode usar a Lista de IIs (filtragem de conexão) ou as regras de fluxo de email (também conhecidas como regras de transporte) conforme descrito em Criar listas de remetentes seguros no [Microsoft 365.](create-safe-sender-lists-in-office-365.md)

Não é possível substituir os requisitos de endereço De para emails de saída que você envia do Microsoft 365. Além disso, Outlook.com permitirá substituições de qualquer tipo, mesmo por meio do suporte.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Outras maneiras de evitar e proteger contra ataques cibernéticos no Microsoft 365

Para obter mais informações sobre como você pode fortalecer sua organização contra phishing, spam, violações de dados e outras ameaças, confira as 10 principais maneiras de proteger os planos do [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)para empresas.
