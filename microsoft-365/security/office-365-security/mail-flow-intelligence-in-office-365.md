---
title: Inteligência de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Os administradores podem saber mais sobre os códigos de erro associados à entrega de mensagens usando conectores (também conhecidos como inteligência de fluxo de emails).
ms.openlocfilehash: 5339bf2117a87cd940c4b96b3d00b7b8ba78a1da
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658852"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="0818b-103">Inteligência de fluxo de emails no EOP</span><span class="sxs-lookup"><span data-stu-id="0818b-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0818b-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você geralmente usa um conector para rotear mensagens de email do EOP para seu ambiente de email local.</span><span class="sxs-lookup"><span data-stu-id="0818b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="0818b-105">Você também pode usar um conector para rotear mensagens do Microsoft 365 para uma organização parceira.</span><span class="sxs-lookup"><span data-stu-id="0818b-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="0818b-106">Quando o Microsoft 365 não consegue entregar essas mensagens por meio do conector, elas são colocadas em fila no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0818b-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="0818b-107">O Microsoft 365 continuará a entregar a entrega de cada mensagem por 24 horas.</span><span class="sxs-lookup"><span data-stu-id="0818b-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="0818b-108">Após 24 horas, a mensagem na fila expirará, e a mensagem será retornada ao remetente original em uma notificação de falha na entrega (também conhecida como uma mensagem de erro NDR ou de retorno).</span><span class="sxs-lookup"><span data-stu-id="0818b-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="0818b-109">O Microsoft 365 gera um erro quando uma mensagem não pode ser entregue usando um conector.</span><span class="sxs-lookup"><span data-stu-id="0818b-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="0818b-110">Os erros mais comuns e suas soluções são descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0818b-110">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="0818b-111">Coletivamente, os erros de enfileiramento e notificação para mensagens não entregues enviadas via conectores são conhecidos como _inteligência de fluxo de emails_.</span><span class="sxs-lookup"><span data-stu-id="0818b-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="0818b-112">Código de erro: 450 4.4.312 de consulta DNS falhou</span><span class="sxs-lookup"><span data-stu-id="0818b-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="0818b-113">Normalmente, esse erro significa que o Microsoft 365 tentou se conectar ao host inteligente especificado no conector, mas a consulta DNS para localizar os endereços IP do host inteligente falhou.</span><span class="sxs-lookup"><span data-stu-id="0818b-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="0818b-114">As possíveis causas para esse erro são:</span><span class="sxs-lookup"><span data-stu-id="0818b-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="0818b-115">Há um problema com o serviço de hospedagem DNS do seu domínio (o participante que mantém os servidores de nomes autoritativos para seu domínio).</span><span class="sxs-lookup"><span data-stu-id="0818b-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="0818b-116">Seu domínio expirou recentemente, portanto, o registro MX não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="0818b-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="0818b-117">O registro MX do seu domínio mudou recentemente, e os servidores DNS ainda têm informações de DNS armazenadas em cache anteriormente para seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0818b-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="0818b-118">Como corrigir o código de erro 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="0818b-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="0818b-119">Trabalhe com seu serviço de hospedagem DNS para identificar e corrigir o problema com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0818b-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="0818b-120">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), entre em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="0818b-121">Código de erro: 450 conexão 4.4.315 atingiu o tempo limite</span><span class="sxs-lookup"><span data-stu-id="0818b-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="0818b-122">Normalmente, isso significa que o Microsoft 365 não pode se conectar ao servidor de email de destino.</span><span class="sxs-lookup"><span data-stu-id="0818b-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="0818b-123">Os detalhes do erro explicarão o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-123">The error details will explain the problem.</span></span> <span data-ttu-id="0818b-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0818b-124">For example:</span></span>

- <span data-ttu-id="0818b-125">Seu servidor de email local está inoperante.</span><span class="sxs-lookup"><span data-stu-id="0818b-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="0818b-126">Há um erro nas configurações de host inteligente do conector, portanto, a Microsoft 365 está tentando se conectar ao endereço IP errado.</span><span class="sxs-lookup"><span data-stu-id="0818b-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="0818b-127">Como corrigir o código de erro 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="0818b-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="0818b-128">Descubra qual cenário se aplica a você e faça as correções necessárias.</span><span class="sxs-lookup"><span data-stu-id="0818b-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="0818b-129">Por exemplo, se o fluxo de emails estiver funcionando corretamente, e você não tiver alterado as configurações do conector, você precisará verificar seu ambiente de email local para ver se o servidor está inoperante ou se houve alguma alteração em sua infraestrutura de rede (por exemplo, você alterou provedores de serviços de Internet, portanto, agora tem endereços IP diferentes).</span><span class="sxs-lookup"><span data-stu-id="0818b-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="0818b-130">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), entre em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="0818b-131">Código de erro: 450 4.4.316 conexão recusada</span><span class="sxs-lookup"><span data-stu-id="0818b-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="0818b-132">Normalmente, esse erro significa que o Microsoft 365 encontrou um erro de conexão ao tentar se conectar ao servidor de email de destino.</span><span class="sxs-lookup"><span data-stu-id="0818b-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="0818b-133">Uma causa provável desse erro é o Firewall Bloquear conexões de endereços IP 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0818b-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="0818b-134">Ou, esse erro pode ser por design se você tiver migrado completamente seu sistema de email local para o Microsoft 365 e desligar o ambiente de email local.</span><span class="sxs-lookup"><span data-stu-id="0818b-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="0818b-135">Como corrigir o código de erro 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="0818b-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="0818b-136">Se você tiver caixas de correio em seu ambiente local, precisará modificar suas configurações de firewall para permitir conexões de endereços IP 365 da Microsoft na porta TCP 25 para seus servidores de email locais.</span><span class="sxs-lookup"><span data-stu-id="0818b-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="0818b-137">Para obter uma lista dos endereços IP 365 da Microsoft, confira [URLs e intervalos de endereços IP do microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="0818b-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="0818b-138">Se não houver mais mensagens a serem entregues ao seu ambiente local, clique em **corrigir agora** no alerta para que o Microsoft 365 possa rejeitar imediatamente as mensagens com destinatários inválidos.</span><span class="sxs-lookup"><span data-stu-id="0818b-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="0818b-139">Isso reduzirá o risco de exceder a cota da organização para destinatários inválidos, o que pode afetar a entrega de mensagens normal.</span><span class="sxs-lookup"><span data-stu-id="0818b-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="0818b-140">Ou você pode usar as seguintes instruções para corrigir manualmente o problema:</span><span class="sxs-lookup"><span data-stu-id="0818b-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="0818b-141">No [centro de administração do Exchange (Eat)](https://docs.microsoft.com/Exchange/exchange-admin-center), desabilite ou exclua o conector que entrega emails do Microsoft 365 para seu ambiente de email local:</span><span class="sxs-lookup"><span data-stu-id="0818b-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="0818b-142">No Eat, vá para conectores de **fluxo de emails** \> .</span><span class="sxs-lookup"><span data-stu-id="0818b-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="0818b-143">Selecione o conector com o valor **de do** **Office 365** e o valor **para para** o **servidor de email da sua organização** e execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0818b-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="0818b-144">Exclua o conector clicando no ícone **excluir** ![ remover](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="0818b-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="0818b-145">Para desabilitar o conector, clique em **Editar** ![ Editar ícone ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) e **desative-** o.</span><span class="sxs-lookup"><span data-stu-id="0818b-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="0818b-146">Altere o domínio aceito no Microsoft 365 associado ao seu ambiente de email local da **retransmissão interna** para **autoritativa**.</span><span class="sxs-lookup"><span data-stu-id="0818b-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="0818b-147">Para obter instruções, consulte [gerenciar domínios aceitos no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="0818b-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="0818b-148">**Observação**: normalmente, essas alterações levam entre 30 minutos e uma hora para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="0818b-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="0818b-149">Após uma hora, verifique se você não receberá mais o erro.</span><span class="sxs-lookup"><span data-stu-id="0818b-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="0818b-150">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="0818b-151">Código de erro: 450 4.4.317 não pode se conectar ao servidor remoto</span><span class="sxs-lookup"><span data-stu-id="0818b-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="0818b-152">Normalmente, esse erro significa que o Microsoft 365 está conectado ao servidor de email de destino, mas o servidor respondeu com um erro imediato ou não atende aos requisitos de conexão.</span><span class="sxs-lookup"><span data-stu-id="0818b-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="0818b-153">Os detalhes do erro explicarão o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-153">The error details will explain the problem.</span></span> <span data-ttu-id="0818b-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0818b-154">For example:</span></span>

- <span data-ttu-id="0818b-155">O servidor de email de destino respondeu com um erro "serviço não disponível", que indica que o servidor não pode manter a comunicação com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0818b-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="0818b-156">O conector é configurado para exigir TLS, mas o servidor de email de destino não dá suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="0818b-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="0818b-157">Como corrigir o código de erro 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="0818b-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="0818b-158">Verifique as configurações e os certificados de TLS nos seus servidores de email locais e as configurações de TLS no conector.</span><span class="sxs-lookup"><span data-stu-id="0818b-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="0818b-159">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="0818b-160">Código de erro: 450 4.4.318 conexão foi fechada abruptamente</span><span class="sxs-lookup"><span data-stu-id="0818b-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="0818b-161">Normalmente, esse erro significa que a Microsoft 365 está tendo dificuldade para se comunicar com seu ambiente de email local, portanto, a conexão foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="0818b-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="0818b-162">As possíveis causas para esse erro são:</span><span class="sxs-lookup"><span data-stu-id="0818b-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="0818b-163">O firewall usa regras de exame de pacotes SMTP e essas regras não estão funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="0818b-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="0818b-164">Seu servidor de email local não está funcionando corretamente (por exemplo, bloqueios de serviço, panes ou recursos de sistema Baixos), que está causando o tempo limite do servidor e feche a conexão com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0818b-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="0818b-165">Há problemas de rede entre seu ambiente local e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0818b-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="0818b-166">Como corrigir o código de erro 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="0818b-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="0818b-167">Descubra qual cenário se aplica a você e faça as correções necessárias.</span><span class="sxs-lookup"><span data-stu-id="0818b-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="0818b-168">Se o problema for causado por problemas de rede entre seu ambiente local e o Microsoft 365, entre em contato com sua equipe de rede para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="0818b-169">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="0818b-170">Código de erro: 450 falha na validação do certificado 4.7.320</span><span class="sxs-lookup"><span data-stu-id="0818b-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="0818b-171">Normalmente, esse erro significa que o Microsoft 365 encontrou um erro ao tentar validar o certificado do servidor de email de destino.</span><span class="sxs-lookup"><span data-stu-id="0818b-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="0818b-172">Os detalhes do erro explicarão o erro.</span><span class="sxs-lookup"><span data-stu-id="0818b-172">The error details will explain the error.</span></span> <span data-ttu-id="0818b-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0818b-173">For example:</span></span>

- <span data-ttu-id="0818b-174">Certificado expirado</span><span class="sxs-lookup"><span data-stu-id="0818b-174">Certificate expired</span></span>

- <span data-ttu-id="0818b-175">Incompatibilidade de entidade do certificado</span><span class="sxs-lookup"><span data-stu-id="0818b-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="0818b-176">O certificado não é mais válido</span><span class="sxs-lookup"><span data-stu-id="0818b-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="0818b-177">Como corrigir o código de erro 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="0818b-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="0818b-178">Corrija o certificado ou as configurações no conector para que as mensagens em fila no Microsoft 365 possam ser entregues.</span><span class="sxs-lookup"><span data-stu-id="0818b-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="0818b-179">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="0818b-180">Outros códigos de erro</span><span class="sxs-lookup"><span data-stu-id="0818b-180">Other error codes</span></span>

<span data-ttu-id="0818b-181">A Microsoft 365 está com dificuldades para entregar mensagens ao seu servidor de email local ou de parceiro.</span><span class="sxs-lookup"><span data-stu-id="0818b-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="0818b-182">Use as informações do **servidor de destino** no erro para examinar o problema no seu ambiente ou modifique o conector se houver um erro de configuração.</span><span class="sxs-lookup"><span data-stu-id="0818b-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="0818b-183">Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0818b-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
