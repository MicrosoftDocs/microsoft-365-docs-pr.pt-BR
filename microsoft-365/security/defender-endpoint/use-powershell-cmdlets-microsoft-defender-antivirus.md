---
title: Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender AV
description: Em Windows 10, você pode usar cmdlets do PowerShell para executar verificações, atualizar a inteligência de segurança e alterar configurações em Microsoft Defender Antivírus.
keywords: scan, linha de comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765294"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="0ff64-104">Usar cmdlets do PowerShell para configurar e gerenciar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="0ff64-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0ff64-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0ff64-105">**Applies to:**</span></span>

- [<span data-ttu-id="0ff64-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0ff64-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0ff64-107">Você pode usar o PowerShell para executar várias funções em Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="0ff64-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="0ff64-108">Semelhante ao prompt de comando ou linha de comando, o PowerShell é um shell de linha de comando baseado em tarefas e linguagem de script projetada especialmente para a administração do sistema.</span><span class="sxs-lookup"><span data-stu-id="0ff64-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="0ff64-109">Você pode ler mais sobre isso no [hub do PowerShell no MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="0ff64-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="0ff64-110">Para ver uma lista dos cmdlets e suas funções e parâmetros disponíveis, consulte o [tópico cmdlets](/powershell/module/defender) do Defender.</span><span class="sxs-lookup"><span data-stu-id="0ff64-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="0ff64-111">Os cmdlets do PowerShell são mais úteis em ambientes Windows Server que não dependem de uma interface gráfica do usuário (GUI) para configurar o software.</span><span class="sxs-lookup"><span data-stu-id="0ff64-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="0ff64-112">Os cmdlets do PowerShell não devem ser usados como um substituto para uma infraestrutura completa de gerenciamento de política de rede, [como Microsoft Endpoint Configuration Manager](/configmgr), Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))ou modelos ADMX de política de grupo [Microsoft Defender Antivírus.](https://www.microsoft.com/download/101445)</span><span class="sxs-lookup"><span data-stu-id="0ff64-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="0ff64-113">As alterações feitas com o PowerShell afetarão as configurações locais no ponto de extremidade onde as alterações são implantadas ou feitas.</span><span class="sxs-lookup"><span data-stu-id="0ff64-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="0ff64-114">Isso significa que as implantações de política com a Política de Grupo, Microsoft Endpoint Configuration Manager ou Microsoft Intune podem substituir as alterações feitas com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ff64-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="0ff64-115">Você pode [configurar quais configurações podem ser substituidas localmente com substituições de política local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0ff64-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="0ff64-116">O PowerShell normalmente é instalado na pasta `%SystemRoot%\system32\WindowsPowerShell` .</span><span class="sxs-lookup"><span data-stu-id="0ff64-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="0ff64-117">Usar Microsoft Defender Antivírus cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ff64-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="0ff64-118">Na barra Windows de pesquisa, digite **powershell**.</span><span class="sxs-lookup"><span data-stu-id="0ff64-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="0ff64-119">Selecione **Windows PowerShell** dos resultados para abrir a interface.</span><span class="sxs-lookup"><span data-stu-id="0ff64-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="0ff64-120">Insira o comando do PowerShell e todos os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0ff64-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="0ff64-121">Talvez seja necessário abrir o PowerShell no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="0ff64-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="0ff64-122">Clique com o botão direito do mouse no item no menu Iniciar, clique em **Executar como administrador** e clique em **Sim** no prompt de permissões.</span><span class="sxs-lookup"><span data-stu-id="0ff64-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="0ff64-123">Para abrir a ajuda online para qualquer um dos cmdlets, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0ff64-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="0ff64-124">Omita o `-online` parâmetro para obter ajuda em cache local.</span><span class="sxs-lookup"><span data-stu-id="0ff64-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ff64-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0ff64-125">Related topics</span></span>

- [<span data-ttu-id="0ff64-126">Tópicos de referência para ferramentas de gerenciamento e configuração</span><span class="sxs-lookup"><span data-stu-id="0ff64-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0ff64-127">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="0ff64-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="0ff64-128">Microsoft Defender Antivírus Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0ff64-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)