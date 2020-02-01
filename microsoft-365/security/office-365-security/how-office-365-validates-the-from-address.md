---
title: Como o Office 365 valida o endereço de para impedir o phishing
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
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
description: 'Para ajudar a evitar phishing, o Office 365 e o Outlook.com agora exigem a conformidade RFC de: endereços.'
ms.openlocfilehash: 6459faa22f29017568747b84bbd2935aad6763d1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599178"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="72b5a-103">Como o Office 365 valida o endereço de para impedir o phishing</span><span class="sxs-lookup"><span data-stu-id="72b5a-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="72b5a-104">As contas de email do Office 365 e do Outlook.com recebem um número cada vez maior de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="72b5a-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="72b5a-105">Uma técnica usada por phishers é enviar mensagens com valores para o endereço de: que não são compatíveis com a [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="72b5a-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="72b5a-106">O endereço de: também é chamado de endereço 5322. from.</span><span class="sxs-lookup"><span data-stu-id="72b5a-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="72b5a-107">Para ajudar a evitar esse tipo de phishing, o Office 365 e o Outlook.com exigem que as mensagens recebidas pelo serviço incluam um endereço compatível com RFC de:, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="72b5a-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="72b5a-108">As informações deste artigo exigem que você tenha uma compreensão básica do formato geral dos endereços de email.</span><span class="sxs-lookup"><span data-stu-id="72b5a-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="72b5a-109">Para obter mais informações, consulte [rfc 5322](https://tools.ietf.org/html/rfc5322) (principalmente as seções 3.2.3, 3,4 e 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), bem como [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="72b5a-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="72b5a-110">Este artigo trata da imposição de política para o endereço 5322. from.</span><span class="sxs-lookup"><span data-stu-id="72b5a-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="72b5a-111">Este artigo não se refere ao endereço 5321. MailFrom.</span><span class="sxs-lookup"><span data-stu-id="72b5a-111">This article is not about the 5321.MailFrom address.</span></span>

<span data-ttu-id="72b5a-112">Infelizmente, ainda há alguns servidores de email herdados na Internet que continuam a enviar mensagens de email "legítimas" com um endereço ausente ou malformado de:.</span><span class="sxs-lookup"><span data-stu-id="72b5a-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="72b5a-113">Se você receber emails regularmente das organizações que usam esses sistemas herdados, incentive essas organizações a atualizar seus servidores de email para que estejam em conformidade com os padrões de segurança modernos.</span><span class="sxs-lookup"><span data-stu-id="72b5a-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>

<span data-ttu-id="72b5a-114">A Microsoft começará a implantar as políticas descritas neste artigo em 9 de novembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="72b5a-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>

## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="72b5a-115">Como o Office 365 aplica o uso de um endereço válido de: para impedir ataques de phishing</span><span class="sxs-lookup"><span data-stu-id="72b5a-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="72b5a-116">O Office 365 está fazendo alterações no modo como ele impõe o uso do endereço from: nas mensagens recebidas para melhor proteção contra ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="72b5a-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="72b5a-117">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="72b5a-117">In this article:</span></span>

- [<span data-ttu-id="72b5a-118">Todas as mensagens devem incluir um endereço válido de:</span><span class="sxs-lookup"><span data-stu-id="72b5a-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)

- [<span data-ttu-id="72b5a-119">Formato do endereço de: se você não incluir um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="72b5a-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)

- [<span data-ttu-id="72b5a-120">Formato do endereço de: se você incluir um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="72b5a-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)

- [<span data-ttu-id="72b5a-121">Exemplos adicionais de endereços válidos e inválidos de:</span><span class="sxs-lookup"><span data-stu-id="72b5a-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)

- [<span data-ttu-id="72b5a-122">Suprimir respostas automáticas para seu domínio personalizado sem quebrar a de: política</span><span class="sxs-lookup"><span data-stu-id="72b5a-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)

- [<span data-ttu-id="72b5a-123">Substituindo o Office 365 de: política de aplicação de endereços</span><span class="sxs-lookup"><span data-stu-id="72b5a-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)

- [<span data-ttu-id="72b5a-124">Outras maneiras de evitar e proteger contra o cybercrimes no Office 365</span><span class="sxs-lookup"><span data-stu-id="72b5a-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)

<span data-ttu-id="72b5a-125">Enviar em nome de outro usuário não é afetado por essa alteração, para obter mais detalhes, leia o blog de Terry Zink "[o que queremos dizer quando nos referimos ao" remetente "de um email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="72b5a-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>

### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="72b5a-126">Todas as mensagens devem incluir um endereço válido de:</span><span class="sxs-lookup"><span data-stu-id="72b5a-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="72b5a-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-127"><a name="MustIncludeFromAddress"> </a></span></span>

<span data-ttu-id="72b5a-128">Algumas mensagens automatizadas não incluem um endereço de: ao serem enviados.</span><span class="sxs-lookup"><span data-stu-id="72b5a-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="72b5a-129">No passado, quando o Office 365 ou Outlook.com recebeu uma mensagem sem um endereço de:, o serviço adicionou o seguinte padrão de: endereço à mensagem para torná-lo possível:</span><span class="sxs-lookup"><span data-stu-id="72b5a-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>

```
From: <>
```

<span data-ttu-id="72b5a-130">A partir de 9 de novembro de 2017, o Office 365 será distribuir alterações em seus datacenters e servidores de email que aplicarão uma nova regra onde as mensagens sem um endereço de: não serão mais aceitas pelo Office 365 ou Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="72b5a-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="72b5a-131">Em vez disso, todas as mensagens recebidas pelo Office 365 já devem conter um endereço válido de:.</span><span class="sxs-lookup"><span data-stu-id="72b5a-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="72b5a-132">Caso contrário, a mensagem será enviada para as pastas lixo eletrônico ou itens excluídos no Outlook.com e no Office 365.</span><span class="sxs-lookup"><span data-stu-id="72b5a-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span>

### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="72b5a-133">Visão geral da sintaxe: formato válido para o endereço de: do Office 365</span><span class="sxs-lookup"><span data-stu-id="72b5a-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="72b5a-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-134"><a name="SyntaxOverviewFromAddress"> </a></span></span>

<span data-ttu-id="72b5a-135">O formato para o valor do endereço de: é definido em detalhes em várias RFCs.</span><span class="sxs-lookup"><span data-stu-id="72b5a-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="72b5a-136">Há várias variações no endereçamento e o que pode ser considerado válido ou inválido.</span><span class="sxs-lookup"><span data-stu-id="72b5a-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="72b5a-137">Para simplificar, a Microsoft recomenda que você use o seguinte formato e definições:</span><span class="sxs-lookup"><span data-stu-id="72b5a-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>

```
From: "displayname " <emailaddress >
```

<span data-ttu-id="72b5a-138">Onde:</span><span class="sxs-lookup"><span data-stu-id="72b5a-138">Where:</span></span>

- <span data-ttu-id="72b5a-139">Opcion  *DisplayName* é uma frase que descreve o proprietário do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="72b5a-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="72b5a-140">Por exemplo, este pode ser um nome mais amigável para descrever o remetente do que o nome da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="72b5a-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="72b5a-141">O uso de um nome de exibição é opcional.</span><span class="sxs-lookup"><span data-stu-id="72b5a-141">Using a display name is optional.</span></span> <span data-ttu-id="72b5a-142">No entanto, se você optar por usar um nome de exibição, a Microsoft recomenda que você sempre o coloque entre aspas, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="72b5a-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span>

- <span data-ttu-id="72b5a-143">Precisam  *EmailAddress* é composto por:</span><span class="sxs-lookup"><span data-stu-id="72b5a-143">(Required)  *emailaddress*  is made up of:</span></span>

  ```
  local-part @domain
  ```

    <span data-ttu-id="72b5a-144">Onde:</span><span class="sxs-lookup"><span data-stu-id="72b5a-144">Where:</span></span>

  - <span data-ttu-id="72b5a-145">Precisam  *local-Part* é uma cadeia de caracteres que identifica a caixa de correio associada ao endereço.</span><span class="sxs-lookup"><span data-stu-id="72b5a-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="72b5a-146">Isso é exclusivo no domínio.</span><span class="sxs-lookup"><span data-stu-id="72b5a-146">This is unique within the domain.</span></span> <span data-ttu-id="72b5a-147">Geralmente, o nome de usuário ou o GUID do proprietário da caixa de correio é usado como o valor para a parte local.</span><span class="sxs-lookup"><span data-stu-id="72b5a-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span>

  - <span data-ttu-id="72b5a-148">Precisam  *Domain* é o FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="72b5a-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span>

### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="72b5a-149">Formato do endereço de: se você não incluir um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="72b5a-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="72b5a-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-150"><a name="FormatNoDisplayName"> </a></span></span>

<span data-ttu-id="72b5a-151">Um endereço com formatação adequada de: que não inclua um nome de exibição inclui apenas um endereço de email único com ou sem colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="72b5a-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="72b5a-152">A Microsoft recomenda que você não separe os colchetes angulares com espaços.</span><span class="sxs-lookup"><span data-stu-id="72b5a-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="72b5a-153">Além disso, não inclua nada após o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="72b5a-153">In addition, don't include anything after the email address.</span></span>

<span data-ttu-id="72b5a-154">Os exemplos a seguir são válidos:</span><span class="sxs-lookup"><span data-stu-id="72b5a-154">The following examples are valid:</span></span>

```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="72b5a-155">O exemplo a seguir é válido, mas não é recomendado, pois contém espaços entre os colchetes angulares e o endereço de email:</span><span class="sxs-lookup"><span data-stu-id="72b5a-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>

```
From: < sender@contoso.com >
```

<span data-ttu-id="72b5a-156">O exemplo a seguir é inválido porque contém texto após o endereço de email:</span><span class="sxs-lookup"><span data-stu-id="72b5a-156">The following example is invalid because it contains text after the email address:</span></span>

```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="72b5a-157">Formato do endereço de: se você incluir um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="72b5a-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="72b5a-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-158"><a name="FormatDisplayName"> </a></span></span>

<span data-ttu-id="72b5a-159">Para: endereços que incluem um valor para o nome de exibição, as seguintes regras se aplicam:</span><span class="sxs-lookup"><span data-stu-id="72b5a-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>

- <span data-ttu-id="72b5a-160">Se o endereço do remetente incluir um nome de exibição e o nome de exibição incluir uma vírgula, o nome de exibição deverá ser colocado entre aspas.</span><span class="sxs-lookup"><span data-stu-id="72b5a-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="72b5a-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="72b5a-161">For example:</span></span>

    <span data-ttu-id="72b5a-162">O exemplo a seguir é válido:</span><span class="sxs-lookup"><span data-stu-id="72b5a-162">The following example is valid:</span></span>

  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="72b5a-163">O exemplo a seguir não é válido:</span><span class="sxs-lookup"><span data-stu-id="72b5a-163">The following example is not valid:</span></span>

  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="72b5a-164">Não colocar o nome de exibição entre aspas se esse nome de exibição incluir uma vírgula é inválido de acordo com a RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="72b5a-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>

    <span data-ttu-id="72b5a-165">Como prática recomendada, coloque aspas em torno do nome de exibição, independentemente de haver ou não uma vírgula dentro do nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="72b5a-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>

- <span data-ttu-id="72b5a-166">Se o endereço do remetente incluir um nome de exibição, o endereço de email deverá ser colocado entre colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="72b5a-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>

    <span data-ttu-id="72b5a-167">Como prática recomendada, a Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="72b5a-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="72b5a-168">Exemplos adicionais de endereços válidos e inválidos de:</span><span class="sxs-lookup"><span data-stu-id="72b5a-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="72b5a-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-169"><a name="Examples"> </a></span></span>

- <span data-ttu-id="72b5a-170">Inválido</span><span class="sxs-lookup"><span data-stu-id="72b5a-170">Valid:</span></span>

  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="72b5a-171">Inválido.</span><span class="sxs-lookup"><span data-stu-id="72b5a-171">Invalid.</span></span> <span data-ttu-id="72b5a-172">O endereço de email não está entre colchetes angulares:</span><span class="sxs-lookup"><span data-stu-id="72b5a-172">The email address is not enclosed with angle brackets:</span></span>

  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="72b5a-173">Válido, mas não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="72b5a-173">Valid, but not recommended.</span></span> <span data-ttu-id="72b5a-174">O nome de exibição não está entre aspas.</span><span class="sxs-lookup"><span data-stu-id="72b5a-174">The display name is not in quotes.</span></span> <span data-ttu-id="72b5a-175">Como prática recomendada, sempre coloque o nome de exibição entre aspas:</span><span class="sxs-lookup"><span data-stu-id="72b5a-175">As a best practice, always put quotation marks around the display name:</span></span>

  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="72b5a-176">Inválido.</span><span class="sxs-lookup"><span data-stu-id="72b5a-176">Invalid.</span></span> <span data-ttu-id="72b5a-177">Tudo está entre aspas, não apenas o nome de exibição:</span><span class="sxs-lookup"><span data-stu-id="72b5a-177">Everything is enclosed within quotation marks, not just the display name:</span></span>

  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="72b5a-178">Inválido.</span><span class="sxs-lookup"><span data-stu-id="72b5a-178">Invalid.</span></span> <span data-ttu-id="72b5a-179">Não há colchetes angulares em torno do endereço de email:</span><span class="sxs-lookup"><span data-stu-id="72b5a-179">There are no angle brackets around the email address:</span></span>

  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="72b5a-180">Inválido.</span><span class="sxs-lookup"><span data-stu-id="72b5a-180">Invalid.</span></span> <span data-ttu-id="72b5a-181">Não há espaço entre o nome de exibição e o colchete angular esquerdo:</span><span class="sxs-lookup"><span data-stu-id="72b5a-181">There is no space between the display name and left angle bracket:</span></span>

  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="72b5a-182">Inválido.</span><span class="sxs-lookup"><span data-stu-id="72b5a-182">Invalid.</span></span> <span data-ttu-id="72b5a-183">Não há espaço entre as aspas de fechamento ao redor do nome para exibição e o colchete angular esquerdo.</span><span class="sxs-lookup"><span data-stu-id="72b5a-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>

  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="72b5a-184">Suprimir respostas automáticas para seu domínio personalizado sem quebrar a de: política</span><span class="sxs-lookup"><span data-stu-id="72b5a-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="72b5a-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-185"><a name="SuppressAutoReply"> </a></span></span>

<span data-ttu-id="72b5a-186">Com o novo de: imposição de política, você não pode mais usar \< \> de: para suprimir respostas automáticas.</span><span class="sxs-lookup"><span data-stu-id="72b5a-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="72b5a-187">Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="72b5a-187">Instead, you need to set up a null MX record for your custom domain.</span></span>

<span data-ttu-id="72b5a-188">O registro MX (Mail Exchanger) é um registro de recurso no DNS que identifica o servidor de email que recebe os emails do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="72b5a-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="72b5a-189">As respostas automáticas (e todas as respostas) são suprimidas naturalmente porque não há endereço publicado ao qual o servidor de resposta pode enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="72b5a-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>

<span data-ttu-id="72b5a-190">Quando você configura um registro MX nulo para seu domínio personalizado:</span><span class="sxs-lookup"><span data-stu-id="72b5a-190">When you set up a null MX record for your custom domain:</span></span>

- <span data-ttu-id="72b5a-191">Escolha um domínio do qual enviar mensagens que não aceita (recebe) email.</span><span class="sxs-lookup"><span data-stu-id="72b5a-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="72b5a-192">Por exemplo, se seu domínio primário for contoso.com, você poderá escolher noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72b5a-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="72b5a-193">Configure o registro MX nulo para seu domínio.</span><span class="sxs-lookup"><span data-stu-id="72b5a-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="72b5a-194">Um registro MX nulo consiste em um único ponto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="72b5a-194">A null MX record consists of a single dot, for example:</span></span>

  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="72b5a-195">Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="72b5a-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="72b5a-196">Substituindo o Office 365 de: política de aplicação de endereços</span><span class="sxs-lookup"><span data-stu-id="72b5a-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="72b5a-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-197"><a name="Override"> </a></span></span>

<span data-ttu-id="72b5a-198">Após a implantação da nova política, você só pode ignorar esta política para emails de entrada recebidos do Office 365 usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="72b5a-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span>

- <span data-ttu-id="72b5a-199">Listas de IPs permitidos</span><span class="sxs-lookup"><span data-stu-id="72b5a-199">IP allow lists</span></span>

- <span data-ttu-id="72b5a-200">Regras de fluxo de email do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="72b5a-200">Exchange Online mail flow rules</span></span>

<span data-ttu-id="72b5a-201">A Microsoft recomenda a substituição da aplicação da diretiva from:.</span><span class="sxs-lookup"><span data-stu-id="72b5a-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="72b5a-202">A substituição dessa política pode aumentar o risco de exposição da sua organização a spam, phishing e outros cybercrimes.</span><span class="sxs-lookup"><span data-stu-id="72b5a-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>

<span data-ttu-id="72b5a-203">Você não pode substituir esta política para emails de saída enviados no Office 365.</span><span class="sxs-lookup"><span data-stu-id="72b5a-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="72b5a-204">Além disso, o Outlook.com não permitirá substituições de nenhum tipo, mesmo através de suporte.</span><span class="sxs-lookup"><span data-stu-id="72b5a-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="72b5a-205">Outras maneiras de evitar e proteger contra o cybercrimes no Office 365</span><span class="sxs-lookup"><span data-stu-id="72b5a-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="72b5a-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="72b5a-206"><a name="OtherProtection"> </a></span></span>

<span data-ttu-id="72b5a-207">Para obter mais informações sobre como você pode reforçar sua organização contra cybercrimes como phishing, spam, violações de dados e outras ameaças, consulte [Security Best Practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span><span class="sxs-lookup"><span data-stu-id="72b5a-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span></span>

## <a name="related-topics"></a><span data-ttu-id="72b5a-208">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="72b5a-208">Related Topics</span></span>

[<span data-ttu-id="72b5a-209">Mnsagens backscatter e EOP</span><span class="sxs-lookup"><span data-stu-id="72b5a-209">Backscatter messages and EOP</span></span>](backscatter-messages-and-eop.md)
