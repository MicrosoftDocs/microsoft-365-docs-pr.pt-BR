---
title: Exibir e gerenciar regras de detecção personalizadas no Microsoft Defender ATP
ms.reviewer: ''
description: Saiba como exibir e gerenciar regras de detecção personalizadas
keywords: detecções personalizadas, exibir, gerenciar, alertas, editar, executar sob demanda, regras de detecção, busca avançada, busca, consulta, ações de resposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498751"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="2a898-104">Exibir e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="2a898-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a898-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2a898-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a898-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a898-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a898-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a898-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2a898-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2a898-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2a898-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2a898-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2a898-110">Gerencie suas regras [de detecção personalizadas existentes](custom-detection-rules.md) para garantir que elas estão efetivamente encontrando ameaças e fazendo ações.</span><span class="sxs-lookup"><span data-stu-id="2a898-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="2a898-111">Explore como exibir a lista de regras, verifique suas versões anteriores e revise os alertas disparados.</span><span class="sxs-lookup"><span data-stu-id="2a898-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="2a898-112">Você também pode executar uma regra sob demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="2a898-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2a898-113">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="2a898-113">Required permissions</span></span>

<span data-ttu-id="2a898-114">Para criar ou gerenciar detecções personalizadas, [sua função](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) precisa ter a permissão **gerenciar configurações de** segurança.</span><span class="sxs-lookup"><span data-stu-id="2a898-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="2a898-115">Exibir regras existentes</span><span class="sxs-lookup"><span data-stu-id="2a898-115">View existing rules</span></span>

<span data-ttu-id="2a898-116">Para exibir todas as regras de detecção personalizadas existentes, navegue até **Configurações**  >  **Detecções personalizadas.**</span><span class="sxs-lookup"><span data-stu-id="2a898-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="2a898-117">A página lista todas as regras com as seguintes informações de executar:</span><span class="sxs-lookup"><span data-stu-id="2a898-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="2a898-118">**Última executar**— quando uma regra foi executado pela última vez para verificar se há verificações de consultas e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="2a898-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="2a898-119">**Status da última executar**— se uma regra foi realizada com êxito</span><span class="sxs-lookup"><span data-stu-id="2a898-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="2a898-120">**Próxima executar**— a próxima sequência agendada</span><span class="sxs-lookup"><span data-stu-id="2a898-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="2a898-121">**Status**— se uma regra foi 1ada ou desligada</span><span class="sxs-lookup"><span data-stu-id="2a898-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="2a898-122">Exibir detalhes da regra, modificar regra e executar regra</span><span class="sxs-lookup"><span data-stu-id="2a898-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="2a898-123">Para exibir informações abrangentes sobre uma regra de detecção personalizada, selecione o nome da regra na lista de regras em **Configurações**  >  **Detecções personalizadas.**</span><span class="sxs-lookup"><span data-stu-id="2a898-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="2a898-124">Uma página sobre a regra selecionada exibe as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="2a898-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="2a898-125">Informações gerais sobre a regra, incluindo os detalhes do alerta, status de executar e escopo</span><span class="sxs-lookup"><span data-stu-id="2a898-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="2a898-126">Lista de alertas disparados</span><span class="sxs-lookup"><span data-stu-id="2a898-126">List of triggered alerts</span></span>
- <span data-ttu-id="2a898-127">Lista de ações disparadas</span><span class="sxs-lookup"><span data-stu-id="2a898-127">List of triggered actions</span></span>

<span data-ttu-id="2a898-128">![Página de regra de detecção personalizada](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="2a898-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="2a898-129">*Página de regra de detecção personalizada*</span><span class="sxs-lookup"><span data-stu-id="2a898-129">*Custom detection rule page*</span></span>

<span data-ttu-id="2a898-130">Você também pode tomar as seguintes ações na regra nesta página:</span><span class="sxs-lookup"><span data-stu-id="2a898-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="2a898-131">**Executar**— execute a regra imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2a898-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="2a898-132">Essa ação também redefine o intervalo para a próxima executar.</span><span class="sxs-lookup"><span data-stu-id="2a898-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="2a898-133">**Editar**— modificar a regra sem alterar a consulta</span><span class="sxs-lookup"><span data-stu-id="2a898-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="2a898-134">**Modificar consulta —** editar a consulta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="2a898-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="2a898-135">**Ativar**  /  **Desativar —** habilitar a regra ou impedi-la de executar</span><span class="sxs-lookup"><span data-stu-id="2a898-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="2a898-136">**Excluir**— desativar a regra e removê-la</span><span class="sxs-lookup"><span data-stu-id="2a898-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="2a898-137">Para exibir rapidamente informações e tomar medidas em um item em uma tabela, use a coluna de seleção [&#10003;] à esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="2a898-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a898-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2a898-138">Related topics</span></span>
- [<span data-ttu-id="2a898-139">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="2a898-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="2a898-140">Criar regras de detecção</span><span class="sxs-lookup"><span data-stu-id="2a898-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="2a898-141">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="2a898-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a898-142">Exibir e organizar alertas</span><span class="sxs-lookup"><span data-stu-id="2a898-142">View and organize alerts</span></span>](alerts-queue.md)
