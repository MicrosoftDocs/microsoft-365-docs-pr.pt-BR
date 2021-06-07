---
title: Compatibilidade de solução antivírus com o Defender para Ponto de Extremidade
description: Saiba como o Windows Defender funciona com o Microsoft Defender para Ponto de Extremidade e como ele funciona quando um cliente antimalware de terceiros é usado.
keywords: Compatibilidade com o Windows Defender, Defender, Microsoft Defender para Ponto de Extremidade, Defender para ponto de extremidade, antivírus, mde
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
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782880"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="65191-104">Compatibilidade de soluções antivírus com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65191-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65191-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="65191-105">**Applies to:**</span></span>
- [<span data-ttu-id="65191-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65191-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65191-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65191-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="65191-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="65191-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65191-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="65191-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="65191-110">O agente do Microsoft Defender para Ponto de Extremidade depende Microsoft Defender Antivírus alguns recursos, como a verificação de arquivos.</span><span class="sxs-lookup"><span data-stu-id="65191-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="65191-111">O Defender para Ponto de Extremidade não segue as configurações Microsoft Defender Antivírus Exclusões.</span><span class="sxs-lookup"><span data-stu-id="65191-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="65191-112">Você deve configurar atualizações de inteligência de segurança no Defender para dispositivos de ponto de extremidade, Microsoft Defender Antivírus o antimalware ativo ou não.</span><span class="sxs-lookup"><span data-stu-id="65191-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="65191-113">Para obter mais informações, consulte [Manage Microsoft Defender Antivírus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="65191-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="65191-114">Se um dispositivo conectado estiver protegido por um cliente antimalware de terceiros, Microsoft Defender Antivírus nesse ponto de extremidade entrará no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="65191-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="65191-115">Microsoft Defender Antivírus continuará a receber atualizações, e  o processomspeng.exeserá listado como um serviço em execução, mas ele não executará verificações e não substituirá o cliente antimalware de terceiros em execução.</span><span class="sxs-lookup"><span data-stu-id="65191-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="65191-116">A Microsoft Defender Antivírus interface do usuário será desabilitada e os usuários no dispositivo não poderão usar o Microsoft Defender Antivírus para executar verificações sob demanda ou configurar a maioria das opções.</span><span class="sxs-lookup"><span data-stu-id="65191-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="65191-117">Para obter mais informações, consulte o [tópico Microsoft Defender Antivírus e Defender for Endpoint compatibility](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="65191-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
