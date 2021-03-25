---
title: Ativar o Microsoft 365 Defender no centro de segurança do Microsoft 365
description: Saiba como habilitar o Microsoft 365 Defender e começar a integrar seu incidente e resposta de segurança.
keywords: get started, enable MTP, Microsoft Threat Protection, M365, security, data location, required permissions, license eleibility, settings page
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 399da6fd54145f73ac72fdac04e8d25148f76507
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186744"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="d84fe-104">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d84fe-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d84fe-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d84fe-105">**Applies to:**</span></span>
- <span data-ttu-id="d84fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d84fe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d84fe-107">[O Microsoft 365 Defender](microsoft-365-defender.md) unifica seu processo de resposta a incidentes integrando os principais recursos do Microsoft Defender para Endpoint, do Microsoft Defender para Office 365, do Microsoft Cloud App Security e do Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="d84fe-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="d84fe-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d84fe-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="d84fe-109">O Microsoft 365 Defender é ativado automaticamente quando clientes qualificados com as permissões necessárias visitam o Centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d84fe-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="d84fe-110">Leia este artigo para entender vários pré-requisitos e como o Microsoft 365 Defender é provisionado.</span><span class="sxs-lookup"><span data-stu-id="d84fe-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="d84fe-111">Verificar a qualificação da licença e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="d84fe-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="d84fe-112">Uma licença para um produto de segurança do Microsoft 365 geralmente lhe dá o direito de usar o Microsoft 365 Defender no Centro de segurança do Microsoft 365 sem custo adicional de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="d84fe-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="d84fe-113">Recomendamos obter uma licença de segurança do Microsoft 365 E5, E5 Security, A5 ou A5 ou uma combinação válida de licenças que fornece acesso a todos os serviços com suporte.</span><span class="sxs-lookup"><span data-stu-id="d84fe-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="d84fe-114">Para obter informações detalhadas sobre licenciamento, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="d84fe-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="d84fe-115">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="d84fe-115">Check your role</span></span>

<span data-ttu-id="d84fe-116">Você deve ser um **administrador global** ou um administrador **de** segurança no Azure Active Directory para ativar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d84fe-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="d84fe-117">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="d84fe-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="d84fe-118">Serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="d84fe-118">Supported services</span></span>

<span data-ttu-id="d84fe-119">O Microsoft 365 Defender agrega dados dos vários serviços com suporte que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="d84fe-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="d84fe-120">Ele processará e armazenará dados centralmente para identificar novas percepções e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="d84fe-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="d84fe-121">Ele faz isso sem afetar implantações, configurações ou dados existentes associados aos serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="d84fe-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="d84fe-122">Para obter a melhor proteção e otimizar o Microsoft 365 Defender, recomendamos implantar todos os serviços com suporte aplicáveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="d84fe-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="d84fe-123">Para obter mais informações, [leia sobre a implantação de serviços com suporte.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="d84fe-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="d84fe-124">Integração ao serviço</span><span class="sxs-lookup"><span data-stu-id="d84fe-124">Onboard to the service</span></span>
<span data-ttu-id="d84fe-125">A integração com o Microsoft 365 Defender é simples.</span><span class="sxs-lookup"><span data-stu-id="d84fe-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="d84fe-126">No menu de navegação, selecione qualquer item na seção Pontos de Extremidade, como Incidentes, Busca, Centro de Ações ou Análise de Ameaças para iniciar o processo de integração.</span><span class="sxs-lookup"><span data-stu-id="d84fe-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="d84fe-127">Local do data center</span><span class="sxs-lookup"><span data-stu-id="d84fe-127">Data center location</span></span>

<span data-ttu-id="d84fe-128">O Microsoft 365 Defender armazenará e processará dados no [mesmo local usado pelo Microsoft Defender para o Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="d84fe-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="d84fe-129">Se você não tiver o Microsoft Defender para Ponto de Extremidade, um novo local do data center será selecionado automaticamente com base no local dos serviços de segurança ativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d84fe-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="d84fe-130">O local do data center selecionado é mostrado na tela.</span><span class="sxs-lookup"><span data-stu-id="d84fe-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="d84fe-131">Selecione **Precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento do Microsoft 365 Defender em um local de data center diferente.</span><span class="sxs-lookup"><span data-stu-id="d84fe-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="d84fe-132">O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="d84fe-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="d84fe-133">O Microsoft 365 Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Defender para o Ponto de Extremidade dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="d84fe-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="d84fe-134">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="d84fe-134">Confirm that the service is on</span></span>

<span data-ttu-id="d84fe-135">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="d84fe-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="d84fe-136">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="d84fe-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="d84fe-137">Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="d84fe-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="d84fe-138">Uma central de ações para gerenciar [investigações e respostas automatizadas](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="d84fe-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="d84fe-139">[Recursos avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d84fe-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="d84fe-140">Análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="d84fe-140">Threat analytics</span></span>

<span data-ttu-id="d84fe-141">![Imagem do painel de navegação do Centro de Segurança do Microsoft 365 com o Microsoft 365 Defender apresenta o Centro de segurança do Microsoft 365 com gerenciamento de incidentes e outros recursos do ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="d84fe-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="d84fe-142">Obter dados do Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="d84fe-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="d84fe-143">Para habilitar a integração com o Microsoft Cloud App Security, você precisará fazer logon no Microsoft Cloud App Security pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="d84fe-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="d84fe-144">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="d84fe-144">Get assistance</span></span>

<span data-ttu-id="d84fe-145">Para obter respostas para as perguntas mais frequentes sobre como ligar o Microsoft 365 Defender, [leia as perguntas frequentes](m365d-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d84fe-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="d84fe-146">A equipe de suporte da Microsoft pode ajudar a provisionamento ou desprovisionamento do serviço e recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d84fe-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="d84fe-147">Para assistência, selecione **Precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d84fe-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="d84fe-148">Ao entrar em contato com o suporte, mencione o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d84fe-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d84fe-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d84fe-149">Related topics</span></span>

- [<span data-ttu-id="d84fe-150">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="d84fe-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="d84fe-151">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d84fe-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="d84fe-152">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="d84fe-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="d84fe-153">Visão geral do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d84fe-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="d84fe-154">Visão geral do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d84fe-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="d84fe-155">Visão geral do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d84fe-155">Defender for Office 365 overview</span></span>](../defender-365-security/defender-for-office-365.md)
- [<span data-ttu-id="d84fe-156">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d84fe-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="d84fe-157">Visão geral do Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="d84fe-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="d84fe-158">Microsoft Defender para armazenamento de dados do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d84fe-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
