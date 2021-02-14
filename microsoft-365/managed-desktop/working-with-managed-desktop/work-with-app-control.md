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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289454"
---
# <a name="work-with-app-control"></a><span data-ttu-id="8d77f-103">Trabalhar com o controle de aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d77f-103">Work with app control</span></span>

<span data-ttu-id="8d77f-104">Depois que o controle de aplicativo tiver sido implantado em seu ambiente, você e as Operações de Área de Trabalho Gerenciada da Microsoft terão responsabilidades contínuas.</span><span class="sxs-lookup"><span data-stu-id="8d77f-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="8d77f-105">Por exemplo, talvez você queira adicionar um novo aplicativo no ambiente ou adicionar (ou remover) um signante confiável.</span><span class="sxs-lookup"><span data-stu-id="8d77f-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="8d77f-106">Para melhorar a segurança, todos os aplicativos devem ser assinados por código antes de liberá-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8d77f-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="8d77f-107">Os detalhes do editor de um aplicativo incluem informações sobre o signante.</span><span class="sxs-lookup"><span data-stu-id="8d77f-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="8d77f-108">Adicionar um novo aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d77f-108">Add a new app</span></span>

<span data-ttu-id="8d77f-109">Para adicionar um novo aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8d77f-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="8d77f-110">Adicione o aplicativo ao [Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="8d77f-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="8d77f-111">Implante o aplicativo em qualquer dispositivo no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="8d77f-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="8d77f-112">Teste seu aplicativo de acordo com seus processos empresariais padrão.</span><span class="sxs-lookup"><span data-stu-id="8d77f-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="8d77f-113">Verifique o Visualizador de Eventos em Logs de Aplicativos e **Serviços\Microsoft\Windows\AppLocker**, procurando eventos **8003** ou **8006.**</span><span class="sxs-lookup"><span data-stu-id="8d77f-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="8d77f-114">Esses eventos indicam que o aplicativo seria bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8d77f-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="8d77f-115">Para obter mais informações sobre todos os eventos do App Locker e seus significados, consulte Usando o Visualizador de [Eventos com o AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)</span><span class="sxs-lookup"><span data-stu-id="8d77f-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="8d77f-116">Se você encontrar qualquer um desses eventos, abra uma solicitação de signante com as Operações da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d77f-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="8d77f-117">Adicionar (ou remover) um signante confiável</span><span class="sxs-lookup"><span data-stu-id="8d77f-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="8d77f-118">Ao abrir uma solicitação de signante, você precisará primeiro fornecer alguns detalhes importantes do editor.</span><span class="sxs-lookup"><span data-stu-id="8d77f-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="8d77f-119">Em seguida, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8d77f-119">Then follow these steps:</span></span>

1. <span data-ttu-id="8d77f-120">[Coletar detalhes do editor.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="8d77f-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="8d77f-121">Abra um tíquete com as Operações da Área de Trabalho Gerenciada da Microsoft para solicitar a regra signante e inclua os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="8d77f-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="8d77f-122">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d77f-122">Application name</span></span> 
    - <span data-ttu-id="8d77f-123">Versão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d77f-123">Application version</span></span> 
    - <span data-ttu-id="8d77f-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d77f-124">Description</span></span> 
    - <span data-ttu-id="8d77f-125">Tipo de alteração ("adicionar" ou "remover")</span><span class="sxs-lookup"><span data-stu-id="8d77f-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="8d77f-126">Detalhes do editor (por exemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="8d77f-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="8d77f-127">Para remover a confiança de um aplicativo, siga as mesmas etapas, mas de acordo **com o tipo de alteração** a ser *removido.*</span><span class="sxs-lookup"><span data-stu-id="8d77f-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="8d77f-128">As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:</span><span class="sxs-lookup"><span data-stu-id="8d77f-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="8d77f-129">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="8d77f-129">Deployment group</span></span>  |<span data-ttu-id="8d77f-130">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="8d77f-130">Policy type</span></span>  |<span data-ttu-id="8d77f-131">Tempo</span><span class="sxs-lookup"><span data-stu-id="8d77f-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8d77f-132">Testar</span><span class="sxs-lookup"><span data-stu-id="8d77f-132">Test</span></span>     |  <span data-ttu-id="8d77f-133">Auditoria</span><span class="sxs-lookup"><span data-stu-id="8d77f-133">Audit</span></span>       |  <span data-ttu-id="8d77f-134">Dia 0</span><span class="sxs-lookup"><span data-stu-id="8d77f-134">Day 0</span></span>       |
|<span data-ttu-id="8d77f-135">Primeiro</span><span class="sxs-lookup"><span data-stu-id="8d77f-135">First</span></span>     | <span data-ttu-id="8d77f-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="8d77f-136">Enforced</span></span>        | <span data-ttu-id="8d77f-137">1º dia</span><span class="sxs-lookup"><span data-stu-id="8d77f-137">Day 1</span></span>        |
|<span data-ttu-id="8d77f-138">Rápida</span><span class="sxs-lookup"><span data-stu-id="8d77f-138">Fast</span></span>     | <span data-ttu-id="8d77f-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="8d77f-139">Enforced</span></span>        |  <span data-ttu-id="8d77f-140">2º dia</span><span class="sxs-lookup"><span data-stu-id="8d77f-140">Day 2</span></span>       |
|<span data-ttu-id="8d77f-141">Amplas</span><span class="sxs-lookup"><span data-stu-id="8d77f-141">Broad</span></span>     | <span data-ttu-id="8d77f-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="8d77f-142">Enforced</span></span>        |  <span data-ttu-id="8d77f-143">3º dia</span><span class="sxs-lookup"><span data-stu-id="8d77f-143">Day 3</span></span>       |


<span data-ttu-id="8d77f-144">Você pode pausar ou reverter a implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="8d77f-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="8d77f-145">Para fazer isso, abra outra solicitação de serviço com o Operations.</span><span class="sxs-lookup"><span data-stu-id="8d77f-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="8d77f-146">Se você pausar o lançamento de uma regra signante, essa regra deverá ser retordenada ou concluída antes que outra liberação possa começar.</span><span class="sxs-lookup"><span data-stu-id="8d77f-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="8d77f-147">Coletar detalhes do editor</span><span class="sxs-lookup"><span data-stu-id="8d77f-147">Gather publisher details</span></span>

<span data-ttu-id="8d77f-148">Para acessar os dados do editor de um aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8d77f-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="8d77f-149">Encontre um dispositivo de Área de Trabalho Gerenciada da Microsoft no anel teste que tenha uma política de Modo de Auditoria aplicada.</span><span class="sxs-lookup"><span data-stu-id="8d77f-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="8d77f-150">Tente instalar o aplicativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d77f-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="8d77f-151">Abra o Visualizador de Eventos nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d77f-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="8d77f-152">No Visualizador de Eventos, navegue até Logs de Aplicativos e **Serviços\Microsoft\Windows** e selecione **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="8d77f-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="8d77f-153">Encontre qualquer **evento 8003** ou **8006** e copie as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="8d77f-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="8d77f-154">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d77f-154">Application name</span></span> 
    - <span data-ttu-id="8d77f-155">Versão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d77f-155">Application version</span></span> 
    - <span data-ttu-id="8d77f-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d77f-156">Description</span></span> 
    - <span data-ttu-id="8d77f-157">Detalhes do editor (por exemplo: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="8d77f-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
