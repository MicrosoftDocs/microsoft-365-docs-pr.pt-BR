---
title: Configuração do locatário do Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Neste artigo, aprenda como adicionar localização por satélite e configurar seu locatário para o Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923643"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="1d78d-103">Configuração do locatário do Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="1d78d-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="1d78d-104">Antes de configurar seu locatário do Microsoft 365 Multi-Ge, certifique-se de que você leu o [Plano do Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="1d78d-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="1d78d-105">Para seguir as etapas neste artigo, você precisará de uma lista de localizações geográficas que você deseja habilitar como locais de satélite e os usuários de teste que você deseja provisionar para esses locais.</span><span class="sxs-lookup"><span data-stu-id="1d78d-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="1d78d-106">Adicionar o funcionalidades multigeográficas no Microsoft 365 ao seu locatário</span><span class="sxs-lookup"><span data-stu-id="1d78d-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="1d78d-107">Para usar o Microsoft 365 Multi-Geo, você precisa dos _Recursos Multi-Geo no plano do Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="1d78d-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="1d78d-108">Trabalhar com sua equipe de conta para adicionar este plano para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1d78d-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="1d78d-109">Sua equipe de conectará você com o especialista de licenciamento apropriado e fará a configuração do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1d78d-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="1d78d-p103">Observe que o plano de _Funcionalidades Multigeográficas no Microsoft 365_ são um plano de serviços de nível de usuário. Você precisa de uma licença para cada usuário que quiser hospedar em um local de satélite. Você pode adicionar mais licenças ao longo do tempo ao adicionar usuários nos locais de satélite.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p103">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan. You need a license for each user that you want to host in a satellite location. You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="1d78d-113">Depois que seu locatário for provisionado com os _Recursos de várias regiões no plano do Microsoft 365_, a guia **Locais geográficos** ficará disponível nos centros de administração do OneDrive e do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1d78d-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="1d78d-114">Adicionar locais de satélites ao seu locatário</span><span class="sxs-lookup"><span data-stu-id="1d78d-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="1d78d-115">Você deve adicionar um local de satélite para cada localização geográfica onde você deseja armazenar dados.</span><span class="sxs-lookup"><span data-stu-id="1d78d-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="1d78d-116">As localizações geográficas disponíveis são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="1d78d-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Captura de tela da página de localizações geográficas do centro de administração do SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="1d78d-118">Para adicionar um local de satélite</span><span class="sxs-lookup"><span data-stu-id="1d78d-118">To add a satellite location</span></span>

1. <span data-ttu-id="1d78d-119">Abra o Centro de Administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1d78d-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="1d78d-120">Navegue até a guia **Localizações geográficas**.</span><span class="sxs-lookup"><span data-stu-id="1d78d-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="1d78d-121">Clique em **Adicionar local**.</span><span class="sxs-lookup"><span data-stu-id="1d78d-121">Click **Add location**.</span></span>

4. <span data-ttu-id="1d78d-122">Selecione o local que você deseja adicionar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1d78d-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="1d78d-123">Digite o domínio que você deseja usar com a localização geográfica e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1d78d-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="1d78d-124">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1d78d-124">Click **Close**.</span></span>

<span data-ttu-id="1d78d-p105">O provisionamento pode levar desde algumas horas até 72 horas, dependendo do tamanho de seu locatário. Depois que o provisionamento de uma localização satélite for concluído, você receberá um email de confirmação. Quando o novo local geográfico for exibido em azul no mapa na guia **Localizações geográficas** no Centro de administração do OneDrive, você poderá definir o local preferencial de dados dos usuários como essa localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p105">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant. Once provisioning of a satellite location has completed, you will receive an email confirmation. When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1d78d-p106">A nova localização satélite será definida com configurações padrão. Isso permitirá configurar a localização satélite de acordo com suas necessidades locais de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p106">Your new satellite location will be set up with default settings. This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="1d78d-130">Defina o local de dados preferencial dos usuários</span><span class="sxs-lookup"><span data-stu-id="1d78d-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="1d78d-p107">Depois de habilitar as localizações satélites necessárias, você pode atualizar as contas de usuários para usar o local de dados de sua preferência. É recomendável definir um local preferencial de dados para todos os usuários, mesmo que o usuário permaneça no local de dados central.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p107">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location. We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d78d-133">Se o local de dados preferencial do usuário for definido em um local que não foi configurado como um local de satélite ou um local central, o sistema adotará como padrão o local central ao provisionar sites do OneDrive e do SharePoint e caixas de correio de Grupo.</span><span class="sxs-lookup"><span data-stu-id="1d78d-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="1d78d-134">É recomendável começar validações com um usuário de teste ou um pequeno grupo de usuários antes de implantar Funcionalidades Multigeográficas em sua organização de forma mais ampla.</span><span class="sxs-lookup"><span data-stu-id="1d78d-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="1d78d-135">Há dois tipos de objetos de usuário no Azure Active Directory: usuários somente nuvem e usuários sincronizados.</span><span class="sxs-lookup"><span data-stu-id="1d78d-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="1d78d-136">Siga as instruções apropriadas para o seu tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="1d78d-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="1d78d-137">Sincronizar o Local de Dados Preferencial do usuário usando o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="1d78d-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="1d78d-138">Se os usuários da sua empresa estiverem sincronizados a partir de um sistema local do Active Directory para o Azure AD, o PreferredDataLocation do usuário deve ser preenchido no AD e sincronizado com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1d78d-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="1d78d-139">Siga o processo na [Sincronização do Azure Active Directory Connect: configure o local preferencial de dados para os recursos do Microsoft 365](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) para configurar a sincronização do local preferencial de dados dos serviços de domínio do Active Directory (AD DS) local para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1d78d-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="1d78d-140">Recomendamos que você inclua o Local de Dados Preferencial do usuário na configuração como parte do fluxo de trabalho de criação de usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="1d78d-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d78d-141">Para novos usuários sem o OneDrive provisionado, aguarde pelo menos 24 horas após o PDL do usuário ser sincronizado com o Azure AD para que as alterações se propaguem antes de fazer logon no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="1d78d-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="1d78d-142">(Configurar o Local de Dados Preferencial antes do usuário fazer o logon para provisionar o OneDrive for Business garante que o novo OneDrive do usuário seja provisionado no local correto.)</span><span class="sxs-lookup"><span data-stu-id="1d78d-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="1d78d-143">Configurar Local de Dados Preferencial para usuários somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="1d78d-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="1d78d-144">Se os usuários da sua empresa não forem sincronizados de um sistema Active Directory local com o Azure AD, significando que eles são criados no Microsoft 365 ou no Azure AD, então a PDL deve ser definida usando o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d78d-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="1d78d-145">Os procedimentos nessa seção exigem o [Módulo Microsoft Azure Active Directory para Windows PowerShell](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span><span class="sxs-lookup"><span data-stu-id="1d78d-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="1d78d-146">Se você já tiver esse módulo, certifique-se de atualizar para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="1d78d-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="1d78d-147">[Conecte-se e entre](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) com um conjunto de credenciais de administrador global para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1d78d-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="1d78d-p111">Use o cmdlet [Set-MsolUser](/powershell/msonline/v1/set-msoluser) para definir o local preferencial de dados para cada um dos usuários. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1d78d-p111">Use the [Set-MsolUser](/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users. For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="1d78d-p112">Você pode confirmar se o local preferencial de dados foi atualizado corretamente usando o cmdlet Get-MsolUser. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1d78d-p112">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet. For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Captura de tela de uma janela do PowerShell mostrando o conjunto-msoluser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="1d78d-153">Recomendamos que você inclua o Local de Dados Preferencial do usuário na configuração como parte do fluxo de trabalho de criação de usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="1d78d-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d78d-154">Para novos usuários sem o OneDrive provisionado, aguarde pelo menos de 24 horas após o PDL ser feito para que as alterações se propaguem antes de fazer logon no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1d78d-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="1d78d-155">(Configurar o Local de Dados Preferencial antes do usuário fazer o logon para provisionar o OneDrive for Business garante que o novo OneDrive do usuário seja provisionado no local correto.)</span><span class="sxs-lookup"><span data-stu-id="1d78d-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="1d78d-156">Provisionamento do OneNote e efeito de PDL</span><span class="sxs-lookup"><span data-stu-id="1d78d-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="1d78d-157">Se o usuário já tiver um site do OneDrive criado no locatário, configurar o PDL não moverá automaticamente o OneDrive existente.</span><span class="sxs-lookup"><span data-stu-id="1d78d-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="1d78d-158">Para mover a OneDrive de um usuário, [consulte OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span><span class="sxs-lookup"><span data-stu-id="1d78d-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1d78d-159">Exchange Online realoca automaticamente a caixa de correio do usuário se o PLD mudar e MailboxRegion não mais corresponde ao código de Localização Geográfica do Banco de Dados de Caixa de Correio.</span><span class="sxs-lookup"><span data-stu-id="1d78d-159">Exchange Online automatically relocates the user's mailbox if the PLD changes and the MailboxRegion no longer matches the Mailbox Database Geo Location code.</span></span> <span data-ttu-id="1d78d-160">Para obter mais informações, consulte [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="1d78d-160">For more information, see [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span></span>

<span data-ttu-id="1d78d-161">Se o usuário não tiver um site do OneDrive no locatário, o OneDrive será provisionado para ele de acordo com o valor do PDL, supondo que o PDL do usuário corresponda a um dos locais de satélites da empresa.</span><span class="sxs-lookup"><span data-stu-id="1d78d-161">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="1d78d-162">Configurar pesquisa multigeográfica</span><span class="sxs-lookup"><span data-stu-id="1d78d-162">Configuring Multi-Geo search</span></span>

<span data-ttu-id="1d78d-163">O locatário com Funcionalidades Multigeográficas terá recursos de pesquisa agregados, permitindo que uma consulta de pesquisa retorne resultados de praticamente qualquer lugar no locatário.</span><span class="sxs-lookup"><span data-stu-id="1d78d-163">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="1d78d-164">Por padrão, pesquisas desses pontos de entrada retornam resultados agregados, mesmo que cada índice de pesquisa esteja em sua localização geográfica relevante:</span><span class="sxs-lookup"><span data-stu-id="1d78d-164">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="1d78d-165">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1d78d-165">OneDrive for Business</span></span>

- <span data-ttu-id="1d78d-166">Delve</span><span class="sxs-lookup"><span data-stu-id="1d78d-166">Delve</span></span>

- <span data-ttu-id="1d78d-167">Página inicial do SharePoint</span><span class="sxs-lookup"><span data-stu-id="1d78d-167">SharePoint Home</span></span>

- <span data-ttu-id="1d78d-168">Centro de Pesquisa</span><span class="sxs-lookup"><span data-stu-id="1d78d-168">Search Center</span></span>

<span data-ttu-id="1d78d-169">Além disso, recursos de pesquisa multigeográfica podem ser configurados para os aplicativos de pesquisa personalizados que usam a API de pesquisa do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1d78d-169">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="1d78d-170">Examine [Configurar a pesquisa para o OneDrive for Business com a funcionalidade multigeográfica](configure-search-for-multi-geo.md) para obter instruções, incluindo limitações e diferenças.</span><span class="sxs-lookup"><span data-stu-id="1d78d-170">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="1d78d-171">Validar a configuração do Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="1d78d-171">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="1d78d-172">Abaixo estão alguns casos de uso básicos que você pode incluir no seu plano de validação antes de lançar amplamente o Microsoft 365 Multi-Geo na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="1d78d-172">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="1d78d-173">Depois de concluir esses testes e os casos de uso mais relevantes para sua empresa, você pode optar por prosseguir e adicionar os usuários em seu grupo piloto inicial.</span><span class="sxs-lookup"><span data-stu-id="1d78d-173">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="1d78d-174">**OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="1d78d-174">**OneDrive for Business**</span></span>

<span data-ttu-id="1d78d-175">Selecione o OneDrive no iniciador de aplicativos do Microsoft 365 e confirme se você é direcionado automaticamente para o local geográfico apropriado para o usuário, com base na PDL do usuário.</span><span class="sxs-lookup"><span data-stu-id="1d78d-175">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="1d78d-176">OneDrive for Business agora vai começar a provisionar nesse local.</span><span class="sxs-lookup"><span data-stu-id="1d78d-176">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="1d78d-177">Uma vez provisionado, tente carregar e baixar alguns documentos.</span><span class="sxs-lookup"><span data-stu-id="1d78d-177">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="1d78d-178">**Aplicativo móvel do OneDrive**</span><span class="sxs-lookup"><span data-stu-id="1d78d-178">**OneDrive Mobile App**</span></span>

<span data-ttu-id="1d78d-179">Faça logon no aplicativo móvel do OneDrive com as credenciais da sua conta de teste.</span><span class="sxs-lookup"><span data-stu-id="1d78d-179">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="1d78d-180">Confirme se você pode ver os arquivos do OneDrive for Business e se pode interagir com eles no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="1d78d-180">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="1d78d-181">**Cliente de sincronização do OneDrive**</span><span class="sxs-lookup"><span data-stu-id="1d78d-181">**OneDrive sync client**</span></span>

<span data-ttu-id="1d78d-p119">Confirme que o cliente de sincronização do OneDrive detecta automaticamente a localização geográfica do OneDrive for Business após o logon. Se você precisar baixar o cliente de sincronização, clique em **Sincronização** na biblioteca do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p119">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login. If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="1d78d-184">**Aplicativos do Office**</span><span class="sxs-lookup"><span data-stu-id="1d78d-184">**Office applications**</span></span>

<span data-ttu-id="1d78d-p120">Confirme que você pode acessar o OneDrive for Business fazendo logon de um aplicativo do Office, como o Word. Abra o aplicativo do Office e selecione "OneDrive – <TenantName>". O Office detectará o local do OneDrive e mostrará os arquivos que você pode abrir.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p120">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word. Open the Office application and select "OneDrive – <TenantName>". Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="1d78d-188">**Compartilhamento**</span><span class="sxs-lookup"><span data-stu-id="1d78d-188">**Sharing**</span></span>

<span data-ttu-id="1d78d-p121">Tente compartilhar arquivos do OneDrive. Confirme se o seletor de pessoas mostra todos os usuários online do SharePoint, independentemente da localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="1d78d-p121">Try sharing OneDrive files. Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>