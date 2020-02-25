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
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235210"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b1bec-104">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1bec-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="b1bec-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b1bec-105">**Applies to:**</span></span>
- <span data-ttu-id="b1bec-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1bec-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b1bec-107">A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure.</span><span class="sxs-lookup"><span data-stu-id="b1bec-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b1bec-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1bec-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b1bec-109">Verificar a qualificação de licenças e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="b1bec-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="b1bec-110">Os clientes com o Microsoft 365 e5, a Microsoft 365 E5 Security ou uma combinação equivalente de licenças podem usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1bec-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="b1bec-111">Para obter mais informações [leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="b1bec-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="b1bec-112">Você deve ser um **administrador global** ou um **administrador de segurança** no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para ativar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1bec-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="b1bec-113">Começar a usar o serviço</span><span class="sxs-lookup"><span data-stu-id="b1bec-113">Start using the service</span></span>
<span data-ttu-id="b1bec-114">A proteção contra ameaças da Microsoft agrega dados dos vários serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="b1bec-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="b1bec-115">Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.</span><span class="sxs-lookup"><span data-stu-id="b1bec-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="b1bec-116">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) não mostra os **incidentes** e as opções da **central de ações** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="b1bec-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="b1bec-117">![Imagem do painel de navegação do centro de segurança do Microsoft 365 sem](../../media/mtp-off.png)
o Microsoft Threat Protection recursos*Microsoft 365 Security Center com a proteção contra ameaças da Microsoft desativada*</span><span class="sxs-lookup"><span data-stu-id="b1bec-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="b1bec-118">Para ativar a proteção contra ameaças da Microsoft, selecione **configurações** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="b1bec-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="b1bec-119">Na **[página Configurações](https://security.microsoft.com/settings)**, vá para**aceitação/** aceitação de **proteção** > contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1bec-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="b1bec-120">Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.</span><span class="sxs-lookup"><span data-stu-id="b1bec-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="b1bec-121">Selecionar local do Data Center</span><span class="sxs-lookup"><span data-stu-id="b1bec-121">Select data center location</span></span>
<span data-ttu-id="b1bec-122">Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="b1bec-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b1bec-123">Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1bec-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="b1bec-124">Você precisa fornecer consentimento antes que os dados sejam compartilhados entre os serviços e agregados.</span><span class="sxs-lookup"><span data-stu-id="b1bec-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b1bec-125">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="b1bec-125">Confirm that the service is on</span></span>
<span data-ttu-id="b1bec-126">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="b1bec-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b1bec-127">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="b1bec-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b1bec-128">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="b1bec-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b1bec-129">Recursos de [Busca avançada](advanced-hunting-overview.md) para as páginas de **Busca** existentes</span><span class="sxs-lookup"><span data-stu-id="b1bec-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="b1bec-130">![Imagem do painel de navegação do centro de segurança do Microsoft 365 com](../../media/mtp-on.png)
o Microsoft Threat Protection apresenta a*central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*</span><span class="sxs-lookup"><span data-stu-id="b1bec-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="b1bec-131">Obter dados da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="b1bec-131">Getting Azure ATP data</span></span>
<span data-ttu-id="b1bec-132">Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada.</span><span class="sxs-lookup"><span data-stu-id="b1bec-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="b1bec-133">[Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) </span><span class="sxs-lookup"><span data-stu-id="b1bec-133">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="b1bec-134">Desabilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1bec-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="b1bec-135">Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1bec-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b1bec-136">Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="b1bec-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="b1bec-137">Os dados serão excluídos permanentemente e os recursos correspondentes serão removidos da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1bec-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b1bec-138">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="b1bec-138">Get assistance</span></span>

<span data-ttu-id="b1bec-139">A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b1bec-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b1bec-140">Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1bec-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b1bec-141">Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1bec-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1bec-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b1bec-142">Related topics</span></span>

- [<span data-ttu-id="b1bec-143">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1bec-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b1bec-144">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b1bec-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b1bec-145">Visão geral do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b1bec-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b1bec-146">Visão geral da ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="b1bec-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b1bec-147">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b1bec-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b1bec-148">Visão geral da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="b1bec-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b1bec-149">Armazenamento de dados da ATP do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b1bec-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
