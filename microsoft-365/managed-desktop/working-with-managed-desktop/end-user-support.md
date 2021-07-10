---
title: Obter suporte do usuário para Área de Trabalho Gerenciada da Microsoft
description: Como os usuários podem obter ajuda com o serviço e dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362601"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="14cd6-104">Obter ajuda para usuários</span><span class="sxs-lookup"><span data-stu-id="14cd6-104">Getting help for users</span></span>

<span data-ttu-id="14cd6-105">Se você atingiu o ponto [](../service-description/user-support.md) no fluxo de trabalho em que precisa solicitar acesso ou escalonamento de dispositivos elevados para a Microsoft, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="14cd6-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="14cd6-106">Essas opções de suporte não estão disponíveis para dispositivos no grupo Teste.</span><span class="sxs-lookup"><span data-stu-id="14cd6-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="14cd6-107">Solicitações de elevação</span><span class="sxs-lookup"><span data-stu-id="14cd6-107">Elevation requests</span></span>

<span data-ttu-id="14cd6-108">Antes de solicitar acesso elevado a um dispositivo, é melhor revisar quais ações são mais adequadas.</span><span class="sxs-lookup"><span data-stu-id="14cd6-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="14cd6-109">**As ações típicas** são para as quais esse processo se destina e seria executado rotineiramente durante a solução de problemas com Área de Trabalho Gerenciada da Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14cd6-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="14cd6-110">Os exemplos incluem:</span><span class="sxs-lookup"><span data-stu-id="14cd6-110">Examples include:</span></span>
    - <span data-ttu-id="14cd6-111">Elevar os solução de problemas do sistema integrado, o prompt de comando ou Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14cd6-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="14cd6-112">Solução de problemas de aplicativos de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="14cd6-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="14cd6-113">Usar uma solução alternativa para corrigir algo que deve funcionar pelo design (como a ativação do BitLocker ou o tempo do sistema não atualizando)</span><span class="sxs-lookup"><span data-stu-id="14cd6-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="14cd6-114">Elevar o Gerenciador de Dispositivos para fazer coisas como atualizar drivers, desinstalar um dispositivo ou verificar novas alterações</span><span class="sxs-lookup"><span data-stu-id="14cd6-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="14cd6-115">**As ações que não são recomendadas** incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="14cd6-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="14cd6-116">Instalar softwares ou navegadores</span><span class="sxs-lookup"><span data-stu-id="14cd6-116">Installing software or browsers</span></span>
    - <span data-ttu-id="14cd6-117">Instalar drivers fora das configurações Windows, incluindo os para periféricos</span><span class="sxs-lookup"><span data-stu-id="14cd6-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="14cd6-118">Instalando .msi ou .exe arquivos</span><span class="sxs-lookup"><span data-stu-id="14cd6-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="14cd6-119">Instalando Windows recursos</span><span class="sxs-lookup"><span data-stu-id="14cd6-119">Installing Windows features</span></span>

- <span data-ttu-id="14cd6-120">**As ações que não são suportadas** incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="14cd6-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="14cd6-121">Instalar softwares ou recursos que conflitam com Área de Trabalho Gerenciada da Microsoft ou operações de gerenciamento ou segurança</span><span class="sxs-lookup"><span data-stu-id="14cd6-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="14cd6-122">Desabilitar um recurso Windows que é necessário para Área de Trabalho Gerenciada da Microsoft, como o BitLocker</span><span class="sxs-lookup"><span data-stu-id="14cd6-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="14cd6-123">Modificando configurações gerenciadas por sua organização</span><span class="sxs-lookup"><span data-stu-id="14cd6-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="14cd6-124">Para solicitar elevação</span><span class="sxs-lookup"><span data-stu-id="14cd6-124">To request elevation</span></span>

1. <span data-ttu-id="14cd6-125">Vá para o portal em [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e entre com suas credenciais Azure Active Directory de usuário.</span><span class="sxs-lookup"><span data-stu-id="14cd6-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="14cd6-126">Selecione **Nova solicitação de elevação**.</span><span class="sxs-lookup"><span data-stu-id="14cd6-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="14cd6-127">Forneça estes detalhes:</span><span class="sxs-lookup"><span data-stu-id="14cd6-127">Provide these details:</span></span>
    - <span data-ttu-id="14cd6-128">**ID do tíquete de** suporte do seu próprio sistema de tíquetes de suporte.</span><span class="sxs-lookup"><span data-stu-id="14cd6-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="14cd6-129">**Nome do** dispositivo : insira o número de série do dispositivo e selecione o dispositivo no menu.</span><span class="sxs-lookup"><span data-stu-id="14cd6-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="14cd6-130">**Categoria**: selecione a categoria que melhor se ajusta ao seu problema.</span><span class="sxs-lookup"><span data-stu-id="14cd6-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="14cd6-131">Se nenhuma opção parecer próxima, selecione **Outro** e forneça mais informações nos campos **Título** e **Plano de ação.**</span><span class="sxs-lookup"><span data-stu-id="14cd6-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="14cd6-132">É melhor selecionar uma categoria, se possível.</span><span class="sxs-lookup"><span data-stu-id="14cd6-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="14cd6-133">**Subcategoria**: selecione o que melhor se encaixa no problema.</span><span class="sxs-lookup"><span data-stu-id="14cd6-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="14cd6-134">Se nenhuma opção parecer próxima, selecione **Outro** e forneça uma breve descrição em **Title**.</span><span class="sxs-lookup"><span data-stu-id="14cd6-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="14cd6-135">Em **Plano de ação,** forneça as etapas de solução de problemas que você planeja tomar depois que a elevação for concedida.</span><span class="sxs-lookup"><span data-stu-id="14cd6-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="14cd6-136">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="14cd6-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="14cd6-137">Solicitações de escalonamento</span><span class="sxs-lookup"><span data-stu-id="14cd6-137">Escalation requests</span></span>


<span data-ttu-id="14cd6-138">Se você precisar [escalar um](../service-description/user-support.md#escalation-portal) problema para a Microsoft, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="14cd6-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="14cd6-139">Vá para o portal em [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e entre com suas credenciais Azure Active Directory de usuário.</span><span class="sxs-lookup"><span data-stu-id="14cd6-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="14cd6-140">Selecione **Solicitações de Escalonamento** e selecione **Nova solicitação de escalonamento.**</span><span class="sxs-lookup"><span data-stu-id="14cd6-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="14cd6-141">Forneça estes detalhes:</span><span class="sxs-lookup"><span data-stu-id="14cd6-141">Provide these details:</span></span>
    - <span data-ttu-id="14cd6-142">**Categoria**: selecione a categoria que melhor se ajusta ao seu problema.</span><span class="sxs-lookup"><span data-stu-id="14cd6-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="14cd6-143">**Título:** forneça uma descrição muito breve.</span><span class="sxs-lookup"><span data-stu-id="14cd6-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="14cd6-144">**Descrição**: adicione quaisquer detalhes adicionais que podem ajudar nossa equipe a entender o problema.</span><span class="sxs-lookup"><span data-stu-id="14cd6-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="14cd6-145">Se precisar anexar arquivos, você pode fazer isso voltando à solicitação depois de enviar.</span><span class="sxs-lookup"><span data-stu-id="14cd6-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="14cd6-146">**Principais informações de contato**: Forneça informações sobre como entrar em contato com a principal pessoa responsável por trabalhar com nossa equipe.</span><span class="sxs-lookup"><span data-stu-id="14cd6-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="14cd6-147">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="14cd6-147">Select **Submit**.</span></span>
5. <span data-ttu-id="14cd6-148">Revisite o tíquete no mesmo portal para interagir com nossa equipe.</span><span class="sxs-lookup"><span data-stu-id="14cd6-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="14cd6-149">Somente problemas de Severidade C podem ser escalonados por esse caminho.</span><span class="sxs-lookup"><span data-stu-id="14cd6-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="14cd6-150">Para outros problemas, contate o administrador de IT para arquivar a solicitação por meio do portal de administração.</span><span class="sxs-lookup"><span data-stu-id="14cd6-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>