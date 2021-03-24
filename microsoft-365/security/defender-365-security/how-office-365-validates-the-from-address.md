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
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="94b2c-103">Como o EOP valida o endereço De para evitar phishing</span><span class="sxs-lookup"><span data-stu-id="94b2c-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94b2c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="94b2c-104">**Applies to**</span></span>
- [<span data-ttu-id="94b2c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="94b2c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94b2c-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="94b2c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94b2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94b2c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="94b2c-108">Ataques de phishing são uma ameaça constante para qualquer organização de email.</span><span class="sxs-lookup"><span data-stu-id="94b2c-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="94b2c-109">Além de usar endereços de email falsificados [(falsificados),](anti-spoofing-protection.md)os invasores geralmente usam valores no endereço From que violam os padrões da Internet.</span><span class="sxs-lookup"><span data-stu-id="94b2c-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="94b2c-110">Para ajudar a evitar esse tipo de phishing, o Exchange Online Protection (EOP) e o Outlook.com agora exigem mensagens de entrada para incluir um endereço From compatível com RFC, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="94b2c-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="94b2c-111">Essa imposição foi habilitada em novembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="94b2c-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="94b2c-112">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="94b2c-112">**Notes**:</span></span>

- <span data-ttu-id="94b2c-113">Se você receber regularmente emails de organizações malformadas de endereços, conforme descrito neste artigo, incentive essas organizações a atualizar seus servidores de email para atender aos padrões de segurança modernos.</span><span class="sxs-lookup"><span data-stu-id="94b2c-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="94b2c-114">O campo Remetente relacionado (usado por Enviar em Nome e listas de emails) não é afetado por esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="94b2c-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="94b2c-115">Para obter mais informações, consulte a seguinte postagem de blog: O que queremos dizer quando nos referimos ao ["remetente" de um email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span><span class="sxs-lookup"><span data-stu-id="94b2c-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="94b2c-116">Uma visão geral dos padrões de mensagens de email</span><span class="sxs-lookup"><span data-stu-id="94b2c-116">An overview of email message standards</span></span>

<span data-ttu-id="94b2c-117">Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="94b2c-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="94b2c-118">O envelope de mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP.</span><span class="sxs-lookup"><span data-stu-id="94b2c-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="94b2c-119">O conteúdo da mensagem contém campos de header de mensagem (coletivamente chamado de *header* da mensagem ) e o corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94b2c-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="94b2c-120">O envelope de mensagem é descrito no [RFC 5321](https://tools.ietf.org/html/rfc5321)e o header da mensagem é descrito em [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="94b2c-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="94b2c-121">Os destinatários nunca veem o envelope de mensagem real porque ele é gerado pelo processo de transmissão de mensagens e não faz parte da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94b2c-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="94b2c-122">O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94b2c-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="94b2c-123">Esse endereço de email normalmente é registrado no campo de header **Return-Path** no header da mensagem (embora seja possível que o remetente designe um endereço de email **return-path** diferente).</span><span class="sxs-lookup"><span data-stu-id="94b2c-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="94b2c-124">O (também conhecido como o endereço De ou remetente P2) é o endereço de email no campo de header From e é o endereço de email do remetente exibido em clientes de `5322.From` email. </span><span class="sxs-lookup"><span data-stu-id="94b2c-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="94b2c-125">O endereço From é o foco dos requisitos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="94b2c-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="94b2c-126">O endereço From é definido em detalhes em vários RFCs (por exemplo, seções RFC 5322 3.2.3, 3.4 e 3.4.1 e [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="94b2c-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="94b2c-127">Há muitas variações no endereçamento e o que é considerado válido ou inválido.</span><span class="sxs-lookup"><span data-stu-id="94b2c-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="94b2c-128">Para mantê-lo simples, recomendamos o seguinte formato e definições:</span><span class="sxs-lookup"><span data-stu-id="94b2c-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="94b2c-129">**Nome da** exibição : uma frase opcional que descreve o proprietário do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94b2c-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="94b2c-130">Recomendamos que você sempre coloque o nome de exibição entre aspas duplas (") conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="94b2c-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="94b2c-131">Se o nome de exibição  contiver uma vírgula, coloque a cadeia de caracteres entre aspas duplas por RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="94b2c-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="94b2c-132">Se o endereço From incluir um nome de exibição, o valor EmailAddress deverá estar entre colchetes angulares (< >) conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="94b2c-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="94b2c-133">A Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94b2c-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="94b2c-134">**EmailAddress**: Um endereço de email usa o formato `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="94b2c-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="94b2c-135">**local-part**: uma cadeia de caracteres que identifica a caixa de correio associada ao endereço.</span><span class="sxs-lookup"><span data-stu-id="94b2c-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="94b2c-136">Esse valor é exclusivo dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="94b2c-136">This value is unique within the domain.</span></span> <span data-ttu-id="94b2c-137">Frequentemente, o nome de usuário ou GUID do proprietário da caixa de correio é usado.</span><span class="sxs-lookup"><span data-stu-id="94b2c-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="94b2c-138">**domínio**: O FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94b2c-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="94b2c-139">Estas são algumas considerações adicionais para o valor EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="94b2c-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="94b2c-140">Apenas um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94b2c-140">Only one email address.</span></span>
  - <span data-ttu-id="94b2c-141">Recomendamos que você não separe os colchetes angulares com espaços.</span><span class="sxs-lookup"><span data-stu-id="94b2c-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="94b2c-142">Não inclua texto adicional após o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94b2c-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="94b2c-143">Exemplos de endereços De válidos e inválidos</span><span class="sxs-lookup"><span data-stu-id="94b2c-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="94b2c-144">Os seguintes endereços de email from são válidos:</span><span class="sxs-lookup"><span data-stu-id="94b2c-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="94b2c-145">`From: < sender@contoso.com >` (Não recomendado porque há espaços entre os colchetes angulares e o endereço de email.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="94b2c-146">`From: Microsoft 365 <sender@contoso.com>` (Não recomendado porque o nome de exibição não está entre aspas duplas.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="94b2c-147">Os seguintes endereços de email são inválidos:</span><span class="sxs-lookup"><span data-stu-id="94b2c-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="94b2c-148">**Não Endereço De**: Algumas mensagens automatizadas não incluem um endereço From.</span><span class="sxs-lookup"><span data-stu-id="94b2c-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="94b2c-149">No passado, quando o Microsoft 365 ou Outlook.com recebia uma mensagem sem um endereço From, o serviço adicionou o seguinte endereço padrão De: para tornar a mensagem entregue:</span><span class="sxs-lookup"><span data-stu-id="94b2c-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="94b2c-150">Agora, as mensagens com um endereço From em branco não são mais aceitas.</span><span class="sxs-lookup"><span data-stu-id="94b2c-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="94b2c-151">`From: Microsoft 365 sender@contoso.com` (O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="94b2c-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Texto após o endereço de email.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="94b2c-153">`From: Sender, Example <sender.example@contoso.com>` (O nome de exibição contém uma vírgula, mas não está entre aspas duplas.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="94b2c-154">`From: "Microsoft 365 <sender@contoso.com>"` (O valor inteiro está incorretamente entre aspas duplas.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="94b2c-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="94b2c-156">`From: Microsoft 365<sender@contoso.com>` (Nenhum espaço entre o nome de exibição e o colchete de ângulo esquerdo.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="94b2c-157">`From: "Microsoft 365"<sender@contoso.com>` (Sem espaço entre a aspas dupla de fechamento e o colchete de ângulo esquerdo.)</span><span class="sxs-lookup"><span data-stu-id="94b2c-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="94b2c-158">Suprimir respostas automáticas ao seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="94b2c-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="94b2c-159">Não é possível usar o valor `From: <>` para suprimir respostas automáticas.</span><span class="sxs-lookup"><span data-stu-id="94b2c-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="94b2c-160">Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="94b2c-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="94b2c-161">As respostas automáticas (e todas as respostas) são suprimidas naturalmente porque não há endereço publicado para o que o servidor respondendo possa enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="94b2c-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="94b2c-162">Escolha um domínio de email que não possa receber emails.</span><span class="sxs-lookup"><span data-stu-id="94b2c-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="94b2c-163">Por exemplo, se seu domínio primário contoso.com, você pode escolher noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94b2c-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="94b2c-164">O registro MX nulo para esse domínio consiste em um único período.</span><span class="sxs-lookup"><span data-stu-id="94b2c-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="94b2c-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="94b2c-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="94b2c-166">Para obter mais informações sobre como configurar registros MX, consulte [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="94b2c-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="94b2c-167">Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="94b2c-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="94b2c-168">Substituir a imposição de endereço</span><span class="sxs-lookup"><span data-stu-id="94b2c-168">Override From address enforcement</span></span>

<span data-ttu-id="94b2c-169">Para ignorar os requisitos de endereço From para email de entrada, você pode usar a Lista de IDs (filtragem de conexão) ou as regras de fluxo de emails (também conhecidas como regras de transporte), conforme descrito em Criar listas de remetentes seguros no [Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="94b2c-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="94b2c-170">Não é possível substituir os requisitos de endereço From para emails de saída que você envia do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94b2c-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="94b2c-171">Além disso, Outlook.com permitirá substituições de qualquer tipo, mesmo por meio do suporte.</span><span class="sxs-lookup"><span data-stu-id="94b2c-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="94b2c-172">Outras maneiras de evitar e proteger contra crimes cibernéticos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94b2c-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="94b2c-173">Para obter mais informações sobre como fortalecer sua organização contra phishing, spam, violações de dados e outras ameaças, consulte [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="94b2c-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>