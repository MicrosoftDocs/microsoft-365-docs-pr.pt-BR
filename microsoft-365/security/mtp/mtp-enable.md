---
title: Ativar a Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como habilitar a Proteção contra Ameaças da Microsoft e iniciar a integração do seu incidente de segurança e resposta.
keywords: introdução, habilitar MTP, proteção contra ameaças da Microsoft, M365, segurança, local de dados, permissões necessárias, qualificação para licenças
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
ms.openlocfilehash: 8aeff373b3f5550f7217a5b56aa1dbf994563825
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600058"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="f362b-104">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f362b-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="f362b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f362b-105">**Applies to:**</span></span>
- <span data-ttu-id="f362b-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f362b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f362b-107">A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure.</span><span class="sxs-lookup"><span data-stu-id="f362b-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="f362b-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f362b-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="f362b-109">Verificar a qualificação de licenças e as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f362b-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="f362b-110">Os clientes com uma licença do Microsoft 365 E5 ou equivalente podem usar a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f362b-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="f362b-111">Para obter mais informações [leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f362b-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

 <span data-ttu-id="f362b-112">Para poder ativar a proteção contra ameaças da Microsoft, você precisa ser um **administrador global** ou um **administrador de segurança** no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span><span class="sxs-lookup"><span data-stu-id="f362b-112">To be able to turn on Microsoft Threat Protection, you need to be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="f362b-113">Começar a usar o serviço</span><span class="sxs-lookup"><span data-stu-id="f362b-113">Start using the service</span></span>
<span data-ttu-id="f362b-114">A ativação do serviço de Proteção contra Ameaças da Microsoft agrega os dados de vários serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="f362b-114">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="f362b-115">Os dados serão processados e armazenados centralmente para identificar novas ideias e possibilitar fluxos de trabalho de resposta centralizados.</span><span class="sxs-lookup"><span data-stu-id="f362b-115">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="f362b-116">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) não mostra os **incidentes** e as opções da **central de ações** no menu.</span><span class="sxs-lookup"><span data-stu-id="f362b-116">Before you turn the service on, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="f362b-117">![Imagem do menu do centro de segurança do Microsoft 365 sem os recursos da Proteção contra Ameaças da Microsoft](../images/mtp-off.png)
*Centro de segurança do Microsoft 365 com a Proteção contra Ameaças da Microsoft desativada*</span><span class="sxs-lookup"><span data-stu-id="f362b-117">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="f362b-118">Para ativar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f362b-118">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span>

<span data-ttu-id="f362b-119">Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="f362b-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="f362b-120">Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f362b-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="f362b-121">Será necessário fornecer o consentimento antes que os dados sejam compartilhados entre serviços e agregados.</span><span class="sxs-lookup"><span data-stu-id="f362b-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="f362b-122">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="f362b-122">Confirm that the service is on</span></span>
<span data-ttu-id="f362b-123">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="f362b-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="f362b-124">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="f362b-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="f362b-125">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="f362b-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="f362b-126">Recursos de [Busca avançada](advanced-hunting-overview.md) para as páginas de **Busca** existentes</span><span class="sxs-lookup"><span data-stu-id="f362b-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="f362b-127">![Imagem do menu do centro de segurança do Microsoft 365 com os recursos da Proteção contra Ameaças da Microsoft](../images/mtp-on.png)
*Centro de segurança do Microsoft 365 com gerenciamento de incidentes e outros recursos de Proteção contra Ameaças da Microsoft*</span><span class="sxs-lookup"><span data-stu-id="f362b-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="f362b-128">Obter dados da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="f362b-128">Getting Azure ATP data</span></span>
<span data-ttu-id="f362b-129">Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada.</span><span class="sxs-lookup"><span data-stu-id="f362b-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="f362b-130">[Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) </span><span class="sxs-lookup"><span data-stu-id="f362b-130">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="f362b-131">Desabilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f362b-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="f362b-132">Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f362b-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="f362b-133">Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="f362b-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="f362b-134">Os dados serão excluídos permanentemente e os recursos correspondentes serão removidos da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f362b-134">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="f362b-135">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="f362b-135">Get assistance</span></span>

<span data-ttu-id="f362b-136">A equipe da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f362b-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="f362b-137">Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f362b-137">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="f362b-138">Ao descrever suas preocupações, mencione "proteção contra ameaças da Microsoft".</span><span class="sxs-lookup"><span data-stu-id="f362b-138">When describing your concerns, mention "Microsoft Threat Protection".</span></span>

## <a name="related-topics"></a><span data-ttu-id="f362b-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f362b-139">Related topics</span></span>

- [<span data-ttu-id="f362b-140">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f362b-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="f362b-141">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f362b-141">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f362b-142">Visão geral do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f362b-142">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="f362b-143">Visão geral da ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="f362b-143">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="f362b-144">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f362b-144">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="f362b-145">Visão geral da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="f362b-145">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="f362b-146">Armazenamento de dados da ATP do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f362b-146">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
