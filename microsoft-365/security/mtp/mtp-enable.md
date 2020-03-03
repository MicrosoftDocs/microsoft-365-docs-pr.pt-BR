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
ms.openlocfilehash: 73c4c9864713432d318b0b3cec9fbaf395deff45
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374138"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="f3442-104">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f3442-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="f3442-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f3442-105">**Applies to:**</span></span>
- <span data-ttu-id="f3442-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f3442-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f3442-107">A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure.</span><span class="sxs-lookup"><span data-stu-id="f3442-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="f3442-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3442-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="f3442-109">Para obter a melhor proteção e otimizar a proteção contra ameaças da Microsoft, recomendamos implantar todos os serviços compatíveis em sua rede.</span><span class="sxs-lookup"><span data-stu-id="f3442-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="f3442-110">Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="f3442-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="f3442-111">Verificar a qualificação de licenças e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f3442-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="f3442-112">Uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças oferece acesso a serviços com suporte e o direito de usar a proteção contra ameaças da Microsoft na central de segurança da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3442-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="f3442-113">Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f3442-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="f3442-114">Verificar sua função</span><span class="sxs-lookup"><span data-stu-id="f3442-114">Check your role</span></span>
<span data-ttu-id="f3442-115">Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3442-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="f3442-116">Exibir suas funções no Azure AD</span><span class="sxs-lookup"><span data-stu-id="f3442-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="f3442-117">Começar a usar o serviço</span><span class="sxs-lookup"><span data-stu-id="f3442-117">Start using the service</span></span>
<span data-ttu-id="f3442-118">A proteção contra ameaças da Microsoft agrega dados dos vários serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="f3442-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="f3442-119">Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="f3442-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="f3442-120">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página de boas-vindas da proteção contra ameaças da Microsoft ao selecionar **incidentes**, a **central de ações**ou a **busca** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="f3442-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="f3442-121">Essas opções de navegação não são mostradas se você não estiver qualificado para usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3442-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="f3442-122">![Imagem da página de boas-vindas da proteção contra ameaças da Microsoft mostra se a proteção](../../media/mtp-welcome.png)
contra ameaças da Microsoft não foi ativada na*página de boas-vindas do Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="f3442-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="f3442-123">Para ativar a proteção contra ameaças da Microsoft, basta concluir o processo na página de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="f3442-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="f3442-124">Você também pode ativar a proteção contra ameaças da Microsoft acessando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e selecionando **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f3442-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="f3442-125">Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.</span><span class="sxs-lookup"><span data-stu-id="f3442-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="f3442-126">Selecionar local do Data Center</span><span class="sxs-lookup"><span data-stu-id="f3442-126">Select data center location</span></span>
<span data-ttu-id="f3442-127">Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="f3442-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="f3442-128">Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3442-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="f3442-129">Você precisa fornecer consentimento antes que os dados sejam compartilhados entre os serviços e agregados.</span><span class="sxs-lookup"><span data-stu-id="f3442-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="f3442-130">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="f3442-130">Confirm that the service is on</span></span>
<span data-ttu-id="f3442-131">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="f3442-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="f3442-132">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="f3442-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="f3442-133">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="f3442-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="f3442-134">Recursos [avançados de busca](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f3442-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="f3442-135">![Imagem do painel de navegação do centro de segurança do Microsoft 365 com](../../media/mtp-on.png)
o Microsoft Threat Protection apresenta a*central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*</span><span class="sxs-lookup"><span data-stu-id="f3442-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="f3442-136">Obter dados da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="f3442-136">Getting Azure ATP data</span></span>
<span data-ttu-id="f3442-137">Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada.</span><span class="sxs-lookup"><span data-stu-id="f3442-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="f3442-138">[Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) </span><span class="sxs-lookup"><span data-stu-id="f3442-138">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="f3442-139">Desabilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f3442-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="f3442-140">Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3442-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="f3442-141">Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="f3442-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="f3442-142">Os recursos correspondentes serão removidos da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3442-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="f3442-143">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="f3442-143">Get assistance</span></span>

<span data-ttu-id="f3442-144">A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f3442-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="f3442-145">Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3442-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="f3442-146">Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3442-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3442-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f3442-147">Related topics</span></span>

- [<span data-ttu-id="f3442-148">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f3442-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="f3442-149">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f3442-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f3442-150">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="f3442-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="f3442-151">Visão geral do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f3442-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="f3442-152">Visão geral da ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="f3442-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="f3442-153">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f3442-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="f3442-154">Visão geral da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="f3442-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="f3442-155">Armazenamento de dados da ATP do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f3442-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
