---
title: Implantar e habilitar o Microsoft Defender Antivírus
description: Implante Microsoft Defender Antivírus proteção de seus pontos de extremidade com Microsoft Intune, Microsoft Endpoint Configuration Manager, Política de Grupo, cmdlets do PowerShell ou WMI.
keywords: implantar, habilitar, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 88a5401818c3d6f2b35675830a38b266db9627e4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274491"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="d9061-104">Implantar e habilitar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d9061-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9061-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d9061-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9061-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d9061-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d9061-107">Dependendo da ferramenta de gerenciamento que você está usando, talvez seja necessário habilitar ou configurar especificamente Microsoft Defender Antivírus proteção.</span><span class="sxs-lookup"><span data-stu-id="d9061-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="d9061-108">Consulte a tabela em [Deploy, manage, and report](deploy-manage-report-microsoft-defender-antivirus.md#ref2) on Microsoft Defender Antivírus para obter instruções sobre como habilitar a proteção com Microsoft Intune, Microsoft Endpoint Configuration Manager, Política de Grupo, Active Directory, Microsoft Azure, cmdlets do PowerShell e Windows Instrução de Gerenciamento (WMI).</span><span class="sxs-lookup"><span data-stu-id="d9061-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="d9061-109">Alguns cenários exigem mais orientações sobre como implantar ou configurar com êxito Microsoft Defender Antivírus proteção, como ambientes Virtual Desktop Infrastructure (VDI).</span><span class="sxs-lookup"><span data-stu-id="d9061-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="d9061-110">O artigo restante nesta seção fornece orientações e práticas recomendadas de ponta a ponta para configurar o Microsoft Defender Antivírus em máquinas virtuais (VMs) em um ambiente VDI ou Serviços de Área de Trabalho [Remota (RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d9061-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d9061-111">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d9061-111">Related articles</span></span>

- [<span data-ttu-id="d9061-112">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="d9061-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d9061-113">Implantar, gerenciar atualizações e relatório sobre Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d9061-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d9061-114">Guia de implantação do Microsoft Defender Antivírus em um ambiente virtual de área de trabalho (VDI)</span><span class="sxs-lookup"><span data-stu-id="d9061-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)