---
title: Solução de problemas de emails enviados para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Este artigo fornece informações de solução de problemas para problemas de envio de email para caixas de entrada no Microsoft 365 & práticas recomendadas para envio em massa de emails para clientes do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286376"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="ab107-103">Solução de problemas de emails enviados para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab107-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ab107-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="ab107-104">**Applies to**</span></span>
- [<span data-ttu-id="ab107-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ab107-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ab107-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ab107-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="ab107-107">Este artigo fornece informações de solução de problemas para os envios que estão enfrentando problemas ao tentar enviar emails para caixas de entrada no Microsoft 365 e práticas recomendadas para envio de emails em massa aos clientes.</span><span class="sxs-lookup"><span data-stu-id="ab107-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="ab107-108">Você está gerenciando sua reputação de envio de IP e domínio?</span><span class="sxs-lookup"><span data-stu-id="ab107-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="ab107-109">As tecnologias de filtragem do EOP foram projetadas para fornecer proteção anti-spam para o Microsoft 365, bem como para outros produtos da Microsoft, como o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ab107-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="ab107-110">Também aproveitamos sPF, DKIM e DMARC; tecnologias de autenticação de email que ajudam a resolver o problema de spoofing e phishing, verificando se o domínio que envia o email está autorizado a fazer isso.</span><span class="sxs-lookup"><span data-stu-id="ab107-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="ab107-111">A filtragem do EOP é influenciada por vários fatores relacionados ao IP de envio, domínio, autenticação, precisão de lista, taxas de reclamação, conteúdo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ab107-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="ab107-112">Desses, um dos principais fatores para impulsionar a reputação de um remetente e sua capacidade de entregar emails é a taxa de reclamação de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ab107-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="ab107-113">Você está enviando emails de novos endereços IP?</span><span class="sxs-lookup"><span data-stu-id="ab107-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="ab107-114">Endereços IP não usados anteriormente para enviar emails normalmente não têm nenhuma reputação construída em nossos sistemas.</span><span class="sxs-lookup"><span data-stu-id="ab107-114">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="ab107-115">Como resultado, é mais provável que os emails de novos IPs experimentem problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="ab107-115">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="ab107-116">Depois que o IP tiver criado uma reputação de não enviar spam, o EOP geralmente permitirá uma melhor experiência de entrega de email.</span><span class="sxs-lookup"><span data-stu-id="ab107-116">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="ab107-117">Os novos IPs adicionados para domínios autenticados em registros SPF existentes normalmente têm o benefício agregado de herdar parte da reputação de envio do domínio.</span><span class="sxs-lookup"><span data-stu-id="ab107-117">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="ab107-118">Se o seu domínio tiver uma boa reputação de envio, os novos IPs poderão ter um tempo de adoção mais rápido.</span><span class="sxs-lookup"><span data-stu-id="ab107-118">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="ab107-119">Um novo IP pode esperar ser totalmente preparado dentro de algumas semanas ou mais cedo, dependendo das taxas de reclamação de volume, lista e lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ab107-119">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="ab107-120">Confirme se o DNS está definido corretamente</span><span class="sxs-lookup"><span data-stu-id="ab107-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="ab107-121">Para obter instruções sobre como criar e manter registros DNS, incluindo o registro MX necessário para roteamento de email, você precisará entrar em contato com seu provedor de hospedagem dns.</span><span class="sxs-lookup"><span data-stu-id="ab107-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="ab107-122">Certifique-se de não anunciar a si mesmo como um IP não-rouável</span><span class="sxs-lookup"><span data-stu-id="ab107-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="ab107-123">Talvez não aceitemos emails de envios que falharem em uma lookup de DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="ab107-123">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="ab107-124">Em alguns casos, os autores legítimos anunciam a si mesmos incorretamente como um IP não encaminhável pela Internet ao tentar abrir uma conexão com o EOP.</span><span class="sxs-lookup"><span data-stu-id="ab107-124">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="ab107-125">Os endereços IP reservados para rede privada (não-rouável) incluem:</span><span class="sxs-lookup"><span data-stu-id="ab107-125">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="ab107-126">192.168.0.0/16 (ou 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="ab107-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="ab107-127">10.0.0.0/8 (ou 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="ab107-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="ab107-128">172.16.0.0/11 (ou 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="ab107-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="ab107-129">Você recebeu uma NDR (relatório de não entrega) ao enviar emails para um usuário no Office 365</span><span class="sxs-lookup"><span data-stu-id="ab107-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="ab107-130">Alguns problemas de entrega são o resultado do bloqueio do endereço IP do remetente pela Microsoft ou porque a conta de usuário é identificada como remetente proibida devido a atividades anteriores de spam.</span><span class="sxs-lookup"><span data-stu-id="ab107-130">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="ab107-131">Se você acredita que recebeu a NDR por engano, primeiro siga as instruções na mensagem de NDR para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="ab107-131">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="ab107-132">Para obter mais informações sobre o erro recebido, consulte a lista de códigos de erro nos relatórios de falha na entrega de [email no Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="ab107-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="ab107-133">Por exemplo, se você receber a seguinte NDR, isso indicará que o endereço IP de envio foi bloqueado pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="ab107-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="ab107-134">Para solicitar a remoção dessa lista, você pode usar o portal de remoção da lista para remover a si [mesmo da lista de envios bloqueados.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="ab107-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="ab107-135">Meu email foi enviado para a pasta Lixo Eletrônico do destinatário</span><span class="sxs-lookup"><span data-stu-id="ab107-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="ab107-136">Se uma mensagem tiver sido incorretamente identificada como spam pelo EOP, você poderá trabalhar com o destinatário para enviar essa mensagem de falso positivo à Equipe de Análise de Spam da Microsoft, que avaliará e analisará a mensagem.</span><span class="sxs-lookup"><span data-stu-id="ab107-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="ab107-137">Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ab107-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="ab107-138">O tráfego de meu endereço IP é acelerada pelo EOP</span><span class="sxs-lookup"><span data-stu-id="ab107-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="ab107-139">Se você receber uma NDR do EOP que indica que seu endereço IP está sendo acelerada pelo EOP, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab107-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="ab107-140">Você recebeu a NDR porque atividades suspeitas foram detectadas do endereço IP e ela foi temporariamente restrita enquanto está sendo avaliada ainda mais.</span><span class="sxs-lookup"><span data-stu-id="ab107-140">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="ab107-141">Se o problema for limpo por meio da avaliação, essa restrição será suspensa em breve.</span><span class="sxs-lookup"><span data-stu-id="ab107-141">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="ab107-142">Não consigo receber emails de senders no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab107-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="ab107-143">Para receber mensagens de nossos usuários, certifique-se de que sua rede permita conexões dos endereços IP que o EOP usa em nossos datacenters.</span><span class="sxs-lookup"><span data-stu-id="ab107-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="ab107-144">Para obter mais informações, consulte [Endereços IP da Proteção do Exchange Online.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="ab107-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="ab107-145">Práticas recomendadas para envio de emails em massa para usuários do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab107-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="ab107-146">Se você geralmente conduz campanhas de email em massa para usuários do Microsoft 365 e deseja garantir que seus emails cheguem de maneira segura e o mais rápida possível, siga as dicas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="ab107-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="ab107-147">Verifique se o nome De reflete quem está enviando a mensagem</span><span class="sxs-lookup"><span data-stu-id="ab107-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="ab107-148">O Assunto deve ser um breve resumo do que se trata a mensagem, e o corpo da mensagem deve indicar de forma clara e sucinta a respeito da oferta, serviço ou produto.</span><span class="sxs-lookup"><span data-stu-id="ab107-148">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="ab107-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab107-149">For example:</span></span>

<span data-ttu-id="ab107-150">Correto:</span><span class="sxs-lookup"><span data-stu-id="ab107-150">Correct:</span></span>

> <span data-ttu-id="ab107-151">De: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="ab107-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="ab107-152">Assunto: Catálogo atualizado para a estação natalina!</span><span class="sxs-lookup"><span data-stu-id="ab107-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="ab107-153">Incorreto:</span><span class="sxs-lookup"><span data-stu-id="ab107-153">Incorrect:</span></span>

> <span data-ttu-id="ab107-154">De: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="ab107-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="ab107-155">Assunto: Catálogos</span><span class="sxs-lookup"><span data-stu-id="ab107-155">Subject: Catalogs</span></span>

<span data-ttu-id="ab107-156">Quanto mais fácil você torna as pessoas saberem quem você é e o que você está fazendo, menos dificuldade terá com a maioria dos filtros de spam.</span><span class="sxs-lookup"><span data-stu-id="ab107-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="ab107-157">Sempre incluir uma opção de cancelamento de assinatura em emails de campanha</span><span class="sxs-lookup"><span data-stu-id="ab107-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="ab107-158">Emails de marketing, especialmente boletins informativos, sempre devem incluir uma maneira de cancelar a assinatura de emails futuros.</span><span class="sxs-lookup"><span data-stu-id="ab107-158">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="ab107-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab107-159">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="ab107-160">Alguns destinatários incluem essa opção exigindo que os destinatários enviem um email para um determinado alias com "Cancelar assinatura" no assunto.</span><span class="sxs-lookup"><span data-stu-id="ab107-160">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="ab107-161">Isso não é preferível ao exemplo de um clique acima.</span><span class="sxs-lookup"><span data-stu-id="ab107-161">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="ab107-162">Se você optar por exigir que os destinatários enviem um email, certifique-se de que, quando clicarem no link, todos os campos necessários sejam preenchidos previamente.</span><span class="sxs-lookup"><span data-stu-id="ab107-162">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="ab107-163">Usar a opção de dupla aceitação para email de marketing ou registro de boletim informativo</span><span class="sxs-lookup"><span data-stu-id="ab107-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="ab107-164">Essa prática recomendada do setor será recomendada se sua empresa exigir ou incentivar os usuários a registrar suas informações de contato para acessar seus produtos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="ab107-164">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="ab107-165">Algumas empresas fazem uma prática de inscrever automaticamente seus usuários para emails de marketing ou boletins informativos por email durante o processo de registro, mas isso é considerado uma prática de marketing questionável no mundo da filtragem de email.</span><span class="sxs-lookup"><span data-stu-id="ab107-165">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="ab107-166">Durante o processo de registro, se a caixa de seleção "Sim, envie-me seu boletim informativo" ou "Sim, envie-me ofertas especiais" estiver marcada por padrão, os usuários que não prestarem atenção poderão se inscrever inadimplentemente para receber emails de marketing ou boletins informativos que não querem receber.</span><span class="sxs-lookup"><span data-stu-id="ab107-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="ab107-167">Em vez disso, recomendamos a opção de aceitação dupla, o que significa que a caixa de seleção para emails de marketing ou boletins informativos está desmarcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="ab107-167">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="ab107-168">Além disso, depois que o formulário de registro é enviado, um email de verificação é enviado ao usuário com uma URL que permite que ele confirme sua decisão de receber emails de marketing.</span><span class="sxs-lookup"><span data-stu-id="ab107-168">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="ab107-169">Isso ajuda a garantir que apenas os usuários que querem receber emails de marketing sejam inscrevíveis nos emails, limpando posteriormente a empresa de envio de quaisquer práticas questionáveis de marketing de email.</span><span class="sxs-lookup"><span data-stu-id="ab107-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="ab107-170">Certifique-se de que o conteúdo da mensagem de email seja transparente e rastreável</span><span class="sxs-lookup"><span data-stu-id="ab107-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="ab107-171">Tão importante quanto a maneira como os emails são enviados é o conteúdo que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="ab107-171">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="ab107-172">Ao criar conteúdo de email, use as práticas recomendadas a seguir para garantir que seus emails não sejam sinalizados pelos serviços de filtragem de email:</span><span class="sxs-lookup"><span data-stu-id="ab107-172">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="ab107-173">Quando a mensagem de email solicita que os destinatários adicionem o remetente ao livro de endereços, ela deve claramente dizer que essa ação não é uma garantia de entrega.</span><span class="sxs-lookup"><span data-stu-id="ab107-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="ab107-174">Redirecionamentos incluídos no corpo da mensagem devem ser semelhantes e consistentes, e não múltiplos e variados.</span><span class="sxs-lookup"><span data-stu-id="ab107-174">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="ab107-175">Um redirecionamento nesse contexto é qualquer coisa que aponta para longe da mensagem, como links e documentos.</span><span class="sxs-lookup"><span data-stu-id="ab107-175">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="ab107-176">Se você tiver muitos links de anúncio ou cancelamento de assinatura ou atualizar os links de perfil, todos eles devem apontar para o mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="ab107-176">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="ab107-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab107-177">For example:</span></span>

  <span data-ttu-id="ab107-178">Correto (todos os domínios são os mesmos):</span><span class="sxs-lookup"><span data-stu-id="ab107-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="ab107-179">Incorreto (todos os domínios são diferentes):</span><span class="sxs-lookup"><span data-stu-id="ab107-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="ab107-180">Evite conteúdo com imagens e anexos grandes ou mensagens compostas exclusivamente por uma imagem.</span><span class="sxs-lookup"><span data-stu-id="ab107-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="ab107-181">Sua privacidade pública ou configurações P3P devem claramente dizer a presença de pixels de rastreamento (bugs da Web ou beacons).</span><span class="sxs-lookup"><span data-stu-id="ab107-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="ab107-182">Remover aliases de email incorretos de seus bancos de dados</span><span class="sxs-lookup"><span data-stu-id="ab107-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="ab107-183">Qualquer alias de email em seu banco de dados que cria um retorno é desnecessário e coloca seus emails de saída em risco para maior apuração pelos serviços de filtragem de email.</span><span class="sxs-lookup"><span data-stu-id="ab107-183">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="ab107-184">Verifique se o banco de dados de email está atualizado.</span><span class="sxs-lookup"><span data-stu-id="ab107-184">Ensure that your email database is up-to-date.</span></span>
