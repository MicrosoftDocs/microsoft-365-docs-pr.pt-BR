---
title: Ativar a Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como habilitar a Proteção contra Ameaças da Microsoft e iniciar a integração do seu incidente de segurança e resposta.
keywords: introdução, habilitar MTP, proteção contra ameaças da Microsoft, M365, segurança, local dos dados, permissões necessárias, qualificação para licença, página Configurações
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844583"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="21cd8-104">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="21cd8-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="21cd8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="21cd8-105">**Applies to:**</span></span>
- <span data-ttu-id="21cd8-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="21cd8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="21cd8-107">A [proteção contra ameaças da Microsoft](microsoft-threat-protection.md) unifica seu processo de resposta a incidentes por meio da integração de recursos principais à proteção avançada contra ameaças do Microsoft defender (ATP), Office 365 ATP, Microsoft Cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="21cd8-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="21cd8-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21cd8-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="21cd8-109">A proteção contra ameaças da Microsoft automaticamente é ativada quando os clientes qualificados com as permissões necessárias visitam a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21cd8-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="21cd8-110">Leia este artigo para entender vários pré-requisitos e como a proteção contra ameaças da Microsoft é provisionada.</span><span class="sxs-lookup"><span data-stu-id="21cd8-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="21cd8-111">Verificar a qualificação de licenças e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="21cd8-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="21cd8-112">Uma licença para um produto de segurança do Microsoft 365 geralmente concede a você o uso da proteção contra ameaças da Microsoft no Microsoft 365, sem custo adicional de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="21cd8-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="21cd8-113">Recomendamos obter uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças que forneçam acesso a todos os serviços com suporte.</span><span class="sxs-lookup"><span data-stu-id="21cd8-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="21cd8-114">Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="21cd8-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="21cd8-115">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="21cd8-115">Check your role</span></span>
<span data-ttu-id="21cd8-116">Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21cd8-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="21cd8-117">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="21cd8-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="21cd8-118">Serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="21cd8-118">Supported services</span></span>
<span data-ttu-id="21cd8-119">A proteção contra ameaças da Microsoft agrega dados dos vários serviços com suporte que você já tenha implantado.</span><span class="sxs-lookup"><span data-stu-id="21cd8-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="21cd8-120">Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="21cd8-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="21cd8-121">Ele faz isso sem afetar as implantações, as configurações ou os dados existentes associados aos serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="21cd8-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="21cd8-122">Para obter a melhor proteção e otimizar a proteção contra ameaças da Microsoft, recomendamos implantar todos os serviços compatíveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="21cd8-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="21cd8-123">Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="21cd8-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="21cd8-124">Antes de iniciar o serviço</span><span class="sxs-lookup"><span data-stu-id="21cd8-124">Before starting the service</span></span>
<span data-ttu-id="21cd8-125">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página Configurações de proteção contra ameaças da Microsoft quando você seleciona **incidentes**, **central de ações**ou **busca** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="21cd8-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="21cd8-126">Esses itens de navegação não são mostrados se você não estiver qualificado para usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21cd8-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="21cd8-127">![Imagem da página de configurações de proteção contra ameaças da Microsoft mostra se a proteção contra ameaças da Microsoft não foi ativada nas ](../../media/mtp-enable/mtp-settings.png)
 *configurações de proteção contra ameaças da Microsoft no centro de segurança do Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="21cd8-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="21cd8-128">Iniciar o serviço</span><span class="sxs-lookup"><span data-stu-id="21cd8-128">Starting the service</span></span>
<span data-ttu-id="21cd8-129">Para ativar a proteção contra ameaças da Microsoft, basta selecionar **ativar a proteção contra ameaças da Microsoft** e aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="21cd8-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="21cd8-130">Você também pode acessar essa opção selecionando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e, em seguida, selecionando **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="21cd8-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="21cd8-131">Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.</span><span class="sxs-lookup"><span data-stu-id="21cd8-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="21cd8-132">Local do Data Center</span><span class="sxs-lookup"><span data-stu-id="21cd8-132">Data center location</span></span>
<span data-ttu-id="21cd8-133">A proteção contra ameaças da Microsoft armazenará e processará dados no [mesmo local usado pelo Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="21cd8-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="21cd8-134">Se você não tiver o Microsoft defender ATP, um novo local de Data Center será selecionado automaticamente com base no local dos serviços de segurança do Microsoft 365 ativos.</span><span class="sxs-lookup"><span data-stu-id="21cd8-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="21cd8-135">O local do Data Center selecionado é mostrado na tela.</span><span class="sxs-lookup"><span data-stu-id="21cd8-135">The selected data center location is shown in the screen.</span></span>

>[!NOTE]
><span data-ttu-id="21cd8-136">Selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre a provisão de proteção contra ameaças da Microsoft em um local diferente de data center</span><span class="sxs-lookup"><span data-stu-id="21cd8-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provision Microsoft Threat Protection in a different data center location.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="21cd8-137">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="21cd8-137">Confirm that the service is on</span></span>
<span data-ttu-id="21cd8-138">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="21cd8-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="21cd8-139">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="21cd8-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="21cd8-140">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="21cd8-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="21cd8-141">Recursos [avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="21cd8-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="21cd8-142">![Imagem do painel de navegação do centro de segurança do Microsoft 365 com o Microsoft Threat Protection apresenta a ](../../media/mtp-enable/mtp-on.png)
 *central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*</span><span class="sxs-lookup"><span data-stu-id="21cd8-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="21cd8-143">Obter dados da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="21cd8-143">Getting Azure ATP data</span></span>
<span data-ttu-id="21cd8-144">Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada.</span><span class="sxs-lookup"><span data-stu-id="21cd8-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="21cd8-145">[Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) </span><span class="sxs-lookup"><span data-stu-id="21cd8-145">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="21cd8-146">Desabilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="21cd8-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="21cd8-147">Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21cd8-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="21cd8-148">Desmarque **ativar a proteção contra ameaças da Microsoft** e aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="21cd8-148">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="21cd8-149">Os recursos correspondentes serão removidos da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21cd8-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="21cd8-150">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="21cd8-150">Get assistance</span></span>

<span data-ttu-id="21cd8-151">Para obter respostas para as perguntas mais frequentes sobre como ativar a proteção contra ameaças [da Microsoft, leia as perguntas frequentes](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="21cd8-151">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="21cd8-152">A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="21cd8-152">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="21cd8-153">Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21cd8-153">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="21cd8-154">Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21cd8-154">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="21cd8-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="21cd8-155">Related topics</span></span>

- [<span data-ttu-id="21cd8-156">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="21cd8-156">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="21cd8-157">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="21cd8-157">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="21cd8-158">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="21cd8-158">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="21cd8-159">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="21cd8-159">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="21cd8-160">Visão geral do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="21cd8-160">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="21cd8-161">Visão geral da ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="21cd8-161">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="21cd8-162">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="21cd8-162">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="21cd8-163">Visão geral da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="21cd8-163">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="21cd8-164">Armazenamento de dados da ATP do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="21cd8-164">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)