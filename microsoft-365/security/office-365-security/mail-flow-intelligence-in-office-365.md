---
title: Inteligência de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Os administradores podem aprender sobre os códigos de erro associados à entrega de mensagens usando conectores (também conhecidos como inteligência de fluxo de emails).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32a98459ce3d3494e576b10d5c5b097393ee2335
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289658"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="f9d9d-103">Inteligência de fluxo de emails no EOP</span><span class="sxs-lookup"><span data-stu-id="f9d9d-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9d9d-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f9d9d-104">**Applies to**</span></span>
- [<span data-ttu-id="f9d9d-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f9d9d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f9d9d-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f9d9d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f9d9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9d9d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f9d9d-108">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você normalmente usa um conector para rotear mensagens de email do EOP para seu ambiente de email local.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="f9d9d-109">Você também pode usar um conector para encaminhar mensagens do Microsoft 365 para uma organização parceira.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="f9d9d-110">Quando o Microsoft 365 não consegue entregar essas mensagens por meio do conector, elas estão na fila no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="f9d9d-111">O Microsoft 365 continuará tentando entregar cada mensagem por 24 horas.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="f9d9d-112">Após 24 horas, a mensagem em fila expirará e a mensagem será retornada ao remetente original em um relatório de não entrega (também conhecido como NDR ou mensagem de rejeição).</span><span class="sxs-lookup"><span data-stu-id="f9d9d-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="f9d9d-113">O Microsoft 365 gera um erro quando uma mensagem não pode ser entregue usando um conector.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="f9d9d-114">Os erros mais comuns e suas soluções são descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="f9d9d-115">Coletivamente, erros de fila e notificação para mensagens não entregues enviadas por conectores é conhecido como _inteligência de fluxo de emails._</span><span class="sxs-lookup"><span data-stu-id="f9d9d-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="f9d9d-116">Código de erro: falha na consulta DNS 450 4.4.312</span><span class="sxs-lookup"><span data-stu-id="f9d9d-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="f9d9d-117">Normalmente, esse erro significa que o Microsoft 365 tentou se conectar ao host inteligente especificado no conector, mas a consulta DNS para encontrar os endereços IP do host inteligente falhou.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="f9d9d-118">As possíveis causas para esse erro são:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="f9d9d-119">Há um problema com o serviço de hospedagem DNS do seu domínio (a parte que mantém os servidores de nomes autoritativos para o seu domínio).</span><span class="sxs-lookup"><span data-stu-id="f9d9d-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="f9d9d-120">Seu domínio expirou recentemente, portanto, o registro MX não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="f9d9d-121">O registro MX do seu domínio foi alterado recentemente, e os servidores DNS ainda armazenam anteriormente em cache as informações dns do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="f9d9d-122">Como corrigir o código de erro 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="f9d9d-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="f9d9d-123">Trabalhe com seu serviço de hospedagem DNS para identificar e corrigir o problema com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="f9d9d-124">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), entre em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="f9d9d-125">Código de erro: 450 4.4.315 Tempo de conexão</span><span class="sxs-lookup"><span data-stu-id="f9d9d-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="f9d9d-126">Normalmente, isso significa que o Microsoft 365 não pode se conectar ao servidor de email de destino.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="f9d9d-127">Os detalhes do erro explicarão o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-127">The error details will explain the problem.</span></span> <span data-ttu-id="f9d9d-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-128">For example:</span></span>

- <span data-ttu-id="f9d9d-129">Seu servidor de email local está ino mesmo.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="f9d9d-130">Há um erro nas configurações de host inteligente do conector, portanto, o Microsoft 365 está tentando se conectar ao endereço IP errado.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="f9d9d-131">Como corrigir o código de erro 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="f9d9d-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="f9d9d-132">Descubra qual cenário se aplica a você e faça as correções necessárias.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="f9d9d-133">Por exemplo, se o fluxo de emails está funcionando corretamente e você não alterou as configurações do conector, é necessário verificar seu ambiente de email local para ver se o servidor está inocível ou se houve alguma alteração em sua infraestrutura de rede (por exemplo, você alterou provedores de serviços de Internet, então agora tem diferentes endereços IP).</span><span class="sxs-lookup"><span data-stu-id="f9d9d-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="f9d9d-134">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), entre em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="f9d9d-135">Código de erro: 450 4.4.316 Conexão recusada</span><span class="sxs-lookup"><span data-stu-id="f9d9d-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="f9d9d-136">Normalmente, esse erro significa que o Microsoft 365 encontrou um erro de conexão ao tentar se conectar ao servidor de email de destino.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="f9d9d-137">Uma causa provável para esse erro é que o firewall está bloqueando conexões de endereços IP do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="f9d9d-138">Ou, esse erro pode ser por design se você migrou completamente seu sistema de email local para o Microsoft 365 e fechou seu ambiente de email local.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="f9d9d-139">Como corrigir o código de erro 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="f9d9d-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="f9d9d-140">Se você tiver caixas de correio em seu ambiente local, precisará modificar suas configurações de firewall para permitir conexões de endereços IP do Microsoft 365 na porta TCP 25 para seus servidores de email locais.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="f9d9d-141">Para uma lista de endereços IP do Microsoft 365, confira URLs e intervalos de [endereços IP do Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="f9d9d-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="f9d9d-142">Se nenhuma outra mensagem tiver que ser entregue  ao seu ambiente local, clique em Corrigir agora no alerta para que o Microsoft 365 possa rejeitar imediatamente as mensagens com destinatários inválidos.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="f9d9d-143">Isso reduzirá o risco de exceder a cota da sua organização para destinatários inválidos, o que pode afetar a entrega normal de mensagens.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="f9d9d-144">Ou você pode usar as instruções a seguir para corrigir manualmente o problema:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="f9d9d-145">No [Centro de administração do Exchange (EAC),](https://docs.microsoft.com/Exchange/exchange-admin-center)desabilite ou exclua o conector que entrega emails do Microsoft 365 para seu ambiente de email local:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-145">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="f9d9d-146">No EAC, vá para **Conectores de fluxo** \> **de emails.**</span><span class="sxs-lookup"><span data-stu-id="f9d9d-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="f9d9d-147">Selecione o conector com o valor **De**  **do Office 365** e o servidor de **email** da sua organização e faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="f9d9d-148">Excluir o conector clicando no **ícone** Excluir ![ Remover](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="f9d9d-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="f9d9d-149">Desabilite o conector clicando no **ícone** ![ Editar Editar e ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) desblicando **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="f9d9d-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="f9d9d-150">Altere o domínio aceito no Microsoft 365 associado ao seu ambiente  de email local de Retransmissão Interna para **Autoritativo.**</span><span class="sxs-lookup"><span data-stu-id="f9d9d-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="f9d9d-151">Para obter instruções, [confira Gerenciar domínios aceitos no Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="f9d9d-151">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="f9d9d-152">**Observação:** normalmente, essas alterações levam entre 30 minutos e uma hora para ter efeito.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="f9d9d-153">Após uma hora, verifique se você não recebe mais o erro.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="f9d9d-154">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="f9d9d-155">Código de erro: 450 4.4.317 Não é possível se conectar ao servidor remoto</span><span class="sxs-lookup"><span data-stu-id="f9d9d-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="f9d9d-156">Normalmente, esse erro significa que o Microsoft 365 se conectou ao servidor de email de destino, mas o servidor respondeu com um erro imediato ou não atendeu aos requisitos de conexão.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="f9d9d-157">Os detalhes do erro explicarão o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-157">The error details will explain the problem.</span></span> <span data-ttu-id="f9d9d-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-158">For example:</span></span>

- <span data-ttu-id="f9d9d-159">O servidor de email de destino respondeu com um erro "Serviço não disponível", indicando que o servidor não consegue manter a comunicação com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="f9d9d-160">O conector está configurado para exigir TLS, mas o servidor de email de destino não dá suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="f9d9d-161">Como corrigir o código de erro 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="f9d9d-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="f9d9d-162">Verifique as configurações de TLS e os certificados em seus servidores de email locais e as configurações de TLS no conector.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="f9d9d-163">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="f9d9d-164">Código de erro: 450 4.4.318 A conexão foi fechada abruptamente</span><span class="sxs-lookup"><span data-stu-id="f9d9d-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="f9d9d-165">Normalmente, esse erro significa que o Microsoft 365 está com dificuldades para se comunicar com seu ambiente de email local, portanto, a conexão foi retirada.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="f9d9d-166">As possíveis causas para esse erro são:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="f9d9d-167">O firewall usa regras de exame de pacotes SMTP, e essas regras não estão funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="f9d9d-168">Seu servidor de email local não está funcionando corretamente (por exemplo, travamentos de serviço, falhas ou poucos recursos do sistema), o que está fazendo com que o servidor se esvancie e feche a conexão com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="f9d9d-169">Há problemas de rede entre seu ambiente local e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="f9d9d-170">Como corrigir o código de erro 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="f9d9d-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="f9d9d-171">Descubra qual cenário se aplica a você e faça as correções necessárias.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="f9d9d-172">Se o problema for causado por problemas de rede entre seu ambiente local e o Microsoft 365, entre em contato com sua equipe de rede para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="f9d9d-173">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="f9d9d-174">Código de erro: Falha na validação do certificado 450 4.7.320</span><span class="sxs-lookup"><span data-stu-id="f9d9d-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="f9d9d-175">Normalmente, esse erro significa que o Microsoft 365 encontrou um erro ao tentar validar o certificado do servidor de email de destino.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="f9d9d-176">Os detalhes do erro explicarão o erro.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-176">The error details will explain the error.</span></span> <span data-ttu-id="f9d9d-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f9d9d-177">For example:</span></span>

- <span data-ttu-id="f9d9d-178">Certificado expirado</span><span class="sxs-lookup"><span data-stu-id="f9d9d-178">Certificate expired</span></span>

- <span data-ttu-id="f9d9d-179">Incompatibilidade de assunto do certificado</span><span class="sxs-lookup"><span data-stu-id="f9d9d-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="f9d9d-180">O certificado não é mais válido</span><span class="sxs-lookup"><span data-stu-id="f9d9d-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="f9d9d-181">Como corrigir o código de erro 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="f9d9d-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="f9d9d-182">Corrige o certificado ou as configurações no conector para que as mensagens em fila no Microsoft 365 possam ser entregues.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="f9d9d-183">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="f9d9d-184">Outros códigos de erro</span><span class="sxs-lookup"><span data-stu-id="f9d9d-184">Other error codes</span></span>

<span data-ttu-id="f9d9d-185">O Microsoft 365 está com dificuldades para entregar mensagens ao seu servidor de email local ou parceiro.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="f9d9d-186">Use as **informações do servidor** de Destino no erro para examinar o problema em seu ambiente ou modifique o conector se houver um erro de configuração.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="f9d9d-187">Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="f9d9d-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
