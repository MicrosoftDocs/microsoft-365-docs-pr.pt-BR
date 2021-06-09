---
title: Nomes do dispositivo
description: Como Área de Trabalho Gerenciada da Microsoft gerencia nomes de dispositivos
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893682"
---
# <a name="device-names"></a><span data-ttu-id="ebd48-103">Nomes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ebd48-103">Device names</span></span>

<span data-ttu-id="ebd48-104">Área de Trabalho Gerenciada da Microsoft usa Windows Autopilot, Azure Active Directory e Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ebd48-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="ebd48-105">Para que esses serviços funcionem em conjunto perfeitamente, os dispositivos precisam de nomes consistentes e padronizados.</span><span class="sxs-lookup"><span data-stu-id="ebd48-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="ebd48-106">Área de Trabalho Gerenciada da Microsoft aplica um formato de nome padronizado (do formato *MMD-%RAND11*) quando os dispositivos são inscritos.</span><span class="sxs-lookup"><span data-stu-id="ebd48-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="ebd48-107">Windows O Piloto Automático atribui esses nomes.</span><span class="sxs-lookup"><span data-stu-id="ebd48-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="ebd48-108">Para obter mais informações sobre o Autopilot, consulte Experiência de primeira corrida [com o Autopilot e a Página de Status de Registro.](../get-started/esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="ebd48-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="ebd48-109">Alterações automáticas de nome</span><span class="sxs-lookup"><span data-stu-id="ebd48-109">Automated name changes</span></span>

<span data-ttu-id="ebd48-110">Se um dispositivo for renomeado posteriormente, Área de Trabalho Gerenciada da Microsoft o renomeará automaticamente para um novo nome no formato padronizado.</span><span class="sxs-lookup"><span data-stu-id="ebd48-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="ebd48-111">Esse processo ocorre a cada quatro horas.</span><span class="sxs-lookup"><span data-stu-id="ebd48-111">This process occurs every four hours.</span></span> <span data-ttu-id="ebd48-112">A alteração de nome ocorre na próxima vez que o usuário reiniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ebd48-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebd48-113">Se seu ambiente depender de nomes de dispositivo específicos (por exemplo, para dar suporte a uma configuração de rede específica), você deve investigar opções para remover essa dependência antes de se registrar no Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ebd48-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ebd48-114">Se você deve manter a dependência de nome, você pode enviar uma solicitação por meio do [portal](../working-with-managed-desktop/admin-support.md) de administração para desabilitar a função de renomeação e usar o formato de nome desejado.</span><span class="sxs-lookup"><span data-stu-id="ebd48-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>