---
title: Como a Microsoft 365 valida o endereço de origem para impedir o phishing
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
description: 'Para ajudar a evitar phishing, o Microsoft 365 e o Outlook.com agora exigem a conformidade RFC de: addresses.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef361c7009cc8903ab2721d299412b7d44a4f87c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034077"
---
# <a name="how-microsoft-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="c22ab-103">Como a Microsoft 365 valida o endereço de origem para impedir o phishing</span><span class="sxs-lookup"><span data-stu-id="c22ab-103">How Microsoft 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="c22ab-104">As contas de email do Microsoft 365 recebem um número cada vez maior de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="c22ab-104">Microsoft 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="c22ab-105">Além de usar [endereços de email de remetente falsificados (forjados)](anti-spoofing-protection.md), os invasores freqüentemente usam valores no endereço de que violam os padrões da Internet.</span><span class="sxs-lookup"><span data-stu-id="c22ab-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="c22ab-106">Para ajudar a evitar esse tipo de phishing, o Microsoft 365 e o Outlook.com agora exigem mensagens de entrada para incluir um endereço de conformidade da RFC, conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c22ab-106">To help prevent this type of phishing, Microsoft 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="c22ab-107">Essa imposição foi habilitada em novembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="c22ab-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="c22ab-108">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c22ab-108">**Notes**:</span></span>

- <span data-ttu-id="c22ab-109">Se você receber emails regularmente de organizações malformadas de endereços conforme descrito neste tópico, incentive essas organizações a atualizar seus servidores de email para cumprir com os padrões de segurança modernos.</span><span class="sxs-lookup"><span data-stu-id="c22ab-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="c22ab-110">O campo de remetente relacionado (usado por enviar em nome e listas de email) não é afetado por esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="c22ab-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="c22ab-111">Para obter mais informações, consulte a seguinte postagem [de blog: o que queremos dizer quando nos referimos ao "remetente" de um email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="c22ab-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="c22ab-112">Uma visão geral dos padrões de mensagens de email</span><span class="sxs-lookup"><span data-stu-id="c22ab-112">An overview of email message standards</span></span>

<span data-ttu-id="c22ab-113">Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e um conteúdo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="c22ab-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="c22ab-114">O envelope da mensagem contém informações necessárias para transmitir e entregar a mensagem entre os servidores SMTP.</span><span class="sxs-lookup"><span data-stu-id="c22ab-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="c22ab-115">O conteúdo da mensagem contém os campos de cabeçalho da mensagem (coletivamente chamados de *cabeçalho da mensagem*) e o corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c22ab-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="c22ab-116">O envelope da mensagem é descrito em [rfc 5321](https://tools.ietf.org/html/rfc5321), e o cabeçalho da mensagem é descrito em [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="c22ab-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="c22ab-117">Os destinatários nunca veem o envelope de mensagem real porque é gerado pelo processo de transmissão de mensagens e, na verdade, não faz parte da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c22ab-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="c22ab-118">O `5321.MailFrom` endereço (também conhecido como o endereço **de email de** remetente, o remetente P1 ou o remetente do envelope) é o endereço de email que é usado na transmissão SMTP da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c22ab-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="c22ab-119">Esse endereço de email geralmente é registrado no campo de cabeçalho de **retorno de caminho** no cabeçalho da mensagem (embora seja possível que o remetente designe um endereço de email de **devolução** diferente).</span><span class="sxs-lookup"><span data-stu-id="c22ab-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="c22ab-120">O `5322.From` (também conhecido como o endereço de ou o remetente P2) é o endereço de email no campo **de cabeçalho de** e é o endereço de email do remetente que é exibido em clientes de email.</span><span class="sxs-lookup"><span data-stu-id="c22ab-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="c22ab-121">O endereço de é o foco dos requisitos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c22ab-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="c22ab-122">O endereço de é definido detalhadamente em várias RFCs (por exemplo, as seções RFC 5322 3.2.3, 3,4 e 3.4.1 e [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="c22ab-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="c22ab-123">Há muitas variações no endereçamento e o que é considerado válido ou inválido.</span><span class="sxs-lookup"><span data-stu-id="c22ab-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="c22ab-124">Para simplificar, recomendamos o seguinte formato e definições:</span><span class="sxs-lookup"><span data-stu-id="c22ab-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="c22ab-125">**Nome para exibição**: uma frase opcional que descreve o proprietário do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c22ab-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="c22ab-126">Recomendamos que você sempre coloque o nome de exibição entre aspas duplas ("), conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="c22ab-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="c22ab-127">Se o nome de exibição contiver uma vírgula, você _deverá_ colocar a cadeia de caracteres entre aspas duplas por RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="c22ab-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="c22ab-128">Se o endereço de inclui um nome de exibição, o valor de EmailAddress deve ser colocado entre colchetes angulares (< >), conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="c22ab-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="c22ab-129">A Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c22ab-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="c22ab-130">**EmailAddress**: um endereço de email usa o `local-part@domain`formato:</span><span class="sxs-lookup"><span data-stu-id="c22ab-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="c22ab-131">**parte local**: uma cadeia de caracteres que identifica a caixa de correio associada ao endereço.</span><span class="sxs-lookup"><span data-stu-id="c22ab-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="c22ab-132">Esse valor é exclusivo no domínio.</span><span class="sxs-lookup"><span data-stu-id="c22ab-132">This value is unique within the domain.</span></span> <span data-ttu-id="c22ab-133">Geralmente, o nome de usuário ou o GUID do proprietário da caixa de correio é usado.</span><span class="sxs-lookup"><span data-stu-id="c22ab-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="c22ab-134">**Domain**: o FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c22ab-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="c22ab-135">Estas são algumas considerações adicionais para o valor de EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="c22ab-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="c22ab-136">Apenas um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c22ab-136">Only one email address.</span></span>
  - <span data-ttu-id="c22ab-137">Recomendamos que você não separe os colchetes angulares com espaços.</span><span class="sxs-lookup"><span data-stu-id="c22ab-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="c22ab-138">Não inclua texto adicional após o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c22ab-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="c22ab-139">Exemplos de endereços válidos e inválidos</span><span class="sxs-lookup"><span data-stu-id="c22ab-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="c22ab-140">Os seguintes endereços de email são válidos:</span><span class="sxs-lookup"><span data-stu-id="c22ab-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="c22ab-141">`From: < sender@contoso.com >`(Não recomendado porque há espaços entre os colchetes angulares e o endereço de email).</span><span class="sxs-lookup"><span data-stu-id="c22ab-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="c22ab-142">`From: Microsoft 365 <sender@contoso.com>`(Não recomendado porque o nome de exibição não está entre aspas duplas.)</span><span class="sxs-lookup"><span data-stu-id="c22ab-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="c22ab-143">Os seguintes endereços de email são inválidos:</span><span class="sxs-lookup"><span data-stu-id="c22ab-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="c22ab-144">**Sem endereço de**: algumas mensagens automatizadas não incluem um endereço de remetente.</span><span class="sxs-lookup"><span data-stu-id="c22ab-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="c22ab-145">No passado, quando o Microsoft 365 ou Outlook.com recebeu uma mensagem sem um endereço de remetente, o serviço adicionou o seguinte padrão de: endereço para tornar a mensagem ser entregue:</span><span class="sxs-lookup"><span data-stu-id="c22ab-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="c22ab-146">Agora, as mensagens com um endereço de em branco não são mais aceitas.</span><span class="sxs-lookup"><span data-stu-id="c22ab-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="c22ab-147">`From: Microsoft 365 sender@contoso.com`(O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="c22ab-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="c22ab-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Texto após o endereço de email).</span><span class="sxs-lookup"><span data-stu-id="c22ab-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="c22ab-149">`From: Sender, Example <sender.example@contoso.com>`(O nome de exibição contém uma vírgula, mas não está entre aspas duplas.)</span><span class="sxs-lookup"><span data-stu-id="c22ab-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="c22ab-150">`From: "Microsoft 365 <sender@contoso.com>"`(Todo o valor está incorretamente entre aspas duplas.)</span><span class="sxs-lookup"><span data-stu-id="c22ab-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="c22ab-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(O nome de exibição está presente, mas o endereço de email não está entre colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="c22ab-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="c22ab-152">`From: Microsoft 365<sender@contoso.com>`(Sem espaço entre o nome de exibição e o colchete angular esquerdo)</span><span class="sxs-lookup"><span data-stu-id="c22ab-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="c22ab-153">`From: "Microsoft 365"<sender@contoso.com>`(Sem espaço entre as aspas duplas de fechamento e o colchete angular esquerdo.)</span><span class="sxs-lookup"><span data-stu-id="c22ab-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="c22ab-154">Suprimir respostas automáticas para seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="c22ab-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="c22ab-155">Você não pode usar o `From: <>` valor para suprimir respostas automáticas.</span><span class="sxs-lookup"><span data-stu-id="c22ab-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="c22ab-156">Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="c22ab-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="c22ab-157">As respostas automáticas (e todas as respostas) são supressamente suprimidas porque não há endereços publicados para os quais o servidor de resposta pode enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="c22ab-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="c22ab-158">Escolha um domínio de email que não possa receber emails.</span><span class="sxs-lookup"><span data-stu-id="c22ab-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="c22ab-159">Por exemplo, se seu domínio primário for contoso.com, você poderá escolher noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c22ab-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="c22ab-160">O registro MX nulo desse domínio consiste em um único ponto.</span><span class="sxs-lookup"><span data-stu-id="c22ab-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="c22ab-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c22ab-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="c22ab-162">Para obter mais informações sobre como configurar registros MX, consulte [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c22ab-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="c22ab-163">Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="c22ab-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="c22ab-164">Substituir da imposição de endereço</span><span class="sxs-lookup"><span data-stu-id="c22ab-164">Override From address enforcement</span></span>

<span data-ttu-id="c22ab-165">Para ignorar os requisitos de endereço de entrada para emails de entrada, você pode usar a lista de permissões de IP (filtragem de conexão) ou regras de fluxo de emails (também conhecidas como regras de transporte), conforme descrito em [criar listas de remetentes confiáveis no Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c22ab-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="c22ab-166">Você não pode substituir os requisitos de endereço do para email de saída enviado pelo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c22ab-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="c22ab-167">Além disso, o Outlook.com não permitirá substituições de nenhum tipo, mesmo através de suporte.</span><span class="sxs-lookup"><span data-stu-id="c22ab-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="c22ab-168">Outras maneiras de evitar e proteger contra o cybercrimes no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c22ab-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="c22ab-169">Para saber mais sobre como você pode reforçar sua organização contra phishing, spam, violações de dados e outras ameaças, Confira as [10 maneiras principais de proteger os planos do Microsoft 365 para empresas](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="c22ab-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>