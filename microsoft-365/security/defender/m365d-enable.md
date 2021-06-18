---
title: Ativar Microsoft 365 Defender no centro de segurança Microsoft 365 segurança
description: Saiba como habilitar Microsoft 365 Defender e começar a integrar seu incidente e resposta de segurança.
keywords: get started, enable Microsoft 365 Defender, Microsoft 365 Defender, M365, security, data location, required permissions, license eligibility, settings page
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
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007604"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="6358b-104">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6358b-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6358b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6358b-105">**Applies to:**</span></span>
- <span data-ttu-id="6358b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6358b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6358b-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifica seu processo de resposta a incidentes integrando os principais recursos do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade.</span><span class="sxs-lookup"><span data-stu-id="6358b-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6358b-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6358b-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="6358b-109">Microsoft 365 Defender automaticamente é ativado quando clientes qualificados com as permissões necessárias visitam Microsoft 365 central de segurança.</span><span class="sxs-lookup"><span data-stu-id="6358b-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="6358b-110">Leia este artigo para entender vários pré-requisitos e como Microsoft 365 Defender é provisionado.</span><span class="sxs-lookup"><span data-stu-id="6358b-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="6358b-111">Verificar a qualificação da licença e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="6358b-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="6358b-112">Uma licença para um Microsoft 365 de segurança geralmente lhe dá o direito de usar Microsoft 365 Defender no Microsoft 365 de segurança sem custo adicional de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="6358b-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="6358b-113">Recomendamos obter uma licença de segurança Microsoft 365 E5, segurança do E5, A5 ou A5 ou uma combinação válida de licenças que fornece acesso a todos os serviços com suporte.</span><span class="sxs-lookup"><span data-stu-id="6358b-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="6358b-114">Para obter informações detalhadas sobre licenciamento, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="6358b-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="6358b-115">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="6358b-115">Check your role</span></span>

<span data-ttu-id="6358b-116">Você deve ser um **administrador global ou** um administrador **de** segurança no Active Directory do Azure para ativar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6358b-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="6358b-117">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="6358b-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="6358b-118">Serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="6358b-118">Supported services</span></span>

<span data-ttu-id="6358b-119">Microsoft 365 Defender agrega dados dos vários serviços com suporte que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="6358b-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="6358b-120">Ele processará e armazenará dados centralmente para identificar novas percepções e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="6358b-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="6358b-121">Ele faz isso sem afetar implantações, configurações ou dados existentes associados aos serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="6358b-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="6358b-122">Para obter a melhor proteção e otimizar Microsoft 365 Defender, recomendamos implantar todos os serviços com suporte aplicáveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="6358b-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="6358b-123">Para obter mais informações, [leia sobre a implantação de serviços com suporte.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="6358b-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="6358b-124">Integração ao serviço</span><span class="sxs-lookup"><span data-stu-id="6358b-124">Onboard to the service</span></span>
<span data-ttu-id="6358b-125">A integração ao Microsoft 365 Defender é simples.</span><span class="sxs-lookup"><span data-stu-id="6358b-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="6358b-126">No menu de navegação, selecione qualquer item, como **Incidentes & alertas,** **Busca,** Centro de Ações **ou** Análise de ameaças para iniciar o processo de integração. </span><span class="sxs-lookup"><span data-stu-id="6358b-126">From the navigation menu, select any item, such as **Incidents & alerts**, **Hunting**, **Action center**, or **Threat analytics** to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="6358b-127">Local do data center</span><span class="sxs-lookup"><span data-stu-id="6358b-127">Data center location</span></span>

<span data-ttu-id="6358b-128">Microsoft 365 Defender armazenar e processar dados no [mesmo local usado pelo Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="6358b-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="6358b-129">Se você não tiver o Microsoft Defender para Ponto de Extremidade, um novo local do data center será selecionado automaticamente com base no local dos serviços Microsoft 365 de segurança ativos.</span><span class="sxs-lookup"><span data-stu-id="6358b-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="6358b-130">O local do data center selecionado é mostrado na tela.</span><span class="sxs-lookup"><span data-stu-id="6358b-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="6358b-131">Selecione **Precisa de ajuda?** no centro de segurança Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento Microsoft 365 Defender em um local diferente do data center.</span><span class="sxs-lookup"><span data-stu-id="6358b-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="6358b-132">No passado, o Microsoft Defender para Ponto de Extremidade era provisionado automaticamente nos data centers da União Europeia (UE) quando ativado por meio do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="6358b-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="6358b-133">Microsoft 365 Defender provisionamento automático no mesmo data center da UE para clientes que provisionou o Defender para o Ponto de Extremidade dessa maneira no passado.</span><span class="sxs-lookup"><span data-stu-id="6358b-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="6358b-134">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="6358b-134">Confirm that the service is on</span></span>

<span data-ttu-id="6358b-135">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="6358b-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="6358b-136">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="6358b-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="6358b-137">Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="6358b-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="6358b-138">Uma central de ações para gerenciar [investigações e respostas automatizadas](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="6358b-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="6358b-139">[Recursos avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6358b-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="6358b-140">Análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="6358b-140">Threat analytics</span></span>

<span data-ttu-id="6358b-141">![Imagem do painel Microsoft 365 de navegação do centro de segurança com Microsoft 365 Defender recursos Microsoft 365 central de segurança com gerenciamento de ](../../media/overview-incident.png)
 *incidentes e* outros recursos Microsoft 365 Defender segurança</span><span class="sxs-lookup"><span data-stu-id="6358b-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="6358b-142">Obter dados do Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="6358b-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="6358b-143">Para habilitar a integração com Microsoft Cloud App Security, você precisará fazer logon no Microsoft Cloud App Security pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="6358b-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="6358b-144">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="6358b-144">Get assistance</span></span>

<span data-ttu-id="6358b-145">Para obter respostas para as perguntas mais frequentes sobre como Microsoft 365 Defender, [leia as perguntas frequentes](m365d-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6358b-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="6358b-146">A equipe de suporte da Microsoft pode ajudar a provisionamento ou desprovisionamento do serviço e recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="6358b-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="6358b-147">Para assistência, selecione **Precisa de ajuda?** no centro Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="6358b-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="6358b-148">Ao entrar em contato com o suporte, Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6358b-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6358b-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6358b-149">Related topics</span></span>

- [<span data-ttu-id="6358b-150">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6358b-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="6358b-151">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6358b-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="6358b-152">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="6358b-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="6358b-153">Microsoft 365 Defender visão geral</span><span class="sxs-lookup"><span data-stu-id="6358b-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="6358b-154">Visão geral do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6358b-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="6358b-155">Visão geral do Defender Office 365 visão geral</span><span class="sxs-lookup"><span data-stu-id="6358b-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="6358b-156">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6358b-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="6358b-157">Visão geral do Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="6358b-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="6358b-158">Microsoft Defender para armazenamento de dados do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6358b-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
