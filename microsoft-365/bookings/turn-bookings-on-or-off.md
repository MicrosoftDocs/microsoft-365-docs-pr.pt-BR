---
title: Ativar ou desativar o Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Saiba como obter acesso a reservas da Microsoft no Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126586"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="3e66e-103">Ativar ou desativar o Microsoft bookings</span><span class="sxs-lookup"><span data-stu-id="3e66e-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="3e66e-104">As reservas podem ser ativadas ou desativadas para toda a organização ou para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="3e66e-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="3e66e-105">Quando você ativa reservas para usuários, eles podem criar uma página de reservas, criar um calendário e permitir que outras pessoas façam o horário do livro.</span><span class="sxs-lookup"><span data-stu-id="3e66e-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="3e66e-106">Os controles de administração descritos nessas seções não estão disponíveis para os clientes do Office 365 operado pela 21Vianet (China).</span><span class="sxs-lookup"><span data-stu-id="3e66e-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="3e66e-107">Ativar ou desativar as reservas da sua organização usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e66e-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="3e66e-108">Entre no centro de administração do Microsoft 365 como um administrador global.</span><span class="sxs-lookup"><span data-stu-id="3e66e-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="3e66e-109">No centro de administração, vá para configurações da organização de  **configurações**   \> **Org Settings** e selecione **reservas**.</span><span class="sxs-lookup"><span data-stu-id="3e66e-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="3e66e-110">Marque a caixa de seleção para **permitir que sua organização Use reservas** para habilitar ou desabilitar reservas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3e66e-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3e66e-111">A desativação dos reservas desabilitará todo o acesso ao serviço, incluindo a criação e o gerenciamento de páginas de reservas.</span><span class="sxs-lookup"><span data-stu-id="3e66e-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="3e66e-112">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="3e66e-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="3e66e-113">Ativar ou desativar as reservas da sua organização usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e66e-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="3e66e-114">Para ativar ou desativar as reservas da sua organização usando o cmdlet do PowerShell [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3e66e-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="3e66e-115">Ativar ou desativar reservas para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="3e66e-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="3e66e-116">Você pode desabilitar reservas para usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="3e66e-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="3e66e-117">Vá para o centro de administração do Microsoft 365 e, em seguida, selecione usuários ativos do **usuário** \> **Active users**.</span><span class="sxs-lookup"><span data-stu-id="3e66e-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="3e66e-118">Selecione o usuário desejado e, em seguida, selecione **licenças e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3e66e-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="3e66e-119">Expanda **aplicativos** e desmarque a caixa de seleção de Microsoft bookings.</span><span class="sxs-lookup"><span data-stu-id="3e66e-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="3e66e-120">Exigir aprovações de equipe antes de compartilhar informações de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="3e66e-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="3e66e-121">Os administradores podem exigir que os funcionários de sua organização entrem em uma página para que as informações de disponibilidade sejam compartilhadas por meio de reservas e para poderem ser contratadas por meio de uma página de reserva.</span><span class="sxs-lookup"><span data-stu-id="3e66e-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="3e66e-122">Essa configuração está disponível no centro de administração do Microsoft 365 **em reservas de configurações** \> **Settings** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="3e66e-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="3e66e-123">Quando essa configuração é habilitada, os funcionários adicionados como equipe em calendários de reserva irão encontrar um link aprovar/rejeitar na notificação por email que receberem.</span><span class="sxs-lookup"><span data-stu-id="3e66e-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="3e66e-124">Esse recurso está implantando gradualmente a World Wide para clientes da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e66e-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="3e66e-125">Se você não vir essa opção no centro de administração do Microsoft 365, verifique novamente em breve.</span><span class="sxs-lookup"><span data-stu-id="3e66e-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="3e66e-126">Bloquear opções de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="3e66e-126">Block social sharing options</span></span>

<span data-ttu-id="3e66e-127">Os administradores podem controlar como as páginas de reserva são compartilhadas em redes sociais.</span><span class="sxs-lookup"><span data-stu-id="3e66e-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="3e66e-128">Essa configuração está disponível no centro de administração do Microsoft 365 **em reservas de configurações** \> **Settings** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="3e66e-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="3e66e-129">Esse recurso está implantando gradualmente a World Wide para clientes da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e66e-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="3e66e-130">Se você não vir essa opção no centro de administração do Microsoft 365, verifique novamente em breve.</span><span class="sxs-lookup"><span data-stu-id="3e66e-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="3e66e-131">Permitir que somente usuários selecionados criem calendários de reservas</span><span class="sxs-lookup"><span data-stu-id="3e66e-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="3e66e-132">Usando restrições de política, você pode restringir os usuários licenciados da capacidade de criar calendários de reservas.</span><span class="sxs-lookup"><span data-stu-id="3e66e-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="3e66e-133">Você deve primeiro habilitar reservas para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="3e66e-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="3e66e-134">Todos os usuários em sua organização terão licenças de reservas, mas apenas aquelas incluídas na política podem criar calendários de reservas e ter controle total sobre quem pode acessar os calendários criados.</span><span class="sxs-lookup"><span data-stu-id="3e66e-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="3e66e-135">Os usuários incluídos nessa política podem criar novos calendários de livros e podem ser adicionados como equipe em qualquer capacidade (incluindo a função de administrador) a calendários de livros existentes.</span><span class="sxs-lookup"><span data-stu-id="3e66e-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="3e66e-136">Os usuários que não estão incluídos nesta política não poderão criar novos calendários de livros e receberão uma mensagem de erro se tentarem fazer isso.</span><span class="sxs-lookup"><span data-stu-id="3e66e-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="3e66e-137">Você precisará executar os seguintes comandos usando o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3e66e-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="3e66e-138">Para obter mais informações sobre a execução de cmdlets do Exchange Online, consulte [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3e66e-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e66e-139">As etapas abaixo pressupõem que nenhuma outra política de caixa de correio do Outlook Web App (OWA) tenha sido criada em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3e66e-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="3e66e-140">Crie uma nova política de caixa de correio para usuários que devem ter permissão para criar calendários de reservas.</span><span class="sxs-lookup"><span data-stu-id="3e66e-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="3e66e-141">(A criação de calendário de livros é permitida por padrão por novas diretivas de caixa de correio).</span><span class="sxs-lookup"><span data-stu-id="3e66e-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="3e66e-142">Para obter mais informações, consulte [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="3e66e-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="3e66e-143">Atribua essa política aos usuários relevantes executando este comando para cada usuário que você deseja conceder permissão para criar calendários de reservas.</span><span class="sxs-lookup"><span data-stu-id="3e66e-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="3e66e-144">Para obter mais informações, consulte [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="3e66e-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="3e66e-145">Opcional: Execute este comando se desejar desabilitar reservas para todos os outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3e66e-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="3e66e-146">Para obter mais informações, consulte [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="3e66e-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="3e66e-147">Para obter mais informações sobre as políticas de caixa de correio do OWA, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3e66e-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="3e66e-148">Criar uma política de caixa de correio do Outlook na Web no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3e66e-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="3e66e-149">Aplicar ou remover uma política de caixa de correio do Outlook na Web em uma caixa de correio no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3e66e-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
