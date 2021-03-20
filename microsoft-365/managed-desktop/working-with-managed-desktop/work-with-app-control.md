---
title: Trabalhar com o controle de aplicativo
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917635"
---
# <a name="work-with-app-control"></a><span data-ttu-id="47887-103">Trabalhar com o controle de aplicativo</span><span class="sxs-lookup"><span data-stu-id="47887-103">Work with app control</span></span>

<span data-ttu-id="47887-104">Depois que o controle do aplicativo é implantado em seu ambiente, você e As Operações de Área de Trabalho Gerenciadas da Microsoft têm responsabilidades contínuas.</span><span class="sxs-lookup"><span data-stu-id="47887-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="47887-105">Por exemplo, talvez você queira adicionar um novo aplicativo ao ambiente ou adicionar (ou remover) um signante confiável.</span><span class="sxs-lookup"><span data-stu-id="47887-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="47887-106">Para melhorar a segurança, todos os aplicativos devem ser assinados com código antes de liberá-los para os usuários.</span><span class="sxs-lookup"><span data-stu-id="47887-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="47887-107">Os detalhes do editor de um aplicativo incluem informações sobre o signante.</span><span class="sxs-lookup"><span data-stu-id="47887-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="47887-108">Adicionar um novo aplicativo</span><span class="sxs-lookup"><span data-stu-id="47887-108">Add a new app</span></span>

<span data-ttu-id="47887-109">Para adicionar um novo aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="47887-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="47887-110">Adicione o aplicativo ao [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="47887-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="47887-111">Implante o aplicativo em qualquer dispositivo no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="47887-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="47887-112">Teste seu aplicativo de acordo com seus processos comerciais padrão.</span><span class="sxs-lookup"><span data-stu-id="47887-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="47887-113">Verifique o Visualizador de Eventos em Logs de Aplicativos e **Serviços\Microsoft\Windows\AppLocker**, procurando eventos **8003** ou **8006.**</span><span class="sxs-lookup"><span data-stu-id="47887-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="47887-114">Esses eventos indicam que o aplicativo seria bloqueado.</span><span class="sxs-lookup"><span data-stu-id="47887-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="47887-115">Para obter mais informações sobre todos os eventos do App Locker e seus significados, consulte [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="47887-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="47887-116">Se você encontrar qualquer um desses eventos, abra uma solicitação de signante com Operações de Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47887-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="47887-117">Adicionar (ou remover) um signante confiável</span><span class="sxs-lookup"><span data-stu-id="47887-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="47887-118">Ao abrir uma solicitação de signante, você precisará fornecer alguns detalhes importantes do editor primeiro.</span><span class="sxs-lookup"><span data-stu-id="47887-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="47887-119">Em seguida, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="47887-119">Then follow these steps:</span></span>

1. <span data-ttu-id="47887-120">[Reunir detalhes do editor](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="47887-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="47887-121">Abra um tíquete com Operações de Área de Trabalho Gerenciada da Microsoft para solicitar a regra do signante e inclua os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="47887-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="47887-122">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="47887-122">Application name</span></span> 
    - <span data-ttu-id="47887-123">Versão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="47887-123">Application version</span></span> 
    - <span data-ttu-id="47887-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="47887-124">Description</span></span> 
    - <span data-ttu-id="47887-125">Tipo de alteração ("adicionar" ou "remover")</span><span class="sxs-lookup"><span data-stu-id="47887-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="47887-126">Detalhes do editor (por exemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="47887-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="47887-127">Para remover a confiança de um aplicativo, siga as mesmas etapas, mas de definir **o tipo de alteração** para *remover*.</span><span class="sxs-lookup"><span data-stu-id="47887-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="47887-128">As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:</span><span class="sxs-lookup"><span data-stu-id="47887-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="47887-129">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="47887-129">Deployment group</span></span>  |<span data-ttu-id="47887-130">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="47887-130">Policy type</span></span>  |<span data-ttu-id="47887-131">Tempo</span><span class="sxs-lookup"><span data-stu-id="47887-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="47887-132">Testar</span><span class="sxs-lookup"><span data-stu-id="47887-132">Test</span></span>     |  <span data-ttu-id="47887-133">Auditoria</span><span class="sxs-lookup"><span data-stu-id="47887-133">Audit</span></span>       |  <span data-ttu-id="47887-134">Dia 0</span><span class="sxs-lookup"><span data-stu-id="47887-134">Day 0</span></span>       |
|<span data-ttu-id="47887-135">Primeiro</span><span class="sxs-lookup"><span data-stu-id="47887-135">First</span></span>     | <span data-ttu-id="47887-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="47887-136">Enforced</span></span>        | <span data-ttu-id="47887-137">1º dia</span><span class="sxs-lookup"><span data-stu-id="47887-137">Day 1</span></span>        |
|<span data-ttu-id="47887-138">Rápida</span><span class="sxs-lookup"><span data-stu-id="47887-138">Fast</span></span>     | <span data-ttu-id="47887-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="47887-139">Enforced</span></span>        |  <span data-ttu-id="47887-140">2º dia</span><span class="sxs-lookup"><span data-stu-id="47887-140">Day 2</span></span>       |
|<span data-ttu-id="47887-141">Amplas</span><span class="sxs-lookup"><span data-stu-id="47887-141">Broad</span></span>     | <span data-ttu-id="47887-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="47887-142">Enforced</span></span>        |  <span data-ttu-id="47887-143">3º dia</span><span class="sxs-lookup"><span data-stu-id="47887-143">Day 3</span></span>       |


<span data-ttu-id="47887-144">Você pode pausar ou reverter a implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="47887-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="47887-145">Para fazer isso, abra outra solicitação de serviço com Operações.</span><span class="sxs-lookup"><span data-stu-id="47887-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="47887-146">Se você pausar o lançamento de uma regra de signante, essa regra deverá ser retorda ou concluída antes que outra versão possa ser iniciada.</span><span class="sxs-lookup"><span data-stu-id="47887-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="47887-147">Reunir detalhes do editor</span><span class="sxs-lookup"><span data-stu-id="47887-147">Gather publisher details</span></span>

<span data-ttu-id="47887-148">Para acessar os dados do editor de um aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="47887-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="47887-149">Encontre um dispositivo da Área de Trabalho Gerenciada da Microsoft no anel de teste que tenha uma política de Modo de Auditoria aplicada.</span><span class="sxs-lookup"><span data-stu-id="47887-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="47887-150">Tente instalar o aplicativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47887-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="47887-151">Abra o Visualizador de Eventos nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47887-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="47887-152">No Visualizador de Eventos, navegue até Logs de Aplicativos e **Serviços\Microsoft\Windows** e selecione **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="47887-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="47887-153">Encontre qualquer **evento 8003** ou **8006** e copie informações do evento:</span><span class="sxs-lookup"><span data-stu-id="47887-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="47887-154">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="47887-154">Application name</span></span> 
    - <span data-ttu-id="47887-155">Versão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="47887-155">Application version</span></span> 
    - <span data-ttu-id="47887-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="47887-156">Description</span></span> 
    - <span data-ttu-id="47887-157">Detalhes do editor (por exemplo: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="47887-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>