---
title: Iniciar o portal usando o Agendador de lançamento do portal
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: Este artigo descreve como você pode iniciar seu portal usando o Agendador de lançamento do portal
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999560"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="f7628-103">Iniciar o portal usando o Agendador de lançamento do portal</span><span class="sxs-lookup"><span data-stu-id="f7628-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="f7628-104">Você pode iniciar o portal usando o Agendador de lançamento do portal primeiro validando a capacidade do administrador de locatários de configurar uma ondas para um novo Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="f7628-105">Em seguida, o administrador pode validar um redirecionamento de solicitações, com base na existência de um usuário nas ondas ativas.</span><span class="sxs-lookup"><span data-stu-id="f7628-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="f7628-106">Para obter mais informações sobre como iniciar um portal bem-sucedido, siga os princípios básicos, as práticas e as recomendações detalhadas na [criação, inicialização e manutenção de um portal saudável](https://go.microsoft.com/fwlink/?linkid=2105838).</span><span class="sxs-lookup"><span data-stu-id="f7628-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="f7628-107">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="f7628-107">App setup</span></span>
1. <span data-ttu-id="f7628-108">Desinstale-o se existir um `Microsoft.Online.SharePoint.PowerShell` no seu computador por meio do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="f7628-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="f7628-109">Na passagem do PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="f7628-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="f7628-110">Conectar ao SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7628-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="f7628-111">Abra o [Shell de gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) no Windows.</span><span class="sxs-lookup"><span data-stu-id="f7628-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="f7628-112">Conecte-se ao seu locatário como administrador.</span><span class="sxs-lookup"><span data-stu-id="f7628-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="f7628-113">Forneça sua senha quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="f7628-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="f7628-114">Comando para obter uma configuração existente</span><span class="sxs-lookup"><span data-stu-id="f7628-114">Command to get an existing setup</span></span>

<span data-ttu-id="f7628-115">Para exibir as configurações de lançamento de portal existentes:</span><span class="sxs-lookup"><span data-stu-id="f7628-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="f7628-116">Passagem `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="f7628-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="f7628-117">Passe o parâmetro adicional `-DisplayFormat Raw` se você quiser ver a coleção Wave formatada como um formato de entrada bruto.</span><span class="sxs-lookup"><span data-stu-id="f7628-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="f7628-118">Comandos para redirecionamento bidirecional</span><span class="sxs-lookup"><span data-stu-id="f7628-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="f7628-119">Para migrar usuários antigos do site para o novo site de uma maneira em estágios:</span><span class="sxs-lookup"><span data-stu-id="f7628-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="f7628-120">Criar ondas de lançamento do Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="f7628-121">Isso só é aplicável na fase de teste de versão inicial.</span><span class="sxs-lookup"><span data-stu-id="f7628-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="f7628-122">Para testar o impacto da alteração imediatamente, certifique-se de que a primeira onda `LaunchDateUtc` está definida como a data atual.</span><span class="sxs-lookup"><span data-stu-id="f7628-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="f7628-123">Se você não fornecer esse sinalizador, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="f7628-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="f7628-124">Esse erro ocorre porque o lançamento em produção deve ser agendado pelo menos 7 dias antes.</span><span class="sxs-lookup"><span data-stu-id="f7628-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="f7628-125">Concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="f7628-125">Complete validation.</span></span>
  - <span data-ttu-id="f7628-126">Pode levar até 5 minutos para que o redirecionamento conclua sua configuração no serviço, portanto, aguarde antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f7628-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="f7628-127">Se você efetuar logon com o usuário especificado como `WaveOverrideUsers` , então nada será alterado.</span><span class="sxs-lookup"><span data-stu-id="f7628-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="f7628-128">Você deve permanecer no site para o qual navegou.</span><span class="sxs-lookup"><span data-stu-id="f7628-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="f7628-129">Faça logon com um usuário que faz parte dos *visualizadores SG1*.</span><span class="sxs-lookup"><span data-stu-id="f7628-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="f7628-130">Navegue até o site antigo e você deve ser redirecionado para o novo site.</span><span class="sxs-lookup"><span data-stu-id="f7628-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="f7628-131">Navegue até o novo site e você deverá permanecer no novo site.</span><span class="sxs-lookup"><span data-stu-id="f7628-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="f7628-132">Faça logon com user em *visualizadores SG2* e navegue até o site antigo e permaneça no site antigo.</span><span class="sxs-lookup"><span data-stu-id="f7628-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="f7628-133">Navegue até o novo site e você deve ser redirecionado para o site antigo.</span><span class="sxs-lookup"><span data-stu-id="f7628-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="f7628-134">Pausar o lançamento do Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="f7628-135">Se for necessário pausar as ondas de lançamento, você poderá pausá-las por número de dias.</span><span class="sxs-lookup"><span data-stu-id="f7628-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="f7628-136">Definir o `Status` sinalizador para pausa impede que todos os futuros progressos da onda.</span><span class="sxs-lookup"><span data-stu-id="f7628-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="f7628-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="f7628-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="f7628-138">Isso valida que todos os usuários são redirecionados para o site antigo.</span><span class="sxs-lookup"><span data-stu-id="f7628-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="f7628-139">Reinicie o andamento do lançamento do Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="f7628-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="f7628-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="f7628-141">Valide se o redirecionamento agora é restaurado.</span><span class="sxs-lookup"><span data-stu-id="f7628-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="f7628-142">Excluir uma configuração de início de Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="f7628-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="f7628-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="f7628-144">Validar que nenhum redirecionamento ocorre para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="f7628-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="f7628-145">Comandos de redirecionamento para página temporária</span><span class="sxs-lookup"><span data-stu-id="f7628-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="f7628-146">Siga estas etapas se você não tiver um site anterior e deseja omitir usuários que não estão no pouso da onda na nova página do Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="f7628-147">Para criar uma página temporária em qualquer um dos sites:</span><span class="sxs-lookup"><span data-stu-id="f7628-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="f7628-148">Criar uma onda de lançamento do Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="f7628-149">Concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="f7628-149">Complete validation.</span></span>

  - <span data-ttu-id="f7628-150">Aguarde cinco minutos antes de continuar, pois a ação pode levar até cinco minutos para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="f7628-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="f7628-151">Faça logon com o usuário que faz parte dos *visualizadores SG1* e:</span><span class="sxs-lookup"><span data-stu-id="f7628-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="f7628-152">Navegue até o novo site e você deve estar no novo site.</span><span class="sxs-lookup"><span data-stu-id="f7628-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="f7628-153">Navegue até a página temporária e você deve estar na página Temp.</span><span class="sxs-lookup"><span data-stu-id="f7628-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="f7628-154">Faça logon com o usuário que faz parte dos *visualizadores SG2* e:</span><span class="sxs-lookup"><span data-stu-id="f7628-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="f7628-155">Navegue até o novo site, e você deve ser redirecionado para a página Temp.</span><span class="sxs-lookup"><span data-stu-id="f7628-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="f7628-156">Navegue até a página temporária e você deve permanecer na página Temp.</span><span class="sxs-lookup"><span data-stu-id="f7628-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="f7628-157">Excluir uma configuração de início de Portal.</span><span class="sxs-lookup"><span data-stu-id="f7628-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="f7628-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="f7628-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="f7628-159">Validar que nenhum redirecionamento ocorre para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="f7628-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="f7628-160">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="f7628-160">Learn more</span></span>
[<span data-ttu-id="f7628-161">Planejando o plano de distribuição de início do portal no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7628-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)