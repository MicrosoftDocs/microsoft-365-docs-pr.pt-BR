---
title: Configurar o período de tempo de bloqueio de nuvem do Microsoft Defender Antivírus
description: Você pode configurar por quanto tempo o Microsoft Defender Antivírus impedirá a execução de um arquivo enquanto aguarda uma determinação na nuvem.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, nuvem, tempo decoro, bloqueio, ponto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765798"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="42f20-104">Configurar o período de tempo limite de bloqueio da nuvem</span><span class="sxs-lookup"><span data-stu-id="42f20-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="42f20-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="42f20-105">**Applies to:**</span></span>

- [<span data-ttu-id="42f20-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="42f20-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="42f20-107">Quando o Microsoft Defender Antivírus encontra um arquivo suspeito, ele pode impedir que o arquivo seja executado enquanto ele consulta o serviço de nuvem [do Microsoft Defender Antivírus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="42f20-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="42f20-108">O período padrão em que o arquivo será [bloqueado](configure-block-at-first-sight-microsoft-defender-antivirus.md) é de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="42f20-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="42f20-109">Você pode especificar um período adicional de tempo para aguardar antes que o arquivo possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="42f20-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="42f20-110">Isso pode ajudar a garantir que haja tempo suficiente para receber uma determinação adequada do serviço de nuvem do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="42f20-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="42f20-111">Pré-requisitos para usar o tempo de tempo de bloqueio estendido na nuvem</span><span class="sxs-lookup"><span data-stu-id="42f20-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="42f20-112">[Bloqueie à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) e seus pré-requisitos devem ser habilitados antes que você possa especificar um período de tempo de tempo estendido.</span><span class="sxs-lookup"><span data-stu-id="42f20-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="42f20-113">Especificar o período de tempo de tempo estendido</span><span class="sxs-lookup"><span data-stu-id="42f20-113">Specify the extended timeout period</span></span>

<span data-ttu-id="42f20-114">Você pode usar a Política de Grupo para especificar um tempo de tempo estendido para verificações na nuvem.</span><span class="sxs-lookup"><span data-stu-id="42f20-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="42f20-115">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="42f20-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="42f20-116">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="42f20-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="42f20-117">Expanda a árvore para **componentes do Windows > o Microsoft Defender Antivírus > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="42f20-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="42f20-118">Clique duas vezes em **Configurar verificação de nuvem estendida** e certifique-se de que a opção está habilitada.</span><span class="sxs-lookup"><span data-stu-id="42f20-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="42f20-119">Especifique o tempo adicional para impedir que o arquivo seja executado enquanto aguarda uma determinação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="42f20-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="42f20-120">Você pode especificar o tempo adicional, em segundos, de 1 segundo a 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="42f20-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="42f20-121">Este tempo será adicionado aos 10 segundos padrão.</span><span class="sxs-lookup"><span data-stu-id="42f20-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="42f20-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42f20-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="42f20-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="42f20-123">Related topics</span></span>

- [<span data-ttu-id="42f20-124">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="42f20-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="42f20-125">Usar tecnologias antivírus de última geração por meio da proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="42f20-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="42f20-126">Configurar o bloco à primeira vista</span><span class="sxs-lookup"><span data-stu-id="42f20-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="42f20-127">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="42f20-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)