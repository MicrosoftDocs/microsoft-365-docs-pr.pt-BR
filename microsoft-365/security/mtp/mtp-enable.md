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
ms.openlocfilehash: 394fceffb96350b7702c5eef4a8138b3eb53f714
ms.sourcegitcommit: 997f6227f33c3683ade9672e881d09216df22ee9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44016069"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="1bd95-104">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd95-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="1bd95-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1bd95-105">**Applies to:**</span></span>
- <span data-ttu-id="1bd95-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd95-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1bd95-107">A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure.</span><span class="sxs-lookup"><span data-stu-id="1bd95-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="1bd95-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bd95-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="1bd95-109">Para obter a melhor proteção e otimizar a proteção contra ameaças da Microsoft, recomendamos implantar todos os serviços compatíveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="1bd95-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="1bd95-110">Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="1bd95-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="1bd95-111">Verificar a qualificação de licenças e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="1bd95-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="1bd95-112">Uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças oferece acesso a serviços com suporte e o direito de usar a proteção contra ameaças da Microsoft na central de segurança da Microsoft 365 sem custo adicional de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="1bd95-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="1bd95-113">Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="1bd95-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="1bd95-114">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="1bd95-114">Check your role</span></span>
<span data-ttu-id="1bd95-115">Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bd95-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="1bd95-116">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="1bd95-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="1bd95-117">Começar a usar o serviço</span><span class="sxs-lookup"><span data-stu-id="1bd95-117">Start using the service</span></span>

<span data-ttu-id="1bd95-118">A proteção contra ameaças da Microsoft agrega dados dos vários serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="1bd95-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="1bd95-119">Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="1bd95-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="1bd95-120">Ele faz isso sem afetar as implantações, as configurações ou os dados existentes associados aos serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="1bd95-120">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="1bd95-121">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página de boas-vindas da proteção contra ameaças da Microsoft ao selecionar **incidentes**, a **central de ações**ou a **busca** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="1bd95-121">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="1bd95-122">Essas opções de navegação não são mostradas se você não estiver qualificado para usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bd95-122">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="1bd95-123">![Imagem da página de boas-vindas da proteção contra ameaças da Microsoft mostra se a proteção](../../media/mtp-welcome.png)
contra ameaças da Microsoft não foi ativada na*página de boas-vindas do Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="1bd95-123">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="1bd95-124">Para ativar a proteção contra ameaças da Microsoft, basta concluir o processo na página de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="1bd95-124">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="1bd95-125">Você também pode ativar a proteção contra ameaças da Microsoft acessando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e selecionando **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1bd95-125">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="1bd95-126">Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.</span><span class="sxs-lookup"><span data-stu-id="1bd95-126">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>       

### <a name="select-data-center-location"></a><span data-ttu-id="1bd95-127">Selecionar local do Data Center</span><span class="sxs-lookup"><span data-stu-id="1bd95-127">Select data center location</span></span>
<span data-ttu-id="1bd95-128">Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="1bd95-128">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="1bd95-129">Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bd95-129">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="1bd95-130">Você precisa fornecer consentimento antes que os dados sejam compartilhados entre os serviços e agregados.</span><span class="sxs-lookup"><span data-stu-id="1bd95-130">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="1bd95-131">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="1bd95-131">Confirm that the service is on</span></span>
<span data-ttu-id="1bd95-132">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="1bd95-132">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="1bd95-133">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="1bd95-133">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="1bd95-134">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="1bd95-134">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="1bd95-135">Recursos [avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1bd95-135">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="1bd95-136">![Imagem do painel de navegação do centro de segurança do Microsoft 365 com](../../media/mtp-on.png)
o Microsoft Threat Protection apresenta a*central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*</span><span class="sxs-lookup"><span data-stu-id="1bd95-136">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="1bd95-137">Obter dados da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="1bd95-137">Getting Azure ATP data</span></span>
<span data-ttu-id="1bd95-138">Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada.</span><span class="sxs-lookup"><span data-stu-id="1bd95-138">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="1bd95-139">[Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) </span><span class="sxs-lookup"><span data-stu-id="1bd95-139">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="1bd95-140">Desabilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd95-140">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="1bd95-141">Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bd95-141">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="1bd95-142">Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="1bd95-142">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="1bd95-143">Os recursos correspondentes serão removidos da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bd95-143">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="1bd95-144">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="1bd95-144">Get assistance</span></span>

<span data-ttu-id="1bd95-145">A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1bd95-145">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="1bd95-146">Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bd95-146">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="1bd95-147">Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bd95-147">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1bd95-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1bd95-148">Related topics</span></span>

- [<span data-ttu-id="1bd95-149">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd95-149">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1bd95-150">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1bd95-150">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="1bd95-151">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="1bd95-151">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="1bd95-152">Visão geral do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1bd95-152">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="1bd95-153">Visão geral da ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="1bd95-153">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="1bd95-154">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1bd95-154">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="1bd95-155">Visão geral da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="1bd95-155">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="1bd95-156">Armazenamento de dados da ATP do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1bd95-156">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
