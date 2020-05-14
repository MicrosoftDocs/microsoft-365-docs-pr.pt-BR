---
title: Autenticação de email no Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Os Administradores podem saber como a Proteção do Exchange Online (EOP) usa a autenticação de e-mail (SPF, DKIM e DMARC) para ajudar a evitar falsificações, phishing e spam.
ms.openlocfilehash: c79a75f1ae520a0c4f885c923b4a56cdb0f7fb87
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209494"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="8b90d-103">Autenticação de e-mail no EOP</span><span class="sxs-lookup"><span data-stu-id="8b90d-103">Email authentication in EOP</span></span>

<span data-ttu-id="8b90d-104">A autenticação de email (também conhecida como validação de email) é um grupo de padrões que tenta interromper a falsificação (mensagens de email de remetentes forjados).</span><span class="sxs-lookup"><span data-stu-id="8b90d-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="8b90d-105">Nas organizações Microsoft 365 com caixas de correio do Exchange Online e organizações com Exchange Online Protection (EOP) autônomos, organizações sem caixas de correio do Exchange Online, o EOP usa os padrões para verificar os e-mails de entrada:</span><span class="sxs-lookup"><span data-stu-id="8b90d-105">In Microsoft 365 organizations with mailboxes in Exchange Online, and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="8b90d-106">SPF</span><span class="sxs-lookup"><span data-stu-id="8b90d-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="8b90d-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="8b90d-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="8b90d-108">DMARCDMARC</span><span class="sxs-lookup"><span data-stu-id="8b90d-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="8b90d-109">A autenticação de email verifica se as mensagens de email de um remetente (por exemplo, laura@contoso.com) são legítimas e vêm de fontes esperadas para o domínio de email (por exemplo, contoso.com.)</span><span class="sxs-lookup"><span data-stu-id="8b90d-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="8b90d-110">O restante deste tópico explica como essas tecnologias funcionam e como a EOP as utiliza para verificar emails de entrada.</span><span class="sxs-lookup"><span data-stu-id="8b90d-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="8b90d-111">Use a autenticação de email para ajudar a impedir a falsificação</span><span class="sxs-lookup"><span data-stu-id="8b90d-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="8b90d-112">O DMARC impede a falsificação examinando o endereço **De** nas mensagens (o endereço de email do remetente que os usuários veem no cliente de email).</span><span class="sxs-lookup"><span data-stu-id="8b90d-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="8b90d-113">As organizações de email de destino também podem verificar se o domínio do email passou no SPF ou DKIM, o que significa que o domínio foi autenticado e, portanto, não é falsificado.</span><span class="sxs-lookup"><span data-stu-id="8b90d-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span> 

<span data-ttu-id="8b90d-114">No entanto, o problema é que os registros SPF, DKIM e DMARC no DNS para autenticação de email (conhecidos coletivamente como políticas de autenticação de email) são completamente opcionais.</span><span class="sxs-lookup"><span data-stu-id="8b90d-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="8b90d-115">Portanto, embora domínios com políticas fortes de autenticação de email, como microsoft.com e skype.com, sejam protegidos contra falsificação, domínios que publicam políticas de autenticação de email mais fracas ou nenhuma política são os principais alvos de falsificação.</span><span class="sxs-lookup"><span data-stu-id="8b90d-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="8b90d-116">Em março de 2018, apenas 9% dos domínios de empresas da lista Fortune 500 publicavam políticas de autenticação de emails fortes.</span><span class="sxs-lookup"><span data-stu-id="8b90d-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="8b90d-117">Os 91% restantes das empresas podem ser falsificados por um invasor.</span><span class="sxs-lookup"><span data-stu-id="8b90d-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="8b90d-118">A menos que haja outro mecanismo de filtragem de email, os emails de remetentes falsificados nesses domínios podem ser entregues aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8b90d-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Políticas do DMARC de empresas da lista Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="8b90d-120">A proporção de empresas de pequeno a médio porte que não fazem parte da lista Fortune 500 que publicam políticas fortes de autenticação de email é menor, sendo ainda menor para domínios de email fora da América do Norte e da Europa Ocidental.</span><span class="sxs-lookup"><span data-stu-id="8b90d-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="8b90d-121">Esse é um grande problema porque, embora as empresas possam não estar cientes de como a autenticação de email funciona, os invasores a entendem completamente e se aproveitam disso.</span><span class="sxs-lookup"><span data-stu-id="8b90d-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="8b90d-122">Como o phishing é um problema considerável e devido à adoção limitada de políticas fortes de autenticação de email, a Microsoft usa a *autenticação implícita de email* para verificar os emails de entrada.</span><span class="sxs-lookup"><span data-stu-id="8b90d-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="8b90d-123">A autenticação implícita de email se baseia em várias extensões de políticas regulares de autenticação de email.</span><span class="sxs-lookup"><span data-stu-id="8b90d-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="8b90d-124">Essas extensões incluem a reputação do remetente, histórico do remetente, histórico do destinatário, análise comportamental e outras técnicas avançadas.</span><span class="sxs-lookup"><span data-stu-id="8b90d-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="8b90d-125">Uma mensagem enviada de um domínio que não usa políticas de autenticação de email será marcada como falsa, a menos que contenha outros sinais para indicar que é legítima.</span><span class="sxs-lookup"><span data-stu-id="8b90d-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="8b90d-126">Para ver o anúncio geral da Microsoft, confira [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="8b90d-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="8b90d-127">Autenticação composta</span><span class="sxs-lookup"><span data-stu-id="8b90d-127">Composite authentication</span></span>

<span data-ttu-id="8b90d-128">Embora o SPF, o DKIM e o DMARC sejam úteis por si só, não comunicam um status de autenticação suficiente caso uma mensagem não tenha registros de autenticação explícitos.</span><span class="sxs-lookup"><span data-stu-id="8b90d-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="8b90d-129">Portanto, a Microsoft desenvolveu um algoritmo para autenticação implícita de email, que combina vários sinais em um único valor chamado de _autenticação composta_ ou compauth, abreviado.</span><span class="sxs-lookup"><span data-stu-id="8b90d-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="8b90d-130">O valor compauth é marcado no cabeçalho **Authentication-Results** nos cabeçalhos da mensagem.</span><span class="sxs-lookup"><span data-stu-id="8b90d-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="8b90d-131">Authentication-Results:</span><span class="sxs-lookup"><span data-stu-id="8b90d-131">Authentication-Results:</span></span><br/><span data-ttu-id="8b90d-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="8b90d-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="8b90d-133">Estes valores são explicados em [Resultados de autenticação do cabeçalho da mensagem](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="8b90d-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="8b90d-134">Ao examinar os cabeçalhos das mensagens, os administradores ou usuários finais podem determinar como o Microsoft 365 determinou que o remetente é falsificado.</span><span class="sxs-lookup"><span data-stu-id="8b90d-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="8b90d-135">Por que a autenticação de email nem sempre é suficiente para impedir a falsificação</span><span class="sxs-lookup"><span data-stu-id="8b90d-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="8b90d-136">Confiar apenas nos registros de autenticação de email para determinar se uma mensagem de entrada é falsa tem as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="8b90d-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="8b90d-137">O domínio de envio pode não ter os registros DNS necessários, ou os registros estão configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="8b90d-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="8b90d-138">O domínio de origem configurou corretamente os registros DNS, mas esse domínio não corresponde ao domínio no endereço De.</span><span class="sxs-lookup"><span data-stu-id="8b90d-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="8b90d-139">O SPF e o DKIM não exigem que o domínio seja usado no endereço De.</span><span class="sxs-lookup"><span data-stu-id="8b90d-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="8b90d-140">Invasores ou serviços legítimos podem registrar um domínio, configurar o SPF e o DKIM para o domínio, usar um domínio completamente diferente no endereço De e essa mensagem passará no SPF e DKIM.</span><span class="sxs-lookup"><span data-stu-id="8b90d-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="8b90d-141">A autenticação composta pode solucionar essas limitações transmitindo mensagens que, de outra forma, falhariam nas verificações de autenticação de email.</span><span class="sxs-lookup"><span data-stu-id="8b90d-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="8b90d-142">Conforme descrito anteriormente, a autenticação implícita de email usa vários sinais para determinar se uma mensagem é legítima.</span><span class="sxs-lookup"><span data-stu-id="8b90d-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="8b90d-143">Para simplificar, os exemplos a seguir se concentram nos resultados da autenticação de email.</span><span class="sxs-lookup"><span data-stu-id="8b90d-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="8b90d-144">Outros fatores de inteligência de back-end poderiam identificar mensagens aprovadas na autenticação de email como falsas, ou mensagens reprovadas na autenticação de email como legítimas.</span><span class="sxs-lookup"><span data-stu-id="8b90d-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="8b90d-145">Por exemplo, o domínio fabrikam.com não possui registros SPF, DKIM ou DMARC.</span><span class="sxs-lookup"><span data-stu-id="8b90d-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="8b90d-146">Mensagens de remetentes no domínio fabrikam.com podem ser reprovadas na autenticação composta (observe o valor `compauth` e o motivo):</span><span class="sxs-lookup"><span data-stu-id="8b90d-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="8b90d-147">Se fabrikam.com configurar um SPF sem um registro DKIM, a mensagem poderá passar pela autenticação composta, porque o domínio que passou no SPF está alinhado com o domínio no endereço De:</span><span class="sxs-lookup"><span data-stu-id="8b90d-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="8b90d-148">Se fabrikam.com configurar um registro DKIM sem um registro SPF, a mensagem poderá passar pela autenticação composta, porque o domínio na assinatura DKIM aprovada está alinhado com o domínio no endereço De:</span><span class="sxs-lookup"><span data-stu-id="8b90d-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="8b90d-149">Se o domínio no SPF ou a assinatura DKIM não se alinhar com o domínio no endereço De, a mensagem poderá ser reprovada na autenticação composta:</span><span class="sxs-lookup"><span data-stu-id="8b90d-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="8b90d-150">Soluções para remetentes legítimos que enviam emails não autenticados</span><span class="sxs-lookup"><span data-stu-id="8b90d-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="8b90d-151">O Microsoft 365 mantém o controle de quem está enviando emails não autenticados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b90d-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="8b90d-152">Se o serviço considerar que o remetente não é legítimo, ele o marcará como uma falha de autenticação composta.</span><span class="sxs-lookup"><span data-stu-id="8b90d-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="8b90d-153">Para evitar isso, você pode usar as recomendações nesta seção.</span><span class="sxs-lookup"><span data-stu-id="8b90d-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="8b90d-154">Configure a autenticação de email para domínios que você possui</span><span class="sxs-lookup"><span data-stu-id="8b90d-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="8b90d-155">Você pode usar este método para solucionar problemas de falsificação dentro da organização e falsificação entre domínios nos casos em que você possui ou interage com vários locatários.</span><span class="sxs-lookup"><span data-stu-id="8b90d-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="8b90d-156">Ele também ajuda a resolver a falsificação entre domínios que você envia para outros clientes no Microsoft 365 ou em terceiros que são hospedados por outros provedores.</span><span class="sxs-lookup"><span data-stu-id="8b90d-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="8b90d-157">[Configurar registros SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) para seus domínios.</span><span class="sxs-lookup"><span data-stu-id="8b90d-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="8b90d-158">[Configurar registros DKIM](use-dkim-to-validate-outbound-email.md) para seus domínios principais.</span><span class="sxs-lookup"><span data-stu-id="8b90d-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="8b90d-159">[Considere configurar registros DMARC](use-dmarc-to-validate-email.md) para seu domínio para determinar seus remetentes legítimos.</span><span class="sxs-lookup"><span data-stu-id="8b90d-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="8b90d-160">A Microsoft não fornece diretrizes detalhadas de implementação para registros SPF, DKIM e DMARC.</span><span class="sxs-lookup"><span data-stu-id="8b90d-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="8b90d-161">No entanto, há muitas informações disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="8b90d-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="8b90d-162">Também há empresas de terceiros dedicadas a ajudar sua organização a configurar registros de autenticação de email.</span><span class="sxs-lookup"><span data-stu-id="8b90d-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="8b90d-163">Você não conhece todas as fontes do seu email</span><span class="sxs-lookup"><span data-stu-id="8b90d-163">You don't know all sources for your email</span></span>

<span data-ttu-id="8b90d-164">Muitos domínios não publicam registros SPF porque não conhecem todas as fontes de email das mensagens em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8b90d-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="8b90d-165">Comece publicando um registro SPF que contenha todas as fontes de email que você conhece (especialmente onde o seu tráfego corporativo está localizado) e publique a política neutra de SPF `?all`.</span><span class="sxs-lookup"><span data-stu-id="8b90d-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="8b90d-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8b90d-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="8b90d-167">Este exemplo significa que emails da sua infraestrutura corporativa passarão pela autenticação de email, mas emails de fontes desconhecidas voltarão à neutralidade.</span><span class="sxs-lookup"><span data-stu-id="8b90d-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="8b90d-168">O Microsoft 365 tratará emails de entrada da sua infraestrutura corporativa como autenticados, mas emails de fontes não identificadas ainda poderão ser marcados como falsos (dependendo se o Microsoft 365 puder autenticá-los implicitamente).</span><span class="sxs-lookup"><span data-stu-id="8b90d-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="8b90d-169">No entanto, isso ainda é uma melhoria em relação à situação em que todos os emails são marcados como falsificação pelo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b90d-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="8b90d-170">Após começar a usar um registro SPF com a política de fallback `?all`, você poderá gradualmente descobrir e incluir mais fontes de email para suas mensagens e, em seguida, atualizar seu registro SPF com uma política mais rígida.</span><span class="sxs-lookup"><span data-stu-id="8b90d-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="8b90d-171">Use a inteligência contra falsificação para configurar remetentes permitidos de email não autenticado</span><span class="sxs-lookup"><span data-stu-id="8b90d-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="8b90d-172">Você também pode usar a [inteligência contra falsificação](learn-about-spoof-intelligence.md) para permitir que os remetentes transmitam mensagens não autenticadas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b90d-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="8b90d-173">Para domínios externos, o usuário falsificado é o domínio no endereço De, enquanto a infraestrutura de envio é o endereço IP de origem (dividido em intervalos /24 CIDR) ou o domínio organizacional do registro de DNS reverso (PTR).</span><span class="sxs-lookup"><span data-stu-id="8b90d-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="8b90d-174">Na captura de tela abaixo, o IP de origem pode ser 131.107.18.4 com o registro PTR outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8b90d-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="8b90d-175">Isso apareceria como outlook.com para a infraestrutura de envio.</span><span class="sxs-lookup"><span data-stu-id="8b90d-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="8b90d-176">Para permitir que esse remetente envie emails não autenticados, altere **No** para **Yes**.</span><span class="sxs-lookup"><span data-stu-id="8b90d-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Configurar remetentes permitidos pela antifalsificação](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="8b90d-178">Crie uma permissão de entrada para o par remetente/destinatário</span><span class="sxs-lookup"><span data-stu-id="8b90d-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="8b90d-179">Para ignorar a filtragem de spam, algumas partes da filtragem de phish, mas não a filtragem de malware de remetentes específicos, confira [Criar listas de remetentes confiáveis no Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8b90d-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="8b90d-180">Peça ao remetente para configurar a autenticação de email para domínios que você não possui</span><span class="sxs-lookup"><span data-stu-id="8b90d-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="8b90d-181">Devido ao problema de spam e phishing, a Microsoft recomenda autenticação de email para todas as organizações de email.</span><span class="sxs-lookup"><span data-stu-id="8b90d-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="8b90d-182">Em vez de configurar substituições manuais em sua organização, você pode pedir a um administrador no domínio de envio para configurar seus registros de autenticação de email.</span><span class="sxs-lookup"><span data-stu-id="8b90d-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="8b90d-183">Mesmo que ele não tenha precisado publicar registros de autenticação de email no passado, ele deverá fazê-lo se enviar emails para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b90d-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="8b90d-184">Configure o SPF para publicar os endereços IP de envio do domínio e configure o DKIM (se disponível) para assinar digitalmente as mensagens.</span><span class="sxs-lookup"><span data-stu-id="8b90d-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="8b90d-185">Ele também deve considerar a criação de registros DMARC.</span><span class="sxs-lookup"><span data-stu-id="8b90d-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="8b90d-186">Se ele usar remetentes em massa para enviar emails em seu nome, verifique se o domínio no endereço De (se pertencer a ele) está alinhado com o domínio que passa no SPF ou no DMARC.</span><span class="sxs-lookup"><span data-stu-id="8b90d-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="8b90d-187">Verifique se os seguintes locais (se ele não os usar) estão incluídos no registro SPF:</span><span class="sxs-lookup"><span data-stu-id="8b90d-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="8b90d-188">Servidores de email no local.</span><span class="sxs-lookup"><span data-stu-id="8b90d-188">On-premises email servers.</span></span>
  - <span data-ttu-id="8b90d-189">Email enviado de um provedor de software como serviço (SaaS).</span><span class="sxs-lookup"><span data-stu-id="8b90d-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="8b90d-190">Email enviado de um serviço de hospedagem em nuvem (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span><span class="sxs-lookup"><span data-stu-id="8b90d-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="8b90d-191">Para domínios pequenos hospedados por um ISP, configure o registro SPF de acordo com as instruções do ISP.</span><span class="sxs-lookup"><span data-stu-id="8b90d-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="8b90d-192">Embora inicialmente possa ser difícil enviar domínios para autenticação, com o passar do tempo, à medida que mais e mais filtros de email começarem a acumular ou até mesmo rejeitar seus emails, isso fará com que eles configurem os registros apropriados para melhorar a entrega.</span><span class="sxs-lookup"><span data-stu-id="8b90d-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="8b90d-193">Além disso, sua participação pode ajudar no combate a phishing e reduzir a possibilidade de phishing em sua organização ou organizações para as quais ele envia emails.</span><span class="sxs-lookup"><span data-stu-id="8b90d-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="8b90d-194">Informações para provedores de infraestrutura (ISPs, ESPs ou serviços de hospedagem em nuvem)</span><span class="sxs-lookup"><span data-stu-id="8b90d-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="8b90d-195">Se você hospedar o email de um domínio ou fornecer uma infraestrutura de hospedagem que possa enviar emails, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8b90d-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="8b90d-196">Garanta que seus clientes tenham uma documentação que explique como eles devem configurar seus registros SPF</span><span class="sxs-lookup"><span data-stu-id="8b90d-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="8b90d-197">Considere a inclusão de assinaturas DKIM nos emails de saída, mesmo que o cliente não os configure explicitamente (assine com um domínio padrão).</span><span class="sxs-lookup"><span data-stu-id="8b90d-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="8b90d-198">Você pode até mesmo assinar duplamente o email com assinaturas DKIM (uma vez com o domínio do cliente, se ele estiver configurado, e uma segunda vez com a assinatura DKIM de sua empresa)</span><span class="sxs-lookup"><span data-stu-id="8b90d-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="8b90d-199">A capacidade de entrega para a Microsoft não é garantida, mesmo que você autentique emails originados de sua plataforma, mas pelo menos isso garante que a Microsoft não marque seu email como lixo eletrônico porque ele não está autenticado.</span><span class="sxs-lookup"><span data-stu-id="8b90d-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="8b90d-200">Para obter mais detalhes sobre as práticas recomendadas dos provedores de serviços, confira [Práticas recomendadas de mensagens móveis do M3AAWG para provedores de serviços](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span><span class="sxs-lookup"><span data-stu-id="8b90d-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
