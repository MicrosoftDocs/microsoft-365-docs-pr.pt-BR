---
title: Ativar a Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como habilitar a Proteção contra Ameaças da Microsoft e iniciar a integração do seu incidente de segurança e resposta.
keywords: introdução, MTP, Proteção contra Ameaças da Microsoft, M365, segurança, local dos dados
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: a70754be6e1bd37d292a44e3ada82b3ae13ee6b7
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910748"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="d6ad9-104">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ad9-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="d6ad9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d6ad9-105">**Applies to:**</span></span>
- <span data-ttu-id="d6ad9-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ad9-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="d6ad9-107">A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="d6ad9-108">Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-your-eligibility"></a><span data-ttu-id="d6ad9-109">Verificar sua qualificação </span><span class="sxs-lookup"><span data-stu-id="d6ad9-109">Check your eligibility</span></span>
<span data-ttu-id="d6ad9-110">Os clientes com uma licença do Microsoft 365 E5 ou equivalente podem usar a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="d6ad9-111">Para obter mais informações [leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="d6ad9-111">For more information about licensing requirements:</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="d6ad9-112">Começar a usar o serviço</span><span class="sxs-lookup"><span data-stu-id="d6ad9-112">Start the administration service</span></span>
<span data-ttu-id="d6ad9-113">A ativação do serviço de Proteção contra Ameaças da Microsoft agrega os dados de vários serviços integrados.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-113">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="d6ad9-114">Os dados serão processados e armazenados centralmente para identificar novas ideias e possibilitar fluxos de trabalho de resposta centralizados.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-114">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="d6ad9-115">Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) não mostra as opções de **Incidentes** e **Central de Ações** no menu.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-115">Before you turn the service on, Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="d6ad9-116">![Imagem do menu do centro de segurança do Microsoft 365 sem os recursos da Proteção contra Ameaças da Microsoft](../images/mtp-off.png)
*Centro de segurança do Microsoft 365 com a Proteção contra Ameaças da Microsoft desativada*</span><span class="sxs-lookup"><span data-stu-id="d6ad9-116">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="d6ad9-117">Para ativar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-117">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="d6ad9-118">Será necessário ser um administrador global ou um administrador de segurança no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-118">You will need to be a global administrator or a security administrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to perform this task.</span></span>

<span data-ttu-id="d6ad9-119">Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="d6ad9-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="d6ad9-120">Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="d6ad9-121">Será necessário fornecer o consentimento antes que os dados sejam compartilhados entre serviços e agregados.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="d6ad9-122">Confirmar se o serviço está ativado</span><span class="sxs-lookup"><span data-stu-id="d6ad9-122">Confirm that the service is on</span></span>
<span data-ttu-id="d6ad9-123">Depois que o serviço é provisionado, ele adiciona:</span><span class="sxs-lookup"><span data-stu-id="d6ad9-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="d6ad9-124">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="d6ad9-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="d6ad9-125">Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="d6ad9-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="d6ad9-126">Recursos de [Busca avançada](advanced-hunting-overview.md) para as páginas de **Busca** existentes</span><span class="sxs-lookup"><span data-stu-id="d6ad9-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="d6ad9-127">![Imagem do menu do centro de segurança do Microsoft 365 com os recursos da Proteção contra Ameaças da Microsoft](../images/mtp-on.png)
*Centro de segurança do Microsoft 365 com gerenciamento de incidentes e outros recursos de Proteção contra Ameaças da Microsoft*</span><span class="sxs-lookup"><span data-stu-id="d6ad9-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="d6ad9-128">Obter dados da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="d6ad9-128">Getting Azure ATP data</span></span>
<span data-ttu-id="d6ad9-129">Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="d6ad9-130">[Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) </span><span class="sxs-lookup"><span data-stu-id="d6ad9-130">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="d6ad9-131">Desabilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ad9-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="d6ad9-132">Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > \*\* Proteção contra Ameaças da Microsoft\*\* > **Aceitar/Recusar** no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="d6ad9-133">Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="d6ad9-134">Os dados serão excluídos permanentemente e os recursos correspondentes serão removidos do centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-134">Data will be permanently deleted and corresponding features will be removed from Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="d6ad9-135">Obter assistência</span><span class="sxs-lookup"><span data-stu-id="d6ad9-135">Get assistance</span></span>

<span data-ttu-id="d6ad9-136">A equipe da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d6ad9-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="d6ad9-137">Para obter assistência, [contatar o suporte premier](https://go.microsoft.com/fwlink/?LinkID=733758).</span><span class="sxs-lookup"><span data-stu-id="d6ad9-137">For assistance, [contact premier support](https://go.microsoft.com/fwlink/?LinkID=733758).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d6ad9-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d6ad9-138">Related topics</span></span>

- [<span data-ttu-id="d6ad9-139">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ad9-139">Microsoft Advanced Threat Protection</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d6ad9-140">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d6ad9-140">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="d6ad9-141">Visão geral do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d6ad9-141">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="d6ad9-142">Visão geral da ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="d6ad9-142">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="d6ad9-143">Visão geral do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d6ad9-143">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="d6ad9-144">Visão geral da ATP do Azure</span><span class="sxs-lookup"><span data-stu-id="d6ad9-144">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="d6ad9-145">Armazenamento de dados da ATP do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6ad9-145">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
