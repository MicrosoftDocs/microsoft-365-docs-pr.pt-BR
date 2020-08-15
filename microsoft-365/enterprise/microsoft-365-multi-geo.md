---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Neste artigo, saiba como expandir sua presença do Microsoft 365 para várias regiões geográficas com o Microsoft 365 multigeográfico.
ms.openlocfilehash: a5843b98b5d64dfb3872c3d8a5d48c0e56949c02
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687346"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="acc3c-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="acc3c-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="acc3c-104">Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.</span><span class="sxs-lookup"><span data-stu-id="acc3c-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="acc3c-105">Entre em contato com sua equipe de contas da Microsoft para inscrever sua empresa multinacional no Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="acc3c-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="acc3c-106">Com o Microsoft 365 Multi-Geo, você pode provisionar e armazenar dados em repouso nos locais geográficos escolhidos para atender aos requisitos de residência de dados e, ao mesmo tempo, desbloquear sua distribuição global de experiências modernas de produtividade à sua força de trabalho.</span><span class="sxs-lookup"><span data-stu-id="acc3c-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

#### <a name="video-introducing-microsoft-365-multi-geo"></a><span data-ttu-id="acc3c-107">Vídeo: apresentando o Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="acc3c-107">Video: Introducing Microsoft 365 Multi-Geo</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1Yk6B?autoplay=false]

<span data-ttu-id="acc3c-108">Em um ambiente de várias regiões, o locatário do Microsoft 365 consiste de um local central (onde sua assinatura do Microsoft 365 foi originalmente provisionada) e um ou mais locais de satélite.</span><span class="sxs-lookup"><span data-stu-id="acc3c-108">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="acc3c-109">Em um locatário multigeográfico, as informações sobre localizações geográficas, grupos e informações do usuário são dominadas no Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="acc3c-109">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="acc3c-110">Como as informações de locatário são dominadas centralmente e sincronizadas em cada localização geográfica, compartilhamento e experiências envolvendo qualquer pessoa da sua empresa contêm percepção global.</span><span class="sxs-lookup"><span data-stu-id="acc3c-110">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Captura de tela do menu do centro de administração do SharePoint](../media/multi-geo-world-map.png)

<span data-ttu-id="acc3c-112">Observe que o Microsoft 365 Multi-Geo não foi projetado para otimização de desempenho, ele foi projetado para atender aos requisitos da residência de dados.</span><span class="sxs-lookup"><span data-stu-id="acc3c-112">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="acc3c-113">Para obter mais informações sobre otimização de desempenho do Microsoft 365, consulte [Planejamento de rede e ajuste de desempenho do Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) ou entre em contato com seu grupo de suporte.</span><span class="sxs-lookup"><span data-stu-id="acc3c-113">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="acc3c-114">Terminologia</span><span class="sxs-lookup"><span data-stu-id="acc3c-114">Terminology</span></span>

<span data-ttu-id="acc3c-115">Aqui estão os principais termos usados na descrição do Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="acc3c-115">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="acc3c-116">**Uma localização central** -a localização geográfica onde seu locatário foi originalmente provisionado.</span><span class="sxs-lookup"><span data-stu-id="acc3c-116">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="acc3c-117">**Administrador geográfico**, um administrador que pode administrar um ou mais locais do satélite especificado.</span><span class="sxs-lookup"><span data-stu-id="acc3c-117">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="acc3c-118">**Geocódigo** -um código de três letras de uma localização geográfica determinada.</span><span class="sxs-lookup"><span data-stu-id="acc3c-118">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="acc3c-119">**Localização geográfica** – uma localização geográfica pode ser usada em um locatário multigeográfico para hospedar dados, incluindo caixas de correio do Exchange e o OneDrive e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="acc3c-119">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="acc3c-120">**Preferenciais de dados local (PDL)** a propriedade do usuário definido pelo administrador que indica onde a localização geográfica onde a caixa de correio do Exchange usuários e do OneDrive devem ser provisionadas.</span><span class="sxs-lookup"><span data-stu-id="acc3c-120">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="acc3c-121">A PDL determina também onde os sites do SharePoint criados pelo usuário estão provisionados.</span><span class="sxs-lookup"><span data-stu-id="acc3c-121">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="acc3c-122">**Localização do satélite** – As localizações geográficas onde as cargas de trabalho do Microsoft 365 com reconhecimento geográfico (SharePoint, OneDrive e Exchange) são ativadas em um inquilino com várias geografias.</span><span class="sxs-lookup"><span data-stu-id="acc3c-122">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="acc3c-123">**Locatário** – A representação de uma organização no Microsoft 365 que normalmente possui um ou mais domínios associados a ela (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="acc3c-123">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="acc3c-124">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="acc3c-124">Licensing</span></span>

<span data-ttu-id="acc3c-125">O Microsoft 365 Multi-Geo está disponível como um complemento para os seguintes planos de assinatura do Microsoft 365 para os clientes da EA, com um mínimo de 250 assinaturas do Microsoft 365 em seus locatários e um mínimo de 5% desses usuários usando várias regiões.</span><span class="sxs-lookup"><span data-stu-id="acc3c-125">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="acc3c-126">Entre em contato com a equipe de conta Microsoft para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="acc3c-126">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="acc3c-127">Microsoft 365 F1, E1, E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="acc3c-127">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="acc3c-128">Exchange Online Plano 1 ou Plano 2</span><span class="sxs-lookup"><span data-stu-id="acc3c-128">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="acc3c-129">OneDrive for Business Plano 1 ou Plano 2</span><span class="sxs-lookup"><span data-stu-id="acc3c-129">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="acc3c-130">SharePoint Online Plano 1 ou Plano 2</span><span class="sxs-lookup"><span data-stu-id="acc3c-130">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="acc3c-131">Disponibilidade do Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="acc3c-131">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="acc3c-132">Atualmente, o Microsoft 365 Multi-Geo é oferecido nessas regiões e países:</span><span class="sxs-lookup"><span data-stu-id="acc3c-132">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="acc3c-133">Introdução</span><span class="sxs-lookup"><span data-stu-id="acc3c-133">Getting started</span></span>

<span data-ttu-id="acc3c-134">Siga estas etapas para iniciar com o multigeográfico:</span><span class="sxs-lookup"><span data-stu-id="acc3c-134">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="acc3c-135">Trabalhe com sua equipe de conta para adicionar os _Recursos de várias áreas geográficas no plano de serviço do Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="acc3c-135">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="acc3c-136">Elas orientarão você ra adicionar o número de licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="acc3c-136">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="acc3c-137">O recurso de várias áreas geográficas está disponível para clientes da EA com no mínimo 250 assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="acc3c-137">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="acc3c-138">Antes de começar a usar o Microsoft 365 Multi-Geo, a Microsoft precisa configurar seu locatário do Exchange Online do suporte multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="acc3c-138">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="acc3c-139">Esse processo de configuração única é acionado após o pedido do *Plano de serviços do Recursos Geográficos no Microsoft 365*, sendo que as licenças são exibidas no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="acc3c-139">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="acc3c-140">Você receberá notificações no [Centro de mensagens do Microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) assim que suas licenças do Multi-Geo forem aplicadas e, em seguida, você poderá começar a configurar e usar seus recursos do Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="acc3c-140">You'll receive notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="acc3c-141">Leia [planejar o ambiente multigeográfico](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="acc3c-141">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="acc3c-142">Saiba mais sobre [administrar um ambiente multigeográfico](administering-a-multi-geo-environment.md) e [como seus usuários terão o ambiente](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="acc3c-142">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="acc3c-143">Quando você estiver pronto para configurar o Microsoft 365 Multi-Geo, [configure seu locatário para multigeográfico](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="acc3c-143">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="acc3c-144">[Configurar pesquisa](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="acc3c-144">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="acc3c-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="acc3c-145">See also</span></span>

[<span data-ttu-id="acc3c-146">Multigeográfico no Exchange Online e no OneDrive</span><span class="sxs-lookup"><span data-stu-id="acc3c-146">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="acc3c-147">Recursos multigeográficos no OneDrive e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="acc3c-147">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="acc3c-148">Recursos multigeográficos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="acc3c-148">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="acc3c-149">Experiência da equipe em um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="acc3c-149">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
