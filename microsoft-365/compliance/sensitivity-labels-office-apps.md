---
title: Como os rótulos de confidencialidade funcionam nos aplicativos do Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Com os rótulos de confidencialidade, você pode classificar e ajudar a proteger seu conteúdo confidencial, garantindo ao mesmo tempo que a produtividade e a capacidade de colaboração de seu pessoal não sejam prejudicadas. Você pode usar rótulos de confidencialidade para impor configurações de proteção, como criptografia ou marcas d'água em conteúdo rotulado.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417560"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="460b4-104">Como os rótulos de confidencialidade funcionam nos aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="460b4-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="460b4-105">Quais pré-requisitos existem para usar rótulos de confidencialidade nos aplicativos do Office?</span><span class="sxs-lookup"><span data-stu-id="460b4-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="460b4-106">Requisitos comuns</span><span class="sxs-lookup"><span data-stu-id="460b4-106">Common requirements</span></span> 

- <span data-ttu-id="460b4-107">Rótulos de confidencialidade unificados devem ser [configurados e publicados no Centro de conformidade e segurança](https://aka.ms/managemip)</span><span class="sxs-lookup"><span data-stu-id="460b4-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="460b4-108">Os usuários devem estar conectados ao Office com suas contas profissionais.</span><span class="sxs-lookup"><span data-stu-id="460b4-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="460b4-109">Os usuários devem ter uma licença do Office 365 E3 ou superior atribuída.</span><span class="sxs-lookup"><span data-stu-id="460b4-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="460b4-110">Requisitos adicionais para o Office para Windows</span><span class="sxs-lookup"><span data-stu-id="460b4-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="460b4-111">O cliente da Proteção de Informações do Azure não deve estar em execução no Office.</span><span class="sxs-lookup"><span data-stu-id="460b4-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="460b4-112">Confira também: [Os rótulos de confidencialidade podem ser executados juntamente com o cliente da Proteção de Informações do Azure no Office para Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span><span class="sxs-lookup"><span data-stu-id="460b4-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="460b4-113">Requisitos adicionais para o Outlook em todas as plataformas</span><span class="sxs-lookup"><span data-stu-id="460b4-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="460b4-114">Na sua configuração de rótulo, se você ativar a marcação de conteúdo, deverá estar usando o Exchange Online para que a marcação de conteúdo seja inserida em trânsito.</span><span class="sxs-lookup"><span data-stu-id="460b4-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="460b4-115">Quais recursos de rótulos de confidencialidade são compatíveis com o Office hoje?</span><span class="sxs-lookup"><span data-stu-id="460b4-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="460b4-116"><font size="-1">Recurso</span><span class="sxs-lookup"><span data-stu-id="460b4-116"><font size="-1">Capability</span></span><th><span data-ttu-id="460b4-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="460b4-117"><font size="-1">Windows</span></span><th><span data-ttu-id="460b4-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="460b4-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="460b4-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="460b4-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="460b4-120">Excel</span><span class="sxs-lookup"><span data-stu-id="460b4-120">Excel</span></span><br>
<span data-ttu-id="460b4-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="460b4-121">PowerPoint</span></span><br>
<span data-ttu-id="460b4-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="460b4-122">Outlook</span></span>


<td><span data-ttu-id="460b4-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="460b4-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="460b4-124">Excel</span><span class="sxs-lookup"><span data-stu-id="460b4-124">Excel</span></span><br>
<span data-ttu-id="460b4-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="460b4-125">PowerPoint</span></span><br>
<span data-ttu-id="460b4-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="460b4-126">Outlook</span></span>

<td><span data-ttu-id="460b4-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="460b4-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="460b4-128">Excel</span><span class="sxs-lookup"><span data-stu-id="460b4-128">Excel</span></span><br>
<span data-ttu-id="460b4-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="460b4-129">PowerPoint</span></span>
<td><span data-ttu-id="460b4-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="460b4-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="460b4-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="460b4-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="460b4-132">Excel</span><span class="sxs-lookup"><span data-stu-id="460b4-132">Excel</span></span><br>
<span data-ttu-id="460b4-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="460b4-133">PowerPoint</span></span>
<td><span data-ttu-id="460b4-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="460b4-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="460b4-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="460b4-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="460b4-136">Excel</span><span class="sxs-lookup"><span data-stu-id="460b4-136">Excel</span></span><br>
<span data-ttu-id="460b4-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="460b4-137">PowerPoint</span></span>
<td><span data-ttu-id="460b4-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="460b4-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="460b4-139"><font size="-1">Aplicar, alterar ou remover rótulos manualmente</span><span class="sxs-lookup"><span data-stu-id="460b4-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="460b4-140"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-142"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="460b4-144"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="460b4-146"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-147"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="460b4-149"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-150"><font size="-1">Em breve<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="460b4-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="460b4-151"><font size="-1">Em breve<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="460b4-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="460b4-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Aplicar um rótulo padrão</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="460b4-153"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-155"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="460b4-157"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="460b4-159"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-160"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="460b4-162"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-163"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-164"><font size="-1">Em breve<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="460b4-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="460b4-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Exigir uma justificativa para alterar um rótulo</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="460b4-166"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-168"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="460b4-170"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="460b4-172"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-173"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="460b4-175"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-176"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-177"><font size="-1">Em breve<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="460b4-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="460b4-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Fornecer um link de ajuda para uma página de ajuda personalizada</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="460b4-179"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-181"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="460b4-183"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="460b4-185"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-186"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="460b4-188"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-189"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-190"><font size="-1">Em breve<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="460b4-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="460b4-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Marcar o conteúdo</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="460b4-192"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-194"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="460b4-196"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="460b4-198"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-199"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="460b4-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="460b4-201"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-202"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-203"><font size="-1">Em breve<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="460b4-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="460b4-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Atribuir permissões predefinidas</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="460b4-205"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-207"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="460b4-209"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="460b4-211"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-212"><font size="-1"><b>Sim</b></span><span class="sxs-lookup"><span data-stu-id="460b4-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="460b4-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="460b4-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="460b4-214"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-215"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-216"><font size="-1">Em breve<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="460b4-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="460b4-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Permitir que os usuários atribuam permissões</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="460b4-218"><font size="-1"><b>Sim</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="460b4-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="460b4-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="460b4-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="460b4-220"><font size="-1"><b>Sim</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="460b4-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="460b4-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="460b4-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="460b4-222"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-223"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-224"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="460b4-225"><font size="-1">Em breve<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="460b4-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="460b4-226"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-227"><font size="-1">Em breve<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="460b4-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="460b4-228"><font size="-1">Enviar dados de <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">análise de rótulos</a> para administradores</span><span class="sxs-lookup"><span data-stu-id="460b4-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="460b4-229"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="460b4-230"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="460b4-231"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-232"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-233"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-234"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-235"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-236"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="460b4-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Exigir que os usuários apliquem um rótulo a seus emails e documentos</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="460b4-238"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="460b4-239"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="460b4-240"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-241"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-242"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-243"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-244"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-245"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="460b4-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Aplicar um rótulo de confidencialidade ao conteúdo automaticamente</a>
</span><span class="sxs-lookup"><span data-stu-id="460b4-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="460b4-247"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="460b4-248"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="460b4-249"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-250"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-251"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-252"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-253"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="460b4-254"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="460b4-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="460b4-255"><sup>1</sup>Se configurado, os usuários serão solicitados a justificar os downgrades de rótulos.</span><span class="sxs-lookup"><span data-stu-id="460b4-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="460b4-256">No entanto, os dados de justificativa ainda não estão disponíveis para administradores.</span><span class="sxs-lookup"><span data-stu-id="460b4-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="460b4-257">Eles ficarão disponíveis quando o recurso "enviar dados de análise de rótulos para administradores" for suportado.</span><span class="sxs-lookup"><span data-stu-id="460b4-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="460b4-258"><sup>2</sup>No momento, permitir que os usuários atribuam permissões está disponível apenas no Outlook para Windows e Mac.</span><span class="sxs-lookup"><span data-stu-id="460b4-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="460b4-259">A disponibilidade para Word, Excel e PowerPoint ainda não foi definida.</span><span class="sxs-lookup"><span data-stu-id="460b4-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="460b4-260"><sup>3</sup>T4 esperado do ano civil de 2019.</span><span class="sxs-lookup"><span data-stu-id="460b4-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="460b4-261">Quando marcas de conteúdo ou criptografia são aplicadas depois que o conteúdo recebe um rótulo de confidencialidade?</span><span class="sxs-lookup"><span data-stu-id="460b4-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="460b4-262">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="460b4-262">Application</span></span> | <span data-ttu-id="460b4-263">Marcação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="460b4-263">Content marking</span></span> | <span data-ttu-id="460b4-264">Criptografia</span><span class="sxs-lookup"><span data-stu-id="460b4-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="460b4-265">Word, Excel, PowerPoint em todas as plataformas</span><span class="sxs-lookup"><span data-stu-id="460b4-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="460b4-266">Imediatamente</span><span class="sxs-lookup"><span data-stu-id="460b4-266">Immediately</span></span> | <span data-ttu-id="460b4-267">Imediatamente</span><span class="sxs-lookup"><span data-stu-id="460b4-267">Immediately</span></span> |
| <span data-ttu-id="460b4-268">Outlook para PC e Mac</span><span class="sxs-lookup"><span data-stu-id="460b4-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="460b4-269">Após o email ser enviado pelo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="460b4-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="460b4-270">Imediatamente</span><span class="sxs-lookup"><span data-stu-id="460b4-270">Immediately</span></span> |
| <span data-ttu-id="460b4-271">Outlook na Web, iOS e Android</span><span class="sxs-lookup"><span data-stu-id="460b4-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="460b4-272">Após o email ser enviado pelo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="460b4-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="460b4-273">Após o email ser enviado pelo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="460b4-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="460b4-274">Os rótulos de confidencialidade podem ser executados juntamente com o cliente da Proteção de Informações do Azure no Office para Windows?</span><span class="sxs-lookup"><span data-stu-id="460b4-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="460b4-275">Não.</span><span class="sxs-lookup"><span data-stu-id="460b4-275">No.</span></span> <span data-ttu-id="460b4-276">Os rótulos de confidencialidade serão desativados se o cliente da Proteção de Informações do Azure estiver carregado no Office para Windows.</span><span class="sxs-lookup"><span data-stu-id="460b4-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="460b4-277">Se você tiver o cliente da Proteção de Informações do Azure instalado, mas desejar usar rótulos de confidencialidade, poderá:</span><span class="sxs-lookup"><span data-stu-id="460b4-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="460b4-278">Configurar a configuração de Diretiva de Grupo  **Usar o recurso Confidencialidade no Office para aplicar e exibir rótulos de confidencialidade**, que pode ser encontrada em **Configuração do Usuário/Modelos Administrativos/Microsoft Office 2016/Configurações de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="460b4-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="460b4-279">Nota: essa configuração pode ser implantada por meio de mecanismos tradicionais de implantação de política de grupo ou pelo [serviço de política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span><span class="sxs-lookup"><span data-stu-id="460b4-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="460b4-280">Como alternativa, você pode desinstalar ou  [desabilitar](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) o cliente da Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="460b4-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="460b4-281">Reinicie todos os aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="460b4-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="460b4-282">Os rótulos de confidencialidade serão compatíveis com as versões sem assinatura do Office, como o Office 2016 ou o Office 2019?</span><span class="sxs-lookup"><span data-stu-id="460b4-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="460b4-283">Não.</span><span class="sxs-lookup"><span data-stu-id="460b4-283">No.</span></span> <span data-ttu-id="460b4-284">Os rótulos de confidencialidade serão compatíveis apenas com a assinatura do Office 365, e não serão compatíveis com nenhuma versão que não seja de assinatura.</span><span class="sxs-lookup"><span data-stu-id="460b4-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="460b4-285">No entanto, o cliente de rotulagem unificada da Proteção de Informações do Azure pode ser usado em versões sem assinatura do Office.</span><span class="sxs-lookup"><span data-stu-id="460b4-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="460b4-286">Implantei anteriormente modelos de proteção antes de configurar rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="460b4-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="460b4-287">Para onde eles foram?</span><span class="sxs-lookup"><span data-stu-id="460b4-287">Where did they go?</span></span>

<span data-ttu-id="460b4-288">Os [modelos de proteção](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definidos pelo administrador ficam ocultos da experiência do usuário do Office quando os rótulos de confidencialidade são ativados porque são redundantes com os rótulos de confidencialidade com criptografia ativada.</span><span class="sxs-lookup"><span data-stu-id="460b4-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="460b4-289">Um arquivo ou email pode ter mais de uma classificação?</span><span class="sxs-lookup"><span data-stu-id="460b4-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="460b4-290">Não.</span><span class="sxs-lookup"><span data-stu-id="460b4-290">No.</span></span> <span data-ttu-id="460b4-291">Os usuários podem selecionar apenas um rótulo de cada vez para cada documento ou email.</span><span class="sxs-lookup"><span data-stu-id="460b4-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="460b4-292">Quando um email é rotulado, os anexos recebem automaticamente a mesma rotulagem?</span><span class="sxs-lookup"><span data-stu-id="460b4-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="460b4-293">Não.</span><span class="sxs-lookup"><span data-stu-id="460b4-293">No.</span></span> <span data-ttu-id="460b4-294">Quando você rotula uma mensagem de email com anexos, esses anexos não herdam o mesmo rótulo.</span><span class="sxs-lookup"><span data-stu-id="460b4-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="460b4-295">Os anexos permanecem sem rótulo ou retêm um rótulo aplicado separadamente.</span><span class="sxs-lookup"><span data-stu-id="460b4-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="460b4-296">No entanto, se o rótulo do email aplicar proteção, essa proteção será aplicada aos anexos do Office.</span><span class="sxs-lookup"><span data-stu-id="460b4-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="460b4-297">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="460b4-297">Additional resources</span></span>

[<span data-ttu-id="460b4-298">Perguntas frequentes sobre classificação e rotulagem na Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="460b4-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="460b4-299">Aplicar rótulos de confidencialidade aos seus documentos e email no Office</span><span class="sxs-lookup"><span data-stu-id="460b4-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
