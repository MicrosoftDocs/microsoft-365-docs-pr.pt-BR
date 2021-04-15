---
title: Configurar o Microsoft Defender Antivírus com WMI
description: Saiba como configurar e gerenciar o Microsoft Defender Antivírus usando scripts WMI para recuperar, modificar e atualizar configurações no Microsoft Defender para Ponto de Extremidade.
keywords: wmi, scripts, instrumentação de gerenciamento do Windows, configuração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764058"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="1e235-104">Use a Instrumentação de Gerenciamento do Windows (WMI) para configurar e gerenciar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="1e235-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1e235-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1e235-105">**Applies to:**</span></span>

- [<span data-ttu-id="1e235-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1e235-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1e235-107">A Instrumentação de Gerenciamento do Windows (WMI) é uma interface de script que permite recuperar, modificar e atualizar configurações.</span><span class="sxs-lookup"><span data-stu-id="1e235-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="1e235-108">Leia mais sobre o WMI na biblioteca Administração do Sistema de Rede de Desenvolvedores [da Microsoft.](/windows/win32/wmisdk/wmi-start-page)</span><span class="sxs-lookup"><span data-stu-id="1e235-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="1e235-109">O Microsoft Defender Antivírus tem várias classes WMI específicas que podem ser usadas para executar a maioria das mesmas funções que a Política de Grupo e outras ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="1e235-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="1e235-110">Muitas das classes são análogas aos [cmdlets do Defender PowerShell.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1e235-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="1e235-111">A biblioteca de referência do [provedor WMIv2 Windows Defender MSDN](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lista as classes WMI disponíveis para o Microsoft Defender Antivírus e inclui scripts de exemplo.</span><span class="sxs-lookup"><span data-stu-id="1e235-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="1e235-112">As alterações feitas com o WMI afetarão as configurações locais no ponto de extremidade onde as alterações são implantadas ou feitas.</span><span class="sxs-lookup"><span data-stu-id="1e235-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="1e235-113">Isso significa que as implantações de política com a Política de Grupo, o Microsoft Endpoint Configuration Manager ou o Microsoft Intune podem substituir as alterações feitas com o WMI.</span><span class="sxs-lookup"><span data-stu-id="1e235-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="1e235-114">Você pode [configurar quais configurações podem ser substituidas localmente com substituições de política local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1e235-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e235-115">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e235-115">Related topics</span></span>

- [<span data-ttu-id="1e235-116">Tópicos de referência para ferramentas de gerenciamento e configuração</span><span class="sxs-lookup"><span data-stu-id="1e235-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1e235-117">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="1e235-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)