---
title: Ative o Microsoft 365 defender no centro de segurança do Microsoft 365
description: Saiba como habilitar o Microsoft 365 defender e começar a integrar seu incidente de segurança e resposta.
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760501"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="f006d-104">Ativar o Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f006d-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f006d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f006d-105">**Applies to:**</span></span>
- <span data-ttu-id="f006d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f006d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f006d-107">O [Microsoft 365 defender](microsoft-threat-protection.md) unifica seu processo de resposta a incidentes por meio da integração de recursos importantes no Microsoft defender para ponto de extremidade, Microsoft defender para Office 365, Microsoft Cloud app Security e Microsoft defender para identidade.</span><span class="sxs-lookup"><span data-stu-id="f006d-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="f006d-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f006d-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="f006d-109">O Microsoft 365 defender automaticamente é ativado quando os clientes qualificados com as permissões necessárias visitam a central de segurança da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f006d-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="f006d-110">Leia este artigo para entender vários pré-requisitos e como o Microsoft 365 defender é provisionado.</span><span class="sxs-lookup"><span data-stu-id="f006d-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="f006d-111">Verificar a qualificação de licenças e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f006d-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="f006d-112">Uma licença para um produto de segurança do Microsoft 365 geralmente concede a você o uso do Microsoft 365 defender no centro de segurança do Microsoft 365 sem custo adicional de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="f006d-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="f006d-113">Recomendamos obter uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças que forneçam acesso a todos os serviços com suporte.</span><span class="sxs-lookup"><span data-stu-id="f006d-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="f006d-114">Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f006d-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="f006d-115">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="f006d-115">Check your role</span></span>

<span data-ttu-id="f006d-116">Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar o Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="f006d-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="f006d-117">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="f006d-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="f006d-118">Serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="f006d-118">Supported services</span></span>

<span data-ttu-id="f006d-119">O Microsoft 365 defender agrega dados dos vários serviços com suporte que você já tenha implantado.</span><span class="sxs-lookup"><span data-stu-id="f006d-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="f006d-120">Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="f006d-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="f006d-121">Ele faz isso sem afetar as implantações, as configurações ou os dados existentes associados aos serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="f006d-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="f006d-122">Para obter a melhor proteção e otimizar o Microsoft 365 defender, recomendamos implantar todos os serviços compatíveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="f006d-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="f006d-123">Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="f006d-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="f006d-124">Antes de iniciar o serviço</span><span class="sxs-lookup"><span data-stu-id="f006d-124">Before starting the service</span></span>

<span data-ttu-id="f006d-125">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página de configurações do Microsoft 365 defender quando você seleciona **incidentes**, **central de ações** ou **busca** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="f006d-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="f006d-126">Esses itens de navegação não são mostrados se você não estiver qualificado para usar o Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="f006d-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="f006d-127">![Imagem da página de configurações do Microsoft 365 defender mostra se o Microsoft 365 defender não foi ativado nas ](../../media/mtp-enable/mtp-settings.png)
 *configurações do Microsoft 365 defender no centro de segurança do Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="f006d-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="f006d-128">Iniciar o serviço</span><span class="sxs-lookup"><span data-stu-id="f006d-128">Starting the service</span></span>

<span data-ttu-id="f006d-129">Para ativar o Microsoft 365 defender, basta selecionar **ativar o microsoft 365 defender** e aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="f006d-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="f006d-130">Você também pode acessar essa opção selecionando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e, em seguida, selecionando **o Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="f006d-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="f006d-131">Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.</span><span class="sxs-lookup"><span data-stu-id="f006d-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="f006d-132">Local do Data Center</span><span class="sxs-lookup"><span data-stu-id="f006d-132">Data center location</span></span>

<span data-ttu-id="f006d-133">O Microsoft 365 defender armazenará e processará dados no [mesmo local usado pelo Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="f006d-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="f006d-134">Se você não tiver o Microsoft defender para ponto de extremidade, um novo local de Data Center será selecionado automaticamente com base no local dos serviços de segurança do Microsoft 365 ativos.</span><span class="sxs-lookup"><span data-stu-id="f006d-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="f006d-135">O local do Data Center selecionado é mostrado na tela.</span><span class="sxs-lookup"><span data-stu-id="f006d-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="f006d-136">Selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento do Microsoft 365 defender em um local diferente de data center.</span><span class="sxs-lookup"><span data-stu-id="f006d-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="f006d-137">O Microsoft defender for Endpoint provisiona automaticamente nos data centers da União Europeia (UE) quando ativado pelo Azure defender.</span><span class="sxs-lookup"><span data-stu-id="f006d-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="f006d-138">O Microsoft 365 defender será automaticamente provisionado no mesmo Data Center da UE para clientes que tenham provisionado o defender para ponto de extremidade dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="f006d-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="f006d-139">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="f006d-139">Confirm that the service is on</span></span>

<span data-ttu-id="f006d-140">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="f006d-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="f006d-141">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="f006d-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="f006d-142">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="f006d-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="f006d-143">Recursos [avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f006d-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="f006d-144">![Imagem do painel de navegação do centro de segurança do Microsoft 365 com o Microsoft 365 defender apresenta ](../../media/mtp-enable/mtp-on.png)
 *o centro de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos do Microsoft 365 defender*</span><span class="sxs-lookup"><span data-stu-id="f006d-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="f006d-145">Obtendo dados do Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="f006d-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="f006d-146">Para compartilhar os dados do Microsoft defender para identidade com o Microsoft 365 defender, certifique-se de que o Microsoft Cloud app Security e o Microsoft defender para integração de identidade estejam ativados.</span><span class="sxs-lookup"><span data-stu-id="f006d-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="f006d-147">[Saiba mais sobre essa integração](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="f006d-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="f006d-148">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="f006d-148">Get assistance</span></span>

<span data-ttu-id="f006d-149">Para obter respostas para as perguntas mais frequentes sobre como ativar o Microsoft 365 defender, [Leia as perguntas frequentes](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="f006d-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="f006d-150">A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f006d-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="f006d-151">Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f006d-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="f006d-152">Ao entrar em contato com o suporte, mencione o Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="f006d-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f006d-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f006d-153">Related topics</span></span>

- [<span data-ttu-id="f006d-154">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="f006d-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="f006d-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f006d-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f006d-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="f006d-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="f006d-157">Visão geral do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f006d-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="f006d-158">Visão geral do Microsoft defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f006d-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="f006d-159">Visão geral do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f006d-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="f006d-160">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f006d-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="f006d-161">Visão geral do Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="f006d-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="f006d-162">Armazenamento de dados do Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="f006d-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
