---
title: Especificar o nível de proteção fornecido na nuvem para o Microsoft Defender Antivírus
description: De definir seu nível de proteção entregue na nuvem para o Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, nuvem, agressividade, nível de proteção
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274899"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="6f5c4-104">Especificar o nível de proteção fornecida na nuvem</span><span class="sxs-lookup"><span data-stu-id="6f5c4-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6f5c4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6f5c4-105">**Applies to:**</span></span>

- [<span data-ttu-id="6f5c4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6f5c4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6f5c4-107">Você pode especificar seu nível de proteção entregue na nuvem oferecido pelo Microsoft Defender Antivírus usando o Microsoft Endpoint Manager (recomendado) ou a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="6f5c4-108">A proteção em nuvem não é simplesmente proteção para arquivos armazenados na nuvem.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="6f5c4-109">O serviço de nuvem do Microsoft Defender Antivírus é um mecanismo para fornecer proteção atualizada para sua rede e dispositivos (também chamados de pontos de extremidade).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="6f5c4-110">A proteção na nuvem com o Microsoft Defender Antivírus usa recursos distribuídos e aprendizado de máquina para oferecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="6f5c4-111">O Microsoft Intune e o Microsoft Endpoint Manager agora fazem parte do [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="6f5c4-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="6f5c4-112">Usar o Microsoft Endpoint Manager para especificar o nível de proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="6f5c4-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="6f5c4-113">Vá para o Centro de administração do Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="6f5c4-114">Escolha **Endpoint security**  >  **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="6f5c4-115">Selecione um perfil antivírus.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-115">Select an antivirus profile.</span></span> <span data-ttu-id="6f5c4-116">(Se você ainda não tiver um ou se quiser criar um novo perfil, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="6f5c4-117">Selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-117">Select **Properties**.</span></span> <span data-ttu-id="6f5c4-118">Em seguida, ao lado **das configurações,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="6f5c4-119">Expanda **a proteção na** nuvem e, em seguida, na lista de níveis de proteção entregues na nuvem, selecione um dos seguintes: </span><span class="sxs-lookup"><span data-stu-id="6f5c4-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="6f5c4-120">**Alto**: aplica um nível forte de detecção.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="6f5c4-121">**Alta a** mais : usa **o nível** Alto e aplica medidas de proteção adicionais (pode afetar o desempenho do cliente).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="6f5c4-122">**Tolerância zero**: bloqueia todos os executáveis desconhecidos.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="6f5c4-123">Escolha **Revisar + salvar** e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="6f5c4-124">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="6f5c4-124">Need some help?</span></span> <span data-ttu-id="6f5c4-125">Consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-125">See the following resources:</span></span>
> - [<span data-ttu-id="6f5c4-126">Configurar a Proteção de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6f5c4-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="6f5c4-127">Adicionar configurações de proteção de ponto de extremidade no Intune</span><span class="sxs-lookup"><span data-stu-id="6f5c4-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="6f5c4-128">Usar a Política de Grupo para especificar o nível de proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="6f5c4-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="6f5c4-129">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="6f5c4-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="6f5c4-130">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="6f5c4-131">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do Computador  >  **Modelos administrativos.**</span><span class="sxs-lookup"><span data-stu-id="6f5c4-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="6f5c4-132">Expanda a árvore para **Componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="6f5c4-133">Clique duas vezes na **configuração Selecionar nível** de proteção na nuvem e des ajuste-o **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="6f5c4-134">Selecione o nível de proteção:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-134">Select the level of protection:</span></span>
    - <span data-ttu-id="6f5c4-135">**O nível de bloqueio padrão** fornece uma detecção forte sem aumentar o risco de detectar arquivos legítimos.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="6f5c4-136">**O nível de bloqueio moderado** fornece apenas moderado para detecções de alta confiança</span><span class="sxs-lookup"><span data-stu-id="6f5c4-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="6f5c4-137">**Alto nível de bloqueio** aplica um alto nível de detecção ao otimizar o desempenho do cliente (mas também pode dar uma maior chance de falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="6f5c4-138">**Alto + nível de bloqueio** aplica medidas de proteção adicionais (pode afetar o desempenho do cliente e aumentar a chance de falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="6f5c4-139">**O nível de bloqueio de tolerância** zero bloqueia todos os executáveis desconhecidos.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="6f5c4-140">Embora improvável, definir essa opção como **Alto** ou Alto **+** pode fazer com que alguns arquivos legítimos sejam detectados (embora você tenha a opção de desbloquear ou contestar essa detecção).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="6f5c4-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-141">Click **OK**.</span></span>

7. <span data-ttu-id="6f5c4-142">Implante seu objeto de Política de Grupo atualizado.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="6f5c4-143">Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="6f5c4-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="6f5c4-144">Você está usando Objetos de Política de Grupo no local?</span><span class="sxs-lookup"><span data-stu-id="6f5c4-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="6f5c4-145">Veja como eles se traduzem na nuvem.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-145">See how they translate in the cloud.</span></span> <span data-ttu-id="6f5c4-146">Analisar seus objetos de política de grupo local usando análise de Política de Grupo [no Microsoft Endpoint Manager - Visualização](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="6f5c4-147">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="6f5c4-147">Related articles</span></span>

- [<span data-ttu-id="6f5c4-148">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f5c4-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="6f5c4-149">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="6f5c4-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6f5c4-150">Como criar e implantar políticas antimalware: serviço de proteção na nuvem</span><span class="sxs-lookup"><span data-stu-id="6f5c4-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)