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
ms.openlocfilehash: 4b26a3e95b11feb5c6a5894702b86e74f82bde03
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399687"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="826c0-103">Configurar as opções de lançamento padrão ou direcionadas</span><span class="sxs-lookup"><span data-stu-id="826c0-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="826c0-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="826c0-104">The admin center is changing.</span></span> <span data-ttu-id="826c0-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="826c0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="826c0-106">Com o Microsoft 365, você recebe novos recursos e atualizações de produtos à medida que eles são disponibilizados em vez de realizar atualizações dispendiosas a cada ano.</span><span class="sxs-lookup"><span data-stu-id="826c0-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="826c0-107">Você pode gerenciar como sua organização recebe essas atualizações.</span><span class="sxs-lookup"><span data-stu-id="826c0-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="826c0-108">Por exemplo, você pode se inscrever em uma versão antecipada para que sua organização receba as atualizações primeiro.</span><span class="sxs-lookup"><span data-stu-id="826c0-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="826c0-109">Você pode designar que apenas alguns usuários recebem as atualizações.</span><span class="sxs-lookup"><span data-stu-id="826c0-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="826c0-110">Ou você pode permanecer no cronograma de lançamento padrão e receber as atualizações mais tarde.</span><span class="sxs-lookup"><span data-stu-id="826c0-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="826c0-111">Este artigo explica as diferentes opções de versão e como você pode usá-las para sua organização.</span><span class="sxs-lookup"><span data-stu-id="826c0-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="826c0-112">As atualizações 365 da Microsoft descritas neste artigo aplicam-se ao Microsoft 365, ao SharePoint Online e ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="826c0-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="826c0-113">Elas não se aplicam ao Skype for Business e aos serviços relacionados.</span><span class="sxs-lookup"><span data-stu-id="826c0-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="826c0-114">Essas opções de versão são direcionadas, as melhores maneiras de lançar as alterações no Microsoft 365, mas não podem ser garantidas sempre ou para todas as atualizações.</span><span class="sxs-lookup"><span data-stu-id="826c0-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="826c0-115">Como funciona - validação de versão</span><span class="sxs-lookup"><span data-stu-id="826c0-115">How it works - release validation</span></span>

<span data-ttu-id="826c0-116">Qualquer nova versão é testada e validada pela equipe de recursos e, em seguida, por toda a equipe de recursos do Microsoft 365, seguida por toda a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="826c0-116">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="826c0-117">Depois de testes internos e validação, a próxima etapa é um **lançamento direcionado** (conhecido anteriormente como Primeiro Lançamento) para clientes que aceitarem.</span><span class="sxs-lookup"><span data-stu-id="826c0-117">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="826c0-118">Em cada anel de lançamento, a Microsoft coleta comentários e valida mais a qualidade ao monitorar métricas de utilização importantes.</span><span class="sxs-lookup"><span data-stu-id="826c0-118">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="826c0-119">Esta série de processos progressivos de validação serve para garantir que a versão mundial seja o mais robusta possível.</span><span class="sxs-lookup"><span data-stu-id="826c0-119">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="826c0-120">As versões são ilustradas na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="826c0-120">The releases are pictured in the following figure.</span></span> 
  
![Liberar toques de validação para o Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="826c0-122">Para atualizações significativas, os clientes são inicialmente notificados pelo [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="826c0-122">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="826c0-123">Como uma atualização está mais próxima de ser implantada, ela é comunicada através do seu [centro de mensagens do Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="826c0-123">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="826c0-124">Você precisa de uma conta do Microsoft 365 ou do Azure AD para acessar seu centro de mensagens por meio do [centro de administração](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="826c0-124">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="826c0-125">O Microsoft 365 Home Plan Users não têm um centro de administração.</span><span class="sxs-lookup"><span data-stu-id="826c0-125">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="826c0-126">Lançamento padrão</span><span class="sxs-lookup"><span data-stu-id="826c0-126">Standard release</span></span>

<span data-ttu-id="826c0-127">Esta é a opção padrão em que você e seus usuários recebem as atualizações mais recentes quando são lançadas amplamente para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="826c0-127">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="826c0-128">Uma boa prática é deixar a maioria dos usuários em **lançamentos padrão** e profissionais de ti e usuários avançados no **lançamento direcionado** para avaliar novos recursos e preparar o Microsoft Teams para dar suporte a usuários e executivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="826c0-128">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="826c0-129">Caso mude do lançamento direcionado para o padrão, seus usuários podem perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="826c0-129">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="826c0-130">Lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="826c0-130">Targeted release</span></span>

<span data-ttu-id="826c0-p107">Com esta opção, você e seus usuários podem ser os primeiros a conferir as atualizações mais recentes e ajudar no ajuste do produto, fornecendo comentários antecipadamente. Você pode optar que algumas pessoas ou que toda a organização receba as atualizações antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="826c0-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="826c0-p108">As atualizações grandes ou complexas podem demorar mais do que as outras, portanto, nenhum usuário é afetado negativamente. Não há garantia quanto à linha do tempo exata de uma versão.</span><span class="sxs-lookup"><span data-stu-id="826c0-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="826c0-135">Lançamento direcionado para toda a organização</span><span class="sxs-lookup"><span data-stu-id="826c0-135">Targeted release for entire organization</span></span>

<span data-ttu-id="826c0-136">Se você [Configurar a opção de lançamento no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, todos os usuários receberão a experiência de lançamento direcionada.</span><span class="sxs-lookup"><span data-stu-id="826c0-136">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="826c0-137">Para organizações com mais de 300 usuários, recomendamos usar uma assinatura de teste para essa opção.</span><span class="sxs-lookup"><span data-stu-id="826c0-137">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="826c0-138">Para obter informações sobre a assinatura de teste, fale com seu contato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="826c0-138">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="826c0-139">Lançamento direcionado para usuários selecionados</span><span class="sxs-lookup"><span data-stu-id="826c0-139">Targeted release for selected users</span></span>

<span data-ttu-id="826c0-140">Se você [Configurar a opção liberar no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, é possível definir usuários específicos, geralmente usuários avançados, para receber acesso antecipado aos recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="826c0-140">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="826c0-141">Benefícios do lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="826c0-141">Benefits of Targeted release</span></span>

<span data-ttu-id="826c0-142">O lançamento direcionado permite que os administradores, os gerentes de alteração ou qualquer pessoa responsável pelas atualizações da Microsoft 365 se preparam nas alterações futuras, permitindo que eles:</span><span class="sxs-lookup"><span data-stu-id="826c0-142">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="826c0-143">Testem e validem novas atualizações antes de elas serem lançadas para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="826c0-143">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="826c0-144">Preparem a notificação para os usuários e a documentação antes que as atualizações sejam lançadas para todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="826c0-144">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="826c0-145">Preparem uma central de ajuda interna para as alterações futuras.</span><span class="sxs-lookup"><span data-stu-id="826c0-145">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="826c0-146">Analisem as revisões de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="826c0-146">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="826c0-147">Usem controles de recursos, quando aplicável, para controlar o lançamento das atualizações para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="826c0-147">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="826c0-148">Configurar a opção de lançamento no centro de administração</span><span class="sxs-lookup"><span data-stu-id="826c0-148">Set up the release option in the admin center</span></span>

<span data-ttu-id="826c0-149">Você pode alterar como sua organização recebe as atualizações da Microsoft 365 seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="826c0-149">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="826c0-150">Você precisa ser um administrador global no Microsoft 365 para aceitar o.</span><span class="sxs-lookup"><span data-stu-id="826c0-150">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="826c0-151">Pode levar até 24 horas para que as alterações abaixo tenham efeito no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="826c0-151">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="826c0-152">Se você optar por cancelar o lançamento direcionado depois de ativá-lo, os usuários poderão perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="826c0-152">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="826c0-153">No centro de administração, vá para a **Settings**  >  **configuração org**Settings e, na guia **perfil da organização** , escolha **preferências de versão**.</span><span class="sxs-lookup"><span data-stu-id="826c0-153">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="826c0-154">Para desabilitar o lançamento direcionado, selecione **versão padrão**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="826c0-154">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="826c0-155">Para habilitar o lançamento direcionado para todos os usuários em sua organização, selecione **lançamento direcionado para todos**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="826c0-155">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="826c0-156">Para habilitar o lançamento direcionado para algumas pessoas em sua organização, selecione **lançamento direcionado para usuários selecionados**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="826c0-156">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="826c0-157">Escolha **Selecionar usuários** para adicionar usuários, um de cada vez, ou **carregar usuários** para adicioná-los em massa.</span><span class="sxs-lookup"><span data-stu-id="826c0-157">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="826c0-158">Quando terminar de adicionar usuários, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="826c0-158">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="826c0-159">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="826c0-159">Learn more</span></span>

<span data-ttu-id="826c0-160">Descubra como [gerenciar mensagens](https://docs.microsoft.com/office365/admin/manage/message-center) no seu [centro de mensagens do Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obter notificações sobre futuras atualizações e versões do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="826c0-160">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
