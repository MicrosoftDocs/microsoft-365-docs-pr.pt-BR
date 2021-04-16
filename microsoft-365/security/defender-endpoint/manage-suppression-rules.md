---
title: Gerenciar regras de supressão do Microsoft Defender para Pontos de Extremidade
description: Talvez seja necessário impedir que alertas apareçam no portal usando regras de supressão. Saiba como gerenciar suas regras de supressão no Microsoft Defender para Ponto de Extremidade.
keywords: gerenciar supressão, regras, nome da regra, escopo, ação, alertas, ativar, desativar
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
ms.openlocfilehash: f1549512a02fe3af71d32c6b33c69cc705de99a8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862122"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="d0e5a-105">Gerenciar regras de supressão</span><span class="sxs-lookup"><span data-stu-id="d0e5a-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d0e5a-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d0e5a-106">**Applies to:**</span></span>
- [<span data-ttu-id="d0e5a-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d0e5a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0e5a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0e5a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d0e5a-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d0e5a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d0e5a-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="d0e5a-111">Pode haver cenários em que você precisa suprimir alertas de aparecer no portal.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="d0e5a-112">Você pode criar regras de supressão para alertas específicos conhecidos como ferramentas ou processos conhecidos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="d0e5a-113">Para obter mais informações sobre como suprimir alertas, consulte [Suppress alerts](manage-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="d0e5a-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="d0e5a-114">Você pode exibir uma lista de todas as regras de supressão e gerenciá-las em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="d0e5a-115">Você também pode ativar ou desativar uma regra de supressão de alerta.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="d0e5a-116">No painel de navegação, selecione **Configurações**  >  **Supressão de alerta**.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="d0e5a-117">A lista de regras de supressão criadas pelos usuários em sua organização é exibida.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="d0e5a-118">Selecione uma regra clicando na caixa de seleção ao lado do nome da regra.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="d0e5a-119">Clique **em Ativar regra,** **Editar regra** ou Excluir  **regra**.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="d0e5a-120">Ao fazer alterações em uma regra, você pode optar por liberar alertas que já foram suprimidos, independentemente de esses alertas corresponderem ou não aos novos critérios.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="d0e5a-121">Exibir detalhes de uma regra de supressão</span><span class="sxs-lookup"><span data-stu-id="d0e5a-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="d0e5a-122">No painel de navegação, selecione **Configurações**  >  **Supressão de alerta**.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="d0e5a-123">A lista de regras de supressão criadas pelos usuários em sua organização é exibida.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="d0e5a-124">Clique em um nome de regra.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-124">Click on a rule name.</span></span> <span data-ttu-id="d0e5a-125">Os detalhes da regra são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-125">Details of the rule is displayed.</span></span> <span data-ttu-id="d0e5a-126">Você verá os detalhes da regra, como status, escopo, ação, número de alertas correspondentes, criado por e data quando a regra foi criada.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="d0e5a-127">Você também pode exibir alertas associados e as condições de regra.</span><span class="sxs-lookup"><span data-stu-id="d0e5a-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0e5a-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d0e5a-128">Related topics</span></span>

- [<span data-ttu-id="d0e5a-129">Gerenciar alertas</span><span class="sxs-lookup"><span data-stu-id="d0e5a-129">Manage alerts</span></span>](manage-alerts.md)
