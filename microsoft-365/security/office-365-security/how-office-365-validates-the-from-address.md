---
title: Como o EOP valida o endereço de para impedir o phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre os tipos de endereços de email que são aceitos ou rejeitados pela proteção do Exchange Online (EOP) e o Outlook.com para ajudar a evitar phishing.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f16bb9b0af1ca5481437ef253c6d36dd519ff9e2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209446"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Como o EOP valida o endereço de para impedir o phishing

Os ataques de phishing são uma ameaça constante para qualquer organização de email. Além de usar [endereços de email de remetente falsificados (forjados)](anti-spoofing-protection.md), os invasores freqüentemente usam valores no endereço de que violam os padrões da Internet. Para ajudar a evitar esse tipo de phishing, o Exchange Online Protection (EOP) e o Outlook.com agora exigem mensagens de entrada para incluir um endereço de conformidade da RFC, conforme descrito neste tópico. Essa imposição foi habilitada em novembro de 2017.

**Observações**:

- Se você receber emails regularmente de organizações malformadas de endereços conforme descrito neste tópico, incentive essas organizações a atualizar seus servidores de email para cumprir com os padrões de segurança modernos.

- O campo de remetente relacionado (usado por enviar em nome e listas de email) não é afetado por esses requisitos. Para obter mais informações, consulte a seguinte postagem [de blog: o que queremos dizer quando nos referimos ao "remetente" de um email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Uma visão geral dos padrões de mensagens de email

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e um conteúdo de mensagem. O envelope da mensagem contém informações necessárias para transmitir e entregar a mensagem entre os servidores SMTP. O conteúdo da mensagem contém os campos de cabeçalho da mensagem (coletivamente chamados de *cabeçalho da mensagem*) e o corpo da mensagem. O envelope da mensagem é descrito em [rfc 5321](https://tools.ietf.org/html/rfc5321), e o cabeçalho da mensagem é descrito em [RFC 5322](https://tools.ietf.org/html/rfc5322). Os destinatários nunca veem o envelope de mensagem real porque é gerado pelo processo de transmissão de mensagens e, na verdade, não faz parte da mensagem.

- O `5321.MailFrom` Endereço (também conhecido como o endereço **de email de** remetente, o remetente P1 ou o remetente do envelope) é o endereço de email que é usado na transmissão SMTP da mensagem. Esse endereço de email geralmente é registrado no campo de cabeçalho de **retorno de caminho** no cabeçalho da mensagem (embora seja possível que o remetente designe um endereço de email de **devolução** diferente).

- O `5322.From` (também conhecido como o endereço de ou o remetente P2) é o endereço de email no campo **de cabeçalho de** e é o endereço de email do remetente que é exibido em clientes de email. O endereço de é o foco dos requisitos neste tópico.

O endereço de é definido detalhadamente em várias RFCs (por exemplo, as seções RFC 5322 3.2.3, 3,4 e 3.4.1 e [RFC 3696](https://tools.ietf.org/html/rfc3696)). Há muitas variações no endereçamento e o que é considerado válido ou inválido. Para simplificar, recomendamos o seguinte formato e definições:

`From: "Display Name" <EmailAddress>`

- **Nome para exibição**: uma frase opcional que descreve o proprietário do endereço de email.

  - Recomendamos que você sempre coloque o nome de exibição entre aspas duplas ("), conforme mostrado. Se o nome de exibição contiver uma vírgula, você _deverá_ colocar a cadeia de caracteres entre aspas duplas por RFC 5322.
  - Se o endereço de inclui um nome de exibição, o valor de EmailAddress deve ser colocado entre colchetes angulares (< >), conforme mostrado.
  - A Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.

- **EmailAddress**: um endereço de email usa o formato `local-part@domain` :

  - **parte local**: uma cadeia de caracteres que identifica a caixa de correio associada ao endereço. Esse valor é exclusivo no domínio. Geralmente, o nome de usuário ou o GUID do proprietário da caixa de correio é usado.
  - **Domain**: o FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email.

  Estas são algumas considerações adicionais para o valor de EmailAddress:

  - Apenas um endereço de email.
  - Recomendamos que você não separe os colchetes angulares com espaços.
  - Não inclua texto adicional após o endereço de email.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exemplos de endereços válidos e inválidos

Os seguintes endereços de email são válidos:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >`(Não recomendado porque há espaços entre os colchetes angulares e o endereço de email).

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>`(Não recomendado porque o nome de exibição não está entre aspas duplas.)

Os seguintes endereços de email são inválidos:

- **Sem endereço de**: algumas mensagens automatizadas não incluem um endereço de remetente. No passado, quando o Microsoft 365 ou Outlook.com recebeu uma mensagem sem um endereço de remetente, o serviço adicionou o seguinte padrão de: endereço para tornar a mensagem ser entregue:

  `From: <>`

  Agora, as mensagens com um endereço de em branco não são mais aceitas.

- `From: Microsoft 365 sender@contoso.com`(O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares).

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Texto após o endereço de email).

- `From: Sender, Example <sender.example@contoso.com>`(O nome de exibição contém uma vírgula, mas não está entre aspas duplas.)

- `From: "Microsoft 365 <sender@contoso.com>"`(Todo o valor está incorretamente entre aspas duplas.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares).

- `From: Microsoft 365<sender@contoso.com>`(Sem espaço entre o nome de exibição e o colchete angular esquerdo)

- `From: "Microsoft 365"<sender@contoso.com>`(Sem espaço entre as aspas duplas de fechamento e o colchete angular esquerdo.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Suprimir respostas automáticas para seu domínio personalizado

Você não pode usar o valor `From: <>` para suprimir respostas automáticas. Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado. As respostas automáticas (e todas as respostas) são supressamente suprimidas porque não há endereços publicados para os quais o servidor de resposta pode enviar mensagens.

- Escolha um domínio de email que não possa receber emails. Por exemplo, se seu domínio primário for contoso.com, você poderá escolher noreply.contoso.com.

- O registro MX nulo desse domínio consiste em um único ponto.

Por exemplo:

```text
noreply.contoso.com IN MX .
```

Para obter mais informações sobre como configurar registros MX, consulte [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Substituir da imposição de endereço

Para ignorar os requisitos de endereço de entrada para emails de entrada, você pode usar a lista de permissões de IP (filtragem de conexão) ou regras de fluxo de emails (também conhecidas como regras de transporte), conforme descrito em [criar listas de remetentes confiáveis no Microsoft 365](create-safe-sender-lists-in-office-365.md).

Você não pode substituir os requisitos de endereço do para email de saída enviado pelo Microsoft 365. Além disso, o Outlook.com não permitirá substituições de nenhum tipo, mesmo através de suporte.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Outras maneiras de evitar e proteger contra o cybercrimes no Microsoft 365

Para saber mais sobre como você pode reforçar sua organização contra phishing, spam, violações de dados e outras ameaças, Confira as [10 maneiras principais de proteger os planos do Microsoft 365 para empresas](../../admin/security-and-compliance/secure-your-business-data.md).
