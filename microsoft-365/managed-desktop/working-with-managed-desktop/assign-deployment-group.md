---
title: Atribuir dispositivos a um grupo de implantação
description: Como especificar em qual grupo de implantação você deseja que os dispositivos sejam
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985511"
---
# <a name="assign-devices-to-a-deployment-group"></a><span data-ttu-id="f512c-104">Atribuir dispositivos a um grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="f512c-104">Assign devices to a deployment group</span></span>

<span data-ttu-id="f512c-105">Área de Trabalho Gerenciada da Microsoft atribuirá dispositivos aos vários grupos de implantação, mas você pode especificar ou alterar o grupo que um dispositivo é atribuído a um dispositivo usando o portal de administração.</span><span class="sxs-lookup"><span data-stu-id="f512c-105">Microsoft Managed Desktop will assign devices to the various deployment groups, but you can specify or change group a device is assigned to a device by using the Admin portal.</span></span> <span data-ttu-id="f512c-106">Você altera a atribuição depois que um dispositivo é registrado ou depois que um usuário se registra.</span><span class="sxs-lookup"><span data-stu-id="f512c-106">You change the assignment after a device is registered or after a user has enrolled.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f512c-107">Se você alterar a atribuição, as políticas específicas desse grupo serão aplicadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f512c-107">If you change the assignment, policies that are specific to that group will be applied to the device.</span></span> <span data-ttu-id="f512c-108">A alteração pode instalar a versão mais recente do Windows 10 (incluindo qualquer novo recurso ou atualizações de qualidade).</span><span class="sxs-lookup"><span data-stu-id="f512c-108">The change might install the latest version of Windows 10 (including any new feature or quality updates).</span></span> <span data-ttu-id="f512c-109">É melhor mover apenas alguns dispositivos no início e verificar a experiência do usuário resultante.</span><span class="sxs-lookup"><span data-stu-id="f512c-109">It's best to move just a few devices at first and then check the resulting user experience.</span></span> <span data-ttu-id="f512c-110">Esteja ciente de que determinadas atualizações reiniciarão o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f512c-110">Be aware that certain updates will restart the device.</span></span> <span data-ttu-id="f512c-111">Verifique se você selecionou os dispositivos certos a atribuir.</span><span class="sxs-lookup"><span data-stu-id="f512c-111">Double-check that you've selected the right devices to assign.</span></span> <span data-ttu-id="f512c-112">Pode levar até 24 horas para que a atribuição entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="f512c-112">It can take up to 24 hours for the assignment to take effect.</span></span>

<span data-ttu-id="f512c-113">Para atribuir dispositivos a um grupo de implantação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f512c-113">To assign devices to a deployment group, follow these steps.</span></span> <span data-ttu-id="f512c-114">Se você quiser mover dispositivos separados para grupos diferentes, repita estas etapas para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="f512c-114">If you want to move separate devices to different groups, repeat these steps for each group.</span></span>

1. <span data-ttu-id="f512c-115">Em Microsoft Endpoint Manager, selecione **Dispositivos** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="f512c-115">In Microsoft Endpoint Manager, select **Devices** in the left pane.</span></span> <span data-ttu-id="f512c-116">Na seção **Área de Trabalho Gerenciada da Microsoft,** selecione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f512c-116">In the **Microsoft Managed Desktop** section, select **Devices**.</span></span>
2. <span data-ttu-id="f512c-117">Selecione os dispositivos que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="f512c-117">Select the devices you want to assign.</span></span> <span data-ttu-id="f512c-118">Todos os dispositivos selecionados serão atribuídos ao grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="f512c-118">All selected devices will be assigned to the group you specify.</span></span>
3. <span data-ttu-id="f512c-119">Selecione **Ações do dispositivo** no menu.</span><span class="sxs-lookup"><span data-stu-id="f512c-119">Select **Device actions** from the menu.</span></span>
4. <span data-ttu-id="f512c-120">Selecione **Atribuir dispositivo ao grupo**.</span><span class="sxs-lookup"><span data-stu-id="f512c-120">Select **Assign device to group**.</span></span> <span data-ttu-id="f512c-121">Um fly-in é aberto.</span><span class="sxs-lookup"><span data-stu-id="f512c-121">A fly-in opens.</span></span>
5. <span data-ttu-id="f512c-122">Use o menu suspenso para selecionar o grupo para o que mover dispositivos e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f512c-122">Use the drop-down menu to select the group to move devices to, and then select **Save**.</span></span> <span data-ttu-id="f512c-123">O **Grupo atribuído por mudará** para **Pendente**.</span><span class="sxs-lookup"><span data-stu-id="f512c-123">The **Group assigned by** will change to **Pending**.</span></span>

<span data-ttu-id="f512c-124">Quando a atribuição for concluída, **o** Grupo atribuído por será alternada  para **Admin** (indicado que você fez a alteração) e a coluna Grupo mostrará a nova atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="f512c-124">When the assignment is complete, **Group assigned by** will change to **Admin** (indicated that you made the change) and the **Group** column will show the new group assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="f512c-125">Não é possível mover dispositivos para outros grupos se eles estão no estado de registro "erro" ou "pendente".</span><span class="sxs-lookup"><span data-stu-id="f512c-125">You can't move devices to other groups if they're in the "error" or "pending" registration state.</span></span>
>
><span data-ttu-id="f512c-126">Se um dispositivo não tiver sido removido corretamente, ele poderá mostrar um status de "pronto".</span><span class="sxs-lookup"><span data-stu-id="f512c-126">If a device hasn't been properly removed, it could show a status of "ready."</span></span> <span data-ttu-id="f512c-127">Se você mover esse dispositivo, é possível que a movimentação não seja concluída.</span><span class="sxs-lookup"><span data-stu-id="f512c-127">If you move such a device, it's possible that the move won't complete.</span></span> <span data-ttu-id="f512c-128">Se você não  vir Grupo atribuído por alteração para **Pendente** na Etapa 5, verifique se o dispositivo está disponível pesquisando-o no Intune.</span><span class="sxs-lookup"><span data-stu-id="f512c-128">If you don't see **Group assigned by** change to **Pending** in Step 5, check that the device is available by searching for it in Intune.</span></span> <span data-ttu-id="f512c-129">Para obter mais informações, confira [Ver detalhes do dispositivo no Intune](/mem/intune/remote-actions/device-inventory).</span><span class="sxs-lookup"><span data-stu-id="f512c-129">For more information, see [See device details in Intune](/mem/intune/remote-actions/device-inventory).</span></span>