---
title: Monitoramento do Exchange Online para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Use o monitoramento do Exchange Online para obter informações sobre incidentes de email ou avisos no Microsoft 365.
ms.openlocfilehash: ee31f8e152d7c54e37b850563bea57971e07f61c
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707291"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="4b22a-103">Monitoramento do Exchange Online para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b22a-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="4b22a-104">É possível usar o monitoramento do Exchange Online no Centro de administração do Microsoft 365 para monitorar a integridade do serviço do Exchange para a assinatura do Microsoft 365 da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4b22a-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="4b22a-105">O monitoramento do Exchange Online fornece informações sobre incidentes e avisos que são coletados nestas categorias:</span><span class="sxs-lookup"><span data-stu-id="4b22a-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="4b22a-106">**Infraestrutura**: O problema é detectado na infraestrutura do Microsoft 365 que a Microsoft possui para fornecer atualizações regulares e resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="4b22a-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="4b22a-107">Por exemplo, os usuários não podem acessar o Exchange Online devido a problemas com o Exchange ou outra infraestrutura de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b22a-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="4b22a-108">**Infraestrutura de terceiros**: O problema é detectado em uma infraestrutura de terceiros da qual sua organização depende e requer a adoção de medidas da sua organização para sua resolução.</span><span class="sxs-lookup"><span data-stu-id="4b22a-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="4b22a-109">Por exemplo, as transações de autenticação de usuários estão sendo aceleradas por um provedor de serviços de token de segurança (STS) de terceiros que impede que os usuários se conectem ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b22a-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="4b22a-110">**Infraestrutura do cliente**: O problema é detectado na infra-estrutura da sua organização e requer ação de sua organização para resolução.</span><span class="sxs-lookup"><span data-stu-id="4b22a-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="4b22a-111">Por exemplo, os usuários não podem acessar o Exchange Online porque não conseguem obter um token de autenticação do provedor STS hospedado por sua organização devido a um certificado expirado.</span><span class="sxs-lookup"><span data-stu-id="4b22a-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="4b22a-112">Aqui está um exemplo da página **Integridade do serviço** no Centro de administração do Microsoft 365, disponível em **Integridade > Integridade do serviço**.</span><span class="sxs-lookup"><span data-stu-id="4b22a-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![A página Integridade do Serviço no Centro de administração do Microsoft 365](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="4b22a-114">O valor da coluna **Status** indica se o serviço está funcionando bem ou se possui avisos ou incidentes baseados nos serviços de nuvem que a Microsoft mantém.</span><span class="sxs-lookup"><span data-stu-id="4b22a-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="4b22a-115">O valor da coluna **Sua organização e edições de terceiros** indica que a infraestrutura da sua organização ou o software de terceiros estão afetando sua experiência com a integridade do serviço dos usuários do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b22a-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="4b22a-116">Os avisos ou incidentes requerem a adoção de medidas *suas* para serem resolvidos.</span><span class="sxs-lookup"><span data-stu-id="4b22a-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="4b22a-117">Aqui está um exemplo da página de monitoramento do **Exchange Online** no Centro de administração do Microsoft 365, disponível em **Integridade > Integridade do serviço > Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="4b22a-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![A página de monitoramento do Exchange Online no Centro de administração do Microsoft 365](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="4b22a-119">Com a página de **monitoramento do Exchange Online**, você pode ver se o serviço do Exchange Online está íntegro ou não e se há algum incidente ou aviso associado.</span><span class="sxs-lookup"><span data-stu-id="4b22a-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="4b22a-120">Com o monitoramento do Exchange Online, você pode observar a integridade do serviço para cenários de email específicos e visualizar sinais em tempo quase real para determinar o impacto por cenário.</span><span class="sxs-lookup"><span data-stu-id="4b22a-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="4b22a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b22a-121">Requirements</span></span>

<span data-ttu-id="4b22a-122">Esta pré-visualização está habilitada para os clientes que atendem a estes requisitos:</span><span class="sxs-lookup"><span data-stu-id="4b22a-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="4b22a-123">A organização precisa ter uma contagem de licenças de pelo menos 5.000, de um ou uma combinação destes produtos: Office 365 E3, Microsoft 365 E3, Office 365 E5 e Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4b22a-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="4b22a-124">Por exemplo, a organização pode ter 3.000 licenças do Office 365 E3 e 2.500 do Microsoft 365 E5, para um total de 5.500 licenças dos produtos qualificados.</span><span class="sxs-lookup"><span data-stu-id="4b22a-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="4b22a-125">A organização precisa ter pelo menos 50 usuários ativos mensais do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b22a-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="4b22a-126">Com o monitoramento do Exchange Online, você pode ver a integridade dos seguintes clientes de email com base na atividade de leitura de email:</span><span class="sxs-lookup"><span data-stu-id="4b22a-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="4b22a-127">Outlook para Desktop </span><span class="sxs-lookup"><span data-stu-id="4b22a-127">Outlook Desktop</span></span>
- <span data-ttu-id="4b22a-128">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="4b22a-128">Outlook on the Web</span></span>
- <span data-ttu-id="4b22a-129">Clientes nativos do iOS e do Android</span><span class="sxs-lookup"><span data-stu-id="4b22a-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="4b22a-130">Aplicativo Móvel do Outlook no iOS e no Android</span><span class="sxs-lookup"><span data-stu-id="4b22a-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="4b22a-131">Cliente Outlook para o Mac</span><span class="sxs-lookup"><span data-stu-id="4b22a-131">Outlook Mac client</span></span>

<span data-ttu-id="4b22a-132">Para estes clientes, você pode ver o número de usuários ativos nos últimos 30 minutos com base nos usuários que leram um email, juntamente com o número de incidentes e avisos no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="4b22a-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="4b22a-133">Estes dados são comparados com o mesmo intervalo da semana anterior para ver se há algum problema.</span><span class="sxs-lookup"><span data-stu-id="4b22a-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="4b22a-134">A contagem de usuários ativos é medida por uma única atividade, por exemplo, quando o usuário lê um email.</span><span class="sxs-lookup"><span data-stu-id="4b22a-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="4b22a-135">Ela contabiliza apenas os últimos 30 minutos de atividade.</span><span class="sxs-lookup"><span data-stu-id="4b22a-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="4b22a-136">Também é possível monitorar a integridade do Exchange Online para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="4b22a-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="4b22a-137">**Fluxo de Email do Outlook**: O número de mensagens entregues com sucesso a uma caixa postal sem qualquer atraso após a mensagem ter chegado à rede Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b22a-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="4b22a-138">**Autenticação Básica e Autenticação Moderna**: O número de usuários validados com êxito no serviço Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b22a-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Um exemplo de monitoramento da integridade do Exchange para entrega de emails](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="4b22a-140">Para todos esses cenários, os números-chave são para os últimos 30 minutos no painel principal.</span><span class="sxs-lookup"><span data-stu-id="4b22a-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="4b22a-141">As visualizações detalhadas para cada um desses cenários mostram a tendência quase em tempo real para sete dias com o agregado de 30 minutos em comparação com a semana anterior.</span><span class="sxs-lookup"><span data-stu-id="4b22a-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="4b22a-142">Envie-nos o seu feedback</span><span class="sxs-lookup"><span data-stu-id="4b22a-142">Send us feedback</span></span>

<span data-ttu-id="4b22a-143">Há duas maneiras de fornecer um feedback:</span><span class="sxs-lookup"><span data-stu-id="4b22a-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="4b22a-144">Use a opção **Enviar feedback** disponível em todas as páginas do Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b22a-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="4b22a-145">Enviar o feedback usando o link **Esta postagem é útil?** para um incidente específico ou um aviso.</span><span class="sxs-lookup"><span data-stu-id="4b22a-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![O "Esta postagem é útil?"?](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="4b22a-148">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="4b22a-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4b22a-149">1. Por que não vejo “Monitoramento do Exchange Online” em Integridade no Centro de administração do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="4b22a-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="4b22a-150">Primeiro, certifique-se de ter ativado o novo Centro de administração na página **Início** do Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b22a-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4b22a-151">Em seguida, certifique-se de atender a ambos os requisitos a seguir:</span><span class="sxs-lookup"><span data-stu-id="4b22a-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="4b22a-152">A organização precisa ter uma contagem de licenças de pelo menos 5.000, de um ou uma combinação destes produtos: Office 365 E3, Microsoft 365 E3, Office 365 E5 e Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4b22a-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="4b22a-153">A organização precisa ter pelo menos 50 usuários ativos mensais do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b22a-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="4b22a-154">Se a contagem de licenças para a organização ficar abaixo de 5.000 usuários e os usuários ativos mensais ficarem abaixo de 50 usuários, o monitoramento do Exchange Online não será habilitado até que esses requisitos sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="4b22a-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="4b22a-155">2. A contagem de usuários ativos no painel de cada cliente parece ser baixa.</span><span class="sxs-lookup"><span data-stu-id="4b22a-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="4b22a-156">Temos muitas licenças ativas atribuídas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="4b22a-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="4b22a-157">O que isto significa?</span><span class="sxs-lookup"><span data-stu-id="4b22a-157">What does this mean?</span></span> 

<span data-ttu-id="4b22a-158">A contagem de usuários ativos mostrada no monitoramento é baseada em uma janela de 30 minutos onde os usuários realizaram a atividade chamada no recurso.</span><span class="sxs-lookup"><span data-stu-id="4b22a-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="4b22a-159">Isso não deve ser confundido com números de uso.</span><span class="sxs-lookup"><span data-stu-id="4b22a-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="4b22a-160">Para visualizar os números de utilização, utilize relatórios de atividades no Centro de administração do Microsoft 365 (**Relatórios > Utilização**).</span><span class="sxs-lookup"><span data-stu-id="4b22a-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="4b22a-161">3. Haverá outros cenários de monitoramento para outros serviços, tais como o Teams e o Microsoft Office SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="4b22a-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="4b22a-162">A Microsoft está integrando essa experiência diretamente no painel de integridade do serviço no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b22a-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4b22a-163">Isto proporcionará oportunidades para a Microsoft ampliar os cenários de monitoramento para outros serviços, que serão anunciados quando houver novidades a serem compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="4b22a-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="4b22a-164">4. Qual é o plano para a disponibilidade geral desta experiência?</span><span class="sxs-lookup"><span data-stu-id="4b22a-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="4b22a-165">A Microsoft integrou o monitoramento do Exchange Online diretamente no painel **Integridade do Serviço** no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b22a-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4b22a-166">Com esta nova experiência integrada, o plano da Microsoft é coletar seu feedback e depois definir nosso plano de disponibilidade geral.</span><span class="sxs-lookup"><span data-stu-id="4b22a-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="4b22a-167">5. Este é um recurso gratuito (incluído) ou pago (extra)?</span><span class="sxs-lookup"><span data-stu-id="4b22a-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="4b22a-168">Este recurso está em Visualização Pública e disponível apenas para clientes que atendam aos requisitos da pergunta 1.</span><span class="sxs-lookup"><span data-stu-id="4b22a-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="4b22a-169">6. Como faço para enviar meus comentários?</span><span class="sxs-lookup"><span data-stu-id="4b22a-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="4b22a-170">Para obter comentários gerais, use o ícone **Fornecer comentários** no canto inferior direito da página de monitoramento do **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="4b22a-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="4b22a-171">Para comentários sobre incidentes ou avisos, use o link **Esta postagem é útil?**.</span><span class="sxs-lookup"><span data-stu-id="4b22a-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="4b22a-172">7. Onde estão os dados instrumentados para os cenários que mostram tendências de atividade?</span><span class="sxs-lookup"><span data-stu-id="4b22a-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="4b22a-p114">Os dados são instrumentados no serviço Exchange Online. Se houver uma falha que acontece antes da solicitação chegar no Exchange Online ou se houver uma falha no Exchange Online, você verá uma queda do sinal de atividade.</span><span class="sxs-lookup"><span data-stu-id="4b22a-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

