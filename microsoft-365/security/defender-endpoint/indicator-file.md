---
title: Criar indicadores para arquivos
ms.reviewer: ''
description: Crie indicadores para um hash de arquivo que define a detecção, a prevenção e a exclusão de entidades.
keywords: file, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d78f90e78a50d5902070f441a1d60693a5f531c8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185714"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="87ce3-104">Criar indicadores para arquivos</span><span class="sxs-lookup"><span data-stu-id="87ce3-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="87ce3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="87ce3-105">**Applies to:**</span></span>
- [<span data-ttu-id="87ce3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="87ce3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87ce3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87ce3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="87ce3-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="87ce3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="87ce3-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="87ce3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="87ce3-110">Você pode impedir a propagação posterior de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos.</span><span class="sxs-lookup"><span data-stu-id="87ce3-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="87ce3-111">Se você conhecer um arquivo executável portátil potencialmente mal-intencionado (PE), poderá bloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="87ce3-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="87ce3-112">Essa operação impedirá que ela seja lida, escrita ou executada em máquinas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="87ce3-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="87ce3-113">Há duas maneiras de criar indicadores para arquivos:</span><span class="sxs-lookup"><span data-stu-id="87ce3-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="87ce3-114">Criando um indicador por meio da página de configurações</span><span class="sxs-lookup"><span data-stu-id="87ce3-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="87ce3-115">Criando um indicador contextual usando o botão adicionar indicador na página de detalhes do arquivo</span><span class="sxs-lookup"><span data-stu-id="87ce3-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="87ce3-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="87ce3-116">Before you begin</span></span>
<span data-ttu-id="87ce3-117">É importante entender os seguintes pré-requisitos antes da criação de indicadores para arquivos:</span><span class="sxs-lookup"><span data-stu-id="87ce3-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="87ce3-118">Esse recurso estará disponível se sua organização usar Windows Defender proteção baseada em antivírus e nuvem está habilitada.</span><span class="sxs-lookup"><span data-stu-id="87ce3-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="87ce3-119">Para obter mais informações, [consulte Use next-generation technologies in Microsoft Defender Antivírus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="87ce3-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="87ce3-120">A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior.</span><span class="sxs-lookup"><span data-stu-id="87ce3-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="87ce3-121">Suportado em computadores no Windows 10, versão 1703 ou posterior, Windows server 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="87ce3-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="87ce3-122">Para começar a bloquear arquivos, primeiro você precisa ativar o [ **recurso Bloquear ou** permitir](advanced-features.md) em Configurações.</span><span class="sxs-lookup"><span data-stu-id="87ce3-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="87ce3-123">Esse recurso foi projetado para impedir que o malware suspeito (ou arquivos potencialmente mal-intencionados) seja baixado da Web.</span><span class="sxs-lookup"><span data-stu-id="87ce3-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="87ce3-124">Atualmente, ele dá suporte a arquivos executáveis portáteis (PE), incluindo _arquivos .exe_ e _.dll._</span><span class="sxs-lookup"><span data-stu-id="87ce3-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="87ce3-125">A cobertura será estendida ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="87ce3-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="87ce3-126">A função permitir ou bloquear não pode ser feita em arquivos se a classificação do arquivo existir no cache do dispositivo antes da ação permitir ou bloquear</span><span class="sxs-lookup"><span data-stu-id="87ce3-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="87ce3-127">Os arquivos assinados confiáveis serão tratados de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="87ce3-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="87ce3-128">O Defender for Endpoint é otimizado para manipular arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="87ce3-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="87ce3-129">Tentar bloquear arquivos assinados confiáveis, em alguns casos, pode ter implicações de desempenho.</span><span class="sxs-lookup"><span data-stu-id="87ce3-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="87ce3-130">Normalmente, os blocos de arquivos são imposto dentro de alguns minutos, mas podem levar mais de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="87ce3-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="87ce3-131">Criar um indicador para arquivos na página de configurações</span><span class="sxs-lookup"><span data-stu-id="87ce3-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="87ce3-132">No painel de navegação, selecione **Indicadores de**  >  **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="87ce3-133">Selecione a **guia Hash de** arquivo.</span><span class="sxs-lookup"><span data-stu-id="87ce3-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="87ce3-134">Selecione **Adicionar indicador**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="87ce3-135">Especifique os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="87ce3-135">Specify the following details:</span></span>
   - <span data-ttu-id="87ce3-136">Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.</span><span class="sxs-lookup"><span data-stu-id="87ce3-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="87ce3-137">Ação - Especifique a ação a ser tomada e forneça uma descrição.</span><span class="sxs-lookup"><span data-stu-id="87ce3-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="87ce3-138">Escopo - Definir o escopo do grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="87ce3-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="87ce3-139">Revise os detalhes na guia Resumo e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="87ce3-140">Criar um indicador contextual na página de detalhes do arquivo</span><span class="sxs-lookup"><span data-stu-id="87ce3-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="87ce3-141">Uma das opções ao tomar ações [de resposta em um arquivo é](respond-file-alerts.md) adicionar um indicador para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="87ce3-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="87ce3-142">Quando você adiciona um hash de indicador para um arquivo, você pode optar por levantar um alerta e bloquear o arquivo sempre que um computador em sua organização tentar execute-o.</span><span class="sxs-lookup"><span data-stu-id="87ce3-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="87ce3-143">Os arquivos bloqueados automaticamente por um indicador não aparecerão no Centro de Ações do arquivo, mas os alertas ainda estarão visíveis na fila alertas.</span><span class="sxs-lookup"><span data-stu-id="87ce3-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="87ce3-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="87ce3-144">Related topics</span></span>
- [<span data-ttu-id="87ce3-145">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="87ce3-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="87ce3-146">Criar indicadores para IPs e URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="87ce3-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="87ce3-147">Criar indicadores com base em certificados</span><span class="sxs-lookup"><span data-stu-id="87ce3-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="87ce3-148">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="87ce3-148">Manage indicators</span></span>](indicator-manage.md)
