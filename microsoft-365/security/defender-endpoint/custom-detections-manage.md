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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165772"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="b5406-104">Exibir e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="b5406-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5406-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b5406-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5406-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b5406-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b5406-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5406-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b5406-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b5406-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b5406-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b5406-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b5406-110">Gerencie suas regras [de detecção personalizadas existentes](custom-detection-rules.md) para garantir que elas estão efetivamente encontrando ameaças e fazendo ações.</span><span class="sxs-lookup"><span data-stu-id="b5406-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="b5406-111">Explore como exibir a lista de regras, verifique suas versões anteriores e revise os alertas disparados.</span><span class="sxs-lookup"><span data-stu-id="b5406-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="b5406-112">Você também pode executar uma regra sob demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="b5406-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b5406-113">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="b5406-113">Required permissions</span></span>

<span data-ttu-id="b5406-114">Para criar ou gerenciar detecções personalizadas, [sua função](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) precisa ter a permissão **gerenciar configurações de** segurança.</span><span class="sxs-lookup"><span data-stu-id="b5406-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="b5406-115">Exibir regras existentes</span><span class="sxs-lookup"><span data-stu-id="b5406-115">View existing rules</span></span>

<span data-ttu-id="b5406-116">Para exibir todas as regras de detecção personalizadas existentes, navegue até **Configurações**  >  **Detecções personalizadas.**</span><span class="sxs-lookup"><span data-stu-id="b5406-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="b5406-117">A página lista todas as regras com as seguintes informações de executar:</span><span class="sxs-lookup"><span data-stu-id="b5406-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="b5406-118">**Última executar**— quando uma regra foi executado pela última vez para verificar se há verificações de consultas e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="b5406-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="b5406-119">**Status da última executar**— se uma regra foi realizada com êxito</span><span class="sxs-lookup"><span data-stu-id="b5406-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="b5406-120">**Próxima executar**— a próxima sequência agendada</span><span class="sxs-lookup"><span data-stu-id="b5406-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="b5406-121">**Status**— se uma regra foi 1ada ou desligada</span><span class="sxs-lookup"><span data-stu-id="b5406-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="b5406-122">Exibir detalhes da regra, modificar regra e executar regra</span><span class="sxs-lookup"><span data-stu-id="b5406-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="b5406-123">Para exibir informações abrangentes sobre uma regra de detecção personalizada, selecione o nome da regra na lista de regras em **Configurações**  >  **Detecções personalizadas.**</span><span class="sxs-lookup"><span data-stu-id="b5406-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="b5406-124">Uma página sobre a regra selecionada exibe as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b5406-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="b5406-125">Informações gerais sobre a regra, incluindo os detalhes do alerta, status de executar e escopo</span><span class="sxs-lookup"><span data-stu-id="b5406-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="b5406-126">Lista de alertas disparados</span><span class="sxs-lookup"><span data-stu-id="b5406-126">List of triggered alerts</span></span>
- <span data-ttu-id="b5406-127">Lista de ações disparadas</span><span class="sxs-lookup"><span data-stu-id="b5406-127">List of triggered actions</span></span>

<span data-ttu-id="b5406-128">![Página de regra de detecção personalizada](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="b5406-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="b5406-129">*Página de regra de detecção personalizada*</span><span class="sxs-lookup"><span data-stu-id="b5406-129">*Custom detection rule page*</span></span>

<span data-ttu-id="b5406-130">Você também pode tomar as seguintes ações na regra nesta página:</span><span class="sxs-lookup"><span data-stu-id="b5406-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="b5406-131">**Executar**— execute a regra imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b5406-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="b5406-132">Essa ação também redefine o intervalo para a próxima executar.</span><span class="sxs-lookup"><span data-stu-id="b5406-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="b5406-133">**Editar**— modificar a regra sem alterar a consulta</span><span class="sxs-lookup"><span data-stu-id="b5406-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="b5406-134">**Modificar consulta —** editar a consulta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="b5406-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="b5406-135">**Ativar**  /  **Desativar —** habilitar a regra ou impedi-la de executar</span><span class="sxs-lookup"><span data-stu-id="b5406-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="b5406-136">**Excluir**— desativar a regra e removê-la</span><span class="sxs-lookup"><span data-stu-id="b5406-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="b5406-137">Para exibir rapidamente informações e tomar medidas em um item em uma tabela, use a coluna de seleção [&#10003;] à esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="b5406-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5406-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b5406-138">Related topics</span></span>
- [<span data-ttu-id="b5406-139">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="b5406-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="b5406-140">Criar regras de detecção</span><span class="sxs-lookup"><span data-stu-id="b5406-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="b5406-141">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b5406-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b5406-142">Exibir e organizar alertas</span><span class="sxs-lookup"><span data-stu-id="b5406-142">View and organize alerts</span></span>](alerts-queue.md)
