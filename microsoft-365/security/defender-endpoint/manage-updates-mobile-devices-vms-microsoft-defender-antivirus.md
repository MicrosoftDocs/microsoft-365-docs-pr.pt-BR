---
title: Definir como os dispositivos móveis são atualizados pelo Microsoft Defender Antivírus
description: Gerencie como dispositivos móveis, como laptops, devem ser atualizados com atualizações de proteção do Microsoft Defender Antivírus.
keywords: atualizações, proteção, agendar atualizações, bateria, dispositivo móvel, laptop, bloco de anotações, aceitação, microsoft update, wsus, override
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
ms.openlocfilehash: 826e1456de2aadf4031a91e30925a1e771d44f70
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765582"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="809a0-104">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="809a0-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="809a0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="809a0-105">**Applies to:**</span></span>

- [<span data-ttu-id="809a0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="809a0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="809a0-107">Dispositivos móveis e VMs podem exigir mais configuração para garantir que o desempenho não seja afetado pelas atualizações.</span><span class="sxs-lookup"><span data-stu-id="809a0-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="809a0-108">Há duas configurações úteis para esses dispositivos:</span><span class="sxs-lookup"><span data-stu-id="809a0-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="809a0-109">Optar pelo Microsoft Update em computadores móveis sem uma conexão WSUS</span><span class="sxs-lookup"><span data-stu-id="809a0-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="809a0-110">Impedir atualizações de inteligência de segurança ao executar na energia da bateria</span><span class="sxs-lookup"><span data-stu-id="809a0-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="809a0-111">Os artigos a seguir também podem ser úteis nessas situações:</span><span class="sxs-lookup"><span data-stu-id="809a0-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="809a0-112">Configurando verificações agendadas e de catch-up</span><span class="sxs-lookup"><span data-stu-id="809a0-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="809a0-113">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="809a0-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="809a0-114">Guia de implantação do Microsoft Defender Antivírus em um ambiente virtual de área de trabalho (VDI)</span><span class="sxs-lookup"><span data-stu-id="809a0-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="809a0-115">Optar pelo Microsoft Update em computadores móveis sem uma conexão WSUS</span><span class="sxs-lookup"><span data-stu-id="809a0-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="809a0-116">Você pode usar o Microsoft Update para manter a inteligência de segurança em dispositivos móveis executando o Microsoft Defender Antivírus atualizada quando eles não estão conectados à rede corporativa ou não têm uma conexão WSUS.</span><span class="sxs-lookup"><span data-stu-id="809a0-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="809a0-117">Isso significa que as atualizações de proteção podem ser entregues a dispositivos (por meio do Microsoft Update) mesmo que você tenha definido o WSUS para substituir o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="809a0-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="809a0-118">Você pode optar pelo Microsoft Update no dispositivo móvel de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="809a0-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="809a0-119">Altere a configuração com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="809a0-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="809a0-120">Use um VBScript para criar um script e execute-o em cada computador em sua rede.</span><span class="sxs-lookup"><span data-stu-id="809a0-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="809a0-121">Opte manualmente por todos os computadores em sua rede por meio do menu **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="809a0-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="809a0-122">Usar a Política de Grupo para optar pelo Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="809a0-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="809a0-123">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="809a0-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="809a0-124">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="809a0-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="809a0-125">Selecione **Políticas** e **modelos administrativos.**</span><span class="sxs-lookup"><span data-stu-id="809a0-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="809a0-126">Expanda a árvore para **componentes do Windows** Atualizações de Assinatura do  >  **Microsoft Defender**  >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="809a0-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="809a0-127">Definir **Permitir atualizações de inteligência de segurança do Microsoft Update** como **Habilitado** e selecione  **OK**.</span><span class="sxs-lookup"><span data-stu-id="809a0-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="809a0-128">Usar um VBScript para optar pelo Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="809a0-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="809a0-129">Use as instruções no artigo do MSDN [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) para criar o VBScript.</span><span class="sxs-lookup"><span data-stu-id="809a0-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="809a0-130">Execute o VBScript criado em cada computador em sua rede.</span><span class="sxs-lookup"><span data-stu-id="809a0-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="809a0-131">Optar manualmente pelo Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="809a0-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="809a0-132">Abra **o Windows Update** no Update **&** configurações de segurança no computador em que você deseja optar.</span><span class="sxs-lookup"><span data-stu-id="809a0-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="809a0-133">Selecione **Opções** avançadas.</span><span class="sxs-lookup"><span data-stu-id="809a0-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="809a0-134">Marque a caixa de seleção Para **me atualizar para outros produtos Microsoft quando atualizar o Windows**.</span><span class="sxs-lookup"><span data-stu-id="809a0-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="809a0-135">Impedir atualizações de inteligência de segurança ao executar na energia da bateria</span><span class="sxs-lookup"><span data-stu-id="809a0-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="809a0-136">Você pode configurar o Microsoft Defender Antivírus para baixar apenas atualizações de proteção quando o computador estiver conectado a uma fonte de energia com fio.</span><span class="sxs-lookup"><span data-stu-id="809a0-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="809a0-137">Usar a Política de Grupo para impedir atualizações de inteligência de segurança na energia da bateria</span><span class="sxs-lookup"><span data-stu-id="809a0-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="809a0-138">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))escolha o Objeto de Política de Grupo que você deseja configurar e abra-o para edição.</span><span class="sxs-lookup"><span data-stu-id="809a0-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="809a0-139">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="809a0-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="809a0-140">Selecione **Políticas** e **modelos administrativos.**</span><span class="sxs-lookup"><span data-stu-id="809a0-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="809a0-141">Expanda a árvore para **componentes** do Windows Atualizações de Assinatura do  >  **Microsoft Defender**  >  **Antivírus** e,  em seguida, de definir Permitir atualizações de inteligência de segurança ao executar a energia da bateria como **Desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="809a0-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="809a0-142">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="809a0-142">Then select **OK**.</span></span> 

<span data-ttu-id="809a0-143">Essa ação impede que as atualizações de proteção baixem quando o computador está com bateria.</span><span class="sxs-lookup"><span data-stu-id="809a0-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="809a0-144">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="809a0-144">Related articles</span></span>

- [<span data-ttu-id="809a0-145">Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="809a0-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="809a0-146">Atualizar e gerenciar o Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="809a0-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)