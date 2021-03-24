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
description: Os administradores podem aprender sobre os tipos de endereços de email aceitos ou rejeitados pela Proteção do Exchange Online (EOP) e Outlook.com ajudar a evitar phishing.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053173"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Como o EOP valida o endereço De para evitar phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Ataques de phishing são uma ameaça constante para qualquer organização de email. Além de usar endereços de email falsificados [(falsificados),](anti-spoofing-protection.md)os invasores geralmente usam valores no endereço From que violam os padrões da Internet. Para ajudar a evitar esse tipo de phishing, o Exchange Online Protection (EOP) e o Outlook.com agora exigem mensagens de entrada para incluir um endereço From compatível com RFC, conforme descrito neste artigo. Essa imposição foi habilitada em novembro de 2017.

**Observações**:

- Se você receber regularmente emails de organizações malformadas de endereços, conforme descrito neste artigo, incentive essas organizações a atualizar seus servidores de email para atender aos padrões de segurança modernos.

- O campo Remetente relacionado (usado por Enviar em Nome e listas de emails) não é afetado por esses requisitos. Para obter mais informações, consulte a seguinte postagem de blog: O que queremos dizer quando nos referimos ao ["remetente" de um email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).

## <a name="an-overview-of-email-message-standards"></a>Uma visão geral dos padrões de mensagens de email

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem. O envelope de mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP. O conteúdo da mensagem contém campos de header de mensagem (coletivamente chamado de *header* da mensagem ) e o corpo da mensagem. O envelope de mensagem é descrito no [RFC 5321](https://tools.ietf.org/html/rfc5321)e o header da mensagem é descrito em [RFC 5322](https://tools.ietf.org/html/rfc5322). Os destinatários nunca veem o envelope de mensagem real porque ele é gerado pelo processo de transmissão de mensagens e não faz parte da mensagem.

- O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem. Esse endereço de email normalmente é registrado no campo de header **Return-Path** no header da mensagem (embora seja possível que o remetente designe um endereço de email **return-path** diferente).

- O (também conhecido como o endereço De ou remetente P2) é o endereço de email no campo de header From e é o endereço de email do remetente exibido em clientes de `5322.From` email.  O endereço From é o foco dos requisitos neste artigo.

O endereço From é definido em detalhes em vários RFCs (por exemplo, seções RFC 5322 3.2.3, 3.4 e 3.4.1 e [RFC 3696](https://tools.ietf.org/html/rfc3696)). Há muitas variações no endereçamento e o que é considerado válido ou inválido. Para mantê-lo simples, recomendamos o seguinte formato e definições:

`From: "Display Name" <EmailAddress>`

- **Nome da** exibição : uma frase opcional que descreve o proprietário do endereço de email.

  - Recomendamos que você sempre coloque o nome de exibição entre aspas duplas (") conforme mostrado. Se o nome de exibição  contiver uma vírgula, coloque a cadeia de caracteres entre aspas duplas por RFC 5322.
  - Se o endereço From incluir um nome de exibição, o valor EmailAddress deverá estar entre colchetes angulares (< >) conforme mostrado.
  - A Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.

- **EmailAddress**: Um endereço de email usa o formato `local-part@domain` :

  - **local-part**: uma cadeia de caracteres que identifica a caixa de correio associada ao endereço. Esse valor é exclusivo dentro do domínio. Frequentemente, o nome de usuário ou GUID do proprietário da caixa de correio é usado.
  - **domínio**: O FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email.

  Estas são algumas considerações adicionais para o valor EmailAddress:

  - Apenas um endereço de email.
  - Recomendamos que você não separe os colchetes angulares com espaços.
  - Não inclua texto adicional após o endereço de email.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exemplos de endereços De válidos e inválidos

Os seguintes endereços de email from são válidos:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Não recomendado porque há espaços entre os colchetes angulares e o endereço de email.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Não recomendado porque o nome de exibição não está entre aspas duplas.)

Os seguintes endereços de email são inválidos:

- **Não Endereço De**: Algumas mensagens automatizadas não incluem um endereço From. No passado, quando o Microsoft 365 ou Outlook.com recebia uma mensagem sem um endereço From, o serviço adicionou o seguinte endereço padrão De: para tornar a mensagem entregue:

  `From: <>`

  Agora, as mensagens com um endereço From em branco não são mais aceitas.

- `From: Microsoft 365 sender@contoso.com` (O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Texto após o endereço de email.)

- `From: Sender, Example <sender.example@contoso.com>` (O nome de exibição contém uma vírgula, mas não está entre aspas duplas.)

- `From: "Microsoft 365 <sender@contoso.com>"` (O valor inteiro está incorretamente entre aspas duplas.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares.)

- `From: Microsoft 365<sender@contoso.com>` (Nenhum espaço entre o nome de exibição e o colchete de ângulo esquerdo.)

- `From: "Microsoft 365"<sender@contoso.com>` (Sem espaço entre a aspas dupla de fechamento e o colchete de ângulo esquerdo.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Suprimir respostas automáticas ao seu domínio personalizado

Não é possível usar o valor `From: <>` para suprimir respostas automáticas. Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado. As respostas automáticas (e todas as respostas) são suprimidas naturalmente porque não há endereço publicado para o que o servidor respondendo possa enviar mensagens.

- Escolha um domínio de email que não possa receber emails. Por exemplo, se seu domínio primário contoso.com, você pode escolher noreply.contoso.com.

- O registro MX nulo para esse domínio consiste em um único período.

Por exemplo:

```text
noreply.contoso.com IN MX .
```

Para obter mais informações sobre como configurar registros MX, consulte [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Substituir a imposição de endereço

Para ignorar os requisitos de endereço From para email de entrada, você pode usar a Lista de IDs (filtragem de conexão) ou as regras de fluxo de emails (também conhecidas como regras de transporte), conforme descrito em Criar listas de remetentes seguros no [Microsoft 365](create-safe-sender-lists-in-office-365.md).

Não é possível substituir os requisitos de endereço From para emails de saída que você envia do Microsoft 365. Além disso, Outlook.com permitirá substituições de qualquer tipo, mesmo por meio do suporte.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Outras maneiras de evitar e proteger contra crimes cibernéticos no Microsoft 365

Para obter mais informações sobre como fortalecer sua organização contra phishing, spam, violações de dados e outras ameaças, consulte [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).