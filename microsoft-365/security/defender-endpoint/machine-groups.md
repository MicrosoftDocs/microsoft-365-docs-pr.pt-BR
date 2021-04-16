---
title: Criar e gerenciar grupos de dispositivos no Microsoft Defender para Ponto de Extremidade
description: Criar grupos de dispositivos e definir níveis automatizados de correção neles, confiando as regras que se aplicam ao grupo
keywords: grupos de dispositivos, grupos, correção, nível, regras, aad group, role, assign, rank
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
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860298"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="b3e1a-104">Criar e gerenciar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b3e1a-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b3e1a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b3e1a-105">**Applies to:**</span></span>
- <span data-ttu-id="b3e1a-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b3e1a-106">Azure Active Directory</span></span>
- <span data-ttu-id="b3e1a-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="b3e1a-107">Office 365</span></span>

> <span data-ttu-id="b3e1a-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b3e1a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3e1a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="b3e1a-110">Em um cenário empresarial, as equipes de operação de segurança normalmente são atribuídas a um conjunto de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="b3e1a-111">Esses dispositivos são agrupados com base em um conjunto de atributos, como seus domínios, nomes de computador ou marcas designadas.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="b3e1a-112">No Microsoft Defender para Ponto de Extremidade, você pode criar grupos de dispositivos e usá-los para:</span><span class="sxs-lookup"><span data-stu-id="b3e1a-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="b3e1a-113">Limitar o acesso a alertas e dados relacionados a grupos de usuários específicos do Azure AD com [funções RBAC atribuídas](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="b3e1a-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="b3e1a-114">Configurar configurações de correção automática diferentes para diferentes conjuntos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b3e1a-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="b3e1a-115">Atribuir níveis de correção específicos a aplicar durante investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="b3e1a-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="b3e1a-116">Em uma investigação, filtre a lista **Dispositivos** para grupos de dispositivos específicos usando o **filtro Group.**</span><span class="sxs-lookup"><span data-stu-id="b3e1a-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="b3e1a-117">Você pode criar grupos de dispositivos no contexto do RBAC (acesso baseado em função) para controlar quem pode tomar ações específicas ou ver informações atribuindo os grupos de dispositivos a um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="b3e1a-118">Para obter mais informações, consulte [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="b3e1a-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="b3e1a-119">Para uma análise abrangente do aplicativo RBAC, leia: Seu SOC está sendo [executado com RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span><span class="sxs-lookup"><span data-stu-id="b3e1a-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="b3e1a-120">Como parte do processo de criação de um grupo de dispositivos, você:</span><span class="sxs-lookup"><span data-stu-id="b3e1a-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="b3e1a-121">De definir o nível de correção automatizado para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="b3e1a-122">Para obter mais informações sobre níveis de correção, consulte [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="b3e1a-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="b3e1a-123">Especifique a regra correspondente que determina qual grupo de dispositivos pertence ao grupo com base no nome do dispositivo, domínio, marcas e plataforma do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="b3e1a-124">Se um dispositivo também for corresponder a outros grupos, ele será adicionado apenas ao grupo de dispositivos mais alto classificado.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="b3e1a-125">Selecione o grupo de usuários do Azure AD que deve ter acesso ao grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="b3e1a-126">Rank the device group relative to other groups after it is created.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="b3e1a-127">Um grupo de dispositivos será acessível a todos os usuários se você não atribuir nenhum grupo do Azure AD a ele.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="b3e1a-128">Criar um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b3e1a-128">Create a device group</span></span>

1. <span data-ttu-id="b3e1a-129">No painel de navegação, selecione **Configurações**  >  **Grupos de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="b3e1a-130">Clique **em Adicionar grupo de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="b3e1a-131">Insira o nome do grupo e as configurações de automação e especifique a regra correspondente que determina quais dispositivos pertencem ao grupo.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="b3e1a-132">Veja [Como a investigação automatizada é iniciada.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="b3e1a-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="b3e1a-133">Se você quiser agrupar dispositivos por unidade organizacional, você pode configurar a chave do Registro para a afiliação de grupo.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="b3e1a-134">Para obter mais informações sobre a marcação de dispositivo, consulte [Create and manage device tags](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b3e1a-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="b3e1a-135">Visualize vários dispositivos que serão compatíveis com essa regra.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="b3e1a-136">Se você estiver satisfeito com a regra, clique na **guia Acesso do** usuário.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="b3e1a-137">Atribua os grupos de usuários que podem acessar o grupo de dispositivos que você criou.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b3e1a-138">Você só pode conceder acesso a grupos de usuários do Azure AD atribuídos a funções RBAC.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="b3e1a-139">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-139">Click **Close**.</span></span> <span data-ttu-id="b3e1a-140">As alterações de configuração são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="b3e1a-141">Gerenciar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b3e1a-141">Manage device groups</span></span>

<span data-ttu-id="b3e1a-142">Você pode promover ou rebaixar a classificação de um grupo de dispositivos para que ele seja priorizado mais ou menos durante a correspondência.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="b3e1a-143">Quando um dispositivo é corresponder a mais de um grupo, ele é adicionado apenas ao grupo de classificação mais alto.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="b3e1a-144">Você também pode editar e excluir grupos.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="b3e1a-145">Excluir um grupo de dispositivos pode afetar as regras de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="b3e1a-146">Se um grupo de dispositivos estiver configurado sob uma regra de notificação de email, ele será removido dessa regra.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="b3e1a-147">Se o grupo de dispositivos for o único grupo configurado para uma notificação de email, essa regra de notificação de email será excluída juntamente com o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="b3e1a-148">Por padrão, os grupos de dispositivos são acessíveis a todos os usuários com acesso ao portal.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="b3e1a-149">Você pode alterar o comportamento padrão atribuindo grupos de usuários do Azure AD ao grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="b3e1a-150">Dispositivos que não são compatíveis com nenhum grupo são adicionados ao grupo Dispositivos Desagrupados (padrão).</span><span class="sxs-lookup"><span data-stu-id="b3e1a-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="b3e1a-151">Não é possível alterar a classificação desse grupo ou excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="b3e1a-152">No entanto, você pode alterar o nível de correção desse grupo e definir os grupos de usuários do Azure AD que podem acessar esse grupo.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="b3e1a-153">A aplicação de alterações na configuração do grupo de dispositivos pode levar até vários minutos.</span><span class="sxs-lookup"><span data-stu-id="b3e1a-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3e1a-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b3e1a-154">Related topics</span></span>

- [<span data-ttu-id="b3e1a-155">Gerenciar o acesso ao portal usando o controle de acesso baseado em função</span><span class="sxs-lookup"><span data-stu-id="b3e1a-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="b3e1a-156">Criar e gerenciar marcas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b3e1a-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="b3e1a-157">Obter lista de grupos de dispositivos de locatários usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="b3e1a-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
