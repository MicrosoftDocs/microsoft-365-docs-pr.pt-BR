---
title: Executar e personalizar verificações agendadas e sob demanda
description: Personalizar e iniciar Microsoft Defender Antivírus verificações em pontos de extremidade em toda a sua rede.
keywords: scan, schedule, customize, exclusions, exclude files, remediation, scan results, quarantine, remove threat, quick scan, full scan, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 31dbfa2ac6d5537f6d42c0bad612be5ef059368d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275271"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="5f6f8-104">Personalizar, iniciar e revisar os resultados de Microsoft Defender Antivírus e correção</span><span class="sxs-lookup"><span data-stu-id="5f6f8-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5f6f8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5f6f8-105">**Applies to:**</span></span>

- [<span data-ttu-id="5f6f8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5f6f8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5f6f8-107">Você pode usar a Política de Grupo, o PowerShell e Windows Instrumentação de Gerenciamento (WMI) para configurar Microsoft Defender Antivírus verificações.</span><span class="sxs-lookup"><span data-stu-id="5f6f8-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="5f6f8-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5f6f8-108">In this section</span></span>

<span data-ttu-id="5f6f8-109">Tópico</span><span class="sxs-lookup"><span data-stu-id="5f6f8-109">Topic</span></span> | <span data-ttu-id="5f6f8-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f6f8-110">Description</span></span>
---|---
[<span data-ttu-id="5f6f8-111">Configurar e validar exclusões de arquivo, pasta e processo aberto em Microsoft Defender Antivírus verificações</span><span class="sxs-lookup"><span data-stu-id="5f6f8-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="5f6f8-112">Você pode excluir arquivos (incluindo arquivos modificados por processos especificados) e pastas de verificações sob demanda, verificações agendadas e monitoramento e verificação de proteção em tempo real sempre em tempo real</span><span class="sxs-lookup"><span data-stu-id="5f6f8-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="5f6f8-113">Configurar opções de verificação do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="5f6f8-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="5f6f8-114">Você pode configurar o Microsoft Defender Antivírus para incluir determinados tipos de arquivos de armazenamento de email, pontos de back-up ou reparse e arquivos arquivados (como arquivos .zip) em verificações.</span><span class="sxs-lookup"><span data-stu-id="5f6f8-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="5f6f8-115">Você também pode habilitar a verificação de arquivos de rede</span><span class="sxs-lookup"><span data-stu-id="5f6f8-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="5f6f8-116">Configurar correção para verificações</span><span class="sxs-lookup"><span data-stu-id="5f6f8-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="5f6f8-117">Configure o Microsoft Defender Antivírus deve ser feito quando detectar uma ameaça e por quanto tempo os arquivos em quarentena devem ser mantidos na pasta de quarentena</span><span class="sxs-lookup"><span data-stu-id="5f6f8-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="5f6f8-118">Configurar verificações agendadas</span><span class="sxs-lookup"><span data-stu-id="5f6f8-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="5f6f8-119">Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas</span><span class="sxs-lookup"><span data-stu-id="5f6f8-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="5f6f8-120">Configurar e executar verificações</span><span class="sxs-lookup"><span data-stu-id="5f6f8-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="5f6f8-121">Executar e configurar verificações sob demanda usando o PowerShell, Windows Instrumentação de Gerenciamento ou individualmente nos pontos de extremidade com o aplicativo Segurança do Windows de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="5f6f8-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="5f6f8-122">Revisar resultados da verificação</span><span class="sxs-lookup"><span data-stu-id="5f6f8-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="5f6f8-123">Revise os resultados das verificações usando Microsoft Endpoint Configuration Manager, Microsoft Intune ou o Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="5f6f8-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>