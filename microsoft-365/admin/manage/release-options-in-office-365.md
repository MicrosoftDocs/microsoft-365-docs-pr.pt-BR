---
title: Configurar as opções de versão Padrão ou Direcionada
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
description: Saiba como configurar a opção de versão para novas atualizações de produtos e recursos no Centro de administração do Microsoft 365.
ms.openlocfilehash: d3692f2e1cca58fec81f2ad492b9232d5576f99b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579249"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="4cf10-103">Configurar as opções de versão Padrão ou Direcionada</span><span class="sxs-lookup"><span data-stu-id="4cf10-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cf10-104">As atualizações do Microsoft 365 descritas neste artigo se aplicam ao Microsoft 365, SharePoint Online e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4cf10-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="4cf10-105">Essas opções de versão são direcionadas, melhores maneiras de lançar alterações no Microsoft 365, mas não podem ser garantidas em todos os momentos ou para todas as atualizações.</span><span class="sxs-lookup"><span data-stu-id="4cf10-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="4cf10-106">Eles não se aplicam ao Microsoft 365 Apps, Skype for Business, Microsoft Teams e serviços relacionados.</span><span class="sxs-lookup"><span data-stu-id="4cf10-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="4cf10-107">Para obter informações sobre opções de versão para Aplicativos do Microsoft 365, consulte [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="4cf10-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="4cf10-108">Com o Microsoft 365, você recebe novas atualizações de produtos e recursos à medida que elas se tornam disponíveis em vez de fazer atualizações de custo a cada poucos anos.</span><span class="sxs-lookup"><span data-stu-id="4cf10-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="4cf10-109">Você pode gerenciar como sua organização recebe essas atualizações.</span><span class="sxs-lookup"><span data-stu-id="4cf10-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="4cf10-110">Por exemplo, você pode se inscrever para uma versão antecipada para que sua organização receba atualizações primeiro.</span><span class="sxs-lookup"><span data-stu-id="4cf10-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="4cf10-111">Você pode designar que apenas determinados indivíduos recebam as atualizações.</span><span class="sxs-lookup"><span data-stu-id="4cf10-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="4cf10-112">Ou, você pode permanecer no cronograma de lançamento padrão e receber as atualizações posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4cf10-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="4cf10-113">Este artigo explica as diferentes opções de versão e como você pode usá-las para sua organização.</span><span class="sxs-lookup"><span data-stu-id="4cf10-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="4cf10-114">Como funciona - validação de versão</span><span class="sxs-lookup"><span data-stu-id="4cf10-114">How it works - release validation</span></span>

<span data-ttu-id="4cf10-115">Qualquer nova versão é primeiro testada e validada pela equipe de recursos e, em seguida, por toda a equipe de recursos do Microsoft 365, seguida por toda a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4cf10-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="4cf10-116">Depois de testes internos e validação, a próxima etapa é um **lançamento direcionado** (conhecido anteriormente como Primeiro Lançamento) para clientes que aceitarem.</span><span class="sxs-lookup"><span data-stu-id="4cf10-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="4cf10-117">Em cada anel de lançamento, a Microsoft coleta comentários e valida mais a qualidade ao monitorar métricas de utilização importantes.</span><span class="sxs-lookup"><span data-stu-id="4cf10-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="4cf10-118">Esta série de processos progressivos de validação serve para garantir que a versão mundial seja o mais robusta possível.</span><span class="sxs-lookup"><span data-stu-id="4cf10-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="4cf10-119">As versões são ilustradas na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="4cf10-119">The releases are pictured in the following figure.</span></span> 
  
![Anéis de validação de versão do Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="4cf10-121">Para atualizações significativas, os clientes são notificados inicialmente pelo Roteiro do [Microsoft 365](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="4cf10-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="4cf10-122">À medida que uma atualização fica mais próxima de ser implantada, ela é comunicada por meio do centro de mensagens do [Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="4cf10-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="4cf10-123">Você precisa de uma conta do Microsoft 365 ou do Azure AD para acessar seu Centro de Mensagens por meio do [centro de administração.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="4cf10-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="4cf10-124">Os usuários do plano 1 do Microsoft 365 não têm um centro de administração.</span><span class="sxs-lookup"><span data-stu-id="4cf10-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="4cf10-125">Lançamento padrão</span><span class="sxs-lookup"><span data-stu-id="4cf10-125">Standard release</span></span>

<span data-ttu-id="4cf10-126">Essa é a opção padrão em que você e seus usuários recebem as atualizações mais recentes quando são lançadas amplamente para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="4cf10-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="4cf10-127">Uma boa prática é deixar a  maioria dos usuários em Versão padrão e profissionais de IT e usuários de energia em **Versão** direcionada para avaliar novos recursos e preparar equipes para dar suporte a usuários e executivos de negócios.</span><span class="sxs-lookup"><span data-stu-id="4cf10-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4cf10-128">Caso mude do lançamento direcionado para o padrão, seus usuários podem perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="4cf10-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="4cf10-129">Lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="4cf10-129">Targeted release</span></span>

<span data-ttu-id="4cf10-p106">Com esta opção, você e seus usuários podem ser os primeiros a conferir as atualizações mais recentes e ajudar no ajuste do produto, fornecendo comentários antecipadamente. Você pode optar que algumas pessoas ou que toda a organização receba as atualizações antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="4cf10-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4cf10-p107">As atualizações grandes ou complexas podem demorar mais do que as outras, portanto, nenhum usuário é afetado negativamente. Não há garantia quanto à linha do tempo exata de uma versão.</span><span class="sxs-lookup"><span data-stu-id="4cf10-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="4cf10-134">Lançamento direcionado para toda a organização</span><span class="sxs-lookup"><span data-stu-id="4cf10-134">Targeted release for entire organization</span></span>

<span data-ttu-id="4cf10-135">Se você [configurar a opção de versão no](#set-up-the-release-option-in-the-admin-center) centro de administração para essa opção, todos os usuários obterão a experiência de versão direcionada.</span><span class="sxs-lookup"><span data-stu-id="4cf10-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="4cf10-136">Para organizações com mais de 300 usuários, recomendamos usar uma assinatura de teste para essa opção.</span><span class="sxs-lookup"><span data-stu-id="4cf10-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="4cf10-137">Para obter informações sobre a assinatura de teste, fale com seu contato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4cf10-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="4cf10-138">Lançamento direcionado para usuários selecionados</span><span class="sxs-lookup"><span data-stu-id="4cf10-138">Targeted release for selected users</span></span>

<span data-ttu-id="4cf10-139">Se você [configurar a opção de](#set-up-the-release-option-in-the-admin-center) versão no centro de administração para essa opção, poderá definir usuários específicos, geralmente usuários de energia, para receber acesso antecipado aos recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="4cf10-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="4cf10-140">Benefícios do lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="4cf10-140">Benefits of Targeted release</span></span>

<span data-ttu-id="4cf10-141">A versão direcionada permite que os administradores, gerentes de alterações ou qualquer outra pessoa responsável pelas atualizações do Microsoft 365 se preparem para as próximas alterações, permitindo que eles:</span><span class="sxs-lookup"><span data-stu-id="4cf10-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="4cf10-142">Testem e validem novas atualizações antes de elas serem lançadas para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="4cf10-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="4cf10-143">Preparem a notificação para os usuários e a documentação antes que as atualizações sejam lançadas para todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="4cf10-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="4cf10-144">Preparem uma central de ajuda interna para as alterações futuras.</span><span class="sxs-lookup"><span data-stu-id="4cf10-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="4cf10-145">Analisem as revisões de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="4cf10-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="4cf10-146">Usem controles de recursos, quando aplicável, para controlar o lançamento das atualizações para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="4cf10-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="4cf10-147">Configurar a opção de versão no centro de administração</span><span class="sxs-lookup"><span data-stu-id="4cf10-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="4cf10-148">Você pode alterar como sua organização recebe atualizações do Microsoft 365 seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4cf10-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="4cf10-149">Você precisa ser um administrador global no Microsoft 365 para entrar.</span><span class="sxs-lookup"><span data-stu-id="4cf10-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4cf10-150">Pode levar até 24 horas para que as alterações abaixo entre em vigor no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf10-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="4cf10-151">Se você optar por cancelar o lançamento direcionado depois de ativá-lo, os usuários poderão perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="4cf10-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="4cf10-152">No centro de administração, vá para a **Configuração** da Organização de Configurações e, na guia Perfil da  >  Organização, escolha **Preferências de versão.** </span><span class="sxs-lookup"><span data-stu-id="4cf10-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="4cf10-153">Para desabilitar a versão direcionada, selecione **Versão padrão** e, em seguida, selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="4cf10-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="4cf10-154">Para habilitar a versão direcionada para todos os usuários em sua organização, selecione **Liberar direcionado para todos** e, em seguida, selecione Salvar **alterações**.</span><span class="sxs-lookup"><span data-stu-id="4cf10-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="4cf10-155">Para habilitar a versão direcionada para algumas pessoas em sua organização, selecione **Lançamento** direcionado para usuários selecionados e, em seguida, **selecione Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="4cf10-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="4cf10-156">Escolha **Selecionar usuários** para adicionar usuários um de cada vez ou Carregar **usuários** para adicioná-los em massa.</span><span class="sxs-lookup"><span data-stu-id="4cf10-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="4cf10-157">Quando terminar de adicionar usuários, selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="4cf10-157">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="4cf10-158">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="4cf10-158">Learn more</span></span>

<span data-ttu-id="4cf10-159">Descubra como gerenciar [mensagens no](/office365/admin/manage/message-center) centro de mensagens do [Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para receber notificações sobre as próximas atualizações e versões do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf10-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4cf10-160">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="4cf10-160">Related Articles</span></span>

[<span data-ttu-id="4cf10-161">Office Insider</span><span class="sxs-lookup"><span data-stu-id="4cf10-161">Office Insider</span></span>](https://insider.office.com/join/windows)
