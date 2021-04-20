---
title: Remover dispositivos
description: Remover dispositivos do gerenciamento da Área de Trabalho Gerenciada da Microsoft
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893663"
---
# <a name="remove-devices"></a><span data-ttu-id="75e83-103">Remover dispositivos</span><span class="sxs-lookup"><span data-stu-id="75e83-103">Remove devices</span></span>

<span data-ttu-id="75e83-104">Você pode remover dispositivos do gerenciamento da Área de Trabalho Gerenciada da Microsoft usando o portal de administração.</span><span class="sxs-lookup"><span data-stu-id="75e83-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="75e83-105">Essa ação é permanente, mas você pode registrá-los na Área de Trabalho Gerenciada da Microsoft novamente seguindo as etapas [de registro](../get-started/register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="75e83-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="75e83-106">Quando você remove um dispositivo, todos os seguintes ocorrem:</span><span class="sxs-lookup"><span data-stu-id="75e83-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="75e83-107">Removemos o dispositivo do Autopilot.</span><span class="sxs-lookup"><span data-stu-id="75e83-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="75e83-108">Removemos o dispositivo de todos os grupos de dispositivos "Modern Workplace".</span><span class="sxs-lookup"><span data-stu-id="75e83-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="75e83-109">Removemos o dispositivo da folha **Dispositivos** no portal de administração.</span><span class="sxs-lookup"><span data-stu-id="75e83-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="75e83-110">Ao remover um dispositivo, você tem a opção de também removê-lo do Azure Active Directory (Azure AD) e do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="75e83-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="75e83-111">Remover os objetos relacionados a um dispositivo do Azure AD e do Microsoft Intune é permanente.</span><span class="sxs-lookup"><span data-stu-id="75e83-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="75e83-112">Se você remover os objetos, não poderá exibir ou gerenciar os dispositivos dos portais do Intune e do Azure.</span><span class="sxs-lookup"><span data-stu-id="75e83-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="75e83-113">Os dispositivos não poderão acessar os recursos corporativos da empresa.</span><span class="sxs-lookup"><span data-stu-id="75e83-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="75e83-114">Os dados da empresa podem ser excluídos deles se os dispositivos tentarem entrar depois de serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="75e83-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="75e83-115">No [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), selecione **Dispositivos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="75e83-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="75e83-116">Procure a seção **Área de Trabalho Gerenciada da Microsoft** do menu e selecione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="75e83-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="75e83-117">No espaço de trabalho Dispositivos de Área de Trabalho Gerenciados da Microsoft, selecione os dispositivos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="75e83-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="75e83-118">Selecione **Ações do dispositivo** e selecione Excluir **Dispositivo** que abre um sub-entrada para remover os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="75e83-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="75e83-119">No sub-entrada, revise os dispositivos selecionados e selecione **Remover dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="75e83-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="75e83-120">Se você quiser também remover os objetos do Azure AD e do Intune ao mesmo tempo, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="75e83-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="75e83-121">A remoção do dispositivo pode levar alguns minutos para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="75e83-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="75e83-122">Não é possível remover dispositivos que estão em um **estado de** registro pendente.</span><span class="sxs-lookup"><span data-stu-id="75e83-122">You can't remove devices that are in a **pending** registration state.</span></span>