---
title: Configurar o período Microsoft Defender Antivírus tempo de bloqueio de nuvem
description: Você pode configurar por quanto Microsoft Defender Antivírus impedirá que um arquivo seja executado enquanto aguarda uma determinação na nuvem.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, nuvem, tempo decoro, bloqueio, ponto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789082"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="52a2b-104">Configurar o período de tempo limite de bloqueio da nuvem</span><span class="sxs-lookup"><span data-stu-id="52a2b-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="52a2b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="52a2b-105">**Applies to:**</span></span>

- [<span data-ttu-id="52a2b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="52a2b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="52a2b-107">Quando Microsoft Defender Antivírus um arquivo suspeito, ele pode impedir que o arquivo seja executado enquanto ele consulta o serviço Microsoft Defender Antivírus [nuvem](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="52a2b-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="52a2b-108">O período padrão em que o arquivo é [bloqueado](configure-block-at-first-sight-microsoft-defender-antivirus.md) é de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="52a2b-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="52a2b-109">Se você for um administrador de segurança, poderá especificar mais tempo para aguardar antes que o arquivo possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="52a2b-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="52a2b-110">Estender o período de tempo de tempo de bloqueio da nuvem pode ajudar a garantir que haja tempo suficiente para receber uma determinação adequada do serviço Microsoft Defender Antivírus nuvem.</span><span class="sxs-lookup"><span data-stu-id="52a2b-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="52a2b-111">Pré-requisitos para usar o tempo de tempo de bloqueio estendido na nuvem</span><span class="sxs-lookup"><span data-stu-id="52a2b-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="52a2b-112">[Bloqueie à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) e seus pré-requisitos devem ser habilitados antes que você possa especificar um período de tempo de tempo estendido.</span><span class="sxs-lookup"><span data-stu-id="52a2b-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="52a2b-113">Especifique o período de tempo Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="52a2b-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="52a2b-114">Você pode especificar o período de tempo de bloqueio da nuvem com uma política de segurança do ponto de extremidade [em Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span><span class="sxs-lookup"><span data-stu-id="52a2b-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="52a2b-115">Vá para o Endpoint Manager de administração ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="52a2b-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="52a2b-116">Selecione **Segurança do ponto de** extremidade e, em **Gerenciar,** escolha **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="52a2b-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="52a2b-117">Selecione (ou crie) uma política de antivírus.</span><span class="sxs-lookup"><span data-stu-id="52a2b-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="52a2b-118">Na seção **Configuração de configurações,** expanda **Proteção de nuvem**.</span><span class="sxs-lookup"><span data-stu-id="52a2b-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="52a2b-119">Em seguida, na **caixa Tempo** Decoro Estendido da Nuvem do Defender em Segundos, especifique quanto mais tempo, em segundos, de 1 segundo a 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="52a2b-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="52a2b-120">O que você especificar é adicionado aos 10 segundos padrão.</span><span class="sxs-lookup"><span data-stu-id="52a2b-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="52a2b-121">(Esta etapa é opcional) Faça outras alterações em sua política de antivírus.</span><span class="sxs-lookup"><span data-stu-id="52a2b-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="52a2b-122">(Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="52a2b-122">(Need help?</span></span> <span data-ttu-id="52a2b-123">Consulte [Configurações para Microsoft Defender Antivírus política em Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span><span class="sxs-lookup"><span data-stu-id="52a2b-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="52a2b-124">Escolha **Próximo** e termine de configurar sua política.</span><span class="sxs-lookup"><span data-stu-id="52a2b-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="52a2b-125">Especificar o período de tempo de tempo estendido usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="52a2b-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="52a2b-126">Você pode usar a Política de Grupo para especificar um tempo de tempo estendido para verificações na nuvem.</span><span class="sxs-lookup"><span data-stu-id="52a2b-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="52a2b-127">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento [de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="52a2b-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="52a2b-128">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="52a2b-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="52a2b-129">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="52a2b-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="52a2b-130">Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="52a2b-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="52a2b-131">Clique duas vezes em **Configurar verificação de nuvem estendida** e certifique-se de que a opção está habilitada.</span><span class="sxs-lookup"><span data-stu-id="52a2b-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="52a2b-132">Especifique o tempo extra para impedir que o arquivo seja executado enquanto aguarda uma determinação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="52a2b-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="52a2b-133">Especifique o tempo extra, em segundos, de 1 segundo a 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="52a2b-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="52a2b-134">O que você especificar é adicionado aos 10 segundos padrão.</span><span class="sxs-lookup"><span data-stu-id="52a2b-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="52a2b-135">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="52a2b-135">Select **OK**.</span></span>

 