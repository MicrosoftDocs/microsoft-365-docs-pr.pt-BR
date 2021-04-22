---
title: Compatibilidade do Microsoft Defender Antivírus com o Defender para Ponto de Extremidade
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935372"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="1f62f-104">Compatibilidade do Microsoft Defender Antivírus com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1f62f-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f62f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1f62f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f62f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1f62f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f62f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f62f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="1f62f-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1f62f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1f62f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1f62f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="1f62f-110">O agente do Microsoft Defender para Ponto de Extremidade depende do Microsoft Defender Antivírus para alguns recursos, como a verificação de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1f62f-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1f62f-111">O Defender para Ponto de Extremidade não está de acordo com as configurações de Exclusão do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="1f62f-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="1f62f-112">Você deve configurar atualizações de inteligência de segurança no Defender para dispositivos de ponto de extremidade, se o Microsoft Defender Antivírus é o antimalware ativo ou não.</span><span class="sxs-lookup"><span data-stu-id="1f62f-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="1f62f-113">Para obter mais informações, consulte [Manage Microsoft Defender Antivírus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1f62f-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="1f62f-114">Se um dispositivo conectado estiver protegido por um cliente antimalware de terceiros, o Microsoft Defender Antivírus nesse ponto de extremidade entrará no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="1f62f-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="1f62f-115">O Microsoft Defender Antivírus continuará a  receber atualizações, e o processo demspeng.exeserá listado como um serviço em execução, mas ele não executará verificações e não substituirá o cliente antimalware de terceiros em execução.</span><span class="sxs-lookup"><span data-stu-id="1f62f-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="1f62f-116">A interface do Microsoft Defender Antivírus será desabilitada e os usuários no dispositivo não poderão usar o Microsoft Defender Antivírus para executar verificações sob demanda ou configurar a maioria das opções.</span><span class="sxs-lookup"><span data-stu-id="1f62f-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="1f62f-117">Para obter mais informações, consulte o tópico de compatibilidade do Microsoft Defender Antivírus e [do Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="1f62f-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
