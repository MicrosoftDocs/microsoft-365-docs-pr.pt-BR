---
title: Gerenciar Windows Defender em sua empresa
description: Saiba como usar a Política de Grupo, o Gerenciador de Configurações, o PowerShell, o WMI, o Intune e a linha de comando para gerenciar o Microsoft Defender AV
keywords: política de grupo, gpo, gerente de configuração, sccm, scep, powershell, wmi, intune, defender, antivírus, antimalware, segurança, proteção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2265f3680e425ade062d444685fbd8873eaa02ca
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274959"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="9da01-104">Gerenciar Microsoft Defender Antivírus em sua empresa</span><span class="sxs-lookup"><span data-stu-id="9da01-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9da01-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9da01-105">**Applies to:**</span></span>

- [<span data-ttu-id="9da01-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9da01-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9da01-107">Você pode gerenciar e configurar Microsoft Defender Antivírus com as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="9da01-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="9da01-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (agora parte do Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="9da01-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="9da01-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (agora parte do Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="9da01-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="9da01-110">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="9da01-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9da01-111">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9da01-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9da01-112">Windows Instrumentação de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="9da01-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="9da01-113">O [Utilitário de Linha](./command-line-arguments-microsoft-defender-antivirus.md) de Comando da Proteção de Malware da Microsoft (conhecido como utilitário *de* mpcmdrun.exede segurança)</span><span class="sxs-lookup"><span data-stu-id="9da01-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="9da01-114">Os artigos a seguir fornecem mais informações, links e recursos para usar essas ferramentas para gerenciar e configurar Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="9da01-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="9da01-115">Artigo</span><span class="sxs-lookup"><span data-stu-id="9da01-115">Article</span></span> | <span data-ttu-id="9da01-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="9da01-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="9da01-117">Gerenciar Microsoft Defender Antivírus com Microsoft Intune e Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9da01-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="9da01-118">Informações sobre como usar o Intune e o Configuration Manager para implantar, gerenciar, relatar e configurar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="9da01-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="9da01-119">Gerenciar Microsoft Defender Antivírus com configurações de Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="9da01-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="9da01-120">Lista de todas as configurações de Política de Grupo localizadas em modelos ADMX</span><span class="sxs-lookup"><span data-stu-id="9da01-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="9da01-121">Gerenciar Microsoft Defender Antivírus com cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9da01-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="9da01-122">Instruções para usar cmdlets do PowerShell para gerenciar Microsoft Defender Antivírus, além de links para a documentação de todos os cmdlets e parâmetros permitidos</span><span class="sxs-lookup"><span data-stu-id="9da01-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="9da01-123">Gerenciar Microsoft Defender Antivírus com Windows Instrumentação de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="9da01-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="9da01-124">Instruções para usar o WMI para gerenciar Microsoft Defender Antivírus, além de links para documentação das APIs WMIv2 (incluindo todas as classes, métodos e propriedades)</span><span class="sxs-lookup"><span data-stu-id="9da01-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="9da01-125">Gerenciar Microsoft Defender Antivírus com a ferramenta mpcmdrun.exe linha de comando</span><span class="sxs-lookup"><span data-stu-id="9da01-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="9da01-126">Instruções sobre como usar a ferramenta de linha de comando dedicada para gerenciar e usar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="9da01-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |