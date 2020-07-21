---
title: Trabalhar com controle de aplicativos
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
ms.openlocfilehash: 74cd1ec93058ed733e7d79da2d6932f04acfa5da
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170680"
---
# <a name="work-with-app-control"></a><span data-ttu-id="a32fd-103">Trabalhar com controle de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a32fd-103">Work with app control</span></span>

<span data-ttu-id="a32fd-104">Depois que o controle de aplicativos é implantado em seu ambiente, você e as operações de área de trabalho gerenciada da Microsoft têm responsabilidades contínuas.</span><span class="sxs-lookup"><span data-stu-id="a32fd-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="a32fd-105">Por exemplo, você pode querer adicionar um novo aplicativo no ambiente ou adicionar (ou remover) um signatário confiável.</span><span class="sxs-lookup"><span data-stu-id="a32fd-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="a32fd-106">Para melhorar a segurança, todos os aplicativos devem ser assinados por código antes de você liberá-los para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="a32fd-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="a32fd-107">Os detalhes do fornecedor do aplicativo incluem informações sobre o Assinante.</span><span class="sxs-lookup"><span data-stu-id="a32fd-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="a32fd-108">Adicionar um novo aplicativo</span><span class="sxs-lookup"><span data-stu-id="a32fd-108">Add a new app</span></span>

<span data-ttu-id="a32fd-109">Para adicionar um novo aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a32fd-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="a32fd-110">Adicione o aplicativo ao [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="a32fd-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="a32fd-111">Implante o aplicativo em qualquer dispositivo no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a32fd-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="a32fd-112">Teste seu aplicativo de acordo com seus processos de negócios padrão.</span><span class="sxs-lookup"><span data-stu-id="a32fd-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="a32fd-113">Verifique o Visualizador de eventos em **aplicativos e serviços Logs\Microsoft\Windows\AppLocker**, procurando qualquer evento **8003** ou **8006** .</span><span class="sxs-lookup"><span data-stu-id="a32fd-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="a32fd-114">Esses eventos indicam que o aplicativo seria bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a32fd-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="a32fd-115">Para obter mais informações sobre todos os eventos do bloqueador de aplicativos e seus significados, consulte [usando o Visualizador de eventos com AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="a32fd-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="a32fd-116">Se você encontrar qualquer um desses eventos, abra uma solicitação de signatário com operações de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a32fd-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="a32fd-117">Adicionar (ou remover) um signatário confiável</span><span class="sxs-lookup"><span data-stu-id="a32fd-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="a32fd-118">Ao abrir uma solicitação de signatário, você precisará fornecer alguns detalhes importantes do Publisher.</span><span class="sxs-lookup"><span data-stu-id="a32fd-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="a32fd-119">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a32fd-119">Then follow these steps:</span></span>

1. <span data-ttu-id="a32fd-120">[Coletar detalhes do editor](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="a32fd-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="a32fd-121">Abra uma permissão com operações de área de trabalho gerenciada da Microsoft para solicitar a regra de signatário e incluir os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="a32fd-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="a32fd-122">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="a32fd-122">Application name</span></span> 
    - <span data-ttu-id="a32fd-123">Versão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="a32fd-123">Application version</span></span> 
    - <span data-ttu-id="a32fd-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="a32fd-124">Description</span></span> 
    - <span data-ttu-id="a32fd-125">Tipo de alteração ("Adicionar" ou "remover")</span><span class="sxs-lookup"><span data-stu-id="a32fd-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="a32fd-126">Detalhes do editor (por exemplo: "O = <publisher name> , L = <location> , S = estado, C = país")</span><span class="sxs-lookup"><span data-stu-id="a32fd-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="a32fd-127">Para remover a confiança de um aplicativo, siga as mesmas etapas, mas defina o **tipo de alteração** como *remover*.</span><span class="sxs-lookup"><span data-stu-id="a32fd-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="a32fd-128">As operações implantarão progressivamente políticas em grupos de implantação seguindo esta programação:</span><span class="sxs-lookup"><span data-stu-id="a32fd-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="a32fd-129">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="a32fd-129">Deployment group</span></span>  |<span data-ttu-id="a32fd-130">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="a32fd-130">Policy type</span></span>  |<span data-ttu-id="a32fd-131">Tempo</span><span class="sxs-lookup"><span data-stu-id="a32fd-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a32fd-132">Testar</span><span class="sxs-lookup"><span data-stu-id="a32fd-132">Test</span></span>     |  <span data-ttu-id="a32fd-133">Auditoria</span><span class="sxs-lookup"><span data-stu-id="a32fd-133">Audit</span></span>       |  <span data-ttu-id="a32fd-134">Dia 0</span><span class="sxs-lookup"><span data-stu-id="a32fd-134">Day 0</span></span>       |
|<span data-ttu-id="a32fd-135">Primeiro</span><span class="sxs-lookup"><span data-stu-id="a32fd-135">First</span></span>     | <span data-ttu-id="a32fd-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="a32fd-136">Enforced</span></span>        | <span data-ttu-id="a32fd-137">1º dia</span><span class="sxs-lookup"><span data-stu-id="a32fd-137">Day 1</span></span>        |
|<span data-ttu-id="a32fd-138">Rápida</span><span class="sxs-lookup"><span data-stu-id="a32fd-138">Fast</span></span>     | <span data-ttu-id="a32fd-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="a32fd-139">Enforced</span></span>        |  <span data-ttu-id="a32fd-140">3º dia</span><span class="sxs-lookup"><span data-stu-id="a32fd-140">Day 3</span></span>       |
|<span data-ttu-id="a32fd-141">Amplas</span><span class="sxs-lookup"><span data-stu-id="a32fd-141">Broad</span></span>     | <span data-ttu-id="a32fd-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="a32fd-142">Enforced</span></span>        |  <span data-ttu-id="a32fd-143">Day 7</span><span class="sxs-lookup"><span data-stu-id="a32fd-143">Day 7</span></span>       |


<span data-ttu-id="a32fd-144">Você pode pausar ou reverter a implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="a32fd-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="a32fd-145">Para fazer isso, abra outra solicitação de serviço com operações.</span><span class="sxs-lookup"><span data-stu-id="a32fd-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="a32fd-146">Se você pausar o lançamento de uma regra de signatário, essa regra deverá ser revertida ou concluída para que outra distribuição possa ser iniciada.</span><span class="sxs-lookup"><span data-stu-id="a32fd-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="a32fd-147">Coletar detalhes do editor</span><span class="sxs-lookup"><span data-stu-id="a32fd-147">Gather publisher details</span></span>

<span data-ttu-id="a32fd-148">Para acessar os dados do editor de um aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a32fd-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="a32fd-149">Encontre um dispositivo de área de trabalho gerenciada da Microsoft no anel de teste que tem uma política de modo de auditoria aplicada.</span><span class="sxs-lookup"><span data-stu-id="a32fd-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="a32fd-150">Tente instalar o aplicativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a32fd-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="a32fd-151">Abra o Visualizador de eventos nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a32fd-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="a32fd-152">No Visualizador de eventos, navegue até **aplicativo e serviços Logs\Microsoft\Windows**e, em seguida, selecione **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="a32fd-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="a32fd-153">Encontre qualquer evento **8003** ou **8006** e, em seguida, copie informações do evento:</span><span class="sxs-lookup"><span data-stu-id="a32fd-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="a32fd-154">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="a32fd-154">Application name</span></span> 
    - <span data-ttu-id="a32fd-155">Versão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="a32fd-155">Application version</span></span> 
    - <span data-ttu-id="a32fd-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="a32fd-156">Description</span></span> 
    - <span data-ttu-id="a32fd-157">Detalhes do editor (por exemplo: "O = <publisher name> , L = <location> , S = estado, C = país")</span><span class="sxs-lookup"><span data-stu-id="a32fd-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 