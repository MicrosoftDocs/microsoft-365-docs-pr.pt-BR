---
title: Configurar as opções dos programas Padrão ou Direcionado no Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Saiba como configurar a opção de lançamento para novas atualizações de produtos e recursos no centro de administração do Microsoft 365.
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250591"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="b4b46-103">Configurar as opções dos programas Padrão ou Direcionado no Office 365</span><span class="sxs-lookup"><span data-stu-id="b4b46-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="b4b46-p101">Com o Office 365, você recebe novas atualizações de produtos e recursos assim que eles estiverem disponíveis, em vez de fazer atualizações dispendiosas quase todos os anos. Você pode gerenciar a forma como a sua organização recebe as atualizações. Por exemplo, é possível se inscrever em uma versão antecipada para que a sua organização receba as atualizações primeiro. É possível designar que somente determinadas pessoas recebam as atualizações, ou permanecer no cronograma de versão padrão e receber as atualizações posteriormente. Este artigo explica as várias opções de versão e informa sobre como usá-las na sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b4b46-p102">As atualizações do Office 365 descritas neste artigo se aplicam ao Office 365, ao SharePoint Online e ao Exchange Online. Elas não se aplicam ao Skype for Business e aos serviços relacionados. As opções de versão são maneiras objetivas e direcionadas de lançar as alterações do Office 365, mas nem sempre são garantidas ou nem sempre se destinam a todas as atualizações.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="b4b46-113">Como funciona - validação de versão</span><span class="sxs-lookup"><span data-stu-id="b4b46-113">How it works - release validation</span></span>

<span data-ttu-id="b4b46-114">Qualquer nova versão é testada e validada pela equipe de recursos e, em seguida, por toda a equipe de recursos do Office 365, seguida por toda a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4b46-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="b4b46-115">Depois de testes internos e validação, a próxima etapa é um **lançamento direcionado** (conhecido anteriormente como Primeiro Lançamento) para clientes que aceitarem.</span><span class="sxs-lookup"><span data-stu-id="b4b46-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="b4b46-116">Em cada anel de lançamento, a Microsoft coleta comentários e valida mais a qualidade ao monitorar métricas de utilização importantes.</span><span class="sxs-lookup"><span data-stu-id="b4b46-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="b4b46-117">Esta série de processos progressivos de validação serve para garantir que a versão mundial seja o mais robusta possível.</span><span class="sxs-lookup"><span data-stu-id="b4b46-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="b4b46-118">As versões são ilustradas na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="b4b46-118">The releases are pictured in the following figure.</span></span> 
  
![Liberar toques de validação para o Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="b4b46-120">Para atualizações significativas, os clientes do Office são inicialmente notificados pelo [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="b4b46-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="b4b46-121">Como uma atualização está mais próxima de ser implantada, ela é comunicada através do [centro de mensagens do Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="b4b46-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="b4b46-122">Você precisa de uma conta do Office 365 ou do Azure AD para acessar seu centro de mensagens por meio do [centro de administração](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b4b46-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="b4b46-123">O Office 365 Home Plan Users não têm um centro de administração.</span><span class="sxs-lookup"><span data-stu-id="b4b46-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="b4b46-124">Lançamento padrão</span><span class="sxs-lookup"><span data-stu-id="b4b46-124">Standard release</span></span>

<span data-ttu-id="b4b46-125">Esta é a opção padrão em que você e seus usuários recebem as atualizações mais recentes quando são lançadas amplamente para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="b4b46-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="b4b46-126">Uma boa prática é deixar a maioria dos usuários em **lançamentos padrão** e profissionais de ti e usuários avançados no **lançamento direcionado** para avaliar novos recursos e preparar o Microsoft Teams para dar suporte a usuários e executivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="b4b46-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b4b46-127">Caso mude do lançamento direcionado para o padrão, seus usuários podem perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="b4b46-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="b4b46-128">Lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="b4b46-128">Targeted release</span></span>

<span data-ttu-id="b4b46-p106">Com esta opção, você e seus usuários podem ser os primeiros a conferir as atualizações mais recentes e ajudar no ajuste do produto, fornecendo comentários antecipadamente. Você pode optar que algumas pessoas ou que toda a organização receba as atualizações antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b4b46-p107">As atualizações grandes ou complexas podem demorar mais do que as outras, portanto, nenhum usuário é afetado negativamente. Não há garantia quanto à linha do tempo exata de uma versão.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="b4b46-133">Lançamento direcionado para toda a organização</span><span class="sxs-lookup"><span data-stu-id="b4b46-133">Targeted release for entire organization</span></span>

<span data-ttu-id="b4b46-134">Se você [Configurar a opção de lançamento no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, todos os usuários receberão a experiência de lançamento direcionada.</span><span class="sxs-lookup"><span data-stu-id="b4b46-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="b4b46-135">Para organizações com mais de 300 usuários, recomendamos usar uma assinatura de teste para essa opção.</span><span class="sxs-lookup"><span data-stu-id="b4b46-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="b4b46-136">Para obter informações sobre a assinatura de teste, fale com seu contato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4b46-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="b4b46-137">Lançamento direcionado para usuários selecionados</span><span class="sxs-lookup"><span data-stu-id="b4b46-137">Targeted release for selected users</span></span>

<span data-ttu-id="b4b46-138">Se você [Configurar a opção liberar no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, é possível definir usuários específicos, geralmente usuários avançados, para receber acesso antecipado aos recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="b4b46-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="b4b46-139">Benefícios do lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="b4b46-139">Benefits of Targeted release</span></span>

<span data-ttu-id="b4b46-140">O lançamento direcionado permite que os administradores, os gerentes de alterações ou qualquer outra pessoa responsável pelas atualizações do Office 365 se preparem para alterações futuras, permitindo que eles:</span><span class="sxs-lookup"><span data-stu-id="b4b46-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="b4b46-141">Testem e validem novas atualizações antes de elas serem lançadas para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="b4b46-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="b4b46-142">Preparem a notificação para os usuários e a documentação antes que as atualizações sejam lançadas para todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="b4b46-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="b4b46-143">Preparem uma central de ajuda interna para as alterações futuras.</span><span class="sxs-lookup"><span data-stu-id="b4b46-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="b4b46-144">Analisem as revisões de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="b4b46-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="b4b46-145">Usem controles de recursos, quando aplicável, para controlar o lançamento das atualizações para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="b4b46-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="b4b46-146">Configurar a opção de lançamento no centro de administração</span><span class="sxs-lookup"><span data-stu-id="b4b46-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="b4b46-p109">Você pode alterar a forma como a sua organização recebe as atualizações do Office 365 seguindo estas etapas: Você precisa ser um administrador global no Office 365 para participar.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b4b46-p110">Pode levar até 24 horas para que as seguintes alterações entrem em vigor no Office 365. Se você optar por cancelar o lançamento direcionado depois de ativá-lo, os usuários poderão perder o acesso aos recursos que ainda não chegaram ao lançamento padrão.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="b4b46-151">No centro de administração, vá para a \*\*\*\* > **configuração**configurações e, na guia **perfil da organização** , escolha **preferências de versão**.</span><span class="sxs-lookup"><span data-stu-id="b4b46-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="b4b46-152">Para desabilitar o lançamento direcionado, selecione **versão padrão**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b4b46-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="b4b46-153">Para habilitar o lançamento direcionado para todos os usuários em sua organização, selecione **lançamento direcionado para todos**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b4b46-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="b4b46-154">Para habilitar o lançamento direcionado para algumas pessoas em sua organização, selecione **lançamento direcionado para usuários selecionados**e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b4b46-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="b4b46-155">Escolha **Selecionar usuários** para adicionar usuários, um de cada vez, ou **carregar usuários** para adicioná-los em massa.</span><span class="sxs-lookup"><span data-stu-id="b4b46-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="b4b46-156">Quando terminar de adicionar usuários, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b4b46-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="b4b46-157">Obter a versão de lançamento direcionado do Office</span><span class="sxs-lookup"><span data-stu-id="b4b46-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="b4b46-p111">Para instalar um build de lançamento direcionado do Office, [siga estas etapas](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Isso lhe dará acesso antecipado aos novos recursos do Office 2016 para área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="b4b46-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="b4b46-160">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="b4b46-160">Learn more</span></span>

<span data-ttu-id="b4b46-161">Descubra como [gerenciar mensagens](https://docs.microsoft.com/office365/admin/manage/message-center) no centro de [mensagens do Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obter notificações sobre futuras atualizações e versões do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4b46-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
