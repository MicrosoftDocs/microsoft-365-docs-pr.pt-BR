---
title: Configurar as opções de lançamento padrão ou direcionadas
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Saiba como configurar a opção de lançamento para novas atualizações de produtos e recursos no centro de administração do Microsoft 365.
ms.openlocfilehash: 110cefa646f7c42c6979a97ca617b015a100866e
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324531"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="e1e40-103">Configurar as opções de lançamento padrão ou direcionadas</span><span class="sxs-lookup"><span data-stu-id="e1e40-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e1e40-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="e1e40-104">The admin center is changing.</span></span> <span data-ttu-id="e1e40-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e1e40-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="e1e40-106">As atualizações 365 da Microsoft descritas neste artigo aplicam-se ao Microsoft 365, ao SharePoint Online e ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e1e40-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="e1e40-107">Essas opções de versão são direcionadas, as melhores maneiras de lançar as alterações no Microsoft 365, mas não podem ser garantidas sempre ou para todas as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e1e40-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="e1e40-108">Eles não se aplicam a aplicativos do Microsoft 365, Skype for Business, Microsoft Teams e serviços relacionados.</span><span class="sxs-lookup"><span data-stu-id="e1e40-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="e1e40-109">Para obter informações sobre as opções de versão para aplicativos Microsoft 365, consulte [Overview of Update Channels for microsoft 365 apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="e1e40-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="e1e40-110">Com o Microsoft 365, você recebe novos recursos e atualizações de produtos à medida que eles são disponibilizados em vez de realizar atualizações dispendiosas a cada ano.</span><span class="sxs-lookup"><span data-stu-id="e1e40-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="e1e40-111">Você pode gerenciar como sua organização recebe essas atualizações.</span><span class="sxs-lookup"><span data-stu-id="e1e40-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="e1e40-112">Por exemplo, você pode se inscrever em uma versão antecipada para que sua organização receba as atualizações primeiro.</span><span class="sxs-lookup"><span data-stu-id="e1e40-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="e1e40-113">Você pode designar que apenas alguns usuários recebem as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e1e40-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="e1e40-114">Ou você pode permanecer no cronograma de lançamento padrão e receber as atualizações mais tarde.</span><span class="sxs-lookup"><span data-stu-id="e1e40-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="e1e40-115">Este artigo explica as diferentes opções de versão e como você pode usá-las para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e1e40-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="e1e40-116">Como funciona - validação de versão</span><span class="sxs-lookup"><span data-stu-id="e1e40-116">How it works - release validation</span></span>

<span data-ttu-id="e1e40-117">Qualquer nova versão é testada e validada pela equipe de recursos e, em seguida, por toda a equipe de recursos do Microsoft 365, seguida por toda a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1e40-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="e1e40-118">Depois de testes internos e validação, a próxima etapa é um **lançamento direcionado** (conhecido anteriormente como Primeiro Lançamento) para clientes que aceitarem.</span><span class="sxs-lookup"><span data-stu-id="e1e40-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="e1e40-119">Em cada anel de lançamento, a Microsoft coleta comentários e valida mais a qualidade ao monitorar métricas de utilização importantes.</span><span class="sxs-lookup"><span data-stu-id="e1e40-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="e1e40-120">Esta série de processos progressivos de validação serve para garantir que a versão mundial seja o mais robusta possível.</span><span class="sxs-lookup"><span data-stu-id="e1e40-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="e1e40-121">As versões são ilustradas na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="e1e40-121">The releases are pictured in the following figure.</span></span> 
  
![Liberar toques de validação para o Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="e1e40-123">Para atualizações significativas, os clientes são inicialmente notificados pelo [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="e1e40-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="e1e40-124">Como uma atualização está mais próxima de ser implantada, ela é comunicada através do seu [centro de mensagens do Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="e1e40-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="e1e40-125">Você precisa de uma conta do Microsoft 365 ou do Azure AD para acessar seu centro de mensagens por meio do [centro de administração](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e1e40-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="e1e40-126">O Microsoft 365 Home Plan Users não têm um centro de administração.</span><span class="sxs-lookup"><span data-stu-id="e1e40-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="e1e40-127">Lançamento padrão</span><span class="sxs-lookup"><span data-stu-id="e1e40-127">Standard release</span></span>

<span data-ttu-id="e1e40-128">Esta é a opção padrão em que você e seus usuários recebem as atualizações mais recentes quando são lançadas amplamente para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="e1e40-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="e1e40-129">Uma boa prática é deixar a maioria dos usuários em **lançamentos padrão** e profissionais de ti e usuários avançados no **lançamento direcionado** para avaliar novos recursos e preparar o Microsoft Teams para dar suporte a usuários e executivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="e1e40-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e1e40-130">Caso mude do lançamento direcionado para o padrão, seus usuários podem perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="e1e40-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="e1e40-131">Lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="e1e40-131">Targeted release</span></span>

<span data-ttu-id="e1e40-p107">Com esta opção, você e seus usuários podem ser os primeiros a conferir as atualizações mais recentes e ajudar no ajuste do produto, fornecendo comentários antecipadamente. Você pode optar que algumas pessoas ou que toda a organização receba as atualizações antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="e1e40-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1e40-p108">As atualizações grandes ou complexas podem demorar mais do que as outras, portanto, nenhum usuário é afetado negativamente. Não há garantia quanto à linha do tempo exata de uma versão.</span><span class="sxs-lookup"><span data-stu-id="e1e40-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="e1e40-136">Lançamento direcionado para toda a organização</span><span class="sxs-lookup"><span data-stu-id="e1e40-136">Targeted release for entire organization</span></span>

<span data-ttu-id="e1e40-137">Se você [Configurar a opção de lançamento no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, todos os usuários receberão a experiência de lançamento direcionada.</span><span class="sxs-lookup"><span data-stu-id="e1e40-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="e1e40-138">Para organizações com mais de 300 usuários, recomendamos usar uma assinatura de teste para essa opção.</span><span class="sxs-lookup"><span data-stu-id="e1e40-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="e1e40-139">Para obter informações sobre a assinatura de teste, fale com seu contato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1e40-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="e1e40-140">Lançamento direcionado para usuários selecionados</span><span class="sxs-lookup"><span data-stu-id="e1e40-140">Targeted release for selected users</span></span>

<span data-ttu-id="e1e40-141">Se você [Configurar a opção liberar no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, é possível definir usuários específicos, geralmente usuários avançados, para receber acesso antecipado aos recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="e1e40-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="e1e40-142">Benefícios do lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="e1e40-142">Benefits of Targeted release</span></span>

<span data-ttu-id="e1e40-143">O lançamento direcionado permite que os administradores, os gerentes de alteração ou qualquer pessoa responsável pelas atualizações da Microsoft 365 se preparam nas alterações futuras, permitindo que eles:</span><span class="sxs-lookup"><span data-stu-id="e1e40-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="e1e40-144">Testem e validem novas atualizações antes de elas serem lançadas para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="e1e40-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="e1e40-145">Preparem a notificação para os usuários e a documentação antes que as atualizações sejam lançadas para todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="e1e40-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="e1e40-146">Preparem uma central de ajuda interna para as alterações futuras.</span><span class="sxs-lookup"><span data-stu-id="e1e40-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="e1e40-147">Analisem as revisões de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="e1e40-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="e1e40-148">Usem controles de recursos, quando aplicável, para controlar o lançamento das atualizações para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="e1e40-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="e1e40-149">Configurar a opção de lançamento no centro de administração</span><span class="sxs-lookup"><span data-stu-id="e1e40-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="e1e40-150">Você pode alterar como sua organização recebe as atualizações da Microsoft 365 seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e1e40-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="e1e40-151">Você precisa ser um administrador global no Microsoft 365 para aceitar o.</span><span class="sxs-lookup"><span data-stu-id="e1e40-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1e40-152">Pode levar até 24 horas para que as alterações abaixo tenham efeito no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1e40-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="e1e40-153">Se você optar por cancelar o lançamento direcionado depois de ativá-lo, os usuários poderão perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="e1e40-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="e1e40-154">No centro de administração, vá para a **Settings**  >  **configuração org**Settings e, na guia **perfil da organização** , escolha **preferências de versão**.</span><span class="sxs-lookup"><span data-stu-id="e1e40-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="e1e40-155">Para desabilitar o lançamento direcionado, selecione **versão padrão**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="e1e40-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="e1e40-156">Para habilitar o lançamento direcionado para todos os usuários em sua organização, selecione **lançamento direcionado para todos**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="e1e40-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="e1e40-157">Para habilitar o lançamento direcionado para algumas pessoas em sua organização, selecione **lançamento direcionado para usuários selecionados**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="e1e40-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="e1e40-158">Escolha **Selecionar usuários** para adicionar usuários, um de cada vez, ou **carregar usuários** para adicioná-los em massa.</span><span class="sxs-lookup"><span data-stu-id="e1e40-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="e1e40-159">Quando terminar de adicionar usuários, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="e1e40-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="e1e40-160">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="e1e40-160">Learn more</span></span>

<span data-ttu-id="e1e40-161">Descubra como [gerenciar mensagens](https://docs.microsoft.com/office365/admin/manage/message-center) no seu [centro de mensagens do Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obter notificações sobre futuras atualizações e versões do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1e40-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
