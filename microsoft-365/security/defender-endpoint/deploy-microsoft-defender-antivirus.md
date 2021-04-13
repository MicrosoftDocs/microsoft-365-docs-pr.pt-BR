---
title: Implantar e habilitar o Microsoft Defender Antivírus
description: Implante o Microsoft Defender Antivírus para proteção de seus pontos de extremidade com o Microsoft Intune, o Microsoft Endpoint Configuration Manager, a Política de Grupo, os cmdlets do PowerShell ou o WMI.
keywords: implantar, habilitar, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: efc2aa0f48cb2bc55e729b65c892a07b74c1bc46
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690001"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="08ab0-104">Implantar e habilitar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="08ab0-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="08ab0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="08ab0-105">**Applies to:**</span></span>

- [<span data-ttu-id="08ab0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="08ab0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="08ab0-107">Dependendo da ferramenta de gerenciamento que você está usando, talvez seja necessário habilitar ou configurar especificamente a proteção do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="08ab0-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="08ab0-108">Consulte a tabela em Implantar, gerenciar e relatar sobre o [Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) para obter instruções sobre como habilitar a proteção com o Microsoft Intune, o Microsoft Endpoint Configuration Manager, a Política de Grupo, o Active Directory, o Microsoft Azure, os cmdlets do PowerShell e a Instrução de Gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="08ab0-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="08ab0-109">Alguns cenários exigem mais orientações sobre como implantar ou configurar com êxito a proteção do Microsoft Defender Antivírus, como ambientes Virtual Desktop Infrastructure (VDI).</span><span class="sxs-lookup"><span data-stu-id="08ab0-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="08ab0-110">O artigo restante nesta seção fornece orientações e práticas recomendadas de ponta a ponta para configurar o Microsoft Defender Antivírus em máquinas virtuais (VMs) em um ambiente VDI ou Serviços de Área de Trabalho [Remota (RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="08ab0-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="08ab0-111">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="08ab0-111">Related articles</span></span>

- [<span data-ttu-id="08ab0-112">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="08ab0-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="08ab0-113">Implantar, gerenciar atualizações e relatório sobre o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="08ab0-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="08ab0-114">Guia de implantação do Microsoft Defender Antivírus em um ambiente de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="08ab0-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)