---
title: Iniciar seu portal usando o agendador de início do portal
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
description: Este artigo descreve como você pode iniciar seu portal usando o agendador de início do portal
ms.openlocfilehash: d7ea64b3a9fef25ddfde43e61624e49d2b7d4352
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280964"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="c76fa-103">Iniciar seu portal usando o agendador de SharePoint portal</span><span class="sxs-lookup"><span data-stu-id="c76fa-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="c76fa-104">Um portal é um site SharePoint de comunicação em sua intranet que é de alto tráfego – um site que tem de 10.000 a mais de 100.000 visualizadores ao longo de várias semanas.</span><span class="sxs-lookup"><span data-stu-id="c76fa-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="c76fa-105">Use o agendador de início do Portal para iniciar seu portal para garantir que os usuários tenham uma experiência de visualização suave ao acessar seu novo portal SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="c76fa-106">O agendador de início do Portal foi projetado para ajudá-lo a seguir uma abordagem de lançamento em fases, direcionando os visualizadores em lotes em ondas e gerenciando os redirecionamentos de URL para o novo portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="c76fa-107">Durante o início de cada onda, você pode coletar comentários do usuário, monitorar o desempenho do portal e pausar o lançamento para resolver problemas antes de prosseguir com a próxima onda.</span><span class="sxs-lookup"><span data-stu-id="c76fa-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="c76fa-108">Saiba mais sobre como planejar [um lançamento de portal em SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c76fa-108">Learn more about how to [plan a portal launch in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="c76fa-109">**Há dois tipos de redirecionamentos:**</span><span class="sxs-lookup"><span data-stu-id="c76fa-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="c76fa-110">**Bidirecional**: iniciar um novo portal SharePoint moderno para substituir um portal SharePoint clássico ou moderno existente</span><span class="sxs-lookup"><span data-stu-id="c76fa-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="c76fa-111">**Redirecionar para uma página temporária**: iniciar um novo portal SharePoint moderno sem nenhum portal SharePoint existente</span><span class="sxs-lookup"><span data-stu-id="c76fa-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="c76fa-112">As permissões de site devem ser configuradas separadamente das ondas como parte do lançamento.</span><span class="sxs-lookup"><span data-stu-id="c76fa-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="c76fa-113">Por exemplo, se você estiver liberando um portal de toda a organização, poderá definir permissões como "Todos, exceto usuários externos", em seguida, separe seus usuários em ondas usando grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="c76fa-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="c76fa-114">Adicionar um grupo de segurança a uma onda não dá acesso a esse grupo de segurança ao site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="c76fa-115">Esse recurso será acessível a partir do painel **Configurações** na home page de sites de comunicação do SharePoint para clientes de versão direcionada a partir de maio de 2021 e ficará disponível para todos os clientes até julho de 2021</span><span class="sxs-lookup"><span data-stu-id="c76fa-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="c76fa-116">A versão do PowerShell desta ferramenta está disponível hoje</span><span class="sxs-lookup"><span data-stu-id="c76fa-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="c76fa-117">Esse recurso só pode ser usado em sites de SharePoint de comunicação modernos</span><span class="sxs-lookup"><span data-stu-id="c76fa-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="c76fa-118">Você deve ter permissões de proprietário do site para que o site personalize e agende o lançamento de um portal</span><span class="sxs-lookup"><span data-stu-id="c76fa-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="c76fa-119">Os lançamentos devem ser agendados com pelo menos sete dias de antecedência e cada onda pode durar de um a sete dias</span><span class="sxs-lookup"><span data-stu-id="c76fa-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="c76fa-120">O número de ondas necessárias é determinado automaticamente pelo número esperado de usuários</span><span class="sxs-lookup"><span data-stu-id="c76fa-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="c76fa-121">Antes de agendar um lançamento de portal, a ferramenta Diagnóstico de Página para SharePoint [deve](https://aka.ms/perftool) ser executado para verificar se a home page do site é saudável</span><span class="sxs-lookup"><span data-stu-id="c76fa-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="c76fa-122">No final do lançamento, todos os usuários com permissões para o site poderão acessar o novo site</span><span class="sxs-lookup"><span data-stu-id="c76fa-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="c76fa-123">Se sua organização estiver usando o [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), os usuários poderão ver o ícone da sua organização na barra de aplicativos Microsoft Teams, no entanto, quando o ícone estiver selecionado, os usuários não poderão acessar o portal até que sua onda seja lançada</span><span class="sxs-lookup"><span data-stu-id="c76fa-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="c76fa-124">Esse recurso não está disponível para Office 365 Alemanha, Office 365 operado pela 21Vianet (China) ou Microsoft 365 do Governo dos EUA</span><span class="sxs-lookup"><span data-stu-id="c76fa-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="c76fa-125">Entenda as diferenças entre as opções do agendador de início do portal:</span><span class="sxs-lookup"><span data-stu-id="c76fa-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="c76fa-126">Anteriormente, os lançamentos de portal só podiam ser agendados por meio SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c76fa-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="c76fa-127">Agora, você tem duas opções para ajudá-lo a agendar e gerenciar o lançamento do portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="c76fa-128">Saiba mais sobre as principais diferenças entre ambas as ferramentas:</span><span class="sxs-lookup"><span data-stu-id="c76fa-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="c76fa-129">**SharePoint Versão do PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="c76fa-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="c76fa-130">As credenciais de administrador são necessárias para usar [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="c76fa-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="c76fa-131">Requisito mínimo de uma onda</span><span class="sxs-lookup"><span data-stu-id="c76fa-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="c76fa-132">Agendar seu lançamento com base no fuso horário UTC (Tempo Universal Coordenado)</span><span class="sxs-lookup"><span data-stu-id="c76fa-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="c76fa-133">**Versão no produto:**</span><span class="sxs-lookup"><span data-stu-id="c76fa-133">**In-product version:**</span></span>

- <span data-ttu-id="c76fa-134">As credenciais do proprietário do site são necessárias</span><span class="sxs-lookup"><span data-stu-id="c76fa-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="c76fa-135">Requisito mínimo de duas ondas</span><span class="sxs-lookup"><span data-stu-id="c76fa-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="c76fa-136">Agende seu lançamento com base no fuso horário local do portal, conforme indicado nas configurações regionais</span><span class="sxs-lookup"><span data-stu-id="c76fa-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="c76fa-137">Começar a usar o agendador de início do portal</span><span class="sxs-lookup"><span data-stu-id="c76fa-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="c76fa-138">Antes de usar a ferramenta agendador de início do Portal, adicione todos os usuários que precisarão de acesso a esse site por meio de permissões de [site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) como proprietário do site, membro do site ou visitante. </span><span class="sxs-lookup"><span data-stu-id="c76fa-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="c76fa-139">Em seguida, comece a agendar o lançamento do portal acessando o agendador de início do Portal de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="c76fa-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="c76fa-140">**Opção 1**: Nas primeiras vezes que você editar e republicar alterações na home page - ou até a home page versão 3.0 - você será solicitado a usar a ferramenta agendador de início do Portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="c76fa-141">Selecione **Agendar o início** para avançar com o agendamento.</span><span class="sxs-lookup"><span data-stu-id="c76fa-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="c76fa-142">Ou selecione **Republicar para** republicar suas edições de página sem agendar o lançamento.</span><span class="sxs-lookup"><span data-stu-id="c76fa-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![Imagem do prompt para usar o agendador de início do portal ao publicar a home page](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="c76fa-144">**Opção 2:** **a** qualquer momento, você pode navegar até a home page do site de comunicação SharePoint, selecione Configurações e agende o início do **site** para agendar o lançamento do portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![Imagem do painel Configurações agendar um lançamento de site realçada](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="c76fa-146">Em seguida, confirme a pontuação de saúde do portal e faça [melhorias](https://aka.ms/perftool) no portal, se necessário, usando a ferramenta Diagnóstico de Página para SharePoint até que seu portal receba uma **pontuação** Saudável.</span><span class="sxs-lookup"><span data-stu-id="c76fa-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="c76fa-147">Em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c76fa-147">Then, select **Next**.</span></span>

    ![Imagem da ferramenta agendador de início do portal](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="c76fa-149">O nome e **a descrição** do site não podem ser editados a partir do agendador de início do Portal e, em vez disso, podem ser alterados selecionando Configurações e, em seguida, informações **do** site na home page.</span><span class="sxs-lookup"><span data-stu-id="c76fa-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="c76fa-150">Selecione o **Número de usuários esperados** no drop-down.</span><span class="sxs-lookup"><span data-stu-id="c76fa-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="c76fa-151">Essa figura representa o número de usuários que provavelmente precisarão de acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="c76fa-152">O agendador de início do Portal determinará automaticamente o número ideal de ondas, dependendo dos usuários esperados como este:</span><span class="sxs-lookup"><span data-stu-id="c76fa-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="c76fa-153">Menos de 10 mil usuários: Duas ondas</span><span class="sxs-lookup"><span data-stu-id="c76fa-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="c76fa-154">Usuários de 10 mil a 30 mil: três ondas</span><span class="sxs-lookup"><span data-stu-id="c76fa-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="c76fa-155">30k+ a 100 mil usuários: Cinco ondas</span><span class="sxs-lookup"><span data-stu-id="c76fa-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="c76fa-156">Mais de 100 mil usuários: cinco ondas e contate sua equipe de conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c76fa-156">More than 100k users: Five waves and contact your Microsoft account team</span></span>

5.  <span data-ttu-id="c76fa-157">Em seguida, determine **o Tipo de redirecionamento** necessário:</span><span class="sxs-lookup"><span data-stu-id="c76fa-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="c76fa-158">Opção 1: Enviar usuários para uma página de SharePoint **existente (bidirecional)** – Use essa opção ao iniciar um novo portal SharePoint moderno para substituir um portal SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="c76fa-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="c76fa-159">Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de navegar para o site antigo ou novo.</span><span class="sxs-lookup"><span data-stu-id="c76fa-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="c76fa-160">Os usuários em uma onda não lançada que tentam acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada.</span><span class="sxs-lookup"><span data-stu-id="c76fa-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="c76fa-161">Ao usar a opção bidirecional, a pessoa que está agendando o lançamento também deve ter permissões de proprietário do site para o outro portal SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="c76fa-162">**Opção 2: Enviar** usuários para uma página temporária de geração automática (redirecionamento temporário de página) – Use um redirecionamento de página temporário deve ser usado quando não houver um portal SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="c76fa-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="c76fa-163">Os usuários são direcionados para um novo portal de SharePoint moderno e, se um usuário estiver em uma onda que não foi lançada, eles serão redirecionados para uma página temporária.</span><span class="sxs-lookup"><span data-stu-id="c76fa-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="c76fa-164">**Opção 3: Enviar usuários** para uma página externa – Fornecer uma URL externa para uma experiência de página de aterrissagem temporária até que a onda do usuário seja lançada.</span><span class="sxs-lookup"><span data-stu-id="c76fa-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="c76fa-165">Separar sua audiência em ondas.</span><span class="sxs-lookup"><span data-stu-id="c76fa-165">Break up your audience into waves.</span></span> <span data-ttu-id="c76fa-166">Adicione até 20 grupos de segurança por onda.</span><span class="sxs-lookup"><span data-stu-id="c76fa-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="c76fa-167">Os detalhes da onda podem ser editados até o início de cada onda.</span><span class="sxs-lookup"><span data-stu-id="c76fa-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="c76fa-168">Cada onda pode durar pelo menos um dia (24 horas) e, no máximo, sete dias.</span><span class="sxs-lookup"><span data-stu-id="c76fa-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="c76fa-169">Isso permite SharePoint e seu ambiente técnico uma oportunidade de se aclimatar e dimensionar para o grande volume de usuários do site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="c76fa-170">Ao agendar um lançamento pela interface do usuário, o fuso horário se baseia nas configurações regionais do site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="c76fa-171">O agendador de início do Portal será automaticamente padrão para um mínimo de 2 ondas.</span><span class="sxs-lookup"><span data-stu-id="c76fa-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="c76fa-172">No entanto, a versão do PowerShell desta ferramenta permitirá 1 onda.</span><span class="sxs-lookup"><span data-stu-id="c76fa-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="c76fa-173">Microsoft 365 grupos não são suportados por esta versão do agendador de início do Portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="c76fa-174">Determine quem precisa exibir o site imediatamente e insira suas informações no **campo Usuários isentos de** ondas.</span><span class="sxs-lookup"><span data-stu-id="c76fa-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="c76fa-175">Esses usuários são excluídos das ondas e não serão redirecionados antes, durante ou após o início.</span><span class="sxs-lookup"><span data-stu-id="c76fa-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

8.  <span data-ttu-id="c76fa-176">Confirme os detalhes de início do portal e selecione **Agendar**.</span><span class="sxs-lookup"><span data-stu-id="c76fa-176">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="c76fa-177">Depois que o lançamento tiver sido agendado, quaisquer alterações na home page do portal SharePoint precisarão receber um resultado de diagnóstico saudável antes que o início do portal seja retomado.</span><span class="sxs-lookup"><span data-stu-id="c76fa-177">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>


## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="c76fa-178">Fazer alterações em um lançamento de portal agendado</span><span class="sxs-lookup"><span data-stu-id="c76fa-178">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="c76fa-179">Os detalhes de início podem ser editados para cada onda até a data de início da onda.</span><span class="sxs-lookup"><span data-stu-id="c76fa-179">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="c76fa-180">Para editar detalhes de início do portal, navegue **até Configurações** e selecione **Agendar o início do site.**</span><span class="sxs-lookup"><span data-stu-id="c76fa-180">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="c76fa-181">Em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c76fa-181">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="c76fa-182">Quando terminar de fazer suas edições, selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="c76fa-182">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="c76fa-183">Excluir um lançamento de portal agendado</span><span class="sxs-lookup"><span data-stu-id="c76fa-183">Delete a scheduled portal launch</span></span>

<span data-ttu-id="c76fa-184">As iniciações agendadas usando a ferramenta agendador de início do Portal podem ser canceladas ou excluídas a qualquer momento, mesmo que algumas ondas já tenham sido lançadas.</span><span class="sxs-lookup"><span data-stu-id="c76fa-184">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="c76fa-185">Para cancelar o lançamento do seu portal, navegue até **Configurações** **e Agende o início do site.**</span><span class="sxs-lookup"><span data-stu-id="c76fa-185">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="c76fa-186">Em seguida, selecione **Excluir** e, em seguida, quando você vir a mensagem abaixo, selecione **Excluir** novamente.</span><span class="sxs-lookup"><span data-stu-id="c76fa-186">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![Imagem da ferramenta agendador de início do portal](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="c76fa-188">Usar o agendador de início do Portal do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76fa-188">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="c76fa-189">A SharePoint do agendador de início do Portal estava originalmente disponível apenas por meio do [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) e continuará a ter suporte por meio do PowerShell para clientes que preferem esse método.</span><span class="sxs-lookup"><span data-stu-id="c76fa-189">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="c76fa-190">As mesmas anotações no início deste artigo se aplicam às duas versões do agendador de início do Portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-190">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="c76fa-191">Você precisa de permissões de administrador para usar SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c76fa-191">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="c76fa-192">Os detalhes de início do portal para lançamentos criados no PowerShell serão exibidos e poderão ser gerenciados na nova ferramenta de agendador de início do Portal SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c76fa-192">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="c76fa-193">Configuração de aplicativo e conexão com SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c76fa-193">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="c76fa-194">[Baixe o Shell de Gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="c76fa-194">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c76fa-p116">Se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá até Adicionar ou remover programas e desinstale o "Shell de Gerenciamento do SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="c76fa-p116">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="c76fa-196">Na página Centro de Downloads, selecione seu idioma e clique no botão Download.</span><span class="sxs-lookup"><span data-stu-id="c76fa-196">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="c76fa-197">Você deverá escolher entre baixar um arquivo x64 e x86 .msi.</span><span class="sxs-lookup"><span data-stu-id="c76fa-197">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="c76fa-198">Baixe o arquivo x64 se estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c76fa-198">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="c76fa-199">Se você não souber, consulte [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="c76fa-199">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="c76fa-200">Depois de baixar o arquivo, execute-o e siga as etapas do assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="c76fa-200">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="c76fa-201">Conecte-se ao SharePoint como um [administrador global ou administrador do SharePoint](/sharepoint/sharepoint-admin-role) no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c76fa-201">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="c76fa-202">Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="c76fa-202">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="c76fa-203">Exibir quaisquer configurações de início de portal existentes</span><span class="sxs-lookup"><span data-stu-id="c76fa-203">View any existing portal launch setups</span></span>

<span data-ttu-id="c76fa-204">Para ver se há configurações de início de portal existentes:</span><span class="sxs-lookup"><span data-stu-id="c76fa-204">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="c76fa-205">Agendar um início de portal no site</span><span class="sxs-lookup"><span data-stu-id="c76fa-205">Schedule a portal launch on the site</span></span>

<span data-ttu-id="c76fa-206">O número de ondas necessárias depende do tamanho de lançamento esperado.</span><span class="sxs-lookup"><span data-stu-id="c76fa-206">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="c76fa-207">Menos de 10 mil usuários: uma onda</span><span class="sxs-lookup"><span data-stu-id="c76fa-207">Less than 10k users: One wave</span></span>
- <span data-ttu-id="c76fa-208">Usuários de 10 mil a 30 mil: três ondas</span><span class="sxs-lookup"><span data-stu-id="c76fa-208">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="c76fa-209">30k+ a 100 mil usuários: Cinco ondas</span><span class="sxs-lookup"><span data-stu-id="c76fa-209">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="c76fa-210">Mais de 100 mil usuários: cinco ondas e contate sua equipe de conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c76fa-210">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="c76fa-211">Etapas para redirecionamento bidirecional</span><span class="sxs-lookup"><span data-stu-id="c76fa-211">Steps for bidirectional redirection</span></span>

<span data-ttu-id="c76fa-212">O redirecionamento bidirecional envolve o lançamento de um novo portal SharePoint Online moderno para substituir um portal SharePoint clássico ou moderno existente.</span><span class="sxs-lookup"><span data-stu-id="c76fa-212">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="c76fa-213">Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de navegar para o site antigo ou novo.</span><span class="sxs-lookup"><span data-stu-id="c76fa-213">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="c76fa-214">Os usuários em uma onda não lançada que tentam acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada.</span><span class="sxs-lookup"><span data-stu-id="c76fa-214">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="c76fa-215">Só há suporte para redirecionamento entre a home page padrão no site antigo e a home page padrão no novo site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-215">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="c76fa-216">Se você tiver administradores ou proprietários que precisem de acesso aos sites antigos e novos sem serem redirecionados, verifique se eles estão listados usando o `WaveOverrideUsers` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c76fa-216">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="c76fa-217">Para migrar usuários de um site SharePoint existente para um novo site SharePoint em estágios:</span><span class="sxs-lookup"><span data-stu-id="c76fa-217">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="c76fa-218">Execute o seguinte comando para designar as ondas de início do portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-218">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="c76fa-219">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c76fa-219">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="c76fa-220">Validação completa.</span><span class="sxs-lookup"><span data-stu-id="c76fa-220">Complete validation.</span></span> <span data-ttu-id="c76fa-221">Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração em todo o serviço.</span><span class="sxs-lookup"><span data-stu-id="c76fa-221">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="c76fa-222">Etapas para redirecionamento para página temporária</span><span class="sxs-lookup"><span data-stu-id="c76fa-222">Steps for redirection to temporary page</span></span>

<span data-ttu-id="c76fa-223">O redirecionamento temporário de página deve ser usado quando nenhum portal SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="c76fa-223">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="c76fa-224">Os usuários são direcionados para um novo portal SharePoint Online em estágios.</span><span class="sxs-lookup"><span data-stu-id="c76fa-224">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="c76fa-225">Se um usuário estiver em uma onda que não foi lançada, ele será redirecionado para uma página temporária (qualquer URL).</span><span class="sxs-lookup"><span data-stu-id="c76fa-225">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="c76fa-226">Execute o seguinte comando para designar as ondas de início do portal.</span><span class="sxs-lookup"><span data-stu-id="c76fa-226">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="c76fa-227">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c76fa-227">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="c76fa-228">Validação completa.</span><span class="sxs-lookup"><span data-stu-id="c76fa-228">Complete validation.</span></span> <span data-ttu-id="c76fa-229">Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração em todo o serviço.</span><span class="sxs-lookup"><span data-stu-id="c76fa-229">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="c76fa-230">Pausar ou reiniciar um início de portal no site</span><span class="sxs-lookup"><span data-stu-id="c76fa-230">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="c76fa-231">Para pausar um lançamento de portal em andamento e impedir temporariamente que as progressões de onda futuras ocorram, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c76fa-231">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="c76fa-232">Valide se todos os usuários são redirecionados para o site antigo.</span><span class="sxs-lookup"><span data-stu-id="c76fa-232">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="c76fa-233">Para reiniciar um lançamento de portal que foi pausado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c76fa-233">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="c76fa-234">Valide se o redirecionamento foi restaurado.</span><span class="sxs-lookup"><span data-stu-id="c76fa-234">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="c76fa-235">Excluir um início de portal no site</span><span class="sxs-lookup"><span data-stu-id="c76fa-235">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="c76fa-236">Execute o seguinte comando para excluir um início de portal agendado ou em andamento para um site.</span><span class="sxs-lookup"><span data-stu-id="c76fa-236">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="c76fa-237">Valide se nenhum redirecionamento acontece para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c76fa-237">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c76fa-238">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="c76fa-238">Learn more</span></span>

[<span data-ttu-id="c76fa-239">Planejando seu plano de lançamento do portal no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c76fa-239">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="c76fa-240">Planejar seu site de comunicação</span><span class="sxs-lookup"><span data-stu-id="c76fa-240">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
