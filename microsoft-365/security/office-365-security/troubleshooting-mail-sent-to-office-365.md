---
title: Solução de problemas de email enviados para o Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: Este artigo fornece informações de solução de problemas para remetentes que estão enfrentando problemas ao tentar enviar emails para caixas de entrada no Office 365 e práticas recomendadas para envio de email em massa para clientes do Office 365.
ms.openlocfilehash: 59c02b31b759870892846947940744e123c73788
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441178"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="741da-103">Solução de problemas de email enviados para o Office 365</span><span class="sxs-lookup"><span data-stu-id="741da-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="741da-104">Este artigo fornece informações de solução de problemas para remetentes que estão enfrentando problemas ao tentar enviar emails para caixas de entrada no Office 365 e práticas recomendadas para envio de email em massa para clientes do Office 365.</span><span class="sxs-lookup"><span data-stu-id="741da-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="741da-105">Solucionando problemas comuns com a entrega de emails para o Office 365</span><span class="sxs-lookup"><span data-stu-id="741da-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="741da-106">Escolha um desses problemas normalmente encontrados.</span><span class="sxs-lookup"><span data-stu-id="741da-106">Choose from one of these commonly encountered issues.</span></span>

- [<span data-ttu-id="741da-107">Você está gerenciando sua reputação de envio de IP e de domínio?</span><span class="sxs-lookup"><span data-stu-id="741da-107">Are you managing your IP and domain's sending reputation?</span></span>](#are-you-managing-your-ip-and-domains-sending-reputation)

- [<span data-ttu-id="741da-108">Você está enviando emails de novos endereços IP?</span><span class="sxs-lookup"><span data-stu-id="741da-108">Are you sending email from new IP addresses?</span></span>](#are-you-sending-email-from-new-ip-addresses)

- [<span data-ttu-id="741da-109">Confirmar se o DNS está configurado corretamente</span><span class="sxs-lookup"><span data-stu-id="741da-109">Confirm that your DNS is set up correctly</span></span>](#confirm-that-your-dns-is-set-up-correctly)

- [<span data-ttu-id="741da-110">Não se anuncie como um IP não roteável</span><span class="sxs-lookup"><span data-stu-id="741da-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [<span data-ttu-id="741da-111">Você recebeu uma notificação de falha na entrega (NDR) ao enviar emails para um usuário no Office 365</span><span class="sxs-lookup"><span data-stu-id="741da-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [<span data-ttu-id="741da-112">Meu email Redirecionado na pasta lixo eletrônico do destinatário no EOP</span><span class="sxs-lookup"><span data-stu-id="741da-112">My email landed in the recipient's junk folder in EOP</span></span>](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [<span data-ttu-id="741da-113">O tráfego do meu endereço IP é limitado por EOP</span><span class="sxs-lookup"><span data-stu-id="741da-113">Traffic from my IP address is throttled by EOP</span></span>](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="741da-114">Você está gerenciando sua reputação de envio de IP e de domínio?</span><span class="sxs-lookup"><span data-stu-id="741da-114">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="741da-115">As tecnologias de filtragem do EOP são projetadas para fornecer proteções antispam para o Microsoft Office 365, bem como outros produtos da Microsoft, como o Exchange Server, o Microsoft Office Outlook e o Windows Live mail.</span><span class="sxs-lookup"><span data-stu-id="741da-115">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail.</span></span> <span data-ttu-id="741da-116">Também aproveitamos o SPF, DKIM e DMARC; tecnologias de autenticação de email que ajudam a resolver o problema de falsificação e phishing, verificando se o domínio que envia o email está autorizado a fazer isso.</span><span class="sxs-lookup"><span data-stu-id="741da-116">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="741da-117">A filtragem EOP é influenciada por vários fatores relacionados ao IP de envio, domínio, autenticação, precisão da lista, taxas de reclamação, conteúdo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="741da-117">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="741da-118">Desses, um dos principais fatores para a condução da reputação de um remetente e sua capacidade de entregar emails é a taxa de reclamação de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="741da-118">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="741da-119">Você está enviando emails de novos endereços IP?</span><span class="sxs-lookup"><span data-stu-id="741da-119">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="741da-120">Os endereços IP não usados anteriormente para enviar emails normalmente não têm nenhuma reputação criada em nossos sistemas.</span><span class="sxs-lookup"><span data-stu-id="741da-120">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="741da-121">Como resultado, os emails de novos IPs têm maior probabilidade de sofrer problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="741da-121">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="741da-122">Depois que o IP tiver criado uma reputação de não enviar spam, o EOP geralmente permitirá uma melhor experiência de entrega de email.</span><span class="sxs-lookup"><span data-stu-id="741da-122">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="741da-123">Os novos IPs que são adicionados para domínios autenticados em registros SPF existentes normalmente apresentam a vantagem adicional de herdar alguns dos domínios de envio do domínio.</span><span class="sxs-lookup"><span data-stu-id="741da-123">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="741da-124">Se seu domínio tem uma boa reputação de envio, novos IPs podem ter um tempo de crescimento mais rápido.</span><span class="sxs-lookup"><span data-stu-id="741da-124">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="741da-125">Um novo IP pode esperar ser totalmente enescalado dentro de algumas semanas ou antes, dependendo do volume, da precisão da lista e das taxas de reclamação de emails de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="741da-125">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="741da-126">Confirmar se o DNS está configurado corretamente</span><span class="sxs-lookup"><span data-stu-id="741da-126">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="741da-127">Para obter instruções sobre como criar e manter registros DNS, incluindo o registro MX exigido para roteamento de email, você precisará entrar em contato com o provedor de hospedagem DNS.</span><span class="sxs-lookup"><span data-stu-id="741da-127">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="741da-128">Não se anuncie como um IP não roteável</span><span class="sxs-lookup"><span data-stu-id="741da-128">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="741da-129">Podemos não aceitar emails de remetentes que falham em uma pesquisa de DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="741da-129">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="741da-130">Em alguns casos, os remetentes legítimos se anunciam incorretamente como um IP que não é roteável pela Internet ao tentar abrir uma conexão com o EOP.</span><span class="sxs-lookup"><span data-stu-id="741da-130">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="741da-131">Os endereços IP reservados para redes privadas (não roteáveis) incluem:</span><span class="sxs-lookup"><span data-stu-id="741da-131">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="741da-132">192.168.0.0/16 (ou 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="741da-132">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="741da-133">10.0.0.0/8 (ou 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="741da-133">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="741da-134">172.16.0.0/11 (ou 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="741da-134">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="741da-135">Você recebeu uma notificação de falha na entrega (NDR) ao enviar emails para um usuário no Office 365</span><span class="sxs-lookup"><span data-stu-id="741da-135">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="741da-136">Alguns problemas de entrega são o resultado do endereço IP do remetente sendo bloqueado pela Microsoft ou porque a conta do usuário é identificada como remetente proibido devido à atividade de spam anterior.</span><span class="sxs-lookup"><span data-stu-id="741da-136">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="741da-137">Se você achar que recebeu a notificação por erro, primeiro siga as instruções na mensagem de notificação de falha na entrega para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="741da-137">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="741da-138">Para obter mais informações sobre o erro recebido, consulte a lista completa de códigos de erro SMTP em [DSNs e NDRs no Exchange 2013 local e no Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span><span class="sxs-lookup"><span data-stu-id="741da-138">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>

 <span data-ttu-id="741da-139">Por exemplo, se você receber a seguinte notificação de falha na entrega, ela indicará que o endereço IP de envio foi bloqueado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="741da-139">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="741da-140">Para solicitar a remoção dessa lista, você pode [usar o portal de deslista para se remover da lista de remetentes bloqueados do Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="741da-140">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="741da-141">Meu email Redirecionado na pasta lixo eletrônico do destinatário no EOP</span><span class="sxs-lookup"><span data-stu-id="741da-141">My email landed in the recipient's junk folder in EOP</span></span>

<span data-ttu-id="741da-142">Se uma mensagem foi identificada incorretamente como spam pelo EOP, você poderá trabalhar com o destinatário para enviar essa mensagem falsa positiva para a equipe de análise de spam da Microsoft, que avaliará e analisará a mensagem.</span><span class="sxs-lookup"><span data-stu-id="741da-142">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="741da-143">Dependendo dos resultados da análise, as regras de filtro de conteúdo de spam de todo o serviço podem ser ajustadas para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="741da-143">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> <span data-ttu-id="741da-144">Você usa email para enviar mensagens para a Microsoft que não devem ser classificadas como spam.</span><span class="sxs-lookup"><span data-stu-id="741da-144">You use email to submit messages to Microsoft that should not be classified as spam.</span></span> <span data-ttu-id="741da-145">Ao fazer isso, certifique-se de usar as etapas do seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="741da-145">When doing so, be sure to use the steps in the following procedure.</span></span>

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="741da-146">Para usar o email para enviar mensagens de falso positivo para a equipe de análise de spam da Microsoft</span><span class="sxs-lookup"><span data-stu-id="741da-146">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="741da-147">Salve a mensagem que você deseja enviar como não spam.</span><span class="sxs-lookup"><span data-stu-id="741da-147">Save the message you want to submit as non-spam.</span></span>

2. <span data-ttu-id="741da-148">Crie uma nova mensagem em branco e anexe a ela a mensagem que não é spam.</span><span class="sxs-lookup"><span data-stu-id="741da-148">Create a new, blank message and attach the non-spam message to it.</span></span>

    <span data-ttu-id="741da-149">Você pode anexar várias mensagens que não são spam, se necessário.</span><span class="sxs-lookup"><span data-stu-id="741da-149">You can attach multiple non-spam messages if needed.</span></span>

3. <span data-ttu-id="741da-150">Copie e cole a linha de assunto da mensagem original na linha de assunto da nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="741da-150">Copy and paste the original message subject line into the new message subject line.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="741da-151">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="741da-151">Leave the body of the new message empty.</span></span>

4. <span data-ttu-id="741da-152">Envie a mensagem para [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="741da-152">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="741da-153">O tráfego do meu endereço IP é limitado por EOP</span><span class="sxs-lookup"><span data-stu-id="741da-153">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="741da-154">Se você receber uma notificação de falha na EOP que indica que seu endereço IP está sendo limitado por EOP, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="741da-154">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="741da-155">Você recebeu a notificação de falha na entrega porque a atividade suspeita foi detectada no endereço IP e foi temporariamente restringida enquanto está sendo avaliada.</span><span class="sxs-lookup"><span data-stu-id="741da-155">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="741da-156">Se a suspeita for limpa através da avaliação, essa restrição será levantada em breve.</span><span class="sxs-lookup"><span data-stu-id="741da-156">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="741da-157">Não consigo receber emails de remetentes no Office 365</span><span class="sxs-lookup"><span data-stu-id="741da-157">I can't receive email from senders in Office 365</span></span>

 <span data-ttu-id="741da-158">Para receber mensagens de nossos usuários, certifique-se de que a sua rede permite conexões dos endereços IP que o EOP usa em nossos data centers.</span><span class="sxs-lookup"><span data-stu-id="741da-158">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="741da-159">Confira mais informações em [endereços IP do Exchange Online Protection](https://docs.microsoft.com/en-us/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="741da-159">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/en-us/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="741da-160">Práticas recomendadas para envio de email em massa para usuários do Office 365</span><span class="sxs-lookup"><span data-stu-id="741da-160">Best practices for bulk emailing to Office 365 users</span></span>

<span data-ttu-id="741da-161">Se você costuma conduzir campanhas de email em massa para os usuários do Office 365 e quiser garantir que seus emails cheguem de forma segura e oportuna, siga as dicas desta seção.</span><span class="sxs-lookup"><span data-stu-id="741da-161">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="741da-162">Verifique se o nome de: reflete quem está enviando a mensagem</span><span class="sxs-lookup"><span data-stu-id="741da-162">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="741da-163">O assunto deve ser um breve resumo do que a mensagem está sobre, e o corpo da mensagem deve indicar claramente e sucintamente o que a oferta, serviço ou produto está.</span><span class="sxs-lookup"><span data-stu-id="741da-163">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="741da-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="741da-164">For example:</span></span>

<span data-ttu-id="741da-165">Correto:</span><span class="sxs-lookup"><span data-stu-id="741da-165">Correct:</span></span>

> <span data-ttu-id="741da-166">De: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="741da-166">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="741da-167">Assunto: Catálogo atualizado para a temporada de Natal!</span><span class="sxs-lookup"><span data-stu-id="741da-167">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="741da-168">Incorreto:</span><span class="sxs-lookup"><span data-stu-id="741da-168">Incorrect:</span></span>

> <span data-ttu-id="741da-169">De: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="741da-169">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="741da-170">Assunto: Catálogos</span><span class="sxs-lookup"><span data-stu-id="741da-170">Subject: Catalogs</span></span>

<span data-ttu-id="741da-171">Quanto mais fácil você fizer isso para que as pessoas saibam quem é e o que você está fazendo, menos dificuldade você terá de fornecer pela maioria dos filtros de spam.</span><span class="sxs-lookup"><span data-stu-id="741da-171">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="741da-172">Sempre incluir uma opção de cancelamento de assinatura em emails de campanha</span><span class="sxs-lookup"><span data-stu-id="741da-172">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="741da-173">Os emails de marketing, especialmente boletins informativos, devem sempre incluir uma forma de inscrever-se em emails futuros.</span><span class="sxs-lookup"><span data-stu-id="741da-173">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="741da-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="741da-174">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`

<span data-ttu-id="741da-175">Alguns remetentes incluem essa opção exigindo que os destinatários enviem um email para um determinado alias com "unsubscribe" no assunto.</span><span class="sxs-lookup"><span data-stu-id="741da-175">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="741da-176">Isso não é preferível ao exemplo de um clique acima.</span><span class="sxs-lookup"><span data-stu-id="741da-176">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="741da-177">Se você optar por exigir que os destinatários enviem um email, certifique-se de que ao clicar no link, todos os campos obrigatórios sejam preenchidos previamente.</span><span class="sxs-lookup"><span data-stu-id="741da-177">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="741da-178">Use a opção de consentimento duplo para o email de marketing ou o registro de boletim informativo</span><span class="sxs-lookup"><span data-stu-id="741da-178">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="741da-179">Essa prática recomendada do setor é recomendada se sua empresa requer ou incentiva os usuários a registrar suas informações de contato para acessar seu produto ou serviço.</span><span class="sxs-lookup"><span data-stu-id="741da-179">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="741da-180">Algumas empresas fazem dele uma prática inscrever automaticamente seus usuários para emails de marketing ou boletins eletrônicos durante o processo de registro, mas isso é considerado uma prática de marketing questionável no mundo da filtragem de email.</span><span class="sxs-lookup"><span data-stu-id="741da-180">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="741da-181">Durante o processo de registro, se a caixa de seleção "Sim, envie-me seu boletim informativo" ou "Sim, enviar ofertas especiais" estiver selecionada por padrão, os usuários que não pagarão mais atenção podem inadvertidamente involuntariamente inscrever-se no email de marketing ou boletins informativos de que não deseja receber.</span><span class="sxs-lookup"><span data-stu-id="741da-181">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="741da-182">Recomendamos a opção de consentimento duplo em vez disso, o que significa que a caixa de seleção para os emails de marketing ou boletins informativos está desmarcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="741da-182">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="741da-183">Além disso, após o formulário de registro ter sido enviado, um email de verificação é enviado para o usuário com uma URL que permite confirmar sua decisão de receber emails de marketing.</span><span class="sxs-lookup"><span data-stu-id="741da-183">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="741da-184">Isso ajuda a garantir que apenas os usuários que desejam receber emails de marketing estão inscritos para os emails, subseqüentemente limpando a empresa de envio de qualquer prática de marketing de email questionável.</span><span class="sxs-lookup"><span data-stu-id="741da-184">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="741da-185">Garantir que o conteúdo da mensagem de email seja transparente e rastreável</span><span class="sxs-lookup"><span data-stu-id="741da-185">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="741da-186">Tão importante quanto a forma como os emails são enviados é o conteúdo que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="741da-186">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="741da-187">Ao criar conteúdo de email, use as práticas recomendadas a seguir para garantir que seus emails não sejam sinalizados por serviços de filtragem de email:</span><span class="sxs-lookup"><span data-stu-id="741da-187">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="741da-188">Quando a mensagem de email solicita que os destinatários adicionem o remetente ao catálogo de endereços, deve indicar claramente que essa ação não é uma garantia de entrega.</span><span class="sxs-lookup"><span data-stu-id="741da-188">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="741da-189">Redirecionamentos incluídos no corpo da mensagem devem ser semelhantes e consistentes, e não múltiplos e variados.</span><span class="sxs-lookup"><span data-stu-id="741da-189">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="741da-190">Um redirecionamento neste contexto é qualquer coisa que aponte para longe da mensagem, como links e documentos.</span><span class="sxs-lookup"><span data-stu-id="741da-190">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="741da-191">Se você tiver muitos links de propaganda ou cancelamento de assinatura ou atualizar os links de perfil, todos eles apontarão para o mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="741da-191">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="741da-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="741da-192">For example:</span></span>

  <span data-ttu-id="741da-193">Correto:</span><span class="sxs-lookup"><span data-stu-id="741da-193">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="741da-194">Incorreto:</span><span class="sxs-lookup"><span data-stu-id="741da-194">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profiles.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="741da-195">Evite conteúdo com imagens e anexos grandes ou mensagens que são exclusivamente compostas por uma imagem.</span><span class="sxs-lookup"><span data-stu-id="741da-195">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="741da-196">Suas configurações de privacidade pública ou P3P devem indicar claramente a presença de pixels de rastreamento (Web bugs ou beacons).</span><span class="sxs-lookup"><span data-stu-id="741da-196">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="741da-197">Remover aliases de email incorretos dos bancos de dados</span><span class="sxs-lookup"><span data-stu-id="741da-197">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="741da-198">Qualquer alias de email em seu banco de dados que cria um repercussão é desnecessário e coloca seus emails de saída em risco para mais investigações por serviços de filtragem de email.</span><span class="sxs-lookup"><span data-stu-id="741da-198">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="741da-199">Verifique se o banco de dados de email está atualizado.</span><span class="sxs-lookup"><span data-stu-id="741da-199">Ensure that your email database is up-to-date.</span></span>
