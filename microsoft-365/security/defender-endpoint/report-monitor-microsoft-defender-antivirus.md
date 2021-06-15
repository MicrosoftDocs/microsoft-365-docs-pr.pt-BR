---
title: Monitorar e relatar sobre Microsoft Defender Antivírus proteção
description: Use o Configuration Manager ou as ferramentas de gerenciamento de eventos e informações de segurança (SIEM) para consumir relatórios e monitorar o Microsoft Defender AV com o PowerShell e o WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 91891af35def83f21b3db8c7e8fa4b320bef563c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926146"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="778ad-104">Relatório sobre o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="778ad-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="778ad-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="778ad-105">**Applies to:**</span></span>

- [<span data-ttu-id="778ad-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="778ad-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="778ad-107">Microsoft Defender Antivírus é integrado ao Windows 10, Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="778ad-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="778ad-108">Microsoft Defender Antivírus é da sua proteção de última geração no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="778ad-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="778ad-109">A proteção de última geração ajuda a proteger seus dispositivos contra ameaças de software, como vírus, malware e spyware em email, aplicativos, nuvem e Web.</span><span class="sxs-lookup"><span data-stu-id="778ad-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="778ad-110">Com Microsoft Defender Antivírus, você tem várias opções para revisar o status e os alertas de proteção.</span><span class="sxs-lookup"><span data-stu-id="778ad-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="778ad-111">Você pode usar Microsoft Endpoint Manager para [monitorar Microsoft Defender Antivírus](/configmgr/protect/deploy-use/monitor-endpoint-protection) ou [criar alertas de email.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="778ad-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="778ad-112">Ou você pode monitorar a proteção usando [Microsoft Intune](/intune/introduction-intune).</span><span class="sxs-lookup"><span data-stu-id="778ad-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="778ad-113">O Microsoft Operations Management Suite tem um complemento de [Conformidade](/windows/deployment/update/update-compliance-get-started) de Atualização que relata os principais problemas Microsoft Defender Antivírus, incluindo atualizações de proteção e configurações de proteção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="778ad-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="778ad-114">Se você tiver um servidor siem (gerenciamento de eventos) e informações de segurança de terceiros, você também poderá consumir Windows Defender [eventos de cliente.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="778ad-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="778ad-115">Windows eventos incluem várias fontes de eventos de segurança, incluindo eventos SAM (Security [](/windows/device-security/auditing/security-auditing-overview) Account Manager)[(](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)aprimorados para Windows 10 , também consulte o tópico auditoria de segurança) e Windows Defender [eventos](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="778ad-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="778ad-116">Esses eventos podem ser agregados centralmente usando o [coletor Windows evento](/windows/win32/wec/windows-event-collector).</span><span class="sxs-lookup"><span data-stu-id="778ad-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="778ad-117">Frequentemente, os servidores SIEM têm conectores para eventos Windows, permitindo correlacionar todos os eventos de segurança em seu servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="778ad-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="778ad-118">Você também pode [monitorar eventos de malware usando a solução de Avaliação de Malware no Log Analytics.](/azure/log-analytics/log-analytics-malware)</span><span class="sxs-lookup"><span data-stu-id="778ad-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="778ad-119">Para monitorar ou determinar o status com o PowerShell, WMI ou Microsoft Azure, consulte [a tabela (Opções](deploy-manage-report-microsoft-defender-antivirus.md#ref2)de implantação, gerenciamento e relatório) .</span><span class="sxs-lookup"><span data-stu-id="778ad-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="778ad-120">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="778ad-120">Related articles</span></span>

- [<span data-ttu-id="778ad-121">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="778ad-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="778ad-122">Microsoft Defender Antivírus no Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="778ad-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="778ad-123">Implantar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="778ad-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)