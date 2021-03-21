---
title: Iniciar seu portal usando o Agendador de Início do Portal
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
description: Este artigo descreve como você pode iniciar seu portal usando o Agendador de Início do Portal
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926137"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="db2b9-103">Iniciar seu portal usando o Agendador de Início do Portal</span><span class="sxs-lookup"><span data-stu-id="db2b9-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="db2b9-104">Um portal é um site do SharePoint na intranet que tem um grande número de visualizadores de site que consomem o conteúdo dele.</span><span class="sxs-lookup"><span data-stu-id="db2b9-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="db2b9-105">Iniciar seu portal em ondas é uma parte importante para garantir que os usuários tenham uma experiência suave e performante acessando um novo portal do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="db2b9-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="db2b9-106">Iniciar em ondas é uma maneira fundamental de lançar seu portal, conforme detalhado em Planejamento do seu plano de lançamento de [portal no SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="db2b9-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span></span> <span data-ttu-id="db2b9-107">O Agendador de Início de Portal foi projetado para ajudá-lo a seguir uma abordagem de lançamento em fases/onda gerenciando os redirecionamentos para o novo portal.</span><span class="sxs-lookup"><span data-stu-id="db2b9-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="db2b9-108">Durante cada uma das ondas, você pode coletar comentários do usuário e monitorar o desempenho durante cada onda de implantação.</span><span class="sxs-lookup"><span data-stu-id="db2b9-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="db2b9-109">Isso tem a vantagem de introduzir lentamente o portal, dando a você a opção de pausar e resolver problemas antes de prosseguir com a próxima onda e, finalmente, garantir uma experiência positiva para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="db2b9-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="db2b9-110">Há dois tipos de redirecionamento:</span><span class="sxs-lookup"><span data-stu-id="db2b9-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="db2b9-111">bidirecional: iniciar um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno existente do SharePoint</span><span class="sxs-lookup"><span data-stu-id="db2b9-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="db2b9-112">redirecionamento de página temporária: iniciar um novo portal moderno do SharePoint Online sem portal existente do SharePoint</span><span class="sxs-lookup"><span data-stu-id="db2b9-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="db2b9-113">O agendador de início do portal só está disponível para iniciar portais modernos do SharePoint Online (ou seja, sites de comunicação).</span><span class="sxs-lookup"><span data-stu-id="db2b9-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="db2b9-114">Os lançamentos devem ser agendados com pelo menos 7 dias de antecedência.</span><span class="sxs-lookup"><span data-stu-id="db2b9-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="db2b9-115">O número de ondas necessárias é determinado pelo número esperado de usuários.</span><span class="sxs-lookup"><span data-stu-id="db2b9-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="db2b9-116">Antes de agendar um lançamento de portal, a ferramenta Diagnóstico de Página para [SharePoint](./page-diagnostics-for-spo.md) deve ser executado para verificar se a home page no portal está bem.</span><span class="sxs-lookup"><span data-stu-id="db2b9-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="db2b9-117">No final do início do portal, todos os usuários com permissões para o site poderão acessar o novo site.</span><span class="sxs-lookup"><span data-stu-id="db2b9-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="db2b9-118">Para obter mais informações sobre como iniciar um portal bem-sucedido, siga os princípios básicos, práticas e recomendações detalhados em Criação, lançamento e manutenção de [um portal saudável.](/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="db2b9-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="db2b9-119">Esse recurso não está disponível para planos do Office 365 Germany, Office 365 operado pela 21Vianet (China) ou Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="db2b9-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="db2b9-120">Configuração de aplicativo e conexão com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="db2b9-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="db2b9-121">[Baixe o Shell de Gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="db2b9-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="db2b9-p104">Se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá até Adicionar ou remover programas e desinstale o "Shell de Gerenciamento do SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="db2b9-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="db2b9-123">Na página Centro de Downloads, selecione seu idioma e clique no botão Download.</span><span class="sxs-lookup"><span data-stu-id="db2b9-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="db2b9-124">Você deverá escolher entre baixar um arquivo x64 e x86 .msi.</span><span class="sxs-lookup"><span data-stu-id="db2b9-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="db2b9-125">Baixe o arquivo x64 se estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="db2b9-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="db2b9-126">Se você não souber, consulte [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="db2b9-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="db2b9-127">Depois de baixar o arquivo, execute-o e siga as etapas do assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="db2b9-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="db2b9-128">Conecte-se ao SharePoint como um [administrador global ou administrador do SharePoint](/sharepoint/sharepoint-admin-role) no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db2b9-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="db2b9-129">Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="db2b9-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="db2b9-130">Exibir quaisquer configurações de início de portal existentes</span><span class="sxs-lookup"><span data-stu-id="db2b9-130">View any existing portal launch setups</span></span>

<span data-ttu-id="db2b9-131">Para ver se há configurações de início de portal existentes:</span><span class="sxs-lookup"><span data-stu-id="db2b9-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="db2b9-132">Agendar um início de portal no site</span><span class="sxs-lookup"><span data-stu-id="db2b9-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="db2b9-133">O número de ondas necessárias depende do tamanho de lançamento esperado.</span><span class="sxs-lookup"><span data-stu-id="db2b9-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="db2b9-134">Menos de 10 mil usuários: 1 onda</span><span class="sxs-lookup"><span data-stu-id="db2b9-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="db2b9-135">Usuários de 10 mil a 30 mil: 3 ondas</span><span class="sxs-lookup"><span data-stu-id="db2b9-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="db2b9-136">30k+ a 100 mil usuários: 5 ondas</span><span class="sxs-lookup"><span data-stu-id="db2b9-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="db2b9-137">Mais de 100 mil usuários: 5 ondas e contate sua equipe de conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="db2b9-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="db2b9-138">Etapas para redirecionamento bidirecional</span><span class="sxs-lookup"><span data-stu-id="db2b9-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="db2b9-139">O redirecionamento bidirecional envolve o lançamento de um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno existente do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="db2b9-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="db2b9-140">Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de navegar para o site antigo ou novo.</span><span class="sxs-lookup"><span data-stu-id="db2b9-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="db2b9-141">Os usuários em uma onda não lançada que tentam acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada.</span><span class="sxs-lookup"><span data-stu-id="db2b9-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="db2b9-142">Só há suporte para redirecionamento entre a home page padrão no site antigo e a home page padrão no novo site.</span><span class="sxs-lookup"><span data-stu-id="db2b9-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="db2b9-143">Se você tiver administradores ou proprietários que precisem de acesso aos sites antigos e novos sem serem redirecionados, verifique se eles estão listados usando o `WaveOverrideUsers` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="db2b9-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="db2b9-144">Para migrar usuários de um site existente do SharePoint para um novo site do SharePoint em estágios:</span><span class="sxs-lookup"><span data-stu-id="db2b9-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="db2b9-145">Execute o seguinte comando para designar as ondas de início do portal.</span><span class="sxs-lookup"><span data-stu-id="db2b9-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="db2b9-146">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="db2b9-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="db2b9-147">Validação completa.</span><span class="sxs-lookup"><span data-stu-id="db2b9-147">Complete validation.</span></span> <span data-ttu-id="db2b9-148">Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração em todo o serviço.</span><span class="sxs-lookup"><span data-stu-id="db2b9-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="db2b9-149">Etapas para redirecionamento para página temporária</span><span class="sxs-lookup"><span data-stu-id="db2b9-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="db2b9-150">O redirecionamento temporário de página deve ser usado quando nenhum portal existente do SharePoint existir.</span><span class="sxs-lookup"><span data-stu-id="db2b9-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="db2b9-151">Os usuários são direcionados para um novo portal moderno do SharePoint Online em estágios.</span><span class="sxs-lookup"><span data-stu-id="db2b9-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="db2b9-152">Se um usuário estiver em uma onda que não foi lançada, ele será redirecionado para uma página temporária (qualquer URL).</span><span class="sxs-lookup"><span data-stu-id="db2b9-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="db2b9-153">Execute o seguinte comando para designar as ondas de início do portal.</span><span class="sxs-lookup"><span data-stu-id="db2b9-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="db2b9-154">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="db2b9-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="db2b9-155">Validação completa.</span><span class="sxs-lookup"><span data-stu-id="db2b9-155">Complete validation.</span></span> <span data-ttu-id="db2b9-156">Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração em todo o serviço.</span><span class="sxs-lookup"><span data-stu-id="db2b9-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="db2b9-157">Pausar ou reiniciar um início de portal no site</span><span class="sxs-lookup"><span data-stu-id="db2b9-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="db2b9-158">Para pausar um lançamento de portal em andamento e impedir temporariamente que as progressões de onda futuras ocorram, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="db2b9-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="db2b9-159">Valide se todos os usuários são redirecionados para o site antigo.</span><span class="sxs-lookup"><span data-stu-id="db2b9-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="db2b9-160">Para reiniciar um lançamento de portal que foi pausado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="db2b9-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="db2b9-161">Valide se o redirecionamento foi restaurado.</span><span class="sxs-lookup"><span data-stu-id="db2b9-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="db2b9-162">Excluir um início de portal no site</span><span class="sxs-lookup"><span data-stu-id="db2b9-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="db2b9-163">Execute o seguinte comando para excluir um início de portal agendado ou em andamento para um site.</span><span class="sxs-lookup"><span data-stu-id="db2b9-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="db2b9-164">Valide se nenhum redirecionamento acontece para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="db2b9-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="db2b9-165">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="db2b9-165">Learn more</span></span>
[<span data-ttu-id="db2b9-166">Planejando seu plano de lançamento do portal no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="db2b9-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)