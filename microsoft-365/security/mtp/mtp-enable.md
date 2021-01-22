---
title: Ativar o Microsoft 365 Defender na central de segurança do Microsoft 365
description: Saiba como habilitar o Microsoft 365 Defender e começar a integrar seu incidente de segurança e resposta.
keywords: get started, enable MTP, Microsoft Threat Protection, M365, security, data location, required permissions, license eligibility, settings page
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930217"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="8f222-104">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f222-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8f222-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8f222-105">**Applies to:**</span></span>
- <span data-ttu-id="8f222-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f222-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8f222-107">[O Microsoft 365 Defender](microsoft-threat-protection.md) unifica o processo de resposta a incidentes integrando os principais recursos do Microsoft Defender para Ponto de Extremidade, do Microsoft Defender para Office 365, do Microsoft Cloud App Security e do Microsoft Defender para Identidade.</span><span class="sxs-lookup"><span data-stu-id="8f222-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="8f222-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f222-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="8f222-109">O Microsoft 365 Defender é ativado automaticamente quando clientes qualificados com as permissões necessárias visitam a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f222-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="8f222-110">Leia este artigo para entender vários pré-requisitos e como o Microsoft 365 Defender é provisionado.</span><span class="sxs-lookup"><span data-stu-id="8f222-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="8f222-111">Verificar a qualificação de licença e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="8f222-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="8f222-112">Uma licença para um produto de segurança do Microsoft 365 geralmente dá o direito de usar o Microsoft 365 Defender na central de segurança do Microsoft 365 sem custo adicional de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="8f222-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="8f222-113">Recomendamos obter uma licença do Microsoft 365 E5, E5 Security, A5 ou A5 Security ou uma combinação válida de licenças que fornece acesso a todos os serviços com suporte.</span><span class="sxs-lookup"><span data-stu-id="8f222-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="8f222-114">Para obter informações detalhadas de licenciamento, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="8f222-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="8f222-115">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="8f222-115">Check your role</span></span>

<span data-ttu-id="8f222-116">Você deve ser um **administrador global ou** um administrador **de** segurança no Azure Active Directory para ativar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8f222-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="8f222-117">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="8f222-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="8f222-118">Serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="8f222-118">Supported services</span></span>

<span data-ttu-id="8f222-119">O Microsoft 365 Defender agrega dados dos vários serviços com suporte que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="8f222-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="8f222-120">Ele processará e armazenará dados centralmente para identificar novas ideias e possibilitar fluxos de trabalho de resposta centralizados.</span><span class="sxs-lookup"><span data-stu-id="8f222-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="8f222-121">Ele faz isso sem afetar implantações, configurações ou dados existentes associados aos serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="8f222-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="8f222-122">Para obter a melhor proteção e otimizar o Microsoft 365 Defender, recomendamos implantar todos os serviços com suporte aplicáveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="8f222-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="8f222-123">Para obter mais informações, [leia sobre a implantação de serviços com suporte.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="8f222-124">Antes de iniciar o serviço</span><span class="sxs-lookup"><span data-stu-id="8f222-124">Before starting the service</span></span>

<span data-ttu-id="8f222-125">Antes de ativar o serviço, a central de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) mostra a página de  configurações do Microsoft 365 Defender quando você seleciona **Incidentes** **,** Central de Ações ou Busca no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="8f222-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="8f222-126">Esses itens de navegação não serão mostrados se você não estiver qualificado para usar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8f222-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="8f222-127">![Imagem da página de configurações do Microsoft 365 Defender mostrada se o Microsoft 365 Defender não tiver sido ligado às configurações do Microsoft 365 Defender na central de segurança do ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="8f222-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="8f222-128">Iniciando o serviço</span><span class="sxs-lookup"><span data-stu-id="8f222-128">Starting the service</span></span>

<span data-ttu-id="8f222-129">Para ativar o Microsoft 365 Defender, basta selecionar **Ativar o Microsoft 365 Defender** e aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="8f222-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="8f222-130">Você também pode acessar  essa opção selecionando Configurações [(security.microsoft.com/settings)](https://security.microsoft.com/settings)no painel de navegação e selecionando **o Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="8f222-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="8f222-131">Se você não vir **Configurações** no painel de navegação ou não conseguiu acessar a página, verifique suas permissões e licenças.</span><span class="sxs-lookup"><span data-stu-id="8f222-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="8f222-132">Local do data center</span><span class="sxs-lookup"><span data-stu-id="8f222-132">Data center location</span></span>

<span data-ttu-id="8f222-133">O Microsoft 365 Defender armazenará e processará dados no [mesmo local usado pelo Microsoft Defender para o ponto de extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="8f222-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="8f222-134">Se você não tiver o Microsoft Defender para o Ponto de Extremidade, um novo local do data center será selecionado automaticamente com base no local dos serviços de segurança ativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f222-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="8f222-135">O local selecionado do data center é mostrado na tela.</span><span class="sxs-lookup"><span data-stu-id="8f222-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="8f222-136">Selecione **Precisa de ajuda?** No centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento do Microsoft 365 Defender em um local diferente do data center.</span><span class="sxs-lookup"><span data-stu-id="8f222-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="8f222-137">O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="8f222-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="8f222-138">O Microsoft 365 Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Defender para o Ponto de Extremidade dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="8f222-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="8f222-139">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="8f222-139">Confirm that the service is on</span></span>

<span data-ttu-id="8f222-140">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="8f222-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="8f222-141">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="8f222-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="8f222-142">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="8f222-143">[Recursos avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="8f222-144">![Imagem do painel de navegação da central de segurança do Microsoft 365 com o Microsoft 365 Defender recursos da central de segurança do Microsoft 365 com gerenciamento de incidentes e outros ](../../media/mtp-enable/mtp-on.png)
 *recursos do Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="8f222-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="8f222-145">Obter dados do Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="8f222-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="8f222-146">Para compartilhar dados do Microsoft Defender for Identity com o Microsoft 365 Defender, certifique-se de que a integração do Microsoft Cloud App Security e do Microsoft Defender for Identity está 1.</span><span class="sxs-lookup"><span data-stu-id="8f222-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="8f222-147">[Saiba mais sobre essa integração.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="8f222-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="8f222-148">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="8f222-148">Get assistance</span></span>

<span data-ttu-id="8f222-149">Para obter respostas para as perguntas mais frequentes sobre como ligar o Microsoft 365 Defender, [leia as perguntas frequentes.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="8f222-150">A equipe de suporte da Microsoft pode ajudar a provisionamento ou desprovisionamento do serviço e dos recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="8f222-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="8f222-151">Para assistência, selecione **Precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f222-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="8f222-152">Ao entrar em contato com o suporte, mencione o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8f222-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f222-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8f222-153">Related topics</span></span>

- [<span data-ttu-id="8f222-154">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="8f222-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="8f222-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8f222-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="8f222-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="8f222-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="8f222-157">Visão geral do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f222-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8f222-158">Visão geral do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8f222-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="8f222-159">Visão geral do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8f222-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="8f222-160">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8f222-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="8f222-161">Visão geral do Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8f222-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="8f222-162">Armazenamento de dados do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8f222-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
