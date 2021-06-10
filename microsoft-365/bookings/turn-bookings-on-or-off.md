---
title: Ativar ou desativar o Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Saiba como obter acesso ao Microsoft Bookings Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913761"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="3d7d3-103">Ativar ou desativar o Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="3d7d3-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="3d7d3-104">As reservas podem ser ativas ou desligadas para toda a organização ou para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="3d7d3-105">Ao ativar o Bookings para usuários, eles podem criar uma página do Bookings, criar um calendário e permitir que outras pessoas reservem tempo com eles.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7d3-106">Os controles de administrador descritos nessas seções não estão disponíveis para Office 365 operados por clientes da 21Vianet (China).</span><span class="sxs-lookup"><span data-stu-id="3d7d3-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="3d7d3-107">Ativar ou desativar o Bookings para sua organização usando o Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="3d7d3-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="3d7d3-108">Entre no centro de administração Microsoft 365 como administrador global.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="3d7d3-109">No centro de administração, vá  **para** Configurações   \> **Org Configurações** e selecione **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="3d7d3-110">Marque a caixa de seleção Permitir **que sua organização use o Bookings** para habilitar ou desabilitar o Bookings para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3d7d3-111">Desativar o Bookings desabilitará todo o acesso ao serviço, incluindo a criação e o gerenciamento de páginas do Bookings.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="3d7d3-112">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="3d7d3-113">Ativar ou desativar o Bookings para sua organização usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d7d3-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="3d7d3-114">Para ativar ou desativar o Bookings para sua organização usando o cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)do PowerShell, Conexão para [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) e executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3d7d3-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="3d7d3-115">Ativar ou desativar o Bookings para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="3d7d3-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="3d7d3-116">Você pode desabilitar o Bookings para usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="3d7d3-117">Vá para o Microsoft 365 de administração e selecione **Usuários** \> **Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="3d7d3-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="3d7d3-118">Selecione o usuário desejado e selecione **Licenças e Aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="3d7d3-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="3d7d3-119">Expanda **Aplicativos** e limpe a caixa de seleção do Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="3d7d3-120">Exigir aprovações da equipe antes de compartilhar informações de livre/ocupado</span><span class="sxs-lookup"><span data-stu-id="3d7d3-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="3d7d3-121">Os administradores podem exigir que os funcionários em sua organização se adotem antes que suas informações de disponibilidade sejam compartilhadas por meio do Bookings e antes que eles possam ser reservados por meio de uma página de reserva.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="3d7d3-122">Essa configuração está disponível no centro de administração Microsoft 365 **em** Configurações \> **Configurações** \> **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="3d7d3-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="3d7d3-123">Quando essa configuração estiver habilitada, os funcionários adicionados como funcionários nos calendários de reserva encontrarão um link Aprovar/Rejeitar na notificação de email recebida.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="3d7d3-124">Esse recurso está implantando gradualmente todo o mundo para Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="3d7d3-125">Se você não vir essa opção no centro de administração Microsoft 365, verifique novamente em breve.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="3d7d3-126">Bloquear opções de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="3d7d3-126">Block social sharing options</span></span>

<span data-ttu-id="3d7d3-127">Os administradores podem controlar como as páginas de reserva são compartilhadas nas redes sociais.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="3d7d3-128">Essa configuração está disponível no centro de administração Microsoft 365 **em** Configurações \> **Configurações** \> **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="3d7d3-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="3d7d3-129">Esse recurso está implantando gradualmente todo o mundo para Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="3d7d3-130">Se você não vir essa opção no centro de administração Microsoft 365, verifique novamente em breve.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="3d7d3-131">Permitir que apenas usuários selecionados criem calendários do Bookings</span><span class="sxs-lookup"><span data-stu-id="3d7d3-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="3d7d3-132">Usando restrições de política, você pode restringir os usuários licenciados de serem capazes de criar calendários do Bookings.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="3d7d3-133">Primeiro, você deve habilitar o Bookings para toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="3d7d3-134">Todos os usuários em sua organização terão licenças do Bookings, mas somente aqueles incluídos na política podem criar calendários do Bookings e ter controle total sobre quem pode acessar os calendários que eles criam.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="3d7d3-135">Os usuários incluídos nesta política podem criar novos calendários do Bookings e podem ser adicionados como funcionários em qualquer capacidade (incluindo a função de administrador) aos calendários existentes do Bookings.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="3d7d3-136">Os usuários que não estão incluídos nesta política não poderão criar novos calendários do Bookings e receberão uma mensagem de erro se tentarem fazer isso.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="3d7d3-137">Você precisará executar os seguintes comandos usando o Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="3d7d3-138">Para obter mais informações sobre como executar Exchange Online cmdlets, consulte [Conexão para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d7d3-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d7d3-139">As etapas a seguir pressuem que nenhuma outra Outlook Web App de caixa de correio (OWA) tenha sido criada em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="3d7d3-140">Crie uma nova política de caixa de correio para usuários que devem ter permissão para criar calendários do Bookings.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="3d7d3-141">(A criação de calendário do Bookings é permitida por padrão por novas políticas de caixa de correio.)</span><span class="sxs-lookup"><span data-stu-id="3d7d3-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="3d7d3-142">Para obter mais informações, [consulte New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="3d7d3-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="3d7d3-143">Atribua essa política aos usuários relevantes executando esse comando para cada usuário que você deseja conceder permissão para criar calendários do Bookings.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="3d7d3-144">Para obter mais informações, consulte [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="3d7d3-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="3d7d3-145">Opcional: execute este comando se quiser desabilitar o Bookings para todos os outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d7d3-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="3d7d3-146">Para obter mais informações, consulte [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="3d7d3-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="3d7d3-147">Para obter mais informações sobre políticas de caixa de correio do OWA, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3d7d3-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="3d7d3-148">Criar um Outlook na política de caixa de correio da Web em Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3d7d3-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="3d7d3-149">Aplicar ou remover um Outlook na política de caixa de correio da Web em uma caixa de correio em Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3d7d3-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)