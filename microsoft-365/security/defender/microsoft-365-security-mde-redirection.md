---
title: Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para Microsoft 365 Defender
description: Como redirecionar contas e sessões do Defender para o Ponto de Extremidade para Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Iniciando o Microsoft 365 Defender, redirecionamento do centro de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842561"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a><span data-ttu-id="7b426-104">Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b426-104">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7b426-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7b426-105">**Applies to:**</span></span>
- <span data-ttu-id="7b426-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b426-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="7b426-107">Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7b426-107">Defender for Endpoint</span></span>

<span data-ttu-id="7b426-108">Em alinhamento com a abordagem entre domínios da Microsoft para proteção contra ameaças com SIEM e XDR (Detecção e resposta estendida), renomeamos o Proteção Avançada contra Ameaças do Microsoft Defender como Microsoft Defender para Ponto de Extremidade e unificamos-o em um único portal integrado - Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b426-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - Microsoft 365 Defender.</span></span>

<span data-ttu-id="7b426-109">Este guia explica como rotear contas para o Microsoft 365 Defender habilitando o redirecionamento automático do antigo portal do Microsoft Defender para Ponto de Extremidade (securitycenter.windows.com ou securitycenter.microsoft.com), para o portal do Defender (Microsoft 365) (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7b426-109">This guide explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to Microsoft 365 Defender portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="7b426-110">O Microsoft Defender for Endpoint no Microsoft 365 Defender dá suporte à concessão de acesso a [MSSPs (provedores](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de serviços de segurança gerenciados) da mesma forma que o acesso é concedido no centro de segurança do [Microsoft Defender.](./mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="7b426-110">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="7b426-111">O que esperar</span><span class="sxs-lookup"><span data-stu-id="7b426-111">What to expect</span></span>
<span data-ttu-id="7b426-112">Depois que o redirecionamento automático for habilitado, as contas que acessam o antigo portal do Microsoft Defender para Ponto de Extremidade no securitycenter.windows.com ou securitycenter.microsoft.com, serão roteados automaticamente para o portal do Microsoft 365 Defender no security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7b426-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to Microsoft 365 Defender portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="7b426-113">Saiba mais sobre o que mudou: Microsoft Defender para Ponto de [Extremidade no Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="7b426-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="7b426-114">Isso inclui redirecionamento para acesso direto ao portal anterior por meio do navegador, incluindo links apontando para o antigo portal securitycenter.windows.com - como links em notificações de email e links retornados por chamadas de API SIEM.</span><span class="sxs-lookup"><span data-stu-id="7b426-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="7b426-115">Links externos de notificações por email ou APIs SIEM atualmente contêm links para ambos os portais.</span><span class="sxs-lookup"><span data-stu-id="7b426-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="7b426-116">Depois que o redirecionamento for habilitado, ambos os links apontarão para Microsoft 365 Defender até que o link antigo seja removido.</span><span class="sxs-lookup"><span data-stu-id="7b426-116">Once redirection is enabled, both links will point to Microsoft 365 Defender until the old link is eventually removed.</span></span> <span data-ttu-id="7b426-117">Recomendamos que você adote o novo link apontando para Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b426-117">We encourage you to adopt the new link pointing to Microsoft 365 Defender.</span></span>

<span data-ttu-id="7b426-118">Consulte a tabela abaixo para obter mais informações sobre links e roteamento.</span><span class="sxs-lookup"><span data-stu-id="7b426-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="7b426-119">Roteamento de API SIEM</span><span class="sxs-lookup"><span data-stu-id="7b426-119">SIEM API routing</span></span>

|<span data-ttu-id="7b426-120">**Property**</span><span class="sxs-lookup"><span data-stu-id="7b426-120">**Property**</span></span>  |<span data-ttu-id="7b426-121">**Destino quando o redirecionamento está OFF**</span><span class="sxs-lookup"><span data-stu-id="7b426-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="7b426-122">**Destino quando o redirecionamento está ON**</span><span class="sxs-lookup"><span data-stu-id="7b426-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="7b426-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="7b426-123">LinkToWDATP</span></span> | <span data-ttu-id="7b426-124">Página de alerta no securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="7b426-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="7b426-125">Página de alerta em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="7b426-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="7b426-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="7b426-127">Página incidente no securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="7b426-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="7b426-128">Página de incidentes em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="7b426-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="7b426-129">LinkToMTP</span></span> | <span data-ttu-id="7b426-130">Página de alerta em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="7b426-131">Página de alerta em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="7b426-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="7b426-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="7b426-133">Página de incidentes em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="7b426-134">Página de incidentes em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="7b426-135">Notificações de alerta de email</span><span class="sxs-lookup"><span data-stu-id="7b426-135">Email alert notifications</span></span>

|<span data-ttu-id="7b426-136">**Property**</span><span class="sxs-lookup"><span data-stu-id="7b426-136">**Property**</span></span>  |<span data-ttu-id="7b426-137">**Destino quando o redirecionamento está OFF**</span><span class="sxs-lookup"><span data-stu-id="7b426-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="7b426-138">**Destino quando o redirecionamento está ON**</span><span class="sxs-lookup"><span data-stu-id="7b426-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="7b426-139">Página alerta</span><span class="sxs-lookup"><span data-stu-id="7b426-139">Alert page</span></span>  | <span data-ttu-id="7b426-140">Página de alerta no securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="7b426-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="7b426-141">Página de alerta em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="7b426-142">Página incidente</span><span class="sxs-lookup"><span data-stu-id="7b426-142">Incident page</span></span>  |<span data-ttu-id="7b426-143">Página incidente no securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="7b426-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="7b426-144">Página de incidentes em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="7b426-145">Página de alerta no portal do Centro de Segurança</span><span class="sxs-lookup"><span data-stu-id="7b426-145">Alert page in security center portal</span></span> | <span data-ttu-id="7b426-146">Página de alerta em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="7b426-147">Página de alerta em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="7b426-148">Página de incidentes no portal da central de segurança</span><span class="sxs-lookup"><span data-stu-id="7b426-148">Incident page in security center portal</span></span> | <span data-ttu-id="7b426-149">Página de incidentes em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="7b426-150">Página de incidentes em security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7b426-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="7b426-151">Quando isso tem efeito?</span><span class="sxs-lookup"><span data-stu-id="7b426-151">When does this take effect?</span></span> 
<span data-ttu-id="7b426-152">Depois de habilitada, essa atualização pode ter efeito quase imediatamente para algumas contas.</span><span class="sxs-lookup"><span data-stu-id="7b426-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="7b426-153">Mas o redirecionamento pode levar mais tempo para se propagar para todas as contas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b426-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="7b426-154">As contas em sessões ativas enquanto essa configuração é aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o Microsoft 365 Defender após o término da sessão atual e a sessão de logon novamente.</span><span class="sxs-lookup"><span data-stu-id="7b426-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="7b426-155">Configurar redirecionamento de portal</span><span class="sxs-lookup"><span data-stu-id="7b426-155">Set up portal redirection</span></span>
<span data-ttu-id="7b426-156">Para iniciar o roteamento de contas para Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="7b426-156">To start routing accounts to Microsoft 365 Defender:</span></span>
1. <span data-ttu-id="7b426-157">Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory</span><span class="sxs-lookup"><span data-stu-id="7b426-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="7b426-158">[Entre no](https://security.microsoft.com/) Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b426-158">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>

3. <span data-ttu-id="7b426-159">Navegue **Configurações**  >  **redirecionamento geral** do Portal de Pontos de  >    >  **Extremidade** ou clique [aqui](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="7b426-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="7b426-160">Alterne a configuração de redirecionamento automático para **On**.</span><span class="sxs-lookup"><span data-stu-id="7b426-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="7b426-161">Clique **em Habilitar** para aplicar redirecionamento automático ao Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b426-161">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7b426-162">A habilitação dessa configuração não encerrará sessões de usuário ativas.</span><span class="sxs-lookup"><span data-stu-id="7b426-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="7b426-163">As contas que estão em uma sessão ativa enquanto essa configuração é aplicada serão direcionadas Microsoft 365 Defender depois de encerrar a sessão atual e entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="7b426-163">Accounts who are in an active session while this setting is applied will only be directed to Microsoft 365 Defender after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="7b426-164">Você deve ser um administrador global ou ter permissões de administrador de segurança Azure Active Directory habilitar ou desabilitar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="7b426-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="7b426-165">Posso voltar a usar o portal anterior?</span><span class="sxs-lookup"><span data-stu-id="7b426-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="7b426-166">Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do Microsoft 365 Defender, queremos ouvir sobre isso.</span><span class="sxs-lookup"><span data-stu-id="7b426-166">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it.</span></span> <span data-ttu-id="7b426-167">Se você tiver encontrado algum problema com redirecionamento, recomendamos que você nos avise usando o formulário De envio de comentários.</span><span class="sxs-lookup"><span data-stu-id="7b426-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="7b426-168">Para reverter para o antigo portal do Microsoft Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="7b426-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="7b426-169">[Entre no](https://security.microsoft.com/) Microsoft 365 Defender como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="7b426-169">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="7b426-170">Navegue **Configurações**  >  **redirecionamento geral** do Portal de Pontos de  >    >  **Extremidade** ou abra a página [aqui](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="7b426-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="7b426-171">Alterne a configuração de redirecionamento automático para **Off**.</span><span class="sxs-lookup"><span data-stu-id="7b426-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="7b426-172">Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="7b426-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="7b426-173">Essa configuração pode ser habilitada novamente a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7b426-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="7b426-174">Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior - securitycenter.windows.com ou securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7b426-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="7b426-175">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="7b426-175">Related information</span></span>
- [<span data-ttu-id="7b426-176">Microsoft 365 Visão geral do Defender</span><span class="sxs-lookup"><span data-stu-id="7b426-176">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="7b426-177">Microsoft Defender para Ponto de Extremidade no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b426-177">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="7b426-178">A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança</span><span class="sxs-lookup"><span data-stu-id="7b426-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="7b426-179">Infográfico XDR versus SIEM</span><span class="sxs-lookup"><span data-stu-id="7b426-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="7b426-180">O Novo Defensor</span><span class="sxs-lookup"><span data-stu-id="7b426-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="7b426-181">Sobre Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b426-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="7b426-182">Portais de segurança e centros de administração da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b426-182">Microsoft security portals and admin centers</span></span>](portals.md)